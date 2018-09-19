---
title: Proteggere l’accesso a dati e servizi in Office 365
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
ms.openlocfilehash: 6ea617b1a7a7a34492689908d4816a851d58e776
ms.sourcegitcommit: 0ce722533d72fa8dcc1d8a58d3c649cb345b938d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "24009102"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a>Proteggere l’accesso a dati e servizi in Office 365

La protezione dell'accesso ai dati di Office 365 e servizi è fondamentale per la difesa contro gli attacchi cyber e protegge la perdita di dati. Le stesse protezioni possono essere applicate ad altre applicazioni SaaS nell'ambiente in uso e pubblicati anche per le applicazioni in locale con il Proxy di applicazione di Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Passaggio 1: Esaminare i suggerimenti

Funzionalità consigliate per proteggere le identità e i dispositivi che accedono a Office 365, ad altri servizi SaaS e ad applicazioni locali pubblicate con proxy di applicazione Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>Passaggio 2: Configurare MFA

Utilizzare le risorse per orientare se stessi a MFA, decidere quale versione è adatta alle proprie esigenze e quindi pianificare e distribuire MFA per l'ambiente.
  
- [Che cos'è autenticazione multifattore Azure?](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [Scegliere la soluzione di autenticazione multifattore Azure automaticamente](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Come ottenere autenticazione multifattore Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Configurare l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [Pianificare dove distribuire MFA, Cloud o locale](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Configurare le impostazioni di autenticazione multifattore Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>Passaggio 3: Applicare MFA con le regole di accesso condizionale Azure Active Directory

Se si utilizza MFA di Azure Active Directory, creare una regola di accesso condizionato per richiedere MFA per accedere a Office 365 e altre applicazioni SaaS nell'ambiente in uso.
  
- [Accesso condizionato in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a>Passaggio 4: Configurare la gestione dei privilegi di accesso

Accesso privilegiato management consente di controllare l'accesso granulare attività di amministrazione con privilegi in Office 365.  È possibile proteggere dell'organizzazione da violazioni che possono utilizzare un account con privilegi di amministratore esistenti con la condizione accesso ai dati riservati o l'accesso alle impostazioni di configurazione critici.

- [Panoramica dei privilegi accedere a gestione](privileged-access-managment-overview.md)
- [Configurare la gestione dei privilegi di accesso](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a>Passaggio 5: Configurare criteri di accesso di dispositivi di SharePoint

Criteri di accesso di dispositivi per SharePoint Online e OneDrive for Business sono consigliati per la protezione dei dati riservati, classificati e regolamentati. Disponibile a breve è la possibilità di applicare criteri di accesso di dispositivi ai singoli siti.
  
- [Controllare l'accesso da dispositivi non gestiti](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a>Passaggio 6: Configurazione app e protezione dei dati per i dispositivi

È possibile gestire applicazioni per dispositivi mobili indipendentemente dal fatto che vengono registrati i dispositivi per la gestione dei dispositivi mobili. Questo protegge da danni accidentale perdita di dati in Office 365, inclusi file e posta elettronica.
  
- IOS e Android: [dati di app Protect utilizzando criteri di protezione di app con Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
Per Windows 10, configurare Windows Information Protection (WIP) per evitare perdite di dati accidentali.
  
- Per i dispositivi gestiti: [Crea una protezione informazioni Windows (WIP) con criteri di registrazione tramite il portale per Intune Microsoft Azure](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- Per i dispositivi riattivare gestiti: [creare e distribuire i criteri di protezione di Windows Information Protection (WIP) app con Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)
    
## <a name="step-7-manage-devices-with-intune"></a>Passaggio 7: Gestiscono dispositivi con Intune

Gestione di dispositivi consente di verificare che siano corretti e compatibile prima di autorizzarli ad accedere alle risorse nell'ambiente in uso. Dispositivo basato su accesso condizionato regole garantire chi effettua l'attacco non può accedere alle risorse dai dispositivi non gestiti.
  
- [Registrare i dispositivi per la gestione in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>Passaggio 8: Configurare i criteri di Intune aggiuntivi e le regole di accesso condizionale per l'ambiente

Utilizzare queste configurazioni consigliate come punto di partenza per implementare la scalabilità dell'organizzazione o scenari di protezione accesso sofisticati.
  
- [Criteri di protezione della posta elettronica e le configurazioni](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

