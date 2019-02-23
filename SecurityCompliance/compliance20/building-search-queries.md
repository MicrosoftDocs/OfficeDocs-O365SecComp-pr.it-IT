---
title: Creare query di ricerca
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8e7f3d798d3b6cfe25d57b941ed2be1d8d5e92b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216986"
---
# <a name="build-search-queries"></a><span data-ttu-id="ea82f-102">Creare query di ricerca</span><span class="sxs-lookup"><span data-stu-id="ea82f-102">Build search queries</span></span>

<span data-ttu-id="ea82f-103">Per creare la query, è possibile utilizzare diverse parole chiave e condizioni per definire gli elementi da trovare.</span><span class="sxs-lookup"><span data-stu-id="ea82f-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="ea82f-104">Ricerche di parole chiave</span><span class="sxs-lookup"><span data-stu-id="ea82f-104">Keyword searches</span></span>

<span data-ttu-id="ea82f-p101">Digitare una query di ricerca nella casella **parole chiave** . È possibile specificare le parole chiave, le proprietà del messaggio, ad esempio le date inviate e ricevute, o le proprietà del documento, ad esempio i nomi di file o la data dell'Ultima modifica di un documento. È possibile utilizzare una query più complessa che utilizza un operatore booleano, ad esempio **e**, **o**, **non**e **vicino**. È inoltre possibile cercare informazioni riservate (ad esempio i numeri di previdenza sociale) nei documenti oppure cercare documenti che sono stati condivisi esternamente. Se si lascia vuota la casella parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificato verrà incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ea82f-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="ea82f-p102">In alternativa, è possibile fare clic sulla casella di controllo **Mostra elenco parole chiave** e digitare una parola chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono connesse da un operatore logico ( **c:s**) simile alla funzionalità all'operatore **or** nella query di ricerca creata.</span><span class="sxs-lookup"><span data-stu-id="ea82f-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="ea82f-p103">Perché usare l'elenco delle parole chiave? È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave. In questo modo è possibile identificare rapidamente quali parole chiave sono le più (e meno) effettive. È inoltre possibile utilizzare una frase di parole chiave (racchiusa tra parentesi) in una riga. Per ulteriori informazioni sulle statistiche di ricerca, vedere [statistica](search-statistics.md)della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ea82f-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="ea82f-117">Condizioni</span><span class="sxs-lookup"><span data-stu-id="ea82f-117">Conditions</span></span>
    
<span data-ttu-id="ea82f-p104">È possibile aggiungere condizioni di ricerca per restringere una ricerca e restituire un insieme di risultati più raffinato. Ogni condizione aggiunge una clausola alla query di ricerca che viene creata e eseguita all'avvio della ricerca. Una condizione è connessa logicamente alla query con parole chiave, specificata nella casella parola chiave, da un operatore logico (**c:c**) simile alla funzionalità all'operatore **and** . Questo significa che gli elementi devono soddisfare sia la query di parole chiave che una o più condizioni da includere nei risultati. Questo è il modo in cui le condizioni aiutano a limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "condizioni di ricerca" in [query di parole chiave e condizioni di ricerca per la ricerca di contenuto](../keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="ea82f-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


