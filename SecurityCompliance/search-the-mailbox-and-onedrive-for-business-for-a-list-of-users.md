---
title: Usare la Ricerca contenuto per eseguire ricerche nella cassetta postale e nel sito OneDrive for Business per un elenco di utenti
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Utilizzare la ricerca del contenuto e lo script in questo articolo per cercare le cassette postali e OneDrive per i siti di Business per un gruppo di utenti.
ms.openlocfilehash: e7f16ec0ca34d9f7f6155cab7e473119de3966cb
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038169"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Usare la Ricerca contenuto per eseguire ricerche nella cassetta postale e nel sito OneDrive for Business per un elenco di utenti

La protezione di Office 365 &amp; centro conformità fornisce una serie di cmdlet di Windows PowerShell che consentono di automatizzare le attività correlate eDiscovery richiedere molto tempo. Attualmente, creazione di una ricerca di contenuto per la protezione &amp; centro conformità per la ricerca di un numero elevato di percorsi di contenuti depositaria richiede tempo e preparazione. Prima di creare una ricerca, è necessario raccogliere l'URL per ogni OneDrive per sito aziendale e quindi aggiungere le cassette postali e neDrive O di sito aziendale per la ricerca. Nelle future versioni, sarà più semplice effettuare la sicurezza &amp; centro conformità. Nel frattempo, è possibile utilizzare lo script in questo articolo per automatizzare il processo. Questo script consente di chiedere il nome del dominio di sito personale dell'organizzazione (ad esempio, **contoso** nell'URL https://contoso-my.sharepoint.com), gli indirizzi di un elenco di messaggi di posta elettronica utente, il nome della nuova ricerca contenuto e la query di ricerca da utilizzare. Lo script ottiene il OneDrive per Business URL per ogni utente nell'elenco e quindi crea e avvia una ricerca di contenuto che esegue una ricerca cassetta postale e OneDrive per sito aziendale per ogni utente nell'elenco utilizzando la query di ricerca che fornisce. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità e un amministratore globale di SharePoint Online per eseguire lo script nel passaggio 3.
    
- Assicurarsi di salvare l'elenco degli utenti creata nel passaggio 2 e lo script nel passaggio 3 nella stessa cartella. Che verranno rendono più semplice eseguire lo script.
    
- Lo script include la gestione degli errori o molto ridotto. È lo scopo principale consiste nel modo rapido e semplice cercare la cassetta postale e OneDrive sito aziendale di ogni utente.
    
- Gli script di esempio forniti in questo argomento non sono supportati in qualsiasi programma Microsoft supporto standard o del servizio. Esempi di script vengono forniti così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutti i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied garanzie, in via esemplificativa, qualsiasi implicita garanzie implicite di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Passaggio 1: Installare SharePoint Online Management Shell
<a name="step1"> </a>

Il primo passaggio consiste per installare SharePoint Online Management Shell. Non è necessario utilizzare la shell di questa procedura, ma è necessario installarlo perché contiene prerequisiti necessari per lo script che viene eseguita nel passaggio 3. Questi prerequisiti consentono lo script comunicare con SharePoint Online per ottenere l'URL di OneDrive per i siti.
  
Passare a [impostare l'ambiente di SharePoint Online Management Shell di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286318) ed eseguire il passaggio 1 e il passaggio 2 per installare SharePoint Online Management Shell.
  
## <a name="step-2-generate-a-list-of-users"></a>Passaggio 2: Generare un elenco di utenti
<a name="step2"> </a>

Lo script nel passaggio 3 verrà creata una ricerca di contenuto per eseguire la ricerca di cassette postali e gli account di OneDrive per un elenco di utenti. È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure è possibile eseguire un comando di Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file (nella stessa cartella in cui verrà salvare lo script nel passaggio 3).
  
Ecco un comando di [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) che è possibile Run per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato `Users.txt`. 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Dopo aver eseguito questo comando, è necessario aprire il file e rimuovere l'intestazione che contiene il nome della proprietà, `PrimarySmtpAddress`. Il file di testo deve contenere solo un elenco di indirizzi di posta elettronica e nessun altro elemento. Verificare che non sono presenti righe vuote prima o dopo l'elenco di indirizzi di posta elettronica.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Passaggio 3: Eseguire lo script per creare e avviare la ricerca

Quando si esegue lo script in questo passaggio, verrà chiesto per le informazioni seguenti. Assicurarsi di disporre di tali informazioni pronte prima di eseguire lo script.
  
- **Le credenziali dell'utente** - lo script utilizzerà le credenziali per accedere a SharePoint Online per ottenere il OneDrive for Business URLs e per la connessione per la protezione &amp; centro conformità con remote PowerShell. 
    
- **Nome del dominio MySite** - MySite il dominio è il dominio che contiene tutte le OneDrive per i siti all'interno dell'organizzazione. Ad esempio, se l'URL per il dominio del sito personale è **https://contoso-my.sharepoint.com**, quindi immettere `contoso` quando viene richiesto per il nome del dominio sito personale. 
    
- **Percorso del file di testo del passaggio 2** - il percorso del file di testo che è stato creato nel passaggio 2. Se il file di testo e lo script si trovano nella stessa cartella, quindi immettere il nome del file di testo. In caso contrario, immettere il percorso completo del file di testo. 
    
- **Nome della ricerca contenuto** - il nome della ricerca contenuto a cui verranno creati per lo script. 
    
- **Query di ricerca** - query di ricerca che verrà utilizzata con la ricerca del contenuto viene creato ed eseguire. Per ulteriori informazioni sulle query di ricerca, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md).


**Per eseguire lo script:**
    
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `SearchEXOOD4B.ps1`. Salvare il file nella stessa cartella a cui è stato salvato l'elenco di utenti nel passaggio 2.
    
  ```
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
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
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
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
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. Aprire Windows PowerShell e passare alla cartella a cui è stato salvato lo script e l'elenco degli utenti del passaggio 2.
    
3. Avviare lo script. Per esempio:
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. Quando richiesto per le proprie credenziali, immettere l'indirizzo di posta elettronica e la password e quindi fare clic su **OK**. 
    
5. Immettere il seguente informazioni quando viene richiesto dallo script. Digitare ogni informazione e quindi premere **INVIO**.
    
    - Il nome del dominio sito personale. 
    
    - Percorso del file di testo che contiene l'elenco di utenti.
    
    - Un nome per la ricerca del contenuto.
    
    - Query di ricerca (lasciare vuoto questo per restituire tutti gli elementi nelle posizioni contenute).
    
    Lo script ottiene l'URL per ogni OneDrive per sito aziendale e quindi crea e avvia la ricerca. È possibile eseguire il cmdlet **Get-ComplianceSearch** in sicurezza e conformità centro PowerShell per visualizzare le statistiche di ricerca e i risultati o consente di passare alla pagina di **ricerca del contenuto** in sicurezza &amp; centro conformità per visualizzare informazioni sulla ricerca. 
