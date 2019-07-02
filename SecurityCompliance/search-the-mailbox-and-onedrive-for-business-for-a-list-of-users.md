---
title: Usare Ricerca contenuto per cercare un elenco di utenti nella cassetta postale e nel sito di OneDrive for Business
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Utilizzare la ricerca contenuto e lo script in questo articolo per eseguire ricerche nelle cassette postali e nei siti di OneDrive for business per un gruppo di utenti.
ms.openlocfilehash: a9ee2db0bc0fc7a4b53c58f02bcb9d16f96fc403
ms.sourcegitcommit: a6968df6e47ab5733a995f1efdc6e3676c5b5d7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "35253925"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="910ea-103">Usare Ricerca contenuto per cercare un elenco di utenti nella cassetta postale e nel sito di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="910ea-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="910ea-104">Il Centro sicurezza & conformità fornisce una serie di cmdlet di Windows PowerShell che consentono di automatizzare le attività relative a eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="910ea-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="910ea-105">Attualmente, la creazione di una ricerca di contenuto nel centro sicurezza & conformità per la ricerca di un numero elevato di posizioni di contenuto del custode richiede tempo e preparazione.</span><span class="sxs-lookup"><span data-stu-id="910ea-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="910ea-106">Prima di creare una ricerca, è necessario raccogliere l'URL per ogni sito di OneDrive for business e quindi aggiungere ogni cassetta postale e sito di OneDrive for business alla ricerca.</span><span class="sxs-lookup"><span data-stu-id="910ea-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="910ea-107">Nelle versioni future, questo sarà più facile da fare nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="910ea-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="910ea-108">Fino a quel momento, è possibile utilizzare lo script in questo articolo per automatizzare il processo.</span><span class="sxs-lookup"><span data-stu-id="910ea-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="910ea-109">Questo script richiede l'utilizzo del nome del dominio del sito Web dell'organizzazione, ad esempio **Contoso** nell'URL https://contoso-my.sharepoint.com), un elenco di indirizzi di posta elettronica utente, il nome della nuova ricerca contenuto e la query di ricerca da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="910ea-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="910ea-110">Lo script ottiene l'URL di OneDrive for business per ogni utente nell'elenco e quindi crea e avvia una ricerca di contenuto che cerca nella cassetta postale e nel sito di OneDrive for business ogni utente nell'elenco, utilizzando la query di ricerca fornita.</span><span class="sxs-lookup"><span data-stu-id="910ea-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="910ea-111">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="910ea-111">Before you begin</span></span>

- <span data-ttu-id="910ea-112">È necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & compliance e un amministratore globale di SharePoint Online per eseguire lo script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="910ea-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="910ea-113">Assicurarsi di salvare l'elenco di utenti creato nel passaggio 2 e lo script nel passaggio 3 alla stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="910ea-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="910ea-114">Questo renderà più facile eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="910ea-114">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="910ea-115">Lo script include la gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="910ea-115">The script includes minimal error handling.</span></span> <span data-ttu-id="910ea-116">Lo scopo principale è la ricerca rapida e semplice della cassetta postale e del sito di OneDrive for business di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="910ea-116">It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="910ea-117">Gli script di esempio forniti in questo argomento non sono supportati in alcun servizio o programma di supporto Microsoft standard.</span><span class="sxs-lookup"><span data-stu-id="910ea-117">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="910ea-118">Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia.</span><span class="sxs-lookup"><span data-stu-id="910ea-118">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="910ea-119">Microsoft nega inoltre tutte le garanzie di[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied, incluse, a titolo esemplificativo, le garanzie implicite di commerciabilità o di idoneità per uno scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="910ea-119">Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="910ea-120">Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente.</span><span class="sxs-lookup"><span data-stu-id="910ea-120">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="910ea-121">In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="910ea-121">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="910ea-122">Passaggio 1: Installare SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="910ea-122">Step 1: Install the SharePoint Online Management Shell</span></span>
<span data-ttu-id="910ea-123"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="910ea-123"></span></span>

<span data-ttu-id="910ea-124">Il primo passaggio consiste nell'installare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="910ea-124">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="910ea-125">Non è necessario utilizzare la shell in questa procedura, ma è necessario installarla perché contiene i prerequisiti richiesti dallo script eseguito nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="910ea-125">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="910ea-126">Questi prerequisiti consentono allo script di comunicare con SharePoint Online per ottenere gli URL per i siti di OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="910ea-126">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="910ea-127">Andare a [configurare l'ambiente di Windows PowerShell per SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkID=286318) ed eseguire il passaggio 1 e il passaggio 2 per installare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="910ea-127">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="910ea-128">Passaggio 2: generazione di un elenco di utenti</span><span class="sxs-lookup"><span data-stu-id="910ea-128">Step 2: Generate a list of users</span></span>
<span data-ttu-id="910ea-129"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="910ea-129"></span></span>

