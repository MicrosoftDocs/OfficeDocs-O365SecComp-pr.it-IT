---
title: Aggiungere depositari a un caso eDiscovery avanzate (Preview)
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
ms.openlocfilehash: 88d2e64f4e1fb519955d8970b34e9670fb18d3f8
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706107"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="b4bab-102">Aggiungere depositari a un caso eDiscovery avanzate (Preview)</span><span class="sxs-lookup"><span data-stu-id="b4bab-102">Add custodians to an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="b4bab-p101">Utilizzo di eDiscovery avanzate (anteprima), è possibile utilizzare lo strumento di gestione incorporati depositaria per coordinare i flussi di lavoro intorno a gestione depositari e identificare le origini dati rilevanti, detentive all'interno di un caso. Quando si aggiunge un depositaria, il sistema può automaticamente identificare e archiviazioni sul posto alle loro cassette postali di Exchange primaria e OneDrive per sito aziendale. Come di procedere con l'individuazione, si potrebbe Scopri e mappare le cassette postali di altri o siti che un depositaria a cui si accede al passato o team che un depositaria appartenga alla data odierna.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p101">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case. When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site. As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="b4bab-106">Utilizzare il flusso di lavoro seguente per aggiungere e gestire depositari in casi di eDiscovery avanzate (Preview) all'interno di sicurezza & centro conformità.</span><span class="sxs-lookup"><span data-stu-id="b4bab-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="b4bab-107">Passaggio 1: Identificare potenziali depositari</span><span class="sxs-lookup"><span data-stu-id="b4bab-107">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="b4bab-p102">Il primo passaggio consiste nel identificare depositari appropriati per la materia. Per aggiungere depositari a un caso, è necessario essere un membro di eDiscovery Manager o un gruppo di ruoli di eDiscovery Admins.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p102">The first step is to identify the appropriate custodians for your matter. To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

<span data-ttu-id="b4bab-110">Per aggiungere depositari a un caso eDiscovery avanzate (Preview) esistenti:</span><span class="sxs-lookup"><span data-stu-id="b4bab-110">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="b4bab-111">Nella pagina **eDiscovery avanzate (anteprima)** , andare al caso.</span><span class="sxs-lookup"><span data-stu-id="b4bab-111">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="b4bab-112">Dopo aver selezionato un caso, passare alla scheda **depositari** e fare clic su **Aggiungi depositaria +**.</span><span class="sxs-lookup"><span data-stu-id="b4bab-112">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="b4bab-p103">Scegliere depositari che si desidera aggiungere al caso. È possibile avviare digitando per cercare e selezionare gli utenti Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p103">Choose the custodians that you want to add to the case. You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="b4bab-115">Dopo avere scelto l'elenco dei depositari, fare clic su **Avanti** per iniziare a identificare possibili origini dati.</span><span class="sxs-lookup"><span data-stu-id="b4bab-115">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
   
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="b4bab-116">(Facoltativo) Passaggio 2: Selezionare le origini dati depositaria</span><span class="sxs-lookup"><span data-stu-id="b4bab-116">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="b4bab-p104">Dopo aver aggiunto depositari a un caso, è possibile utilizzare Office 365 che consentono di identificare e mantenere le origini dati depositaria principale. Il prossimo passaggio del flusso di lavoro consiste nel selezionare le origini dati e di proprietà di depositari specificati nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p104">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources. The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

<span data-ttu-id="b4bab-119">Per identificare le origini dati depositaria:</span><span class="sxs-lookup"><span data-stu-id="b4bab-119">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="b4bab-120">Per ogni depositaria selezionare **Exchange** se si desidera che il sistema per identificare e aggiungere cassette postali di Exchange primaria del depositaria automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b4bab-120">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="b4bab-121">Per ogni depositaria selezionare **OneDrive** se si desidera che il sistema per identificare e aggiungere URL OneDrive primario del depositaria automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b4bab-121">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="b4bab-122">Dopo aver apportato le selezioni effettuate, essi sistema tenterà di identificare le origini dati e aggiungerli al caso automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b4bab-122">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="b4bab-123">Fare clic su **Avanti** per iniziare il mapping di origini dati aggiuntive per la depositaria.</span><span class="sxs-lookup"><span data-stu-id="b4bab-123">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="b4bab-124">(Facoltativo) Passaggio 3: Eseguire il mapping di origini dati aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b4bab-124">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="b4bab-p105">In base al caso, è anche possibile aggiungere cassette postali che un determinato depositaria potrebbe essere utilizzati in passato, gruppi di cui una depositaria attualmente è un membro o i siti che un depositaria hanno accesso a in passato. Oltre alle origini dati depositaria principale, è possibile aggiungere ulteriori origini di dati di Office 365 per un depositaria o utilizzare Office 365 per aiutare a identificare le origini dati potenzialmente pertinenti anche.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p105">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past. In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

