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
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Informazioni su come automatizzare le attività di ricerca del contenuto come creazione ricerche e l'esecuzione di report tramite script di PowerShell in Office 365 Security &amp; centro conformità.
ms.openlocfilehash: a32c003dfd9a27ea8c38b29b31001b612368bc4a
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038139"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="cba7b-103">Creare, ottenere rapporti ed eliminare più Ricerche di contenuto</span><span class="sxs-lookup"><span data-stu-id="cba7b-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="cba7b-p101">Rapidamente la creazione e segnalazione individuazione ricerche spesso è un aspetto importante di eDiscovery e indagini quando si sta tentando di conoscere i dati sottostanti e la complessità e la qualità delle ricerche. Per eseguire questa operazione, la sicurezza &amp; centro conformità offre un set di cmdlet di Windows PowerShell per automatizzare le attività di ricerca del contenuto richiedere molto tempo. Questi script offrono un modo semplice e veloce per creare un numero di ricerche e quindi creare i rapporti dei risultati della ricerca stimati che consentono di determinare la quantità di dati in questione. Inoltre, è possibile utilizzare gli script per creare versioni diverse di ricerche per confrontare i risultati di che ciascuna di esse produce. Questi script consentono a più rapido ed efficiente identificare e riforma dei dati.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p101">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches. To help you do this, the Security &amp; Compliance Center offers a set of Windows PowerShell cmdlets to automate time-consuming Content Search tasks. These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question. You can also use the scripts to create different versions of searches to compare the results each one produces. These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="cba7b-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="cba7b-109">Before you begin</span></span>