<span data-ttu-id="910ea-130">Lo script nel passaggio 3 creerà una ricerca di contenuto per cercare le cassette postali e gli account di OneDrive per un elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="910ea-130">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="910ea-131">È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure eseguire un comando in Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file (che si trova nella stessa cartella in cui verrà salvato lo script nel passaggio 3).</span><span class="sxs-lookup"><span data-stu-id="910ea-131">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="910ea-132">Di seguito è riportato un comando di [PowerShell di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283) che può essere utilizzato per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato `Users.txt`.</span><span class="sxs-lookup"><span data-stu-id="910ea-132">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="910ea-133">Dopo aver eseguito il comando, accertarsi di aprire il file e rimuovere l'intestazione che contiene il nome della proprietà `PrimarySmtpAddress`.</span><span class="sxs-lookup"><span data-stu-id="910ea-133">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="910ea-134">Il file di testo deve contenere solo un elenco di indirizzi di posta elettronica e nient'altro.</span><span class="sxs-lookup"><span data-stu-id="910ea-134">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="910ea-135">Verificare che non vi siano righe vuote prima o dopo l'elenco di indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="910ea-135">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="910ea-136">Passaggio 3: eseguire lo script per creare e avviare la ricerca</span><span class="sxs-lookup"><span data-stu-id="910ea-136">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="910ea-137">Quando si esegue lo script in questo passaggio, vengono richieste le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="910ea-137">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="910ea-138">Assicurarsi di avere queste informazioni pronte prima di eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="910ea-138">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="910ea-139">**Credenziali utente** : lo script utilizzerà le credenziali per accedere a SharePoint Online per ottenere gli URL di OneDrive for business e connettersi al centro sicurezza & conformità con Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="910ea-139">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="910ea-140">**Nome del dominio del sito Web** : il dominio del sito Web è il dominio che contiene tutti i siti di OneDrive for business nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="910ea-140">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="910ea-141">Ad esempio, se l'URL del dominio del sito Web è **https://contoso-my.sharepoint.com**, è necessario immetterlo `contoso` quando lo script richiede il nome del dominio di siti personali.</span><span class="sxs-lookup"><span data-stu-id="910ea-141">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="910ea-142">**Percorso del file di testo del passaggio 2** : il percorso del file di testo creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="910ea-142">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="910ea-143">Se il file di testo e lo script si trovano nella stessa cartella, immettere il nome del file di testo.</span><span class="sxs-lookup"><span data-stu-id="910ea-143">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="910ea-144">In caso contrario, immettere il percorso completo per il file di testo.</span><span class="sxs-lookup"><span data-stu-id="910ea-144">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="910ea-145">**Nome della ricerca di contenuto** -il nome della ricerca di contenuto che verrà creata dallo script.</span><span class="sxs-lookup"><span data-stu-id="910ea-145">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="910ea-146">**Query di ricerca** -la query di ricerca che verrà utilizzata con la ricerca di contenuto viene creata ed eseguita.</span><span class="sxs-lookup"><span data-stu-id="910ea-146">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="910ea-147">Per ulteriori informazioni sulle query di ricerca, vedere [keyword query and Search Conditions for content search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="910ea-147">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="910ea-148">**Per eseguire lo script:**</span><span class="sxs-lookup"><span data-stu-id="910ea-148">**To run the script:**</span></span>
    
1. <span data-ttu-id="910ea-149">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `SearchEXOOD4B.ps1`.</span><span class="sxs-lookup"><span data-stu-id="910ea-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="910ea-150">Salvare il file nella stessa cartella in cui è stato salvato l'elenco di utenti nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="910ea-150">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="910ea-151">Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script e l'elenco di utenti del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="910ea-151">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="910ea-152">Avviare lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="910ea-152">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="910ea-153">Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="910ea-153">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="910ea-154">Immettere le informazioni seguenti quando richiesto dallo script.</span><span class="sxs-lookup"><span data-stu-id="910ea-154">Enter following information when prompted by the script.</span></span> <span data-ttu-id="910ea-155">Digitare ogni informazione e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="910ea-155">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="910ea-156">Nome del dominio di siti personali.</span><span class="sxs-lookup"><span data-stu-id="910ea-156">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="910ea-157">Il percorso del file di testo che contiene l'elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="910ea-157">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="910ea-158">Un nome per la ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="910ea-158">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="910ea-159">La query di ricerca (lasciare vuoto questo elemento per restituire tutti gli elementi nei percorsi di contenuto).</span><span class="sxs-lookup"><span data-stu-id="910ea-159">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="910ea-160">Lo script consente di recuperare gli URL per ogni sito di OneDrive for business e quindi di creare e avviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="910ea-160">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="910ea-161">È possibile eseguire il cmdlet **Get-ComplianceSearch** in PowerShell per la sicurezza & Compliance Center per visualizzare le statistiche di ricerca e i risultati oppure andare alla pagina **Ricerca contenuto** nel centro sicurezza & conformità per visualizzare le informazioni informazioni sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="910ea-161">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span> 
