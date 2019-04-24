---
title: Raccogliere i dati per un caso in Advanced eDiscovery (Preview)
ms.author: esclee
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
ms.openlocfilehash: fb4b36841394576c44667f9677507c5655179e45
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242554"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="f609f-102">Raccogliere i dati per un caso in Advanced eDiscovery (Preview)</span><span class="sxs-lookup"><span data-stu-id="f609f-102">Collect data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="f609f-103">Dopo aver identificato i depositari e le origini dati di interesse per il caso, è necessario identificare il set di documenti in cui eseguire l'approfondimento.</span><span class="sxs-lookup"><span data-stu-id="f609f-103">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="f609f-104">È possibile utilizzare lo strumento di ricerca in Advanced eDiscovery (Preview) per identificarli da posizioni detentive e non detentive in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f609f-104">You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="f609f-105">Dopo aver eseguito una ricerca, sarà possibile visualizzare le statistiche sugli elementi recuperati, ad esempio le posizioni con la maggior parte degli elementi corrispondenti alla query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f609f-105">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="f609f-106">È inoltre possibile visualizzare in anteprima un sottoinsieme dei risultati.</span><span class="sxs-lookup"><span data-stu-id="f609f-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="f609f-107">Dopo aver identificato il set di documenti che si desidera esaminare ulteriormente, è possibile aggiungere i risultati di ricerca a un working set per la raccolta e l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f609f-107">When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="f609f-108">Create a search</span><span class="sxs-lookup"><span data-stu-id="f609f-108">Create a search</span></span>

<span data-ttu-id="f609f-109">Se si fa clic su **nuova ricerca** nella scheda **ricerche** , verrà avviata una procedura guidata che consentirà di creare una ricerca.</span><span class="sxs-lookup"><span data-stu-id="f609f-109">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="f609f-110">Per informazioni dettagliate su come creare una ricerca, vedere [creare una ricerca per raccogliere i dati](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="f609f-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="f609f-111">Dopo la creazione di una ricerca, viene visualizzata una pagina a comparsa con dettagli.</span><span class="sxs-lookup"><span data-stu-id="f609f-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="f609f-112">Si noti che i pulsanti **statistiche** e **Anteprima** inizialmente sono inattivati perché la ricerca non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="f609f-112">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet.</span></span> <span data-ttu-id="f609f-113">È possibile tenere conto dello stato di avanzamento della ricerca nella scheda **ricerche** .</span><span class="sxs-lookup"><span data-stu-id="f609f-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="f609f-114">Visualizzare i risultati della ricerca e le statistiche</span><span class="sxs-lookup"><span data-stu-id="f609f-114">View search results and statistics</span></span>
<span data-ttu-id="f609f-115">Sono disponibili due componenti di una ricerca di contenuto: statistiche (stime) e anteprima.</span><span class="sxs-lookup"><span data-stu-id="f609f-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="f609f-116">Quando ognuno di questi componenti è stato completato, verrà visualizzato lo stato mostrato nelle colonne corrispondenti nella scheda **ricerche** che variano da da **inviato** a **in corso** a **completato**.</span><span class="sxs-lookup"><span data-stu-id="f609f-116">As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="f609f-117">Una volta completata la stima della ricerca, fare clic sulla pagina di ricerca per visualizzare la pagina a comparsa, in cui vengono visualizzate le statistiche di alto livello sui risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="f609f-117">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="f609f-118">A questo punto, il pulsante **statistiche** sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="f609f-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="f609f-119">È possibile fare clic su di esso per visualizzare le statistiche di ricerca, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f609f-119">You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="f609f-120">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f609f-120">Summary</span></span>
- <span data-ttu-id="f609f-121">Posizioni principali</span><span class="sxs-lookup"><span data-stu-id="f609f-121">Top locations</span></span>
- <span data-ttu-id="f609f-122">Query</span><span class="sxs-lookup"><span data-stu-id="f609f-122">Queries</span></span>

<span data-ttu-id="f609f-123">Per ulteriori informazioni sulle statistiche di ricerca, vedere [Search Statistics](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="f609f-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="f609f-124">Dopo aver completato l'anteprima, il pulsante **Anteprima** sarà attivo.</span><span class="sxs-lookup"><span data-stu-id="f609f-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="f609f-125">Fare clic su di esso per visualizzare in anteprima un sottoinsieme di campionamento dei risultati.</span><span class="sxs-lookup"><span data-stu-id="f609f-125">Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="f609f-126">Aggiunta dei risultati di ricerca a un working set</span><span class="sxs-lookup"><span data-stu-id="f609f-126">Adding search results to a working set</span></span>

<span data-ttu-id="f609f-127">Quando si è pronti per la raccolta e l'elaborazione di tutti i risultati di una ricerca, è possibile farlo aggiungendoli a un working set.</span><span class="sxs-lookup"><span data-stu-id="f609f-127">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set.</span></span> <span data-ttu-id="f609f-128">Per ulteriori informazioni, vedere [Add Data to a working set](add-data-to-working-set.md).</span><span class="sxs-lookup"><span data-stu-id="f609f-128">For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 