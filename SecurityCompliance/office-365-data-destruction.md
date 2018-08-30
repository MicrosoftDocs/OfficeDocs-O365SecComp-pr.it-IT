---
title: Eliminazione dei dati di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Panoramica di criteri di Microsoft relativamente alle riciclo, eliminazione o distruzione di unità disco di Office 365 Data Center e server.
ms.openlocfilehash: c9950be4919520f2f46badaa4a7d4cfce5c55b45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530542"
---
# <a name="office-365-data-destruction"></a>Eliminazione dei dati di Office 365
Microsoft ha criteri Standard di gestione dei dati in grado di risolvere recycle e l'eliminazione delle unità disco e i server non riuscito o ritirare. Prima di utilizzare nuovamente le unità disco in Office 365, Microsoft esegue un processo il filtraggio fisico coerente con National Institute of Standards e pubblicazione speciale tecnologia 800-88 ([SP NIST 800 88 le linee guida per il filtraggio multimediale](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) ). Tutte le unità disco in Office 365 vengono crittografate utilizzando la crittografia a livello di volume BitLocker, in modo che in pratica, non è necessaria la cancellazione 800 88-compatibile con SP NIST. Tuttavia, ancora viene eseguita da Microsoft.

Non è riuscita dischi utilizzati in Office 365 datacenter sono fisicamente eliminato e controllati i passaggi del processo ISO. Il sistema appropriato di eliminazione dipende dal tipo di risorse. Per le unità disco rigido non possono essere cancellate, Microsoft utilizza un processo di eliminazione che elimina il supporto (ad esempio, disintegrates, pulverizes o incinerates) e viene eseguito il rendering ovviamente impossibile realizzare il ripristino dei dati. Microsoft conserva anche tutti i record della distruzione. Microsoft esegue un processo il filtraggio simile nei server che vengono riutilizzati in Office 365. Queste linee guida per comprendere il filtraggio elettronico e fisico.

Unità disco che non possono essere riutilizzate eliminate utilizzando un processo di eliminazione fisica che viene eseguito sul posto all'interno del datacenter che contiene i dischi in corso l'eliminazione. Supporto di archiviazione designato per l'eliminazione è incluso nel Cestini sicuri disponibile in ogni area del centro dati. Ogni station bin sicuro viene monitorato dal controllo video. Una volta che un cassetto cessione raggiunge circa 50% della capacità, il team di servizi di siti contatta il team di protezione fisica per coordinare la rimozione. Personale Services del sito, rimuovere la collocazione di disposizione in escort da un responsabile della sicurezza fino a quando non viene effettuata in un'area di archiviazione protetto in attesa di eliminazione dei dati. Criteri e le procedure per la gestione dei dati è contrassegnato dal dispositivi durante l'eliminazione vengono verificate comprese le procedure per garantire la condizione di una macchina approvata per l'eliminazione.

Nel processo di eliminazione dei dati nel disco prima viene cancellato in modo che sia compatibile con NIST 800-88, se possibile, e quindi viene inserito in un frantumati industriale e fisicamente demolito. Microsoft gestisce la responsabilità per le risorse lasciando datacenter con SP NIST 800 88 coerente pulitura/eliminazione, distruzione delle risorse, la crittografia, precisi inventario, verifica e protezione della catena di controllo durante il trasporto. Questo processo viene monitorato da maggiormente la televisione circuito chiuso e un certificato di distruzione viene inviata al termine.

Microsoft utilizza le unità cancellazione dati da [Soluzioni protocollo Extreme](http://www.enterprisedataerasure.com/) (EPS). EPS in grado di supportare SP NIST 800 88 requisiti per la pulizia e l'eliminazione sicura cancellazione. Prima di pulitura o distruzione, viene creato un inventario per la gestione delle risorse di Microsoft. Se un fornitore viene utilizzato per l'eliminazione, il fornitore fornisce un certificato di distruzione per ogni risorsa eliminata, che viene convalidato il Manager delle risorse.