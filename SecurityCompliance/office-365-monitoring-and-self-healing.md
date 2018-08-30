---
title: Monitoraggio di Office 365 e riparazione automatica
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
description: Informazioni sul monitoraggio e risoluzione automatica dei problemi delle funzionalità di Office 365.
ms.openlocfilehash: ff9471eaa6117ca3d7761549bca9ab629020fe79
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530400"
---
# <a name="office-365-monitoring-and-self-healing"></a>Monitoraggio di Office 365 e riparazione automatica
Dato la scala di Office 365, potrebbe essere impossibile da mantenere i dati dei clienti resiliente e sicuro da malware senza monitoraggio integrate completezza, generazione di avvisi che è intelligente e riparazione automatica che è veloci e affidabili. Monitoraggio di un insieme di servizi in scala di Office 365 è molto complesso. Approcci mentali nuove e le metodologie necessari per introdurre e necessari da creare per utilizzare e gestire il servizio in un ambiente connesso globale completamente nuovo set di tecnologia. Sono stati spostati dal tradizionale approccio di raccolta dati di monitoraggio e filtro di creare avvisi per un approccio basato su analisi dei dati; Taking segnali e creazione di probabilità di tali dati e quindi utilizzare l'automazione per recuperare o di risolvere il problema. Tale approccio consente di richiedere persone da equazione di ripristino, che a sua volta renda operazioni errore meno costosi, più veloci e meno soggetta. 

Concetti fondamentali per Office 365 monitoraggio è un insieme di tecnologie che costituiscono il motore di Insights dati, si basa su Azure SQL Azure e [open source flusso tecnologia di database](http://cassandra.apache.org/). Progettato per raccogliere e aggregare dati e raggiungere conclusioni. Attualmente, l'elaborazione di più di 500 milioni di eventi all'ora da più di 100.000 server (~ 15 TB al giorno) sparse in decine di datacenter in numerose aree e stanno diventando tali numeri. 

Office 365 utilizza *di fuori di monitoraggio*, che prevede la creazione di transazioni sintetiche per testare tutto ciò che ti interessano. Ad esempio, in Exchange Online ogni scenario sta testando ogni database del tutto il mondo ogni cinque minuti in modo sparsi, che fornisce quasi continua copertura di tutti gli elementi presenti nel sistema. Da più posizioni, vengono eseguite transazioni test 250 milioni al giorno per creare una previsione affidabile o heartbeat per il servizio. 

Office 365 utilizza inoltre il concetto di *Avviso rosso*, che viene ridotta verso il basso tutti i segnali monitoraggio da tutti i computer nel nostro centri dati a un elemento gestibile da un essere umano. Il concetto è piuttosto semplice: se un elemento avviene tra più segnali, deve esistere un elemento succedendo. Non è presente sulla creazione di probabilità di un segnale, l'obiettivo è avere fedeltà accettabile per ogni segnale in modo da ottenere maggiore precisione. In questo sistema di monitoraggio è così potente che non è registrato personale 24 / 7 guardare i monitor; è la macchina che non si attiva se viene rilevato un problema, nel qual caso pagina personale nella chiamata appropriato sarà o più spesso come nel caso, verrà semplicemente proseguire e risolvere il problema. Una volta si inizia la raccolta dei segnali e creazione avvisi rossi off li, è possibile avviare triangolazione su tutte le partizioni il nostro servizio. 

In base alla combinazione di avviso di errore e gli avvisi di rosso, questo avviso indica esattamente quali componenti è stato rilevato un problema e che il sistema verrà tentare di risolvere il problema autonomamente mediante il riavvio di un server cassette postali. 

Oltre a riparazione automatica funzionalità, ad esempio il ripristino di singola pagina, Exchange Online include diverse funzionalità che un metodo per eseguire il monitoraggio e la riparazione automatica che riguarda la conservazione dell'utente finale. Tali caratteristiche includono la *Disponibilità gestita*, che offre azioni di monitoraggio e il ripristino incorporate e reseeding automatico, che consente di ripristinare automaticamente ridondanza del database dopo un errore del disco. 

## <a name="managed-availability"></a>Disponibilità gestita 
Disponibilità gestita offre una soluzione di verifica e il ripristino di integrità native che esegue il monitoraggio e la protegge esperienza dell'utente finale di azioni di ripristino. Disponibilità gestita è l'integrazione di azioni di monitoraggio e il ripristino integrate con la piattaforma di disponibilità elevata di Exchange. È progettato per rilevare e risolvere i problemi appena che si verificano e vengono individuate dal sistema. A differenza delle soluzioni di monitoraggio esterne precedente e tecniche di Exchange, disponibilità gestita non tenta di identificare o comunicare le cause radice di un problema. In realtà, si occupa di aspetti ripristino riferite tre aree principali dell'esperienza dell'utente finale: 
- **Disponibilità** - gli utenti possono accedere al servizio? 
- **Latenza** - com'è l'esperienza degli utenti? 
- **Errori** - sono in grado di realizzare ciò che desiderano utenti? 

Disponibilità gestita è una funzionalità interna che viene eseguito in ogni server di Office 365 con Exchange Online. Che esegue il polling e analizza ogni secondo centinaia di metriche di integrità. Se un elemento viene trovato un problema, la maggior parte dei casi è corretto automaticamente. Ma ci sarà sempre problemi disponibilità gestita non saranno in grado di correggere il proprio. In questi casi, disponibilità gestita verrà trasformare il problema a un team di supporto per Office 365 tramite la registrazione degli eventi. 

## <a name="autoreseed"></a>Reseeding automatico 
Server di Exchange Online vengono distribuiti in una configurazione con cui vengono archiviati i flussi di registro e più database nello stesso disco non RAID. Questa configurazione è spesso denominata *semplicemente un gruppo di dischi* (JBOD) perché non meccanismi di ridondanza di archiviazione, ad esempio RAID, vengono utilizzati i dati nel disco. Quando un disco ha esito negativo in un ambiente JBOD, i dati in tale disco vengono persi. 

Determinati le dimensioni di Exchange Online e il fatto che distribuiti in essa contenuti vengono milioni di unità disco, errori del disco rigido sono regolari in Exchange Online. Più di 100, infatti, non ogni giorno. Quando un disco ha esito negativo in una distribuzione aziendale locale, un amministratore deve manualmente sostituire il disco e ripristinare i dati interessati. In una distribuzione cloud le dimensioni di Office 365, con operatori (amministratori cloud) sostituzione manuale dei dischi è pratico né economicamente realizzabile. 

Reseeding automatico o *reseeding automatico*, è una funzionalità che è la sostituzione per le quali è normalmente basati su operatore azione in risposta a un errore del disco, evento danneggiamento dei database o altro problema che richiede un reseeding di una copia del database. Reseeding automatico è progettato per il ripristino automatico ridondanza del database dopo un errore del disco con dischi di riserva sottoposti a provisioning nel sistema. Se un disco non riesce, le copie del database archiviate in tale disco sono automaticamente eseguito il reseeding di dischi di riserva preconfigurato nel server, quindi ripristinare la ridondanza. 