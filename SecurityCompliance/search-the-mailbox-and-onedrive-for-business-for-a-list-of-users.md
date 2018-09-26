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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="c1a2b-103">Usare la Ricerca contenuto per eseguire ricerche nella cassetta postale e nel sito OneDrive for Business per un elenco di utenti</span><span class="sxs-lookup"><span data-stu-id="c1a2b-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="c1a2b-p101">La protezione di Office 365 &amp; centro conformità fornisce una serie di cmdlet di Windows PowerShell che consentono di automatizzare le attività correlate eDiscovery richiedere molto tempo. Attualmente, creazione di una ricerca di contenuto per la protezione &amp; centro conformità per la ricerca di un numero elevato di percorsi di contenuti depositaria richiede tempo e preparazione. Prima di creare una ricerca, è necessario raccogliere l'URL per ogni OneDrive per sito aziendale e quindi aggiungere le cassette postali e neDrive O di sito aziendale per la ricerca. Nelle future versioni, sarà più semplice effettuare la sicurezza &amp; centro conformità. Nel frattempo, è possibile utilizzare lo script in questo articolo per automatizzare il processo. Questo script consente di chiedere il nome del dominio di sito personale dell'organizzazione (ad esempio, **contoso** nell'URL https://contoso-my.sharepoint.com), gli indirizzi di un elenco di messaggi di posta elettronica utente, il nome della nuova ricerca contenuto e la query di ricerca da utilizzare. Lo script ottiene il OneDrive per Business URL per ogni utente nell'elenco e quindi crea e avvia una ricerca di contenuto che esegue una ricerca cassetta postale e OneDrive per sito aziendale per ogni utente nell'elenco utilizzando la query di ricerca che fornisce.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p101">The Office 365 Security &amp; Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks. Currently, creating a Content Search in the Security &amp; Compliance Center to search a large number of custodian content locations takes time and preparation. Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and O neDrive for Business site to the search. In future releases, this will be easier to do in the Security &amp; Compliance Center. Until then, you can use the script in this article to automate this process. This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use. The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c1a2b-111">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="c1a2b-111">Before you begin</span></span>

- <span data-ttu-id="c1a2b-112">È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità e un amministratore globale di SharePoint Online per eseguire lo script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="c1a2b-p102">Assicurarsi di salvare l'elenco degli utenti creata nel passaggio 2 e lo script nel passaggio 3 nella stessa cartella. Che verranno rendono più semplice eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p102">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="c1a2b-p103">Lo script include la gestione degli errori o molto ridotto. È lo scopo principale consiste nel modo rapido e semplice cercare la cassetta postale e OneDrive sito aziendale di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p103">The script includes minimal error handling. It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="c1a2b-p104">Gli script di esempio forniti in questo argomento non sono supportati in qualsiasi programma Microsoft supporto standard o del servizio. Esempi di script vengono forniti così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutti i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied garanzie, in via esemplificativa, qualsiasi implicita garanzie implicite di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="c1a2b-122">Passaggio 1: Installare SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="c1a2b-122">Step 1: Install the SharePoint Online Management Shell</span></span>
<span data-ttu-id="c1a2b-123"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="c1a2b-123"></span></span>

<span data-ttu-id="c1a2b-p105">Il primo passaggio consiste per installare SharePoint Online Management Shell. Non è necessario utilizzare la shell di questa procedura, ma è necessario installarlo perché contiene prerequisiti necessari per lo script che viene eseguita nel passaggio 3. Questi prerequisiti consentono lo script comunicare con SharePoint Online per ottenere l'URL di OneDrive per i siti.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p105">The first step is to install the SharePoint Online Management Shell. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="c1a2b-127">Passare a [impostare l'ambiente di SharePoint Online Management Shell di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286318) ed eseguire il passaggio 1 e il passaggio 2 per installare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-127">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="c1a2b-128">Passaggio 2: Generare un elenco di utenti</span><span class="sxs-lookup"><span data-stu-id="c1a2b-128">Step 2: Generate a list of users</span></span>
<span data-ttu-id="c1a2b-129"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="c1a2b-129"></span></span>

