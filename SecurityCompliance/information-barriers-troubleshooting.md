---
title: Risoluzione dei problemi di barriere informative
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare questo articolo come guida per la risoluzione dei problemi relativi alle barriere informative.
ms.openlocfilehash: b37585469ec8bb299b7976f8a330f4c6b29e3f95
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668309"
---
# <a name="troubleshooting-information-barriers-preview"></a><span data-ttu-id="fabb9-103">Risoluzione dei problemi relativi alle informazioni sugli ostacoli (anteprima)</span><span class="sxs-lookup"><span data-stu-id="fabb9-103">Troubleshooting information barriers (Preview)</span></span>

<span data-ttu-id="fabb9-104">Gli ostacoli alle informazioni consentono all'organizzazione di rimanere conforme ai requisiti legali e ai regolamenti di settore.</span><span class="sxs-lookup"><span data-stu-id="fabb9-104">Information barriers can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="fabb9-105">Ad esempio, con barriere informative, è possibile limitare le comunicazioni tra gruppi specifici di utenti per evitare conflitti di interesse o altri problemi.</span><span class="sxs-lookup"><span data-stu-id="fabb9-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="fabb9-106">Per ulteriori informazioni, vedere [barriere informative (Preview)](information-barriers.md).</span><span class="sxs-lookup"><span data-stu-id="fabb9-106">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span>

<span data-ttu-id="fabb9-107">In questo articolo vengono fornite indicazioni che è possibile utilizzare per ottenere risposte a domande o risolvere problemi che possono verificarsi con barriere informative.</span><span class="sxs-lookup"><span data-stu-id="fabb9-107">This article provides guidance you can use to get answers to questions or resolve issues that may arise with information barriers.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="fabb9-108">Prima di iniziare...</span><span class="sxs-lookup"><span data-stu-id="fabb9-108">Before you begin...</span></span>

