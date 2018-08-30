---
title: Ricerca e aggiunta di tag
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: In eDiscovery avanzate, la funzionalità di ricerca e utilizzo dei tag consente di ricercare, visualizzare in anteprima e organizzare i documenti nel case. In questo modulo è attualmente disponibile la versione beta.
ms.openlocfilehash: fde887e496e9a40aa88d841053a0c66e48f04200
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530880"
---
# <a name="search-and-tagging"></a><span data-ttu-id="c157e-104">Ricerca e aggiunta di tag</span><span class="sxs-lookup"><span data-stu-id="c157e-104">Search and Tagging</span></span>

<span data-ttu-id="c157e-p102">In eDiscovery avanzate, la funzionalità di ricerca e utilizzo dei tag consente di ricercare, visualizzare in anteprima e organizzare i documenti nel case. In questo modulo è attualmente disponibile la versione beta.</span><span class="sxs-lookup"><span data-stu-id="c157e-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta.</span></span>

> [!NOTE]
> <span data-ttu-id="c157e-p103">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="c157e-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="c157e-109">Cercare i documenti nel case</span><span class="sxs-lookup"><span data-stu-id="c157e-109">Search the documents in your case</span></span>

<span data-ttu-id="c157e-p104">Una volta che viene elaborata documenti di eDiscovery avanzate e se lo si desidera eseguire la funzionalità di analisi o il modulo di pertinenza, è possibile utilizzare la ricerca e utilizzo dei tag per cercare i documenti nel caso e organizzare i contatti utilizzando i tag specifico. È possibile definire la query utilizzando le schede condizione specificata o tramite un linguaggio di query KQL simili le parole chiave condizione scheda. Sintassi KQL comune, ad esempio AND, OR, NOT, e NEAR(n) sono supportati, nonché finale più caratteri jolly (\*). Queste proprietà sono supportate nel nome della proprietà language query:</span><span class="sxs-lookup"><span data-stu-id="c157e-p104">Once you have processed documents in Advanced eDiscovery and optionally run the Analyze module or the Relevance module, you can use Search and Tagging to search through the documents in the case and organize them using case-specific tags. You can define your queries using the provided condition cards, or through a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*). These properties are supported in the query language property name:</span></span>

