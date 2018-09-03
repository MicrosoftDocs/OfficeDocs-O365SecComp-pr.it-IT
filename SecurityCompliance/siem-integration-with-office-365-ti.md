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
ms.openlocfilehash: 40c84b9d7b7ec4c9b15383e3ffbbabf839294def
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782143"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="13b01-103">Integrazione di SIEM con Business Intelligence di Office 365 rischio e protezione da minacce avanzate</span><span class="sxs-lookup"><span data-stu-id="13b01-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="13b01-p101">Se l'organizzazione utilizza un server di gestione (SIEM) incidente e l'evento di protezione, è possibile integrare Business Intelligence di Office 365 rischio e protezione rischio avanzate con il server SIEM. Integrazione SIEM consente di visualizzare informazioni, ad esempio malware rilevato da protezione avanzata di Office 365 e Business Intelligence di rischio, i rapporti di server SIEM. Per impostare l'integrazione SIEM, utilizzare l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="13b01-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="13b01-p102">L'API di gestione di Office 365 attività consente di recuperare informazioni sull'utente, amministrazione, sistema e le azioni dei criteri e gli eventi di Office 365 e i registri attività di Azure Active Directory dell'organizzazione. [Protezione rischio avanzate di Office 365 e allo schema di Business Intelligence di rischio](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) opera Intelligence rischio e/o avanzate Threat Protection, pertanto se l'organizzazione dispone di protezione di rischio avanzate ma non Intelligence rischio (e viceversa), è possibile Utilizzare la stessa API per l'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="13b01-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="13b01-p103">Il server SIEM o un altro sistema simile deve eseguire il polling del carico di lavoro **audit.general** degli eventi di rilevamento di access. Per ulteriori informazioni, vedere [Introduzione a Office 365 Management API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="13b01-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="13b01-111">È necessario essere un amministratore globale di Office 365 o disporre del ruolo di amministratore di sicurezza assegnato nel centro conformità sicurezza configurare l'integrazione SIEM con Business Intelligence di Office 365 rischio e protezione da minacce avanzate.</span><span class="sxs-lookup"><span data-stu-id="13b01-111">You must be an Office 365 global administrator or have the security administrator role assigned in the Security & Compliance Center to set up SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection.</span></span></br><span data-ttu-id="13b01-p104">Deve essere attivata la registrazione di controllo per l'ambiente Office 365. Per ottenere assistenza per questo, vedere [attivare Office 365 ricerca dei registri di controllo attivato o disattivato](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="13b01-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="13b01-114">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="13b01-114">Related topics</span></span>

[<span data-ttu-id="13b01-115">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="13b01-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="13b01-116">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="13b01-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="13b01-117">Smart report e sui concetti di Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="13b01-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="13b01-118">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="13b01-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

