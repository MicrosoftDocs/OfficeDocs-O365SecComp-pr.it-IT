---
title: Integrazione di SIEM con Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 03/11/2019
ms.collection:
- M365-security-compliance
description: Integrare il server SIEM dell'organizzazione con Office 365 Advanced Threat Protection e gli eventi relativi alle minacce correlati nell'API di gestione delle attività di Office 365.
ms.openlocfilehash: da34073669d50cadcc01b5dd885d209a329c645f
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077192"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a><span data-ttu-id="588de-103">Integrazione di SIEM con Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="588de-103">SIEM integration with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="588de-104">Se l'organizzazione utilizza un server di gestione eventi e incidenti di sicurezza (SIEM), è possibile integrare Office 365 Advanced Threat Protection con il server SIEM.</span><span class="sxs-lookup"><span data-stu-id="588de-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="588de-105">L'integrazione di SIEM consente di visualizzare le informazioni, ad esempio malware o phishing rilevate da Office 365 Advanced Protection, nei report di SIEM server.</span><span class="sxs-lookup"><span data-stu-id="588de-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="588de-106">Per configurare l'integrazione di SIEM, è possibile utilizzare l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="588de-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="588de-107">L'API di gestione delle attività di Office 365 recupera informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Office 365 e Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="588de-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="588de-108">Lo [schema office 365 Advanced Threat Protection](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) è compatibile con Advanced Threat Protection, quindi se l'organizzazione dispone di Office 365 Advanced Threat Protection Plan 1 o Plan 2 o Office 365 E5, è comunque possibile utilizzare la stessa API per l'integrazione del server Siem.</span><span class="sxs-lookup"><span data-stu-id="588de-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="588de-109">Il server SIEM o un altro sistema analogo deve eseguire il polling del carico di lavoro **generale** per accedere agli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="588de-109">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="588de-110">Per ulteriori informazioni, vedere [Introduzione alle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="588de-110">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="588de-111">Inoltre, i seguenti valori di **AuditLogRecordType** sono rilevanti per gli eventi ATP di Office 365:</span><span class="sxs-lookup"><span data-stu-id="588de-111">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="588de-112">Enum: AuditLogRecordType-Type: EDM. Int32</span><span class="sxs-lookup"><span data-stu-id="588de-112">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="588de-113">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="588de-113">AuditLogRecordType</span></span>

|<span data-ttu-id="588de-114">Valore</span><span class="sxs-lookup"><span data-stu-id="588de-114">Value</span></span>|<span data-ttu-id="588de-115">Nome membro</span><span class="sxs-lookup"><span data-stu-id="588de-115">Member name</span></span>|<span data-ttu-id="588de-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="588de-116">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="588de-117">28</span><span class="sxs-lookup"><span data-stu-id="588de-117">28</span></span>|<span data-ttu-id="588de-118">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="588de-118">ThreatIntelligence</span></span>|<span data-ttu-id="588de-119">Eventi di phishing e malware da Exchange Online Protection e Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="588de-119">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="588de-120">41</span><span class="sxs-lookup"><span data-stu-id="588de-120">41</span></span>|<span data-ttu-id="588de-121">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="588de-121">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="588de-122">Collegamenti sicuri ATP gli eventi Time-of-Block e Block override di Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="588de-122">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="588de-123">47</span><span class="sxs-lookup"><span data-stu-id="588de-123">47</span></span>|<span data-ttu-id="588de-124">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="588de-124">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="588de-125">Eventi di phishing e malware per i file in SharePoint Online, OneDrive for business e Microsoft teams dalla protezione avanzata dalle minacce di Office 365.</span><span class="sxs-lookup"><span data-stu-id="588de-125">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="588de-126">È necessario essere un amministratore globale di Office 365 o disporre del ruolo di amministratore della sicurezza assegnato per il Centro sicurezza & Compliance per configurare l'integrazione di SIEM con Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="588de-126">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="588de-127">La registrazione di controllo deve essere attivata per l'ambiente Office 365.</span><span class="sxs-lookup"><span data-stu-id="588de-127">Audit logging must be turned on for your Office 365 environment.</span></span> <span data-ttu-id="588de-128">Per ottenere assistenza, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="588de-128">To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="588de-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="588de-129">Related topics</span></span>

[<span data-ttu-id="588de-130">Indagine e risposta alle minacce di Office 365</span><span class="sxs-lookup"><span data-stu-id="588de-130">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)

[<span data-ttu-id="588de-131">Protezione avanzata dalle minacce di Office 365</span><span class="sxs-lookup"><span data-stu-id="588de-131">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="588de-132">Smart report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="588de-132">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="588de-133">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="588de-133">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
