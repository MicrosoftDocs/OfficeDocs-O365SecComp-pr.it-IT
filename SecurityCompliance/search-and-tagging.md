---
title: Ricerca e aggiunta di tag
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: In eDiscovery avanzate, la funzionalità di ricerca e utilizzo dei tag consente di ricercare, visualizzare in anteprima e organizzare i documenti nel case. In questo modulo è attualmente disponibile la versione beta.
ms.openlocfilehash: 013e559ca55e9a877dfb2f8747c4696f81e1e095
ms.sourcegitcommit: 25f1028643d8a20d17306e8b09cafea46eaf7a58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2019
ms.locfileid: "29666146"
---
# <a name="search-and-tagging"></a><span data-ttu-id="06ef1-104">Ricerca e aggiunta di tag</span><span class="sxs-lookup"><span data-stu-id="06ef1-104">Search and Tagging</span></span>

<span data-ttu-id="06ef1-p102">In eDiscovery avanzate, la funzionalità di ricerca e utilizzo dei tag consente di ricercare, visualizzare in anteprima e organizzare i documenti nel case. In questo modulo è attualmente disponibile la versione beta. Per una dimostrazione breve di ricerca e l'assegnazione dei tag, vedere il video di [gestione dei dati con eDiscovery avanzate](https://www.youtube.com/watch?v=VaPYL3DHP6I) .</span><span class="sxs-lookup"><span data-stu-id="06ef1-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta. For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="06ef1-p103">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="06ef1-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="06ef1-110">Cercare i documenti nel case</span><span class="sxs-lookup"><span data-stu-id="06ef1-110">Search the documents in your case</span></span>

