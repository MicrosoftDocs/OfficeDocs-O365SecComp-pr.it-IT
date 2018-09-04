---
title: Limiti per la ricerca del contenuto in Office 365 protezione &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/30/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: 'Informazioni sui limiti valido per la funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità, ad esempio il numero massimo di ricerche simultanee. '
ms.openlocfilehash: 896d1fb5aafb7ae28f00c5e19af229415d800f36
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530834"
---
# <a name="limits-for-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="87d25-103">Limiti per la ricerca del contenuto in Office 365 protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="87d25-103">Limits for Content Search in the Office 365 Security &amp; Compliance Center</span></span>

> [!NOTE]
> <span data-ttu-id="87d25-104">I limiti riportati in questo argomento sono diversi da quelli correnti per eDiscovery In locale in Exchange Online e per il centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="87d25-104">The limits in this topic are different from the current limits for In-Place eDiscovery in Exchange Online and for the eDiscovery Center in SharePoint Online.</span></span> 
  
<span data-ttu-id="87d25-p101">Limiti vari vengono applicati alla funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità. In questo ricerche include eseguire nella pagina di **ricerca del contenuto** e le ricerche associati a un caso eDiscovery. Questi limiti utili per mantenere l'integrità e la qualità dei servizi forniti per organizzazioni di Office 365. Esistono limiti relativi all'indicizzazione di messaggi di posta elettronica di Exchange Online per la ricerca. Non è possibile modificare la ricerca del contenuto o posta elettronica indicizzazione limiti, ma è necessario tenere conto di essi in modo che è possibile eseguire questi limiti in considerazione durante la pianificazione, l'esecuzione e la risoluzione dei problemi di ricerche di contenuto.</span><span class="sxs-lookup"><span data-stu-id="87d25-p101">Various limits are applied to the Content Search feature in the Office 365 Security &amp; Compliance Center. This include searches run on the **Content search** page and searches that are associated with an eDiscovery case. These limits help to maintain the health and quality of services provided to Office 365 organizations. There are also limits related to the indexing of email messages in Exchange Online for search. You can't modify the Content Search or email indexing limits, but you should be aware of them so that you can take these limits into consideration when planning, running, and troubleshooting Content Searches.</span></span> 
  
 <span data-ttu-id="87d25-110">**Sommario**</span><span class="sxs-lookup"><span data-stu-id="87d25-110">**Contents**</span></span>
  
