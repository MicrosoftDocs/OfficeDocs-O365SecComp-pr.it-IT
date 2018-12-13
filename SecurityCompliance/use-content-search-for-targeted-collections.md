---
title: Utilizzare la ricerca del contenuto in Office 365 per le raccolte di destinazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Utilizzare la ricerca del contenuto in Office 365 Security &amp; centro conformità eseguire raccolte di destinazione. Una raccolta di destinazione significa che si è certi che gli elementi risponde a un caso o elementi con privilegi si trovano in una cartella delle cassette postali o un sito specifica. Utilizzare lo script in questo articolo per ottenere l'ID della cartella o il percorso per le cartelle delle cassette postali o un sito specifiche che si desidera eseguire la ricerca.
ms.openlocfilehash: 094fa4de4b8de9782a9bafb2eb8fb6ef3c52b46b
ms.sourcegitcommit: 06ae71741875f604bcc7a4e01b0b62cc768cbe97
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/13/2018
ms.locfileid: "27245063"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>Utilizzare la ricerca del contenuto in Office 365 per le raccolte di destinazione

La funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità non fornisce un modo diretto nell'interfaccia utente per la ricerca di cartelle specifiche cassette postali di Exchange o SharePoint e OneDrive per i siti. Tuttavia, è possibile eseguire la ricerca di cartelle specifiche (noti come una *raccolta di destinazione*) specificando l'ID della cartella o il percorso nella sintassi di query ricerca effettiva. Utilizzo di ricerca del contenuto per eseguire una raccolta di destinazione è utile quando si è certi che gli elementi risponde a un caso o elementi con privilegi si trovano in una cartella delle cassette postali o un sito specifica. È possibile utilizzare lo script in questo articolo per ottenere l'ID della cartella per le cartelle delle cassette postali o il percorso per le cartelle in SharePoint e OneDrive per sito aziendale. Quindi è possibile utilizzare l'ID della cartella o il percorso di una query di ricerca per restituire elementi disponibile nella cartella.
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità per eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
    
    Inoltre, è necessario essere assegnato il ruolo destinatari di posta elettronica nell'organizzazione Exchange Online. Questa operazione è necessaria per eseguire il cmdlet **Get-MailboxFolderStatistics** incluso nello script nel passaggio 1. Per impostazione predefinita, viene assegnato il ruolo destinatari di posta elettronica per i gruppi di ruoli Gestione organizzazione e gestione dei destinatari di Exchange Online. Per ulteriori informazioni sull'assegnazione di autorizzazioni in Exchange Online, vedere [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). È possibile inoltre creare un gruppo di ruoli personalizzati, assegnare il ruolo destinatari di posta elettronica e quindi aggiungere i membri che devono eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).
    
- Ogni volta che si esegue lo script nel passaggio 1, viene creata una nuova sessione di PowerShell remota. È possibile utilizzare backup di tutte le remote PowerShell sessioni disponibile. Per impedire questo, è possibile eseguire il comando seguente per interrompere le sessioni di PowerShell remote attive.
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Lo script include la gestione degli errori o molto ridotto. Lo scopo principale dello script consiste nel visualizzare un elenco di ID di cartella delle cassette postali rapidamente o percorsi da utilizzare nella sintassi della query di ricerca di una ricerca di contenuto per eseguire una raccolta di destinazione del sito.
    
- Lo script di esempio fornito in questo argomento non è supportato in qualsiasi programma Microsoft supporto standard o del servizio. Lo script di esempio viene fornito così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Passaggio 1: Eseguire lo script per ottenere un elenco delle cartelle di una cassetta postale o sito

Lo script che viene eseguita in questo passaggio primo verrà restituito un elenco delle cartelle delle cassette postali o SharePoint o OneDrive per le cartelle di Business e l'ID cartella corrispondente o percorso per ogni cartella. Quando si esegue questo script, verrà chiesto per le informazioni seguenti.
  
- **URL del sito o indirizzo di posta elettronica** Digitare un indirizzo di posta elettronica di depositaria per restituire un elenco di cartelle delle cassette postali di Exchange e ID di cartella. O digitare l'URL per un sito di SharePoint o OneDrive per sito aziendale per restituire un elenco di percorsi per il sito specificato. Di seguito sono riportati alcuni esempi: 
    
  - **Exchange** - stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Le credenziali dell'utente** - lo script utilizzerà le credenziali per connettersi a Exchange Online e la sicurezza &amp; centro conformità con remote PowerShell. Come indicato in precedenza, è necessario assegnare le autorizzazioni appropriate per eseguire questo script.
    
