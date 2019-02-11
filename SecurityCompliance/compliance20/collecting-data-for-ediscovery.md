---
title: Raccogliere i dati per un caso di eDiscovery avanzate (Preview)
ms.author: esclee
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
ms.openlocfilehash: 11e2c336512c91d65bd046c3022d5375ebecde4a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695052"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="e2e8c-102">Raccogliere i dati per un caso di eDiscovery avanzate (Preview)</span><span class="sxs-lookup"><span data-stu-id="e2e8c-102">Collect data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="e2e8c-p101">Dopo aver identificato depositari e origini dati di interesse per i casi, è necessario identificare il set di documenti da approfondire. È possibile utilizzare lo strumento di ricerca di eDiscovery avanzate (Preview) per individuare tali da posizioni detentive e non detentive in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2e8c-p101">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into. You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="e2e8c-p102">Dopo aver eseguito la ricerca, sarà in grado di visualizzare le statistiche di elementi recuperati, ad esempio i percorsi in cui si è verificato il maggior parte degli elementi corrispondenti a query di ricerca. È inoltre possibile visualizzare un'anteprima di un sottoinsieme dei risultati. Quando è stato identificato il set di documenti che desidera esaminare ulteriormente, è possibile aggiungere i risultati della ricerca a un gruppo di lavoro per raccogliere ed elaborare.</span><span class="sxs-lookup"><span data-stu-id="e2e8c-p102">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query. You can also preview a subset of the results. When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="e2e8c-108">Creazione di una ricerca</span><span class="sxs-lookup"><span data-stu-id="e2e8c-108">Create a search</span></span>

<span data-ttu-id="e2e8c-p103">Fare clic su **nuova ricerca** nella scheda **ricerche** avvierà una procedura guidata che viene descritta la creazione di una ricerca. Per informazioni dettagliate su come creare una ricerca, vedere [creare una ricerca per raccogliere i dati](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="e2e8c-p103">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search. For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="e2e8c-p104">Dopo la creazione di una ricerca, viene visualizzata una pagina di comparsa con i dettagli. Si noti che i pulsanti di **Anteprima** e **statistiche** inizialmente grigio poiché la ricerca non è ancora completata. È possibile tenere traccia dello stato di avanzamento della ricerca nella scheda **ricerche** .</span><span class="sxs-lookup"><span data-stu-id="e2e8c-p104">After a search is created, a flyout page with details is displayed. Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet. You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="e2e8c-114">Visualizza risultati di ricerca e statistiche</span><span class="sxs-lookup"><span data-stu-id="e2e8c-114">View search results and statistics</span></span>
<span data-ttu-id="e2e8c-p105">Esistono due componenti di una ricerca di contenuto: anteprima e statistiche (stime). Come ognuno di questi componenti completati, sarà possibile visualizzare lo stato visualizzato nelle colonne corrispondenti nella scheda **ricerche** passare da **inoltrato** a **In stato** su **completata**.</span><span class="sxs-lookup"><span data-stu-id="e2e8c-p105">There are two components of a content search: Statistics (Estimates) and Preview. As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="e2e8c-p106">Una volta completata la stima di ricerca, fare clic su Cerca per visualizzare la pagina comparsa, che consente di visualizzare alcuni statistiche generali sui risultati della ricerca. A questo punto, il pulsante **statistiche** è attivo. È possibile fare clic per visualizzare le statistiche di ricerca, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e2e8c-p106">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search. At this point, the **Statistics** button will be active. You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="e2e8c-120">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e2e8c-120">Summary</span></span>
- <span data-ttu-id="e2e8c-121">Percorsi principali</span><span class="sxs-lookup"><span data-stu-id="e2e8c-121">Top locations</span></span>
- <span data-ttu-id="e2e8c-122">Query</span><span class="sxs-lookup"><span data-stu-id="e2e8c-122">Queries</span></span>
- <span data-ttu-id="e2e8c-123">Criteri di affinamento</span><span class="sxs-lookup"><span data-stu-id="e2e8c-123">Refiners</span></span>

<span data-ttu-id="e2e8c-124">Per ulteriori informazioni sulle statistiche di ricerca, vedere [le statistiche della ricerca](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="e2e8c-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="e2e8c-p107">Al termine dell'anteprima, il pulsante **Anteprima** è attivo. Fare clic per visualizzare l'anteprima di un sottoinsieme dei risultati del campione.</span><span class="sxs-lookup"><span data-stu-id="e2e8c-p107">Once preview is completed, the **Preview** button will be active. Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="e2e8c-127">Aggiungere i risultati della ricerca a un gruppo di lavoro</span><span class="sxs-lookup"><span data-stu-id="e2e8c-127">Adding search results to a working set</span></span>

<span data-ttu-id="e2e8c-p108">Quando si è pronti raccogliere ed elaborare i risultati della ricerca intero, è possibile eseguire questa operazione aggiunta a un gruppo di lavoro. Per ulteriori informazioni, vedere [Add dati a un gruppo di lavoro](add-data-to-working-set.md).</span><span class="sxs-lookup"><span data-stu-id="e2e8c-p108">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set. For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 