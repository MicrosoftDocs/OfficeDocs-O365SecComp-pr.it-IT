---
title: Controlli per tecnologia di Office 365
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
description: 'Riepilogo: Panoramica della tecnologia controllo procedure di Microsoft per Office 365.'
ms.openlocfilehash: 2ef04b558f5fa82075d9aa602b83d437aa4b2ee6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530689"
---
# <a name="office-365-technology-controls"></a>Controlli per tecnologia di Office 365 

Microsoft utilizza diversi strumenti e le tecnologie per controllare, gestire e controllare l'accesso ai dati dei clienti di Exchange Online e SharePoint Online, tra cui archivio protetto e archivio protetto cliente, l'autenticazione a più fattori e altro ancora. Yammer che Enterprise utilizza controlli simili, come descritto in [Yammer Enterprise accedere a controlli](office-365-yammer-enterprise-access-controls.md).

Tecnici di Office 365 hanno zero accesso la condizione dati dei clienti di Office 365 e si deve passare attraverso un processo di approvazione che include Microsoft e – se il cliente concede in licenza la funzionalità archivio protetto cliente per Exchange Online e SharePoint Online-cliente approvazione, per poter effettuare l'accesso ai dati dei clienti per le operazioni del servizio. Dopo l'approvazione, gli account amministrativi specifici del servizio sono fornite just-in-time con sufficiente access per eseguire le attività necessarie per la richiesta del servizio.

## <a name="lockbox-and-customer-lockbox"></a>Archivio protetto e archivio protetto cliente
Anche se è molto raro, un cliente potrebbe richiedere assistenza da Microsoft che può esporre un tecnico Microsoft per il contenuto del cliente assistere con un problema da. Per controllare l'accesso a Exchange Online (che include qualsiasi Skype per dati Business archiviati in cassette postali degli utenti (Skype per copertura Business non include Skype riunione trasmissione registrazioni o contenuto caricati in riunioni dagli utenti)) e SharePoint Online (che include OneDrive for Business), Microsoft utilizza un sistema di controllo denominato archivio protetto. Prima di qualsiasi engineer Microsoft può accedere a qualsiasi sistemi Exchange Online o SharePoint Online o dati, è necessario inviare una richiesta di accesso utilizzando l'archivio protetto. Utilizzo dell'archivio protetto è obbligatorio per tutti gli accessi con privilegi elevati per Exchange Online o SharePoint Online.

Archivio protetto elabora le richieste per le autorizzazioni concesse tecnici la possibilità di eseguire operazioni operativi e amministrativi all'interno del servizio. Tecnici invia le richieste attraverso archivio protetto, devono essere approvate dal manager prima engineer acquisire la possibilità di accedere ai dati dei clienti. Al responsabile approvazione, il responsabile è limitata nel tempo e ambito limitato l'accesso ai dati dei clienti per l'utilizzo sul problema del cliente.

