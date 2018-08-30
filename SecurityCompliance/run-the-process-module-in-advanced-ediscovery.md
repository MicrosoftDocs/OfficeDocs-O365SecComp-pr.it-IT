---
title: Eseguire il modulo di processo in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: "Scopri le linee guida per maiuscole preparazione dei file di dati di Office 365 per l'analisi con Office 365 avanzate eDiscovery.  "
ms.openlocfilehash: 52b1dce9fb778c6628d90c39135f0c93f08134d7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531351"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="aa693-103">Eseguire il modulo di processo in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="aa693-103">Run the Process module in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="aa693-104">File maiuscole vengono caricati in eDiscovery avanzate durante **Prepara** \> **processo**.</span><span class="sxs-lookup"><span data-stu-id="aa693-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="aa693-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="aa693-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="aa693-107">Linee guida: Preparazione dei dati per eDiscovery avanzate</span><span class="sxs-lookup"><span data-stu-id="aa693-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="aa693-108">**Qualità**: identificare chiaramente popolazione file maiuscole pertinenti al caso.</span><span class="sxs-lookup"><span data-stu-id="aa693-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="aa693-109">**Carichi**: caricare i file in un percorso accessibile a eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="aa693-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="aa693-p102">**ID del file**: un identificatore di file univoco di eDiscovery avanzate. Se nessun identificatore file importato, eDiscovery avanzate genera automaticamente l'ID. Se si eseguire il mapping dell'ID nel caricamento processo successivo e mappare un percorso diverso dal carico di processo iniziale, eDiscovery avanzate verrà sostituire il percorso (anziché aggiungere una nuova voce del file). Consente l'ID come riferimento nel processo di esportazione. Il valore ID non deve essere "-1".</span><span class="sxs-lookup"><span data-stu-id="aa693-p102">**File ID**: A unique file identifier in Advanced eDiscovery. If no file identifier is imported, Advanced eDiscovery automatically generates the ID. If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry). The ID can be used as a reference in the Export process. The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="aa693-p103">**MD5**: la firma viene utilizzata per distinguere i file (due file non sono considerati duplicati a meno che non hanno la stessa MD5). Per impostazione predefinita, eDiscovery avanzate calcola MD5 dei file. Quando i file caricati sono file di testo, è consigliabile per caricare e mappare il valore MD5 originale anziché il calcolo di eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="aa693-p103">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5). By default, Advanced eDiscovery calculates the MD5 of files. When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="aa693-118">**Nome e tipo di file**:</span><span class="sxs-lookup"><span data-stu-id="aa693-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="aa693-p104">Avanzate eDiscovery può del processo di diversi formati file ed estrarre i file di nativi caricati in un formato standard, ad esempio \*. TXT, HTML o. XML. l'elaborazione dei file di testo è più rapido rispetto ai file nativi. File di testo estratto vengono archiviati nella cartella maiuscole.</span><span class="sxs-lookup"><span data-stu-id="aa693-p104">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML. Processing of text files is faster than native files. Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="aa693-p105">Non caricare i file che non possono essere estratti, ad esempio i file di sistema o immagini grafiche. Questi file potrebbero ritardare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="aa693-p105">Do not load files that cannot be extracted, such as system files or graphic images. These files may delay processing.</span></span>
    
  - <span data-ttu-id="aa693-124">Verificare che i nomi di file in modo significativo sono denominati e percorsi siano corretti.</span><span class="sxs-lookup"><span data-stu-id="aa693-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="aa693-125">**Percorso del file**: avanzate eDiscovery può caricare file con le lunghezze dei percorsi fino a 400 caratteri.</span><span class="sxs-lookup"><span data-stu-id="aa693-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="aa693-p106">**Estrazione di testo**: anche estratto durante l'estrazione di testo dal file nativi, oltre al testo normale, le operazioni seguenti: colonne di testo nascosto, Excel e file con estensione doc, nascosta (Excel), tenere traccia delle modifiche (con estensione doc), gli oggetti di Lotus notes (con estensione ppt) incorporato altoparlante (ad esempio, Oggetti di Excel in un file con estensione ppt). Questi possono essere visualizzati nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="aa693-p106">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt). These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="aa693-p107">**Ignora testo**: questa funzionalità facoltativa è definita dopo l'esecuzione di processo e prima dell'analisi. Ignora testo deve essere utilizzato con attenzione perché il suo utilizzo può consentire una riduzione delle prestazioni di analisi del file.</span><span class="sxs-lookup"><span data-stu-id="aa693-p107">**Ignore Text**: This optional feature is defined after Process is run and before Analyze. Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="aa693-130">**Testo multilingue**: eDiscovery avanzate non è attualmente la nomi in più lingue per i tag, depositaria e problemi.</span><span class="sxs-lookup"><span data-stu-id="aa693-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="aa693-p108">**Metadati**: determinare se esiste metadati che si desidera salvare nel database di maiuscole per riferimento futuro, ad esempio l'intervallo di date, dimensioni dei file, tipo di file, depositaria e del soggetto. Metadati possono essere caricati dopo che i file sono stati già caricati senza eseguire nuovamente l'inventario o aggiunta di rielaborare sovraccarico.</span><span class="sxs-lookup"><span data-stu-id="aa693-p108">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject. Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="aa693-p109">Se i file di origine sono stati caricati dal percorso, eseguire il mapping nella colonna percorso durante l'importazione di metadati più avanti. È possibile fare riferimento al file in base all'ID ed eseguire il mapping di un percorso diverso. Si tratta di uno scenario utile quando modificano i percorsi dei file.</span><span class="sxs-lookup"><span data-stu-id="aa693-p109">If the files were originally loaded by path, map the path column when later importing metadata. It is possible to refer to the file by ID and to map a different path. This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="aa693-p110">Se i file di origine sono stati caricati in base all'ID di File, eseguire il mapping della colonna ID durante il caricamento dei metadati. Per il riferimento al file path (anziché ID) determinerà i file da caricare nuovamente con un ID diverso. EDiscovery avanzate consente di creare copie dei file piuttosto che il caricamento metadati dei file esistenti.</span><span class="sxs-lookup"><span data-stu-id="aa693-p110">If the files were originally loaded by File ID, map the ID column when loading metadata. Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID. Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="aa693-139">**Famiglie**: non è possibile caricare una famiglia senza padre (testa della famiglia).</span><span class="sxs-lookup"><span data-stu-id="aa693-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="aa693-p111">**Dimensione del file**: non esiste alcun limite le dimensioni dei file caricato in eDiscovery avanzate. Per l'analisi (analisi, pertinenza e così via), il limite è 5.242.880 caratteri del testo estratto. File di dimensioni maggiori vengono ignorato (ad esempio, di pertinenza, i file non fanno parte del processo di formazione di pertinenza e non ricevono un punteggio di pertinenza dopo il calcolo batch).</span><span class="sxs-lookup"><span data-stu-id="aa693-p111">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery. For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text. Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="aa693-p112">**Quantità di file**: non esiste alcun limite consigliato al numero di file che possono essere gestiti in un singolo caso. Le prestazioni dipendono le risorse del sistema.</span><span class="sxs-lookup"><span data-stu-id="aa693-p112">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case. Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="aa693-145">Il filtraggio dei file</span><span class="sxs-lookup"><span data-stu-id="aa693-145">Filtering files</span></span>

<span data-ttu-id="aa693-p113">Un'etichetta definita dall'utente può essere associata a un insieme di file da escludere loro dal processo o altre attività. Ogni sessione processo è associato un ID batch. Sebbene l'ID del blocco non è visibile all'esperto di pertinenza, questa operazione può essere eseguita utilizzando un'utilità di ricerca aggiungendo un filtro per il batch corrente e tagging tutti i file appropriati con un'etichetta definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="aa693-p113">A user-defined label can be associated with a set of files to exclude them from Process or other tasks. Each Process session is associated with a batch ID. Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="aa693-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa693-149">See also</span></span>

[<span data-ttu-id="aa693-150">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="aa693-150">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="aa693-151">In esecuzione il modulo di processo e il caricamento dei dati</span><span class="sxs-lookup"><span data-stu-id="aa693-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="aa693-152">Visualizzazione dei risultati modulo processo</span><span class="sxs-lookup"><span data-stu-id="aa693-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

