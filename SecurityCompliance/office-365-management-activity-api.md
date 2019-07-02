---
title: API Office 365 Management Activity
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
description: Un breve riepilogo sull'API di attività di gestione di Office 365.
ms.openlocfilehash: 759a8c7035c02ddf17d18080629a715a5525c4d6
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622506"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="16b0a-103">API Office 365 Management Activity</span><span class="sxs-lookup"><span data-stu-id="16b0a-103">Office 365 Management Activity API</span></span>

<span data-ttu-id="16b0a-104">Microsoft fornisce Reporting Services che è possibile utilizzare per ottenere informazioni transazionali aggregate sul tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="16b0a-104">Microsoft provides reporting services you can use to obtain aggregated transactional information about your Office 365 tenant.</span></span> <span data-ttu-id="16b0a-105">L' [API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) utilizza una struttura RESTful standard del settore e OAuth V2 per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="16b0a-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) uses an industry-standard RESTful design and OAuth v2 for authentication.</span></span> <span data-ttu-id="16b0a-106">In questo modo è più facile iniziare a sperimentare con il recupero dei dati e l'ingestione in strumenti e applicazioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="16b0a-106">This makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="16b0a-107">L'API fornisce un feed di dati con informazioni sull'utente, l'amministratore, le operazioni e le attività di sicurezza in Office 365.</span><span class="sxs-lookup"><span data-stu-id="16b0a-107">The API provides a data feed with information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="16b0a-108">I dati possono essere conservati per scopi normativi oppure combinati con i dati di log acquistati da un'infrastruttura locale o da altre origini.</span><span class="sxs-lookup"><span data-stu-id="16b0a-108">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources.</span></span> <span data-ttu-id="16b0a-109">In questo modo viene creata una soluzione di monitoraggio per le operazioni, la sicurezza e la conformità all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="16b0a-109">This helps build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="16b0a-110">L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Office 365 e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="16b0a-110">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="16b0a-111">L'API fornisce uno schema di controllo coerente con oltre 10 campi comuni in tutti i servizi.</span><span class="sxs-lookup"><span data-stu-id="16b0a-111">The API provides a consistent audit schema with over 10 fields common across all the services.</span></span> <span data-ttu-id="16b0a-112">L'API consente alle organizzazioni di semplificare le connessioni tra gli eventi e consente di creare nuovi modi per ragionare sui dati.</span><span class="sxs-lookup"><span data-stu-id="16b0a-112">The API allows organizations to make easy connections between events, and enables new ways to reason over the data.</span></span>

<span data-ttu-id="16b0a-113">Dozzine di fornitori di software indipendenti (ISV) hanno collaborato con Microsoft e hanno costruito soluzioni basate sull'API.</span><span class="sxs-lookup"><span data-stu-id="16b0a-113">Dozens of Independent Software Vendors (ISVs) partnered with Microsoft and have built solutions based on the API.</span></span> <span data-ttu-id="16b0a-114">Alcune soluzioni sono incentrate unicamente sui dati di Office 365 e su altri dati di origine provenienti da più provider cloud e sistemi locali per creare una visualizzazione unificata delle attività relative a operazioni, sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="16b0a-114">Some solutions focus solely on Office 365 data and others source data from multiple cloud providers and on-premises systems to create a unified view of operations, security, and compliance-related activity.</span></span> 

<span data-ttu-id="16b0a-115">Per ulteriori informazioni, vedere la Guida di [riferimento all'API dell'attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="16b0a-115">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
