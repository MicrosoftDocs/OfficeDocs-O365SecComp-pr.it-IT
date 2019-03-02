---
title: Integrazione di SIEM con Office 365 Threat Intelligence e Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.collection:
- M365-security-compliance
description: Integrare il server SIEM dell'organizzazione con Office 365 Threat Intelligence e Advanced Threat Protection con l'API di gestione delle attività di Office 365.
ms.openlocfilehash: 68d2b4387c1af2363fbb67d0671edeaaa4dc652d
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357437"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a>Integrazione di SIEM con Office 365 Threat Intelligence e Advanced Threat Protection

Se l'organizzazione utilizza un server di gestione eventi e incidenti di sicurezza (SIEM), è possibile integrare Office 365 Threat Intelligence e Advanced Threat Protection con il server SIEM. L'integrazione di SIEM consente di visualizzare le informazioni, ad esempio i malware rilevati da Office 365 Advanced Protection e Threat Intelligence, nei report di SIEM server. Per configurare l'integrazione di SIEM, è possibile utilizzare l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

L'API di gestione delle attività di Office 365 recupera informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Office 365 e Azure Active Directory dell'organizzazione. Lo [schema di Office 365 Advanced Threat Protection and Threat Intelligence](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) è compatibile con Threat Intelligence e/o Advanced Threat Protection, quindi se l'organizzazione dispone di una protezione avanzata dalle minacce, ma non di una minaccia (o viceversa), è possibile è ancora in uso la stessa API per l'integrazione del server SIEM. 

Il server SIEM o un altro sistema analogo deve eseguire il polling del carico di lavoro **generale** per accedere agli eventi di rilevamento. Per ulteriori informazioni, vedere [Introduzione alle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

> [!IMPORTANT]
> È necessario essere un amministratore globale di Office 365 o disporre del ruolo di amministratore della sicurezza assegnato per il Centro sicurezza & Compliance per configurare l'integrazione di SIEM con Office 365 Advanced Threat Protection.<br/>La registrazione di controllo deve essere attivata per l'ambiente Office 365. Per ottenere assistenza, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Argomenti correlati

[Office 365 Threat Intelligence](office-365-ti.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Smart report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365](reports-and-insights-in-security-and-compliance.md)
  
[Autorizzazioni nel centro sicurezza &amp; e conformità di Office 365](permissions-in-the-security-and-compliance-center.md)
  

