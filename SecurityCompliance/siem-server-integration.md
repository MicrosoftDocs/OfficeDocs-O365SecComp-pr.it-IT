---
title: Integrazione del server SIEM con Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
description: "Riepilogo: Leggere questo articolo per una panoramica dell'integrazione di SIEM server con Microsoft 365."
ms.openlocfilehash: bd512ca6d75928712e3444581a78610a0869123d
ms.sourcegitcommit: 63ed467fc3e1ab1ab9ee122df97c64737169834e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842683"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integrazione del server SIEM con le applicazioni e servizi Microsoft 365

## <a name="overview"></a>Panoramica

Se l'organizzazione utilizza un server informazioni sulla sicurezza e gestione di eventi (SIEM) o se si prevede di ottenere un server SIEM breve, è importante sapere modalità che saranno integrazione con Microsoft 365, tra cui Office 365 Enterprise. Se è necessario un server SIEM dipende da diversi fattori, quali i requisiti di sicurezza della propria organizzazione. Microsoft 365 offre un'ampia gamma di funzionalità di sicurezza; Tuttavia, se l'organizzazione dispone di contenuto e le applicazioni in locale e nel cloud (come nel caso di una distribuzione ibrida di cloud), è possibile aggiungere un server SIEM per una maggiore protezione. In alternativa, se l'organizzazione ha requisiti di protezione particolarmente rigide che devono essere soddisfatti, è possibile aggiungere un server SIEM al proprio ambiente.

## <a name="siem-server-integration-microsoft-365"></a>Integrazione del server SIEM Microsoft 365

SIEM dal server per ricevere dati da un'ampia gamma di applicazioni e servizi Microsoft 365. Nella tabella seguente sono elencati alcuni servizi Microsoft 365 e le applicazioni e gli input server SIEM e dove è possibile per ottenere ulteriori informazioni sull'integrazione server SIEM. 

| Applicazione o il servizio Microsoft 365 | Input server SIEM | Risorse per ulteriori informazioni |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md) <br/>   oppure   <br/>[Office 365 Threat Intelligence](office-365-ti.md) | Registri di controllo | [Integrazione di SIEM con Business Intelligence di Office 365 rischio e protezione da minacce avanzate](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integrazione di registro | [Integrazione con Microsoft Cloud App Security SIEM](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 Cloud App Security](office-365-cas-overview.md) | Integrazione di registro | [Integrare il server SIEM con Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md) |
| [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | Integrazione di registro | [Estrarre gli avvisi per gli strumenti SIEM](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Centro protezione di Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Rischio protezione e il rilevamento di rischio) | Avvisi | [Esportazione di dati di sicurezza Azure in SIEM - configurazione Pipeline - anteprima](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Protezione dell'identità di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | Registri di controllo | [Integrare i registri di controllo di Azure Active Directory](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Analitica Azure rischio avanzate](https://docs.microsoft.com/azure/security/azure-threat-detection) | Integrazione di registro | [Guida di riferimento registro ATA SIEM](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>Deve essere attivata la registrazione di controllo

Verificare che viene attivata la registrazione di controllo prima di configurare l'integrazione del server SIEM. 

- SharePoint Online, OneDrive for Business e Azure Active Directory, [la registrazione di controllo è attivata nel centro conformità sicurezza](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Per Exchange Online, [viene attivata la registrazione di controllo con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="see-also"></a>Vedere anche

[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Test Lab Guide (TLG) di adozione cloud](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


