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
ms.openlocfilehash: 3405eaac000111fb5d5f054edcbe6816aa9af9e7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262558"
---
# <a name="office-365-management-activity-api"></a>API Office 365 Management Activity
Microsoft fornisce servizi di Reporting che consentono agli amministratori di ottenere informazioni transazionali aggregate sul tenant di Office 365. L' [API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) utilizza una struttura RESTful standard del settore e OAuth V2 per l'autenticazione, il che rende più facile iniziare a sperimentare il recupero dei dati e a ingerirli in applicazioni e strumenti di visualizzazione. L'API fornisce un feed di dati che include informazioni sull'utente, l'amministratore, le operazioni e le attività di sicurezza in Office 365. I dati possono essere conservati per scopi normativi oppure combinati con i dati di log acquistati da un'infrastruttura locale o da altre origini per creare una soluzione di monitoraggio per operazioni, sicurezza e conformità all'interno dell'organizzazione.

L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Office 365 e Azure Active Directory. L'API fornisce uno schema di controllo coerente con oltre 10 campi che sono in comune in tutti i servizi. Questo consente alle organizzazioni di semplificare le connessioni tra gli eventi e consente di creare nuovi modi per ragionare sui dati. Dozzine di fornitori di software indipendenti (ISV) hanno collaborato con Microsoft e hanno costruito soluzioni basate sull'API. Alcune soluzioni sono incentrate unicamente sui dati di Office 365, mentre altre offrono la possibilità di ingerire dati da più provider cloud e sistemi locali per creare una visualizzazione unificata di tutte le operazioni, la sicurezza e le attività relative alla conformità. Per ulteriori informazioni, vedere la Guida di [riferimento all'API dell'attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).
