---
title: Monitoraggio e autoGuarigione di Office 365
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Informazioni sulle funzionalità di monitoraggio e correzione automatica di Office 365.
ms.openlocfilehash: 799c4dc97e9cc88dcc77f17b0f11ab76525012d9
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090518"
---
# <a name="office-365-monitoring-and-self-healing"></a>Monitoraggio e autoGuarigione di Office 365
Data la scala di Office 365, sarebbe impossibile mantenere i dati dei clienti resilienti e sicuri da malware senza il monitoraggio integrato che è completo, avvisando che è intelligente e auto-guarigione che è veloce e affidabile. Il monitoraggio di un insieme di servizi alla scala di Office 365 è molto impegnativo. Sono state introdotte nuove mentalità e metodologie che sono state necessarie per creare e gestire il servizio in un ambiente globale connesso. L'approccio di monitoraggio tradizionale della raccolta e del filtro dei dati è stato rimosso per creare avvisi per un approccio basato sull'analisi dei dati. prendere segnali e creare fiducia nei dati e quindi utilizzare l'automazione per recuperare o risolvere il problema. Questo approccio consente di eliminare gli umani dall'equazione di ripristino, che rende le operazioni meno onerose, veloci e meno soggette a errori. 

Fondamentale per il monitoraggio di Office 365 è una raccolta di tecnologie che comprendono il motore Data Insights, basato su Azure, SQL Azure e la tecnologia dei [database di flusso open source](http://cassandra.apache.org/). È stato creato per raccogliere e aggregare i dati e raggiungere conclusioni. Attualmente, elabora più di 500 milioni eventi all'ora da oltre 100.000 server (~ 15 TB al giorno) sparsi in decine di datacenter in molte aree geografiche e questi numeri sono in crescita. 

Office 365 utilizza il *monitoraggio esterno*, che prevede la creazione di transazioni sintetiche per testare tutto ciò che è importante. Ad esempio, in Exchange Online ogni scenario verifica tutti i database di tutto il mondo ogni cinque minuti in modo sparso, fornendo una copertura continua di tutto ciò che vive nel sistema. Da più posizioni vengono eseguite 250 milioni transazioni di test giornalieri per creare una linea di base o un battito cardiaco robusto per il servizio. 

Office 365 utilizza anche il concetto di *Red Alert*, che riduce tutti i segnali di monitoraggio provenienti da tutte le macchine nei nostri centri dati a un elemento gestibile da un essere umano. Il concetto è piuttosto semplice: se succede qualcosa su più segnali, deve esserci qualcosa da fare. Non si tratta di creare la sicurezza in un unico segnale, bensì di avere una fedeltà ragionevole per ogni segnale, in modo da ottenere una maggiore accuratezza. Questo sistema di monitoraggio è talmente potente che non è presente il personale 24x7 che guarda i nostri monitor; tutto quello che abbiamo è la macchina che si risveglia se rileva un problema, nel qual caso verrà pagina il personale di chiamata appropriato, o più spesso come è il caso, sarà solo andare avanti e risolvere il problema. Dopo aver avviato la raccolta dei segnali e la creazione di avvisi rossi, è possibile avviare la triangolazione in tutte le partizioni di servizio. 

In base alla combinazione tra l'avviso di errore e gli avvisi rossi, questo avviso indica esattamente quali componenti potrebbero avere un problema e che il sistema tenterà di risolvere il problema da solo riavviando un server cassette postali. 

Oltre alle funzionalità di autoguarigione, ad esempio il ripristino di una singola pagina, Exchange Online include diverse funzionalità che interessano il monitoraggio e la guarigione automatica, che si concentra sulla conservazione dell'esperienza degli utenti finali. Queste funzionalità includono la *disponibilità gestita*, che fornisce azioni di monitoraggio e ripristino incorporate, e il reseeding automatico, che ripristina automaticamente la ridondanza dei database dopo un errore del disco. 

## <a name="managed-availability"></a>Disponibilità gestita 
La disponibilità gestita fornisce una soluzione per il ripristino e il controllo dell'integrità nativo che monitora e protegge l'esperienza dell'utente finale mediante azioni orientate al ripristino. La disponibilità gestita è l'integrazione delle azioni di monitoraggio e ripristino incorporate con la piattaforma a disponibilità elevata di Exchange. È stato creato per rilevare e recuperare i problemi non appena si verificano e vengono scoperti dal sistema. A differenza delle soluzioni e delle tecniche di monitoraggio esterne precedenti per Exchange, la disponibilità gestita non tenta di identificare o comunicare la causa principale di un problema. Si concentra invece sugli aspetti di ripristino che si riferiscono a tre aree principali dell'esperienza dell'utente finale: 
- **Disponibilità** : gli utenti possono accedere al servizio? 
- **Latenza** -come è l'esperienza per gli utenti? 
- **Errori** : gli utenti sono in grado di realizzare ciò che desiderano? 

La disponibilità gestita è una funzionalità interna che viene eseguita su ogni server di Office 365 in cui è in esecuzione Exchange Online. Esegue il polling e analizza centinaia di metriche di integrità ogni secondo. Se si verifica un errore, la maggior parte delle volte viene risolta automaticamente. Tuttavia, saranno sempre presenti problemi che la disponibilità gestita non sarà in grado di risolvere autonomamente. In questi casi, la disponibilità gestita escrescerà il problema in un team di supporto di Office 365 tramite la registrazione di eventi. 

## <a name="autoreseed"></a>Reseeding automatico 
I server Exchange Online vengono distribuiti in una configurazione in cui vengono archiviati più database e i relativi flussi di log sullo stesso disco non RAID. Questa configurazione viene spesso definita solo come *un gruppo di dischi* (JBOD) perché non vengono utilizzati meccanismi di ridondanza dello spazio di archiviazione, ad esempio RAID, per duplicare i dati nel disco. Quando un disco ha esito negativo in un ambiente JBOD, i dati del disco sono persi. 

Date le dimensioni di Exchange Online e il fatto che è distribuito all'interno di esso sono milioni di unità disco, gli errori dell'unità disco sono un'occorrenza normale in Exchange Online. Infatti, più di 100 hanno esito negativo ogni giorno. Quando un disco ha esito negativo in una distribuzione aziendale locale, è necessario che un amministratore sostituisca manualmente il disco non riuscito e ripristini i dati interessati. In una distribuzione del cloud le dimensioni di Office 365, con operatori (amministratori cloud) che sostituiscono manualmente i dischi non è né pratico né economicamente fattibile. 

Il reseeding automatico, o *il reseeding automatico*, è una funzionalità che è la sostituzione di quella che è in genere azione basata sull'operatore in risposta a un errore del disco, un evento di danneggiamento del database o un altro problema che richiede il reseeding di una copia del database. Il reseeding automatico è stato creato per ripristinare automaticamente la ridondanza dei database dopo un errore del disco utilizzando dischi di riserva che sono stati sottoposta a provisioning nel sistema. Se un disco ha esito negativo, le copie del database archiviate su tale disco vengono reseedate automaticamente su un disco di riserva preconfigurato sul server, ripristinando in tal modo la ridondanza. 