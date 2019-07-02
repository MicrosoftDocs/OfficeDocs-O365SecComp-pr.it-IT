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
# <a name="office-365-management-activity-api"></a>API Office 365 Management Activity

Microsoft fornisce Reporting Services che è possibile utilizzare per ottenere informazioni transazionali aggregate sul tenant di Office 365. L' [API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) utilizza una struttura RESTful standard del settore e OAuth V2 per l'autenticazione. In questo modo è più facile iniziare a sperimentare con il recupero dei dati e l'ingestione in strumenti e applicazioni di visualizzazione. L'API fornisce un feed di dati con informazioni sull'utente, l'amministratore, le operazioni e le attività di sicurezza in Office 365. I dati possono essere conservati per scopi normativi oppure combinati con i dati di log acquistati da un'infrastruttura locale o da altre origini. In questo modo viene creata una soluzione di monitoraggio per le operazioni, la sicurezza e la conformità all'interno dell'organizzazione.

L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Office 365 e Azure Active Directory. L'API fornisce uno schema di controllo coerente con oltre 10 campi comuni in tutti i servizi. L'API consente alle organizzazioni di semplificare le connessioni tra gli eventi e consente di creare nuovi modi per ragionare sui dati.

Dozzine di fornitori di software indipendenti (ISV) hanno collaborato con Microsoft e hanno costruito soluzioni basate sull'API. Alcune soluzioni sono incentrate unicamente sui dati di Office 365 e su altri dati di origine provenienti da più provider cloud e sistemi locali per creare una visualizzazione unificata delle attività relative a operazioni, sicurezza e conformità. 

Per ulteriori informazioni, vedere la Guida di [riferimento all'API dell'attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).
