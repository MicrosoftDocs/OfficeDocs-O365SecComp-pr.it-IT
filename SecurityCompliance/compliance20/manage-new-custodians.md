---
title: Gestire i depositari in un caso avanzato di eDiscovery (anteprima)
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
ms.openlocfilehash: 95a1bcbbc279ad4e476fc479e701b0f8a921c83b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295679"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="3c631-102">Gestire i depositari in un caso avanzato di eDiscovery (anteprima)</span><span class="sxs-lookup"><span data-stu-id="3c631-102">Manage custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="3c631-p101">La scheda depositari contiene un elenco ordinabile di tutti i depositari nel caso. Dopo aver aggiunto i depositari a un caso, i dettagli relativi a ogni custode verranno raccolti automaticamente da Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3c631-p101">The Custodians tab contains a sortable list of all the custodians in the case. After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

## <a name="viewing-custodian-details"></a><span data-ttu-id="3c631-105">Visualizzazione dei dettagli del custode</span><span class="sxs-lookup"><span data-stu-id="3c631-105">Viewing custodian details</span></span>

<span data-ttu-id="3c631-p102">Dopo aver aggiunto un custode a un caso e averli selezionati nell'elenco della scheda **depositari** , viene visualizzata la pagina del riquadro a comparsa contenente i dettagli del custode. Da qui, è possibile visualizzare tutti i dettagli relativi a quel custode. La pagina del riquadro a comparsa contiene i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c631-p102">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian. The flyout page contains the following fields:</span></span>

- <span data-ttu-id="3c631-108">Informazioni di contatto</span><span class="sxs-lookup"><span data-stu-id="3c631-108">Contact information</span></span>

  - <span data-ttu-id="3c631-p103">**Nome**visualizzato: il nome visualizzato nella rubrica per il custode. Questo è in genere la combinazione del nome, dell'iniziale e del cognome del custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-p103">**Display Name**: The name displayed in the address book for the custodian. This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="3c631-111">**Posta/SMTP**: indirizzo SMTP per il custode, ad esempio Jeff@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="3c631-111">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="3c631-112">**Titolo**: titolo del processo del custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-112">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="3c631-113">**Reparto**: il nome del reparto in cui lavora il custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-113">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="3c631-p104">**Manager**: il responsabile della banca depositaria. Il responsabile designato riceverà eventuali comunicazioni di esCalation per questo custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-p104">**Manager**: The custodian’s manager. The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="3c631-116">Informazioni sulle posizioni</span><span class="sxs-lookup"><span data-stu-id="3c631-116">Location information</span></span>

  - <span data-ttu-id="3c631-117">**Città**: la città in cui si trova il custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-117">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="3c631-118">**Stato**: lo stato o la provincia nell'indirizzo del custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-118">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="3c631-119">**Paese/area**geografica: il paese/area geografica in cui si trova il custode; ad esempio, "US" o "UK".</span><span class="sxs-lookup"><span data-stu-id="3c631-119">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="3c631-120">**Office**: la sede dell'ufficio nel luogo di lavoro del custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-120">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="3c631-121">Informazioni sul caso</span><span class="sxs-lookup"><span data-stu-id="3c631-121">Case information</span></span>

  - <span data-ttu-id="3c631-122">**Stato blocco**: indica se il custode è stato messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="3c631-122">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="3c631-p105">**Stato della comunicazione**: indica se il custode ha emesso un avviso di esenzione. Se il custode ha emesso un avviso, questo verrà contrassegnato come *pubblicato*. Se al custode non è stato emesso un avviso, lo stato non verrà *pubblicato*.</span><span class="sxs-lookup"><span data-stu-id="3c631-p105">**Communication status**: Indicates if the custodian has been issued a hold notice. If the custodian has been issued a notice, then this will be marked as *Published*. If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="3c631-p106">**Status**: lo stato del custode all'interno del caso. Questo sarà *attivo* se il custode è ancora in attesa per il caso. Se un custode è stato rimosso da un caso, il relativo stato verrà modificato in *rilasciato*.</span><span class="sxs-lookup"><span data-stu-id="3c631-p106">**Status**: The status of the custodian within the case. This will be *Active* if the custodian is still on hold for the case. If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="3c631-129">Stato di elaborazione</span><span class="sxs-lookup"><span data-stu-id="3c631-129">Processing status</span></span>

  - <span data-ttu-id="3c631-130">**Stato**di indicizzazione: indica lo stato del processo di indicizzazione Deep.</span><span class="sxs-lookup"><span data-stu-id="3c631-130">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="3c631-131">**IndexIng Last updated Time**: indica la DateStamp di quando è stato attivato l'ultimo processo di indicizzazione Deep.</span><span class="sxs-lookup"><span data-stu-id="3c631-131">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="3c631-132">**Origini dati**: Visualizza il numero di cassette postali, siti e team selezionati per il custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-132">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="updating-a-custodian"></a><span data-ttu-id="3c631-133">Aggiornamento di un custode</span><span class="sxs-lookup"><span data-stu-id="3c631-133">Updating a custodian</span></span>