[<span data-ttu-id="87d25-111">Limiti relativi alla ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="87d25-111">Content Search limits</span></span>](limits-for-content-search.md#searchlimits)
  
[<span data-ttu-id="87d25-112">Limiti di indicizzazione per i messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="87d25-112">Indexing limits for email messages</span></span>](limits-for-content-search.md#indexinglimits)
  
[<span data-ttu-id="87d25-113">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="87d25-113">More information</span></span>](limits-for-content-search.md#moreinfo)
  
## <a name="content-search-limits"></a><span data-ttu-id="87d25-114">Limiti relativi alla ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="87d25-114">Content Search limits</span></span>
<span data-ttu-id="87d25-115"><a name="searchlimits"> </a></span><span class="sxs-lookup"><span data-stu-id="87d25-115"></span></span>

<span data-ttu-id="87d25-116">Nella tabella seguente sono elencati i limiti di ricerca nella protezione &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="87d25-116">The following table lists the search limits in the Security &amp; Compliance Center.</span></span>
  
|<span data-ttu-id="87d25-117">**Descrizione del limite**</span><span class="sxs-lookup"><span data-stu-id="87d25-117">**Description of limit**</span></span>|<span data-ttu-id="87d25-118">**Tipo di limite**</span><span class="sxs-lookup"><span data-stu-id="87d25-118">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="87d25-119">Il numero massimo di cassette postali o siti che possono essere ricercati in una singola ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="87d25-119">The maximum number of mailboxes or sites that can be searched in a single Content Search</span></span>  <br/> |<span data-ttu-id="87d25-120">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="87d25-120">No limit</span></span>  <br/> |
|<span data-ttu-id="87d25-121">Il numero massimo di ricerche di contenuto che è possibile eseguire contemporaneamente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="87d25-121">The maximum number of Content Searches that can run at the same time in your organization.</span></span>  <br/> |<span data-ttu-id="87d25-122">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="87d25-122">No limit</span></span>  <br/> |
|<span data-ttu-id="87d25-p102">Il numero massimo di ricerche di contenuto che un singolo utente possono essere avviati contemporaneamente. Si noti che questo limite viene raggiunto più comodo quando l'utente tenta di avviare più ricerche utilizzando il **Get-ComplianceSearch \| Start ComplianceSearch** comando PowerShell centro conformità e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="87d25-p102">The maximum number of Content Searches that a single user can start at the same time. Note that this limit is most likely hit when the user tries to start multiple searches by using the **Get-ComplianceSearch \| Start-ComplianceSearch** command in Security & Compliance Center PowerShell.  </span></span><br/> |<span data-ttu-id="87d25-125">10 </span><span class="sxs-lookup"><span data-stu-id="87d25-125">10</span></span>  <br/> |
|<span data-ttu-id="87d25-126">Il numero massimo di elementi per ogni cassetta postale dell'utente che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto.</span><span class="sxs-lookup"><span data-stu-id="87d25-126">The maximum number of items per user mailbox that are displayed on the preview page when previewing Content Search results.</span></span>  <br/> |<span data-ttu-id="87d25-127">100</span><span class="sxs-lookup"><span data-stu-id="87d25-127">100</span></span>  <br/> |
|<span data-ttu-id="87d25-p103">Numero massimo di elementi disponibili in tutte le cassette postali degli utenti che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto. Vengono visualizzati gli elementi più recenti.</span><span class="sxs-lookup"><span data-stu-id="87d25-p103">The maximum number of items found in all user mailboxes that are displayed on the preview page when previewing Content Search results. The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="87d25-130">1,000</span><span class="sxs-lookup"><span data-stu-id="87d25-130">1,000</span></span>  <br/> |
|<span data-ttu-id="87d25-p104">Il numero massimo di cassette postali degli utenti che possono essere visualizzati in anteprima dei risultati della ricerca. Se sono presenti più di 1000 cassette postali che includono contenuto corrispondente alla query di ricerca, solo le prime 1000 cassette postali con la maggior parte dei risultati della ricerca saranno disponibili per l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="87d25-p104">The maximum number of user mailboxes that can be previewed for search results. If there are more than 1000 mailboxes that contain content that matches the search query, only the top 1000 mailboxes with the most search results will be available for preview.</span></span>  <br/> |<span data-ttu-id="87d25-133">1,000</span><span class="sxs-lookup"><span data-stu-id="87d25-133">1,000</span></span>  <br/> |
|<span data-ttu-id="87d25-p105">Numero massimo di elementi disponibili in SharePoint e OneDrive per i siti che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto. Vengono visualizzati gli elementi più recenti.</span><span class="sxs-lookup"><span data-stu-id="87d25-p105">The maximum number of items found in SharePoint and OneDrive for Business sites that are displayed on the preview page when previewing Content Search results. The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="87d25-136">200</span><span class="sxs-lookup"><span data-stu-id="87d25-136">200</span></span>  <br/> |
|<span data-ttu-id="87d25-p106">Il numero massimo di siti (in SharePoint e OneDrive for Business) che può essere visualizzata l'anteprima dei risultati della ricerca. Se sono presenti più di 200 siti totali che includono contenuto corrispondente alla query di ricerca, solo i siti principali 200 con la maggior parte dei risultati della ricerca saranno disponibili per l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="87d25-p106">The maximum number of sites (in SharePoint and OneDrive for Business) that can be previewed for search results. If there are more than 200 total sites that contain content that matches the search query, only the top 200 sites with the most search results will be available for preview.</span></span>  <br/> |<span data-ttu-id="87d25-139">200</span><span class="sxs-lookup"><span data-stu-id="87d25-139">200</span></span>  <br/> |
|<span data-ttu-id="87d25-140">Il numero massimo di elementi per ogni cassetta postale di cartelle pubbliche che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto.</span><span class="sxs-lookup"><span data-stu-id="87d25-140">The maximum number of items per public folder mailbox that are displayed on the preview page when previewing Content Search results.</span></span>  <br/> |<span data-ttu-id="87d25-141">100</span><span class="sxs-lookup"><span data-stu-id="87d25-141">100</span></span>  <br/> |
|<span data-ttu-id="87d25-142">Numero massimo di elementi disponibili in tutte le cassette postali di cartelle pubbliche che vengono visualizzate nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto.</span><span class="sxs-lookup"><span data-stu-id="87d25-142">The maximum number of items found in all public folder mailboxes that are displayed on the preview page when previewing Content Search results.</span></span>  <br/> |<span data-ttu-id="87d25-143">200</span><span class="sxs-lookup"><span data-stu-id="87d25-143">200</span></span>  <br/> |
|<span data-ttu-id="87d25-p107">Il numero massimo di cassette postali pubbliche possono visualizzare in anteprima dei risultati della ricerca. Se sono presenti più di 500 cassette postali delle cartelle pubbliche che includono contenuto corrispondente alla query di ricerca, solo le prime 500 cartelle pubbliche cassette postali con la maggior parte dei risultati della ricerca saranno disponibili per l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="87d25-p107">The maximum number of public mailboxes that can be previewed for search results. If there are more than 500 public folder mailboxes that contain content that matches the search query, only the top 500 public folder mailboxes with the most search results will be available for preview.</span></span>  <br/> |<span data-ttu-id="87d25-146">500</span><span class="sxs-lookup"><span data-stu-id="87d25-146">500</span></span>  <br/> |
|<span data-ttu-id="87d25-147">Numero massimo di caratteri per la query di ricerca (inclusi gli operatori e condizioni) per una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="87d25-147">The maximum number of characters for the search query (including operators and conditions) for a Content Search.</span></span>  <br/> <span data-ttu-id="87d25-p108">**Nota:** Questo limite avrà effetto dopo la query viene espansa, ovvero le che query verrà ottenere espansa per ognuna delle parole chiave. Ad esempio, se una query di ricerca è 15 parole chiave e parametri aggiuntivi e le condizioni, la query viene espanso 15 volte, ognuno con gli altri parametri e le condizioni nella query. Anche se il numero di caratteri inclusi nella query di ricerca può essere inferiore al limite, è la query espansa che può contribuire alla se si supera questo limite.</span><span class="sxs-lookup"><span data-stu-id="87d25-p108">**Note:** This limit takes effect after the query is expanded, which means the query will get expanded against each of the keywords. For example, if a search query has 15 keywords and additional parameters and conditions, the query gets expanded 15 times, each with the other parameters and conditions in the query. So even though the number of characters in search query may be below the limit, it's the expanded query that may contribute to exceeding this limit.  </span></span><br/> |<span data-ttu-id="87d25-151">**Le cassette postali:** 10.000</span><span class="sxs-lookup"><span data-stu-id="87d25-151">**Mailboxes:** 10,000</span></span>  <br/> <span data-ttu-id="87d25-152">**Siti:** 4.000 durante la ricerca di tutti i siti o 2.000 durante la ricerca un massimo di 20 siti <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="87d25-152">**Sites:** 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>1</sup></span></span> <br/> |
|<span data-ttu-id="87d25-153">Numero massimo di valori Variant restituiti quando si utilizza un prefisso con caratteri jolly per cercare una frase specifica in una query di ricerca o quando si utilizza un carattere jolly prefisso e l'operatore booleano **NEAR** o **ONEAR** .</span><span class="sxs-lookup"><span data-stu-id="87d25-153">Maximum number of variants returned when using a prefix wildcard to search for an exact phrase in a search query or when using a prefix wildcard and the **NEAR** or **ONEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="87d25-154">10.000<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="87d25-154">10,000<sup>2</sup></span></span> <br/> |
|<span data-ttu-id="87d25-155">Il numero minimo di caratteri alfabetici per i caratteri jolly prefisso; ad esempio `time*`, `one*`, o `set*`.</span><span class="sxs-lookup"><span data-stu-id="87d25-155">The minimum number of alpha characters for prefix wildcards; for example,  `time*`,  `one*`, or  `set*`.</span></span>  <br/> |<span data-ttu-id="87d25-156">3</span><span class="sxs-lookup"><span data-stu-id="87d25-156">3</span></span>  <br/> |
|<span data-ttu-id="87d25-p109">Il numero massimo di cassette postali in una ricerca di contenuto che è possibile eliminare gli elementi nel eseguendo un'azione "cercare ed eliminare" (utilizzando il **ComplianceSearchAction New-eliminare** comando). Se la ricerca del contenuto che si sta eseguendo un'azione di eliminazione per dispone di più cassette postali di origine questo limite, l'azione di eliminazione avrà esito negativo. Per ulteriori informazioni sulla ricerca ed eliminazione, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione Office 365](search-for-and-delete-messages-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="87d25-p109">The maximum number of mailboxes in a Content Search that you can delete items in by doing a "search and purge" action (by using the **New-ComplianceSearchAction -Purge** command). If the Content Search that you're doing a purge action for has more source mailboxes than this limit, the purge action will fail. For more information about search and purge, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).  </span></span><br/> |<span data-ttu-id="87d25-160">50.000</span><span class="sxs-lookup"><span data-stu-id="87d25-160">50,000</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="87d25-p110"><sup>1</sup> durante la ricerca di SharePoint e OneDrive per i percorsi di Business, gli URL dei siti in cui cercare i caratteri vengono contati su questo limite. > <sup>2</sup> per le query non frase (un valore parola chiave che non utilizza le virgolette doppie) viene utilizzato un indice prefisso speciale. Ciò indica che si verifica una parola in un documento, ma non dove si trova nel documento. Per eseguire una query di frase (un valore di parola chiave con le virgolette doppie), è necessario confrontare la posizione all'interno del documento per le parole nella frase. Ciò significa che è possibile utilizzare l'indice di prefisso per le query di frase. In questo caso, è internamente espandere le query con tutte le parole possibili che si espande il prefisso per; ad esempio `"time*"` possibile espandere a `"time OR timer OR times OR timex OR timeboxed OR …"`. 10.000 è il numero massimo di valori Variant che può espandere la parola e non il numero di documenti che soddisfano la query. Non esiste alcun limite massimo di termini non frase.</span><span class="sxs-lookup"><span data-stu-id="87d25-p110"><sup>1</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched are counted against this limit. > <sup>2</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index. This tells us that a word occurs in a document, but not where it occurs in the document. To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase. This means that we can't use the prefix index for phrase queries. In this case, we internally expand the query with all possible words that the prefix expands to; for example,  `"time*"` can expand to  `"time OR timer OR times OR timex OR timeboxed OR …"`. 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query. There is no upper limit for non-phrase terms.</span></span> 
  
[<span data-ttu-id="87d25-169">Inizio pagina</span><span class="sxs-lookup"><span data-stu-id="87d25-169">Return to top</span></span>](limits-for-content-search.md#top)
  
## <a name="indexing-limits-for-email-messages"></a><span data-ttu-id="87d25-170">Limiti di indicizzazione per i messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="87d25-170">Indexing limits for email messages</span></span>
<span data-ttu-id="87d25-171"><a name="indexinglimits"> </a></span><span class="sxs-lookup"><span data-stu-id="87d25-171"></span></span>

<span data-ttu-id="87d25-172">Nella tabella seguente vengono descritti i limiti di indicizzazione che possono causare tempi di un messaggio di posta elettronica vengono restituito come un elemento non indicizzato o un elemento indicizzato parzialmente nei risultati della ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="87d25-172">The following table describes the indexing limits that might result in an email message being returned as an unindexed item or a partially indexed item in the results of a Content Search.</span></span>
  
|<span data-ttu-id="87d25-173">**Limite di indicizzazione**</span><span class="sxs-lookup"><span data-stu-id="87d25-173">**Indexing limit**</span></span>|<span data-ttu-id="87d25-174">**Note**</span><span class="sxs-lookup"><span data-stu-id="87d25-174">**Maximum value**</span></span>|<span data-ttu-id="87d25-175">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="87d25-175">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="87d25-176">Dimensione massima degli allegati (esclusi i file di Excel)</span><span class="sxs-lookup"><span data-stu-id="87d25-176">Maximum attachment size (excluding Excel files)</span></span>  <br/> |<span data-ttu-id="87d25-177">150 MB</span><span class="sxs-lookup"><span data-stu-id="87d25-177">150 MB</span></span>  <br/> |<span data-ttu-id="87d25-p111">La dimensione massima di un allegato di posta elettronica che consente di analizzare per l'indicizzazione. Gli allegati che superano questo limite non vengono analizzati per l'indicizzazione e il messaggio con allegato viene contrassegnato come parzialmente indicizzato.</span><span class="sxs-lookup"><span data-stu-id="87d25-p111">The maximum size of an email attachment that will parse for indexing. Any attachment that's larger than this limit won't be parsed for indexing, and the message with the attachment will be marked as partially indexed.  </span></span><br/> <span data-ttu-id="87d25-180">> [!NOTE]> L'analisi è il processo di cui il servizio di indicizzazione estrae il testo dalla allegato, rimuove i caratteri non necessari, ad esempio i segni di punteggiatura e spazi e quindi lo divide il testo in parole (in un processo denominato la suddivisione in token), che vengono memorizzati in corrispondenza dell'indice.</span><span class="sxs-lookup"><span data-stu-id="87d25-180">> [!NOTE]> Parsing is the process where the indexing service extracts text from the attachment, removes unnecessary characters like punctuation and spaces, and then divides the text into words (in a process called tokenization), that are then stored in the index.</span></span>           |
|<span data-ttu-id="87d25-181">Dimensione massima dei file di Excel</span><span class="sxs-lookup"><span data-stu-id="87d25-181">Maximum size of Excel files</span></span>  <br/> |<span data-ttu-id="87d25-182">4 MB</span><span class="sxs-lookup"><span data-stu-id="87d25-182">4 MB</span></span>  <br/> |<span data-ttu-id="87d25-p112">La dimensione massima di un file di Excel presente in un sito o associato a un messaggio di posta elettronica che viene analizzato per l'indicizzazione. Eventuali file di Excel che è maggiore della non verrà analizzato questo limite e il file o messaggio di posta elettronica che il messaggio con allegato il file verrà contrassegnato come non indicizzate.</span><span class="sxs-lookup"><span data-stu-id="87d25-p112">The maximum size of an Excel file located on a site or attached to an email message that will be parsed for indexing. Any Excel file that's larger than this limit won't be parsed, and the file or the email the message with the file attachment will be marked as unindexed.</span></span>  <br/> |
|<span data-ttu-id="87d25-185">Numero massimo di allegati</span><span class="sxs-lookup"><span data-stu-id="87d25-185">Maximum number of attachments</span></span>  <br/> |<span data-ttu-id="87d25-186">250</span><span class="sxs-lookup"><span data-stu-id="87d25-186">250</span></span>  <br/> |<span data-ttu-id="87d25-p113">Numero massimo di file allegato al messaggio di posta elettronica che viene analizzato per l'indicizzazione. Se un messaggio non ha più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio è contrassegnato come parzialmente indicizzato perché era allegati aggiuntivi che non sono stati analizzati.</span><span class="sxs-lookup"><span data-stu-id="87d25-p113">The maximum number of files attached to an email message that will be parsed for indexing. If a message has more than 250 attachments, the first 250 attachments are parsed and indexed, and the message is marked as partially indexed because it had additional attachments that weren't parsed.</span></span>  <br/> |
|<span data-ttu-id="87d25-189">Profondità massima degli allegati</span><span class="sxs-lookup"><span data-stu-id="87d25-189">Maximum attachment depth</span></span>  <br/> |<span data-ttu-id="87d25-190">30</span><span class="sxs-lookup"><span data-stu-id="87d25-190">30</span></span>  <br/> |<span data-ttu-id="87d25-p114">Il numero massimo di allegati nidificati che vengono analizzati. Ad esempio, se un messaggio di posta elettronica con un altro messaggio associato e il messaggio allegato è un documento di Word, il documento di Word e il messaggio allegato verrà essere indicizzati. Questo comportamento continua per gli allegati annidati fino a 30.</span><span class="sxs-lookup"><span data-stu-id="87d25-p114">The maximum number of nested attachments that are parsed. For example, if an email message has another message attached to it and the attached message has an attached Word document, the Word document and the attached message will be indexed. This behavior will continue for up to 30 nested attachments.</span></span>  <br/> |
|<span data-ttu-id="87d25-194">Numero massimo di immagini associate</span><span class="sxs-lookup"><span data-stu-id="87d25-194">Maximum number of attached images</span></span>  <br/> |<span data-ttu-id="87d25-195">0</span><span class="sxs-lookup"><span data-stu-id="87d25-195">0</span></span>  <br/> |<span data-ttu-id="87d25-196">Immagine in cui è associata a un messaggio di posta elettronica viene ignorata dal parser e non è indicizzata.</span><span class="sxs-lookup"><span data-stu-id="87d25-196">An image that's attached to an email message is skipped by the parser and isn't indexed.</span></span>  <br/> |
|<span data-ttu-id="87d25-197">Tempo massimo trascorso per l'analisi di un elemento</span><span class="sxs-lookup"><span data-stu-id="87d25-197">Maximum time spent parsing an item</span></span>  <br/> |<span data-ttu-id="87d25-198">30 secondi</span><span class="sxs-lookup"><span data-stu-id="87d25-198">30 seconds</span></span>  <br/> |<span data-ttu-id="87d25-p115">È trascorso un massimo di 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera 30 secondi, l'elemento è contrassegnato come parzialmente indicizzato.</span><span class="sxs-lookup"><span data-stu-id="87d25-p115">A maximum of 30 seconds is spent parsing an item for indexing. If the parsing time exceeds 30 seconds, the item is marked as partially indexed.</span></span>  <br/> |
|<span data-ttu-id="87d25-201">Output parser massimo</span><span class="sxs-lookup"><span data-stu-id="87d25-201">Maximum parser output</span></span>  <br/> |<span data-ttu-id="87d25-202">2 milioni di caratteri</span><span class="sxs-lookup"><span data-stu-id="87d25-202">2 million characters</span></span>  <br/> |<span data-ttu-id="87d25-p116">La quantità massima di output di testo da parser indicizzato. Ad esempio, se il parser estratto 8 milioni di caratteri da un documento, solo i primi 2 milioni di caratteri vengono indicizzati.</span><span class="sxs-lookup"><span data-stu-id="87d25-p116">The maximum amount of text output from the parser that's indexed. For example, if the parser extracted 8 million characters from a document, only the first 2 million characters are indexed.</span></span>  <br/> |
|<span data-ttu-id="87d25-205">Token di annotazione massimo</span><span class="sxs-lookup"><span data-stu-id="87d25-205">Maximum annotation tokens</span></span>  <br/> |<span data-ttu-id="87d25-206">2 milioni</span><span class="sxs-lookup"><span data-stu-id="87d25-206">2 million</span></span>  <br/> |<span data-ttu-id="87d25-p117">Quando un messaggio di posta elettronica è indicizzato, ogni parola con annotazioni con istruzioni di elaborazione diversi che specificano come deve essere indicizzato da word. Ogni set di istruzioni di elaborazione viene chiamato un token di annotazione. Per garantire la qualità del servizio di Office 365, non esiste un limite di token di annotazione 2 milioni per un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="87d25-p117">When an email message is indexed, each word is annotated with different processing instructions that specify how that word should be indexed. Each set of processing instructions is called an annotation token. To maintain the quality of service in Office 365, there is a limit of 2 million annotation tokens for an email message.</span></span>  <br/> |
|<span data-ttu-id="87d25-210">Dimensioni massime del corpo nell'indice</span><span class="sxs-lookup"><span data-stu-id="87d25-210">Maximum body size in index</span></span>  <br/> |<span data-ttu-id="87d25-211">67 milioni di caratteri</span><span class="sxs-lookup"><span data-stu-id="87d25-211">67 million characters</span></span>  <br/> |<span data-ttu-id="87d25-p118">Numero totale di caratteri nel corpo del messaggio di posta elettronica e tutti i suoi allegati. Quando un messaggio di posta elettronica è indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati è concatenato in un'unica stringa. La dimensione massima della stringa indicizzato è 67 milioni di caratteri.</span><span class="sxs-lookup"><span data-stu-id="87d25-p118">The total number of characters in the body of an email message and all its attachments. When an email message is indexed, all text in the body of the message and in all attachments is concatenated into a single string. The maximum size of this string that is indexed is 67 million characters.</span></span>  <br/> |
|<span data-ttu-id="87d25-215">Token univoco massimo nel corpo</span><span class="sxs-lookup"><span data-stu-id="87d25-215">Maximum unique tokens in body</span></span>  <br/> |<span data-ttu-id="87d25-216">1 milione</span><span class="sxs-lookup"><span data-stu-id="87d25-216">1 million</span></span>  <br/> |<span data-ttu-id="87d25-p119">Come precedentemente illustrato, token sono il risultato di estrazione del testo rispetto al contenuto, rimuovendo i segni di punteggiatura e spazi e quindi la suddivisione in parole (noti come token) che vengono archiviate in corrispondenza dell'indice. Ad esempio, la frase `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 questi sono i token univoci. Non esiste un limite di 1 milione token univoco per ogni messaggio di posta elettronica, che consente di impedire l'indice di Guida troppo grande con token casuale.</span><span class="sxs-lookup"><span data-stu-id="87d25-p119">As previously explained, tokens are the result of extracting text from content, removing punctuation and spaces, and then dividing it into words (called tokens) that are stored in the index. For example, the phrase  `"cat, mouse, bird, dog, dog"` contains 5 tokens. But only 4 of these are unique tokens. There is a limit of 1 million unique tokens per email message, which helps prevent the index from getting too large with random tokens.  </span></span><br/> |
   
[<span data-ttu-id="87d25-221">Return to top</span><span class="sxs-lookup"><span data-stu-id="87d25-221">Return to top</span></span>](limits-for-content-search.md#top)
  
## <a name="more-information"></a><span data-ttu-id="87d25-222">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="87d25-222">More information</span></span>
<span data-ttu-id="87d25-223"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="87d25-223"></span></span>

<span data-ttu-id="87d25-p120">Esistono limiti aggiuntive correlate a diversi aspetti di ricerca di contenuti, ad esempio l'esportazione dei risultati di ricerca e indicizzazione del contenuto. Per una descrizione di questi limiti, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="87d25-p120">There are additional limits related to different aspects of Content Search, such as exporting search results and content indexing. For a description of these limits, see the following topics:</span></span>
  
- 
    
- <span data-ttu-id="87d25-226">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="87d25-226">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>
    
- <span data-ttu-id="87d25-227">[Investigating partially indexed items in Office 365 eDiscovery](investigating-partially-indexed-items-in-ediscovery.md) (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)</span><span class="sxs-lookup"><span data-stu-id="87d25-227">[Investigating partially indexed items in Office 365 eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)</span></span>
    
- [<span data-ttu-id="87d25-228">Limiti relativi alla ricerca per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="87d25-228">Search limits for SharePoint Online</span></span>](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f)
    
<span data-ttu-id="87d25-229">Per informazioni sulle ricerche del contenuto, vedere:</span><span class="sxs-lookup"><span data-stu-id="87d25-229">For information about Content Searches, see:</span></span>
  
- [<span data-ttu-id="87d25-230">Ricerca del contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="87d25-230">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="87d25-231">Query delle parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="87d25-231">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
[<span data-ttu-id="87d25-232">Inizio pagina</span><span class="sxs-lookup"><span data-stu-id="87d25-232">Return to top</span></span>](limits-for-content-search.md#top)
  
