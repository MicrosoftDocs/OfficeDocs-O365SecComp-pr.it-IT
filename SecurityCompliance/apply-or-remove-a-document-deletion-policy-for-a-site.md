---
title: Applicare o rimuovere un criterio di eliminazione del documento per un sito
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Le organizzazioni spesso sono soggette a regolamentazioni di conformità, normative legali o di altro tipo, che richiedono di mantenere i documenti per un certo periodo di tempo. Tuttavia, mantenere i documenti più a lungo del necessario può esporre l'organizzazione a rischi legali. Per questo motivo, la tua organizzazione potrebbe aver creato un criterio di eliminazione del documento per il tuo sito; per esempio, potrebbe essere necessario eliminare i documenti dell'attività generale cinque anni dopo la loro creazione.
ms.openlocfilehash: c00298a177ac405181ab2b2d9642b631e60a8a92
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219166"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="6cad3-105">Applicare o rimuovere un criterio di eliminazione del documento per un sito</span><span class="sxs-lookup"><span data-stu-id="6cad3-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="6cad3-p102">Le organizzazioni spesso sono soggette a regolamentazioni di conformità, normative legali o di altro tipo, che richiedono di mantenere i documenti per un certo periodo di tempo. Tuttavia, mantenere i documenti più a lungo del necessario può esporre l'organizzazione a rischi legali. Per questo motivo, la tua organizzazione potrebbe aver creato un criterio di eliminazione del documento per il tuo sito; per esempio, potrebbe essere necessario eliminare i documenti dell'attività generale cinque anni dopo la loro creazione.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p102">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time. However, retaining documents for longer than required can expose the organization to legal risk. For this reason, your organization may have created a document deletion policy for your site — for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="6cad3-109">A seconda dell'organizzazione, un criterio di eliminazione del documento può essere:</span><span class="sxs-lookup"><span data-stu-id="6cad3-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="6cad3-110">**Obbligatorio** Il proprietario di un sito non può escludere un criterio obbligatorio, che viene automaticamente applicato al sito.</span><span class="sxs-lookup"><span data-stu-id="6cad3-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="6cad3-111">**Predefinito** Un criterio predefinito è applicato al sito automaticamente, ma il proprietario del sito può:</span><span class="sxs-lookup"><span data-stu-id="6cad3-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="6cad3-112">Selezionare un altro criterio, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="6cad3-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="6cad3-113">Disattivare completamente il criterio, se non è rilevante ai fini del contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="6cad3-113">Opt out of the policy entirely if it is not relevant to the content in the site.</span></span>
    
