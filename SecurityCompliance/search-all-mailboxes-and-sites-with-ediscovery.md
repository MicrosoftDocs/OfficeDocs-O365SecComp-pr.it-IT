---
title: Ricerca di tutte le cassette postali e dei siti utilizzando il Centro eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 56e2978f-71b6-4141-b769-ad856d31bbec
description: In Centro eDiscovery di Office 365, è possibile cercare tutte le cassette postali di Exchange Online, siti di SharePoint Online e OneDrive per i siti di Business in una ricerca eDiscovery singolo. Per trovare tutte le origini di contenuto nell'organizzazione, è necessario assegnare a un manager di eDiscovery autorizzazioni eDiscovery appropriato per ogni origine di contenuto.
ms.openlocfilehash: b3508d5929ca2b5b7a937eb2dccf677a2968cbbc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530641"
---
# <a name="search-all-mailboxes-and-sites-using-the-ediscovery-center"></a><span data-ttu-id="616a6-104">Ricerca di tutte le cassette postali e dei siti utilizzando il Centro eDiscovery</span><span class="sxs-lookup"><span data-stu-id="616a6-104">Search all mailboxes and sites using the eDiscovery Center</span></span>

<span data-ttu-id="616a6-p102">In Centro eDiscovery di Office 365, è possibile cercare tutte le cassette postali di Exchange Online, siti di SharePoint Online e OneDrive per i siti di Business in una ricerca eDiscovery singolo. Per trovare tutte le origini di contenuto nell'organizzazione, è necessario assegnare a un manager di eDiscovery autorizzazioni eDiscovery appropriato per ogni origine di contenuto.</span><span class="sxs-lookup"><span data-stu-id="616a6-p102">In the eDiscovery Center in Office 365, you can search all Exchange Online mailboxes, SharePoint Online sites, and OneDrive for Business sites in a single eDiscovery search. To search all content sources in the organization, an eDiscovery manager must be assigned the appropriate eDiscovery permissions for each content source.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="616a6-107">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="616a6-107">Before you begin</span></span>

- <span data-ttu-id="616a6-p103">È necessario assegnare le autorizzazioni opportune a un responsabile eDiscovery affinché quest'ultimo sia in grado di ricercare un'origine contenuto. Per ulteriori informazioni sull'assegnazione di autorizzazioni eDiscovery per i siti e le cassette postali, vedere i seguenti articoli:</span><span class="sxs-lookup"><span data-stu-id="616a6-p103">An eDiscovery manager must be assigned the appropriate permissions to search a content source. For more information about assigning eDiscovery permissions to mailboxes and sites, see the following:</span></span> 
    
  - [<span data-ttu-id="616a6-110">Assegnare le autorizzazioni di eDiscovery di Exchange</span><span class="sxs-lookup"><span data-stu-id="616a6-110">Assign eDiscovery permissions in Exchange</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526886)
    
  - [<span data-ttu-id="616a6-111">Assegnare le autorizzazioni di eDiscovery in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="616a6-111">Assign eDiscovery permissions in SharePoint Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526885)
    
  - [<span data-ttu-id="616a6-112">Assegnare le autorizzazioni eDiscovery ai siti OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="616a6-112">Assign eDiscovery permissions to OneDrive for Business sites</span></span>](assign-permissions-to-onedrive-for-business-sites.md)
    
- <span data-ttu-id="616a6-p104">È possibile cercare un massimo di 10.000 cassette postali e un numero illimitato di SharePoint Online e OneDrive per i siti in una query di ricerca di eDiscovery singolo. Tuttavia, se si specificano i siti specifici per la ricerca, il limite è 100 siti.</span><span class="sxs-lookup"><span data-stu-id="616a6-p104">You can search a maximum of 10,000 mailboxes and an unlimited number of SharePoint Online and OneDrive for Business sites in a single eDiscovery search query. However, if you specify the specific sites to search, the limit is 100 sites.</span></span>
    
- <span data-ttu-id="616a6-115">Quando si visualizzano i risultati durante la ricerca di tutti i siti e le cassette postali, vedere la sezione [informazioni](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo) per una descrizione dei limiti.</span><span class="sxs-lookup"><span data-stu-id="616a6-115">See the [More information](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo) section for a description of the limits when viewing the results when searching all mailboxes and sites.</span></span> 
    
