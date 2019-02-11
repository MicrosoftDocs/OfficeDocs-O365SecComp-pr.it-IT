---
title: Gestire depositari in un caso eDiscovery avanzate (Preview)
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
ms.openlocfilehash: cce823924502fa2617d7819dc0967733fbc072e0
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706097"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="505b6-102">Gestire depositari in un caso eDiscovery avanzate (Preview)</span><span class="sxs-lookup"><span data-stu-id="505b6-102">Manage custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="505b6-p101">La scheda depositari contiene un elenco di tutti i depositari nel caso può essere ordinato. Dopo aver aggiunto depositari a un caso, verranno raccolti automaticamente informazioni dettagliate su ogni depositaria da Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="505b6-p101">The Custodians tab contains a sortable list of all the custodians in the case. After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

## <a name="viewing-custodian-details"></a><span data-ttu-id="505b6-105">Visualizzazione dei dettagli depositaria</span><span class="sxs-lookup"><span data-stu-id="505b6-105">Viewing custodian details</span></span>

<span data-ttu-id="505b6-p102">Dopo avere aggiunto un depositaria a un caso e selezionarli dall'elenco nella scheda **depositari** , viene visualizzata la pagina comparsa che contiene i dettagli depositaria. Da qui è possibile visualizzare tutti i dettagli relativi a tale depositaria. Nella pagina comparsa sono i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="505b6-p102">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian. The flyout page contains the following fields:</span></span>

- <span data-ttu-id="505b6-108">Informazioni di contatto</span><span class="sxs-lookup"><span data-stu-id="505b6-108">Contact information</span></span>

  - <span data-ttu-id="505b6-p103">**Nome visualizzato**: il nome visualizzato nella Rubrica per il depositaria. Questa è in genere la combinazione del nome del depositaria, intermedio iniziale e cognome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="505b6-p103">**Display Name**: The name displayed in the address book for the custodian. This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="505b6-111">**/ SMTP Mail**: indirizzo SMTP per depositaria, ad esempio jeff@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="505b6-111">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="505b6-112">**Titolo**: titolo professionale del depositaria.</span><span class="sxs-lookup"><span data-stu-id="505b6-112">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="505b6-113">**Reparto**: il nome per il reparto in cui lavora il depositaria.</span><span class="sxs-lookup"><span data-stu-id="505b6-113">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="505b6-p104">**Manager**: responsabile della depositaria. Il manager designato ricevono tutte le comunicazioni Escalation per questo depositaria.</span><span class="sxs-lookup"><span data-stu-id="505b6-p104">**Manager**: The custodian’s manager. The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="505b6-116">Informazioni sulle posizioni</span><span class="sxs-lookup"><span data-stu-id="505b6-116">Location information</span></span>

  - <span data-ttu-id="505b6-117">**Città**: città in cui si trova il depositaria.</span><span class="sxs-lookup"><span data-stu-id="505b6-117">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="505b6-118">**Informazioni sullo stato**: lo stato o la provincia nell'indirizzo del depositaria.</span><span class="sxs-lookup"><span data-stu-id="505b6-118">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="505b6-119">**Paese**: paese/area geografica in cui si trova; il depositaria ad esempio, "Usa" o "UK".</span><span class="sxs-lookup"><span data-stu-id="505b6-119">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="505b6-120">**Office**: l'ubicazione dell'ufficio sul posto di depositaria d'ufficio.</span><span class="sxs-lookup"><span data-stu-id="505b6-120">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="505b6-121">Informazioni sul casi</span><span class="sxs-lookup"><span data-stu-id="505b6-121">Case information</span></span>

  - <span data-ttu-id="505b6-122">**Stato esenzione**: indica se il depositaria è messe in attesa.</span><span class="sxs-lookup"><span data-stu-id="505b6-122">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="505b6-p105">**Lo stato di comunicazione**: indica se il depositaria è stata eseguita una notifica di attesa. Se il depositaria è stato rilasciato un avviso, questo verrà contrassegnato come *pubblicati*. Se il depositaria non è stato rilasciato un avviso, quindi questo stato saranno *rimosse*.</span><span class="sxs-lookup"><span data-stu-id="505b6-p105">**Communication status**: Indicates if the custodian has been issued a hold notice. If the custodian has been issued a notice, then this will be marked as *Published*. If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="505b6-p106">**Stato**: lo stato di depositaria all'interno del case. Questo valore sarà *Attiva* se il depositaria è ancora in attesa per il case. Se un depositaria viene rimosso da un caso, il relativo stato verrà modificato in *rilasciato*.</span><span class="sxs-lookup"><span data-stu-id="505b6-p106">**Status**: The status of the custodian within the case. This will be *Active* if the custodian is still on hold for the case. If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="505b6-129">Stato di elaborazione</span><span class="sxs-lookup"><span data-stu-id="505b6-129">Processing status</span></span>

  - <span data-ttu-id="505b6-130">**Lo stato di indicizzazione**: indica lo stato del processo di indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="505b6-130">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="505b6-131">**Indicizzazione l'ultima volta aggiornati**: indica datestamp dell'ultima attivazione quando il processo di indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="505b6-131">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="505b6-132">**Origini dati**: Visualizza il numero di cassette postali, i siti e i team che sono stati selezionati per la depositaria.</span><span class="sxs-lookup"><span data-stu-id="505b6-132">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="updating-a-custodian"></a><span data-ttu-id="505b6-133">Aggiornamento di un depositaria</span><span class="sxs-lookup"><span data-stu-id="505b6-133">Updating a custodian</span></span>

