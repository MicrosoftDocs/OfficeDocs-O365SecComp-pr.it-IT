---
title: Panoramica delle revisioni per l'eliminazione
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: Quando si crea un'etichetta che consente di conservare il contenuto in Office 365, è possibile scegliere di attivare la revisione eliminazione alla fine del periodo di conservazione.
ms.openlocfilehash: c0a2933f597c9b314ac4ce2e72de9619fac90082
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013720"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="73b2d-103">Panoramica delle revisioni per l'eliminazione</span><span class="sxs-lookup"><span data-stu-id="73b2d-103">Overview of disposition reviews</span></span>

<span data-ttu-id="73b2d-p101">Quando è stata raggiunta la fine del periodo di conservazione, sono diversi i motivi per cui è necessario verificare che il contenuto di decidere se che può essere eliminato ("eliminati"). Ad esempio, potrebbe essere necessario:</span><span class="sxs-lookup"><span data-stu-id="73b2d-p101">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed"). For example, you might need to:</span></span>
  
- <span data-ttu-id="73b2d-106">Sospendere l'eliminazione ("eliminazione") di contenuto pertinente in caso di controversia legale o un controllo.</span><span class="sxs-lookup"><span data-stu-id="73b2d-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="73b2d-107">Rimuovere contenuto nell'elenco di eliminazione per l'archiviazione in un archivio, se tale contenuto dispone di ricerca o cronologiche valore.</span><span class="sxs-lookup"><span data-stu-id="73b2d-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="73b2d-108">Assegnare un periodo di conservazione diversi per il contenuto, se il criterio originale non è una soluzione temporanea o provvisoria.</span><span class="sxs-lookup"><span data-stu-id="73b2d-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="73b2d-109">Restituire il contenuto per i client o trasferire a un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="73b2d-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="73b2d-p102">Quando si crea un'etichetta che consente di conservare il contenuto in Office 365, è possibile scegliere di attivare la revisione eliminazione alla fine del periodo di conservazione. In una revisione eliminazione:</span><span class="sxs-lookup"><span data-stu-id="73b2d-p102">When you create a label that retains content in Office 365, you can choose to trigger a disposition review at the end of the retention period. In a disposition review:</span></span>
  
- <span data-ttu-id="73b2d-p103">Le persone che si sceglie ricevano una notifica di posta elettronica che dispongono di contenuto per la revisione. Questi revisori possono essere singoli utenti, la distribuzione o gruppi di sicurezza o gruppi di Office 365. Si noti che le notifiche vengano inviate in una frequenza settimanale.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p103">The people you choose receive an email notification that they have content to review. These reviewers can be individual users, distribution or security groups, or Office 365 groups. Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="73b2d-115">I revisori passare alla pagina **eliminazione** della protezione &amp; centro conformità per controllare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="73b2d-115">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> 
    
- <span data-ttu-id="73b2d-116">Per ogni documento il revisore può:</span><span class="sxs-lookup"><span data-stu-id="73b2d-116">For each document, the reviewer can:</span></span>
    
  - <span data-ttu-id="73b2d-117">Applica un'etichetta diversa.</span><span class="sxs-lookup"><span data-stu-id="73b2d-117">Apply a different label.</span></span>
    
  - <span data-ttu-id="73b2d-118">Estendere il periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="73b2d-118">Extend its retention period.</span></span>
    
  - <span data-ttu-id="73b2d-119">Elimina permanentemente.</span><span class="sxs-lookup"><span data-stu-id="73b2d-119">Permanently delete it.</span></span>
    
- <span data-ttu-id="73b2d-120">I revisori possono visualizzare in sospeso o cronologiche disposizioni ed esportare lista di come file CSV.</span><span class="sxs-lookup"><span data-stu-id="73b2d-120">Reviewers can view either pending or historical dispositions, and export that list as a .csv file.</span></span>
    
<span data-ttu-id="73b2d-121">Si noti che la disposizione valutazioni richiedono una sottoscrizione a Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="73b2d-121">Note that disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="73b2d-p104">Un'analisi di eliminazione può includere contenuto cassette postali di Exchange, siti di SharePoint, OneDrive account e gruppi di Office 365. In attesa di una revisione eliminazione in tali percorsi il contenuto viene eliminato solo dopo che il revisore decide di eliminare definitivamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p104">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups. Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![Pagina di eliminazione](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a><span data-ttu-id="73b2d-125">Impostazione di revisione della disposizione mediante la creazione di un'etichetta</span><span class="sxs-lookup"><span data-stu-id="73b2d-125">Setting up the disposition review by creating a label</span></span>

