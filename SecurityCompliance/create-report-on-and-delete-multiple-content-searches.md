---
title: Creare, ottenere rapporti ed eliminare più Ricerche di contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Informazioni su come automatizzare le attività di ricerca del contenuto come creazione ricerche e l'esecuzione di report tramite script di PowerShell in Office 365 Security &amp; centro conformità.
ms.openlocfilehash: 2baa569c28ed5324e6674addeac688b854a65ed8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530452"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Creare, ottenere rapporti ed eliminare più Ricerche di contenuto

 Rapidamente la creazione e segnalazione individuazione ricerche spesso è un aspetto importante di eDiscovery e indagini quando si sta tentando di conoscere i dati sottostanti e la complessità e la qualità delle ricerche. Per eseguire questa operazione, la sicurezza &amp; centro conformità offre un set di cmdlet di Windows PowerShell per automatizzare le attività di ricerca del contenuto richiedere molto tempo. Questi script offrono un modo semplice e veloce per creare un numero di ricerche e quindi creare i rapporti dei risultati della ricerca stimati che consentono di determinare la quantità di dati in questione. Inoltre, è possibile utilizzare gli script per creare versioni diverse di ricerche per confrontare i risultati di che ciascuna di esse produce. Questi script consentono a più rapido ed efficiente identificare e riforma dei dati. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità di eseguire gli script descritti in questo argomento. 
    
- Per raccogliere un elenco degli URL per il OneDrive per i siti all'interno dell'organizzazione che è possibile aggiungere il file CSV nel passaggio 1, vedere [creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a). 
    
- Assicurarsi di salvare tutti i file creati in questo argomento nella stessa cartella. Che verranno rendono più semplice eseguire gli script.
    
- Gli script includono la gestione degli errori o molto ridotto. Lo scopo principale consiste nel creare, creare relazioni sulle ed eliminare più ricerche di contenuto.
    
- Gli script di esempio forniti in questo argomento non sono supportati in qualsiasi programma Microsoft supporto standard o del servizio. Esempi di script vengono forniti così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Passaggio 1: Creare un file CSV che contiene informazioni sulle ricerche che si desidera eseguire

Il file virgole (CSV) virgola creati in questo passaggio contiene una riga per ogni utente che si desidera eseguire la ricerca. È possibile cercare cassette postali di Exchange Online dell'utente (che includono la cassetta postale di archiviazione, se abilitato) e le OneDrive per sito aziendale. Oppure è possibile cercare solo la cassetta postale o OneDrive per sito aziendale. È inoltre possibile cercare tutti i siti dell'organizzazione di SharePoint Online. Lo script che viene eseguita nel passaggio 3 creerà una ricerca distinto per ogni riga nel file CSV. 
  
1. Copiare e incollare il testo seguente in un file con estensione txt utilizzando il blocco note. Salvare il file in una cartella nel computer locale. È possibile risparmiare altri script in anche questa cartella.
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    La prima riga o una riga di intestazione, del file vengono elencati i parametri utilizzati dal cmdlet **New-ComplianceSearch** (tramite uno script nel passaggio 3) per creare un nuovo ricerche di contenuto. Ogni nome del parametro è separata da una virgola. Verificare che non vi sono spazi nella riga di intestazione. Ogni riga sotto la riga di intestazione rappresenta i valori dei parametri per ogni ricerca. Assicurarsi di sostituire i segnaposto i dati nel file CSV con dati effettivi. 
    
2. Aprire il file con estensione txt in Excel e quindi utilizzare le informazioni nella tabella seguente per modificare il file con le informazioni per ogni ricerca. 
    
    |**Parametro**|**Descrizione**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |L'indirizzo SMTP della cassetta postale dell'utente.  <br/> |
    | `SharePointLocation` <br/> |URL di OneDrive for sito aziendale dell'utente o l'URL di qualsiasi sito dell'organizzazione. Per l'URL di OneDrive per i siti, utilizzare il seguente formato: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `. Ad esempio `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.<br/> |
    | `ContentMatchQuery` <br/> |Query di ricerca per la ricerca. Per ulteriori informazioni sulla creazione di una query di ricerca, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md).<br/> |
    | `StartDate` <br/> |Per la posta elettronica, la data o dopo un messaggio è stata ricevuta da un destinatario o inviata dal mittente. Per i documenti in SharePoint o OneDrive per i siti, la data o dopo un documento dell'ultima modifica.  <br/> |
    | `EndDate` <br/> |Per la posta elettronica, la data o prima di un messaggio è stata inviata dal inviati dall'utente. Per i documenti in SharePoint o OneDrive per i siti, la data o prima di un documento dell'ultima modifica.  <br/> |
   
3. Salvare il file di Excel come file CSV in una cartella nel computer locale. Lo script creato nel passaggio 3 verrà utilizzate le informazioni nel file CSV per creare le ricerche. 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Passaggio 2: Connettersi a PowerShell centro conformità e sicurezza

Il passaggio successivo consiste nel connettere Windows PowerShell per la protezione &amp; centro conformità per l'organizzazione.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `ConnectSCC.ps1`. Salvare il file per la stessa cartella in cui è stato salvato il file CSV da nel passaggio 1.
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente e quindi eseguire lo script. Per esempio:
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Passaggio 3: Eseguire lo script per creare e avviare le ricerche

Lo script in questo passaggio verrà creato un ricerca contenuto separato per ogni riga nel file CSV creato nel passaggio 1. Quando si esegue questo script, verrà richiesto di due valori:
  
