---
title: Aggiungere i depositari a un caso avanzato di eDiscovery (anteprima)
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
ms.openlocfilehash: fe208f4a9f7927d8481d5c6ec8b901baafb98626
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243570"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="14760-102">Aggiungere i depositari a un caso avanzato di eDiscovery (anteprima)</span><span class="sxs-lookup"><span data-stu-id="14760-102">Add custodians to an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="14760-103">Utilizzando Advanced eDiscovery (Preview), è possibile sfruttare lo strumento di gestione del custode incorporato per coordinare i flussi di lavoro in merito alla gestione dei depositari e identificare le origini dati rilevanti e detentive all'interno di un caso.</span><span class="sxs-lookup"><span data-stu-id="14760-103">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case.</span></span> <span data-ttu-id="14760-104">Quando si aggiunge un custode, il sistema è in grado di identificare automaticamente e inserire le esenzioni nella cassetta postale di Exchange principale e nel sito di OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="14760-104">When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site.</span></span> <span data-ttu-id="14760-105">Quando si esegue l'individuazione, è possibile anche scoprire e mappare altre cassette postali o siti a cui è stato effettuato l'accesso di un custode nel passato o i team a cui è membro un custode.</span><span class="sxs-lookup"><span data-stu-id="14760-105">As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="14760-106">Utilizzare il flusso di lavoro seguente per aggiungere e gestire i depositari nei casi avanzati di eDiscovery (Preview) all'interno del Centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="14760-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

![Scheda Gestione depositaria](../media/CustodianMgtPage.png)


## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="14760-108">Passaggio 1: identificare i potenziali depositari</span><span class="sxs-lookup"><span data-stu-id="14760-108">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="14760-109">Il primo passaggio consiste nell'identificare i depositari idonei per la propria materia.</span><span class="sxs-lookup"><span data-stu-id="14760-109">The first step is to identify the appropriate custodians for your matter.</span></span> <span data-ttu-id="14760-110">Per aggiungere depositari a un caso, è necessario essere membri del gruppo di ruoli eDiscovery managers o eDiscovery Admins.</span><span class="sxs-lookup"><span data-stu-id="14760-110">To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

![Identificare i potenziali depositari](../media/AddCustodianStep1.png)

<span data-ttu-id="14760-112">Per aggiungere i depositari a un caso avanzato esistente di eDiscovery (anteprima):</span><span class="sxs-lookup"><span data-stu-id="14760-112">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="14760-113">Dalla pagina **Advanced eDiscovery (Preview)** , passare al caso.</span><span class="sxs-lookup"><span data-stu-id="14760-113">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="14760-114">Dopo aver selezionato un caso, passare alla scheda **depositari** e fare clic su **+ Aggiungi custode**.</span><span class="sxs-lookup"><span data-stu-id="14760-114">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="14760-115">Scegliere i depositari che si desidera aggiungere al caso.</span><span class="sxs-lookup"><span data-stu-id="14760-115">Choose the custodians that you want to add to the case.</span></span> <span data-ttu-id="14760-116">È possibile iniziare digitando la ricerca e selezionando gli utenti dall'Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14760-116">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="14760-117">Dopo aver completato l'elenco dei depositari, fare clic su **Avanti** per iniziare a identificare potenziali origini dati.</span><span class="sxs-lookup"><span data-stu-id="14760-117">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
  
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="14760-118">Optional Passaggio 2: selezionare origini dati di un custode</span><span class="sxs-lookup"><span data-stu-id="14760-118">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="14760-119">Dopo aver aggiunto i depositari a un caso, è possibile sfruttare Office 365 per identificare e preservare le origini dati del custode principale.</span><span class="sxs-lookup"><span data-stu-id="14760-119">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources.</span></span> <span data-ttu-id="14760-120">Il passaggio successivo in questo flusso di lavoro consiste nel selezionare le origini dati di proprietà dei depositari specificati nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14760-120">The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

![Selezionare origini dati di custodia](../media/AddCustodianStep2.png)

