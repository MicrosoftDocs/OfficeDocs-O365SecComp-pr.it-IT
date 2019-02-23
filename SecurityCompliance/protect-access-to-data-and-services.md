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
# <a name="protect-access-to-data-and-services-in-office-365"></a>Proteggere l'accesso a dati e servizi di Office 365

La protezione dell'accesso ai dati e ai servizi di Office 365 è cruciale per la difesa contro gli attacchi cibernetici e la protezione contro la perdita di dati. Le stesse protezioni possono essere applicate ad altre applicazioni SaaS nell'ambiente e persino alle applicazioni locali pubblicate con il proxy di applicazione di Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Passaggio 1: esaminare i suggerimenti

Funzionalità consigliate per proteggere le identità e i dispositivi che accedono a Office 365, ad altri servizi SaaS e ad applicazioni locali pubblicate con proxy di applicazione Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>Passaggio 2: configurare l'autenticazione Master

Utilizzare queste risorse per orientarsi all'AMF, decidere quale versione è adatta per l'utente e quindi pianificare e distribuire l'infrastruttura Mae per l'ambiente.
  
- [Che cos'è l'autenticazione a più fattori di Azure?](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [Scegliere la soluzione di autenticazione a più fattori di Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Come ottenere l'autenticazione a più fattori di Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Configurare l'autenticazione a più fattori per utenti di Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [Pianificare la distribuzione di AMF, cloud o locale](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Configurare le impostazioni di autenticazione a più fattori di Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>Passaggio 3: applicare l'AMF con le regole di accesso condizionale di Azure AD

Se si utilizza Azure AD AMF, creare una regola di accesso condizionale per richiedere l'accesso a Microsoft Office 365 e ad altre app SaaS nell'ambiente.
  
- [Accesso condizionale in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a>Passaggio 4: configurare la gestione degli accessi con privilegi

La gestione degli accessi con privilegi consente il controllo di accesso granulare sulle attività amministrative privilegiate in Office 365.  Può aiutare a proteggere l'organizzazione da violazioni che possono utilizzare gli account di amministrazione privilegiati esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche.

- [Panoramica della gestione degli accessi con privilegi](privileged-access-management-overview.md)
- [Configurare Privileged Access Management](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a>Passaggio 5: configurare i criteri di accesso ai dispositivi di SharePoint

I criteri di accesso ai dispositivi per SharePoint Online e OneDrive for business sono consigliati per la protezione dei dati sensibili, classificati e regolati. La prossima è la possibilità di applicare i criteri di accesso ai dispositivi ai singoli siti del team.
  
- [Controllare l'accesso da dispositivi non gestiti](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a>Passaggio 6: configurare l'applicazione e la protezione dei dati per i dispositivi

È possibile gestire le applicazioni su dispositivi mobili indipendentemente dal fatto che i dispositivi siano registrati per la gestione dei dispositivi mobili. Questo protegge dalla perdita accidentale dei dati in Office 365, inclusi i messaggi e la posta elettronica.
  
- Per iOS e Android: [Proteggi i dati delle app usando i criteri di protezione delle app con Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
Per Windows 10, configurare Windows Information Protection (WIP) per impedire perdite di dati accidentali.
  
- Per i dispositivi gestiti: [creare un Windows Information Protection (WIP) con il criterio di registrazione tramite il portale di Azure per Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- Per i dispositivi non gestiti: [creare e distribuire i criteri di protezione delle app di Windows Information Protection (WIP) con Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)
    
## <a name="step-7-manage-devices-with-intune"></a>Passaggio 7: gestione dei dispositivi con Intune

La gestione dei dispositivi consente di assicurarsi che siano integre e conformi prima di consentire loro di accedere alle risorse nell'ambiente in uso. Le regole di accesso condizionale basate su dispositivo aiutano a garantire che gli aggressori non possano accedere alle risorse dai dispositivi non gestiti.
  
- [Registrare i dispositivi per la gestione in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>Passaggio 8: configurare ulteriori criteri di Intune e regole di accesso condizionale per l'ambiente

Utilizzare queste configurazioni consigliate come punto di partenza per scenari di protezione di livello aziendale o di sicurezza dell'accesso avanzato.
  
- [Criteri di posta elettronica e configurazioni sicure](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

