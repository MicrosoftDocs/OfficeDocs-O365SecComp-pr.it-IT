---
title: Resilienza dei dati di Exchange di Office 365
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
description: Spiegazione dei vari aspetti della resilienza dei dati all'interno di Exchange Online e Office 365.
ms.openlocfilehash: 8d0448a95f010b766faf852a374513a1c2da61fa
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530694"
---
# <a name="exchange-online-data-resiliency-in-office-365"></a>Resilienza dei dati in linea di Exchange in Office 365

## <a name="introduction"></a>Introduzione
Esistono due tipi di danneggiamento che possono influire su un database di Exchange: danneggiamento fisico, che può essere causato da problemi hardware (in particolare, hardware di archiviazione), e danneggiamento logico che si verifica a causa di altri fattori. In generale, esistono due tipi di danneggiamento logico che possono verificarsi all'interno di un database di Exchange: 
- **Danneggiamento logico di database** - corrisponde a checksum di pagina di database, ma i dati nella pagina non sono corrette logicamente. Ciò può verificarsi quando il motore di database (il motore di ESE (Extensible Storage)) tenterà di scrivere una pagina del database e anche se il sistema operativo restituisce un messaggio di conferma, i dati non vengono sia mai scritti su disco o viene scritto nella posizione errata. Questa operazione viene definita una *perdita flush*. ESE include numerose funzionalità e misure di protezione che sono progettati per evitare il danneggiamento fisico di un database e altri scenari di perdita di dati. Per impedire la perdita di dati di scaricamenti perse, ESE include un meccanismo di rilevamento flush perse nel database con una caratteristica (ripristino singola pagina) per correggere i dati. 
- **Danneggiamento logico dell'archivio** - dati viene aggiunto, eliminato o modificato in modo che l'utente non si aspettano. Questi casi sono in genere causati da applicazioni di terze parti. In genere è danneggiato preferibile che l'utente visualizza il danneggiamento. Archivio di Exchange considera la transazione che ha generato il danneggiamento logico da una serie di operazioni MAPI valide. Le funzionalità di [Archiviazione sul posto](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in Exchange Online è assicurata dall'archivio danneggiamento logico (perché per impedire che il contenuto viene eliminato definitivamente da un utente o di un'applicazione). 

Exchange Online consente di eseguire verifiche di coerenza diversi nel file di registro replicati durante l'ispezione di registro sia la riesecuzione del registro. Tali verifiche di coerenza evitare il danneggiamento fisico la replica dal sistema. Ad esempio, durante l'ispezione di registro, non esiste una verifica di integrità fisica che consente di verificare il file di registro e convalida che checksum registrato nel file di registro corrisponda checksum generato in memoria. Inoltre, l'intestazione del file di registro viene esaminato per verificare che la firma del file di log registrata nell'intestazione del registro corrisponda a quello del file di registro. Durante la riproduzione dei registri, il file di registro viene sottoposto a un'ulteriore esame minuzioso. Ad esempio, l'intestazione del database contiene inoltre la firma di registro che viene confrontata con firma del file di registro per verificare che devono essere uguali. 

Protezione da danneggiamento dei dati delle cassette postali in Exchange Online è possibile utilizzare Exchange Native Data Protection, una strategia di resilienza che utilizza la replica a livello di applicazione in più server e più centri dati con altri caratteristiche che consentono di proteggere i dati da persi a causa di danneggiamento o per altri motivi. Tali caratteristiche includono funzionalità native gestite da Microsoft o l'applicazione di Exchange Online, ad esempio:

- [Gruppi di disponibilità dei dati](https://docs.microsoft.com/exchange/back-up-email)
- Correzione singolo Bit 
- Analisi del Database in linea 
- Rilevamento Flush perso 
- Ripristino di singola pagina 
- Servizio di replica delle cassette postali 
- Controlli di File di registro 
- Distribuzione in resiliente File System 

Per ulteriori informazioni sulle funzionalità native sopra elencati, fare clic sui collegamenti sopra e vedere di seguito per ulteriori informazioni e per informazioni dettagliate sugli elementi senza collegamenti ipertestuali. Oltre a queste funzionalità native, Exchange Online include anche funzionalità di resilienza dei dati che i clienti possono gestire, ad esempio: 
- [Ripristino di un elemento singolo (impostazione predefinita)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [Conservazione in locale e per controversia legale](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [Eliminato il mantenimento degli elementi e le cassette postali Soft-Deleted (sia abilitata per impostazione predefinita)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a>Gruppi di disponibilità del database 
Ogni database delle cassette postali in Office 365 è ospitata in un [gruppo di disponibilità del database (DAG)](https://docs.microsoft.com/exchange/back-up-email) e replicate in diverse aree geografiche separata centri dati all'interno dell'area stessa. La configurazione più comune è quattro copie del database in quattro datacenter; Tuttavia, alcune aree hanno un numero inferiore datacenter (database vengono replicati in tre datacenter in India e due datacenter in Australia e Giappone). Ma in tutti i casi, tutti i database delle cassette postali con quattro copie che vengono distribuite su più centri dati, in modo da assicurare che dati delle cassette postali sono protetto da software, hardware e anche gli errori di Data Center. 

Da questi quattro copie tre di questi sono configurati per la disponibilità elevata. La quarta copia viene configurata come una [copia del database ritardate](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies). La copia ritardata del database non è progettata per il ripristino di singole cassette postali o il ripristino di elementi della cassetta postale. Lo scopo è per fornire un meccanismo di ripristino per l'evento raro del livello di sistema e grave danneggiamento logico. 

Copia ritardata del database in Exchange Online devono essere configurate con un intervallo di riesecuzione di sette giorni log file. Inoltre, il gestore di ritardo di riesecuzione di Exchange è abilitato per offrire dinamico log file di riproduzione per le copie ritardate consentire di copie del database ritardate ripristino automatico e gestire le dimensioni dei file registro. Sebbene del database ritardate copie vengono utilizzate in Exchange Online, è importante tenere presente che non sono garantiti backup punto nel tempo. Copia ritardata del database in Exchange Online hanno una soglia di disponibilità, in genere circa il 90%, a causa di periodi di cui si perde un errore del disco, la copia ritardata diventare un'elevata disponibilità il disco contenente una copia ritardata copiare (a causa di automatica di riproduzione), nonché come i periodi in cui la copia ritardata del database è compilando nuovamente il Registro di riesecuzione delle code. 

## <a name="transport-resilience"></a>Resilienza del trasporto 
Exchange Online include due funzionalità di resilienza trasporto primario: ridondanza Shadow e rete sicura. Ridondanza shadow consente di mantenere una copia di riserva di un messaggio mentre è in corso. Rete sicura consente di mantenere una copia di riserva di un messaggio dopo che il messaggio viene recapitato con successo. 

Con ridondanza Shadow, ogni server di trasporto di Exchange Online crea una copia di ogni i messaggi ricevuti prima riconosce correttamente la ricezione del messaggio al server di invio. In questo modo tutti i messaggi nella pipeline di trasporto ridondanti in transito. Se Exchange Online determina che il messaggio originale è stato perso in transito, ridistribuisce una copia di riserva del messaggio. 

Rete sicura è una coda di trasporto associato al servizio di trasporto in un server cassette postali. Questa coda vengono archiviate copie dei messaggi che sono state elaborate correttamente dal server. Quando un errore di database o un server cassette postali richiede l'attivazione di una copia del database delle cassette postali non aggiornata, i messaggi nella coda di rete sicura vengono automaticamente inviati di nuovo alla nuova copia attiva del database delle cassette postali. Rete sicura è anche ridondanti, eliminando trasporto come un singolo punto di errore. Viene utilizzato il concetto di una rete sicura principale e una rete sicura ombreggiatura in cui se la rete sicura principale non è disponibile per più di 12 ore, inviare nuovamente le richieste di diventano le richieste di reinvio ombreggiatura e i messaggi vengono nuovamente recapitati dalla rete sicura ombreggiatura.

Resubmissions messaggi dalla rete sicura vengono avviati automaticamente dal componente Active Manager del servizio replica di Microsoft Exchange che gestisce DAG e cassetta postale di copie del database. Nessuna azione manuale vengono richiesto di reinvio dei messaggi dalla rete sicura. 

## <a name="single-bit-correction"></a>Correzione singolo Bit 
ESE include un meccanismo per rilevare e risolvere gli errori CRC di bit singolo (ovvero bit singolo capovolge) che derivano da errori hardware (e in quanto tale che essi rappresentano danneggiamento fisico). Quando si verificano tali errori, li corregge automaticamente ESE e registri un evento nel registro eventi. 

## <a name="online-database-scanning"></a>Analisi del Database in linea 
Database online analisi (noto anche come *checksumming database*) è il processo in cui un ESE utilizza una verifica di coerenza database per ogni pagina di lettura e controllare danneggiato pagina. Lo scopo principale consiste nel rilevare danneggiamento fisico e cancellazioni perse che potrebbero non essere Guida rilevati dalle operazioni transazionali. Analisi dei database esegue inoltre operazioni successive all'archivio arresto anomalo del sistema. Spazio può essere compromesso a causa di arresti anomali e analisi dei database in linea consente di trovare e consente di recuperare spazio perso. Il sistema è progettato partendo dal presupposto che tutti i database vengono esaminati completamente una volta ogni sette giorni. 

## <a name="lost-flush-detection"></a>Rilevamento Flush perso 
Si verifica uno svuotamento perso durante un'operazione di scrittura del database che il sistema operativo/sottosistema del disco restituito come completata non effettivamente scritte a disco o è stato scritto nella posizione errata. Perso risolte flush può risultato di danneggiamento logiche dei database, in modo per evitare che perse scaricamenti causando la perdita di dati, ESE include un meccanismo di rilevamento flush perso. Quando le pagine del database vengono scritti copie passive, viene eseguita una verifica di scaricamenti perse sulla copia attiva. Se viene rilevato un scaricamento perso, ESE può ripristinare il processo di utilizzo di una pagina applicazione di patch processo. 

## <a name="single-page-restore"></a>Ripristino di singola pagina 
Ripristino di singola pagina, ovvero *applicate patch per pagina*, è un processo automatico in pagine di database danneggiato sono state sostituite da copie integre da una replica integra. Il processo di ripristino di una pagina danneggiato varia a seconda che la copia del database attivo o passivo. Quando una copia del database attivo viene rilevata una pagina danneggiata, è possibile copiare una pagina da una delle proprie repliche fornita la pagina che viene copiata viene aggiornata. Questa operazione viene eseguita mediante l'inserimento di una richiesta per la pagina nel flusso di log, che costituisce la base di replica del database delle cassette postali. Non appena una replica rileva la richiesta della pagina che viene inviata una copia della pagina per la copia del database richiedente. Ripristino di singola pagina offre inoltre un meccanismo di comunicazione asincrona per l'oggetto attivo richiedere una pagina di repliche, anche se le repliche sono attualmente non in linea. 

In caso di danneggiamento in una copia passiva del database, tra cui una copia ritardata del database, dal momento che queste copie sono sempre dietro le copie attive, in genere consigliabile copiare qualsiasi pagina dalla copia attiva una copia passiva. Una copia passiva del database è dalla natura altamente disponibile, in modo che durante la pagina applicazione di patch processo, viene sospesa la riproduzione di registro, ma la copia registro continua. La copia passiva del database consente di recuperare una copia della pagina danneggiata dalla copia attiva, si attende che il file di registro che soddisfi il requisito di generazione massima registro richiesti viene copiato esaminato e quindi le patch della pagina danneggiata. Una volta che la pagina è stata aggiornata, riprende la riproduzione dei registri. Il processo è lo stesso per la copia ritardata del database, ad eccezione del fatto che il database ritardato riesegue innanzitutto tutti i file di registro necessari ottenere uno stato di inserimento. 

## <a name="mailbox-replication-service"></a>Servizio di replica delle cassette postali 
Spostamento delle cassette postali è una parte essenziale di gestione di un servizio di posta elettronica su larga scala. Sono sempre aggiornate tecnologie e gli aggiornamenti hardware e la versione di gestione di, in modo con un'efficace limitate sistema che consente l'i tecnici eseguire questa operazione mantenendo la cassetta postale Sposta trasparente per gli utenti (verificando rimanere in linea nel corso del processo) è chiave e controllando che il processo di scalabilità normalmente come ottenere di cassette postali di grandi dimensioni. 

Exchange Mailbox Replication Service (MRS) è responsabile per lo spostamento delle cassette postali tra database. Durante lo spostamento MRS della coerenza su tutti gli elementi nella cassetta postale. Se viene rilevato un problema di coerenza, MRS verrà correggere il problema o ignorare gli elementi danneggiati, eliminando danneggiamento dalla cassetta postale. 

Poiché MRS è un componente di Exchange Online, è possibile modificare il relativo codice in modo da indirizzo nuove forme di danneggiamento rilevati in futuro. Ad esempio, se viene rilevato un problema di coerenza MRS non è in grado di risolvere, è possibile analizzare il danneggiamento, modificare il codice MRS e correggere il problema (se è comprendere come). 

## <a name="log-file-checks"></a>Controlli di File di registro 
Tutti i file di registro delle transazioni generati da un database di Exchange essere sottoposti a diverse forme di verifiche di coerenza. Quando viene creato un file di registro, fine prima cosa viene scritto un modello di bit e quindi viene eseguita una serie di operazioni di scrittura del registro. In questo modo Exchange Online per l'esecuzione di una serie di controlli, scaricamento persa, CRC e altri controlli per convalidare ogni file di registro in cui vengono scritti e nuovamente viene replicato. 

## <a name="deployment-on-resilient-file-system"></a>Distribuzione in resiliente File System 
Per evitare il danneggiamento non si verificherà il livello di file system, Exchange Online viene distribuito su partizioni resiliente File System (ReFS) per fornire funzionalità migliorate di ripristino. ReFS è un file system in Windows Server 2012 e versioni successive è progettato per essere più resiliente dal danneggiamento dei dati che consentono di ottimizzare l'integrità e disponibilità dei dati. In particolare, ReFS permette di utilizzare miglioramenti in modo che sia aggiornati i metadati che offre maggiore protezione per i dati e si riduce il caso di danneggiamento dei dati. Checksum viene inoltre utilizzato per verificare l'integrità dei dati dei file e metadati assicurarsi che il danneggiamento dei dati sono facilmente rilevati e riparati. 

Exchange Online sfrutta i vantaggi ReFS diversi: 
- Resilienza ulteriori sull'integrità dei dati significa meno interventi di danneggiamento dei dati. Riduzione del numero di problemi di danneggiamento significa meno del reseeding del database non necessari. 
- Checksum in esecuzione sui metadati abilitazione rilevamenti casi danneggiamento più rapidamente e in modo più deterministico, che consente di correggere i dati dei clienti danneggiamento prima che si verificano errori grigi per i volumi di dati.
- Progettato per funzionare anche con estremamente grandi quantità di dati, ovvero petabyte e grandi dimensioni, ovvero senza impatto sulle prestazioni
- Supporto per altre funzionalità utilizzati da Exchange Online, ad esempio BitLocker. 

Exchange Online anche ai vantaggi da altre caratteristiche ReFS: 
- **Integrità (integrità flussi)** - ReFS archivia i dati in modo da protegge da molti degli errori comuni in genere possono causare perdite di dati. Ricerca di Office 365 utilizza i flussi di integrità al fine di facilitare il rilevamento di danneggiamento anticipati su disco e checksum di contenuto del file. La caratteristica riduce inoltre risolte danneggiamento causate da "Strappata scrive" (durante un'operazione di scrittura non viene completata a causa di interruzioni dell'alimentazione, ecc.). 
- **Disponibilità (salvataggio)** - ReFS assegna una priorità la disponibilità dei dati. In passato, file System spesso sono soggetti a danneggiamento dei dati che richiede il sistema disconnesso per il ripristino. Sebbene rari caso danneggiamento implementa ReFS di salvataggio, una caratteristica che consente di rimuovere i dati danneggiati dallo spazio dei nomi in un volume live e garantisce che una buona dati non hanno conseguenze negative dai dati danneggiati non ripristinabile. Applicare la caratteristica di salvataggio e isolare il danneggiamento dei dati di Exchange Online volumi del database significa che è possibile gestire in modo non interessato database su un volume danneggiato ottimale tra il momento dell'azione danneggiamento e il ripristino. In questo modo aumenta la disponibilità del database che normalmente potrebbe essere influenzate dalle quali problemi di danneggiamento del disco. 