<span data-ttu-id="06ef1-p104">Dopo avere elaborate documenti in un caso eDiscovery avanzate (e se lo si desidera eseguire la funzionalità di analisi o pertinenza), è possibile utilizzare la ricerca e utilizzo dei tag per cercare i documenti e quindi organizzare i contatti tramite l'applicazione di tag specifico (denominato anche le etichette). È possibile definire una query di ricerca tramite schede fornito condizione o condizione scheda utilizzando un linguaggio di query KQL simili le parole chiave. Sintassi KQL comune, ad esempio AND, OR, NOT, e NEAR(n) sono supportati, nonché finale più caratteri jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="06ef1-p104">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels). You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="06ef1-p105">Nella tabella seguente sono elencate le proprietà che è possibile cercare per l'utilizzo di una query con parole chiave KQL. In alternativa, è possibile utilizzare una scheda condizione per di eDiscovery avanzate dello strumento di ricerca per aggiungere una condizione (per le proprietà selezionate) a una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="06ef1-p105">The following table lists the properties that you can search for using a KQL keyword query. Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="06ef1-116">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="06ef1-116">**Property**</span></span>|<span data-ttu-id="06ef1-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="06ef1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="06ef1-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="06ef1-118">**caselabel**</span></span> <br/> | <span data-ttu-id="06ef1-119">Il nome del tag creato/applicato quando viene contrassegnato come un documento.</span><span class="sxs-lookup"><span data-stu-id="06ef1-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="06ef1-120">**depositaria**</span><span class="sxs-lookup"><span data-stu-id="06ef1-120">**custodian**</span></span> <br/> | <span data-ttu-id="06ef1-121">Depositaria associata a un documento. soggetta a limitazioni.</span><span class="sxs-lookup"><span data-stu-id="06ef1-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="06ef1-122">**Data**</span><span class="sxs-lookup"><span data-stu-id="06ef1-122">**date**</span></span> <br/> | <span data-ttu-id="06ef1-123">Inviati data per la posta elettronica; Data di modifica di documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="06ef1-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="06ef1-124">**fileid**</span><span class="sxs-lookup"><span data-stu-id="06ef1-124">**fileid**</span></span> <br/> | <span data-ttu-id="06ef1-125">ID di File all'interno del case.</span><span class="sxs-lookup"><span data-stu-id="06ef1-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="06ef1-126">**tipo di file**</span><span class="sxs-lookup"><span data-stu-id="06ef1-126">**filetype**</span></span> <br/> | <span data-ttu-id="06ef1-127">Estensione di file nativo.</span><span class="sxs-lookup"><span data-stu-id="06ef1-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="06ef1-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="06ef1-128">**fileclass**</span></span> <br/> | <span data-ttu-id="06ef1-129">Posta elettronica, documenti o degli allegati.</span><span class="sxs-lookup"><span data-stu-id="06ef1-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="06ef1-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="06ef1-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="06ef1-131">Il mittente per la posta elettronica; creazione di documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="06ef1-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="06ef1-132">**dimensioni**</span><span class="sxs-lookup"><span data-stu-id="06ef1-132">**size**</span></span> <br/> | <span data-ttu-id="06ef1-133">La dimensione del file in KB.</span><span class="sxs-lookup"><span data-stu-id="06ef1-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="06ef1-134">**si**</span><span class="sxs-lookup"><span data-stu-id="06ef1-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="06ef1-135">L'oggetto per la posta elettronica; il titolo di documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="06ef1-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="06ef1-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="06ef1-136">**bcc**</span></span> <br/> | <span data-ttu-id="06ef1-137">Il campo Ccn di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="06ef1-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="06ef1-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="06ef1-138">**cc**</span></span> <br/> | <span data-ttu-id="06ef1-139">Il campo Cc di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="06ef1-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="06ef1-140">**partecipanti**</span><span class="sxs-lookup"><span data-stu-id="06ef1-140">**participants**</span></span> <br/> | <span data-ttu-id="06ef1-141">L'indirizzo di posta elettronica di tutti i partecipanti a un thread di posta elettronica, inclusi i collegamenti mancante.</span><span class="sxs-lookup"><span data-stu-id="06ef1-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="06ef1-142">**ricevuta**</span><span class="sxs-lookup"><span data-stu-id="06ef1-142">**received**</span></span> <br/> | <span data-ttu-id="06ef1-143">Data che è stato ricevuto un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="06ef1-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="06ef1-144">**destinatari**</span><span class="sxs-lookup"><span data-stu-id="06ef1-144">**recipients**</span></span> <br/> | <span data-ttu-id="06ef1-145">Destinatari di un messaggio di posta elettronica, inclusi su a, Cc o Ccn campi.</span><span class="sxs-lookup"><span data-stu-id="06ef1-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="06ef1-146">**mittente**</span><span class="sxs-lookup"><span data-stu-id="06ef1-146">**sender**</span></span> <br/> | <span data-ttu-id="06ef1-147">Il mittente di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="06ef1-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="06ef1-148">**LastModifiedDate**</span><span class="sxs-lookup"><span data-stu-id="06ef1-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="06ef1-149">L'ultima data di un documento di un sito.</span><span class="sxs-lookup"><span data-stu-id="06ef1-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="06ef1-150">**inviati**</span><span class="sxs-lookup"><span data-stu-id="06ef1-150">**sent**</span></span> <br/> | <span data-ttu-id="06ef1-151">Data di invio di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="06ef1-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="06ef1-152">**A**</span><span class="sxs-lookup"><span data-stu-id="06ef1-152">**to**</span></span> <br/> | <span data-ttu-id="06ef1-153">Il destinatario elencato nel campo a di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="06ef1-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="06ef1-154">**autore**</span><span class="sxs-lookup"><span data-stu-id="06ef1-154">**author**</span></span> <br/> | <span data-ttu-id="06ef1-155">L'autore di un documento di un sito.</span><span class="sxs-lookup"><span data-stu-id="06ef1-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="06ef1-156">**titolo**</span><span class="sxs-lookup"><span data-stu-id="06ef1-156">**title**</span></span> <br/> | <span data-ttu-id="06ef1-157">Il titolo di un documento di un sito.</span><span class="sxs-lookup"><span data-stu-id="06ef1-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="06ef1-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="06ef1-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="06ef1-159">Il tema dominante di un elemento.</span><span class="sxs-lookup"><span data-stu-id="06ef1-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="06ef1-160">**themeslist**\*</span><span class="sxs-lookup"><span data-stu-id="06ef1-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="06ef1-161">Temi associati a un elemento.</span><span class="sxs-lookup"><span data-stu-id="06ef1-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="06ef1-162">**readpercentile_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="06ef1-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="06ef1-163">Percentile lettura di un elemento per il rilascio definito da [issuenum].</span><span class="sxs-lookup"><span data-stu-id="06ef1-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="06ef1-164">**relevancescore_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="06ef1-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="06ef1-165">Il punteggio di pertinenza di un elemento per il rilascio definito da [issuenum].</span><span class="sxs-lookup"><span data-stu-id="06ef1-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="06ef1-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="06ef1-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="06ef1-167">Se un elemento è stato contrassegnato manualmente la pertinenza, il tag definito dalla [tagname].</span><span class="sxs-lookup"><span data-stu-id="06ef1-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="06ef1-168">\*È disponibile solo se è stato eseguito il modulo di temi.</span><span class="sxs-lookup"><span data-stu-id="06ef1-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="06ef1-169">\*\*È disponibile solo se è stato eseguito il modulo di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="06ef1-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="06ef1-p106">In alternativa, è possibile utilizzare una scheda condizione di eDiscovery avanzate dello strumento di ricerca per aggiungere una condizione (per le proprietà selezionate) a una query di ricerca. La schermata seguente mostra le condizioni che possono essere aggiunti a una query. Nella colonna **gruppo** indica se la proprietà si applica al messaggio di posta elettronica, documenti del sito o a entrambi (indicata dal valore *comune*). Questa colonna vengono indicati le proprietà supportano la ricerca sono disponibili dopo l'esecuzione del modulo di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="06ef1-p106">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query. The following screenshot shows the conditions that can be added to a query. The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*). This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![I criteri di ricerca nello strumento di ricerca avanzata eDiscovery](media/AeDSearchConditions.png)

<span data-ttu-id="06ef1-175">Per ulteriori informazioni sulle proprietà di ricerca, vedere [query con parole chiave e le condizioni di ricerca](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="06ef1-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="06ef1-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06ef1-176">See also</span></span>

[<span data-ttu-id="06ef1-177">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="06ef1-177">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="06ef1-178">Informazioni sulla valutazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="06ef1-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="06ef1-179">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="06ef1-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="06ef1-180">Tagging e formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="06ef1-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="06ef1-181">Analisi di pertinenza di verifica</span><span class="sxs-lookup"><span data-stu-id="06ef1-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="06ef1-182">Stabilire in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="06ef1-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="06ef1-183">Test di analisi di pertinenza</span><span class="sxs-lookup"><span data-stu-id="06ef1-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

