---
title: Office 365 servizi Cloud la difesa contro gli attacchi Denial of Service
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
description: Microsoft come difesa relativi servizi cloud contro gli attacchi di tipo denial of service (DoS).
ms.openlocfilehash: f11a4293a35de4d36fd38fce892a4e59919111cc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530912"
---
# <a name="defending-microsoft-cloud-services-against-denial-of-service-attacks"></a>La difesa contro gli attacchi Denial of Service i servizi Cloud Microsoft

## <a name="introduction"></a>Introduzione
Data Center Microsoft sono protetti da sicurezza difesa che includa recinzione perimetrale, fotocamere video, il personale di sicurezza e ingressi protette che utilizzano biometrica, smart card e l'autenticazione a più fattori. La difesa continua a ogni area della struttura e per ogni unità server fisico. L' [infrastruttura Microsoft Cloud e operazioni di gruppo](https://www.microsoft.com/en-us/cloud-platform/global-datacenters) offre l'infrastruttura di base e le tecnologie fondamentali per i servizi cloud. I centri dati rispettare gli standard di settore per la protezione fisica e l'affidabilità e sono gestiti monitorati e gestiti da personale Microsoft operations.

Per proteggere ulteriormente dei servizi cloud, è disponibile un sistema di difesa DDoS che fa parte di Microsoft Azure continua monitoraggio e processi di test di penetrazione. Il sistema di difesa DDoS Azure è progettato non solo ad attacchi dall'esterno, ma anche da altro tenant di Azure. Azure utilizza rilevamento standard e tecniche di riduzione dei, ad esempio i cookie SYN, frequenza di limitazione e limiti delle connessioni per la protezione da attacchi DDoS.

Servizi cloud Microsoft sono soggetti a rischio di attacco da più origini. Per ovviare e protezione contro le minacce DoS diversi, un rilevamento dinamici e altamente scalabile basata su Azure rischio e attenuazione sistema è stato sviluppato e implementato con l'obiettivo primario dell'infrastruttura di protezione da attacchi Denial of Service e che aiuta a evitare le interruzioni di servizio per il cloud services clienti. Il sistema di attenuazione DoS Azure consente di proteggere il traffico in ingresso e in uscita al paese.

La maggior parte degli attacchi Denial of Service rivolti contro gli obiettivi con connessioni di rete (L3) e trasporto livelli (L4) del modello [Open Systems Interconnection](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model) (OSI). Attacchi diretti livelli L3 e L4 sono progettati per saturazione di un'interfaccia di rete o servizio con il traffico di attacco a sovraccaricare le risorse e negare l'autorizzazione per rispondere al traffico legittimo. In particolare, L3 e L4 attacchi tentativo di saturare la capacità dei collegamenti di rete, dispositivi o i servizi o di sovraccaricare la CPU del server o macchine virtuali che supporta un'applicazione.

Per proteggere il sistema contro gli attacchi L3 e L4 Microsoft ha progettato, sviluppato e distribuito una soluzione progettati specificatamente per la protezione gli obiettivi di infrastruttura e dei clienti implementati in attacco da questi livelli di protezione. Protezione dell'infrastruttura assicura che il traffico di attacco progettato per un cliente non provoca danni collaterali o diminuire la qualità di rete del servizio per gli altri utenti. La soluzione utilizza i dati di campionare il traffico dal router datacenter. Questi dati viene analizzati tramite una rete di servizio per rilevare gli attacchi di monitoraggio. Quando viene rilevato un attacco, meccanismi di difesa automatici attivato.

## <a name="application-level-defenses"></a>Protezione a livello di applicazione
Team di tecnici di Microsoft seguire rigorosi impostati da [Microsoft il controllo della protezione operative](https://www.microsoft.com/en-us/SDL/OperationalSecurityAssurance) per proteggere i dati dei clienti. Servizi cloud Microsoft intenzionalmente sono progettati per supportare un carico elevato anche per proteggere e ridurre i rischi di attacchi Denial of Service a livello di applicazione. È stata implementata un'architettura di scalabilità orizzontale in servizi vengono distribuiti su più centri dati globali con isolamento regionale e limitazione delle caratteristiche in alcuni dei carichi di lavoro.

Paese o regione, amministratore del cliente identifica durante l'installazione iniziale dei servizi, ogni cliente determina la posizione di archiviazione principale per i dati del cliente. Dati relativi ai clienti vengono replicate tra Data Center ridondanti in base a una strategia di backup/principale. Un centro dati principale ospita del software applicativo insieme a tutti i dati dei clienti principale in esecuzione sul software. Un centro dati di backup offre il failover automatico. Se datacenter principale smette di funzionare per qualsiasi motivo, le richieste verranno reindirizzate alla copia dei dati del software e dei clienti nel centro dati di backup. In un momento specifico, i dati dei clienti possono essere elaborati nel primario o datacenter del backup. La distribuzione dei dati tra più centri dati consente di ridurre la superficie di attacco interessata in caso di un datacenter è un attacco. Inoltre, i servizi nel centro dati interessato possono essere rapidamente reindirizzati al datacenter secondario come uno dei meccanismi di ripristino e viceversa viceversa (reindirizzata al datacenter principale una volta ripristinato service).

Singoli carichi di lavoro include funzionalità incorporate per la gestione dell'utilizzo delle risorse. Ad esempio, la limitazione delle richieste meccanismi di Exchange Online e SharePoint Online sono parte di un approccio più livelli di difesa da attacchi Denial of Service. Limitazione per gli utenti di Exchange Online si basa sul livello di risorse utilizzati per l'utente finale, se sono le risorse in Active Directory, l'archivio informazioni di Exchange Online o in un' posizione. Un budget viene assegnato a ogni client per limitare le risorse impiegate da un utente. Exchange Online di limitazione per i componenti di sistema e l'attività utente si basa sulla [gestione del carico di lavoro](http://technet.microsoft.com/en-us/library/jj150503(v=exchg.150).aspx). Un carico di lavoro di Exchange Online è un Exchange Online caratteristica, protocollo o servizio che è stata definita in modo esplicito per quanto riguarda la gestione delle risorse del sistema Exchange Online. Risorse di sistema, ad esempio CPU, operazioni di database delle cassette postali, è necessario ogni carico di lavoro di Exchange Online o richieste per eseguire le richieste degli utenti o di sfondo lavoro Active Directory. Esempi di carichi di lavoro di Exchange Online Outlook web, Exchange ActiveSync, migrazione delle cassette postali e Assistenti cassette postali. Gli amministratori tenant possono gestire la gestione del carico di lavoro di Exchange impostazioni di limitazione per gli utenti con Exchange Management Shell. Esistono diversi tipi di limitazione che sono state implementate in Exchange Online, compresi PowerShell, servizi Web Exchange e POP e IMAP, Exchange ActiveSync, connessioni dei dispositivi mobili, i destinatari e altro ancora. Sebbene gli amministratori delle distribuzioni di Exchange locale possono configurare criteri di limitazione, gli amministratori non possono configurare criteri di limitazione per Exchange Online.

Il trigger più comune per la limitazione in SharePoint Online è codice model (CSOM) oggetti del lato client che consente di eseguire azioni troppi eccessiva frequenza. Con CSOM, è possibile eseguire molte delle azioni con una singola richiesta che può superare i limiti di utilizzo e causare la limitazione per ogni utente.

Indipendentemente dal fatto l'attività che possono causare tempi di limitazione, quando un utente supera i limiti di utilizzo, SharePoint Online limitazioni qualsiasi ulteriore delle richieste da tale account utente, in genere di un breve periodo di tempo. Mentre è attiva una limitazione utente, tutte le azioni dall'utente vengono limitate finché non scade la limitazione, in base ai criteri seguenti:
- Per le richieste eseguite dall'utente direttamente in un browser, SharePoint Online reindirizza a una pagina di informazioni di limitazione delle richieste e le richieste di esito negativo.
- Per tutte le altre richieste, incluse le chiamate CSOM, SharePoint Online restituisce il codice di stato HTTP 429 ("troppe richieste") e le richieste di esito negativo.

Se il processo che continua a superare i limiti di utilizzo, SharePoint Online può completamente bloccare il processo e restituire il codice di stato HTTP 503 ("servizio non disponibile").

## <a name="vulnerability-and-penetration-testing"></a>Vulnerabilità e penetrazioni
Microsoft utilizza molti [consigliate e le tecnologie di protezione](https://www.microsoft.com/en-us/trustcenter/security/threatmanagement) per [proteggere l'infrastruttura cloud](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/) e locali reti contro le minacce moderne e sofisticate, incluso l'utilizzo di antimalware componenti e servizi per i servizi cloud, virtuali macchine virtuali e altri sistemi. Avanzate rischio Analitica, che consente di monitorare i modelli di utilizzo normale per reti, sistemi e gli utenti e implementazione di apprendimento contrassegnare un comportamento è fuori le normali operazioni e regolare penetrazione.

Oltre a eseguire un test penetrazione e che offre ai nostri clienti un [programma Microsoft Cloud unificata penetrazione](https://technet.microsoft.com/en-us/mt784683), è inoltre consultare i professionisti eseguono le verifiche delle regolari vulnerabilità di sicurezza di terze parti e penetrazione rispetto ai servizi cloud. È rendere disponibile per il download i report di queste valutazioni vulnerabilità di terze parti da [Considerare attendibile del servizio](https://aka.ms/STP) e dei portali [Garanzia di servizio](https://aka.ms/ServiceAssurance) .
