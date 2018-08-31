---
title: Investigating partially indexed items in Office 365 eDiscovery (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Parzialmente voci indicizzate (anche gli elementi di chiamata non indicizzata) sono elementi della cassetta postale di Exchange e i documenti in SharePoint e ai siti OneDrive per qualche motivo non sono stati completamente indicizzato per la ricerca del contenuto. In questo articolo per informazioni sui motivi per cui gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi indicizzati parzialmente, identificare gli errori di ricerca di elementi indicizzati parzialmente e utilizzare uno script di PowerShell per determinare l'esposizione dell'organizzazione per la posta elettronica parzialmente indicizzato elementi.
ms.openlocfilehash: 4e8e8c31e6c5450a9b84a1240c2ae8d891c1bd6f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531347"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a><span data-ttu-id="7adba-104">Investigating partially indexed items in Office 365 eDiscovery (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)</span><span class="sxs-lookup"><span data-stu-id="7adba-104">Investigating partially indexed items in Office 365 eDiscovery</span></span>

<span data-ttu-id="7adba-p102">Una ricerca di contenuto che viene eseguita da Office 365 Security &amp; centro conformità include automaticamente elementi indicizzati parzialmente nei risultati della ricerca stimati quando si esegue una ricerca. Elementi indicizzati parzialmente sono elementi della cassetta postale di Exchange e documenti in SharePoint e OneDrive per i siti che, per qualche motivo, non sono stati completamente indicizzati per la ricerca. La maggior parte dei messaggi di posta elettronica e documenti del sito vengono indicizzati correttamente perché sono inclusi entro il [limite per il servizio di indicizzazione di messaggi di posta elettronica](limits-for-content-search.md#indexinglimits). Tuttavia, alcuni elementi possono superare i limiti di indicizzazione e sarà possibile indicizzare parzialmente. Di seguito sono altri motivi per cui gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi indicizzati parzialmente quando si esegue una ricerca di contenuto:</span><span class="sxs-lookup"><span data-stu-id="7adba-p102">A Content Search that you run from the Office 365 Security &amp; Compliance Center automatically includes partially indexed items in the estimated search results when you run a search. Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search. Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexinglimits). However, some items may exceed these indexing limits, and will be partially indexed. Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="7adba-110">Messaggi di posta elettronica dispongono di un file allegato di un tipo di file che non possono essere indicizzato; Nella maggior parte dei casi, il tipo di file è [sconosciuta o non è supportato per l'indicizzazione](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="7adba-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="7adba-111">Messaggi di posta elettronica sono un file allegato senza un gestore valido, ad esempio file di immagine. Questa è la causa più comune di elementi di posta elettronica parzialmente indicizzati</span><span class="sxs-lookup"><span data-stu-id="7adba-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="7adba-112">Troppi file allegati al messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7adba-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="7adba-113">Un file allegato al messaggio di posta elettronica è troppo grande</span><span class="sxs-lookup"><span data-stu-id="7adba-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="7adba-114">Il tipo di file è supportato per l'indicizzazione ma si è verificato un errore di indicizzazione per uno specifico file</span><span class="sxs-lookup"><span data-stu-id="7adba-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="7adba-p103">Sebbene varino, per dimensioni parzialmente indicizzato maggior parte dei clienti di organizzazioni di Office 365 hanno meno dell'1% del contenuto dal volume e inferiore a 12% del contenuto. Il motivo per la differenza tra il volume rispetto alla dimensione è che i file di dimensioni maggiori probabilità di che include contenuto che non possono essere indicizzato completamente.</span><span class="sxs-lookup"><span data-stu-id="7adba-p103">Although it varies, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed. The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="7adba-117">Perché il conteggio di elementi indicizzati parzialmente viene modificati per una ricerca?</span><span class="sxs-lookup"><span data-stu-id="7adba-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="7adba-p104">Dopo l'esecuzione di una ricerca di contenuto in Office 365 Security &amp; centro conformità, il numero totale e le dimensioni di elementi indicizzati parzialmente nelle posizioni in cui sono stati ricercati sono elencate nelle statistiche di risultati di ricerca che vengono visualizzate nelle statistiche dettagliate per la ricerca. Si noti che detti *elementi indicizzati* nelle statistiche di ricerca. Ecco alcuni aspetti che incideranno il numero di elementi indicizzati parzialmente restituite nei risultati della ricerca:</span><span class="sxs-lookup"><span data-stu-id="7adba-p104">After you run a Content Search in the Office 365 Security &amp; Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search. Note these are called  *unindexed items*  in the search statistics. Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="7adba-p105">Se un elemento è parzialmente indicizzato e genera una corrispondenza per la query di ricerca, viene incluso il conteggio (e dimensioni) di elementi indicizzati parzialmente e gli elementi dei risultati di ricerca. Tuttavia, quando vengono esportati i risultati della ricerca stessa, l'elemento è incluso solo con set di risultati di ricerca; non è incluso come elemento parzialmente indicizzato.</span><span class="sxs-lookup"><span data-stu-id="7adba-p105">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items. However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="7adba-p106">Se si specifica un intervallo di date per una query di ricerca (per includerla nella query con parole chiave) o utilizzando una condizione, qualsiasi elemento parzialmente indicizzata che non soddisfano l'intervallo di date non include il numero di elementi indicizzati parzialmente. Solo gli elementi indicizzati parzialmente compresi nell'intervallo di date sono inclusi nel conteggio degli elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="7adba-p106">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items. Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="7adba-p107">**Nota:** Parzialmente indicizzato elementi disponibili in SharePoint e OneDrive siti *non* inclusi nella stima di elementi indicizzati parzialmente visualizzate nelle statistiche dettagliate per la ricerca. Tuttavia, è possono esportare elementi indicizzati parzialmente quando si esportano i risultati di ricerca di contenuto. Ad esempio, se la ricerca solo i siti in una ricerca di contenuto, il numero stimato parzialmente elementi indicizzati sarà zero.</span><span class="sxs-lookup"><span data-stu-id="7adba-p107">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search. However, partially indexed items can be exported when you export the results of a Content Search. For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="7adba-128">Calcolare il rapporto di elementi indicizzati parzialmente all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7adba-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="7adba-p108">Per comprendere i propri sistemi dell'organizzazione a elementi indicizzati parzialmente, è possibile eseguire una ricerca per tutto il contenuto in tutte le cassette postali (tramite una query con parole chiave vuota). Nell'esempio seguente riportata di seguito, esistono 56,208 (4,830 MB) completamente indicizzato elementi e 470 (316 MB) parzialmente voci indicizzate.</span><span class="sxs-lookup"><span data-stu-id="7adba-p108">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query). In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Ad esempio che mostra le statistiche ricerca parzialmente voci indicizzate](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="7adba-132">È possibile determinare la percentuale di elementi indicizzati parzialmente utilizzando i calcoli seguenti.</span><span class="sxs-lookup"><span data-stu-id="7adba-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="7adba-133">**Per calcolare il rapporto di elementi indicizzati parzialmente all'interno dell'organizzazione:**</span><span class="sxs-lookup"><span data-stu-id="7adba-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="7adba-134">Utilizzando i risultati della ricerca dell'esempio precedente,. 84% di tutti gli elementi delle cassette postali parzialmente vengono indicizzati.</span><span class="sxs-lookup"><span data-stu-id="7adba-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="7adba-135">**Per calcolare la percentuale delle dimensioni di elementi indicizzati parzialmente all'interno dell'organizzazione:**</span><span class="sxs-lookup"><span data-stu-id="7adba-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="7adba-p109">Nell'esempio precedente, in modo 6.54% della dimensione totale di elementi delle cassette postali sono di elementi indicizzati parzialmente. Come affermato in precedenza, la maggior parte delle organizzazioni di Office 365 per dimensioni parzialmente indicizzato i clienti hanno meno dell'1% del contenuto volume e inferiore a 12% del contenuto.</span><span class="sxs-lookup"><span data-stu-id="7adba-p109">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items. As previously stated, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="7adba-138">Utilizzo di parzialmente voci indicizzate</span><span class="sxs-lookup"><span data-stu-id="7adba-138">Working with partially indexed items</span></span>

<span data-ttu-id="7adba-p110">In casi quando è necessario esaminare parzialmente gli elementi per verificare che non contengono informazioni necessarie, è possibile [esportare un report di ricerca del contenuto](export-a-content-search-report.md) che contiene informazioni sugli elementi parzialmente indicizzati. Quando si esporta un report di ricerca del contenuto, assicurarsi di selezionare una delle opzioni di esportazione che include gli elementi parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="7adba-p110">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items. When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![Scegliere l'opzione secondo o terzo per esportare elementi parzialmente indicizzati](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="7adba-p111">Quando si esporta i risultati di ricerca del contenuto o un report di ricerca del contenuto mediante una delle opzioni seguenti, Esporta include un report denominato Items.csv non indicizzate. In questo report include la maggior parte delle stesse informazioni come file ResultsLog.csv. Tuttavia, il file non indicizzate Items.csv include due campi relativi agli elementi indicizzati parzialmente: **Errore tag** e **Le proprietà di errore**. Questi campi contenenti informazioni sull'errore di indicizzazione per ogni elemento parzialmente indicizzato. Utilizzando le informazioni contenute in questi due campi consentono di determinare se l'errore di indicizzazione per un determinato un impatto significativo sull'analisi. In caso affermativo, è possibile eseguire una ricerca di contenuto mirata e recuperare ed esportare documenti di SharePoint o OneDrive e messaggi di posta elettronica specifici in modo da poter esaminare in modo da determinare se è rilevanti per le indagini. Per istruzioni dettagliate, vedere [Preparazione di un file CSV per una ricerca di contenuto personalizzati in Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="7adba-p111">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv. This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**. These fields contain information about the indexing error for each partially indexed item. Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation. If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation. For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="7adba-p112">**Nota:** Il file non indicizzate Items.csv contiene inoltre campi denominati **Tipo di errore** e il **Messaggio di errore**. Si tratta di campi legacy che contengono informazioni simili a quelle contenute nei campi **I tag di errore** e **Le proprietà di errore** , ma con informazioni meno dettagliate. È possibile ignorare questi campi legacy.</span><span class="sxs-lookup"><span data-stu-id="7adba-p112">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**. These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information. You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="7adba-151">Errori correlati agli elementi parzialmente indicizzati</span><span class="sxs-lookup"><span data-stu-id="7adba-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="7adba-p113">I tag di errore è costituiti da due tipi di informazioni, l'errore e il tipo di file. Ad esempio, in questa coppia di errori/filetype:</span><span class="sxs-lookup"><span data-stu-id="7adba-p113">Error tags are made up of two pieces of information, the error and the file type. For example, in this error/filetype pair:</span></span>

```
 parseroutputsize_xls
```

   
 <span data-ttu-id="7adba-p114">`parseroutputsize`è l'errore e `xls` corrisponde al tipo di file del file di cui si è verificato l'errore. In casi sono stati il tipo di file non è stato il tipo di file è stato riconosciuto o non si applica all'errore che verrà visualizzato il valore `noformat` al posto del tipo di file.</span><span class="sxs-lookup"><span data-stu-id="7adba-p114">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on. In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="7adba-156">Di seguito è un elenco di indicizzazione errori e una descrizione per la possibile causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="7adba-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="7adba-157">**Tag di errore**</span><span class="sxs-lookup"><span data-stu-id="7adba-157">**Error tag**</span></span>|<span data-ttu-id="7adba-158">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7adba-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="7adba-159">Messaggio di posta elettronica con un numero eccessivo di allegati e alcune di questi allegati non sono stati elaborati.</span><span class="sxs-lookup"><span data-stu-id="7adba-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="7adba-p115">Il parser fact e documenti contenuto trovato troppi livelli di allegati annidati all'interno degli altri allegati. Alcuni di questi allegati non sono stati elaborati.</span><span class="sxs-lookup"><span data-stu-id="7adba-p115">The content retriever and document parser found too many levels of attachments nested inside other attachments. Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="7adba-162">Un allegato non riuscito decodifica perché non è stato protetti con RMS.</span><span class="sxs-lookup"><span data-stu-id="7adba-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="7adba-163">Un file allegato al messaggio di posta elettronica è troppo grande e non può essere elaborato.</span><span class="sxs-lookup"><span data-stu-id="7adba-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="7adba-p116">Quando si scrive il messaggio di posta elettronica elaborato nell'indice, una delle proprietà indicizzabili troppo grande ed è stata troncata. Le proprietà troncate sono elencate nel campo proprietà errori.</span><span class="sxs-lookup"><span data-stu-id="7adba-p116">When writing the processed email message to the index, one of the indexable properties was too large and was truncated. The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="7adba-p117">Messaggio di posta elettronica contenuto testo che non è stato elaborato come Unicode valido. Indicizzazione di questo elemento può essere incompleta.</span><span class="sxs-lookup"><span data-stu-id="7adba-p117">An email message contained text that couldn't be processed as valid Unicode. Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="7adba-168">Il contenuto dell'allegato o messaggio di posta elettronica è crittografato e Office 365 non decodificare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="7adba-168">The content of attachment or email message is encrypted, and Office 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="7adba-p118">Si è verificato un errore sconosciuto durante l'analisi. Ciò è dovuto in genere a un bug software o un arresto anomalo del servizio.</span><span class="sxs-lookup"><span data-stu-id="7adba-p118">An unknown error occurred during parsing. This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="7adba-171">Un allegato è troppo grande per il parser per la gestione e l'analisi di tale allegato non avvenire o non è stato completato.</span><span class="sxs-lookup"><span data-stu-id="7adba-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="7adba-p119">Un allegato non valido e non gestito dal parser. Il risultato dal file precedente can formati, file creati da software incompatibile o virus FALSO qualcosa di diverso da quello richiesto.</span><span class="sxs-lookup"><span data-stu-id="7adba-p119">An attachment was malformed and couldn't be handled by the parser. This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="7adba-174">L'output dell'analisi di un allegato è troppo grande e hanno dovuto essere troncato.</span><span class="sxs-lookup"><span data-stu-id="7adba-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="7adba-175">Un allegato con un tipo di file che non è stato rilevato Office 365.</span><span class="sxs-lookup"><span data-stu-id="7adba-175">An attachment had a file type that Office 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="7adba-176">Un allegato con un tipo di file Office 365could rileva, ma l'analisi di tale tipo di file non è supportata.</span><span class="sxs-lookup"><span data-stu-id="7adba-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="7adba-p120">Il valore di una proprietà di un messaggio di posta elettronica di Exchange archivio è troppo grande per essere recuperati e il messaggio non è stato elaborato. Ciò accade di solito alla proprietà del corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="7adba-p120">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed. This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="7adba-179">La funzione di recupero del contenuto non riuscito decodificare un messaggio protetto con RMS.</span><span class="sxs-lookup"><span data-stu-id="7adba-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="7adba-p121">Sono state identificate troppe parole del documento durante l'indicizzazione. Elaborazione della proprietà interrotta quando sta per raggiungere il limite e la proprietà viene troncata.</span><span class="sxs-lookup"><span data-stu-id="7adba-p121">Too many words were identified in the document during indexing. Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="7adba-p122">Campi di errore vengono descritti i campi che sono interessati dall'errore elaborazione elencato nel campo tag di errore. Se si esegue la ricerca una proprietà come `subject` o `participants`, errori nel corpo del messaggio non influiscono su risultati della ricerca. Può essere utile per determinare esattamente quali elementi indicizzati parzialmente potrebbe essere necessario ulteriori analisi.</span><span class="sxs-lookup"><span data-stu-id="7adba-p122">Error fields describe which fields are affected by the processing error listed in the Error Tags field. If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search. This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="7adba-185">Utilizzo di uno script di PowerShell per determinare l'esposizione dell'organizzazione agli elementi di posta elettronica parzialmente indicizzati</span><span class="sxs-lookup"><span data-stu-id="7adba-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="7adba-p123">La procedura seguente è illustrato come eseguire uno script di PowerShell che esegue la ricerca per tutti gli elementi in tutte le cassette postali di Exchange, quindi genera un report su rapporto dell'organizzazione di elementi di posta elettronica parzialmente indicizzati (numero e dimensioni) e viene visualizzato il numero di elementi (e il tipo di file) per ogni errore di indicizzazione che si verifica. Utilizzare le descrizioni dei tag di errore nella sezione precedente per identificare l'errore di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="7adba-p123">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs. Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="7adba-188">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `PartiallyIndexedItems.ps1`.</span><span class="sxs-lookup"><span data-stu-id="7adba-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. <span data-ttu-id="7adba-189">[Connettersi a Office 365 protezione &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="7adba-189">[Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="7adba-190">In sicurezza &amp; PowerShell centro conformità, passare alla cartella a cui è stato salvato lo script nel passaggio 1 e quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="7adba-190">In Security &amp; Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
<span data-ttu-id="7adba-191">Di seguito è riportato un esempio fo l'output restituito dallo script.</span><span class="sxs-lookup"><span data-stu-id="7adba-191">Here's an example fo the output returned by the script.</span></span>
  
![Esempio di output di uno script che genera un report sull'esposizione dell'organizzazione agli elementi di posta elettronica parzialmente indicizzati](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="7adba-193">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7adba-193">Note the following:</span></span>
  
1. <span data-ttu-id="7adba-194">Il numero totale e le dimensioni degli elementi di posta elettronica e rapporto dell'organizzazione indicizzati parzialmente degli elementi di posta (numero e dimensioni)</span><span class="sxs-lookup"><span data-stu-id="7adba-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="7adba-195">Un tag di errore di elenco e i corrispondenti tipi di file per cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="7adba-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7adba-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7adba-196">See also</span></span>

<span data-ttu-id="7adba-197">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="7adba-197">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>
