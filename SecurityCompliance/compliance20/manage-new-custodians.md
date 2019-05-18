---
title: Gestire i depositari in un caso avanzato di eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9806ecbc23f46ee2d39f8d7e6be07af0d6a83e8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151618"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="b8e32-102">Gestire i depositari in un caso avanzato di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b8e32-102">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="b8e32-103">La scheda depositari in Advanced eDiscovery contiene un elenco di tutti i depositari che sono stati aggiunti al caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-103">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="b8e32-104">Dopo aver aggiunto i depositari a un caso, i dettagli relativi a ogni custode vengono raccolti automaticamente da Azure Active Directory e sono visualizzabili in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b8e32-104">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Gestire i depositari](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="b8e32-106">Visualizzare i dettagli del custode</span><span class="sxs-lookup"><span data-stu-id="b8e32-106">View custodian details</span></span>

<span data-ttu-id="b8e32-107">Per visualizzare i dettagli relativi a un custode, fare clic sul custode dall'elenco nella scheda **depositari** . Viene visualizzata una pagina a comparsa che contiene le seguenti informazioni sul custode:</span><span class="sxs-lookup"><span data-stu-id="b8e32-107">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="b8e32-108">Informazioni di contatto</span><span class="sxs-lookup"><span data-stu-id="b8e32-108">Contact information</span></span>

  - <span data-ttu-id="b8e32-109">**Nome** visualizzato-nome visualizzato nella rubrica del custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-109">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="b8e32-110">Questo è in genere la combinazione del nome, dell'iniziale e del cognome del custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-110">This is usually the combination of the custodian’s first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="b8e32-111">**Mail/SMTP** : l'indirizzo SMTP primario per il custode, ad esempio brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b8e32-111">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="b8e32-112">Si noti che anche il nome dell'entità utente (UPN) del custode è elencato.</span><span class="sxs-lookup"><span data-stu-id="b8e32-112">Note that the custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="b8e32-113">**Title** -titolo del processo del custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-113">**Title** - The custodian’s job title.</span></span>

  - <span data-ttu-id="b8e32-114">**Department** -nome del reparto in cui lavora il custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-114">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="b8e32-115">**Manager** -responsabile del custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-115">**Manager** - The custodian’s manager.</span></span> <span data-ttu-id="b8e32-116">Il responsabile designato riceverà eventuali comunicazioni di escalation per questo custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-116">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="b8e32-117">Informazioni sulle posizioni</span><span class="sxs-lookup"><span data-stu-id="b8e32-117">Location information</span></span>

  - <span data-ttu-id="b8e32-118">**City** : la città in cui si trova il custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-118">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="b8e32-119">**Stato** : lo stato o la provincia nell'indirizzo del custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-119">**State** - The state or province in the custodian’s address.</span></span>

  - <span data-ttu-id="b8e32-120">**Paese/area** geografica-paese/area geografica in cui si trova il custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-120">**Country/Region** - The country/region where the custodian’s is located.</span></span>

  - <span data-ttu-id="b8e32-121">**Office** : la sede dell'ufficio nel luogo di lavoro del custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-121">**Office** - The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="b8e32-122">Informazioni sul caso</span><span class="sxs-lookup"><span data-stu-id="b8e32-122">Case information</span></span>

  - <span data-ttu-id="b8e32-123">**Stato blocco** -indica se il custode è stato messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="b8e32-123">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="b8e32-124">**Stato della comunicazione**: indica se il custode ha emesso un avviso di esenzione.</span><span class="sxs-lookup"><span data-stu-id="b8e32-124">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="b8e32-125">Se al custode è stato emesso un avviso, viene **pubblicato**questo valore di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8e32-125">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="b8e32-126">Se al custode non è stato emesso alcun avviso, lo stato non viene **pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="b8e32-126">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="b8e32-127">**Status** : lo stato del custode all'interno del caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-127">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="b8e32-128">Lo stato **attivo** indica che il custode è parte del caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-128">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="b8e32-129">Se un custode viene rilasciato da un caso, lo stato viene modificato in **rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="b8e32-129">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="b8e32-130">Origini dati e informazioni sull'indicizzazione</span><span class="sxs-lookup"><span data-stu-id="b8e32-130">Data sources and indexing information</span></span>

    - <span data-ttu-id="b8e32-131">**Origini dati** : consente di visualizzare il numero e il tipo di origini dati (cassette postali, siti e Team) associati al custode e fanno parte del caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-131">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="b8e32-132">**Tempo di aggiornamento dell'indice** : indica la data e l'ora in cui è stato attivato l'ultimo processo di indicizzazione avanzato.</span><span class="sxs-lookup"><span data-stu-id="b8e32-132">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="b8e32-133">Questa proprietà indicherà anche quando il processo di indicizzazione avanzato è attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-133">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="b8e32-134">Modificare un custode</span><span class="sxs-lookup"><span data-stu-id="b8e32-134">Edit a custodian</span></span>

<span data-ttu-id="b8e32-135">Man mano che il caso progredisce, è possibile rilevare che potrebbero essere presenti ulteriori origini dati rilevanti per un determinato custode & il caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-135">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="b8e32-136">In altri scenari potrebbe essere necessario rimuovere determinate origini dati che sono state esaminate e ritenute irrilevanti.</span><span class="sxs-lookup"><span data-stu-id="b8e32-136">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="b8e32-137">Per aggiornare le origini dati associate a un custode:</span><span class="sxs-lookup"><span data-stu-id="b8e32-137">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="b8e32-138">Passare a **eDiscovery _GT_ Advanced eDiscovery** e aprire il caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-138">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="b8e32-139">Fare clic sulla scheda **depositari** .</span><span class="sxs-lookup"><span data-stu-id="b8e32-139">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="b8e32-140">Selezionare un custode dall'elenco e fare clic su **modifica** nella pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="b8e32-140">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Modificare origini dati](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="b8e32-142">Fare clic su scegliere la scheda **origini dati** per modificare le impostazioni per la cassetta postale di Exchange e l'account OneDrive della banca depositaria, fare clic su **Scegli origini dati**.</span><span class="sxs-lookup"><span data-stu-id="b8e32-142">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="b8e32-143">Fare clic sulla scheda **Seleziona origini dati aggiuntive** per aggiungere o rimuovere team, SharePoint o cassette postali di Exchange associati al custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-143">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="b8e32-144">Per ulteriori informazioni sulle origini dati associate a un custode, vedere "passaggio 3: associare altre origini dati a un custode" in [Aggiungi depositari a un caso](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span><span class="sxs-lookup"><span data-stu-id="b8e32-144">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="b8e32-145">Fare clic su **Place detentive** holds per abilitare o disabilitare il blocco per il custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-145">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="resolve-custodian-processing-errors"></a><span data-ttu-id="b8e32-146">Risolvere gli errori di elaborazione del custode</span><span class="sxs-lookup"><span data-stu-id="b8e32-146">Resolve custodian processing errors</span></span>

<span data-ttu-id="b8e32-147">Nella maggior parte dei flussi di lavoro di eDiscovery per le indagini giudiziarie, viene cercato un sottoinsieme di dati di un custode dopo che il custode è stato aggiunto a un caso legale.</span><span class="sxs-lookup"><span data-stu-id="b8e32-147">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="b8e32-148">A causa dei file di dimensioni molto grandi o di un possibile danneggiamento dei dati, alcuni elementi nelle origini dati associate a un custode possono essere parzialmente indicizzati.</span><span class="sxs-lookup"><span data-stu-id="b8e32-148">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="b8e32-149">Utilizzando la funzionalità di indicizzazione [avanzata](indexing-custodian-data.md) in Advanced eDiscovery, è possibile correggere automaticamente gli elementi indicizzati in modo automatico riindicizzando questi elementi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="b8e32-149">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="b8e32-150">Quando un custode viene aggiunto a un caso, i dati che si trovano nelle origini dati associate al custode vengono reindicizzati automaticamente (tramite il processo di indicizzazione avanzato).</span><span class="sxs-lookup"><span data-stu-id="b8e32-150">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="b8e32-151">Questo significa che è possibile lasciare i dati sul posto invece di scaricarli e rimediarli e quindi cercarli in modalità non in linea.</span><span class="sxs-lookup"><span data-stu-id="b8e32-151">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="b8e32-152">Tuttavia, durante il ciclo di vita di un caso legale, è possibile associare nuove origini dati a un custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-152">However, during the lifecycle of a legal case new data sources might be associated to a custodian.</span></span> <span data-ttu-id="b8e32-153">In questo caso, è necessario reindicizzare i dati del custode rieseguendo il processo di indicizzazione avanzato per correggere gli elementi parzialmente indicizzati e aggiornare l'indice per i dati del custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-153">In this case, you re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="b8e32-154">Per attivare il processo di reindicizzazione per risolvere gli elementi parzialmente indicizzati:</span><span class="sxs-lookup"><span data-stu-id="b8e32-154">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="b8e32-155">Passare a **eDiscovery _GT_ Advanced eDiscovery** e aprire il caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-155">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="b8e32-156">Fare clic **sulla scheda depositari**e quindi selezionare un custode i cui dati devono essere reindicizzati.</span><span class="sxs-lookup"><span data-stu-id="b8e32-156">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="b8e32-157">Nella pagina riquadro a comparsa fare clic su **Aggiorna indice**.</span><span class="sxs-lookup"><span data-stu-id="b8e32-157">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="b8e32-158">Viene visualizzata una finestra di dialogo che indica che è stato creato il processo di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8e32-158">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="b8e32-159">La reindicizzazione dei dati del custode è un processo a esecuzione prolungata. il processo corrispondente creato è denominato reindicizzazione **dei dati del custode**.</span><span class="sxs-lookup"><span data-stu-id="b8e32-159">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="b8e32-160">È possibile monitorare lo stato di avanzamento nella scheda **processi** o nella scheda **depositari** monitorando lo stato nella colonna **stato processo** di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8e32-160">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="b8e32-161">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="b8e32-161">For more information, see:</span></span>

- [<span data-ttu-id="b8e32-162">Gestire gli errori di elaborazione</span><span class="sxs-lookup"><span data-stu-id="b8e32-162">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="b8e32-163">Gestire processi</span><span class="sxs-lookup"><span data-stu-id="b8e32-163">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="b8e32-164">Rilasciare un custode da un caso</span><span class="sxs-lookup"><span data-stu-id="b8e32-164">Release a custodian from a case</span></span>

<span data-ttu-id="b8e32-165">Un custode viene rilasciato in situazioni in cui un caso è chiuso, il custode non è più in dovere di preservare il contenuto di un caso o quando il custode è ritenuto non più pertinente al caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-165">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="b8e32-166">Se si rilascia un custode dopo la pubblicazione di un avviso di esenzione, verrà inviato un avviso di rilascio al custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-166">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="b8e32-167">Inoltre, tutte le esenzioni inserite nelle origini dati associate al custode vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="b8e32-167">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="b8e32-168">Se il custode è stato collocato in una conservazione *invisibile all'utente*, in cui non sono state rilasciate notifiche per la conservazione legale, non verrà inviato un avviso di rilascio, ma verranno rimosse tutte le esenzioni eseguite su origini dati associate a tale custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-168">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="b8e32-169">Per rilasciare un custode:</span><span class="sxs-lookup"><span data-stu-id="b8e32-169">To release a custodian:</span></span> 

1. <span data-ttu-id="b8e32-170">Passare a **eDiscovery _GT_ Advanced eDiscovery** e aprire il caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-170">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.  <span data-ttu-id="b8e32-171">Passare alla scheda **depositari** .</span><span class="sxs-lookup"><span data-stu-id="b8e32-171">Go to the **Custodians** tab.</span></span>

3.  <span data-ttu-id="b8e32-172">Fare clic sulla **scheda depositari**e quindi selezionare il custode che viene rilasciato dal caso.</span><span class="sxs-lookup"><span data-stu-id="b8e32-172">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="b8e32-173">Nella pagina riquadro a comparsa fare clic su **rilascia custode**.</span><span class="sxs-lookup"><span data-stu-id="b8e32-173">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="b8e32-174">Viene visualizzata una pagina di avviso in cui viene spiegato che se un blocco è posizionato su un'origine dati associata al custode, il blocco verrà rimosso e qualsiasi altro blocco associato a un caso di eDiscovery avanzato verrà applicato.</span><span class="sxs-lookup"><span data-stu-id="b8e32-174">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="b8e32-175">Che include altri tipi di funzionalità di conservazione e conservazione in Office 365, ad esempio i criteri di conservazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8e32-175">That includes other types of preservation and retention features in Office 365 (such as an Office 365 retention policy).</span></span>

5. <span data-ttu-id="b8e32-176">Fare clic su **Sì** per confermare che si desidera rilasciare il custode.</span><span class="sxs-lookup"><span data-stu-id="b8e32-176">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="b8e32-177">Si noti che lo stato di questo utente nella scheda **depositari** è impostato su **rilasciato** e lo **stato di blocco** sulla pagina a comparsa viene modificato in **false**.</span><span class="sxs-lookup"><span data-stu-id="b8e32-177">Note that status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="b8e32-178">Un custode potrebbe essere coinvolto contemporaneamente in numerosi casi legali.</span><span class="sxs-lookup"><span data-stu-id="b8e32-178">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="b8e32-179">Quando un custode viene rilasciato da un caso, le esenzioni e le notifiche su altre questioni non verranno influenzate.</span><span class="sxs-lookup"><span data-stu-id="b8e32-179">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="b8e32-180">Modifica in blocco di custodi</span><span class="sxs-lookup"><span data-stu-id="b8e32-180">Bulk-edit custodians</span></span>

<span data-ttu-id="b8e32-181">È possibile utilizzare l'editor di massa per modificare più depositari contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b8e32-181">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="b8e32-182">A tale scopo, è sufficiente selezionare due o più depositari nella scheda **depositari** per visualizzare l'editor di massa e quindi fare clic su una delle attività.</span><span class="sxs-lookup"><span data-stu-id="b8e32-182">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Pagina a comparsa per modificare le impostazioni di più depositari](../media/AeDBulkEditCustodians.png)