- <span data-ttu-id="616a6-116">Per ulteriori informazioni sulla creazione delle query di ricerca di eDiscovery Center, vedere [Create and query eseguire eDiscovery](https://go.microsoft.com/fwlink/p/?LinkID=404032).</span><span class="sxs-lookup"><span data-stu-id="616a6-116">For more information about creating search queries in the eDiscovery Center, see [Create and run eDiscovery queries](https://go.microsoft.com/fwlink/p/?LinkID=404032).</span></span>
    
## <a name="search-all-locations"></a><span data-ttu-id="616a6-117">Ricerca di tutti i percorsi</span><span class="sxs-lookup"><span data-stu-id="616a6-117">Search all locations</span></span>

1. <span data-ttu-id="616a6-118">Nel Centro eDiscovery, aprire il caso di eDiscovery per il quale si desidera eseguire la query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="616a6-118">In the eDiscovery Center, open the eDiscovery case that you want to run the search query for.</span></span>
    
2. <span data-ttu-id="616a6-119">In **ricerca e l'esportazione**, fare clic su una query esistente o fare clic su **nuovo elemento** per creare una nuova query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="616a6-119">Under **Search and Export**, click an existing query or click **New item** to create a new search query.</span></span> 
    
3. <span data-ttu-id="616a6-120">Nella pagina della query di ricerca, nella sezione **Origini** fare clic su **Modifica ambito della query**.</span><span class="sxs-lookup"><span data-stu-id="616a6-120">On the search query page, in the **Sources** section, click **Modify Query Scope**.</span></span>
    
4. <span data-ttu-id="616a6-121">Nella pagina **Modifica ambito della query**, fare clic su **Cerca ovunque** e selezionare i percorsi dei contenuti da ricercare.</span><span class="sxs-lookup"><span data-stu-id="616a6-121">On the **Modify Query Scope** page, click **Search everything**, and select the content locations to search.</span></span>
    
  - <span data-ttu-id="616a6-122">Selezionare **Exchange** per la ricerca di tutte le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="616a6-122">Select **Exchange** to search all mailboxes.</span></span> 
    
  - <span data-ttu-id="616a6-123">Selezionare **SharePoint** per cercare tutti SharePoint Online e OneDrive per i siti.</span><span class="sxs-lookup"><span data-stu-id="616a6-123">Select **SharePoint** to search all SharePoint Online and OneDrive for Business sites.</span></span> 
    
  - <span data-ttu-id="616a6-124">Selezionare **Exchange** e **SharePoint** per cercare tutti i percorsi di contenuti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="616a6-124">Select both **Exchange** and **SharePoint** to search all content locations in your organization.</span></span> 
    
![Ricerca in tutte le cassette postali e i siti](media/e1f919ab-5596-43bb-a3c9-626cd41067b3.gif)
  
5. <span data-ttu-id="616a6-126">Fare clic su **OK** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="616a6-126">Click **OK** to save the changes.</span></span> 
    
6. <span data-ttu-id="616a6-p105">Completare o rivedere altre informazioni nella pagina della query di ricerca, come la query della parola chiave, l'intervallo di date o la definizione di tipi specifici dei contenuti da ricercare. Una volta pronti, eseguire la query facendo clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="616a6-p105">Complete or revise other information on the search query page, such as the keyword query, the date range, or narrowing the specific types of content to search for. When you're ready to run the query, click **Search**.</span></span> 
    
## <a name="more-information"></a><span data-ttu-id="616a6-129">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="616a6-129">More information</span></span>
<span data-ttu-id="616a6-130"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="616a6-130"></span></span>

- <span data-ttu-id="616a6-131">I 500 siti e le 500 cassette postali principali con il maggior numero di risultati vengono elencati in **Origini** nella pagina **Query**.</span><span class="sxs-lookup"><span data-stu-id="616a6-131">The top 500 mailboxes and the top 500 sites with the most results are listed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="616a6-132">Il numero complessivo di elementi rilevati in tutte le origini di contenuti e la relativa dimensione totale vengono visualizzati in **Origini** nella pagina **Query**. 
</span><span class="sxs-lookup"><span data-stu-id="616a6-132">The total number of items found in all content sources and their combined total size are displayed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="616a6-133">È possibile visualizzare in anteprima i 200 risultati di ricerca più recenti delle cassette postali di Exchange o dei siti SharePoint nella pagina **Query**.</span><span class="sxs-lookup"><span data-stu-id="616a6-133">You can preview the 200 most recent search results located in Exchange mailboxes or SharePoint sites on the **Query** page.</span></span> 
    
    <span data-ttu-id="616a6-134">Nella seguente schermata è illustrato un esempio relativo ai risultati di ricerca visualizzati nella pagina **Query**, quando si eseguono ricerche in tutti i siti e in tutte le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="616a6-134">The following screenshot shows an example of the search results displayed on the **Query** page when you search all mailboxes and sites.</span></span> 
    
    ![Schermata dei risultati relativi alla ricerca di tutte le posizioni](media/4bf430f6-41ab-4bf6-afa9-33c3f6fd8b16.gif)
  