Archivio protetto cliente per Office 365 consentono di soddisfare gli obblighi di conformità, ad esempio quelle disponibili in FedRAMP e HIPAA, se è necessario procedure sul posto per le autorizzazioni di accesso esplicito dati. Nell'istanza raro quando un tecnico Microsoft richiede l'accesso ai dati, si concede che l'accesso solo ai dati necessari per risolvere il problema e per un periodo di tempo limitato. Azioni effettuate del supporto tecnico vengono registrate ai fini del controllo e sono accessibili tramite l' [API di attività di gestione di Office 365](https://msdn.microsoft.com/library/office/dn707383.aspx) e [centro conformità e sicurezza](http://protection.office.com/). Archivio protetto cliente inserisce il processo di approvazione di archivio protetto cliente e fornisce la possibilità di controllare l'autorizzazione di Microsoft access al relativo Exchange Online o il contenuto di SharePoint Online per operazioni di servizio.

>**Nota**: cliente archivio protetto è disponibile in [Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software) e come acquistare un componente aggiuntivo, ma manuale azioni devono essere effettuate nell'interfaccia di amministrazione di Office 365 (in impostazioni servizio | Archivio protetto cliente) abilitarla. Per ulteriori informazioni, vedere [Le richieste di archivio protetto clienti di Office 365](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

Tutte le richieste di servizio di Exchange Online e SharePoint Online vengono gestite dal sistema di archivio protetto. E con clienti archivio protetto, passa attraverso il processo di approvazione di archivio protetto qualsiasi operazione di servizio la necessità di eseguire l'accesso a tali servizi con l'esposizione di dati dei clienti e quindi viene attivata l'analisi approvare o rifiutare la richiesta in seguito.
 
*Figura 1 - flusso di lavoro dell'archivio protetto cliente*

Se la richiesta viene rifiutata dal cliente, il responsabile di Microsoft non possono accedere al contenuto del cliente e non sarà in grado di completare l'operazione di servizio. Se la richiesta viene approvata dal cliente, il responsabile di Microsoft sarà limitato in fase di accesso al contenuto del cliente tramite le interfacce di gestione di monitoraggio e vincolata. Con archivio protetto e archivio protetto clienti, tutti gli accessi approvato sono rintracciabili a un solo utente, effettuare ingegneri responsabile per la modalità di gestione dei dati dei clienti.

## <a name="just-in-time-access"></a>Access-in-Time
Microsoft utilizza il principio dell'accesso-in-time (JIT) per Office 365 per ridurre ulteriormente il rischio di attacchi laterali e manomissioni credenziali. JIT rimuove persistent accesso amministrativo ai servizi e i diritti viene sostituito con la possibilità di elevare a tali ruoli su richiesta. Rimozione dei diritti persistenti da parte degli amministratori assicura che le credenziali siano disponibili solo quando sono necessarie e consente di rimuovere i rischi per la società in caso di furto di credenziali.

Il modello di accesso JIT richiede gli ingegneri possono richiedere privilegi elevati per un periodo limitato eseguire le attività amministrative. Inoltre, OCEs utilizzare account temporanei creati con password complesse generate dal computer e la concessione solo i ruoli che consentono di eseguire le attività necessarie. Ad esempio, accesso amministrativo concesso dall'archivio protetto è ora associato e la quantità di tempo viene concesso l'accesso dipende dal ruolo richiesto. Un responsabile di specifica la durata di tempo di accesso che durante la richiesta al sistema dell'archivio protetto. Il sistema dell'archivio protetto verrà respinta richieste dove il tempo richiesto supera il limite massimo consentito di tempo per l'elevazione. Dopo la scadenza della richiesta di elevazione di privilegi, viene rimosso l'accesso amministrativo e l'account temporaneo è scaduto.

Autorizzati e approvata per l'accesso (ad esempio, eseguire il debug di un sistema), gli ingegneri possono ricevano una password di amministrazione utilizzo occasionale generato dal sistema di autorizzazione ogni volta che viene approvata una richiesta per l'accesso con privilegi elevato. Questa password viene copiata dal tecnico in una password sicura, distinto dalle credenziali del responsabile per l'ambiente aziendale Microsoft ed è utile solo per la sessione di cui è stata approvata l'accesso con privilegi elevato.

## <a name="constrained-management-interfaces"></a>Interfacce di gestione vincolata
OCEs utilizzare due interfacce di gestione per eseguire attività amministrative: Desktop remoto tramite gateway di servizi Terminal protetto (STG) e Remote PowerShell. In questi gestione interfacce sono disponibili i criteri di software e i controlli di accesso effettuare notevoli limitazioni possono essere eseguite le applicazioni e i comandi e i cmdlet sono disponibili. 

Server di Office 365 limitare sessioni simultanee a un amministratore di team per ogni servizio sessione, per ogni server. Stg sono configurati per consentire a una singola sessione simultanea per gli utenti e non consentono più sessioni. Stg consentono agli amministratori di team del servizio di Office 365 per connettersi a più server contemporaneamente, utilizzando una singola sessione per ogni server, in modo che gli amministratori possono eseguire in modo efficace loro compiti. Gli amministratori del servizio team privi di tutte le autorizzazioni su stg se stessi. Lo stg viene utilizzato solo per attivare l'autenticazione a più fattori (MFA) e requisiti di crittografia. Dopo che l'amministratore del team del servizio si connette a uno specifico server attraverso un STG, il server specifico determinerà una limitazione per sessione di uno per amministratore.

Limitazioni di utilizzo e i requisiti di connessione e la configurazione per il personale di Office 365 vengono stabiliti i criteri di gruppo Active Directory. Questi criteri sono le seguenti caratteristiche:
- Stg sono configurati per utilizzare solo [FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 crittografia convalidati
- Sessioni stg sono configurate per disconnettere dopo 30 minuti di inattività
- Sessioni stg sono configurate per l'accesso automatico dopo 24 ore

Connessioni a stg richiedono inoltre MFA utilizzando una smart card fisica separata e un account distinto dai credenziali aziendali del responsabile tecnico Microsoft. Tecnici vengono rilasciati diverse smart card per diverse piattaforme e piattaforme di gestione di informazioni riservate vengono utilizzate per garantire spazio di archiviazione sicura delle credenziali. Stg utilizzare criteri di gruppo di Active Directory per controllare chi può accedere al server remoto, il numero di sessioni consentite e le impostazioni di timeout di inattività. Criteri aggiuntivi sono presenti per limitare l'accesso alle applicazioni consentite e per limitare l'accesso a Internet.

Oltre all'accesso remoto utilizzando appositamente configurati STG, Exchange Online consente agli utenti con il ruolo di responsabile tecnico operazioni del servizio di accedere a determinate funzionalità amministrative sui server di produzione utilizzando PowerShell remoto. A tale scopo, l'utente deve essere autorizzato per l'accesso in sola lettura (debug) per l'ambiente di produzione di Office 365. Acquisizione di privilegi è abilitata allo stesso modo sia abilitata per stg tramite il processo dell'archivio protetto.

Per l'accesso remoto, non esiste un indirizzo IP virtuale con carico bilanciato in ogni centro dati che funge da un singolo punto di accesso. I cmdlet di PowerShell remoto che possono essere eseguiti sono in base al principio dei privilegi livello identificato nell'attestazione access ottenuta durante l'autenticazione. Questi cmdlet sono le funzionalità amministrative solo che possono accedere ed eseguita dagli utenti per connettersi utilizzando questo metodo. Remote PowerShell viene utilizzato per limitare l'ambito dei comandi disponibili per il tecnico che si basa il livello di accesso concesso tramite il processo dell'archivio protetto. Ad esempio, in Exchange Online, Get-Mailbox potrebbe essere disponibile, ma potrebbe non essere Set-Mailbox.
