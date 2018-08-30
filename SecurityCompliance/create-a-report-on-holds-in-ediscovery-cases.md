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
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Utilizzare lo script in questo articolo per generare un report che contiene informazioni su tutte le esenzioni associati ai casi di eDiscovery in Office 365 Security &amp; centro conformità.
ms.openlocfilehash: 8bc1285f776e2b1aa0c0330c06ccffff8ce4585c
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258644"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="b84d6-103">Creare un rapporto di conservazioni in casi di eDiscovery in Office 365</span><span class="sxs-lookup"><span data-stu-id="b84d6-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="b84d6-p101">Lo script in questo articolo consente agli amministratori di eDiscovery e responsabili di eDiscovery generano un report che contiene informazioni su tutte le esenzioni associati ai casi di eDiscovery in Office 365 Security &amp; centro conformità. Il report contiene informazioni quali il nome del caso di un'esenzione associata, i percorsi di contenuti che restano in attesa e se la conservazione è basata su query. Se non esistono casi che non hanno alcuna esenzione, lo script creerà un report aggiuntivo con un elenco dei casi senza esenzioni.</span><span class="sxs-lookup"><span data-stu-id="b84d6-p101">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the Office 365 Security &amp; Compliance Center. The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based. If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="b84d6-107">Vedere la sezione [informazioni](#more-information) per una descrizione dettagliata delle informazioni incluse in report.</span><span class="sxs-lookup"><span data-stu-id="b84d6-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="b84d6-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="b84d6-108">Before you begin</span></span>

- <span data-ttu-id="b84d6-p102">Per generare un rapporto di tutti i casi di eDiscovery nell'organizzazione, è necessario essere un'amministratore di eDiscovery nell'organizzazione. Se si è una ricerca eDiscovery Manager, il report includerà solo informazioni sui casi che è possibile accedere. Per ulteriori informazioni sulle autorizzazioni di eDiscovery, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b84d6-p102">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization. If you are an eDiscovery Manager, the report will only include information about the cases that you can access. For more information about eDiscovery permissions, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="b84d6-p103">Lo script in questo articolo è la gestione degli errori o molto ridotto. Lo scopo principale consiste nel creare rapidamente report sulle esenzioni associati i casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b84d6-p103">The script in this article has minimal error handling. The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="b84d6-p104">Gli script di esempio forniti in questo argomento non sono supportati in qualsiasi programma Microsoft supporto standard o del servizio. Esempi di script vengono forniti così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="b84d6-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a><span data-ttu-id="b84d6-119">Passaggio 1: Connessione per la protezione &amp; centro conformità utilizzando PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="b84d6-119">Step 1: Connect to the Security &amp; Compliance Center using Remote PowerShell</span></span>

<span data-ttu-id="b84d6-120">Il primo passaggio consiste nel connettere Windows PowerShell per la protezione &amp; centro conformità per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b84d6-120">The first step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="b84d6-121">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `ConnectSCC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="b84d6-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="b84d6-122">Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="b84d6-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="b84d6-123">Eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="b84d6-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="b84d6-124">Quando richiesto per le proprie credenziali, immettere l'indirizzo di posta elettronica e la password e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b84d6-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="b84d6-125">Passaggio 2: Eseguire lo script per creare relazioni sulle esenzioni associato ai casi di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b84d6-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="b84d6-126">Dopo aver collegato alla protezione &amp; centro conformità con PowerShell remoto, il passaggio successivo consiste nel creare ed eseguire lo script che raccoglie informazioni sui casi eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b84d6-126">After you've connected to the Security &amp; Compliance Center with remote PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="b84d6-127">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio, CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="b84d6-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
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