<span data-ttu-id="73b2d-p105">Questo è il flusso di lavoro di base per la configurazione di un'analisi di eliminazione. Si noti che questo flusso Mostra un'etichetta viene pubblicato e quindi applicata manualmente da un utente. In alternativa, un'etichetta che genera un'analisi di eliminazione può essere applicato automaticamente al contenuto.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p105">This is the basic workflow for setting up a disposition review. Note that this flow shows a label being published and then manually applied by a user; alternatively, a label that triggers a disposition review can be auto-applied to content.</span></span>
  
![Grafico che mostra il flusso del funzionamento di eliminazione](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="73b2d-p106">Un'analisi di eliminazione è un'opzione quando si crea un'etichetta in Office 365. Si noti che questa opzione non è disponibile in un criterio di conservazione ma solo in un'etichetta con le impostazioni di conservazione.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p106">A disposition review is an option when you create a label in Office 365. Note that this option is not available in a retention policy but only in a label with retention settings.</span></span>
  
<span data-ttu-id="73b2d-131">Per ulteriori informazioni sulle etichette, vedere [Overview of etichette](labels.md).</span><span class="sxs-lookup"><span data-stu-id="73b2d-131">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
![Impostazioni di conservazione per un'etichetta](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a><span data-ttu-id="73b2d-133">Eliminazione del contenuto</span><span class="sxs-lookup"><span data-stu-id="73b2d-133">Disposing content</span></span>

<span data-ttu-id="73b2d-p107">Quando un revisore riceve una notifica tramite posta elettronica che il contenuto è pronto per la revisione, consente di passare alla pagina di **eliminazione** per la protezione &amp; centro conformità e selezionare uno o più elementi. Il revisore può quindi:</span><span class="sxs-lookup"><span data-stu-id="73b2d-p107">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center and select one or more items. The reviewer can then:</span></span> 
  
- <span data-ttu-id="73b2d-136">Applica un'etichetta diversa.</span><span class="sxs-lookup"><span data-stu-id="73b2d-136">Apply a different label.</span></span>
    
- <span data-ttu-id="73b2d-137">Estendere il periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="73b2d-137">Extend the retention period.</span></span>
    
- <span data-ttu-id="73b2d-138">Consente di eliminare definitivamente l'elemento.</span><span class="sxs-lookup"><span data-stu-id="73b2d-138">Permanently delete the item.</span></span>
    
<span data-ttu-id="73b2d-p108">Il revisore può utilizzare il collegamento per visualizzare il documento nella posizione originale, se il revisore disponga delle autorizzazioni per tale posizione. Durante un'analisi di eliminazione, il contenuto non viene spostata dalla posizione originale e che non venga eliminato fino a quando il revisore decida di farlo.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p108">A reviewer can use the link to view the document in its original location, if the reviewer has permissions for that location. During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="73b2d-p109">Si noti che le notifiche tramite posta elettronica vengono inviate automaticamente a revisori su base settimanale. Pertanto, quando è stata raggiunta la fine del periodo di conservazione, potrebbe richiedere fino a sette giorni ai revisori di ricevere la notifica di posta elettronica che il contenuto è in attesa di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p109">Note that the email notifications are sent automatically to reviewers on a weekly basis. Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="73b2d-p110">Si noti inoltre che vengono controllate tutte le azioni di eliminazione. A tale scopo, è necessario attivare il controllo almeno un giorno prima della prima azione di eliminazione: per ulteriori informazioni, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="73b2d-p110">Also note that all disposition actions are audited. To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
![Opzioni di eliminazione per un documento](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="73b2d-146">Autorizzazioni per la disposizione</span><span class="sxs-lookup"><span data-stu-id="73b2d-146">Permissions for disposition</span></span>

<span data-ttu-id="73b2d-p111">Per ottenere l'accesso alla pagina di **eliminazione** , i revisori devono essere membri del ruolo di **Gestione di eliminazione** e il ruolo **Registri di controllo View-Only** . È consigliabile la creazione di un nuovo gruppo di ruolo denominato revisori di eliminazione, aggiunta di questi due ruoli a tale gruppo di ruoli e quindi l'aggiunta di membri al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p111">To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="73b2d-149">Per ulteriori informazioni, vedere [fornire agli utenti di accedere a Office 365 Security &amp; centro conformità](grant-access-to-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="73b2d-149">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md)</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="73b2d-150">Quanto tempo fino a quando non viene eliminato definitivamente eliminato il contenuto</span><span class="sxs-lookup"><span data-stu-id="73b2d-150">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="73b2d-p112">Contenuto in attesa di una revisione di eliminazione viene eliminato solo dopo che il revisore decide di eliminare definitivamente il contenuto. Quando il revisore sceglie questa opzione, il contenuto del sito di SharePoint o OneDrive account diventa idoneo per il processo di pulizia standard descritto in questa sezione: [funzionamento di un criterio di conservazione con contenuti in locale](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="73b2d-p112">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content. When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="73b2d-153">Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="73b2d-153">This means that:</span></span>
  
- <span data-ttu-id="73b2d-p113">È contenuto in una raccolta documenti di spostamento per la prima fase Cestino **7 giorni** di eliminazione e quindi eliminati definitivamente **93 giorni** dopo che. Il Cestino non è indicizzato dalla ricerca e quindi il relativo contenuto non è disponibile a un'esenzione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p113">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that. The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span> 
    
- <span data-ttu-id="73b2d-156">Il contenuto in attesa la conservazione raccolta sarà definitivamente eliminato **7 giorni** di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="73b2d-156">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span> 
    
## <a name="view-pending-and-completed-dispositions"></a><span data-ttu-id="73b2d-157">Visualizzazione in sospeso e completate disposizioni</span><span class="sxs-lookup"><span data-stu-id="73b2d-157">View pending and completed dispositions</span></span>

<span data-ttu-id="73b2d-158">Nella pagina **eliminazione** della sicurezza &amp; centro conformità, è possibile visualizzare in sospeso e completate disposizioni:</span><span class="sxs-lookup"><span data-stu-id="73b2d-158">On the **Disposition** page of the Security &amp; Compliance Center, you can view both pending and completed dispositions:</span></span> 
  
- <span data-ttu-id="73b2d-p114">**In sospeso** disposizioni sono raggiunta la fine del loro periodo di conservazione e richiedono un'analisi di eliminazione. Dopo aver verificato ogni elemento, se si desidera applicare un'etichetta diversa, estendere il periodo di conservazione o eliminarla in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p114">**Pending** dispositions have reached the end of their retention period and require a disposition review. After reviewing each item, decide if you want to apply a different label to it, extend its retention period, or permanently delete it.</span></span> 
    
- <span data-ttu-id="73b2d-p115">**Completato** disposizioni approvati per l'eliminazione durante un'analisi di eliminazione e sono in corso l'eliminazione definitiva. Elementi con un'altra etichetta applicato o il periodo di conservazione estese come parte di un'analisi non viene visualizzato di seguito.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p115">**Completed** dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted. Items that had a different label applied or their retention period extended as part of a review won't appear here.</span></span> 
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="73b2d-163">Filtrare le visualizzazioni di eliminazione</span><span class="sxs-lookup"><span data-stu-id="73b2d-163">Filter the disposition views</span></span>

<span data-ttu-id="73b2d-p116">È possibile filtrare le visualizzazioni dall'intervallo di tempo o etichetta. Per in sospeso disposizioni, l'intervallo di tempo in base alla data di scadenza. Per cronologiche disposizioni, l'intervallo di tempo si basa sulla data di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="73b2d-p116">You can filter these views by label or time range. For pending dispositions, the time range is based on the expiry date. For historical dispositions, the time range is based on the deletion date.</span></span>
  
![Opzioni di filtro nella pagina di eliminazione](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a><span data-ttu-id="73b2d-168">Esportare gli elementi di eliminazione</span><span class="sxs-lookup"><span data-stu-id="73b2d-168">Export the disposition items</span></span>

<span data-ttu-id="73b2d-169">È inoltre possibile esportare gli elementi in una visualizzazione come file CSV che è possibile aprire in Excel.</span><span class="sxs-lookup"><span data-stu-id="73b2d-169">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![Eliminazione esportato dati in Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

