---
title: Integrazione di SIEM con Business Intelligence di Office 365 rischio e protezione da minacce avanzate
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: Integrare server SIEM dell'organizzazione con Office 365 rischio Intelligence e avanzate di protezione Threat con l'API di Gestione attività di Office 365.
ms.openlocfilehash: 057d8ac101b96f37846ac751645934279d45dc88
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972258"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a>Integrazione di SIEM con Business Intelligence di Office 365 rischio e protezione da minacce avanzate

Se l'organizzazione utilizza un server di gestione (SIEM) incidente e l'evento di protezione, è possibile integrare Business Intelligence di Office 365 rischio e protezione rischio avanzate con il server SIEM. Integrazione SIEM consente di visualizzare informazioni, ad esempio malware rilevato da protezione avanzata di Office 365 e Business Intelligence di rischio, i rapporti di server SIEM. Per impostare l'integrazione SIEM, utilizzare l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

L'API di gestione di Office 365 attività consente di recuperare informazioni sull'utente, amministrazione, sistema e le azioni dei criteri e gli eventi di Office 365 e i registri attività di Azure Active Directory dell'organizzazione. [Protezione rischio avanzate di Office 365 e allo schema di Business Intelligence di rischio](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) opera Intelligence rischio e/o avanzate Threat Protection, pertanto se l'organizzazione dispone di protezione di rischio avanzate ma non Intelligence rischio (e viceversa), è possibile Utilizzare la stessa API per l'integrazione del server SIEM. 

Il server SIEM o un altro sistema simile deve eseguire il polling del carico di lavoro **audit.general** degli eventi di rilevamento di access. Per ulteriori informazioni, vedere [Introduzione a Office 365 Management API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

> [!IMPORTANT]
> È necessario essere un amministratore globale di Office 365 o disporre del ruolo di amministratore di sicurezza assegnato nel centro conformità sicurezza configurare l'integrazione SIEM con Business Intelligence di Office 365 rischio e protezione da minacce avanzate.<br/>Deve essere attivata la registrazione di controllo per l'ambiente Office 365. Per ottenere assistenza per questo, vedere [attivare Office 365 ricerca dei registri di controllo attivato o disattivato](turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Argomenti correlati

[Office 365 Threat Intelligence](office-365-ti.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Smart report e sui concetti di Office 365 Security &amp; centro conformità](reports-and-insights-in-security-and-compliance.md)
  
[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)
  

