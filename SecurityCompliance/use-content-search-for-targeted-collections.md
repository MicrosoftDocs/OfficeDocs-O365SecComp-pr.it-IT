---
title: Utilizzare la ricerca contenuto in Office 365 per le raccolte mirate
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Utilizzare la ricerca contenuto nel centro sicurezza &amp; e conformità di Office 365 per eseguire le raccolte mirate. Un insieme mirato indica che gli elementi che rispondono a un caso o a elementi privilegiati si trovano in una cassetta postale o in una cartella del sito specifica. Utilizzare lo script in questo articolo per ottenere l'ID o il percorso della cartella specifica della cassetta postale o delle cartelle del sito che si desidera ricercare.
ms.openlocfilehash: c6e837e2f95b4f2ae3e32344f966f096407e360e
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296929"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>Utilizzare la ricerca contenuto in Office 365 per le raccolte mirate

La funzionalità di ricerca contenuto nel centro sicurezza &amp; e conformità di Office 365 non fornisce un modo diretto nell'interfaccia utente per la ricerca di cartelle specifiche nelle cassette postAli di Exchange o nei siti di SharePoint e OneDrive for business. Tuttavia, è possibile eseguire ricerche in cartelle specifiche (denominate *insieme mirato*) specificando l'ID o il percorso della cartella nella sintassi della query di ricerca effettiva. L'utilizzo di ricerca contenuto per l'esecuzione di una raccolta mirata è utile quando si è certi che gli elementi sensibili a un caso o a elementi privilegiati si trovino in una specifica cassetta postale o cartella del sito. È possibile utilizzare lo script in questo articolo per ottenere l'ID della cartella per le cartelle delle cassette postali o il percorso delle cartelle in un sito di SharePoint e OneDrive for business. Successivamente, è possibile utilizzare l'ID o il percorso della cartella in una query di ricerca per restituire gli elementi che si trovano nella cartella.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per eseguire lo script nel passaggio 1, è necessario essere membri del gruppo di &amp; ruoli eDiscovery Manager nel centro sicurezza e conformità. Per ulteriori informazioni, vedere [assegnare le autorizzazioni di eDiscovery nel centro sicurezza &amp; e conformità di Office 365](assign-ediscovery-permissions.md).
    
    Inoltre, è necessario essere assegnati al ruolo destinatari di posta elettronica nell'organizzazione di Exchange Online. Questo è necessario per eseguire il cmdlet **Get-MailboxFolderStatistics** , incluso nello script nel passaggio 1. Per impostazione predefinita, il ruolo destinatari di posta viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione destinatari in Exchange Online. Per ulteriori informazioni sull'assegnazione delle autorizzazioni in Exchange Online, vedere [Manage Role Group Members](https://go.microsoft.com/fwlink/p/?linkid=692102). È inoltre possibile creare un gruppo di ruoli personalizzato, assegnare il ruolo destinatari di posta elettronica e quindi aggiungere i membri che devono eseguire lo script nel passaggio 1. Per ulteriori informazioni, vedere [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).
    
- Ogni volta che si esegue lo script nel passaggio 1, viene creata una nuova sessione di PowerShell remota. In questo modo, è possibile utilizzare tutte le sessioni remote di PowerShell disponibili. Per evitare che ciò accada, è possibile eseguire il comando riportato di seguito per disconnettere le sessioni di PowerShell remote attive.
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    Per ulteriori informazioni, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Lo script include la gestione degli errori minima. Lo scopo principale dello script è la visualizzazione rapida di un elenco di ID cartella delle cassette postali o percorsi del sito che è possibile utilizzare nella sintassi delle query di ricerca di una ricerca contenuto per l'esecuzione di una raccolta di destinazione.
    
- Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Microsoft nega inoltre tutte le garanzie implicite, incluse, senza limitazioni, le garanzie implicite di commerciabilità o di idoneità per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script sarà responsabile per eventuali danni (compresi, senza limitazione, i danni per perdita degli utili aziendali, interruzioni aziendali, perdita di informazioni aziendali o altre perdite pecuniarie) derivanti dall'utilizzo o dall'impossibilità di utilizzare gli script di esempio o la documentazione, anche se Microsoft è stata avvisata della possibilità di tali danni.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Passaggio 1: eseguire lo script per ottenere un elenco di cartelle per una cassetta postale o un sito

Lo script eseguito in questo primo passaggio restituisce un elenco di cartelle di cassette postali o di SharePoint o OneDrive for business e l'ID o il percorso della cartella corrispondente per ogni cartella. Quando si esegue questo script, vengono richieste le informazioni seguenti.
  
- **Indirizzo di posta elettronica o URL del sito** Digitare un indirizzo di posta elettronica del custode per restituire un elenco di cartelle di cassette postali di Exchange e ID cartella. In alternativa, digitare l'URL di un sito di SharePoint o di un sito di OneDrive for business per restituire un elenco di percorsi per il sito specificato. Di seguito sono riportati alcuni esempi: 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Credenziali utente** : lo script utilizzerà le credenziali per la connessione a Exchange Online e il centro &amp; sicurezza e conformità con Remote PowerShell. Come spiegato in precedenza, è necessario assegnare le autorizzazioni appropriate per eseguire correttamente lo script.
    
Per visualizzare un elenco delle cartelle delle cassette postali o dei nomi dei percorsi del sito:
  
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `GetFolderSearchParameters.ps1`.
    
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
    
3. Eseguire lo script; Per esempio:
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. Immettere le informazioni richieste dallo script.
    
    Nello script viene visualizzato un elenco di cartelle di cassette postali o cartella del sito per l'utente specificato. Lasciare aperta la finestra in modo che sia possibile copiare un ID cartella o un nome di percorso e incollarlo in una query di ricerca nel passaggio 2.
    
    > [!TIP]
    > Invece di visualizzare un elenco di cartelle sullo schermo del computer, è possibile reindirizzare l'output dello script in un file di testo. Questo file verrà salvato nella cartella in cui si trova lo script. Ad esempio, per reindirizzare l'output dello script in un file di testo, eseguire il comando riportato `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` di seguito nel passaggio 3: è possibile copiare un ID o un percorso di cartella dal file da utilizzare in una query di ricerca.
  
### <a name="script-output-for-mailbox-folders"></a>Output dello script per le cartelle delle cassette postali

Se si ricevono gli ID della cartella delle cassette postali, lo script si connette a Exchange Online tramite Remote PowerShell, esegue il cmdlet **Get-MailboxFolderStatisics** e quindi Visualizza l'elenco delle cartelle dalla cassetta postale specificata. Per ogni cartella della cassetta postale, nello script viene visualizzato il nome della cartella nella colonna **percorsocartella** e l'ID della cartella nella colonna **FolderQuery** . Inoltre, lo script aggiunge il prefisso di **FolderId** (che è il nome della proprietà della cassetta postale) all'ID della cartella. Poiché la proprietà **FolderId** è una proprietà ricercabile, è possibile utilizzare `folderid:<folderid>` in una query di ricerca nel passaggio 2 per eseguire una ricerca in tale cartella. 
  
Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle delle cassette postali.
  
![Esempio dell'elenco di cartelle di cassette postali e ID cartella restituiti dallo script](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
Nell'esempio del passaggio 2 viene illustrata la query utilizzata per eseguire la ricerca nella sottocartella riPuliture nella cartella elementi ripristinabili dell'utente.
  
### <a name="script-output-for-site-folders"></a>Output dello script per le cartelle del sito

Se si ottengono percorsi da siti di SharePoint o OneDrive for business, lo script si connette al centro &amp; sicurezza e conformità tramite Remote PowerShell, crea una nuova ricerca di contenuto in cui vengono eseguite ricerche nel sito per le cartelle e quindi viene visualizzato un elenco delle cartelle. che si trova nel sito specificato. Lo script Visualizza il nome di ogni cartella e aggiunge il prefisso del **percorso** (che è il nome della proprietà del sito) all'URL della cartella. Poiché la proprietà **path** è una proprietà ricercabile, è possibile utilizzare `path:<path>` in una query di ricerca nel passaggio 2 per eseguire una ricerca in tale cartella. 
  
Di seguito è riportato un esempio dell'output restituito dallo script per le cartelle del sito.
  
![Esempio dell'elenco di nomi di percorso delle cartelle del sito restituite dallo script](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a>Passaggio 2: utilizzare un ID cartella o un percorso per eseguire una raccolta di destinazione

Dopo aver eseguito lo script per raccogliere un elenco di ID o percorsi di cartelle per un utente specifico, il passaggio successivo per accedere al centro sicurezza &amp; e creare una nuova ricerca contenuto per eseguire la ricerca in una cartella specifica. È possibile utilizzare la `folderid:<folderid>` proprietà `path:<path>` or nella query di ricerca configurata nella casella parola chiave ricerca contenuto (o come valore per il parametro *ContentMatchQuery* se si utilizza il cmdlet **New-ComplianceSearch** ). È possibile combinare la `folderid` proprietà `path` or con altri parametri di ricerca o condizioni di ricerca. Se nella query è inclusa `folderid` solo `path` la proprietà or, la ricerca restituirà tutti gli elementi presenti nella cartella specificata. 
  
> [!NOTE]
> L'utilizzo `path` della proprietà per la ricerca nei percorsi di OneDrive non restituirà file multimediali, ad esempio file con estensione png, TIFF o WAV, nei risultati della ricerca. 
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account e le credenziali utilizzati per eseguire lo script nel passaggio 1.
    
3. &amp; Nel riquadro sinistro del Centro sicurezza e conformità fare clic su ** &amp; ** \> ricerca ricerca **contenuto**e quindi su **nuova** ![icona](media/O365-MDM-CreatePolicy-AddIcon.gif)Aggiungi.
    
4. Nella pagina **Nuova ricerca**, digitare un nome relativo alla ricerca contenuto. Questo nome deve essere univoco nell'organizzazione. 
    
5. In **dove si desidera**eseguire la ricerca, eseguire una delle operazioni seguenti, a seconda che si cerchi una cartella della cassetta postale o una cartella del sito:
    
    - Fare clic su **Scegli cassette postali specifiche da cercare** e quindi aggiungere la stessa cassetta postale specificata al momento dell'esecuzione dello script nel passaggio 1. 
    
      Oppure
    
    - Fare clic su **Scegli siti specifici per cercare** e quindi aggiungere lo stesso URL del sito specificato durante l'esecuzione dello script nel passaggio 1. 
    
6. Fare clic su **Avanti**.
    
7. Nella casella parola chiave della pagina **che cosa si desidera cercare per** la pagina, incollare il `folderid:<folderid>` valore o `path:<path>` restituito dallo script nel passaggio 1. 
    
    Ad esempio, la query nello screenshot seguente cercherà tutti gli elementi nella sottocartella Purges nella cartella elementi ripristinabili dell'utente (il valore della `folderid` proprietà per la sottocartella Purges viene visualizzato nello screenshot del passaggio 1):
    
    ![Incollare il FolderId o il percorso nella casella parola chiave della query di ricerca](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Fare clic su **Cerca** per avviare la ricerca di raccolta di destinazione. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Esempi di query di ricerca per gli insiemi di destinazione

Di seguito sono riportati alcuni esempi di `folderid` utilizzo `path` delle proprietà e in una query di ricerca per l'esecuzione di una raccolta di destinazione. Si noti che i segnaposto vengono `folderid:<folderid>` utilizzati `path:<path>` per e per risparmiare spazio. 
  
- In questo esempio vengono cercate tre cartelle di cassette postali diverse. È possibile utilizzare una sintassi di query simile per cercare le cartelle nascoste nella cartella elementi ripristinabili di un utente.
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- In questo esempio viene eseguita la ricerca di elementi che contengono una frase esatta in una cartella della cassetta postale.
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- In questo esempio viene eseguita una ricerca in una cartella del sito e in tutte le sottocartelle per i documenti che contengono le lettere "NDA" nel titolo.
    
  ```
  path:<path> AND filename:nda
  ```

- In questo esempio viene eseguita una ricerca in una cartella del sito e in qualsiasi sottocartella per i documenti che sono stati modificati all'interno di un intervallo di date.
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>Ulteriori informazioni

Quando si utilizza lo script in questo articolo, è necessario tenere presente quanto segue per eseguire le raccolte mirate.
  
- Lo script non rimuove alcuna cartella dai risultati. Pertanto, alcune cartelle elencate nei risultati potrebbero non essere ricercabili (o restituire zero elementi) perché contengono contenuto generato dal sistema.
    
- Questo script restituisce solo informazioni sulla cartella per la cassetta postale principale dell'utente. Non restituisce informazioni sulle cartelle nella cassetta postale di archiviazione dell'utente.
    
- Quando si eseguono ricerche nelle cartelle delle cassette postali, verrà eseguita `folderid` la ricerca solo nella cartella specificata (identificata dalla relativa proprietà). Le sottocartelle non verranno cercate. Per eseguire la ricerca in cartelle secondarie, è necessario utilizzare l'ID cartella per la sottocartella che si desidera ricercare. 
    
- Quando si esegue la ricerca nelle cartelle del sito, la `path` cartella (identificata dalla relativa proprietà) e tutte le sottocartelle verranno ricercate. 
    
- Come indicato in precedenza, non è `path` possibile utilizzare la proprietà per cercare file multimediali, ad esempio file con estensione png, TIFF o WAV, che si trovano nei percorsi di OneDrive. Utilizzare una proprietà diversa del [sito](keyword-queries-and-search-conditions.md#searchable-site-properties) per cercare i file multimediali nelle cartelle di OneDrive. 

- Quando si esportano i risultati di una ricerca in cui è `folderid` stata specificata solo la proprietà nella query di ricerca, è possibile scegliere la prima opzione di esportazione, "tutti gli elementi, esclusi quelli con formato non riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi". Tutti gli elementi della cartella verranno sempre esportati indipendentemente dallo stato di indicizzazione, poiché l'ID della cartella è sempre indicizzato.
