---
title: Creare query di ricerca
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 119cdd9d932b6c1be847c406988efa80b8534795
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607920"
---
# <a name="building-search-queries"></a><span data-ttu-id="610eb-102">Creare query di ricerca</span><span class="sxs-lookup"><span data-stu-id="610eb-102">Building search queries</span></span>
<span data-ttu-id="610eb-103">Nella creazione delle query, è possibile utilizzare diverse parole chiave e le condizioni per definire gli elementi da trovare.</span><span class="sxs-lookup"><span data-stu-id="610eb-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="610eb-104">Ricerche per parole chiave</span><span class="sxs-lookup"><span data-stu-id="610eb-104">Keyword searches</span></span>
<span data-ttu-id="610eb-p101">Nella casella **parole chiave** , digitare una query di ricerca. È possibile specificare le parole chiave, messaggio proprietà come inviati e ricevuti, date o proprietà del documento, ad esempio i nomi di file o la data dell'ultima modifica di un documento. È possibile utilizzare una query più complesse che utilizzano un operatore booleano, ad esempio **AND**, **OR**, **non**e **NEAR**. È inoltre possibile cercare informazioni sensibili (ad esempio numeri di previdenza sociale) nei documenti o ricerca per i documenti condivisi esternamente. Se si lascia vuota la casella parole chiave, tutto il contenuto disponibile nei percorsi di contenuto specificati sarà incluse nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="610eb-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="610eb-p102">In alternativa, è possibile selezionare la casella di controllo **Mostra elenco di parole chiave** e il tipo di una parola chiave in ogni riga. In questo caso, le parole chiave in ogni riga sono connessi tramite un operatore logico ( **c:s**) che è simile all'operatore **OR** nella query di ricerca che viene creata.</span><span class="sxs-lookup"><span data-stu-id="610eb-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="610eb-p103">Perché utilizzare l'elenco delle parole chiave? È possibile ottenere le statistiche che mostra il numero di elementi corrispondenti a ogni parola chiave. Ciò consente di identificare rapidamente i quali le parole chiave sono il massimo (e almeno) efficaci. È inoltre possibile utilizzare una frase parola chiave (racchiusa tra parentesi) in una riga. Per ulteriori informazioni sulle statistiche di ricerca, vedere [informazioni statistiche di ricerca](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="610eb-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="610eb-117">Condizioni</span><span class="sxs-lookup"><span data-stu-id="610eb-117">Conditions</span></span>    
<span data-ttu-id="610eb-p104">È possibile aggiungere le condizioni di ricerca per restringere la ricerca e restituire un set di risultati più dettagliato. Ogni condizione aggiunge una clausola di query di ricerca che viene creata ed eseguita quando si avvia la ricerca. Una condizione è connesso logicamente per le query con parole chiave (specificata nella casella parole chiave) da un operatore logico (**c:c**) funzionalità analogo all'operatore **AND** . Ciò significa che gli elementi presentano soddisfare le query con parole chiave sia una o più condizioni da includere nei risultati. Si tratta come condizioni consentono di limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "Criteri di ricerca" in [condizioni di ricerca per la ricerca del contenuto e query con parole chiave](../keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="610eb-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


