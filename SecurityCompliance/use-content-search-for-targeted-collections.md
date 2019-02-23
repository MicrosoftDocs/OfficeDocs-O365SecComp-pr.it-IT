---
title: Utilizzare la ricerca contenuto in Office 365 per le raccolte mirate
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Utilizzare la ricerca contenuto nel centro sicurezza &amp; e conformità di Office 365 per eseguire le raccolte mirate. Un insieme mirato indica che gli elementi che rispondono a un caso o a elementi privilegiati si trovano in una cassetta postale o in una cartella del sito specifica. Utilizzare lo script in questo articolo per ottenere l'ID o il percorso della cartella specifica della cassetta postale o delle cartelle del sito che si desidera ricercare.
ms.openlocfilehash: 81628c670f80053479b3b7987e8c4ece884793c6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215016"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="14e80-105">Utilizzare la ricerca contenuto in Office 365 per le raccolte mirate</span><span class="sxs-lookup"><span data-stu-id="14e80-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="14e80-p102">La funzionalità di ricerca contenuto nel centro sicurezza &amp; e conformità di Office 365 non fornisce un modo diretto nell'interfaccia utente per la ricerca di cartelle specifiche nelle cassette postAli di Exchange o nei siti di SharePoint e OneDrive for business. Tuttavia, è possibile eseguire ricerche in cartelle specifiche (denominate *insieme mirato*) specificando l'ID o il percorso della cartella nella sintassi della query di ricerca effettiva. L'utilizzo di ricerca contenuto per l'esecuzione di una raccolta mirata è utile quando si è certi che gli elementi sensibili a un caso o a elementi privilegiati si trovino in una specifica cassetta postale o cartella del sito. È possibile utilizzare lo script in questo articolo per ottenere l'ID della cartella per le cartelle delle cassette postali o il percorso delle cartelle in un sito di SharePoint e OneDrive for business. Successivamente, è possibile utilizzare l'ID o il percorso della cartella in una query di ricerca per restituire gli elementi che si trovano nella cartella.</span><span class="sxs-lookup"><span data-stu-id="14e80-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="14e80-111">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="14e80-111">Before you begin</span></span>

