---
title: Controlli delle tecnologie Office 365
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
description: 'Riepilogo: Panoramica delle procedure di controllo della tecnologia Microsoft per Office 365.'
ms.openlocfilehash: 3fe7f47a2a1903d17c5240a0efec1c2abb94a25d
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090768"
---
# <a name="office-365-technology-controls"></a>Controlli delle tecnologie Office 365 

Microsoft utilizza diversi strumenti e tecnologie per controllare, gestire e verificare l'accesso ai dati dei clienti in Exchange Online e SharePoint Online, tra cui archivio protetto e cassetta del cliente, autenticazione a più fattori e altro ancora. Yammer Enterprise utilizza controlli simili, come descritto in [Yammer Enterprise Access Controls](office-365-yammer-enterprise-access-controls.md).

Gli ingegneri di Office 365 hanno accesso a zero diritti ai dati dei clienti di Office 365 e devono passare attraverso un processo di approvazione che includa sia Microsoft che – se il cliente concede la funzionalità di archivio protetto dei clienti per Exchange Online e SharePoint Online – Customer approvazione, prima che sia possibile accedere ai dati dei clienti per le operazioni del servizio. Quando viene concesso l'approvazione, gli account amministrativi specifici del servizio vengono provisioning just-in-Time con accesso appena sufficiente per eseguire le attività richieste dalla richiesta di servizio.

## <a name="lockbox-and-customer-lockbox"></a>Archivio protetto e archivio protetto dei clienti
Anche se è estremamente raro, un cliente potrebbe richiedere assistenza da Microsoft che potrebbe esporre un tecnico Microsoft al contenuto del cliente per fornire assistenza in merito a un problema. Per controllare l'accesso a Exchange Online (che include i dati Skype for business archiviati nelle cassette postali degli utenti (la copertura di Skype for business non include registrazioni o contenuti caricati nelle riunioni da parte degli utenti con Skype meeting)) e SharePoint Online (che include OneDrive for business), Microsoft utilizza un sistema di controllo di accesso denominato archivio protetto. Prima che un tecnico Microsoft possa accedere a qualsiasi sistema o dati di Exchange Online o SharePoint Online, deve inviare una richiesta di accesso tramite archivio protetto. L'utilizzo di archivio protetto è necessario per tutti gli accessi elevati a Exchange Online o SharePoint Online.

L'archivio protetto elabora le richieste per le autorizzazioni che conferiscono agli ingegneri la possibilità di eseguire funzioni operative e amministrative all'interno del servizio. Gli ingegneri inviano richieste tramite archivio protetto, che devono essere approvate da un responsabile prima che il tecnico acquisisca la possibilità di accedere ai dati dei clienti. Dopo l'approvazione da parte del responsabile, il tecnico ha accesso limitato a livello di spazio ai dati dei clienti per poter lavorare sul problema del cliente.