<span data-ttu-id="505b6-p107">Durante l'avanzamento maiuscole, si potrebbe scoprire che potrebbero esserci altre origini dati rilevanti per un & depositaria specifici al caso. In altri scenari, si desidera rimuovere alcune origini dati che sono stati esaminati e considerati come non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="505b6-p107">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case. In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="505b6-136">Per aggiornare un depositaria e le origini dati selezionati:</span><span class="sxs-lookup"><span data-stu-id="505b6-136">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="505b6-137">Selezionare un caso esistente **eDiscovery gt _ avanzate eDiscovery (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="505b6-137">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="505b6-138">Nel caso, fare clic sulla scheda **depositari** .</span><span class="sxs-lookup"><span data-stu-id="505b6-138">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="505b6-139">Selezionare il custodian(s) dall'elenco e fare clic su **Modifica origini**.</span><span class="sxs-lookup"><span data-stu-id="505b6-139">Select the custodian(s) from the list and click **Edit sources**.</span></span>
  
4. <span data-ttu-id="505b6-140">Aggiornare le selezioni per i percorsi di Exchange e OneDrive facendo clic su **origini dati scegliere**.</span><span class="sxs-lookup"><span data-stu-id="505b6-140">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="505b6-p108">Aggiungere o rimuovere i team, SharePoint o Exchange le cassette postali mappato all'utente fare clic per **selezionare origini dati aggiuntive**. Per ulteriori informazioni su come è possibile mappare i dati origini a un depositaria, vedere [Add depositari a un caso](add-custodians-to-case.md).</span><span class="sxs-lookup"><span data-stu-id="505b6-p108">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**. For more information about how you to map data sources to a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="505b6-143">Per aggiornare lo stato di conservazione depositaria, fare clic su **archiviazioni sul posto detentive**e abilitare o disabilitare l'archiviazione per depositari.</span><span class="sxs-lookup"><span data-stu-id="505b6-143">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="505b6-144">È possibile selezionare più depositari per eseguire le operazioni in blocco, ad esempio la reindicizzazione, rilascio o modifica di un set di depositari.</span><span class="sxs-lookup"><span data-stu-id="505b6-144">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="505b6-145">Risoluzione degli errori di elaborazione depositaria</span><span class="sxs-lookup"><span data-stu-id="505b6-145">Resolving custodian processing errors</span></span>

<span data-ttu-id="505b6-p109">Nella maggior parte dei flussi di lavoro legali, dopo l'aggiunta di depositari per il controllo specifico, un sottoinsieme di dati degli utenti verrà eseguita la ricerca. A causa di dimensioni dei file di grandi dimensioni o danneggiamento dei possibile, alcuni elementi all'interno di origini dati degli depositari potrebbero essere parzialmente indicizzati. Utilizzando la funzionalità di indicizzazione completa di eDiscovery avanzate (anteprima), questi elementi indicizzati parzialmente possono essere automaticamente risolte nuovamente la ricerca per indicizzazione e la reindicizzazione questi elementi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="505b6-p109">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched. Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed. Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="505b6-p110">Quando un depositaria viene aggiunto a un caso, i dati vengono automaticamente "estensione indicizzati", che consente agli utenti di lasciare queste parzialmente indicizzato elementi sul posto evita di dover scaricare, correggere ed eseguire di nuovo le ricerche all'esterno di Office 365. Durante il ciclo di vita di un caso, l'utente può correggere gli elementi o aggiungere nuove origini dati per un determinato depositaria. Ciò può richiedere l'indice depositaria da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="505b6-p110">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365. During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian. This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="505b6-152">Per attivare un processo di indicizzazione nuovamente all'indirizzo parzialmente voci indicizzate:</span><span class="sxs-lookup"><span data-stu-id="505b6-152">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="505b6-153">Passare a **eDiscovery gt _ avanzate eDiscovery (Preview)** e selezionare un caso esistente.</span><span class="sxs-lookup"><span data-stu-id="505b6-153">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="505b6-154">Nel caso, fare clic su scheda **depositari**.</span><span class="sxs-lookup"><span data-stu-id="505b6-154">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="505b6-155">Selezionare custodian(s) che deve essere reindicizzazione e quindi fare clic su **Aggiorna indice** nella pagina del riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="505b6-155">Select the custodian(s) that needs to be re-indexed, and then click **Update index** on the flyout page.</span></span>

