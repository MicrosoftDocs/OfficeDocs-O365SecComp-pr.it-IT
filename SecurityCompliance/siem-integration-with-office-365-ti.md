---
title: Integrazione di SIEM con Office 365 Threat Intelligence
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: Integrare il server dell'organizzazione SIEM con Office 365 rischio Intelligence utilizzando l'API di gestione di Office 365 attività.
ms.openlocfilehash: 82aeeea53bf87f1555fa68b2784b8fe38a435e15
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531055"
---
# <a name="siem-integration-with-office-365-threat-intelligence"></a><span data-ttu-id="e1b25-103">Integrazione di SIEM con Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="e1b25-103">SIEM integration with Office 365 Threat Intelligence</span></span>

<span data-ttu-id="e1b25-p101">Se l'organizzazione utilizza un server di gestione (SIEM) incidente e l'evento di protezione, è possibile integrare Intelligence rischio di Office 365 con il server SIEM. In questo modo è possibile visualizzare informazioni, ad esempio malware rilevato da Office 365 rischio Intelligence, i rapporti di server SIEM.</span><span class="sxs-lookup"><span data-stu-id="e1b25-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence with your SIEM server. This enables you to view information, such as malware detected by Office 365 Threat Intelligence, in your SIEM server reports.</span></span>
  
## <a name="use-the-office-365-activity-management-api"></a><span data-ttu-id="e1b25-106">Utilizzare l'API di Gestione attività Office 365</span><span class="sxs-lookup"><span data-stu-id="e1b25-106">Use the Office 365 Activity Management API</span></span>

<span data-ttu-id="e1b25-p102">Per integrare Intelligence rischio di Office 365 con il server SIEM, utilizzare l'API di Gestione attività di Office 365. Questa API consente di recuperare informazioni sull'utente, amministrazione, sistema e le azioni dei criteri e gli eventi di registri delle attività di Office 365 e Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1b25-p102">To integrate Office 365 Threat Intelligence with your SIEM server, use the Office 365 Activity Management API. This API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure AD activity logs.</span></span> 
  
<span data-ttu-id="e1b25-109">È necessario essere un amministratore globale di Office 365 o disporre del ruolo di amministratore di sicurezza assegnato nella protezione &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="e1b25-109">You must be an Office 365 global administrator or have the security administrator role assigned in the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="e1b25-110">Vedere [Guida di riferimento API di attività di gestione di Office 365](https://msdn.microsoft.com/en-us/office-365/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="e1b25-110">See [Office 365 Management Activity API reference](https://msdn.microsoft.com/en-us/office-365/office-365-management-activity-api-reference).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e1b25-111">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e1b25-111">Related topics</span></span>

[<span data-ttu-id="e1b25-112">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="e1b25-112">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="e1b25-113">Protezione contro le minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="e1b25-113">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="e1b25-114">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="e1b25-114">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

