---
title: Eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Informazioni su come utilizzare il Centro sicurezza &amp; e conformità di Office 365 per accedere a Office 365 Advanced eDiscovery ed eseguire il modulo di processo per un caso.  '
ms.openlocfilehash: 95c73c034ed2ffa1c45f9aacd8463c497a842859
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261406"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="c8fb3-103">Eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c8fb3-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="c8fb3-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="c8fb3-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c8fb3-106">In questa sezione viene descritta la funzionalità del modulo di elaborazione di eDiscovery avanzato.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="c8fb3-107">Oltre ai dati dei file, i metadati, ad esempio il tipo di file, l'estensione, la posizione o il percorso, la data e l'ora di creazione, l'autore, il custode e l'oggetto possono essere caricati in Advanced eDiscovery e salvati per ogni caso.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="c8fb3-108">Alcuni metadati vengono calcolati da Advanced eDiscovery, ad esempio quando vengono caricati file nativi.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="c8fb3-109">Advanced eDiscovery fornisce i valori dei metadati di sistema, ad esempio raggruppamenti quasi duplicati o punteggi di riLevanza.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="c8fb3-110">Gli altri metadati, ad esempio le annotazioni di file, possono essere aggiunti dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="c8fb3-111">Processo in esecuzione</span><span class="sxs-lookup"><span data-stu-id="c8fb3-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="c8fb3-112">I numeri di batch vengono assegnati a un file durante il processo per consentire la tracciabilità dei file.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="c8fb3-113">Il numero di batch consente inoltre l'identificazione dei batch di processo per le opzioni di rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="c8fb3-114">Sono disponibili filtri aggiuntivi per il filtro in base al numero di batch e alle sessioni.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="c8fb3-115">Eseguire la procedura seguente per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="c8fb3-116">[Aprire il Centro sicurezza &amp; e conformità di Office 365](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="c8fb3-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="c8fb3-117">Andare a **Search &amp; Investigation** \> **eDiscovery** e quindi fare clic su **go to Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="c8fb3-118">In Advanced eDiscovery selezionare il caso appropriato nella pagina **casi** visualizzati e fare clic su **Vai a maiuscole**/minuscole.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="c8fb3-119">In **preparare** \> l' **installazione**del **processo** \> selezionare un contenitore dall'elenco dei contenitori disponibili.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![Fare clic su processo per aggiungere i risultati della ricerca al caso](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="c8fb3-121">Fare clic su **Impostazioni avanzate...** se si desidera aggiungere il contenitore come file di seeding o come file con tag preselezionati.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="c8fb3-122">Utilizzo dei file di seeding per accelerare la formazione di problemi con una ricchezza limitata (in genere 2% o meno).</span><span class="sxs-lookup"><span data-stu-id="c8fb3-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="c8fb3-123">Per i file di seeding, è consigliabile selezionare una serie di file rilevanti e elaborare circa 20-50 Seeds per ogni problema (troppi file di sementi possono alterare i risultati della pertinenza).</span><span class="sxs-lookup"><span data-stu-id="c8fb3-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="c8fb3-124">I file di seeding devono essere esaminati dalla stessa persona che dovrà addestrare il problema.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="c8fb3-125">Utilizzare i file con tag preselezionati per automatizzare la formazione sulla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="c8fb3-126">È necessario contrassegnare almeno 1.500 file e mantenere la proporzione dei file rilevanti per i non rilevanti come nell'insieme aggiunto a pertinenza.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="c8fb3-127">Questi file devono essere contrassegnati manualmente e devono essere sicuri della qualità del tagging.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![Schermata della pagina Impostazioni avanzate per l'elaborazione dei file batch](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="c8fb3-129">Nella sezione **Seed** :</span><span class="sxs-lookup"><span data-stu-id="c8fb3-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="c8fb3-130">Scegliere **Contrassegna come file** di seeding per contrassegnare il contenitore come file di seeding.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="c8fb3-131">È inoltre necessario scegliere di assegnarli per ogni problema dall'elenco a discesa **per i problemi** .</span><span class="sxs-lookup"><span data-stu-id="c8fb3-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="c8fb3-132">Scegliere **rilevanti** o **non rilevanti** dall'elenco a discesa dei **tag** .</span><span class="sxs-lookup"><span data-stu-id="c8fb3-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c8fb3-133">Dopo aver impostato i file come **Seed**, non è possibile contrassegnarli come preselezionati. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8fb3-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="c8fb3-134">Nella sezione **file con tag** preselezionati:</span><span class="sxs-lookup"><span data-stu-id="c8fb3-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="c8fb3-135">Scegliere **Contrassegna come file con tag** preselezionati per contrassegnare il contenitore come file con tag preselezionati.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="c8fb3-136">È inoltre necessario assegnarle per ogni problema dall'elenco **a discesa per i problemi** .</span><span class="sxs-lookup"><span data-stu-id="c8fb3-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="c8fb3-137">Scegliere **rilevanti** o **non rilevanti** dall'elenco a discesa dei **tag** .</span><span class="sxs-lookup"><span data-stu-id="c8fb3-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c8fb3-138">Dopo aver impostato i file \*\*\*\* come precontrassegnati, non è possibile contrassegnarli come **Seed**.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="c8fb3-139">Nella sezione **tagging messaggio di posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="c8fb3-139">In the **Email tagging** section.</span></span> <span data-ttu-id="c8fb3-140">impostare la parte di un messaggio di posta elettronica elaborata da contrassegnare come Seed o con tag preimpostati.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="c8fb3-141">Per iniziare, fare clic su **elabora**.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-141">To begin, click **Process**.</span></span> <span data-ttu-id="c8fb3-142">Al termine, vengono visualizzati i risultati del processo.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="c8fb3-143">Optional Se è necessario assegnare origini dati a un determinato custode, è possibile aggiungere e modificare i nomi dei depositari nei **depositari** \> che **gestiscono** e assegnano i depositari nei **depositari** \> \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="c8fb3-144">Se si aggiunge il caso, è possibile procedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="c8fb3-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8fb3-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8fb3-145">See also</span></span>

[<span data-ttu-id="c8fb3-146">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c8fb3-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c8fb3-147">Visualizzazione dei risultati del modulo di elaborazione</span><span class="sxs-lookup"><span data-stu-id="c8fb3-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