- <span data-ttu-id="6cad3-114">**Né obbligatorio né predefinito** In questo caso, nessun criterio è applicato al sito automaticamente e il proprietario del sito deve eseguire determinate azioni per applicarne uno.</span><span class="sxs-lookup"><span data-stu-id="6cad3-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="6cad3-p103">Un criterio di eliminazione del documento può contenere più di una regola. Per esempio, una regola potrebbe definire l'eliminazione dei documenti dopo un anno dalla loro creazione, mentre un'altra regola potrebbe definire l'eliminazione dei documenti dopo un anno dall'ultima modifica apportata loro. Se un criterio contiene più di una regola, puoi selezionare quella più appropriata per il tuo sito. La regola di eliminazione verrà applicata a tutte le librerie all'interno del sito. Solo un criterio e una regola alla volta possono essere attivi in un sito. Come un criterio, anche una regola può essere impostata come predefinita, in modo che sia applicata automaticamente quando viene applicato il criterio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p103">A document deletion policy may contain more than one rule — for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified. If a policy contains more than one rule, you can select the rule that best applies to your site. The delete rule will be applied to all libraries within the site. Only one policy and one rule can be active in a site at one time. Like a policy, a rule can be set as default, so that it is applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="6cad3-p104">Infine, i criteri di eliminazione del documento vengono ereditati. Quando selezioni un criterio o una regola per il tuo sito, tale scelta viene ereditata da tutti i siti secondari, anche se il proprietario di un sito secondario può interrompere l'ereditarietà selezionando un criterio o una regola diversi. Quando selezioni un criterio o una regola, tieni presente il contenuto di eventuali siti secondari all'interno del tuo sito.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="6cad3-123">Visualizzare i criteri di eliminazione del documento disponibili in una raccolta siti</span><span class="sxs-lookup"><span data-stu-id="6cad3-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="6cad3-p105">La tua organizzazione può assegnare criteri diversi a raccolte siti diverse. A livello della raccolta siti, il proprietario di una raccolta siti può visualizzare tutti i criteri di eliminazione del documento disponibili per tale raccolta siti. I criteri possono essere stati resi disponibili per il modello della raccolta siti (e di conseguenza per tutte le raccolte siti create da quel modello) oppure per quella specifica raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="6cad3-127">Nel sito principale della raccolta siti, nell'angolo in alto a destra, scegliere **Impostazioni** [icona Gear] \> **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="6cad3-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="6cad3-128">In **criteri di eliminazione dei documenti**di **Amministrazione** \> raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="6cad3-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6cad3-p106">Il collegamento **criteri di eliminazione dei documenti** non verrà visualizzato a meno che non siano stati assegnati criteri alla raccolta siti. Inoltre, il collegamento non viene visualizzato subito dopo che i criteri sono stati assegnati al sito, ma può richiedere fino a 24 ore da quando i criteri vengono assegnati quando viene visualizzato il collegamento **criteri di eliminazione dei documenti** .</span><span class="sxs-lookup"><span data-stu-id="6cad3-p106">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="6cad3-131">In questa pagina puoi trovare:</span><span class="sxs-lookup"><span data-stu-id="6cad3-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="6cad3-p107">I criteri attualmente assegnati e le regole associate. Seleziona un criterio per visualizzare le regole nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="6cad3-134">Se presente, il criterio predefinito presenta l'opzione **Sì** nella colonna **predefinita**.</span><span class="sxs-lookup"><span data-stu-id="6cad3-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="6cad3-135">Se è stato assegnato un criterio **obbligatorio**, al di sotto dell'elenco viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="6cad3-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="6cad3-p108">Questo elenco è solo in modalità visualizzazione e consente al proprietario della raccolta siti di vedere tutti i criteri e le regole disponibili. Per informazioni sull'applicazione di un criterio, consulta la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Visualizzare i criteri di eliminazione dei documenti assegnati a una raccolta siti](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="6cad3-139">Applicare o rimuovere un criterio di eliminazione del documento per un sito</span><span class="sxs-lookup"><span data-stu-id="6cad3-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="6cad3-140">È possibile che la tua organizzazione abbia creato dei criteri che, in qualità di proprietario di un sito o di una raccolta siti, puoi sia applicare al tuo sito sia disattivare completamente.</span><span class="sxs-lookup"><span data-stu-id="6cad3-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="6cad3-141">Nell'angolo in alto a destra, scegliere **Impostazioni** [icona ingranaggi] \> **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="6cad3-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="6cad3-142">In **criteri di eliminazione dei documenti**di amministrazione \> del **sito** .</span><span class="sxs-lookup"><span data-stu-id="6cad3-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6cad3-p109">Il collegamento **criteri di eliminazione dei documenti** non verrà visualizzato a meno che non siano stati assegnati criteri alla raccolta siti. Inoltre, il collegamento non viene visualizzato subito dopo che i criteri sono stati assegnati al sito, ma può richiedere fino a 24 ore da quando i criteri vengono assegnati quando viene visualizzato il collegamento **criteri di eliminazione dei documenti** .</span><span class="sxs-lookup"><span data-stu-id="6cad3-p109">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="6cad3-145">Eseguire una di queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="6cad3-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="6cad3-146">**Per applicare un criterio** Selezionare un criterio \> selezionare una regola per il \> **salvataggio**di un criterio.</span><span class="sxs-lookup"><span data-stu-id="6cad3-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="6cad3-p110">Solo un criterio e una regola alla volta possono essere attivi in un sito. L'organizzazione può fornire più criteri e regole tra cui scegliere oppure metterne a disposizione solo uno.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Selezionare l'opzione criterio](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="6cad3-150">**Per rifiutare l'esclusione di un criterio** Scegliere **opt-out: do note Delete** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="6cad3-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="6cad3-p111">In qualità di proprietario del sito, puoi disattivare un criterio di eliminazione del documento se decidi che quel criterio non è applicabile al contenuto del sito. Tuttavia, non puoi disattivare un criterio che è stato contrassegnato come **obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p111">As a site owner, you can opt out of a document deletion policy if you determine that the policy is not applicable to the content in your site. However, you cannot opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Opzione opt-out](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="6cad3-154">I criteri di eliminazione del documento ignorano altri criteri</span><span class="sxs-lookup"><span data-stu-id="6cad3-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="6cad3-155">Un sito può utilizzare altri criteri per il mantenimento e l'eliminazione dei contenuti:</span><span class="sxs-lookup"><span data-stu-id="6cad3-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="6cad3-156">Criteri tipo di contenuto per la raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="6cad3-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="6cad3-157">Criteri di gestione delle informazioni per un elenco o una libreria.</span><span class="sxs-lookup"><span data-stu-id="6cad3-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="6cad3-p112">Se si applica un criterio di eliminazione dei documenti a un sito che già utilizza criteri del tipo di contenuto o criteri di gestione delle informazioni per un elenco o una raccolta, tali criteri vengono ignorati mentre il criterio di eliminazione del documento è attivo. Se altri criteri vengono ignorati, verrà visualizzato il messaggio "contenuto in questo sito utilizza i criteri di eliminazione dei documenti".</span><span class="sxs-lookup"><span data-stu-id="6cad3-p112">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect. If other policies are ignored, you will see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="6cad3-p113">Questo significa che dovresti pianificare un sito che utilizzi solo criteri destinati a contenuti strutturati (criteri di gestione delle informazioni e criteri tipo di contenuto) o contenuti non strutturati (criteri di eliminazione del documento) e non ad entrambi. Se disattivi il criterio di eliminazione del documento, l'errore segnalato dall'avviso non verrà visualizzato e continueranno a funzionare altri tipi di criteri.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p113">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both. If you opt out of a document deletion policy, the warning will not be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="6cad3-162">I criteri di eliminazione del documento non hanno alcun effetto sui criteri sito.</span><span class="sxs-lookup"><span data-stu-id="6cad3-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="6cad3-163">Determinare se i criteri tipo di contenuto vengono ignorati</span><span class="sxs-lookup"><span data-stu-id="6cad3-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="6cad3-p114">Se il sito utilizza criteri del tipo di contenuto e questo messaggio viene visualizzato, questi criteri non sono più in vigore. Per ripristinare i criteri dei tipi di contenuto, è possibile rimuovere il criterio di eliminazione dei documenti dal sito, come descritto in precedenza, se è disponibile un'opzione di disattivazione. Se non è possibile escludere l'opzione, i criteri di eliminazione dei documenti sono obbligatori ed è necessario contattare il responsabile della conformità nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p114">If your site was using content type policies and you now see this message, those policies are no longer in effect. To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available. If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="6cad3-167">Nell'angolo in alto a destra, scegliere **Impostazioni** [icona ingranaggi] \> **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="6cad3-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="6cad3-168">In \> **modelli di criteri tipo di contenuto** **Amministrazione sito** .</span><span class="sxs-lookup"><span data-stu-id="6cad3-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![Avviso sul sito in cui vengono utilizzati i criteri di eliminazione dei documenti](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="6cad3-170">Determinare se i criteri di gestione delle informazioni vengono ignorati</span><span class="sxs-lookup"><span data-stu-id="6cad3-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="6cad3-p115">Se il sito utilizza i criteri di gestione delle informazioni e il messaggio viene visualizzato, questi criteri non sono più in vigore. Per ripristinare i criteri di gestione delle informazioni, è possibile rimuovere il criterio di eliminazione dei documenti dal sito, come descritto in precedenza, se è disponibile un'opzione di disattivazione. Se non è possibile escludere l'opzione, i criteri di eliminazione dei documenti sono obbligatori ed è necessario contattare il responsabile della conformità nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cad3-p115">If your site was using information management policies and you now see this message, those policies are no longer in effect. To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available. If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="6cad3-174">Per un elenco o una raccolta, nelle impostazioni \> \*\*\*\* della \> **raccolta** \> schede della raccolta della barra multifunzione in **autorizzazioni e gestione** \> delle informazioni di gestione **delle impostazioni dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="6cad3-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![Avviso sul sito in cui vengono utilizzati i criteri di eliminazione dei documenti](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="6cad3-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cad3-176">See also</span></span>

[<span data-ttu-id="6cad3-177">Panoramica dei criteri di eliminazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="6cad3-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="6cad3-178">Creare un criterio di eliminazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="6cad3-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

