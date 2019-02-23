---
title: Distribuire Controllo app per l'accesso condizionale per le app di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Seguire questa procedura per configurare le app di Azure AD Office 365 in modo che siano controllate da Office 365 cloud app Security Conditional Access App Control.
ms.openlocfilehash: cfb3d885fdfaf0e4698b1f8f9a0e13baacf43f66
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221056"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a><span data-ttu-id="3a074-103">Distribuire Controllo app per l'accesso condizionale per le app di Office 365</span><span class="sxs-lookup"><span data-stu-id="3a074-103">Deploy Conditional Access App Control for Office 365 apps</span></span>

|<span data-ttu-id="3a074-104">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3a074-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="3a074-105">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3a074-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="3a074-106">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3a074-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="3a074-107">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3a074-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="3a074-108">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="3a074-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="3a074-109">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="3a074-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="3a074-110">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="3a074-110">You are here!</span></span>  <br/> [<span data-ttu-id="3a074-111">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3a074-111">Next step</span></span>](ocas-session-policies.md) <br/> |[<span data-ttu-id="3a074-112">Iniziare a utilizzare</span><span class="sxs-lookup"><span data-stu-id="3a074-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="3a074-113">Seguire questa procedura per configurare le app di Azure AD Office 365 in modo che siano controllate da Office 365 cloud app Security Conditional Access App Control.</span><span class="sxs-lookup"><span data-stu-id="3a074-113">Follow these steps to configure Azure AD Office 365 apps to be controlled by Office 365 Cloud App Security Conditional Access App Control.</span></span>

<span data-ttu-id="3a074-114">**Passaggio 1: [creare un criterio di test di accesso condizionale di Azure ad](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span><span class="sxs-lookup"><span data-stu-id="3a074-114">**Step 1: [Create an Azure AD conditional access test policy](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span></span>

<span data-ttu-id="3a074-115">**Passaggio 2: [accedere con l'ambito di un utente al criterio nelle app](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span><span class="sxs-lookup"><span data-stu-id="3a074-115">**Step 2: [Sign in with a user scoped to the policy in the apps](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span></span>

<span data-ttu-id="3a074-116">**Passaggio 3: se non è stato selezionato un criterio di protezione delle app cloud incorporato in Azure AD o se si desidera applicare i criteri a un'app non in primo piano, [configurare i controlli avanzati nel portale di cloud app Security](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span><span class="sxs-lookup"><span data-stu-id="3a074-116">**Step 3: If you did not select a built-in Cloud App Security policy in Azure AD or if you want to apply the policy to a non-featured app, [Configure advanced controls in the Cloud App Security portal](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span></span>

<span data-ttu-id="3a074-117">**Passaggio 4: [testare la distribuzione](#step-4-test-the-deployment)**</span><span class="sxs-lookup"><span data-stu-id="3a074-117">**Step 4: [Test the deployment](#step-4-test-the-deployment)**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a074-118">per distribuire il controllo delle app di accesso condizionale per le app di office 365, è necessaria una [licenza valida per Azure ad Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) e una licenza di sicurezza per l'app Cloud di office 365.</span><span class="sxs-lookup"><span data-stu-id="3a074-118">To deploy Conditional Access App Control for Office 365 apps, you need a valid [license for Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) as well as a Office 365 Cloud App Security license.</span></span>

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a><span data-ttu-id="3a074-119">Passaggio 1: creare un criterio di test di accesso condizionale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="3a074-119">Step 1: Create an Azure AD conditional access test policy</span></span> 

1. <span data-ttu-id="3a074-120">In Azure Active Directory, in **sicurezza**, fare clic su **accesso condizionale**.</span><span class="sxs-lookup"><span data-stu-id="3a074-120">In Azure Active Directory, under **Security**, click on **Conditional access**.</span></span>

2. <span data-ttu-id="3a074-121">Fare clic su **nuovo criterio** e creare un nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="3a074-121">Click **New policy** and create a new policy.</span></span>

3. <span data-ttu-id="3a074-122">Nei criteri di TEST, in **utenti**, assegnare un utente o un utente di test che può essere utilizzato per l'accesso iniziale e la verifica.</span><span class="sxs-lookup"><span data-stu-id="3a074-122">In the TEST policy, under **Users**, assign a test user or user that can be used for an initial sign-on and verification.</span></span>

4. <span data-ttu-id="3a074-123">Nei criteri di TEST, in **app Cloud**, assegnare le app che si desidera controllare con il controllo di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="3a074-123">In the TEST policy, under **Cloud app**, assign the apps you want to control with Conditional Access App Control.</span></span>

5. <span data-ttu-id="3a074-p101">In **Session**impostare il criterio per l'utilizzo di uno dei criteri predefiniti, **monitorare solo** o bloccare i **download**. Oppure selezionare **Usa criteri** personalizzati per impostare criteri avanzati nel portale cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="3a074-p101">Under **Session**, set the policy to use either of the built-in policies, **Monitor only** or **Block downloads**. Or select **Use custom policy** to set an advanced policy in the Cloud App Security portal.</span></span>

6. <span data-ttu-id="3a074-126">Aggiungere tutte le **assegnazioni di condizioni** applicabili o i **controlli** di concessione (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="3a074-126">Add any applicable **Condition assignments** or **Grant controls** (optional).</span></span>

> ![Accesso condizionale di Azure AD](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a><span data-ttu-id="3a074-128">Passaggio 2: accedere con l'ambito di un utente al criterio nelle app</span><span class="sxs-lookup"><span data-stu-id="3a074-128">Step 2: Sign in with a user scoped to the policy in the apps</span></span> 

<span data-ttu-id="3a074-p102">Dopo aver creato il criterio, eseguire l'accesso a ogni applicazione configurata in tale criterio. Assicurarsi di accedere utilizzando un utente configurato nel criterio. Assicurarsi di disconnettersi prima delle sessioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="3a074-p102">After you've created the policy, sign in to each app configured in that policy. Make sure you sign in using a user configured in the policy. Make sure to first sign out of existing sessions.</span></span>

<span data-ttu-id="3a074-p103">Cloud app Security consentirà di sincronizzare i dettagli dei criteri ai server per ogni nuova applicazione a cui accedi. Questo potrebbe richiedere fino a un minuto.</span><span class="sxs-lookup"><span data-stu-id="3a074-p103">Cloud App Security will sync your policy details to its servers for each new app you log in to. This may take up to one minute.</span></span>

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a><span data-ttu-id="3a074-134">Passaggio 3: configurare i controlli avanzati nel cloud app Security Portal</span><span class="sxs-lookup"><span data-stu-id="3a074-134">Step 3: Configure advanced controls in the Cloud App Security portal</span></span> 

<span data-ttu-id="3a074-135">Le istruzioni sopra riportate consentono di creare un criterio di protezione delle app cloud incorporato per le app in primo piano in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3a074-135">The instructions above helped you create a built-in Cloud App Security policy for featured apps directly in Azure AD.</span></span>

<span data-ttu-id="3a074-136">per configurare un criterio avanzato, creare un criterio di [accesso](ocas-access-policies.md) o un [criterio](ocas-session-policies.md) di sessione nel portale di Office 365 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="3a074-136">To configure an advanced policy, create an [access policy](ocas-access-policies.md) or a [session policy](ocas-session-policies.md) in the Office 365 Cloud App Security portal.</span></span>

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a><span data-ttu-id="3a074-137">Per identificare i dispositivi che utilizzano i certificati client (facoltativo):</span><span class="sxs-lookup"><span data-stu-id="3a074-137">To identify devices using client certificates (this is optional):</span></span>

1. <span data-ttu-id="3a074-138">Passare al COG impostazioni e scegliere **identificazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="3a074-138">Go to the settings cog and choose **Device identification**.</span></span>

2. <span data-ttu-id="3a074-139">Caricare uno o più certificati radice o intermedi.</span><span class="sxs-lookup"><span data-stu-id="3a074-139">Upload one or more root or intermediate certificates.</span></span>

3. <span data-ttu-id="3a074-140">Dopo aver caricato il certificato, è possibile creare criteri di accesso e criteri di sessione basati sul **tag del dispositivo** e sul **certificato client valido**.</span><span class="sxs-lookup"><span data-stu-id="3a074-140">After the certificate is uploaded, you can create access policies and session policies based on **Device tag** and **Valid client certificate**.</span></span>

![ID del dispositivo di controllo dell'accesso condizionale](media/image2.png)

> [!NOTE]
> <span data-ttu-id="3a074-142">Un certificato viene richiesto solo da un utente se la sessione corrisponde a un criterio che utilizza il filtro certificato client valido.</span><span class="sxs-lookup"><span data-stu-id="3a074-142">A certificate is only requested from a user if the session matches a policy that uses the valid client certificate filter.</span></span>
> 
## <a name="step-4-test-the-deployment"></a><span data-ttu-id="3a074-143">Passaggio 4: testare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="3a074-143">Step 4: Test the deployment</span></span> 

1. <span data-ttu-id="3a074-p104">Primo disconnettersi da eventuali sessioni esistenti. Provare a eseguire l'accesso a ogni app che è stata distribuita correttamente. Accedere utilizzando un utente che corrisponda ai criteri configurati in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3a074-p104">First sign out of any existing sessions. Then, try to sign in to each app that was successfully deployed. Sign in using a user that matches the policy configured in Azure AD.</span></span>

2. <span data-ttu-id="3a074-147">Nel portale di sicurezza delle app Cloud, in **indaga**, selezionare **log attività**e verificare che le attività di login vengano acquisite per ogni app.</span><span class="sxs-lookup"><span data-stu-id="3a074-147">In the Cloud App Security portal, under **Investigate**, select **Activity log**, and make sure the login activities are captured for each app.</span></span>

3. <span data-ttu-id="3a074-148">È possibile filtrare facendo clic su **Avanzate**e quindi utilizzando il filtro **origine è uguale a controllo di accesso**.</span><span class="sxs-lookup"><span data-stu-id="3a074-148">You can filter by clicking on **Advanced**, and then filtering using **Source equals Access control**.</span></span>

4. <span data-ttu-id="3a074-p105">Si consiglia di accedere alle app per dispositivi mobili e desktop da periferiche gestite e non gestite. In questo modo, è necessario verificare che le attività vengano acquisite correttamente nel registro attività. Per verificare la corretta acquisizione dell'attività, fare clic su un'attività di accesso Single Sign-on in modo che apra il cassetto attività. Verificare che il **tag** dell'agente utente indichi correttamente se il dispositivo è un client nativo (ovvero un'app per dispositivi mobili o desktop) oppure se il dispositivo è un dispositivo gestito (conforme, dominio aggiunto o certificato client valido).</span><span class="sxs-lookup"><span data-stu-id="3a074-p105">It's recommended that you sign into mobile and desktop apps from managed and unmanaged devices. This is to make sure that the activities are properly captured in the activity log. To verify that the activity is properly captured, click on a single sign-on log on activity so that it opens the activity drawer. Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).</span></span>

> [!NOTE]
> <span data-ttu-id="3a074-p106">Dopo la distribuzione, non è possibile rimuovere un'app dalla pagina di controllo dell'accesso condizionale. Se non si imposta una sessione o un criterio di accesso sull'app, il controllo delle app di accesso condizionale non modificherà alcun comportamento per l'app.</span><span class="sxs-lookup"><span data-stu-id="3a074-p106">After it is deployed, you can't remove an app from the Conditional Access App Control page. As long as you don't set a session or access policy on the app, the Conditional Access App Control won't change any behavior for the app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a074-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3a074-155">Next steps</span></span>

- [<span data-ttu-id="3a074-156">Informazioni sui criteri di sessione in Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="3a074-156">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="3a074-157">Informazioni sui criteri di accesso in Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="3a074-157">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 

- [<span data-ttu-id="3a074-158">Raggruppare gli indirizzi IP per semplificare la gestione in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3a074-158">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)