<span data-ttu-id="14760-122">Per identificare le origini dati del custode:</span><span class="sxs-lookup"><span data-stu-id="14760-122">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="14760-123">Per ogni custode, selezionare **Exchange** se si desidera che il sistema identifichi automaticamente e aggiunga la cassetta postale di Exchange principale del custode.</span><span class="sxs-lookup"><span data-stu-id="14760-123">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="14760-124">Per ogni custode, selezionare **OneDrive** se si desidera che il sistema identifichi automaticamente e aggiunga l'URL di OneDrive primario del custode.</span><span class="sxs-lookup"><span data-stu-id="14760-124">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="14760-125">Dopo aver apportato le selezioni, il sistema tenterà automaticamente di identificare le origini dati e di aggiungerle al caso.</span><span class="sxs-lookup"><span data-stu-id="14760-125">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="14760-126">Fare clic su **Avanti** per iniziare a mappare le origini dati aggiuntive al custode.</span><span class="sxs-lookup"><span data-stu-id="14760-126">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="14760-127">Optional Passaggio 3: mappare origini dati aggiuntive</span><span class="sxs-lookup"><span data-stu-id="14760-127">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="14760-128">A seconda del caso, è possibile aggiungere anche cassette postali che un determinato custode può aver utilizzato in passato, gruppi in cui un custode è attualmente membro o siti a cui un custode ha avuto accesso in passato.</span><span class="sxs-lookup"><span data-stu-id="14760-128">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past.</span></span> <span data-ttu-id="14760-129">Oltre alle origini dati del custode principale, è possibile aggiungere altre origini dati di Office 365 a un custode o sfruttare Office 365 per identificare anche le origini dati potenzialmente rilevanti.</span><span class="sxs-lookup"><span data-stu-id="14760-129">In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

![Mapping di origini dati aggiuntive](../media/AddCustodianStep3.PNG)

<span data-ttu-id="14760-131">Per eseguire il mapping di cassette postali, siti o team a un determinato custode:</span><span class="sxs-lookup"><span data-stu-id="14760-131">To map mailboxes, sites, or teams to a specific custodian:</span></span>
1. <span data-ttu-id="14760-132">Selezionare **Aggiungi** per assegnare percorsi di contenuto, come cassette postali, siti e team, a un determinato custode.</span><span class="sxs-lookup"><span data-stu-id="14760-132">Select **Add** to assign content locations, like mailboxes, sites, and Teams, to a specific custodian.</span></span> 

2. <span data-ttu-id="14760-133">Nel riquadro a comparsa, specificare quanto segue ![: mapping delle origini dati](../media/AddCustodianStep4.PNG)</span><span class="sxs-lookup"><span data-stu-id="14760-133">In the flyout, specify the following: ![Map Data Sources](../media/AddCustodianStep4.PNG)</span></span>
  -  <span data-ttu-id="14760-134">**Cassette postali di Exchange** -fare clic su **Scegli utenti, gruppi o team** e quindi fare di nuovo clic su **Scegli utenti, gruppi o team** .</span><span class="sxs-lookup"><span data-stu-id="14760-134">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="14760-135">Per specificare le cassette postali da assegnare al custode selezionato, utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="14760-135">To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="14760-136">È inoltre possibile assegnare la cassetta postale associata a un gruppo di Office 365 o a un team Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14760-136">You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="14760-137">Selezionare la casella di controllo utente, gruppo, team, fare clic su **Scegli**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="14760-137">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="14760-138">Quando si fa clic su Scegli utenti, gruppi o team per specificare le cassette postali, lo strumento di selezione delle cassette postali visualizzato è vuoto.</span><span class="sxs-lookup"><span data-stu-id="14760-138">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="14760-139">Si tratta di un'impostazione predefinita per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="14760-139">This is by design to enhance performance.</span></span> <span data-ttu-id="14760-140">Per aggiungere persone a questo elenco, digitare un nome, almeno 3 caratteri, nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="14760-140">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="14760-141">**Siti di SharePoint** -fare clic su **Choose sites** , quindi fare clic su choose **sites** again per specificare altri siti di SharePoint e OneDrive for business che si desidera assegnare al custode selezionato.</span><span class="sxs-lookup"><span data-stu-id="14760-141">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian.</span></span> <span data-ttu-id="14760-142">È inoltre possibile aggiungere l'URL per il sito di SharePoint per un gruppo di Office 365 o un team di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14760-142">You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="14760-143">Digitare l'URL per ogni sito che si desidera assegnare.</span><span class="sxs-lookup"><span data-stu-id="14760-143">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="14760-144">Fare clic su **Scegli**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="14760-144">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="14760-145">**Microsoft teams** -fare clic su **Scegli team** e quindi fare di nuovo clic su **Scegli squadre** per visualizzare un elenco di gruppi di team Microsoft che il custode è un membro di oggi.</span><span class="sxs-lookup"><span data-stu-id="14760-145">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today.</span></span> <span data-ttu-id="14760-146">Selezionare i team che si desidera aggiungere al custode.</span><span class="sxs-lookup"><span data-stu-id="14760-146">Select the Teams that you would like to add to your custodian.</span></span> <span data-ttu-id="14760-147">Una volta selezionata, il sistema identificherà automaticamente & selezionare il sito di SharePoint associato e la cassetta postale del gruppo associata a quel team Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14760-147">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="14760-148">Fare clic su **Scegli**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="14760-148">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="14760-149">Per aggiungere ulteriori Microsoft teams, sarà necessario aggiungere separatamente la cassetta postale e il sito di SharePoint come illustrato in alto.</span><span class="sxs-lookup"><span data-stu-id="14760-149">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="14760-150">Dopo aver completato la mappatura delle origini, è possibile visualizzare le cassette postali, i siti e i team totali per i depositari appena aggiunti.</span><span class="sxs-lookup"><span data-stu-id="14760-150">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added.</span></span> <span data-ttu-id="14760-151">Dopo aver finalizzato le origini dati rilevanti per uno specifico custode, questo mapping verrà mantenuto e esteso all'insieme eDiscovery, all'elaborazione e alla revisione dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="14760-151">When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="14760-152">Optional Passaggio 4: mettere in attesa i depositari</span><span class="sxs-lookup"><span data-stu-id="14760-152">(Optional) Step 4: Place custodians on hold</span></span>