- <span data-ttu-id="c157e-114">caselabel: creato/applicati tag nel servizio di ricerca e utilizzo dei tag di questo case</span><span class="sxs-lookup"><span data-stu-id="c157e-114">caselabel: tags created/applied in Search and Tagging for this case</span></span> 
- <span data-ttu-id="c157e-115">depositari: depositari assegnati nel caso - soggetta a limitazioni</span><span class="sxs-lookup"><span data-stu-id="c157e-115">custodians: custodians assigned in the case - subject to limitations</span></span>
- <span data-ttu-id="c157e-116">Data: data per la posta elettronica inviati, data per i documenti di modifica</span><span class="sxs-lookup"><span data-stu-id="c157e-116">date: sent date for email, modified date for documents</span></span>
- <span data-ttu-id="c157e-117">fileid: ID del file all'interno del case</span><span class="sxs-lookup"><span data-stu-id="c157e-117">fileid: file ID within the case</span></span>
- <span data-ttu-id="c157e-118">FileType: estensione nativa</span><span class="sxs-lookup"><span data-stu-id="c157e-118">filetype: native file extension</span></span>
- <span data-ttu-id="c157e-119">fileclass: messaggio di posta elettronica, documenti o degli allegati</span><span class="sxs-lookup"><span data-stu-id="c157e-119">fileclass: email, document, or attachment</span></span>
- <span data-ttu-id="c157e-120">senderauthor: mittenti di messaggi di posta elettronica, autore per i documenti</span><span class="sxs-lookup"><span data-stu-id="c157e-120">senderauthor: sender for emails, author for documents</span></span>
- <span data-ttu-id="c157e-121">dimensione: dimensione del file in KB</span><span class="sxs-lookup"><span data-stu-id="c157e-121">size: size of the file in KB</span></span>
- <span data-ttu-id="c157e-122">si: interesse per i messaggi di posta elettronica, il titolo per i documenti</span><span class="sxs-lookup"><span data-stu-id="c157e-122">subjecttitle: subject for emails, title for documents</span></span>
- <span data-ttu-id="c157e-123">bcc</span><span class="sxs-lookup"><span data-stu-id="c157e-123">bcc</span></span>
- <span data-ttu-id="c157e-124">cc</span><span class="sxs-lookup"><span data-stu-id="c157e-124">cc</span></span>
- <span data-ttu-id="c157e-125">i partecipanti: gli indirizzi di tutti i partecipanti in un thread di posta elettronica, inclusi i collegamenti mancanti della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c157e-125">participants: Email addresses of all participants in an email thread, including for missing links</span></span>
- <span data-ttu-id="c157e-126">ricevuti: data di ricezione</span><span class="sxs-lookup"><span data-stu-id="c157e-126">received: received date</span></span>
- <span data-ttu-id="c157e-127">destinatari: i nomi dei destinatari o gli indirizzi (a, cc, Ccn) di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c157e-127">recipients: email recipient names or addresses (to, cc, bcc)</span></span>
- <span data-ttu-id="c157e-128">mittente</span><span class="sxs-lookup"><span data-stu-id="c157e-128">sender</span></span>
- <span data-ttu-id="c157e-129">LastModifiedDate: data di un documento dell'ultima modifica</span><span class="sxs-lookup"><span data-stu-id="c157e-129">lastmodifieddate: last modified date of a document</span></span>
- <span data-ttu-id="c157e-130">inviati: data di un messaggio di posta elettronica inviati</span><span class="sxs-lookup"><span data-stu-id="c157e-130">sent: sent date of an email</span></span>
- <span data-ttu-id="c157e-131">a</span><span class="sxs-lookup"><span data-stu-id="c157e-131">to</span></span>
- <span data-ttu-id="c157e-132">Author: creazione di un messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c157e-132">author: author of an email</span></span>
- <span data-ttu-id="c157e-133">titolo: titolo di un documento</span><span class="sxs-lookup"><span data-stu-id="c157e-133">title: title of a document</span></span>
- <span data-ttu-id="c157e-134">dominanttheme: tema dominante di un elemento\*</span><span class="sxs-lookup"><span data-stu-id="c157e-134">dominanttheme: dominant theme of an item\*</span></span>
- <span data-ttu-id="c157e-135">themeslist: temi associati a un elemento\*</span><span class="sxs-lookup"><span data-stu-id="c157e-135">themeslist: themes that are associated with an item\*</span></span>
- <span data-ttu-id="c157e-136">readpercentile_ [issuenum]: leggere percentile di un elemento di problema [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="c157e-136">readpercentile_[issuenum]: read percentile of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="c157e-137">relevancescore_ [issuenum]: punteggio di pertinenza di un elemento di problema [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="c157e-137">relevancescore_[issuenum]: relevance score of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="c157e-138">relevancetag_ [issuenum]: se un elemento è stato contrassegnato manualmente la pertinenza, il tag per [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="c157e-138">relevancetag_[issuenum]: if an item has been manually tagged for relevance, its tag for [issuenum]\*\*</span></span>

<span data-ttu-id="c157e-139">\*Disponibile solo se è stato eseguito il modulo di temi \* \* è disponibile solo se è stato eseguito il modulo di pertinenza</span><span class="sxs-lookup"><span data-stu-id="c157e-139">\* Only available if the Themes module has been run \*\* Only available if the Relevance module has been run</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c157e-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c157e-140">See also</span></span>

[<span data-ttu-id="c157e-141">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c157e-141">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c157e-142">Informazioni sulla valutazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="c157e-142">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c157e-143">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="c157e-143">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c157e-144">Tagging e formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="c157e-144">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c157e-145">Analisi di pertinenza di verifica</span><span class="sxs-lookup"><span data-stu-id="c157e-145">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c157e-146">Stabilire in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="c157e-146">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c157e-147">Test di analisi di pertinenza</span><span class="sxs-lookup"><span data-stu-id="c157e-147">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

