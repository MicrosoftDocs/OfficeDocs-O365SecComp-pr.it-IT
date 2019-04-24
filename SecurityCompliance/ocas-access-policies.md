---
title: Criteri di accesso in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: I criteri di accesso alla sicurezza di Office 365 cloud app consentono il monitoraggio e il controllo in tempo reale sull'accesso alle app cloud basate su utente, posizione, dispositivo e app. È possibile creare criteri di accesso per qualsiasi dispositivo, inclusi i dispositivi che non sono stati aggiunti al dominio e non gestiti da Windows Intune mediante l'implementazione di certificati client su dispositivi gestiti o utilizzando certificati esistenti, ad esempio i certificati MDM di terze parti. Ad esempio, è possibile distribuire i certificati client ai dispositivi gestiti e quindi bloccare l'accesso da dispositivi privi di un certificato.
ms.openlocfilehash: 5e8b8fa293420bc9ff3616daf288b8e02a2eb768
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263006"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="061cd-105">Criteri di accesso in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="061cd-105">Access policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="061cd-106">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="061cd-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="061cd-107">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="061cd-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="061cd-108">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="061cd-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="061cd-109">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="061cd-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="061cd-110">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="061cd-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="061cd-111">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="061cd-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="061cd-112">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="061cd-112">You are here!</span></span>  <br/> [<span data-ttu-id="061cd-113">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="061cd-113">Next step</span></span>](group-your-ip-addresses-in-ocas.md) <br/> |[<span data-ttu-id="061cd-114">Iniziare a utilizzare</span><span class="sxs-lookup"><span data-stu-id="061cd-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="061cd-115">I criteri di accesso alla sicurezza di Office 365 cloud app consentono il monitoraggio e il controllo in tempo reale sull'accesso alle app cloud basate su utente, posizione, dispositivo e app.</span><span class="sxs-lookup"><span data-stu-id="061cd-115">Office 365 Cloud App Security access policies enable real-time monitoring and control over access to cloud apps based on user, location, device, and app.</span></span> <span data-ttu-id="061cd-116">È possibile creare criteri di accesso per qualsiasi dispositivo, inclusi i dispositivi che non sono stati aggiunti al dominio e non gestiti da Windows Intune mediante l'implementazione di certificati client su dispositivi gestiti o utilizzando certificati esistenti, ad esempio i certificati MDM di terze parti.</span><span class="sxs-lookup"><span data-stu-id="061cd-116">You can create access policies for any device, including devices that aren't domain joined, and not managed by Windows Intune by rolling out client certificates to managed devices or by using existing certificates, such as third-party MDM certificates.</span></span> <span data-ttu-id="061cd-117">Ad esempio, è possibile distribuire i certificati client ai dispositivi gestiti e quindi bloccare l'accesso da dispositivi privi di un certificato.</span><span class="sxs-lookup"><span data-stu-id="061cd-117">For example, you can deploy client certificates to managed devices, and then block access from devices without a certificate.</span></span>

<span data-ttu-id="061cd-118">Invece di consentire o bloccare completamente l'accesso, con i [criteri](ocas-session-policies.md) di sessione è possibile consentire l'accesso durante il monitoraggio della sessione e/o limitare le attività specifiche della sessione.</span><span class="sxs-lookup"><span data-stu-id="061cd-118">Instead of allowing or blocking access completely, with [session policies](ocas-session-policies.md) you can allow access while monitoring the session and/or limit specific session activities.</span></span>

## <a name="prerequisites-to-using-access-policies"></a><span data-ttu-id="061cd-119">Prerequisiti per l'utilizzo dei criteri di accesso</span><span class="sxs-lookup"><span data-stu-id="061cd-119">Prerequisites to using access policies</span></span>

