---
title: Proteggere l'accesso a dati e servizi di Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: pagina di destinazione per la protezione dell'accesso ai dati e ai servizi di O365
ms.openlocfilehash: 95933c5a7bc95f9fd70e8f3470055b57193971d4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213536"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="782d1-103">Proteggere l'accesso a dati e servizi di Office 365</span><span class="sxs-lookup"><span data-stu-id="782d1-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="782d1-p101">La protezione dell'accesso ai dati e ai servizi di Office 365 è cruciale per la difesa contro gli attacchi cibernetici e la protezione contro la perdita di dati. Le stesse protezioni possono essere applicate ad altre applicazioni SaaS nell'ambiente e persino alle applicazioni locali pubblicate con il proxy di applicazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="782d1-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="782d1-106">Passaggio 1: esaminare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="782d1-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="782d1-107">Funzionalità consigliate per proteggere le identità e i dispositivi che accedono a Office 365, ad altri servizi SaaS e ad applicazioni locali pubblicate con proxy di applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="782d1-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="782d1-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="782d1-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="782d1-109">Passaggio 2: configurare l'autenticazione Master</span><span class="sxs-lookup"><span data-stu-id="782d1-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="782d1-110">Utilizzare queste risorse per orientarsi all'AMF, decidere quale versione è adatta per l'utente e quindi pianificare e distribuire l'infrastruttura Mae per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="782d1-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="782d1-111">Che cos'è l'autenticazione a più fattori di Azure?</span><span class="sxs-lookup"><span data-stu-id="782d1-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="782d1-112">Scegliere la soluzione di autenticazione a più fattori di Azure</span><span class="sxs-lookup"><span data-stu-id="782d1-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="782d1-113">Come ottenere l'autenticazione a più fattori di Azure</span><span class="sxs-lookup"><span data-stu-id="782d1-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="782d1-114">Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365</span><span class="sxs-lookup"><span data-stu-id="782d1-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="782d1-115">Configurare l'autenticazione a più fattori per utenti di Office 365</span><span class="sxs-lookup"><span data-stu-id="782d1-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="782d1-116">Pianificare la distribuzione di AMF, cloud o locale</span><span class="sxs-lookup"><span data-stu-id="782d1-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="782d1-117">Configurare le impostazioni di autenticazione a più fattori di Azure</span><span class="sxs-lookup"><span data-stu-id="782d1-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="782d1-118">Passaggio 3: applicare l'AMF con le regole di accesso condizionale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="782d1-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="782d1-119">Se si utilizza Azure AD AMF, creare una regola di accesso condizionale per richiedere l'accesso a Microsoft Office 365 e ad altre app SaaS nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="782d1-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="782d1-120">Accesso condizionale in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="782d1-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a><span data-ttu-id="782d1-121">Passaggio 4: configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="782d1-121">Step 4: Configure privileged access management</span></span>

<span data-ttu-id="782d1-p102">La gestione degli accessi con privilegi consente il controllo di accesso granulare sulle attività amministrative privilegiate in Office 365.  Può aiutare a proteggere l'organizzazione da violazioni che possono utilizzare gli account di amministrazione privilegiati esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="782d1-p102">Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="782d1-124">Panoramica della gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="782d1-124">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="782d1-125">Configurare Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="782d1-125">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a><span data-ttu-id="782d1-126">Passaggio 5: configurare i criteri di accesso ai dispositivi di SharePoint</span><span class="sxs-lookup"><span data-stu-id="782d1-126">Step 5: Configure SharePoint device access policies</span></span>

<span data-ttu-id="782d1-p103">I criteri di accesso ai dispositivi per SharePoint Online e OneDrive for business sono consigliati per la protezione dei dati sensibili, classificati e regolati. La prossima è la possibilità di applicare i criteri di accesso ai dispositivi ai singoli siti del team.</span><span class="sxs-lookup"><span data-stu-id="782d1-p103">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="782d1-129">Controllare l'accesso da dispositivi non gestiti</span><span class="sxs-lookup"><span data-stu-id="782d1-129">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="782d1-130">Passaggio 6: configurare l'applicazione e la protezione dei dati per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="782d1-130">Step 6: Configure app and data protection for devices</span></span>

<span data-ttu-id="782d1-p104">È possibile gestire le applicazioni su dispositivi mobili indipendentemente dal fatto che i dispositivi siano registrati per la gestione dei dispositivi mobili. Questo protegge dalla perdita accidentale dei dati in Office 365, inclusi i messaggi e la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="782d1-p104">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="782d1-133">Per iOS e Android: [Proteggi i dati delle app usando i criteri di protezione delle app con Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="782d1-133">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="782d1-134">Per Windows 10, configurare Windows Information Protection (WIP) per impedire perdite di dati accidentali.</span><span class="sxs-lookup"><span data-stu-id="782d1-134">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="782d1-135">Per i dispositivi gestiti: [creare un Windows Information Protection (WIP) con il criterio di registrazione tramite il portale di Azure per Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="782d1-135">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="782d1-136">Per i dispositivi non gestiti: [creare e distribuire i criteri di protezione delle app di Windows Information Protection (WIP) con Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span><span class="sxs-lookup"><span data-stu-id="782d1-136">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-7-manage-devices-with-intune"></a><span data-ttu-id="782d1-137">Passaggio 7: gestione dei dispositivi con Intune</span><span class="sxs-lookup"><span data-stu-id="782d1-137">Step 7: Manage devices with Intune</span></span>

<span data-ttu-id="782d1-p105">La gestione dei dispositivi consente di assicurarsi che siano integre e conformi prima di consentire loro di accedere alle risorse nell'ambiente in uso. Le regole di accesso condizionale basate su dispositivo aiutano a garantire che gli aggressori non possano accedere alle risorse dai dispositivi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="782d1-p105">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="782d1-140">Registrare i dispositivi per la gestione in Intune</span><span class="sxs-lookup"><span data-stu-id="782d1-140">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="782d1-141">Passaggio 8: configurare ulteriori criteri di Intune e regole di accesso condizionale per l'ambiente</span><span class="sxs-lookup"><span data-stu-id="782d1-141">Step 8: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="782d1-142">Utilizzare queste configurazioni consigliate come punto di partenza per scenari di protezione di livello aziendale o di sicurezza dell'accesso avanzato.</span><span class="sxs-lookup"><span data-stu-id="782d1-142">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="782d1-143">Criteri di posta elettronica e configurazioni sicure</span><span class="sxs-lookup"><span data-stu-id="782d1-143">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