![Esenzioni di posizione](../media/AddCustodianStep5.PNG)

<span data-ttu-id="14760-154">Dopo aver finalizzato i depositari e le origini dati che si desidera aggiungere al caso, è possibile facoltativamente mettere in attesa alcuni o tutti i depositari.</span><span class="sxs-lookup"><span data-stu-id="14760-154">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold.</span></span> <span data-ttu-id="14760-155">Quando si attiva il blocco di un custode, il contenuto mappato a tale utente viene mantenuto finché non si rilascia il custode dalla causa o finché non si elimina l'esenzione.</span><span class="sxs-lookup"><span data-stu-id="14760-155">When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold.</span></span> <span data-ttu-id="14760-156">In alcuni casi, potrebbe essere necessario aggiungere i depositari a un caso senza bloccarli.</span><span class="sxs-lookup"><span data-stu-id="14760-156">In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="14760-157">Per posizionare i depositari e le origini dati selezionati in attesa:</span><span class="sxs-lookup"><span data-stu-id="14760-157">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="14760-158">Verificare le selezioni del custode e selezionare la casella di controllo per il blocco di ogni custode.</span><span class="sxs-lookup"><span data-stu-id="14760-158">Verify your custodian selections and select the checkbox to place each custodian on hold.</span></span> <span data-ttu-id="14760-159">Dopo che un custode è stato messo in attesa, verrà creato automaticamente un criterio di conservazione dei depositari contenente tutte le fonti detentive.</span><span class="sxs-lookup"><span data-stu-id="14760-159">After a custodian is placed on hold, a custodian hold policy containing all custodial sources will be automatically created.</span></span> <span data-ttu-id="14760-160">Se l'opzione non è selezionata, il custode e le origini dati selezionate verranno aggiunti al caso, ma il contenuto non verrà conservato.</span><span class="sxs-lookup"><span data-stu-id="14760-160">If the option is not checked, the custodian and selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="14760-161">Passare alla scheda **esenzioni** e selezionare il **criterio**di conservazione dei depositari.</span><span class="sxs-lookup"><span data-stu-id="14760-161">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="14760-162">Fare clic su **modifica** per visualizzare tutte le origini dati del custode selezionate.</span><span class="sxs-lookup"><span data-stu-id="14760-162">Click **Edit** to view all the selected custodian data sources.</span></span>

   