<span data-ttu-id="fabb9-109">Per eseguire le attività descritte in questo articolo, è necessario essere assegnati a un ruolo appropriato, ad esempio uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="fabb9-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span>
- <span data-ttu-id="fabb9-110">Amministratore globale di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fabb9-110">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="fabb9-111">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="fabb9-111">Office 365 Global Administrator</span></span>
- <span data-ttu-id="fabb9-112">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="fabb9-112">Compliance Administrator</span></span>
- <span data-ttu-id="fabb9-113">IB Compliance Management (questo è un nuovo ruolo)</span><span class="sxs-lookup"><span data-stu-id="fabb9-113">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="fabb9-114">Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere Permissions [in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fabb9-114">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="fabb9-115">Per ulteriori informazioni sui prerequisiti per le barriere informative, vedere [prerequisiti (per i criteri barriera informativi)](information-barriers-policies.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="fabb9-115">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span>

<span data-ttu-id="fabb9-116">Assicurarsi inoltre di [connettersi a PowerShell di Office 365 Security & Compliance Center](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="fabb9-116">Also, make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a><span data-ttu-id="fabb9-117">Problema: persone inaspettatamente bloccate dalla comunicazione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fabb9-117">Issue: People are unexpectedly blocked from communicating in Microsoft Teams</span></span> 

<span data-ttu-id="fabb9-118">In questo caso, gli utenti segnalano problemi imprevisti che comunicano in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="fabb9-118">In this case, people are reporting unexpected issues communicating in Microsoft Teams.</span></span> <span data-ttu-id="fabb9-119">Esempi:</span><span class="sxs-lookup"><span data-stu-id="fabb9-119">Examples:</span></span>
- <span data-ttu-id="fabb9-120">Un utente non è in grado di trovare o comunicare con un altro utente in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="fabb9-120">A user is unable to find or communicate with another user in Microsoft Teams.</span></span>
- <span data-ttu-id="fabb9-121">Un utente non può visualizzare o selezionare un altro utente in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="fabb9-121">A user cannot see or select another user in Microsoft Teams.</span></span>
- <span data-ttu-id="fabb9-122">Un utente può vedere, ma non è in grado di inviare messaggi a, un altro utente in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="fabb9-122">A user can see, but cannot send messages to, another user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="fabb9-123">cosa fare</span><span class="sxs-lookup"><span data-stu-id="fabb9-123">What to do</span></span>

1. <span data-ttu-id="fabb9-124">Determinare se gli utenti sono coinvolti in un criterio barriera informativo.</span><span class="sxs-lookup"><span data-stu-id="fabb9-124">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="fabb9-125">A tale scopo, utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="fabb9-125">To do this, use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    <span data-ttu-id="fabb9-126">La sintassi è`Get-InformationBarrierRecipientStatus -Identity`</span><span class="sxs-lookup"><span data-stu-id="fabb9-126">The syntax is `Get-InformationBarrierRecipientStatus -Identity`</span></span>

    <span data-ttu-id="fabb9-127">È possibile utilizzare qualsiasi valore di identità che identifichi in modo univoco ogni destinatario, ad esempio nome, alias, nome distinto (DN), DN canonico, indirizzo di posta elettronica o GUID.</span><span class="sxs-lookup"><span data-stu-id="fabb9-127">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>

    <span data-ttu-id="fabb9-128">Esempio:  `Get-InformationBarrierRecipientStatus -Identity meganb`</span><span class="sxs-lookup"><span data-stu-id="fabb9-128">Example: `Get-InformationBarrierRecipientStatus -Identity meganb`</span></span>

    <span data-ttu-id="fabb9-129">In questo esempio viene utilizzato un alias (*meganb*) per il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="fabb9-129">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="fabb9-130">Questo cmdlet restituirà informazioni che indicano se l'utente è influenzato da un criterio barriera informativo.</span><span class="sxs-lookup"><span data-stu-id="fabb9-130">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="fabb9-131">(Cercare \* ExoPolicyId: \<GUID>.)</span><span class="sxs-lookup"><span data-stu-id="fabb9-131">(Look for \*ExoPolicyId: \<GUID>.)</span></span>

    <span data-ttu-id="fabb9-132">Se gli utenti non sono inclusi nei criteri di barriera delle informazioni, contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="fabb9-132">If the users are not included in information barrier policies, contact support.</span></span> <span data-ttu-id="fabb9-133">In caso contrario, passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="fabb9-133">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="fabb9-134">Scoprire quali segmenti sono inclusi in un criterio barriera informativo.</span><span class="sxs-lookup"><span data-stu-id="fabb9-134">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="fabb9-135">A tale scopo, utilizzare il `Get-InformationBarrierPolicy` cmdlet con il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="fabb9-135">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> <span data-ttu-id="fabb9-136">Utilizzare i dettagli, ad esempio il GUID dei criteri (ExoPolicyId) ricevuto durante il passaggio precedente, come valore di identità.</span><span class="sxs-lookup"><span data-stu-id="fabb9-136">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>

    <span data-ttu-id="fabb9-137">Esempio:  `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span><span class="sxs-lookup"><span data-stu-id="fabb9-137">Example: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span></span>

    <span data-ttu-id="fabb9-138">In questo esempio, vengono fornite informazioni dettagliate sul criterio barriera informativo con ExoPolicyId *b42c3d0f-49E9-4506-a0a5-bf2853b5df6f*.</span><span class="sxs-lookup"><span data-stu-id="fabb9-138">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>
    
    <span data-ttu-id="fabb9-139">Dopo aver eseguito il cmdlet, nei risultati cercare i valori **AssignedSegment**, **SegmentsAllowed**e **SegmentsBlocked** .</span><span class="sxs-lookup"><span data-stu-id="fabb9-139">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="fabb9-140">Esempio: dopo aver eseguito `Get-InformationBarrierPolicy` il cmdlet, è stato riportato quanto segue nell'elenco dei risultati:</span><span class="sxs-lookup"><span data-stu-id="fabb9-140">Example: After running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="fabb9-141">In questo caso, è possibile osservare che un criterio di barriera informativo interessa le persone che si trovano nei segmenti Sales and Research.</span><span class="sxs-lookup"><span data-stu-id="fabb9-141">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="fabb9-142">In questo caso, agli utenti nelle vendite viene impedito di comunicare con gli utenti nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="fabb9-142">In this case, people in Sales are prevented from communicating with people in Research.</span></span> <span data-ttu-id="fabb9-143">Se questo sembra corretto, le barriere informative funzionano come previsto.</span><span class="sxs-lookup"><span data-stu-id="fabb9-143">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="fabb9-144">In caso contrario, procedere al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="fabb9-144">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="fabb9-145">Verificare che i segmenti siano definiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="fabb9-145">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="fabb9-146">A tale scopo, utilizzare il `Get-OrganizationSegment` cmdlet ed esaminare l'elenco dei risultati.</span><span class="sxs-lookup"><span data-stu-id="fabb9-146">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    <span data-ttu-id="fabb9-147">Per visualizzare i dettagli di un segmento specifico, utilizzare `Get-OrganizationSegment` il cmdlet con un parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="fabb9-147">To view details for a specific segment, use the `Get-OrganizationSegment` cmdlet with an Identity parameter.</span></span> 

    <span data-ttu-id="fabb9-148">Esempio:  `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span><span class="sxs-lookup"><span data-stu-id="fabb9-148">Example: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span></span>

    <span data-ttu-id="fabb9-149">In questo esempio vengono riportate informazioni sul segmento con GUID *c96e0837-C232-4a8a-841E-ef45787d8fcd*.</span><span class="sxs-lookup"><span data-stu-id="fabb9-149">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>

    <span data-ttu-id="fabb9-150">Esaminare i dettagli del segmento.</span><span class="sxs-lookup"><span data-stu-id="fabb9-150">Review the details for the segment.</span></span> <span data-ttu-id="fabb9-151">Se necessario, [modificare un segmento](information-barriers-policies.md#edit-a-segment)e quindi riutilizzare il `Start-InformationBarrierPoliciesApplication` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fabb9-151">If necessary, [edit a segment](information-barriers-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="fabb9-152">Se si verificano ancora problemi con il criterio barriera informativo, contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="fabb9-152">If you are still having issues with your information barrier policy, contact support.</span></span>
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="fabb9-153">Problema: il processo di applicazione barriera alle informazioni richiede troppo tempo</span><span class="sxs-lookup"><span data-stu-id="fabb9-153">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="fabb9-154">Dopo aver eseguito il cmdlet **Start-InformationBarrierPoliciesApplication** , il processo richiede molto tempo per il completamento.</span><span class="sxs-lookup"><span data-stu-id="fabb9-154">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="fabb9-155">cosa fare</span><span class="sxs-lookup"><span data-stu-id="fabb9-155">What to do</span></span>

1. <span data-ttu-id="fabb9-156">Tenere presente che, quando si esegue il cmdlet applicazione criteri, i criteri di barriera delle informazioni vengono applicati (o rimossi), utente per utente, per tutti gli account nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fabb9-156">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="fabb9-157">Se si dispone di numerosi utenti, sarà necessario un po' di tempo per elaborarli.</span><span class="sxs-lookup"><span data-stu-id="fabb9-157">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="fabb9-158">(Come linee guida generali, è necessario circa un'ora per elaborare gli account utente di 5.000).</span><span class="sxs-lookup"><span data-stu-id="fabb9-158">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span> 

2. <span data-ttu-id="fabb9-159">Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** per verificare lo stato.</span><span class="sxs-lookup"><span data-stu-id="fabb9-159">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status.</span></span>

    <span data-ttu-id="fabb9-160">Sintassi`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="fabb9-160">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="fabb9-161">Per visualizzare lo stato di tutte le applicazioni dei criteri barriera delle informazioni, utilizzare`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="fabb9-161">To display status for all information barrier policy applications, use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span>

    <span data-ttu-id="fabb9-162">Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.</span><span class="sxs-lookup"><span data-stu-id="fabb9-162">This will display information about whether policy application completed, failed, or is in progress..</span></span>

3. <span data-ttu-id="fabb9-163">A seconda dei risultati del passaggio 2, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fabb9-163">Depending on the results of step 2, take one of the following steps:</span></span>

    - <span data-ttu-id="fabb9-164">Se l'applicazione non è stata avviata e sono passati più di 45 minuti dal momento in cui è stato eseguito il cmdlet **Start-InformationBarrierPoliciesApplication** , esaminare il log di controllo per verificare se sono presenti errori nelle definizioni dei criteri o per un altro motivo per cui l' l'applicazione non è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="fabb9-164">If the application has not started, and it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span>

    - <span data-ttu-id="fabb9-165">Se l'applicazione ha avuto esito negativo, esaminare i segmenti e i criteri.</span><span class="sxs-lookup"><span data-stu-id="fabb9-165">If the application has failed, review your segments and policies.</span></span> <span data-ttu-id="fabb9-166">Se necessario, [modificare i segmenti](information-barriers-policies.md#edit-a-segment) e/o [modificare i criteri](information-barriers-policies.md#edit-a-policy), quindi eseguire di nuovo il cmdlet **Start-InformationBarrierPoliciesApplication** .</span><span class="sxs-lookup"><span data-stu-id="fabb9-166">If necessary, [edit segments](information-barriers-policies.md#edit-a-segment) and/or [edit policies](information-barriers-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>

    - <span data-ttu-id="fabb9-167">Se l'applicazione è ancora in corso, è necessario più tempo per il completamento.</span><span class="sxs-lookup"><span data-stu-id="fabb9-167">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="fabb9-168">Se sono stati diversi giorni, contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="fabb9-168">If it has been several days, contact support.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fabb9-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fabb9-169">Related topics</span></span>

[<span data-ttu-id="fabb9-170">Definire i criteri per le barriere informative in Microsoft Teams (anteprima)</span><span class="sxs-lookup"><span data-stu-id="fabb9-170">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="fabb9-171">Barriere informative (anteprima)</span><span class="sxs-lookup"><span data-stu-id="fabb9-171">Information barriers (Preview)</span></span>](information-barriers.md)