- <span data-ttu-id="14e80-p103">Per eseguire lo script nel passaggio 1, è necessario essere membri del gruppo di &amp; ruoli eDiscovery Manager nel centro sicurezza e conformità. Per ulteriori informazioni, vedere [assegnare le autorizzazioni di eDiscovery nel centro sicurezza &amp; e conformità di Office 365](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="14e80-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="14e80-p104">Inoltre, è necessario essere assegnati al ruolo destinatari di posta elettronica nell'organizzazione di Exchange Online. Questo è necessario per eseguire il cmdlet **Get-MailboxFolderStatistics** , incluso nello script nel passaggio 1. Per impostazione predefinita, il ruolo destinatari di posta viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione destinatari in Exchange Online. Per ulteriori informazioni sull'assegnazione delle autorizzazioni in Exchange Online, vedere [Manage Role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102). È inoltre possibile creare un gruppo di ruoli personalizzato, assegnare il ruolo destinatari di posta elettronica e quindi aggiungere i membri che devono eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="14e80-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="14e80-p105">Ogni volta che si esegue lo script nel passaggio 1, viene creata una nuova sessione di PowerShell remota. In questo modo, è possibile utilizzare tutte le sessioni remote di PowerShell disponibili. Per evitare che ciò accada, è possibile eseguire il comando riportato di seguito per disconnettere le sessioni di PowerShell remote attive.</span><span class="sxs-lookup"><span data-stu-id="14e80-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="14e80-123">Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="14e80-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="14e80-p106">Lo script include la gestione degli errori minima. Lo scopo principale dello script è la visualizzazione rapida di un elenco di ID cartella delle cassette postali o percorsi del sito che è possibile utilizzare nella sintassi delle query di ricerca di una ricerca contenuto per l'esecuzione di una raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="14e80-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="14e80-p107">Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Microsoft nega inoltre tutte le garanzie implicite, incluse, senza limitazioni, le garanzie implicite di commerciabilità o di idoneità per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script sarà responsabile per eventuali danni (compresi, senza limitazione, i danni per perdita degli utili aziendali, interruzioni aziendali, perdita di informazioni aziendali o altre perdite pecuniarie) derivanti dall'utilizzo o dall'impossibilità di utilizzare gli script di esempio o la documentazione, anche se Microsoft è stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="14e80-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="14e80-131">Passaggio 1: eseguire lo script per ottenere un elenco di cartelle per una cassetta postale o un sito</span><span class="sxs-lookup"><span data-stu-id="14e80-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="14e80-p108">Lo script eseguito in questo primo passaggio restituisce un elenco di cartelle di cassette postali o di SharePoint o OneDrive for business e l'ID o il percorso della cartella corrispondente per ogni cartella. Quando si esegue questo script, vengono richieste le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="14e80-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="14e80-p109">**Indirizzo di posta elettronica o URL del sito** Digitare un indirizzo di posta elettronica del custode per restituire un elenco di cartelle di cassette postali di Exchange e ID cartella. In alternativa, digitare l'URL di un sito di SharePoint o di un sito di OneDrive for business per restituire un elenco di percorsi per il sito specificato. Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="14e80-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="14e80-137">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="14e80-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="14e80-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="14e80-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="14e80-139">**OneDrive for business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="14e80-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="14e80-p110">**Credenziali utente** : lo script utilizzerà le credenziali per la connessione a Exchange Online e il centro &amp; sicurezza e conformità con Remote PowerShell. Come spiegato in precedenza, è necessario assegnare le autorizzazioni appropriate per eseguire correttamente lo script.</span><span class="sxs-lookup"><span data-stu-id="14e80-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="14e80-142">Per visualizzare un elenco delle cartelle delle cassette postali o dei nomi dei percorsi del sito:</span><span class="sxs-lookup"><span data-stu-id="14e80-142">To display a list of mailbox folders or site path names:</span></span>
  
1. <span data-ttu-id="14e80-143">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `GetFolderSearchParameters.ps1`.</span><span class="sxs-lookup"><span data-stu-id="14e80-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the folder paths for the site. #
  #    * In both cases, the script supplies the correct search properties (folderid: or path:)      #
  #      appended to the folder ID or path ID to use in a Content Search.               #
  # Notes:                                              #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the   #
  #      the current folder and all sub-folders are searched.                       #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                               #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.       #
  #########################################################################################################
  # Collect the target email address or SharePoint Url
  $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
  # Authenticate with Exchange Online and the Security &amp; Compliance Center (Exchange Online Protection - EOP)
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  if ($addressOrSite.IndexOf("@") -ige 0)
  {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
  }
  elseif ($addressOrSite.IndexOf("http") -ige 0)
  {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security &amp; Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "path:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
  }
  else
  {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
  }
  ```

2. <span data-ttu-id="14e80-144">Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="14e80-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="14e80-145">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="14e80-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="14e80-146">Immettere le informazioni richieste dallo script.</span><span class="sxs-lookup"><span data-stu-id="14e80-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="14e80-p111">Nello script viene visualizzato un elenco di cartelle di cassette postali o cartella del sito per l'utente specificato. Lasciare aperta la finestra in modo che sia possibile copiare un ID cartella o un nome di percorso e incollarlo in una query di ricerca nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="14e80-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="14e80-p112">Invece di visualizzare un elenco di cartelle sullo schermo del computer, è possibile reindirizzare l'output dello script in un file di testo. Questo file verrà salvato nella cartella in cui si trova lo script. Ad esempio, per reindirizzare l'output dello script in un file di testo, eseguire il comando riportato `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` di seguito nel passaggio 3: è possibile copiare un ID o un percorso di cartella dal file da utilizzare in una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="14e80-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="14e80-152">Output dello script per le cartelle delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="14e80-152">Script output for mailbox folders</span></span>

<span data-ttu-id="14e80-p113">Se si ricevono gli ID della cartella delle cassette postali, lo script si connette a Exchange Online tramite Remote PowerShell, esegue il cmdlet **Get-MailboxFolderStatisics** e quindi Visualizza l'elenco delle cartelle dalla cassetta postale specificata. Per ogni cartella della cassetta postale, nello script viene visualizzato il nome della cartella nella colonna **percorsocartella** e l'ID della cartella nella colonna **FolderQuery** . Inoltre, lo script aggiunge il prefisso di **FolderId** (che è il nome della proprietà della cassetta postale) all'ID della cartella. Poiché la proprietà **FolderId** è una proprietà ricercabile, è possibile utilizzare `folderid:<folderid>` in una query di ricerca nel passaggio 2 per eseguire una ricerca in tale cartella.</span><span class="sxs-lookup"><span data-stu-id="14e80-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="14e80-157">Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="14e80-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Esempio dell'elenco di cartelle di cassette postali e ID cartella restituiti dallo script](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="14e80-159">Nell'esempio del passaggio 2 viene illustrata la query utilizzata per eseguire la ricerca nella sottocartella riPuliture nella cartella elementi ripristinabili dell'utente.</span><span class="sxs-lookup"><span data-stu-id="14e80-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="14e80-160">Output dello script per le cartelle del sito</span><span class="sxs-lookup"><span data-stu-id="14e80-160">Script output for site folders</span></span>

<span data-ttu-id="14e80-p114">Se si ottengono percorsi da siti di SharePoint o OneDrive for business, lo script si connette al centro &amp; sicurezza e conformità tramite Remote PowerShell, crea una nuova ricerca di contenuto in cui vengono eseguite ricerche nel sito per le cartelle e quindi viene visualizzato un elenco delle cartelle. che si trova nel sito specificato. Lo script Visualizza il nome di ogni cartella e aggiunge il prefisso del **percorso** (che è il nome della proprietà del sito) all'URL della cartella. Poiché la proprietà **path** è una proprietà ricercabile, è possibile utilizzare `path:<path>` in una query di ricerca nel passaggio 2 per eseguire una ricerca in tale cartella.</span><span class="sxs-lookup"><span data-stu-id="14e80-p114">If you're getting paths from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="14e80-164">Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle del sito.</span><span class="sxs-lookup"><span data-stu-id="14e80-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![Esempio dell'elenco di nomi di percorso delle cartelle del sito restituite dallo script](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a><span data-ttu-id="14e80-166">Passaggio 2: utilizzare un ID cartella o un percorso per eseguire una raccolta di destinazione</span><span class="sxs-lookup"><span data-stu-id="14e80-166">Step 2: Use a folder ID or path to perform a targeted collection</span></span>

<span data-ttu-id="14e80-p115">Dopo aver eseguito lo script per raccogliere un elenco di ID o percorsi di cartelle per un utente specifico, il passaggio successivo per accedere al centro sicurezza &amp; e creare una nuova ricerca contenuto per eseguire la ricerca in una cartella specifica. È possibile utilizzare la `folderid:<folderid>` proprietà `path:<path>` or nella query di ricerca configurata nella casella parola chiave ricerca contenuto (o come valore per il parametro *ContentMatchQuery* se si utilizza il cmdlet **New-ComplianceSearch** ). È possibile combinare la `folderid` proprietà `path` or con altri parametri di ricerca o condizioni di ricerca. Se nella query è inclusa `folderid` solo `path` la proprietà or, la ricerca restituirà tutti gli elementi presenti nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="14e80-p115">After you've run the script to collect a list of folder IDs or paths for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `path:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `path` property with other search parameters or search conditions. If you only include the  `folderid` or  `path` property in the query, the search will return all items located in the specified folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="14e80-171">L'utilizzo `path` della proprietà per la ricerca nei percorsi di OneDrive non restituirà file multimediali, ad esempio file con estensione png, TIFF o WAV, nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="14e80-171">Using the  `path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results.</span></span> 
  
1. <span data-ttu-id="14e80-172">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="14e80-172">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="14e80-173">Accedere a Office 365 utilizzando l'account e le credenziali utilizzati per eseguire lo script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14e80-173">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="14e80-174">&amp; Nel riquadro sinistro del Centro sicurezza e conformità fare clic su \*\* &amp; \*\* \> ricerca ricerca **contenuto**e quindi su **nuova** ![icona](media/O365-MDM-CreatePolicy-AddIcon.gif)Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="14e80-174">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="14e80-p116">Nella pagina **Nuova ricerca**, digitare un nome relativo alla ricerca contenuto. Questo nome deve essere univoco nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14e80-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="14e80-177">In **dove si desidera**eseguire la ricerca, eseguire una delle operazioni seguenti, a seconda che si cerchi una cartella della cassetta postale o una cartella del sito:</span><span class="sxs-lookup"><span data-stu-id="14e80-177">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="14e80-178">Fare clic su **Scegli cassette postali specifiche da cercare** e quindi aggiungere la stessa cassetta postale specificata al momento dell'esecuzione dello script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14e80-178">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="14e80-179">Oppure</span><span class="sxs-lookup"><span data-stu-id="14e80-179">Or</span></span>
    
    - <span data-ttu-id="14e80-180">Fare clic su **Scegli siti specifici per cercare** e quindi aggiungere lo stesso URL del sito specificato durante l'esecuzione dello script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14e80-180">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="14e80-181">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="14e80-181">Click **Next**.</span></span>
    
7. <span data-ttu-id="14e80-182">Nella casella parola chiave della pagina **che cosa si desidera cercare per** la pagina, incollare il `folderid:<folderid>` valore o `path:<path>` restituito dallo script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14e80-182">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `path:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="14e80-183">Ad esempio, la query nello screenshot seguente cercherà tutti gli elementi nella sottocartella Purges nella cartella elementi ripristinabili dell'utente (il valore della `folderid` proprietà per la sottocartella Purges viene visualizzato nello screenshot del passaggio 1):</span><span class="sxs-lookup"><span data-stu-id="14e80-183">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![Incollare il FolderId o il percorso nella casella parola chiave della query di ricerca](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="14e80-185">Fare clic su **Cerca** per avviare la ricerca di raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="14e80-185">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="14e80-186">Esempi di query di ricerca per gli insiemi di destinazione</span><span class="sxs-lookup"><span data-stu-id="14e80-186">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="14e80-p117">Di seguito sono riportati alcuni esempi di `folderid` utilizzo `path` delle proprietà e in una query di ricerca per l'esecuzione di una raccolta di destinazione. Si noti che i segnaposto vengono `folderid:<folderid>` utilizzati `path:<path>` per e per risparmiare spazio.</span><span class="sxs-lookup"><span data-stu-id="14e80-p117">Here are some examples of using the  `folderid` and  `path` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `path:<path>` to save space.</span></span> 
  
- <span data-ttu-id="14e80-p118">In questo esempio vengono cercate tre cartelle di cassette postali diverse. È possibile utilizzare una sintassi di query simile per cercare le cartelle nascoste nella cartella elementi ripristinabili di un utente.</span><span class="sxs-lookup"><span data-stu-id="14e80-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="14e80-191">In questo esempio viene eseguita la ricerca di elementi che contengono una frase esatta in una cartella della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="14e80-191">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="14e80-192">In questo esempio viene eseguita una ricerca in una cartella del sito e in tutte le sottocartelle per i documenti che contengono le lettere "NDA" nel titolo.</span><span class="sxs-lookup"><span data-stu-id="14e80-192">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  path:<path> AND filename:nda
  ```

- <span data-ttu-id="14e80-193">In questo esempio viene eseguita una ricerca in una cartella del sito e in qualsiasi sottocartella per i documenti che sono stati modificati all'interno di un intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="14e80-193">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="14e80-194">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="14e80-194">More information</span></span>

<span data-ttu-id="14e80-195">Quando si utilizza lo script in questo articolo, è necessario tenere presente quanto segue per eseguire le raccolte mirate.</span><span class="sxs-lookup"><span data-stu-id="14e80-195">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="14e80-p119">Lo script non rimuove alcuna cartella dai risultati. Pertanto, alcune cartelle elencate nei risultati potrebbero non essere ricercabili (o restituire zero elementi) perché contengono contenuto generato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="14e80-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="14e80-p120">Questo script restituisce solo informazioni sulla cartella per la cassetta postale principale dell'utente. Non restituisce informazioni sulle cartelle nella cassetta postale di archiviazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="14e80-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="14e80-p121">Quando si eseguono ricerche nelle cartelle delle cassette postali, verrà eseguita `folderid` la ricerca solo nella cartella specificata (identificata dalla relativa proprietà). Le sottocartelle non verranno cercate. Per eseguire la ricerca in cartelle secondarie, è necessario utilizzare l'ID cartella per la sottocartella che si desidera ricercare.</span><span class="sxs-lookup"><span data-stu-id="14e80-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="14e80-203">Quando si esegue la ricerca nelle cartelle del sito, la `path` cartella (identificata dalla relativa proprietà) e tutte le sottocartelle verranno ricercate.</span><span class="sxs-lookup"><span data-stu-id="14e80-203">When searching site folders, the folder (identified by its  `path` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="14e80-p122">Come indicato in precedenza, non è `path` possibile utilizzare la proprietà per cercare file multimediali, ad esempio file con estensione png, TIFF o WAV, che si trovano nei percorsi di OneDrive. Utilizzare una proprietà diversa del [sito](keyword-queries-and-search-conditions.md#searchable-site-properties) per cercare i file multimediali nelle cartelle di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="14e80-p122">As previously stated, you can't use  `path` property to search for media files, such as .png, .tiff, or .wav files, located in OneDrive locations. Use a different [site property](keyword-queries-and-search-conditions.md#searchable-site-properties) to search for media files in OneDrive folders.</span></span> 

- <span data-ttu-id="14e80-p123">Quando si esportano i risultati di una ricerca in cui è `folderid` stata specificata solo la proprietà nella query di ricerca, è possibile scegliere la prima opzione di esportazione, "tutti gli elementi, esclusi quelli con formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi". Tutti gli elementi della cartella verranno sempre esportati indipendentemente dallo stato di indicizzazione, poiché l'ID della cartella è sempre indicizzato.</span><span class="sxs-lookup"><span data-stu-id="14e80-p123">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons." All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