4. <span data-ttu-id="505b6-156">Controllare lo stato dell'indice depositaria facendo clic sul collegamento nella colonna **stato processo di indicizzazione** nella scheda **depositari** .</span><span class="sxs-lookup"><span data-stu-id="505b6-156">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="505b6-157">Tenere traccia dello stato per il processo di indicizzazione nuovamente anche nella scheda **processi** .</span><span class="sxs-lookup"><span data-stu-id="505b6-157">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="505b6-158">Per ulteriori informazioni sugli elementi indicizzati parzialmente monitorando e la nuova indicizzazione, vedere [correggere gli errori di elaborazione](processing-data-for-case.md).</span><span class="sxs-lookup"><span data-stu-id="505b6-158">For more information about re-indexing and remediating partially indexed items, see [Fix processing errors](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="505b6-159">Rilasciare un depositaria dal caso</span><span class="sxs-lookup"><span data-stu-id="505b6-159">Releasing a custodian from a case</span></span>

<span data-ttu-id="505b6-160">Viene rilasciato un depositaria nei casi in cui un caso viene chiuso, un depositaria non è più obbligo di conservare il contenuto per un caso o quando un depositaria viene ritenuta su no più essere pertinenti per una determinata caso.</span><span class="sxs-lookup"><span data-stu-id="505b6-160">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="505b6-p111">Se si rilascia un depositaria dopo la pubblicazione di un avviso di attesa, verrà inviato un avviso di versione per il depositaria. Inoltre, qualsiasi esenzioni detentive attribuite alle depositari rilasciate anche da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="505b6-p111">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian. In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="505b6-163">Se il depositaria è stato messo in un'esenzione invisibile all'utente, cui non sono state inviate le notifiche di conservazione a fini giudiziari, vengono rimosse le esenzioni detentive attribuite alle depositari rilasciati.</span><span class="sxs-lookup"><span data-stu-id="505b6-163">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="505b6-164">Per rilasciare un depositaria:</span><span class="sxs-lookup"><span data-stu-id="505b6-164">To release a custodian:</span></span> 

1.  <span data-ttu-id="505b6-165">Passare alla scheda **depositari** .</span><span class="sxs-lookup"><span data-stu-id="505b6-165">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="505b6-166">Selezionare il depositaria dall'elenco e fare clic su **depositari versione** nella pagina del riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="505b6-166">Select the custodian from the list and click **Release custodians** on the flyout page.</span></span>

    <span data-ttu-id="505b6-167">Lo stato di depositaria nella scheda **depositari** è impostato su **rilascio** e la **Stato esenzione** page comparsa viene modificato in **inattivo**.</span><span class="sxs-lookup"><span data-stu-id="505b6-167">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="505b6-p112">Un depositaria potrebbe essere contemporaneamente essere coinvolto in materia di conservazione a fini giudiziari diversi. Quando viene rilasciato un depositaria dal caso, le esenzioni e le notifiche tra gli altri aspetti non essere interessate.</span><span class="sxs-lookup"><span data-stu-id="505b6-p112">A custodian might be simultaneously be involved in several legal hold matters. When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="505b6-170">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="505b6-170">Related information</span></span>

 - [<span data-ttu-id="505b6-171">Correzione degli errori durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="505b6-171">Error remediation when processing data</span></span>](error-remediation.md) 
- [<span data-ttu-id="505b6-172">Uso delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="505b6-172">Work with communications</span></span>](managing-custodian-communications.md)