- **ID del gruppo di ricerca** - questo nome fornisce un modo semplice per organizzare le ricerche vengono create dal file CSV. Ogni ricerca creato denominato con l'ID di gruppo di ricerca e quindi viene aggiunto un numero per il nome di ricerca. Ad esempio, se si immette **ContosoCase** per l'ID di gruppo di ricerca, le ricerche sono denominate **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**e così via. Si noti che il nome digitato distinzione tra maiuscole e minuscole. Quando si utilizza l'ID di gruppo di ricerca nel passaggio 4 e 5, è necessario utilizzare lo stesso caso, in modo analogo al momento della creazione. 
    
- **File CSV** - il nome del file CSV creato nel passaggio 1. È necessario includere il nome di file completo l'utilizzo, includere l'estensione di file. csv; ad esempio `ContosoCase.csv`.
    
Per eseguire lo script:

1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `CreateSearches.ps1`. Salvare il file nella stessa cartella in cui è stato salvato i file di altri.
    
  ```
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente e quindi eseguire lo script. Per esempio:
    
    ```
    .\CreateSearches.ps1
    ```

3. Al prompt dei comandi **ID gruppo di ricerca** , digitare il nome di un gruppo di ricerca e quindi premere **INVIO**. ad esempio `ContosoCase`. Tenere presente che questo nome viene fatta distinzione tra maiuscole e minuscole, pertanto sarà necessario digitare il testo allo stesso modo nei passaggi successivi.
    
4. Al prompt di **file CSV di origine** , digitare il nome del file CSV, inclusa l'estensione di file. csv; ad esempio `ContosoCase.csv`.
    
5. Premere **INVIO** per continuare l'esecuzione dello script. 
    
    Lo script visualizza lo stato di avanzamento di creazione e l'esecuzione di ricerche. Una volta completato, lo script restituisce al prompt dei comandi. 
    
    ![Output di esempio dall’esecuzione dello script per creare ricerche di conformità multiple](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Passaggio 4: Eseguire lo script per segnalare la ricerca stima

Dopo aver creato le ricerche, il passaggio successivo consiste nell'eseguire uno script che viene visualizzato un semplice report del numero di visite di ricerca per ogni ricerca creato nel passaggio 3. Il report include anche le dimensioni dei risultati per ogni servizio di ricerca e il numero totale di accessi e le dimensioni totali di tutte le ricerche. Quando si esegue lo script report, verrà richiesto per l'ID del gruppo di ricerca e un nome di file CSV se si desidera salvare il report in un file CSV.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `SearchReport.ps1`. Salvare il file nella stessa cartella in cui è stato salvato i file di altri.
    
  ```
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente e quindi eseguire lo script. Per esempio:
    
    ```
    .\SearchReport.ps1
    ```

3. Al prompt dei comandi **ID gruppo di ricerca** , digitare il nome di un gruppo di ricerca e quindi premere **INVIO**. ad esempio `ContosoCase`. Tenere presente che questo nome viene fatta distinzione tra maiuscole e minuscole, pertanto sarà necessario digitare il testo esattamente come è stato durante l'esecuzione dello script nel passaggio 3.
    
4. Al prompt di **percorso in cui salvare il report in un file CSV (lasciare vuoto per visualizzare solo il rapporto) dei File** , digitare un nome file del percorso completo del nome di file (inclusa l'estensione del file con estensione csv) se si desidera salvare il report in un file CSV. nome del file CSV, inclusa l'estensione di file. csv. Ad esempio, è possibile digitare `ContosoCaseReport.csv` per salvarlo nella directory corrente oppure è possibile digitare `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` per salvarlo in una cartella diversa. È inoltre possibile lasciare vuoto per visualizzare il report, ma non salvare un file di prompt dei comandi. 
    
5. Premere **INVIO**.
    
    Lo script visualizza lo stato di avanzamento di creazione e l'esecuzione di ricerche. Una volta completato, lo script viene visualizzato il report. 
    
    ![Eseguire il report di ricerca per visualizzare le stime per il gruppo di ricerca](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> Se la cassetta postale o sito stesso viene specificato come percorso contenuto in più di una ricerca in un gruppo di ricerca, la stima totale risultati del rapporto (per il numero di elementi e le dimensioni totali) può includere i risultati per gli stessi elementi. Ciò avviene perché la stessa messaggio di posta elettronica o il documento vengono conteggiata più volte se viene rilevata una corrispondenza la query per le ricerche diverse nel gruppo di ricerca. 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>Passaggio 5: Eseguire lo script per eliminare le ricerche

Poiché si può creare una quantità elevata di ricerche, questo script ultimo appena facilita eliminare rapidamente le ricerche creata nel passaggio 3. Ad esempio gli script, questo inoltre richiede l'ID del gruppo di ricerca. Tutte le ricerche con l'ID di gruppo di ricerca il nome di ricerca verranno eliminate quando si esegue lo script. 
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `DeleteSearches.ps1`. Salvare il file nella stessa cartella in cui è stato salvato i file di altri.
    
  ```
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente e quindi eseguire lo script. Per esempio:
    
    ```
    .\DeleteSearches.ps1
    ```

3. Al prompt dei comandi **ID gruppo di ricerca** , digitare il nome di un gruppo di ricerca per le ricerche che si desidera eliminare e quindi premere **INVIO**. ad esempio `ContosoCase`. Tenere presente che questo nome viene fatta distinzione tra maiuscole e minuscole, pertanto sarà necessario digitare il testo esattamente come è stato durante l'esecuzione dello script nel passaggio 3.
    
    Lo script viene visualizzato il nome di ogni ricerca venga eliminato.
    
    ![Eseguire lo script per eliminare le ricerche nel gruppo di ricerca](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