- <span data-ttu-id="cba7b-110">È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità di eseguire gli script descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="cba7b-110">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="cba7b-111">Per raccogliere un elenco degli URL per il OneDrive per i siti all'interno dell'organizzazione che è possibile aggiungere il file CSV nel passaggio 1, vedere [creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span><span class="sxs-lookup"><span data-stu-id="cba7b-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> 
    
- <span data-ttu-id="cba7b-p102">Assicurarsi di salvare tutti i file creati in questo argomento nella stessa cartella. Che verranno rendono più semplice eseguire gli script.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p102">Be sure to save all the files that you create in this topic to the same folder. That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="cba7b-p103">Gli script includono la gestione degli errori o molto ridotto. Lo scopo principale consiste nel creare, creare relazioni sulle ed eliminare più ricerche di contenuto.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p103">The scripts include minimal error handling. Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="cba7b-p104">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="cba7b-121">Passaggio 1: Creare un file CSV che contiene informazioni sulle ricerche che si desidera eseguire</span><span class="sxs-lookup"><span data-stu-id="cba7b-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="cba7b-p105">Il file virgole (CSV) virgola creati in questo passaggio contiene una riga per ogni utente che si desidera eseguire la ricerca. È possibile cercare cassette postali di Exchange Online dell'utente (che includono la cassetta postale di archiviazione, se abilitato) e le OneDrive per sito aziendale. Oppure è possibile cercare solo la cassetta postale o OneDrive per sito aziendale. È inoltre possibile cercare tutti i siti dell'organizzazione di SharePoint Online. Lo script che viene eseguita nel passaggio 3 creerà una ricerca distinto per ogni riga nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p105">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search. You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site. Or you can search just the mailbox or the OneDrive for Business site. You can also search any site in your SharePoint Online organization. The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="cba7b-p106">Copiare e incollare il testo seguente in un file con estensione txt utilizzando il blocco note. Salvare il file in una cartella nel computer locale. È possibile risparmiare altri script in anche questa cartella.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p106">Copy and paste the following text into a .txt file using NotePad. Save this file to a folder on your local computer. You'll save the other scripts to this folder as well.</span></span>
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="cba7b-p107">La prima riga o una riga di intestazione, del file vengono elencati i parametri utilizzati dal cmdlet **New-ComplianceSearch** (tramite uno script nel passaggio 3) per creare un nuovo ricerche di contenuto. Ogni nome del parametro è separata da una virgola. Verificare che non vi sono spazi nella riga di intestazione. Ogni riga sotto la riga di intestazione rappresenta i valori dei parametri per ogni ricerca. Assicurarsi di sostituire i segnaposto i dati nel file CSV con dati effettivi.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p107">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches. Each parameter name is separated by a comma. Make sure there aren't any spaces in the header row. Each row under the header row represents the parameter values for each search. Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="cba7b-135">Aprire il file con estensione txt in Excel e quindi utilizzare le informazioni nella tabella seguente per modificare il file con le informazioni per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="cba7b-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="cba7b-136">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="cba7b-136">**Parameter**</span></span>|<span data-ttu-id="cba7b-137">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cba7b-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="cba7b-138">L'indirizzo SMTP della cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cba7b-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="cba7b-p108">URL di OneDrive for sito aziendale dell'utente o l'URL di qualsiasi sito dell'organizzazione. Per l'URL di OneDrive per i siti, utilizzare il seguente formato: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `. Ad esempio `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p108">The URL for the user's OneDrive for Business site or the URL for any site in your organization. For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `. For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.  </span></span><br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="cba7b-p109">Query di ricerca per la ricerca. Per ulteriori informazioni sulla creazione di una query di ricerca, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="cba7b-p109">The search query for the search. For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).  </span></span><br/> |
    | `StartDate` <br/> |<span data-ttu-id="cba7b-p110">Per la posta elettronica, la data o dopo un messaggio è stata ricevuta da un destinatario o inviata dal mittente. Per i documenti in SharePoint o OneDrive per i siti, la data o dopo un documento dell'ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p110">For email, the date on or after a message was received by a recipient or sent by the sender. For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="cba7b-p111">Per la posta elettronica, la data o prima di un messaggio è stata inviata dal inviati dall'utente. Per i documenti in SharePoint o OneDrive per i siti, la data o prima di un documento dell'ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p111">For email, the date on or before a message was sent by a sent by the user. For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="cba7b-p112">Salvare il file di Excel come file CSV in una cartella nel computer locale. Lo script creato nel passaggio 3 verrà utilizzate le informazioni nel file CSV per creare le ricerche.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p112">Save the Excel file as a CSV file to a folder on your local computer. The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="cba7b-150">Passaggio 2: Connettersi a PowerShell centro conformità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="cba7b-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="cba7b-151">Il passaggio successivo consiste nel connettere Windows PowerShell per la protezione &amp; centro conformità per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cba7b-151">The next step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="cba7b-p113">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `ConnectSCC.ps1`. Salvare il file per la stessa cartella in cui è stato salvato il file CSV da nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p113">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`. Save the file to the same folder that you saved the CSV file to in Step 1.</span></span>
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="cba7b-154">Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente e quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="cba7b-154">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="cba7b-155">Passaggio 3: Eseguire lo script per creare e avviare le ricerche</span><span class="sxs-lookup"><span data-stu-id="cba7b-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="cba7b-p114">Lo script in questo passaggio verrà creato un ricerca contenuto separato per ogni riga nel file CSV creato nel passaggio 1. Quando si esegue questo script, verrà richiesto di due valori:</span><span class="sxs-lookup"><span data-stu-id="cba7b-p114">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1. When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="cba7b-p115">**ID del gruppo di ricerca** - questo nome fornisce un modo semplice per organizzare le ricerche vengono create dal file CSV. Ogni ricerca creato denominato con l'ID di gruppo di ricerca e quindi viene aggiunto un numero per il nome di ricerca. Ad esempio, se si immette **ContosoCase** per l'ID di gruppo di ricerca, le ricerche sono denominate **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**e così via. Si noti che il nome digitato distinzione tra maiuscole e minuscole. Quando si utilizza l'ID di gruppo di ricerca nel passaggio 4 e 5, è necessario utilizzare lo stesso caso, in modo analogo al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p115">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file. Each search that's created is named with the Search Group ID, and then a number is appended to the search name. For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on. Note that the name you type is case sensitive. When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="cba7b-p116">**File CSV** - il nome del file CSV creato nel passaggio 1. È necessario includere il nome di file completo l'utilizzo, includere l'estensione di file. csv; ad esempio `ContosoCase.csv`.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p116">**CSV file** - The name of the CSV file that you created in Step 1. Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="cba7b-165">Per eseguire lo script:</span><span class="sxs-lookup"><span data-stu-id="cba7b-165">To run the script:</span></span>

1. <span data-ttu-id="cba7b-p117">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `CreateSearches.ps1`. Salvare il file nella stessa cartella in cui è stato salvato i file di altri.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p117">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="cba7b-168">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente e quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="cba7b-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="cba7b-p118">Al prompt dei comandi **ID gruppo di ricerca** , digitare il nome di un gruppo di ricerca e quindi premere **INVIO**. ad esempio `ContosoCase`. Tenere presente che questo nome viene fatta distinzione tra maiuscole e minuscole, pertanto sarà necessario digitare il testo allo stesso modo nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p118">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="cba7b-171">Al prompt di **file CSV di origine** , digitare il nome del file CSV, inclusa l'estensione di file. csv; ad esempio `ContosoCase.csv`.</span><span class="sxs-lookup"><span data-stu-id="cba7b-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="cba7b-172">Premere **INVIO** per continuare l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="cba7b-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="cba7b-p119">Lo script visualizza lo stato di avanzamento di creazione e l'esecuzione di ricerche. Una volta completato, lo script restituisce al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p119">The script displays the progress of creating and running the searches. When the script is complete, it returns to the prompt.</span></span> 
    
    ![Output di esempio dall’esecuzione dello script per creare ricerche di conformità multiple](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="cba7b-176">Passaggio 4: Eseguire lo script per segnalare la ricerca stima</span><span class="sxs-lookup"><span data-stu-id="cba7b-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="cba7b-p120">Dopo aver creato le ricerche, il passaggio successivo consiste nell'eseguire uno script che viene visualizzato un semplice report del numero di visite di ricerca per ogni ricerca creato nel passaggio 3. Il report include anche le dimensioni dei risultati per ogni servizio di ricerca e il numero totale di accessi e le dimensioni totali di tutte le ricerche. Quando si esegue lo script report, verrà richiesto per l'ID del gruppo di ricerca e un nome di file CSV se si desidera salvare il report in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p120">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3. The report also includes the size of results for each search, and the total number of hits and total size of all searches. When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="cba7b-p121">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `SearchReport.ps1`. Salvare il file nella stessa cartella in cui è stato salvato i file di altri.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="cba7b-182">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente e quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="cba7b-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="cba7b-p122">Al prompt dei comandi **ID gruppo di ricerca** , digitare il nome di un gruppo di ricerca e quindi premere **INVIO**. ad esempio `ContosoCase`. Tenere presente che questo nome viene fatta distinzione tra maiuscole e minuscole, pertanto sarà necessario digitare il testo esattamente come è stato durante l'esecuzione dello script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p122">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="cba7b-p123">Al prompt di **percorso in cui salvare il report in un file CSV (lasciare vuoto per visualizzare solo il rapporto) dei File** , digitare un nome file del percorso completo del nome di file (inclusa l'estensione del file con estensione csv) se si desidera salvare il report in un file CSV. nome del file CSV, inclusa l'estensione di file. csv. Ad esempio, è possibile digitare `ContosoCaseReport.csv` per salvarlo nella directory corrente oppure è possibile digitare `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` per salvarlo in una cartella diversa. È inoltre possibile lasciare vuoto per visualizzare il report, ma non salvare un file di prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p123">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file. name of the CSV file, including the .csv file extension. For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder. You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="cba7b-189">Premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="cba7b-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="cba7b-p124">Lo script visualizza lo stato di avanzamento di creazione e l'esecuzione di ricerche. Una volta completato, lo script viene visualizzato il report.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p124">The script displays the progress of creating and running the searches. When the script is complete, the report is displayed.</span></span> 
    
    ![Eseguire il report di ricerca per visualizzare le stime per il gruppo di ricerca](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="cba7b-p125">Se la cassetta postale o sito stesso viene specificato come percorso contenuto in più di una ricerca in un gruppo di ricerca, la stima totale risultati del rapporto (per il numero di elementi e le dimensioni totali) può includere i risultati per gli stessi elementi. Ciò avviene perché la stessa messaggio di posta elettronica o il documento vengono conteggiata più volte se viene rilevata una corrispondenza la query per le ricerche diverse nel gruppo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p125">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items. That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="cba7b-195">Passaggio 5: Eseguire lo script per eliminare le ricerche</span><span class="sxs-lookup"><span data-stu-id="cba7b-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="cba7b-p126">Poiché si può creare una quantità elevata di ricerche, questo script ultimo appena facilita eliminare rapidamente le ricerche creata nel passaggio 3. Ad esempio gli script, questo inoltre richiede l'ID del gruppo di ricerca. Tutte le ricerche con l'ID di gruppo di ricerca il nome di ricerca verranno eliminate quando si esegue lo script.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p126">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3. Like the other scripts, this one also prompts you for the Search Group ID. All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="cba7b-p127">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `DeleteSearches.ps1`. Salvare il file nella stessa cartella in cui è stato salvato i file di altri.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="cba7b-201">In Windows PowerShell, passare alla cartella in cui è stato salvato lo script nel passaggio precedente e quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="cba7b-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="cba7b-p128">Al prompt dei comandi **ID gruppo di ricerca** , digitare il nome di un gruppo di ricerca per le ricerche che si desidera eliminare e quindi premere **INVIO**. ad esempio `ContosoCase`. Tenere presente che questo nome viene fatta distinzione tra maiuscole e minuscole, pertanto sarà necessario digitare il testo esattamente come è stato durante l'esecuzione dello script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="cba7b-p128">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="cba7b-204">Lo script viene visualizzato il nome di ogni ricerca venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="cba7b-204">The script displays the name of each search that's deleted.</span></span>
    
    ![Eseguire lo script per eliminare le ricerche nel gruppo di ricerca](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
