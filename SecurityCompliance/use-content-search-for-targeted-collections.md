---
title: Utilizzare la ricerca del contenuto in Office 365 per le raccolte di destinazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Utilizzare la ricerca del contenuto in Office 365 Security &amp; centro conformità eseguire raccolte di destinazione. Una raccolta di destinazione significa che si è certi che gli elementi risponde a un caso o elementi con privilegi si trovano in una cartella delle cassette postali o un sito specifica. Utilizzare lo script in questo articolo per ottenere l'ID della cartella o il percorso per le cartelle delle cassette postali o un sito specifiche che si desidera eseguire la ricerca.
ms.openlocfilehash: f4bb63a193a11e7467b3b296b2bdfa50657ae65a
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522287"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="54351-105">Utilizzare la ricerca del contenuto in Office 365 per le raccolte di destinazione</span><span class="sxs-lookup"><span data-stu-id="54351-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="54351-p102">La funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità non fornisce un modo diretto nell'interfaccia utente per la ricerca di cartelle specifiche cassette postali di Exchange o SharePoint e OneDrive per i siti. Tuttavia, è possibile eseguire la ricerca di cartelle specifiche (noti come una raccolta di destinazione) specificando l'ID della cartella o il percorso nella sintassi di query ricerca effettiva. Utilizzo di ricerca del contenuto per eseguire una raccolta di destinazione è utile quando si è certi che gli elementi risponde a un caso o elementi con privilegi si trovano in una cartella delle cassette postali o un sito specifica. È possibile utilizzare lo script in questo articolo per ottenere l'ID della cartella per le cartelle delle cassette postali o il percorso per le cartelle in SharePoint e OneDrive per sito aziendale. Quindi è possibile utilizzare l'ID della cartella o il percorso di una query di ricerca per restituire elementi disponibile nella cartella.</span><span class="sxs-lookup"><span data-stu-id="54351-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it is possible to search specific folders (called a targeted collection) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="54351-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="54351-111">Before you begin</span></span>

- <span data-ttu-id="54351-p103">È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità per eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="54351-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="54351-p104">Inoltre, è necessario essere assegnato il ruolo destinatari di posta elettronica nell'organizzazione Exchange Online. Questa operazione è necessaria per eseguire il cmdlet **Get-MailboxFolderStatistics** incluso nello script nel passaggio 1. Per impostazione predefinita, viene assegnato il ruolo destinatari di posta elettronica per i gruppi di ruoli Gestione organizzazione e gestione dei destinatari di Exchange Online. Per ulteriori informazioni sull'assegnazione di autorizzazioni in Exchange Online, vedere [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). È possibile inoltre creare un gruppo di ruoli personalizzati, assegnare il ruolo destinatari di posta elettronica e quindi aggiungere i membri che devono eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="54351-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="54351-p105">Ogni volta che si esegue lo script nel passaggio 1, viene creata una nuova sessione di PowerShell remota. È possibile utilizzare backup di tutte le remote PowerShell sessioni disponibile. Per impedire questo, è possibile eseguire il comando seguente per interrompere le sessioni di PowerShell remote attive.</span><span class="sxs-lookup"><span data-stu-id="54351-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="54351-123">Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="54351-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="54351-p106">Lo script include la gestione degli errori o molto ridotto. Lo scopo principale dello script consiste nel visualizzare un elenco di ID di cartella delle cassette postali rapidamente o percorsi da utilizzare nella sintassi della query di ricerca di una ricerca di contenuto per eseguire una raccolta di destinazione del sito.</span><span class="sxs-lookup"><span data-stu-id="54351-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="54351-p107">Lo script di esempio fornito in questo argomento non è supportato in qualsiasi programma Microsoft supporto standard o del servizio. Lo script di esempio viene fornito così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="54351-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="54351-131">Passaggio 1: Eseguire lo script per ottenere un elenco delle cartelle di una cassetta postale o sito</span><span class="sxs-lookup"><span data-stu-id="54351-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="54351-p108">Lo script che viene eseguita in questo passaggio primo verrà restituito un elenco delle cartelle delle cassette postali o SharePoint o OneDrive per le cartelle di Business e l'ID cartella corrispondente o percorso per ogni cartella. Quando si esegue questo script, verrà chiesto per le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="54351-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="54351-p109">**URL del sito o indirizzo di posta elettronica** Digitare un indirizzo di posta elettronica di depositaria per restituire un elenco delle cartelle delle cassette postali di Exchange e piega gli ID. O digitare l'URL per un sito di SharePoint o OneDrive per sito aziendale per restituire un elenco di percorsi per il sito specificato. Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="54351-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and fold IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="54351-137">**Exchange** - stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="54351-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="54351-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="54351-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="54351-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="54351-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="54351-p110">**Le credenziali dell'utente** - lo script utilizzerà le credenziali per connettersi a Exchange Online e la sicurezza &amp; centro conformità con remote PowerShell. Come indicato in precedenza, è necessario assegnare le autorizzazioni appropriate per eseguire questo script.</span><span class="sxs-lookup"><span data-stu-id="54351-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="54351-142">Per visualizzare un elenco delle cartelle delle cassette postali o i percorsi dei siti:</span><span class="sxs-lookup"><span data-stu-id="54351-142">To display a list of mailbox folders or site path names:</span></span>
  
