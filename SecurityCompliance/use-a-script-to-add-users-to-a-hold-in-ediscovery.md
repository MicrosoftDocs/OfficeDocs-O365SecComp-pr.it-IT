---
title: Utilizzare uno script per aggiungere utenti a un'esenzione in un caso eDiscovery in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: Eseguire uno script per aggiungere rapidamente le cassette postali e dei siti a un'esenzione nuova associata a un caso eDiscovery in Office 365 Security OneDrive for Business &amp; centro conformità.
ms.openlocfilehash: eb53f01b4f1b7245e1411ac470db629115eb1ef5
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530719"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-office-365-security-amp-compliance-center"></a>Utilizzare uno script per aggiungere utenti a un'esenzione in un caso eDiscovery in Office 365 Security &amp; centro conformità

La protezione di Office 365 &amp; centro conformità fornisce una quantità elevata di cmdlet di Windows PowerShell che consentono di automatizza noiose attività relative alla creazione e gestione dei casi di eDiscovery. Attualmente, utilizzando lo strumento casi eDiscovery in sicurezza &amp; centro conformità per inserire un numero elevato di percorsi di contenuti depositaria in attesa richiede tempo e preparazione. Ad esempio, prima di creare un'esenzione, è necessario raccogliere l'URL per ogni OneDrive per sito aziendale che si desidera mettere in attesa. Quindi per ogni utente che si desidera mettere in attesa, è necessario aggiungere i OneDrive per sito aziendale e delle relative cassette postali all'esenzione. Nelle future versioni di sicurezza &amp; centro conformità, per ottenere una più facile da effettuare. Nel frattempo, è possibile utilizzare lo script in questo articolo per automatizzare il processo.
  
Lo script viene richiesto per il nome di dominio di sito personale dell'organizzazione (ad esempio, **contoso** nell'URL https://contoso-my.sharepoint.com), il nome di un caso eDiscovery esistente, il nome dell'esenzione nuovo che associato al caso, un elenco di indirizzi di posta elettronica degli utenti si desidera Per mettere in attesa e una query di ricerca da utilizzare se si desidera creare un'esenzione basata su query. Lo script quindi Ottiene l'URL per OneDrive for sito aziendale per ogni utente nell'elenco, viene creato il nuovo blocco e quindi consente di aggiungere la cassetta postale e OneDrive per sito aziendale per ogni utente nell'elenco all'esenzione. Lo script genera inoltre i file di registro contenenti informazioni sulla nuova esenzione. 
  
Ecco la procedura per effettuare questa avvenire:
  
[Passaggio 1: Installare SharePoint Online Management Shell](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step1)
  
