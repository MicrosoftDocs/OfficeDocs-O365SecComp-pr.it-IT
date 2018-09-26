---
title: Creare un rapporto di conservazioni in casi di eDiscovery in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Utilizzare lo script in questo articolo per generare un report che contiene informazioni su tutte le esenzioni associati ai casi di eDiscovery in Office 365 Security &amp; centro conformità.
ms.openlocfilehash: b6cef2824002d7e45e4f500bc6c1e9bc880cbd41
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038209"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>Creare un rapporto di conservazioni in casi di eDiscovery in Office 365
  
Lo script in questo articolo consente agli amministratori di eDiscovery e responsabili di eDiscovery generano un report che contiene informazioni su tutte le esenzioni associati ai casi di eDiscovery in Office 365 Security &amp; centro conformità. Il report contiene informazioni quali il nome del caso di un'esenzione associata, i percorsi di contenuti che restano in attesa e se la conservazione è basata su query. Se non esistono casi che non hanno alcuna esenzione, lo script creerà un report aggiuntivo con un elenco dei casi senza esenzioni.

Vedere la sezione [informazioni](#more-information) per una descrizione dettagliata delle informazioni incluse in report. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per generare un rapporto di tutti i casi di eDiscovery nell'organizzazione, è necessario essere un'amministratore di eDiscovery nell'organizzazione. Se si è una ricerca eDiscovery Manager, il report includerà solo informazioni sui casi che è possibile accedere. Per ulteriori informazioni sulle autorizzazioni di eDiscovery, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
    
- Lo script in questo articolo è la gestione degli errori o molto ridotto. Lo scopo principale consiste nel creare rapidamente report sulle esenzioni associati i casi di eDiscovery nell'organizzazione.
    
- Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a>Passaggio 1: Connessione per la protezione &amp; centro conformità utilizzando PowerShell remoto

Il primo passaggio consiste nel connettere Windows PowerShell per la protezione &amp; centro conformità per l'organizzazione.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `ConnectSCC.ps1`. 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script. 
    
3. Eseguire lo script. Per esempio:

    ```
    .\ConnectSCC.ps1
    ```
   
4. Quando richiesto per le proprie credenziali, immettere l'indirizzo di posta elettronica e la password e quindi fare clic su **OK**. 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Passaggio 2: Eseguire lo script per creare relazioni sulle esenzioni associato ai casi di eDiscovery

Dopo aver collegato alla protezione &amp; centro conformità con PowerShell remoto, il passaggio successivo consiste nel creare ed eseguire lo script che raccoglie informazioni sui casi eDiscovery nell'organizzazione. 
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio, CaseHoldsReport.ps1. 
    
  ```
#script begin
" " 
write-host "***********************************************"
write-host "   Office 365 Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" " 
#prompt users to specify a path to store the output files
$time=get-date
$Path = Read-Host 'Enter a file path to save the report to a .csv file'
$outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
$noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
#add case details to the csv file
function add-tocasereport{
Param([string]$casename,
[String]$casestatus,
[datetime]$casecreatedtime,
[string]$casemembers,
[datetime]$caseClosedDateTime,
[string]$caseclosedby,
[string]$holdname,
[String]$Holdenabled,
[string]$holdcreatedby,
[string]$holdlastmodifiedby,
[string]$ExchangeLocation,
[string]$sharePointlocation,
[string]$ContentMatchQuery,
[datetime]$holdcreatedtime,
[datetime]$holdchangedtime
)
$addRow = New-Object PSObject 
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
$allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
$allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii 
}
#get information on the cases and pass values to the case report function
" "
write-host "Gathering a list of cases and holds..."
" "
$edc =Get-ComplianceCase -ErrorAction SilentlyContinue
foreach($cc in $edc)
{
write-host "Working on case :" $cc.name
if($cc.status -eq 'Closed')
{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers 
}
else{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
$policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
if ($policies -ne $NULL)
{
foreach ($policy in $policies)
{
$rule=Get-CaseHoldRule -Policy $policy.name
add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
}
}
else{
write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
" "
[string]$cc.name | out-file -filepath $noholdsfilepath -append 
}
}
}

" "
Write-host "Script complete! Report files saved to this folder: '$Path'"
" "
#script end
  ```

2. Nella sessione di Windows PowerShell che aperto nel passaggio 1, passare alla cartella in cui è stato salvato lo script. 
    
3. Eseguire lo script. Per esempio:

    ```
    .\CaseHoldsReport.ps1
    ```

    Lo script richiesta per una cartella di destinazione in cui salvare il report. 
    
4. Digitare il percorso completo della cartella in cui salvare il report e quindi premere **INVIO**.
    
    > [!TIP]
    > Per salvare il report nella stessa cartella in cui lo script si trova in, digitare un punto (".") quando viene richiesto di una cartella di destinazione. Per salvare il report in una sottocartella della cartella in cui si trova lo script, digitare il nome della sottocartella. 
  
    Lo script inizia a raccogliere informazioni su tutti i casi di eDiscovery nell'organizzazione. Non accedere al file di report durante l'esecuzione dello script. Al termine dello script, viene visualizzato un messaggio di conferma della sessione di Windows PowerShell. Dopo che viene visualizzato questo messaggio, è possibile accedere il report nella cartella specificata nel passaggio 4. Il nome del file per il rapporto è `CaseHoldsReport<DateTimeStamp>.csv`.

    Inoltre, lo script consente inoltre di creare un rapporto con un elenco dei casi che non hanno alcuna esenzione. Il nome del file per il report è `CaseswithNoHolds<DateTimeStamp>.csv`.
    
    Di seguito è riportato un esempio dell'esecuzione dello script CaseHoldsReport.ps1. 
    
    ![L'output dopo l'esecuzione dello script CaseHoldsReport.ps1](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>Ulteriori informazioni

Nel caso contiene report che viene creato quando si esegue lo script in questo articolo contiene le informazioni seguenti relative a ogni esenzione. Come indicato in precedenza, è necessario essere un'amministratore per restituire informazioni per tutte le esenzioni all'interno dell'organizzazione di eDiscovery. Per ulteriori informazioni sui case contiene, vedere [casi di eDiscovery in Office 365 Security &amp; centro conformità](ediscovery-cases.md).
  
  - Nome dell'esenzione e il nome del caso eDiscovery associato all'esenzione.
    
  - Se il caso di eDiscovery è attivo o chiuso.
    
  - O meno l'archiviazione è abilitata o disabilitata.
    
  - I membri del caso eDiscovery associato all'esenzione. Membri maiuscole consente di visualizzare o gestire un caso, a seconda delle autorizzazioni di eDiscovery che è stato assegnati.
    
  - Data e l'ora che di creazione.
    
  - Se un caso viene chiuso, la persona che ha chiuso e l'ora e data è stata chiusa.
    
  - Le cassette postali di Exchange e SharePoint sono in attesa i percorsi dei siti.
    
  - Se la conservazione è basata su query, la sintassi di query.
    
  - L'ora e data di che creazione dell'esenzione e la persona che ha creato.
    
  - L'ora e data del che ultima modifica dell'esenzione e la persona che ha modificata.
