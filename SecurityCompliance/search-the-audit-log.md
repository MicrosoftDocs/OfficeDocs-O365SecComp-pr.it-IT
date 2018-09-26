---
title: Cercare il Registro di controllo per l'attività di amministrazione e utente in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 'Il Registro di controllo di Office 365 è un registro di controllo unificato. Perché un controllo unificato accedere? Poiché gli eventi che sta organizzazione la maggior parte dei servizi di Office 365 sottoscrive vengono registrati in un singolo registro di controllo che è possibile eseguire la ricerca. Di conseguenza, che è possibile cercare per le attività di amministrazione in tali servizi e utente:'
ms.openlocfilehash: 230502f331babeef8f89eacce0d19a7756cb96fc
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038029"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="82335-106">Cercare il Registro di controllo per l'attività di amministrazione e utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="82335-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="82335-p102">Il Registro di controllo di Office 365 è un registro di controllo unificato. Perché un controllo unificato accedere? Poiché gli eventi che sta organizzazione la maggior parte dei servizi di Office 365 sottoscrive vengono registrati in un singolo registro di controllo che è possibile eseguire la ricerca. Di conseguenza, che è possibile cercare per le attività di amministrazione in tali servizi e utente:</span><span class="sxs-lookup"><span data-stu-id="82335-p102">The Office 365 audit log is a unified audit log. Why a unified audit log? Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search. That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="82335-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="82335-111">SharePoint</span></span>
- <span data-ttu-id="82335-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="82335-112">OneDrive</span></span>
- <span data-ttu-id="82335-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="82335-113">Exchange</span></span>
- <span data-ttu-id="82335-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="82335-114">Azure Active Directory</span></span>
- <span data-ttu-id="82335-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82335-115">Microsoft Teams</span></span>
- <span data-ttu-id="82335-116">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="82335-116">eDiscovery</span></span>
- <span data-ttu-id="82335-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="82335-117">Power BI</span></span>
- <span data-ttu-id="82335-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="82335-118">Yammer</span></span>
- <span data-ttu-id="82335-119">Sway</span><span class="sxs-lookup"><span data-stu-id="82335-119">Sway</span></span>
- <span data-ttu-id="82335-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="82335-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="82335-121">Impostare il controllo</span><span class="sxs-lookup"><span data-stu-id="82335-121">Set up auditing</span></span>
  
<span data-ttu-id="82335-122">Esiste alcuni aspetti da eseguire prima che è possibile eseguire ricerche nel Registro di controllo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="82335-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="82335-123">[Abilita la ricerca dei registri di controllo](turn-audit-log-search-on-or-off.md) per avviare la registrazione di eventi che è possibile cercare</span><span class="sxs-lookup"><span data-stu-id="82335-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="82335-124">[Abilitare il controllo delle cassette postali](enable-mailbox-auditing.md) in modo che è possibile cercare gli eventi relativi alla cassetta postale. ad esempio quando un utente accede a loro cassette postali o Elimina elementi nella cartella elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="82335-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="82335-125">Cercare i log di controllo</span><span class="sxs-lookup"><span data-stu-id="82335-125">Search the audit log</span></span>
  
<span data-ttu-id="82335-126">Dopo avere attivato il controllo, cercare centinaia di singoli tipi di eventi da più servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="82335-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="82335-127">[Ricerca nel Registro di controllo](search-the-audit-log-in-security-and-compliance.md) per l'attività degli utenti e amministratori</span><span class="sxs-lookup"><span data-stu-id="82335-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="82335-128">[Acquisire familiarità con le proprietà dettagliate](detailed-properties-in-the-office-365-audit-log.md) di ogni controllo record incluso nei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="82335-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="82335-129">[Ricerca di attività correlate ai eDiscovery](search-for-ediscovery-activities-in-the-audit-log.md) eseguita dai responsabili della conformità e gli amministratori</span><span class="sxs-lookup"><span data-stu-id="82335-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