<span data-ttu-id="3c631-p107">Man mano che il caso progredisce, è possibile rilevare che potrebbero essere presenti ulteriori origini dati rilevanti per un determinato custode & il caso. In altri scenari potrebbe essere necessario rimuovere determinate origini dati che sono state esaminate e ritenute irrilevanti.</span><span class="sxs-lookup"><span data-stu-id="3c631-p107">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case. In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="3c631-136">Per aggiornare un custode e le origini dati selezionate:</span><span class="sxs-lookup"><span data-stu-id="3c631-136">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="3c631-137">Selezionare un caso esistente dall' **eDiscovery _GT_ Advanced eDiscovery (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="3c631-137">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="3c631-138">Nel caso, fare clic sulla scheda **depositari** .</span><span class="sxs-lookup"><span data-stu-id="3c631-138">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="3c631-139">Selezionare il custode o i depositari dall'elenco e fare clic su **modifica origini**.</span><span class="sxs-lookup"><span data-stu-id="3c631-139">Select the custodian(s) from the list and click **Edit sources**.</span></span>
  
4. <span data-ttu-id="3c631-140">Consente di aggiornare le selezioni per i percorsi di Exchange e OneDrive facendo clic su **Scegli origini dati**.</span><span class="sxs-lookup"><span data-stu-id="3c631-140">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="3c631-p108">Aggiunta o rimozione di Team, SharePoint o cassette postali di Exchange mappati dall'utente facendo clic per **selezionare origini dati aggiuntive**. Per ulteriori informazioni su come eseguire il mapping delle origini dati a un custode, vedere [aggiungere i depositari a un caso](add-custodians-to-case.md).</span><span class="sxs-lookup"><span data-stu-id="3c631-p108">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**. For more information about how you to map data sources to a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="3c631-143">Per aggiornare lo stato di conservazione dei depositari, fare clic su **Archivia esenzioni detentive**e abilitare o disabilitare il blocco per i depositari.</span><span class="sxs-lookup"><span data-stu-id="3c631-143">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="3c631-144">È possibile selezionare più depositari per eseguire azioni in blocco, come la reindicizzazione, il rilascio o la modifica di un insieme di depositari.</span><span class="sxs-lookup"><span data-stu-id="3c631-144">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="3c631-145">Risoluzione degli errori di elaborazione del custode</span><span class="sxs-lookup"><span data-stu-id="3c631-145">Resolving custodian processing errors</span></span>

<span data-ttu-id="3c631-p109">Nella maggior parte dei flussi di lavoro legali, dopo l'aggiunta di depositari per un'indagine specifica, verrà eseguita una ricerca in un sottoinsieme di dati degli utenti. A causa di grandi dimensioni o possibili danneggiamenti, alcuni elementi all'interno delle origini dati dei depositari possono essere parzialmente indicizzati. Utilizzando la funzionalità Advanced eDiscovery (Preview) Deep indicizzazione, questi elementi parzialmente indicizzati possono essere corretti automaticamente tramite la ricerca per indicizzazione e la reindicizzazione di questi elementi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="3c631-p109">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched. Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed. Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="3c631-p110">Quando un custode viene aggiunto a un caso, i relativi dati vengono automaticamente "indicizzati in profondità", consentendo agli utenti di lasciare tali elementi parzialmente indicizzati anziché dover scaricare, correggere e rieseguire le ricerche al di fuori di Office 365. Durante il ciclo di vita di un caso, un utente può correggere gli elementi o aggiungere nuove origini dati per un determinato custode. Potrebbe essere necessario aggiornare l'indice del custode.</span><span class="sxs-lookup"><span data-stu-id="3c631-p110">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365. During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian. This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="3c631-152">Per attivare un processo di reindicizzazione per indirizzare gli elementi parzialmente indicizzati:</span><span class="sxs-lookup"><span data-stu-id="3c631-152">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="3c631-153">Passare a **eDiscovery _GT_ Advanced eDiscovery (Preview)** e selezionare un caso esistente.</span><span class="sxs-lookup"><span data-stu-id="3c631-153">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="3c631-154">Nel caso, fare clic su per la **scheda depositari**.</span><span class="sxs-lookup"><span data-stu-id="3c631-154">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="3c631-155">Selezionare il custode o i depositari che devono essere reindicizzati e quindi fare clic su **Aggiorna indice** nella pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="3c631-155">Select the custodian(s) that needs to be re-indexed, and then click **Update index** on the flyout page.</span></span>