Per visualizzare un elenco delle cartelle delle cassette postali o i percorsi dei siti:
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `GetFolderSearchParameters.ps1`.
    
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

2. Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.
    
3. Eseguire lo script. Per esempio:
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. Immettere le informazioni che lo script viene richiesta.
    
    Lo script viene visualizzato un elenco delle cartelle delle cassette postali o di una cartella del sito per l'utente specificato. Consentire a questa finestra aprire in modo che è possibile copiare un nome di un ID o il percorso di cartella e incollarlo in modo da una query di ricerca nel passaggio 2.
    
    > [!TIP]
    > Invece di visualizzare un elenco delle cartelle sullo schermo del computer, è possibile indirizzare nuovamente l'output dello script da un file di testo. In questo file verrà salvato nella cartella in cui si trova lo script. Ad esempio, per reindirizzare l'output in un file di testo degli script, eseguire il comando seguente nel passaggio 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` quindi è possibile copiare una cartella ID o il percorso del file da utilizzare in una query di ricerca.
  
### <a name="script-output-for-mailbox-folders"></a>Output di script per le cartelle delle cassette postali

Se viene riprodotto cartella delle cassette postali ID, lo script si connette a Exchange Online utilizzando PowerShell remoto, esegue il cmdlet **Get-MailboxFolderStatisics** e quindi viene visualizzato l'elenco delle cartelle dalla cassetta postale specificata. Per ogni cartella nella cassetta postale, lo script viene visualizzato il nome della cartella nella colonna **FolderPath** e l'ID della cartella nella colonna **FolderQuery** . Inoltre, lo script aggiunge il prefisso dell' **ID cartella** (ovvero il nome della proprietà delle cassette postali) per l'ID della cartella. Poiché la proprietà **ID cartella** è una proprietà disponibile per la ricerca, si utilizzerà `folderid:<folderid>` in una query di ricerca nel passaggio 2 per la ricerca di tale cartella. 
  
Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle delle cassette postali.
  
![Esempio dell'elenco delle cartelle delle cassette postali e cartelle ID restituiti dallo script.](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
L'esempio nel passaggio 2 mostra la query utilizzata per cercare la sottocartella Elimina nella cartella elementi ripristinabili dell'utente.
  
### <a name="script-output-for-site-folders"></a>Output di script per le cartelle del sito

Se viene riprodotto percorsi di SharePoint o OneDrive per i siti, lo script si connette alla protezione &amp; centro conformità tramite remote PowerShell, crea una nuova ricerca contenuto che esegue la ricerca del sito per le cartelle e quindi viene visualizzato un elenco delle cartelle nel sito specificato. Lo script viene visualizzato il nome di ogni cartella e viene aggiunto il prefisso del **percorso** (ovvero il nome della proprietà del sito) all'URL della cartella. Poiché la proprietà **path** è una proprietà disponibile per la ricerca, si utilizzerà `path:<path>` in una query di ricerca nel passaggio 2 per la ricerca di tale cartella. 
  
Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle del sito.
  
![Esempio dell'elenco dei nomi dei percorsi per le cartelle del sito restituite dallo script.](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a>Passaggio 2: Utilizzare un percorso o un ID di cartella per eseguire una raccolta di destinazione

Dopo aver eseguito lo script per raccogliere un elenco di ID delle cartelle o più percorsi per un utente specifico, il passaggio successivo per passare alla protezione &amp; centro conformità e creare una nuova ricerca contenuto per eseguire la ricerca di una cartella specifica. Verrà utilizzata la `folderid:<folderid>` o `path:<path>` proprietà nella query di ricerca che si configura nella casella parole chiave ricerca del contenuto (o come valore del parametro *ContentMatchQuery* se si utilizza il cmdlet **New-ComplianceSearch** ). È possibile combinare il `folderid` o `path` proprietà con altri parametri di ricerca o i criteri di ricerca. Se si include solo i `folderid` o `path` proprietà nella query, la ricerca restituisce tutti gli elementi disponibili nella cartella specificata. 
  
> [!NOTE]
> Utilizzo di `path` proprietà per la ricerca di OneDrive percorsi non restituiscono i file multimediali, ad esempio file PNG, TIFF o con estensione wav, nei risultati della ricerca. 
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account e le credenziali utilizzate per eseguire lo script nel passaggio 1.
    
3. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini** \> **ricerca contenuto**e quindi fare clic su **Nuovo** ![sull'icona Aggiungi](media/O365-MDM-CreatePolicy-AddIcon.gif).
    
4. Nella pagina **Nuova ricerca**, digitare un nome relativo alla ricerca contenuto. Questo nome deve essere univoco nell'organizzazione. 
    
5. In **cui si desidera di aspetto**, effettuare una delle seguenti, in base a se si esegue la ricerca una cartella delle cassette postali o un sito:
    
    - Fare clic su **Scegli cassette postali specifiche per la ricerca** e quindi aggiungere la stessa cassetta postale specificato durante l'esecuzione dello script nel passaggio 1. 
    
      Oppure
    
    - Fare clic su **Scegli siti specifici per la ricerca** per la ricerca e quindi aggiungere lo stesso URL del sito specificato durante l'esecuzione dello script nel passaggio 1. 
    
6. Fare clic su **Avanti**.
    
7. Nella casella parole chiave nella pagina **scegliere un'opzione di ricerca di** incollare il `folderid:<folderid>` o `path:<path>` valore che è stato restituito dallo script nel passaggio 1. 
    
    Ad esempio, la query nella schermata seguente cercherà di qualsiasi elemento nella sottocartella Elimina nella cartella elementi ripristinabili dell'utente (il valore del `folderid` proprietà per la sottocartella Elimina è illustrato nella schermata nel passaggio 1):
    
    ![Incollare il percorso nella casella parole chiave di query di ricerca o l'ID cartella](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Fare clic su **Cerca** per avviare la ricerca di raccolta di destinazione. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Esempi di query di ricerca per le raccolte di destinazione

Di seguito sono riportati alcuni esempi dell'utilizzo di `folderid` e `path` proprietà in una query di ricerca eseguire una raccolta di destinazione. Si noti che i segnaposto viene utilizzati per `folderid:<folderid>` e `path:<path>` per risparmiare spazio. 
  
- In questo esempio viene eseguita la ricerca dei tre cartelle diverse della cassetta postale. È possibile utilizzare la sintassi di query seguente per cercare le cartelle nascoste nella cartella elementi recuperabili di un utente.
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- Questo esempio viene ricercata una cartella delle cassette postali per gli elementi che contengono una frase specifica.
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- Questo esempio viene ricercata una cartella del sito (e tutte le sottocartelle) per i documenti che contengono le lettere "Accordo di riservatezza" del titolo.
    
  ```
  path:<path> AND filename:nda
  ```

- In questo esempio viene eseguita la ricerca una cartella del sito (e una sottocartella) per documenti non vi sono stati modificati in un intervallo di date.
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>Ulteriori informazioni

Tenere presenti i seguenti aspetti quando si utilizza lo script in questo articolo per eseguire le raccolte di destinazione.
  
- Lo script non viene rimossa alcuna cartella dai risultati. In modo che alcune cartelle elencate nei risultati potrebbero essere non ricercabili (o restituire zero elementi) in quanto contengono contenuto generato dal sistema.
    
- Questo script restituisce solo le informazioni sulle cartelle per la cassetta postale principale dell'utente. Non restituisce informazioni sulle cartelle nella cassetta postale di archivio dell'utente.
    
- Durante la ricerca di cartelle delle cassette postali, solo la cartella specificata (identificato dal relativo `folderid` proprietà) verrà eseguita la ricerca. Non verranno eseguita nelle sottocartelle. Per eseguire la ricerca sottocartelle, è necessario utilizzare l'ID della cartella per la cartella secondaria che si desidera eseguire la ricerca. 
    
- Durante la ricerca di cartelle del sito, nella cartella (identificato dal relativo `path` proprietà) e tutte le sottocartelle verranno eseguita la ricerca. 
    
- Come descritto in precedenza, non è possibile utilizzare `path` proprietà per la ricerca per i file multimediali, ad esempio PNG, TIFF o i file con estensione wav, disponibile nei percorsi OneDrive. Utilizzare una diversa [proprietà site](keyword-queries-and-search-conditions.md#searchable-site-properties) per cercare i file multimediali nelle cartelle OneDrive. 

- Quando si esportano i risultati della ricerca in cui è specificato solo il `folderid` proprietà nella query di ricerca, è possibile scegliere Esporta primo opzione "tutti gli elementi, ad eccezione di quelli con un formato non riconosciuto, vengono crittografati o non indicizzati per altri motivi." Tutti gli elementi nella cartella verranno esportati sempre indipendentemente dallo stato indicizzazione perché l'ID della cartella viene sempre indicizzato.