<span data-ttu-id="c1a2b-p106">Lo script nel passaggio 3 verrà creata una ricerca di contenuto per eseguire la ricerca di cassette postali e gli account di OneDrive per un elenco di utenti. È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure è possibile eseguire un comando di Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file (nella stessa cartella in cui verrà salvare lo script nel passaggio 3).</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p106">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="c1a2b-132">Ecco un comando di [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) che è possibile Run per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato `Users.txt`.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-132">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="c1a2b-p107">Dopo aver eseguito questo comando, è necessario aprire il file e rimuovere l'intestazione che contiene il nome della proprietà, `PrimarySmtpAddress`. Il file di testo deve contenere solo un elenco di indirizzi di posta elettronica e nessun altro elemento. Verificare che non sono presenti righe vuote prima o dopo l'elenco di indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p107">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`. The text file should just contain a list of email addresses, and nothing else. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="c1a2b-136">Passaggio 3: Eseguire lo script per creare e avviare la ricerca</span><span class="sxs-lookup"><span data-stu-id="c1a2b-136">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="c1a2b-p108">Quando si esegue lo script in questo passaggio, verrà chiesto per le informazioni seguenti. Assicurarsi di disporre di tali informazioni pronte prima di eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p108">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="c1a2b-139">**Le credenziali dell'utente** - lo script utilizzerà le credenziali per accedere a SharePoint Online per ottenere il OneDrive for Business URLs e per la connessione per la protezione &amp; centro conformità con remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-139">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security &amp; Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="c1a2b-p109">**Nome del dominio MySite** - MySite il dominio è il dominio che contiene tutte le OneDrive per i siti all'interno dell'organizzazione. Ad esempio, se l'URL per il dominio del sito personale è **https://contoso-my.sharepoint.com**, quindi immettere `contoso` quando viene richiesto per il nome del dominio sito personale.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p109">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="c1a2b-p110">**Percorso del file di testo del passaggio 2** - il percorso del file di testo che è stato creato nel passaggio 2. Se il file di testo e lo script si trovano nella stessa cartella, quindi immettere il nome del file di testo. In caso contrario, immettere il percorso completo del file di testo.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p110">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2. If the text file and the script are located in the same folder, then enter the name of the text file. Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="c1a2b-145">**Nome della ricerca contenuto** - il nome della ricerca contenuto a cui verranno creati per lo script.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-145">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="c1a2b-p111">**Query di ricerca** - query di ricerca che verrà utilizzata con la ricerca del contenuto viene creato ed eseguire. Per ulteriori informazioni sulle query di ricerca, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p111">**Search query** - The search query that will be used with the Content Search is created and run. For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="c1a2b-148">**Per eseguire lo script:**</span><span class="sxs-lookup"><span data-stu-id="c1a2b-148">**To run the script:**</span></span>
    
1. <span data-ttu-id="c1a2b-p112">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `SearchEXOOD4B.ps1`. Salvare il file nella stessa cartella a cui è stato salvato l'elenco di utenti nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p112">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`. Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="c1a2b-151">Aprire Windows PowerShell e passare alla cartella a cui è stato salvato lo script e l'elenco degli utenti del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-151">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="c1a2b-152">Avviare lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="c1a2b-152">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="c1a2b-153">Quando richiesto per le proprie credenziali, immettere l'indirizzo di posta elettronica e la password e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-153">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="c1a2b-p113">Immettere il seguente informazioni quando viene richiesto dallo script. Digitare ogni informazione e quindi premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p113">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="c1a2b-156">Il nome del dominio sito personale.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-156">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="c1a2b-157">Percorso del file di testo che contiene l'elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-157">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="c1a2b-158">Un nome per la ricerca del contenuto.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-158">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="c1a2b-159">Query di ricerca (lasciare vuoto questo per restituire tutti gli elementi nelle posizioni contenute).</span><span class="sxs-lookup"><span data-stu-id="c1a2b-159">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="c1a2b-p114">Lo script ottiene l'URL per ogni OneDrive per sito aziendale e quindi crea e avvia la ricerca. È possibile eseguire il cmdlet **Get-ComplianceSearch** in sicurezza e conformità centro PowerShell per visualizzare le statistiche di ricerca e i risultati o consente di passare alla pagina di **ricerca del contenuto** in sicurezza &amp; centro conformità per visualizzare informazioni sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="c1a2b-p114">The script gets the URLs for each OneDrive for Business site and then creates and starts the search. You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security &amp; Compliance Center to view information about the search.</span></span> 
