---
title: Integrazione di SIEM con Office 365 Threat Intelligence e Advanced Threat Protection
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
description: Integrare il server SIEM dell'organizzazione con Office 365 Threat Intelligence e Advanced Threat Protection con l'API di gestione delle attività di Office 365.
ms.openlocfilehash: 854f763b72dfac1a5dc1442b1d9d123ed5439257
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087245"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="9b990-103">Integrazione di SIEM con Office 365 Threat Intelligence e Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9b990-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="9b990-p101">Se l'organizzazione utilizza un server di gestione eventi e incidenti di sicurezza (SIEM), è possibile integrare Office 365 Threat Intelligence e Advanced Threat Protection con il server SIEM. L'integrazione di SIEM consente di visualizzare le informazioni, ad esempio i malware rilevati da Office 365 Advanced Protection e Threat Intelligence, nei report di SIEM server. Per configurare l'integrazione di SIEM, è possibile utilizzare l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="9b990-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="9b990-p102">L'API di gestione delle attività di Office 365 recupera informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Office 365 e Azure Active Directory dell'organizzazione. Lo [schema di Office 365 Advanced Threat Protection and Threat Intelligence](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) è compatibile con Threat Intelligence e/o Advanced Threat Protection, quindi se l'organizzazione dispone di una protezione avanzata dalle minacce, ma non di una minaccia (o viceversa), è possibile è ancora in uso la stessa API per l'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="9b990-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="9b990-p103">Il server SIEM o un altro sistema analogo deve eseguire il polling del carico di lavoro **generale** per accedere agli eventi di rilevamento. Per ulteriori informazioni, vedere [Introduzione alle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="9b990-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9b990-111">È necessario essere un amministratore globale di Office 365 o disporre del ruolo di amministratore della sicurezza assegnato per il Centro sicurezza & Compliance per configurare l'integrazione di SIEM con Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="9b990-111">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="9b990-p104">La registrazione di controllo deve essere attivata per l'ambiente Office 365. Per ottenere assistenza, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="9b990-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b990-114">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9b990-114">Related topics</span></span>

[<span data-ttu-id="9b990-115">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="9b990-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="9b990-116">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9b990-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="9b990-117">Smart report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="9b990-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="9b990-118">Autorizzazioni nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="9b990-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

