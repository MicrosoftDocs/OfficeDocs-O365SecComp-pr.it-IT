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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e62d486b102fa035ae21b379d30bb0657b82acc9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242504"
---
# <a name="build-search-queries"></a><span data-ttu-id="d3068-102">Creare query di ricerca</span><span class="sxs-lookup"><span data-stu-id="d3068-102">Build search queries</span></span>

<span data-ttu-id="d3068-103">Per creare la query, è possibile utilizzare diverse parole chiave e condizioni per definire gli elementi da trovare.</span><span class="sxs-lookup"><span data-stu-id="d3068-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="d3068-104">Ricerche di parole chiave</span><span class="sxs-lookup"><span data-stu-id="d3068-104">Keyword searches</span></span>

<span data-ttu-id="d3068-105">Digitare una query di ricerca nella casella **parole chiave** .</span><span class="sxs-lookup"><span data-stu-id="d3068-105">Type a search query in **Keywords** box.</span></span> <span data-ttu-id="d3068-106">È possibile specificare parole chiave, proprietà del messaggio, come ad esempio, le date di invio e ricezione o le proprietà del documento, quali ad esempio, i nomi dei file o la data dell'ultima modifica apportata a un documento.</span><span class="sxs-lookup"><span data-stu-id="d3068-106">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="d3068-107">È possibile utilizzare una query più complessa che utilizza un operatore booleano, ad esempio **e**, **o**, **non**e **vicino**.</span><span class="sxs-lookup"><span data-stu-id="d3068-107">You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="d3068-108">È inoltre possibile cercare informazioni riservate (ad esempio i numeri di previdenza sociale) nei documenti oppure cercare documenti che sono stati condivisi esternamente.</span><span class="sxs-lookup"><span data-stu-id="d3068-108">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="d3068-109">Se si lascia vuota la casella parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificato verrà incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="d3068-109">If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="d3068-110">In alternativa, è possibile fare clic sulla casella di controllo **Mostra elenco parole chiave** e digitare una parola chiave in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="d3068-110">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="d3068-111">Se si esegue questa operazione, le parole chiave in ogni riga sono connesse da un operatore logico ( **c:s**) simile alla funzionalità all'operatore **or** nella query di ricerca creata.</span><span class="sxs-lookup"><span data-stu-id="d3068-111">If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="d3068-112">Perché usare l'elenco delle parole chiave?</span><span class="sxs-lookup"><span data-stu-id="d3068-112">Why use the keyword list?</span></span> <span data-ttu-id="d3068-113">È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave.</span><span class="sxs-lookup"><span data-stu-id="d3068-113">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="d3068-114">In questo modo è possibile identificare rapidamente quali parole chiave sono le più (e meno) effettive.</span><span class="sxs-lookup"><span data-stu-id="d3068-114">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="d3068-115">È inoltre possibile utilizzare una frase di parole chiave (racchiusa tra parentesi) in una riga.</span><span class="sxs-lookup"><span data-stu-id="d3068-115">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="d3068-116">Per ulteriori informazioni sulle statistiche di ricerca, vedere [statistica](search-statistics.md)della ricerca.</span><span class="sxs-lookup"><span data-stu-id="d3068-116">For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="d3068-117">Condizioni</span><span class="sxs-lookup"><span data-stu-id="d3068-117">Conditions</span></span>
    
<span data-ttu-id="d3068-118">È possibile aggiungere condizioni di ricerca per restringere una ricerca e restituire un insieme di risultati più raffinato.</span><span class="sxs-lookup"><span data-stu-id="d3068-118">You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="d3068-119">Ogni condizione aggiunge una clausola alla query di ricerca che viene creata e eseguita all'avvio della ricerca.</span><span class="sxs-lookup"><span data-stu-id="d3068-119">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="d3068-120">Una condizione è connessa logicamente alla query con parole chiave, specificata nella casella parola chiave, da un operatore logico (**c:c**) simile alla funzionalità all'operatore **and** .</span><span class="sxs-lookup"><span data-stu-id="d3068-120">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="d3068-121">Questo significa che gli elementi devono soddisfare sia la query di parole chiave che una o più condizioni da includere nei risultati.</span><span class="sxs-lookup"><span data-stu-id="d3068-121">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="d3068-122">Ecco come le condizioni consentono di circoscrivere i risultati.</span><span class="sxs-lookup"><span data-stu-id="d3068-122">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="d3068-123">Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "condizioni di ricerca" in [query di parole chiave e condizioni di ricerca per la ricerca di contenuto](../keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="d3068-123">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


