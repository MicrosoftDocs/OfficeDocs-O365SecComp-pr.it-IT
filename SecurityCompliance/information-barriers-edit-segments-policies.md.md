---
title: Modificare o rimuovere i criteri di barriera delle informazioni
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/24/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Informazioni su come modificare o rimuovere i criteri per le barriere informative.
ms.openlocfilehash: e6bed4df2329d426f86bd4cde07bdc7d1a2792cd
ms.sourcegitcommit: 7c48ce016fa9f45a3813467f7c5a2fd72f9b8f49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "35215649"
---
# <a name="edit-or-remove-information-barrier-policies-preview"></a><span data-ttu-id="6a658-103">Modificare o rimuovere i criteri di barriera delle informazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6a658-103">Edit or remove information barrier policies (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="6a658-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="6a658-104">Overview</span></span>

<span data-ttu-id="6a658-105">Dopo aver [definito i criteri di barriera delle informazioni](information-barriers-policies.md), potrebbe essere necessario apportare modifiche a tali criteri o ai segmenti di utenti, come parte della [risoluzione dei problemi](information-barriers-troubleshooting.md) o come manutenzione regolare.</span><span class="sxs-lookup"><span data-stu-id="6a658-105">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="6a658-106">Utilizzare questo articolo come guida.</span><span class="sxs-lookup"><span data-stu-id="6a658-106">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a658-107">Per eseguire le attività descritte in questo articolo, è necessario essere assegnati a un ruolo appropriato, ad esempio uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a658-107">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="6a658-108">-Microsoft 365 Enterprise Global Administrator</span><span class="sxs-lookup"><span data-stu-id="6a658-108">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="6a658-109">-Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="6a658-109">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="6a658-110">-Compliance Administrator</span><span class="sxs-lookup"><span data-stu-id="6a658-110">- Compliance Administrator</span></span><br/><span data-ttu-id="6a658-111">-IB Compliance Management (questo è un nuovo ruolo)</span><span class="sxs-lookup"><span data-stu-id="6a658-111">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="6a658-112">Per ulteriori informazioni sui prerequisiti per le barriere informative, vedere [prerequisiti (per i criteri barriera informativi)](information-barriers-policies.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="6a658-112">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="6a658-113">Assicurarsi di eseguire la [connessione a PowerShell di Office 365 Security & Compliance Center](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="6a658-113">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="6a658-114">Modificare gli attributi degli account utente</span><span class="sxs-lookup"><span data-stu-id="6a658-114">Edit user account attributes</span></span>

<span data-ttu-id="6a658-115">Utilizzare questa procedura per modificare gli attributi utilizzati per la segmentazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6a658-115">Use this procedure to edit attributes that are used for segmenting users.</span></span> 

<span data-ttu-id="6a658-116">Ad esempio, se si utilizza un attributo Department e uno o più account utente attualmente non dispongono di alcun valore elencato per Department, è necessario modificare tali account utente in modo da includere informazioni di reparto.</span><span class="sxs-lookup"><span data-stu-id="6a658-116">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> 

<span data-ttu-id="6a658-117">Gli attributi degli account utente vengono utilizzati per definire i segmenti in modo che i criteri di barriera delle informazioni possano essere assegnati.</span><span class="sxs-lookup"><span data-stu-id="6a658-117">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="6a658-118">Per visualizzare i dettagli relativi a un account utente specifico, ad esempio i valori degli attributi e i segmenti assegnati, utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity.</span><span class="sxs-lookup"><span data-stu-id="6a658-118">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> 

   <span data-ttu-id="6a658-119">Sintassi`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="6a658-119">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> 
    
   <span data-ttu-id="6a658-120">È possibile utilizzare qualsiasi valore che identifichi in modo univoco ogni utente, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID.</span><span class="sxs-lookup"><span data-stu-id="6a658-120">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> 
    
   <span data-ttu-id="6a658-121">Esempio:  `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="6a658-121">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> 
    
   <span data-ttu-id="6a658-122">In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan*e *alexw* per *Alex*.</span><span class="sxs-lookup"><span data-stu-id="6a658-122">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> 
    
   <span data-ttu-id="6a658-123">È inoltre possibile utilizzare questo cmdlet per un singolo utente: `Get-InformationBarrierRecipientStatus -Identity <value>`</span><span class="sxs-lookup"><span data-stu-id="6a658-123">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> 
    
2. <span data-ttu-id="6a658-124">Determinare l'attributo che si desidera modificare per i profili dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="6a658-124">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="6a658-125">Per ulteriori informazioni, fare riferimento agli [attributi per i criteri di barriera delle informazioni (Preview)](information-barriers-attributes.md) .</span><span class="sxs-lookup"><span data-stu-id="6a658-125">Refer to [Attributes for information barrier policies (Preview)](information-barriers-attributes.md) for more details.</span></span> 

3. <span data-ttu-id="6a658-126">Modificare uno o più account utente in modo da includere i valori dell'attributo selezionato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="6a658-126">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="6a658-127">A tale scopo, utilizzare una delle seguenti procedure:</span><span class="sxs-lookup"><span data-stu-id="6a658-127">To do this, use one of the following procedures:</span></span>

    - <span data-ttu-id="6a658-128">Per modificare un singolo account, vedere [aggiungere o aggiornare le informazioni sul profilo di un utente utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="6a658-128">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="6a658-129">Per modificare più account o utilizzare PowerShell per modificare un singolo account, vedere [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="6a658-129">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="6a658-130">Modifica di un segmento</span><span class="sxs-lookup"><span data-stu-id="6a658-130">Edit a segment</span></span>

<span data-ttu-id="6a658-131">Utilizzare questa procedura per modificare la definizione di un segmento di utenti.</span><span class="sxs-lookup"><span data-stu-id="6a658-131">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="6a658-132">Ad esempio, è possibile modificare il nome di un segmento o il filtro utilizzato per determinare chi è incluso nel segmento.</span><span class="sxs-lookup"><span data-stu-id="6a658-132">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="6a658-133">Per visualizzare tutti i segmenti esistenti, utilizzare il cmdlet **Get-OrganizationSegment** .</span><span class="sxs-lookup"><span data-stu-id="6a658-133">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="6a658-134">Sintassi`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="6a658-134">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="6a658-135">Verrà visualizzato un elenco di segmenti e dettagli per ognuno, ad esempio il tipo di segmento, il valore di UserGroupFilter, che ha creato o modificato l'oggetto, il GUID e così via.</span><span class="sxs-lookup"><span data-stu-id="6a658-135">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="6a658-136">Stampa o salvataggio dell'elenco dei segmenti per riferimento in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="6a658-136">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="6a658-137">Ad esempio, se si desidera modificare un segmento, è necessario conoscere il nome o il valore di identificazione (utilizzato con il parametro Identity).</span><span class="sxs-lookup"><span data-stu-id="6a658-137">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="6a658-138">Per modificare un segmento, utilizzare il cmdlet **set-OrganizationSegment** con il parametro **Identity** e i dettagli rilevanti.</span><span class="sxs-lookup"><span data-stu-id="6a658-138">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="6a658-139">Sintassi`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="6a658-139">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="6a658-140">Esempio:  `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="6a658-140">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="6a658-141">In questo esempio, per il segmento che ha il GUID *c96e0837-C232-4a8a-841E-ef45787d8fcd*, il nome del reparto è stato aggiornato in "HRDept".</span><span class="sxs-lookup"><span data-stu-id="6a658-141">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="6a658-142">Dopo aver completato la modifica dei segmenti per l'organizzazione, è possibile [definire](information-barriers-policies.md#part-2-define-information-barrier-policies) o [modificare](#edit-a-policy) i criteri di barriera delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="6a658-142">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="6a658-143">Modificare un criterio</span><span class="sxs-lookup"><span data-stu-id="6a658-143">Edit a policy</span></span>

1. <span data-ttu-id="6a658-144">Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .</span><span class="sxs-lookup"><span data-stu-id="6a658-144">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="6a658-145">Sintassi`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="6a658-145">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="6a658-146">Nell'elenco dei risultati, identificare il criterio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="6a658-146">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="6a658-147">Prendere nota del GUID e del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="6a658-147">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="6a658-148">Utilizzare il cmdlet **set-InformationBarrierPolicy** con un parametro **Identity** e specificare le modifiche che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="6a658-148">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="6a658-149">Ad esempio, si supponga che sia stato definito un criterio per bloccare il segmento di *ricerca* dalla comunicazione con i segmenti *Sales* and *Marketing* .</span><span class="sxs-lookup"><span data-stu-id="6a658-149">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="6a658-150">Il criterio è stato definito utilizzando il cmdlet seguente:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="6a658-150">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="6a658-151">Si supponga di voler cambiare la comunicazione in modo che gli utenti del segmento di *ricerca* possano comunicare solo con gli utenti del segmento *HR* .</span><span class="sxs-lookup"><span data-stu-id="6a658-151">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="6a658-152">Per apportare questa modifica, è possibile utilizzare questo cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="6a658-152">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="6a658-153">In questo esempio, "SegmentsBlocked" viene modificato in "SegmentsAllowed" e viene specificato il segmento *HR* .</span><span class="sxs-lookup"><span data-stu-id="6a658-153">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="6a658-154">Dopo aver completato la modifica di un criterio, accertarsi di applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6a658-154">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="6a658-155">(Vedere [Apply Information Barrier Policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)).</span><span class="sxs-lookup"><span data-stu-id="6a658-155">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="6a658-156">Impostare un criterio su stato inattivo</span><span class="sxs-lookup"><span data-stu-id="6a658-156">Set a policy to inactive status</span></span>

1. <span data-ttu-id="6a658-157">Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .</span><span class="sxs-lookup"><span data-stu-id="6a658-157">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="6a658-158">Sintassi`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="6a658-158">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="6a658-159">Nell'elenco dei risultati, identificare il criterio che si desidera modificare (o rimuovere).</span><span class="sxs-lookup"><span data-stu-id="6a658-159">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="6a658-160">Prendere nota del GUID e del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="6a658-160">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="6a658-161">Per impostare lo stato del criterio su inattivo, utilizzare il cmdlet **set-InformationBarrierPolicy** con un parametro Identity e il parametro state impostato su inattivo.</span><span class="sxs-lookup"><span data-stu-id="6a658-161">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="6a658-162">Sintassi`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="6a658-162">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="6a658-163">In questo esempio, viene impostato un criterio barriera informativo che include GUID *43c37853-EA10-4b90-a23d-ab8c9377247* su uno stato inattivo.</span><span class="sxs-lookup"><span data-stu-id="6a658-163">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="6a658-164">Per applicare le modifiche, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** .</span><span class="sxs-lookup"><span data-stu-id="6a658-164">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="6a658-165">Sintassi`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="6a658-165">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="6a658-166">Le modifiche vengono applicate dall'utente per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6a658-166">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="6a658-167">Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più).</span><span class="sxs-lookup"><span data-stu-id="6a658-167">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="6a658-168">(Come linee guida generali, è necessario circa un'ora per elaborare gli account utente di 5.000).</span><span class="sxs-lookup"><span data-stu-id="6a658-168">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="6a658-169">A questo punto, uno o più criteri barriera informazioni sono impostati sullo stato inattivo.</span><span class="sxs-lookup"><span data-stu-id="6a658-169">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="6a658-170">Da qui, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a658-170">From here, you can do any of the following:</span></span>
- <span data-ttu-id="6a658-171">Keep it as is (un criterio impostato su stato inattivo non ha alcun effetto sugli utenti)</span><span class="sxs-lookup"><span data-stu-id="6a658-171">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="6a658-172">Modificare un criterio</span><span class="sxs-lookup"><span data-stu-id="6a658-172">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="6a658-173">Rimozione di un criterio</span><span class="sxs-lookup"><span data-stu-id="6a658-173">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="6a658-174">Rimozione di un criterio</span><span class="sxs-lookup"><span data-stu-id="6a658-174">Remove a policy</span></span>

1. <span data-ttu-id="6a658-175">Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .</span><span class="sxs-lookup"><span data-stu-id="6a658-175">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="6a658-176">Sintassi`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="6a658-176">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="6a658-177">Nell'elenco dei risultati, identificare il criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="6a658-177">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="6a658-178">Prendere nota del GUID e del nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="6a658-178">Note the policy's GUID and name.</span></span> <span data-ttu-id="6a658-179">Verificare che il criterio sia impostato su stato inattivo.</span><span class="sxs-lookup"><span data-stu-id="6a658-179">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="6a658-180">Utilizzare il cmdlet **Remove-InformationBarrierPolicy** con un parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="6a658-180">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="6a658-181">Sintassi`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="6a658-181">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="6a658-182">Esempio: Supponiamo di voler rimuovere un criterio con GUID *43c37853-EA10-4b90-a23d-ab8c93772471*.</span><span class="sxs-lookup"><span data-stu-id="6a658-182">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="6a658-183">A tale scopo, viene utilizzato il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="6a658-183">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="6a658-184">Quando richiesto, confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="6a658-184">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="6a658-185">Ripetere i passaggi 1-2 per ogni criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="6a658-185">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="6a658-186">Una volta terminata la rimozione dei criteri, applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6a658-186">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="6a658-187">A tale scopo, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** .</span><span class="sxs-lookup"><span data-stu-id="6a658-187">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="6a658-188">Sintassi`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="6a658-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="6a658-189">Le modifiche vengono applicate dall'utente per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6a658-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="6a658-190">Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più).</span><span class="sxs-lookup"><span data-stu-id="6a658-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="6a658-191">Arrestare un'applicazione di criteri</span><span class="sxs-lookup"><span data-stu-id="6a658-191">Stop a policy application</span></span>

<span data-ttu-id="6a658-192">Se dopo aver avviato l'applicazione di criteri di barriera delle informazioni si desidera impedire l'applicazione di tali criteri, utilizzare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="6a658-192">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="6a658-193">Tenere presente che richiederà circa 30-35 minuti per l'avvio del processo.</span><span class="sxs-lookup"><span data-stu-id="6a658-193">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="6a658-194">Per visualizzare lo stato dell'applicazione del criterio barriera alle informazioni più recente, utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="6a658-194">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="6a658-195">Sintassi`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="6a658-195">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="6a658-196">Tenere presente il GUID dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6a658-196">Note the application's GUID.</span></span>

2. <span data-ttu-id="6a658-197">Utilizzare il cmdlet **Stop-InformationBarrierPoliciesApplication** con un parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="6a658-197">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="6a658-198">Sintassi`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="6a658-198">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="6a658-199">Esempio:  `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="6a658-199">Example: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

    <span data-ttu-id="6a658-200">In questo esempio viene interrotto l'applicazione dei criteri di barriera delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="6a658-200">In this example, we are stopping information barrier policies from being applied.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6a658-201">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="6a658-201">Related articles</span></span>

[<span data-ttu-id="6a658-202">Ottenere una panoramica delle barriere informative</span><span class="sxs-lookup"><span data-stu-id="6a658-202">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="6a658-203">Definire i criteri per le barriere informative (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6a658-203">Define policies for information barriers (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="6a658-204">Per ulteriori informazioni, vedere barriere informative in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a658-204">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="6a658-205">Attributi per i criteri di barriera delle informazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6a658-205">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="6a658-206">Risoluzione dei problemi relativi alle informazioni sugli ostacoli (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6a658-206">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
