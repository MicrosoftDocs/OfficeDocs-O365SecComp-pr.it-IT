---
title: Impedire l’accesso non autorizzato a dati e servizi in Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: pagina di destinazione per la protezione dell'accesso ai dati di Office 365 e servizi
ms.openlocfilehash: e6e2d8d3ba6482d4b80593bd9e09d49d6120af80
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531060"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="71e50-103">Impedire l’accesso non autorizzato a dati e servizi in Office 365</span><span class="sxs-lookup"><span data-stu-id="71e50-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="71e50-p101">La protezione dell'accesso ai dati di Office 365 e servizi è fondamentale per la difesa contro gli attacchi cyber e protegge la perdita di dati. Le stesse protezioni possono essere applicate ad altre applicazioni SaaS nell'ambiente in uso e pubblicati anche per le applicazioni in locale con il Proxy di applicazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71e50-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="71e50-106">Passaggio 1: Esaminare i suggerimenti</span><span class="sxs-lookup"><span data-stu-id="71e50-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="71e50-107">Funzionalità consigliate per proteggere le identità e i dispositivi che accedono a Office 365, ad altri servizi SaaS e ad applicazioni locali pubblicate con proxy di applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="71e50-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="71e50-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="71e50-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="71e50-109">Passaggio 2: Configurare MFA</span><span class="sxs-lookup"><span data-stu-id="71e50-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="71e50-110">Utilizzare le risorse per orientare se stessi a MFA, decidere quale versione è adatta alle proprie esigenze e quindi pianificare e distribuire MFA per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="71e50-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="71e50-111">Che cos'è autenticazione multifattore Azure?</span><span class="sxs-lookup"><span data-stu-id="71e50-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="71e50-112">Scegliere la soluzione di autenticazione multifattore Azure automaticamente</span><span class="sxs-lookup"><span data-stu-id="71e50-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="71e50-113">Come ottenere autenticazione multifattore Azure</span><span class="sxs-lookup"><span data-stu-id="71e50-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="71e50-114">Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365</span><span class="sxs-lookup"><span data-stu-id="71e50-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="71e50-115">Configurare l'autenticazione a più fattori per gli utenti di Office 365</span><span class="sxs-lookup"><span data-stu-id="71e50-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="71e50-116">Pianificare dove distribuire MFA, Cloud o locale</span><span class="sxs-lookup"><span data-stu-id="71e50-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="71e50-117">Configurare le impostazioni di autenticazione multifattore Azure</span><span class="sxs-lookup"><span data-stu-id="71e50-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="71e50-118">Passaggio 3: Applicare MFA con le regole di accesso condizionale Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="71e50-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="71e50-119">Se si utilizza MFA di Azure Active Directory, creare una regola di accesso condizionato per richiedere MFA per accedere a Office 365 e altre applicazioni SaaS nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="71e50-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="71e50-120">Accesso condizionato in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="71e50-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="71e50-121">Passaggio 4: Configurare criteri di accesso di dispositivi di SharePoint</span><span class="sxs-lookup"><span data-stu-id="71e50-121">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="71e50-p102">Criteri di accesso di dispositivi per SharePoint Online e OneDrive for Business sono consigliati per la protezione dei dati riservati, classificati e regolamentati. Disponibile a breve è la possibilità di applicare criteri di accesso di dispositivi ai singoli siti.</span><span class="sxs-lookup"><span data-stu-id="71e50-p102">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="71e50-124">Controllare l'accesso da dispositivi non gestiti</span><span class="sxs-lookup"><span data-stu-id="71e50-124">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-5-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="71e50-125">Passaggio 5: Configurare app e protezione dei dati per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="71e50-125">Step 5: Configure app and data protection for devices</span></span>

<span data-ttu-id="71e50-p103">È possibile gestire applicazioni per dispositivi mobili indipendentemente dal fatto che vengono registrati i dispositivi per la gestione dei dispositivi mobili. Questo protegge da danni accidentale perdita di dati in Office 365, inclusi file e posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="71e50-p103">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="71e50-128">IOS e Android: [dati di app Protect utilizzando criteri di protezione di app con Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="71e50-128">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="71e50-129">Per Windows 10, configurare Windows Information Protection (WIP) per evitare perdite di dati accidentali.</span><span class="sxs-lookup"><span data-stu-id="71e50-129">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="71e50-130">Per i dispositivi gestiti: [Crea una protezione informazioni Windows (WIP) con criteri di registrazione tramite il portale per Intune Microsoft Azure](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="71e50-130">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="71e50-131">Per i dispositivi riattivare gestiti: [creare e distribuire i criteri di protezione di Windows Information Protection (WIP) app con Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span><span class="sxs-lookup"><span data-stu-id="71e50-131">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-6-manage-devices-with-intune"></a><span data-ttu-id="71e50-132">Passaggio 6: Gestire i dispositivi con Intune</span><span class="sxs-lookup"><span data-stu-id="71e50-132">Step 6: Manage devices with Intune</span></span>

<span data-ttu-id="71e50-p104">Gestione di dispositivi consente di verificare che siano corretti e compatibile prima di autorizzarli ad accedere alle risorse nell'ambiente in uso. Dispositivo basato su accesso condizionato regole garantire chi effettua l'attacco non può accedere alle risorse dai dispositivi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="71e50-p104">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="71e50-135">Registrare i dispositivi per la gestione in Intune</span><span class="sxs-lookup"><span data-stu-id="71e50-135">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-7-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="71e50-136">Passaggio 7: Configurare i criteri di Intune aggiuntivi e le regole di accesso condizionale per l'ambiente</span><span class="sxs-lookup"><span data-stu-id="71e50-136">Step 7: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="71e50-137">Utilizzare queste configurazioni consigliate come punto di partenza per implementare la scalabilità dell'organizzazione o scenari di protezione accesso sofisticati.</span><span class="sxs-lookup"><span data-stu-id="71e50-137">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="71e50-138">Criteri di protezione della posta elettronica e le configurazioni</span><span class="sxs-lookup"><span data-stu-id="71e50-138">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