L'archivio protetto dei clienti per Office 365 può essere utile per soddisfare gli obblighi di conformità, ad esempio quelli presenti in FedRAMP e HIPAA, se sono necessarie procedure per l'autorizzazione esplicita di accesso ai dati. Nell'istanza rara quando un tecnico del servizio Microsoft ha bisogno dell'accesso ai dati, si concede l'accesso solo ai dati necessari per risolvere il problema e per un periodo di tempo limitato. Le azioni eseguite dal tecnico del supporto sono registrate per il controllo e sono accessibili tramite l' [API di gestione delle attività di Office 365](https://msdn.microsoft.com/library/office/dn707383.aspx) e il [Centro sicurezza e conformità](http://protection.office.com/). L'archivio protetto dei clienti inserisce il cliente nel processo di approvazione dell'archivio protetto e fornisce loro la possibilità di controllare l'autorizzazione di Microsoft Access al proprio contenuto Exchange Online o SharePoint Online per le operazioni del servizio.

>**Nota**: l'archivio protetto dei clienti è disponibile in [Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software) e come acquisto di un componente aggiuntivo, ma è necessario eseguire operazioni manuali nell'interfaccia di amministrazione di Office 365 (in impostazioni del servizio | Archivio protetto dei clienti) per abilitarlo. Per ulteriori informazioni, vedere [richieste dell'archivio clienti di Office 365](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

Tutte le richieste di servizio per Exchange Online e SharePoint Online vengono gestite dal sistema dell'archivio protetto. E con l'archivio protetto dei clienti, tutte le operazioni di servizio che richiedono l'accesso a questi servizi con l'esposizione ai dati dei clienti passano attraverso il processo di approvazione dell'archivio protetto e quindi consentono al cliente di approvare o rifiutare la richiesta successivamente.
 
*Figura 1-flusso di lavoro archivio clienti*

Se la richiesta viene rifiutata dal cliente, l'assistente tecnico Microsoft non avrà accesso al contenuto del cliente e non sarà in grado di completare l'operazione del servizio. Se la richiesta viene approvata dal cliente, l'assistente tecnico Microsoft avrà limitato l'accesso just-in-time al contenuto del cliente tramite interfacce di gestione monitorate e vincolate. Sia con l'archivio protetto che con l'archivio protetto dei clienti, tutti gli accessi approvati sono rintracciabili con un utente univoco, rendendo gli ingegneri responsabili per la gestione delle informazioni relative ai clienti.

## <a name="just-in-time-access"></a>Accesso just-in-Time
Microsoft utilizza il principio di accesso JIT (just-in-Time) per Office 365 per attenuare ulteriormente il rischio di manomissioni delle credenziali e attacchi laterali. JIT consente di rimuovere l'accesso amministrativo permanente ai servizi e di sostituire tali diritti con la possibilità di elevare i ruoli su richiesta. La rimozione di diritti permanenti da parte degli amministratori garantisce che le credenziali siano disponibili solo quando sono necessarie e rimuovano il rischio posto per la società nei casi di furto di credenziali.

Il modello di accesso JIT richiede agli ingegneri la richiesta di privilegi elevati per un periodo di tempo limitato per l'esecuzione delle mansioni amministrative. OCEs, inoltre, utilizza account temporanei creati con password complesse generate dal computer e concessi solo i ruoli che consentono loro di eseguire le attività necessarie. Ad esempio, l'accesso amministrativo concesso dall'archivio protetto è associato al tempo e l'intervallo di tempo concesso dipende dal ruolo richiesto. Un tecnico specifica il periodo di tempo necessario per l'accesso durante la richiesta al sistema dell'archivio protetto. Il sistema di archivio protetto rifiuterà le richieste in cui il tempo richiesto supera il tempo massimo consentito per l'elevazione. Dopo la scadenza della richiesta di elevazione, l'accesso amministrativo viene rimosso e l'account temporaneo è scaduto.

Quando si autorizza e approva l'accesso (ad esempio, per eseguire il debug di un sistema), gli ingegneri ricevono una password amministrativa monouso che viene generata dal sistema di autorizzazione ogni volta che viene approvata una richiesta di accesso elevato. Questa password viene copiata dal tecnico in una cassetta di sicurezza per le password, è separata dalle credenziali del tecnico per l'ambiente aziendale Microsoft ed è valida solo per la sessione per la quale è stato approvato l'accesso con privilegi elevati.

## <a name="constrained-management-interfaces"></a>Interfacce di gestione vincolate
OCEs utilizzare due interfacce di gestione per eseguire le attività amministrative: Remote Desktop tramite gateway di Servizi terminal protetti (STG) e Remote PowerShell. All'interno di queste interfacce di gestione esistono criteri software e controlli di accesso che applicano restrizioni significative su quali applicazioni possono essere eseguite e sui comandi e sui cmdlet disponibili. 

I server di Office 365 limitano le sessioni simultanee a una sessione per amministratore del team per servizio, per ogni server. STG sono configurati in modo da consentire solo una singola sessione simultanea per gli utenti e non consentono più sessioni. STG consente agli amministratori del team di servizio di Office 365 di connettersi contemporaneamente a più server, utilizzando una singola sessione per ogni server, in modo che gli amministratori possano svolgere efficacemente le proprie mansioni. Gli amministratori del team di servizio non dispongono delle autorizzazioni per gli stessi STG. STG viene utilizzato solo per applicare i requisiti di crittografia e autenticazione a più fattori. Dopo che l'amministratore del team di servizio si è connesso a un server specifico tramite un STG, il server specifico implicherà un limite di sessione di uno per ogni amministratore.

Le restrizioni di utilizzo e i requisiti di connessione e configurazione per il personale di Office 365 sono stabiliti da criteri di gruppo di Active Directory. Questi criteri includono le caratteristiche seguenti:
- STG sono configurati per utilizzare solo la crittografia [FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 convalidata
- Le sessioni STG sono configurate per la disconnessione dopo 30 minuti di inattività
- Le sessioni STG sono configurate per l'accesso automatico dopo 24 ore

Le connessioni a STG richiedono anche l'utilizzo di una smart card fisica distinta e un account separato dalle credenziali Microsoft Corporate del tecnico. Agli ingegneri vengono rilasciate smart card diverse per varie piattaforme e piattaforme di gestione dei segreti vengono utilizzate per garantire l'archiviazione sicura delle credenziali. STG utilizza criteri di gruppo di Active Directory per controllare chi può accedere ai server remoti, il numero di sessioni consentite e le impostazioni di timeout di inattività. Sono disponibili ulteriori criteri per limitare l'accesso alle applicazioni consentite e limitare l'accesso a Internet.

Oltre all'accesso remoto utilizzando STG configurati appositamente, Exchange Online consente agli utenti con il ruolo di Service Engineer Operations di accedere a determinate funzionalità amministrative nei server di produzione tramite Remote PowerShell. A tale scopo, è necessario che l'utente sia autorizzato per l'accesso in sola lettura (debug) all'ambiente di produzione di Office 365. L'escalation dei privilegi è abilitata nello stesso modo in cui è abilitata per STG utilizzando il processo di archivio protetto.

Per l'accesso remoto, è presente un IP virtuale con bilanciamento del carico in ogni data center che funge da singolo punto di accesso. I cmdlet di PowerShell remoti che possono essere eseguiti sono basati sul livello di privilegio identificato nell'attestazione di accesso ottenuta durante l'autenticazione. Questi cmdlet sono l'unica funzionalità amministrativa a cui è possibile accedere ed eseguire gli utenti che si connettono utilizzando questo metodo. Remote PowerShell viene utilizzato per limitare l'ambito dei comandi disponibili per il tecnico, che si basa sul livello di accesso concesso tramite il processo di archivio protetto. Ad esempio, in Exchange Online, Get-Mailbox potrebbe essere disponibile, ma la Set-Mailbox non sarebbe.