<span data-ttu-id="b4bab-127">Per mappare le cassette postali, siti o team a un depositaria specifico:</span><span class="sxs-lookup"><span data-stu-id="b4bab-127">To map mailboxes, sites, or teams to a specific custodian:</span></span>
1. <span data-ttu-id="b4bab-128">Selezionare **aggiornamento** per assegnare i percorsi di contenuti, ad esempio le cassette postali, i siti e i team, a un depositaria specifico.</span><span class="sxs-lookup"><span data-stu-id="b4bab-128">Select **Update** to assign content locations, like mailboxes, sites, and Teams, to a specific custodian.</span></span> 

2. <span data-ttu-id="b4bab-129">Nell'elemento libero, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b4bab-129">In the flyout, specify the following:</span></span>
   
  -  <span data-ttu-id="b4bab-p106">**Cassette postali di Exchange** - fare clic su **Scegli utenti, gruppi o team** e quindi fare clic nuovamente su **Scegli utenti, gruppi o team** . Per specificare le cassette postali per assegnare a depositaria selezionato, utilizzare la casella Cerca per trovare cassette postali degli utenti e gruppi di distribuzione. È inoltre possibile assegnare la cassetta postale associata per un Team di Microsoft o un gruppo di Office 365. Selezionare la casella di controllo team utente, gruppo, fare clic su **Scegli**e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p106">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again. To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups. You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="b4bab-p107">Quando si fa clic su Scegli utenti, gruppi o team per specificare le cassette postali, la selezione delle cassette postali che viene visualizzata sia vuota. Questo è per impostazione predefinita per migliorare le prestazioni. Per aggiungere persone all'elenco, digitare un nome (almeno 3 caratteri) nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p107">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
   - <span data-ttu-id="b4bab-p108">**Siti di SharePoint** - fare clic su **Scegli siti** e quindi **Scegliere siti** per specificare ulteriori SharePoint e OneDrive per i siti che si desidera assegnare al depositaria selezionato. È inoltre possibile aggiungere l'URL del sito di SharePoint per un Team di Microsoft o un gruppo di Office 365. Digitare l'URL per ogni sito che si desidera assegnare. Fare clic su **Scegli**e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p108">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Type the URL for each site that you want to assign. Click **Choose**, and then click **Done**.</span></span>
   - <span data-ttu-id="b4bab-p109">**Team di Microsoft** – fare clic su **Scegliere i team** e quindi fare clic su **Team scegliere** nuovamente per visualizzare un elenco di gruppi di Team Microsoft che il depositaria appartenga alla data odierna. Selezionare il team che si desidera aggiungere il depositaria. Una volta selezionato, il sistema identificherà automaticamente & selezionare che il sito di SharePoint e cassetta postale di gruppo associato associate a tale Team di Microsoft. Fare clic su **Scegli**e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p109">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today. Select the Teams that you would like to add to your custodian. Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="b4bab-145">Per aggiungere ulteriori Teams Microsoft, è necessario aggiungere separatamente le cassette postali e il sito di SharePoint come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b4bab-145">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="b4bab-p110">Dopo avere origini di mapping, è possibile visualizzare il totale delle cassette postali, i siti e i team per depositari appena aggiunto. Quando aver completato le origini dati pertinenti per una specifica depositaria, questo mapping verrà gestito ed estesa alla raccolta di eDiscovery, l'elaborazione e i flussi di lavoro di revisione.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p110">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added. When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="b4bab-148">(Facoltativo) Passaggio 4: Posto depositari in attesa</span><span class="sxs-lookup"><span data-stu-id="b4bab-148">(Optional) Step 4: Place custodians on hold</span></span>

 <span data-ttu-id="b4bab-p111">Dopo avere scelto il depositari e origini dati che si desidera aggiungere al case, facoltativamente è possibile effettuare alcune o tutte le depositari in attesa. Quando si effettua una depositaria in attesa, il contenuto mappato a tale utente viene mantenuto finché non si rilascia depositaria dal case o finché non viene eliminato l'attesa. In alcuni casi, si desidera aggiungere depositari a un caso senza in cui vengono posizionati in attesa.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p111">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold. When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold. In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="b4bab-152">Per mettere il selezionato depositari e le origini dati in attesa:</span><span class="sxs-lookup"><span data-stu-id="b4bab-152">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="b4bab-p112">Verificare le selezioni effettuate depositaria e selezionare checkox posizionare ciascun depositaria in attesa. Una volta che un depositaria viene messa in attesa, verrà creato automaticamente un criterio di conservazione depositaria contenente detentive tutte le origini. Se l'opzione non è selezionata, le origini dati di depositaria & selezionata verranno aggiunto al caso ma non verrà mantenuto il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p112">Verify your custodian selections and select the checkox to place each custodian on hold.Once a custodian is placed on hold, a custodian hold policy containing all custodial sources will automatically be created. If the option is not checked, the custodian & selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="b4bab-155">Passare alla scheda **contiene** e selezionare il **Criterio di conservazione depositaria**.</span><span class="sxs-lookup"><span data-stu-id="b4bab-155">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="b4bab-156">Fare clic su **Modifica** per visualizzare tutte le origini dati depositaria selezionato.</span><span class="sxs-lookup"><span data-stu-id="b4bab-156">Click **Edit** to view all the selected custodian data sources.</span></span>