- <span data-ttu-id="061cd-120">Licenza P1 di Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="061cd-120">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="061cd-121">Le app rilevanti devono essere [distribuite con il controllo delle app di accesso condizionale](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span><span class="sxs-lookup"><span data-stu-id="061cd-121">The relevant apps should be [deployed with Conditional Access App Control](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span></span>

- <span data-ttu-id="061cd-122">un [criterio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) di accesso condizionale di Azure ad dovrebbe essere sul posto che reindirizza gli utenti a Office 365 Cloud App Security, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="061cd-122">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security, as described below.</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="061cd-123">Creare un criterio di accesso condizionale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="061cd-123">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="061cd-124">I criteri di accesso condizionale di Azure Active Directory e i criteri di sessione di sicurezza cloud app funzionano in tandem per esaminare ogni sessione utente e prendere decisioni sui criteri per ogni app.</span><span class="sxs-lookup"><span data-stu-id="061cd-124">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app.</span></span> <span data-ttu-id="061cd-125">Per impostare un criterio di accesso condizionale in Azure Active Directory, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="061cd-125">To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="061cd-126">Configurare un [criterio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) di accesso condizionale di Azure ad con le assegnazioni per l'utente o il gruppo di utenti e l'app che si desidera controllare con il controllo dell'applicazione di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="061cd-126">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users and the app you want to control with Conditional Access App Control.</span></span><br><span data-ttu-id="061cd-127">Nota: sono interessati da questo criterio solo [le app distribuite con il controllo](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) delle app con accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="061cd-127">NOTE: Only apps that were [deployed with Conditional Access App Control](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) will be affected by this policy.</span></span>

2. <span data-ttu-id="061cd-128">instradare gli utenti a Office 365 Cloud app Security selezionando la casella di **controllo usa accesso condizionale** per le restrizioni applicate in **Session**.</span><span class="sxs-lookup"><span data-stu-id="061cd-128">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** under **Session**.</span></span>

## <a name="create-a-cloud-app-security-access-policy"></a><span data-ttu-id="061cd-129">Creare un criterio di accesso alla sicurezza delle app Cloud</span><span class="sxs-lookup"><span data-stu-id="061cd-129">Create a Cloud App Security access policy</span></span>

<span data-ttu-id="061cd-130">Per creare un nuovo criterio di accesso, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="061cd-130">To create a new access policy, follow this procedure:</span></span>

1. <span data-ttu-id="061cd-131">Nel portale selezionare **controllo** seguito dai **criteri**.</span><span class="sxs-lookup"><span data-stu-id="061cd-131">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="061cd-132">Nella pagina **criteri** fare clic su **Crea criterio** e selezionare **criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="061cd-132">In the **Policies** page, click **Create policy** and select **Access policy**.</span></span>

3. <span data-ttu-id="061cd-133">Nella finestra **criteri** di accesso assegnare un nome per il criterio, ad esempio *blocca l'accesso da dispositivi non gestiti*.</span><span class="sxs-lookup"><span data-stu-id="061cd-133">In the **Access policy** window, assign a name for your policy, such as *Block access from unmanaged devices*.</span></span>

4. <span data-ttu-id="061cd-134">Nelle **attività corrispondenti a tutta la sezione seguente** , in **origine attività**, selezionare filtri attività aggiuntivi da applicare al criterio.</span><span class="sxs-lookup"><span data-stu-id="061cd-134">In the **Activities matching all of the following** section, Under **Activity source**, select additional activity filters to apply to the policy.</span></span> <span data-ttu-id="061cd-135">I filtri includono le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="061cd-135">Filters include the following options:</span></span>
    
    - <span data-ttu-id="061cd-136">**Tag del dispositivo**: utilizzare questo filtro per identificare i dispositivi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="061cd-136">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="061cd-137">**Posizione**: utilizzare questo filtro per identificare le posizioni sconosciute (e quindi rischiose).</span><span class="sxs-lookup"><span data-stu-id="061cd-137">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="061cd-138">**Indirizzo IP**: utilizzare questo filtro per filtrare gli indirizzi IP o utilizzare i tag degli indirizzi IP assegnati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="061cd-138">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="061cd-139">**Tag dell'agente utente**: utilizzare questo filtro per abilitare l'euristica per identificare le app per dispositivi mobili e desktop.</span><span class="sxs-lookup"><span data-stu-id="061cd-139">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps.</span></span> <span data-ttu-id="061cd-140">Questo filtro può essere impostato su uguale o diverso.</span><span class="sxs-lookup"><span data-stu-id="061cd-140">This filter can be set to equals or does not equal.</span></span> <span data-ttu-id="061cd-141">I valori devono essere testati con le app per dispositivi mobili e desktop per ogni app cloud.</span><span class="sxs-lookup"><span data-stu-id="061cd-141">The values should be tested against your mobile and desktop apps for each cloud app.</span></span>

5. <span data-ttu-id="061cd-142">In **azioni**, selezionare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="061cd-142">Under **Actions**, select one of the following options:</span></span>
    
    - <span data-ttu-id="061cd-143">**Consenti**: impostare questa azione per consentire in modo esplicito l'accesso in base ai filtri di criteri impostati.</span><span class="sxs-lookup"><span data-stu-id="061cd-143">**Allow**: Set this action to explicitly allow access according to the policy filters you set.</span></span>
    
    - <span data-ttu-id="061cd-144">**Blocca**: impostare questa azione per bloccare in modo esplicito l'accesso in base ai filtri di criteri impostati.</span><span class="sxs-lookup"><span data-stu-id="061cd-144">**Block**: Set this action to explicitly block access according to the policy filters you set.</span></span>

6. <span data-ttu-id="061cd-145">È possibile **creare un avviso per ogni evento corrispondente con la gravità del criterio**e impostare un limite di avviso e selezionare se si desidera che l'avviso venga inviato come un messaggio di posta elettronica, un SMS o entrambi.</span><span class="sxs-lookup"><span data-stu-id="061cd-145">You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.</span></span>

## <a name="next-steps"></a><span data-ttu-id="061cd-146">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="061cd-146">Next steps</span></span>

- [<span data-ttu-id="061cd-147">Raggruppare gli indirizzi IP per semplificare la gestione in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="061cd-147">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)