---
title: Eseguire ricerche nel log di controllo per le attività di utenti e amministratori in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: "Il registro di controllo di Office 365 è un log di controllo unificato. Perché un log di controllo unificato? Poiché gli eventi provenienti dalla maggior parte dei servizi di Office 365 in cui si esegue la sottoscrizione dell'organizzazione vengono registrati in un singolo log di controllo che è possibile ricercare. Questo significa che è possibile cercare l'attività di utenti e amministratori in questi servizi:"
ms.openlocfilehash: d964a1404dd022ba9b56e5d86766c5fc6eabf10a
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296519"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="ff35d-106">Eseguire ricerche nel log di controllo per le attività di utenti e amministratori in Office 365</span><span class="sxs-lookup"><span data-stu-id="ff35d-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="ff35d-p102">Il registro di controllo di Office 365 è un log di controllo unificato. Perché un log di controllo unificato? Poiché gli eventi provenienti dalla maggior parte dei servizi di Office 365 in cui si esegue la sottoscrizione dell'organizzazione vengono registrati in un singolo log di controllo che è possibile ricercare. Questo significa che è possibile cercare l'attività di utenti e amministratori in questi servizi:</span><span class="sxs-lookup"><span data-stu-id="ff35d-p102">The Office 365 audit log is a unified audit log. Why a unified audit log? Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search. That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="ff35d-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ff35d-111">SharePoint</span></span>
- <span data-ttu-id="ff35d-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="ff35d-112">OneDrive</span></span>
- <span data-ttu-id="ff35d-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="ff35d-113">Exchange</span></span>
- <span data-ttu-id="ff35d-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff35d-114">Azure Active Directory</span></span>
- <span data-ttu-id="ff35d-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff35d-115">Microsoft Teams</span></span>
- <span data-ttu-id="ff35d-116">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ff35d-116">eDiscovery</span></span>
- <span data-ttu-id="ff35d-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="ff35d-117">Power BI</span></span>
- <span data-ttu-id="ff35d-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="ff35d-118">Yammer</span></span>
- <span data-ttu-id="ff35d-119">Sway</span><span class="sxs-lookup"><span data-stu-id="ff35d-119">Sway</span></span>
- <span data-ttu-id="ff35d-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="ff35d-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="ff35d-121">Configurare il controllo</span><span class="sxs-lookup"><span data-stu-id="ff35d-121">Set up auditing</span></span>
  
<span data-ttu-id="ff35d-122">Prima di eseguire la ricerca nel registro di controllo di Office 365, è necessario eseguire alcune operazioni.</span><span class="sxs-lookup"><span data-stu-id="ff35d-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="ff35d-123">[Attivare la ricerca del registro di controllo](turn-audit-log-search-on-or-off.md) per avviare la registrazione di eventi che è possibile cercare</span><span class="sxs-lookup"><span data-stu-id="ff35d-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="ff35d-124">[Abilitare il controllo delle cassette postali](enable-mailbox-auditing.md) in modo da poter cercare gli eventi relativi alle cassette postali. ad esempio, quando un utente accede alla propria cassetta postale o Elimina gli elementi dalla cartella elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="ff35d-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="ff35d-125">Eseguire ricerche nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="ff35d-125">Search the audit log</span></span>
  
<span data-ttu-id="ff35d-126">Dopo aver attivato il controllo, è possibile eseguire la ricerca di centinaia di singoli tipi di eventi provenienti da più servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff35d-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="ff35d-127">[Eseguire una ricerca nel registro di controllo per le](search-the-audit-log-in-security-and-compliance.md) attività di utenti e amministratori</span><span class="sxs-lookup"><span data-stu-id="ff35d-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="ff35d-128">[Comprendere le proprietà dettagliate](detailed-properties-in-the-office-365-audit-log.md) di ogni record di controllo incluso nei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="ff35d-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="ff35d-129">[Ricerca di attività correlate a eDiscovery](search-for-ediscovery-activities-in-the-audit-log.md) eseguite da amministratori e responsabili della conformità</span><span class="sxs-lookup"><span data-stu-id="ff35d-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