[Passaggio 2: Generare un elenco di utenti](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[Passaggio 3: Eseguire lo script per creare un'esenzione e aggiungere gli utenti](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità e un amministratore globale di SharePoint Online per eseguire lo script nel passaggio 3. Per ulteriori informazioni, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
    
- Un massimo di 1.000 cassette postali e 100 siti è possibile aggiungere a un'esenzione associata a un caso eDiscovery in sicurezza &amp; centro conformità. Presupponendo che tutti gli utenti che si desidera mettere in attesa con una OneDrive per sito aziendale, è possibile aggiungere un massimo di 100 utenti a un'esenzione utilizzando lo script in questo articolo. 
    
- Assicurarsi di salvare l'elenco degli utenti creata nel passaggio 2 e lo script nel passaggio 3 nella stessa cartella. Che verranno rendono più semplice eseguire lo script.
    
- Lo script aggiunge all'elenco degli utenti a un'esenzione nuova associato a un caso esistente. Assicurarsi che si desidera associare all'esenzione con viene creato prima di eseguire lo script.
    
- Lo script include la gestione degli errori o molto ridotto. Lo scopo principale sia rapido e semplice posizionare la cassetta postale e OneDrive per sito Business di ogni utente in attesa.
    
- Gli script di esempio forniti in questo argomento non sono supportati in qualsiasi programma Microsoft supporto standard o del servizio. Esempi di script vengono forniti così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Passaggio 1: Installare SharePoint Online Management Shell

Il primo passaggio consiste per installare SharePoint Online Management Shell se non è già installato nel computer locale. Non è necessario utilizzare la shell di questa procedura, ma è necessario installarlo perché contiene prerequisiti necessari per lo script che viene eseguita nel passaggio 3. Questi prerequisiti consentono lo script comunicare con SharePoint Online per ottenere l'URL di OneDrive per i siti.
  
Passare a [impostare l'ambiente di SharePoint Online Management Shell di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286318) ed eseguire il passaggio 1 e il passaggio 2 per installare SharePoint Online Management Shell sul computer locale. 

## <a name="step-2-generate-a-list-of-users"></a>Passaggio 2: Generare un elenco di utenti
<a name="step2"> </a>

Lo script nel passaggio 3 verrà creata un'esenzione associata a un caso eDiscovery e Aggiungi le cassette postali e OneDrive per i siti di un elenco di utenti all'esenzione. È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure è possibile eseguire un comando di Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file (nella stessa cartella in cui verrà salvare lo script nel passaggio 3).
  
Ecco un comando PowerShell (che viene eseguita utilizzando PowerShell remoto connesso all'organizzazione Exchange Online) per ottenere un elenco di indirizzi di posta elettronica di tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominata HoldUsers.txt.
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Dopo aver eseguito questo comando, aprire il file di testo e rimuovere l'intestazione che contiene il nome della proprietà, `PrimarySmtpAddress`. Rimuovere tutti gli indirizzi di posta elettronica ad eccezione di quelli per gli utenti che si desidera aggiungere all'esenzione che verrà creata nel passaggio 3. Verificare che non sono presenti righe vuote prima o dopo l'elenco di indirizzi di posta elettronica.
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Passaggio 3: Eseguire lo script per creare un'esenzione e aggiungere gli utenti
<a name="step3"> </a>

Quando si esegue lo script in questo passaggio, verrà chiesto per le informazioni seguenti. Assicurarsi di disporre di tali informazioni pronte prima di eseguire lo script.
  
- **Le credenziali dell'utente** - lo script utilizzeranno le credenziali per connettersi alla protezione di &amp; centro conformità con remote PowerShell. Utilizza anche queste credenziali per accedere a SharePoint Online per ottenere il OneDrive per Business URL per l'elenco di utenti.
    
- **Nome del dominio MySite** - MySite il dominio è il dominio che contiene tutte le OneDrive per i siti all'interno dell'organizzazione. Ad esempio, se l'URL per il dominio del sito personale è **https://contoso-my.sharepoint.com**, quindi immettere `contoso` quando viene richiesto per il nome del dominio sito personale. 
    
- **Nome del case** - il nome di un caso esistente. Lo script verrà creato un nuovo blocco associato in questo caso.
    
- **Nome dell'esenzione** - nome dell'esenzione dello script verranno creati e associare il caso specificato.
    
- **Query di ricerca per una query basata su conservazione** - è possibile creare un'esenzione basata su query in modo che solo il contenuto che soddisfa i criteri di ricerca specificata viene messa in attesa. Per mettere tutti i contenuti in attesa, premere **INVIO** quando l'utente viene richiesto di una query di ricerca. 
    
- **Per attivare l'archiviazione o meno** - è possibile avere attivare la conservazione dopo averlo creato o è possibile impostare lo script creare esenzione senza abilitare lo script. Se non è attiva la conservazione lo script, è possibile attivarlo più avanti in sicurezza &amp; centro conformità oppure eseguire i comandi di PowerShell seguenti: 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Nome del file di testo con l'elenco di utenti** - il nome del file di testo del passaggio 2 che contiene l'elenco di utenti da aggiungere all'esenzione. Se il file si trova nella stessa cartella in cui lo script, digitare il nome del file (ad esempio HoldUsers.txt). Se il file di testo in un'altra cartella, digitare il percorso completo del file.
    
Dopo aver raccolto le informazioni che chieda è per lo script, il passaggio finale consiste nell'eseguire lo script per creare il nuovo blocco e aggiungervi gli utenti.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `AddUsersToHold.ps1`.
    
  ```
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Office 365 Security &amp; Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Office 365 Security &amp; Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
      }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to http://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.
    
3. Eseguire lo script. Per esempio:
    
      ```
    .\AddUsersToHold.ps1
      ```

4. Immettere le informazioni che lo script viene richiesta.
    
    Lo script si connette alla sicurezza e conformità centro PowerShell, quindi crea il nuovo blocco nel caso di eDiscovery e aggiunge le cassette postali e OneDrive for Business per gli utenti nell'elenco. Consente di passare al caso della pagina di **eDiscovery** in sicurezza &amp; centro conformità per visualizzare il nuovo blocco. 
    
Al termine dello script in esecuzione, consente di creare i seguenti file di registro e di salvarli nella cartella in cui si trova lo script.
  
- **LocationsOnHold.txt** - contiene un elenco delle cassette postali e OneDrive per i siti di Business che lo script correttamente messo in attesa.
    
- **LocationsNotOnHold.txt** - contiene un elenco delle cassette postali e OneDrive per i siti di Business che lo script non è stato inserito in attesa. Se un utente dispone di una cassetta postale, ma non un OneDrive per sito aziendale, l'utente verrà incluso nell'elenco di OneDrive per i siti che non sono state messa in attesa.
    
- **GetCaseHoldPolicy.txt** - contiene l'output del cmdlet **Get-CaseHoldPolicy** per il nuovo blocco di script è stato eseguito dopo aver creato il nuovo blocco. Le informazioni restituite da questo cmdlet includono un elenco di utenti con cassette postali e OneDrive per i siti vengono posizionati in attesa e indica se l'archiviazione è abilitata o disabilitata. 
    
- **GetCaseHoldRule.txt** - contiene l'output del cmdlet **Get-CaseHoldRule** per il nuovo blocco di script è stato eseguito dopo aver creato il nuovo blocco. Le informazioni restituite da questo cmdlet includono la query di ricerca, se lo script è stato utilizzato per creare un'esenzione basata su query. 