2. <span data-ttu-id="b84d6-128">Nella sessione di Windows PowerShell che aperto nel passaggio 1, passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="b84d6-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="b84d6-129">Eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="b84d6-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="b84d6-130">Lo script richiesta per una cartella di destinazione in cui salvare il report.</span><span class="sxs-lookup"><span data-stu-id="b84d6-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="b84d6-131">Digitare il percorso completo della cartella in cui salvare il report e quindi premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="b84d6-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b84d6-p105">Per salvare il report nella stessa cartella in cui lo script si trova in, digitare un punto (".") quando viene richiesto di una cartella di destinazione. Per salvare il report in una sottocartella della cartella in cui si trova lo script, digitare il nome della sottocartella.</span><span class="sxs-lookup"><span data-stu-id="b84d6-p105">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder. To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="b84d6-p106">Lo script inizia a raccogliere informazioni su tutti i casi di eDiscovery nell'organizzazione. Non accedere al file di report durante l'esecuzione dello script. Al termine dello script, viene visualizzato un messaggio di conferma della sessione di Windows PowerShell. Dopo che viene visualizzato questo messaggio, è possibile accedere il report nella cartella specificata nel passaggio 4. Il nome del file per il rapporto è `CaseHoldsReport<DateTimeStamp>.csv`.</span><span class="sxs-lookup"><span data-stu-id="b84d6-p106">The script starts to collect information about all the eDiscovery cases in your organization. Don't access the report file while the script is running. After the script is complete, a confirmation message is displayed in the Windows PowerShell session. After this message is displayed, you can access the report in the folder that you specified in Step 4. The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="b84d6-p107">Inoltre, lo script consente inoltre di creare un rapporto con un elenco dei casi che non hanno alcuna esenzione. Il nome del file per il report è `CaseswithNoHolds<DateTimeStamp>.csv`.</span><span class="sxs-lookup"><span data-stu-id="b84d6-p107">Addtionally, the script also creates a report with a list of cases that don't have any holds. The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="b84d6-141">Di seguito è riportato un esempio dell'esecuzione dello script CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="b84d6-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![L'output dopo l'esecuzione dello script CaseHoldsReport.ps1](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="b84d6-143">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b84d6-143">More information</span></span>

<span data-ttu-id="b84d6-p108">Nel caso contiene report che viene creato quando si esegue lo script in questo articolo contiene le informazioni seguenti relative a ogni esenzione. Come indicato in precedenza, è necessario essere un'amministratore per restituire informazioni per tutte le esenzioni all'interno dell'organizzazione di eDiscovery. Per ulteriori informazioni sui case contiene, vedere [casi di eDiscovery in Office 365 Security &amp; centro conformità](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="b84d6-p108">The case holds report that's created when you run the script in this article contains the following information about each hold. As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization. For more information about case holds, see [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="b84d6-147">Nome dell'esenzione e il nome del caso eDiscovery associato all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="b84d6-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="b84d6-148">Se il caso di eDiscovery è attivo o chiuso.</span><span class="sxs-lookup"><span data-stu-id="b84d6-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="b84d6-149">O meno l'archiviazione è abilitata o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="b84d6-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="b84d6-p109">I membri del caso eDiscovery associato all'esenzione. Membri maiuscole consente di visualizzare o gestire un caso, a seconda delle autorizzazioni di eDiscovery che è stato assegnati.</span><span class="sxs-lookup"><span data-stu-id="b84d6-p109">The members of the eDiscovery case that the hold is associated with. Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="b84d6-152">Data e l'ora che di creazione.</span><span class="sxs-lookup"><span data-stu-id="b84d6-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="b84d6-153">Se un caso viene chiuso, la persona che ha chiuso e l'ora e data è stata chiusa.</span><span class="sxs-lookup"><span data-stu-id="b84d6-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="b84d6-154">Le cassette postali di Exchange e SharePoint sono in attesa i percorsi dei siti.</span><span class="sxs-lookup"><span data-stu-id="b84d6-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="b84d6-155">Se la conservazione è basata su query, la sintassi di query.</span><span class="sxs-lookup"><span data-stu-id="b84d6-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="b84d6-156">L'ora e data di che creazione dell'esenzione e la persona che ha creato.</span><span class="sxs-lookup"><span data-stu-id="b84d6-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="b84d6-157">L'ora e data del che ultima modifica dell'esenzione e la persona che ha modificata.</span><span class="sxs-lookup"><span data-stu-id="b84d6-157">The time and date the hold was last changed and the person who changed it.</span></span>