4. <span data-ttu-id="3c631-156">Controllare lo stato dell'indice del custode facendo clic sul collegamento nella colonna **stato processo** di indicizzazione nella scheda **depositari** .</span><span class="sxs-lookup"><span data-stu-id="3c631-156">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="3c631-157">Lo stato del processo di reindicizzazione può essere rilevato anche nella scheda **processi** .</span><span class="sxs-lookup"><span data-stu-id="3c631-157">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="3c631-158">Per ulteriori informazioni su come reindicizzare e correggere gli elementi parzialmente indicizzati, vedere [Fix Processing Errors](processing-data-for-case.md).</span><span class="sxs-lookup"><span data-stu-id="3c631-158">For more information about re-indexing and remediating partially indexed items, see [Fix processing errors](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="3c631-159">Rilascio di un custode da un caso</span><span class="sxs-lookup"><span data-stu-id="3c631-159">Releasing a custodian from a case</span></span>

<span data-ttu-id="3c631-160">Un custode viene rilasciato in situazioni in cui un caso è chiuso, un custode non è più in dovere di preservare il contenuto di un caso o quando un custode è ritenuto non più pertinente a un caso specifico.</span><span class="sxs-lookup"><span data-stu-id="3c631-160">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="3c631-p111">Se si rilascia un custode dopo la pubblicazione di un avviso di esenzione, verrà inviato un avviso di rilascio al custode. Inoltre, verranno rimossi anche tutti gli appigli detentivi attribuiti ai depositari rilasciati.</span><span class="sxs-lookup"><span data-stu-id="3c631-p111">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian. In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="3c631-163">Se il custode è stato collocato in una posizione invisibile all'utente, in cui non sono state rilasciate notifiche di archiviazione legale, verranno rimossi tutti i resti di custodia attribuiti ai depositari rilasciati.</span><span class="sxs-lookup"><span data-stu-id="3c631-163">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="3c631-164">Per rilasciare un custode:</span><span class="sxs-lookup"><span data-stu-id="3c631-164">To release a custodian:</span></span> 

1.  <span data-ttu-id="3c631-165">Passare alla scheda **depositari** .</span><span class="sxs-lookup"><span data-stu-id="3c631-165">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="3c631-166">Selezionare il custode dall'elenco e fare clic su **rilascia i depositari** nella pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="3c631-166">Select the custodian from the list and click **Release custodians** on the flyout page.</span></span>

    <span data-ttu-id="3c631-167">Lo stato del custode nella scheda **depositari** è impostato su **rilasciato** e lo **stato di blocco** sulla pagina del riquadro a comparsa viene modificato in **inattivo**.</span><span class="sxs-lookup"><span data-stu-id="3c631-167">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="3c631-p112">Un custode potrebbe essere coinvolto contemporaneamente in diverse questioni legali. Quando un custode viene rilasciato da un caso, le esenzioni e le notifiche su altre questioni non verranno influenzate.</span><span class="sxs-lookup"><span data-stu-id="3c631-p112">A custodian might be simultaneously be involved in several legal hold matters. When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="3c631-170">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="3c631-170">Related information</span></span>

 - [<span data-ttu-id="3c631-171">Correzione degli errori durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="3c631-171">Error remediation when processing data</span></span>](error-remediation.md) 
- [<span data-ttu-id="3c631-172">Uso delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="3c631-172">Work with communications</span></span>](managing-custodian-communications.md)
