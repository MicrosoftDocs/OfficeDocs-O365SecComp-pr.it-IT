---
title: Registrazione interni di Office 365 per progettazione tecnica di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/18/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Informazioni di registrazione come interna per Office 365 Engineering Team works.
ms.openlocfilehash: 1a613584b6b815524435acb20db7a8022d95e3bc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530508"
---
# <a name="internal-logging-for-office-365-engineering"></a>La registrazione interna per Office 365 Engineering
Oltre a eventi e registrare i dati disponibili per i clienti, è disponibile anche un sistema di raccolta dei dati del log interni è disponibile a tecnici di Office 365. Diversi tipi di dati dei registri vengono caricati dal server di Office 365 per un interno, big dati computing servizio denominato Cosmos. Ogni team servizio consente di caricare i registri di controllo dai rispettivi server nel database Cosmos per l'analisi e di aggregazione. Si verifica questo trasferimento di dati tramite una connessione TLS 140-2-convalidato FIPS su approvato in modo specifico porte e protocolli utilizzando uno strumento di automazione proprietarie denominato Office dati caricatore (IAD).

Servizio Team utilizzano Cosmos come un archivio centralizzato per eseguire un'analisi di utilizzo dell'applicazione per misurare le prestazioni del sistema e operative e di ricercare le alterazioni e modelli che potrebbero indicare problemi o problemi di sicurezza. Ogni team servizio carica una linea di base dei registri in Cosmos, a seconda sta cercando di analizzare, che spesso sono incluse:
- Registri eventi
- Registri AppLocker
- Dati sulle prestazioni
- Dati di System Center
- Registrazione dettagli chiamata
- Qualità dei dati di utilizzo
- Registri del Server Web IIS
- Registri di SQL Server
- Dati di registro di sistema
- Registri di controllo di sicurezza

Prima di caricamento dei dati in Cosmos, l'applicazione ODL utilizza un servizio ripulitura offuscare tutti i campi che contengono i dati dei clienti, ad esempio informazioni tenant e informazioni personali dell'utente finale, e sostituire i campi con un valore hash. I registri resi anonimi e hash vengono riscritti e quindi caricati in Cosmos. I team del servizio eseguono query con ambito per i dati in Cosmos per correlazione, avvisi e report. Il periodo di conservazione dei dati del Registro di controllo in Cosmos dipende dal team servizi; la maggior parte dei dati del Registro di controllo viene mantenuti per 90 giorni o più per supportare indagini ai problemi di sicurezza e per soddisfare i requisiti di conservazione alle normative.

Accesso ai dati di Office 365 archiviati in Cosmos è limitato a personale autorizzato. Microsoft limita la gestione delle funzionalità di controllo per la versione ridotta di membri del team responsabili della funzionalità di controllo del servizio. I membri del team non è in grado di modificare o eliminare dati da Cosmos e tutte le modifiche apportate ai meccanismi di registrazione per Cosmos vengono registrate e controllate.

Ogni team servizio accede relativi dati di registro per l'analisi da parte di alcune applicazioni di condurre analisi specifica. Ad esempio, il team di protezione di Office 365 utilizza i dati da Cosmos attraverso un parser proprietarie registro eventi per correlare, avviso e generare report pronti per interventi sui possibili attività sospette nell'ambiente di produzione di Office 365. I report di questi dati vengono utilizzati per correggere le vulnerabilità e per migliorare le prestazioni complessive del servizio. Se un determinato avviso o un report richiede un'ulteriore indagini, personale di assistenza possono richiedere che i dati da importare precedente nel servizio Office 365. Dopo l'accesso specifico da importare da Cosmos è crittografato e personale di assistenza non hanno accesso alle chiavi decrittografia, nel Registro di destinazione viene passato a livello di programmazione tramite un servizio decrittografia che restituisca risultati con ambiti per il personale autorizzato. Le vulnerabilità trovate da questo esercizio segnalate ed effettuata l'escalation all'utilizzo dei canali di gestione degli eventi imprevisti protezione standard di Microsoft.
