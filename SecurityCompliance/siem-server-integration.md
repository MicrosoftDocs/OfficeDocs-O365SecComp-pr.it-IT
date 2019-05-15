---
title: Integrazione del server SIEM con Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: "Riepilogo: leggere questo articolo per ottenere una panoramica dell'integrazione del server SIEM con Microsoft 365."
ms.openlocfilehash: 75fbfa45288d30363d36ad5046cd46127b0af777
ms.sourcegitcommit: c7989a8ead235aaebb2503abbde598f2c26c0056
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "33979442"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integrazione del server SIEM con i servizi e le applicazioni di Microsoft 365

## <a name="overview"></a>Panoramica

Se l'organizzazione utilizza un server di gestione eventi e informazioni di sicurezza (SIEM) o se si prevede di ottenere un server SIEM al più presto, potrebbe essere utile sapere come si integrerà con Microsoft 365, tra cui Office 365 Enterprise. Se è necessario un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione. Microsoft 365 offre una vasta gamma di funzionalità di sicurezza; Tuttavia, se l'organizzazione dispone di contenuto e applicazioni in locale e nel cloud (come nel caso di una distribuzione di cloud ibrido), è possibile valutare l'aggiunta di un server SIEM per una maggiore protezione. In alternativa, se l'organizzazione ha requisiti di sicurezza particolarmente severi che è necessario soddisfare, è consigliabile aggiungere un server SIEM all'ambiente.

## <a name="siem-server-integration-microsoft-365"></a>Integrazione di server SIEM Microsoft 365

Un server SIEM può ricevere dati da un'ampia gamma di servizi e applicazioni di Microsoft 365. Nella tabella seguente sono elencati diversi servizi e applicazioni di Microsoft 365 insieme agli input del server SIEM e dove andare per ulteriori informazioni sull'integrazione del server SIEM. 

| Servizio o applicazione Microsoft 365 | Input del server SIEM | Risorse per ulteriori informazioni |
| --- | --- | --- |
| [Protezione avanzata dalle minacce di Office 365](office-365-atp.md) <br/>   oppure   <br/>[Office 365 Threat Intelligence](office-365-ti.md) | Registri di controllo | [Integrazione di SIEM con Office 365 Advanced Threat Protection](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integrazione del registro | [Integrazione di SIEM con Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integrazione del registro | [Integrare il server SIEM con cloud app Security](https://docs.microsoft.com/cloud-app-security/siem) |
| [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | Integrazione del registro | [Tirare gli avvisi agli strumenti di SIEM](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Protezione dalle minacce e rilevamento delle minacce) | Avvisi | [Esportazione dei dati di sicurezza di Azure nella configurazione di SIEM-pipeline-anteprima](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Protezione dell'identità di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | Registri di controllo | [Integrazione dei log di controllo di Azure Active Directory](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Analisi avanzata delle minacce di Azure](https://docs.microsoft.com/azure/security/azure-threat-detection) | Integrazione del registro | [Informazioni di riferimento sul log di ATA SIEM](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>La registrazione di controllo deve essere attivata

Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM. 

- Per SharePoint Online, OneDrive for business e Azure Active Directory, [la registrazione di controllo è attivata nel centro sicurezza _AMP_ Compliance](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Per Exchange Online, la [registrazione di controllo è attivata con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="see-also"></a>Vedere anche

[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Test Lab Guide (TLG) per l’adozione del cloud](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