1. <span data-ttu-id="54351-143">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `GetFolderSearchParameters.ps1`.</span><span class="sxs-lookup"><span data-stu-id="54351-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
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
          # Create a Complinace Search Action and wait for it to complete. The folders will be listed in the .Results parameter
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

2. <span data-ttu-id="54351-144">Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="54351-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="54351-145">Eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="54351-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="54351-146">Immettere le informazioni che lo script viene richiesta.</span><span class="sxs-lookup"><span data-stu-id="54351-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="54351-p111">Lo script viene visualizzato un elenco delle cartelle delle cassette postali o di una cartella del sito per l'utente specificato. Consentire a questa finestra aprire in modo che è possibile copiare un nome di un ID o il percorso di cartella e incollarlo in modo da una query di ricerca nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="54351-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="54351-p112">Invece di visualizzare un elenco delle cartelle sullo schermo del computer, è possibile indirizzare nuovamente l'output dello script da un file di testo. In questo file verrà salvato nella cartella in cui si trova lo script. Ad esempio, per reindirizzare l'output in un file di testo degli script, eseguire il comando seguente nel passaggio 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` quindi è possibile copiare una cartella ID o il percorso del file da utilizzare in una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="54351-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="54351-152">Output di script per le cartelle delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="54351-152">Script output for mailbox folders</span></span>

<span data-ttu-id="54351-p113">Se viene riprodotto cartella delle cassette postali ID, lo script si connette a Exchange Online utilizzando PowerShell remoto, esegue il cmdlet **Get-MailboxFolderStatisics** e quindi viene visualizzato l'elenco delle cartelle dalla cassetta postale specificata. Per ogni cartella nella cassetta postale, lo script viene visualizzato il nome della cartella nella colonna **FolderPath** e l'ID della cartella nella colonna **FolderQuery** . Inoltre, lo script aggiunge il prefisso dell' **ID cartella** (ovvero il nome della proprietà delle cassette postali) per l'ID della cartella. Poiché la proprietà **ID cartella** è una proprietà disponibile per la ricerca, si utilizzerà `folderid:<folderid>` in una query di ricerca nel passaggio 2 per la ricerca di tale cartella.</span><span class="sxs-lookup"><span data-stu-id="54351-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="54351-157">Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="54351-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Esempio dell'elenco delle cartelle delle cassette postali e cartelle ID restituiti dallo script.](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="54351-159">L'esempio nel passaggio 2 mostra la query utilizzata per cercare la sottocartella Elimina nella cartella elementi ripristinabili dell'utente.</span><span class="sxs-lookup"><span data-stu-id="54351-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="54351-160">Output di script per le cartelle del sito</span><span class="sxs-lookup"><span data-stu-id="54351-160">Script output for site folders</span></span>

<span data-ttu-id="54351-p114">Se viene riprodotto percorsi di SharePoint o OneDrive per i siti, lo script si connette alla protezione &amp; centro conformità tramite remote PowerShell, crea una nuova ricerca contenuto che esegue la ricerca del sito per le cartelle e quindi viene visualizzato un elenco delle cartelle nel sito specificato. Lo script viene visualizzato il nome di ogni cartella e viene aggiunto il prefisso del **percorso** (ovvero il nome della proprietà del sito) all'URL della cartella. Poiché la proprietà **path** è una proprietà disponibile per la ricerca, si utilizzerà `path:<path>` in una query di ricerca nel passaggio 2 per la ricerca di tale cartella.</span><span class="sxs-lookup"><span data-stu-id="54351-p114">If you're getting paths from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="54351-164">Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle del sito.</span><span class="sxs-lookup"><span data-stu-id="54351-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![Esempio dell'elenco dei nomi dei percorsi per le cartelle del sito restituite dallo script.](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a><span data-ttu-id="54351-166">Passaggio 2: Utilizzare un percorso o un ID di cartella per eseguire una raccolta di destinazione</span><span class="sxs-lookup"><span data-stu-id="54351-166">Step 2: Use a folder ID or path to perform a targeted collection</span></span>

<span data-ttu-id="54351-p115">Dopo aver eseguito lo script per raccogliere un elenco di ID delle cartelle o più percorsi per un utente specifico, il passaggio successivo per passare alla protezione &amp; centro conformità e creare una nuova ricerca contenuto per eseguire la ricerca di una cartella specifica. Verrà utilizzata la `folderid:<folderid>` o `path:<path>` proprietà nella query di ricerca che si configura nella casella parole chiave ricerca del contenuto (o come valore del parametro *ContentMatchQuery* se si utilizza il cmdlet **New-ComplianceSearch** ). È possibile combinare il `folderid` o `path` proprietà con altri parametri di ricerca o i criteri di ricerca. Se si include solo i `folderid` o `path` proprietà nella query, la ricerca restituisce tutti gli elementi disponibili nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="54351-p115">After you've run the script to collect a list of folder IDs or paths for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `path:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `path` property with other search parameters or search conditions. If you only include the  `folderid` or  `path` property in the query, the search will return all items located in the specified folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="54351-171">Utilizzo di `path` proprietà per la ricerca di OneDrive percorsi non restituiscono i file multimediali, ad esempio file PNG, TIFF o con estensione wav, nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="54351-171">Using the  `path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results.</span></span> 
  
1. <span data-ttu-id="54351-172">Accedere a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="54351-172">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="54351-173">Accedere a Office 365 utilizzando l'account e le credenziali utilizzate per eseguire lo script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="54351-173">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="54351-174">Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini** \> **ricerca contenuto**e quindi fare clic su **Nuovo** ![sull'icona Aggiungi](media/O365-MDM-CreatePolicy-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="54351-174">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="54351-p116">Nella pagina **Nuova ricerca**, digitare un nome relativo alla ricerca contenuto. Questo nome deve essere univoco nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="54351-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="54351-177">In **cui si desidera di aspetto**, effettuare una delle seguenti, a seconda che la ricerca di una cartella delle cassette postali o un sito:</span><span class="sxs-lookup"><span data-stu-id="54351-177">Under **Where do you want us to look**, do one of the following, based on whether your searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="54351-178">Fare clic su **Scegli cassette postali specifiche per la ricerca** e quindi aggiungere la stessa cassetta postale specificato durante l'esecuzione dello script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="54351-178">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="54351-179">Oppure</span><span class="sxs-lookup"><span data-stu-id="54351-179">Or</span></span>
    
    - <span data-ttu-id="54351-180">Fare clic su **Scegli siti specifici per la ricerca** per la ricerca e quindi aggiungere lo stesso URL del sito specificato durante l'esecuzione dello script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="54351-180">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="54351-181">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="54351-181">Click **Next**.</span></span>
    
7. <span data-ttu-id="54351-182">Nella casella parole chiave nella pagina **scegliere un'opzione di ricerca di** incollare il `folderid:<folderid>` o `path:<path>` valore che è stato restituito dallo script nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="54351-182">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `path:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="54351-183">Ad esempio, la query nella schermata seguente cercherà di qualsiasi elemento nella sottocartella Elimina nella cartella elementi ripristinabili dell'utente (il valore del `folderid` proprietà per la sottocartella Elimina è illustrato nella schermata nel passaggio 1):</span><span class="sxs-lookup"><span data-stu-id="54351-183">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![Incollare il percorso nella casella parole chiave di query di ricerca o l'ID cartella](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="54351-185">Fare clic su **Cerca** per avviare la ricerca di raccolta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="54351-185">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="54351-186">Esempi di query di ricerca per le raccolte di destinazione</span><span class="sxs-lookup"><span data-stu-id="54351-186">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="54351-p117">Di seguito sono riportati alcuni esempi dell'utilizzo di `folderid` e `path` proprietà in una query di ricerca eseguire una raccolta di destinazione. Si noti che i segnaposto viene utilizzati per `folderid:<folderid>` e `path:<path>` per risparmiare spazio.</span><span class="sxs-lookup"><span data-stu-id="54351-p117">Here are some examples of using the  `folderid` and  `path` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `path:<path>` to save space.</span></span> 
  
- <span data-ttu-id="54351-p118">In questo esempio viene eseguita la ricerca dei tre cartelle diverse della cassetta postale. È possibile utilizzare la sintassi di query seguente per cercare le cartelle nascoste nella cartella elementi recuperabili di un utente.</span><span class="sxs-lookup"><span data-stu-id="54351-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="54351-191">Questo esempio viene ricercata una cartella delle cassette postali per gli elementi che contengono una frase specifica.</span><span class="sxs-lookup"><span data-stu-id="54351-191">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="54351-192">Questo esempio viene ricercata una cartella del sito (e tutte le sottocartelle) per i documenti che contengono le lettere "Accordo di riservatezza" del titolo.</span><span class="sxs-lookup"><span data-stu-id="54351-192">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  path:<path> AND filename:nda
  ```

- <span data-ttu-id="54351-193">In questo esempio viene eseguita la ricerca una cartella del sito (e una sottocartella) per documenti non vi sono stati modificati in un intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="54351-193">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="54351-194">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="54351-194">More information</span></span>

<span data-ttu-id="54351-195">Tenere presenti i seguenti aspetti quando si utilizza lo script in questo articolo ed esegue specifiche raccolte.</span><span class="sxs-lookup"><span data-stu-id="54351-195">Keep the following things in mind when using the script in this article and performing targeted collections.</span></span>
  
- <span data-ttu-id="54351-p119">Lo script non viene rimossa alcuna cartella dai risultati. In modo che alcune cartelle elencate nei risultati potrebbero essere non ricercabili (o restituire zero elementi) in quanto contengono contenuto generato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="54351-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="54351-p120">Questo script restituisce solo le informazioni sulle cartelle per la cassetta postale principale dell'utente. Non restituisce informazioni sulle cartelle nella cassetta postale di archivio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="54351-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="54351-p121">Durante la ricerca di cartelle delle cassette postali, solo la cartella specificata (identificato dal relativo `folderid` proprietà) verrà eseguita la ricerca. Non verranno eseguita nelle sottocartelle. Per eseguire la ricerca sottocartelle, è necessario utilizzare il `folderid` per la cartella secondaria che si desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="54351-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  `folderid` for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="54351-203">Durante la ricerca di cartelle del sito, nella cartella (identificato dal relativo `path` proprietà) e tutte le sottocartelle verranno eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="54351-203">When searching site folders, the folder (identified by its  `path` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="54351-p122">Come descritto in precedenza, non è possibile utilizzare `path` proprietà per la ricerca per i file multimediali, ad esempio PNG, TIFF o i file con estensione wav, disponibile nei percorsi OneDrive. Utilizzare una diversa [proprietà site](keyword-queries-and-search-conditions.md#searchable-site-properties) per cercare i file multimediali nelle cartelle OneDrive.</span><span class="sxs-lookup"><span data-stu-id="54351-p122">As previously stated, you can't use  `path` property to search for media files, such as .png, .tiff, or .wav files, located in OneDrive locations. Use a different [site property](keyword-queries-and-search-conditions.md#searchable-site-properties) to search for media files in OneDrive folders.</span></span> 
