---
title: Isolamento di Office 365 e controllo di accesso in Office 365
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
description: "Riepilogo: Informazioni di isolamento e controllo di accesso all'interno di diverse applicazioni di Office 365."
ms.openlocfilehash: c1989bc546df357740ea963a1a241dfa14557931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531352"
---
# <a name="isolation-and-access-control-in-office-365"></a>Isolamento e controllo di accesso in Office 365

Office 365 e Azure Active Directory usare un modello di dati molto complessa che include decine di servizi, centinaia di entità, migliaia di relazioni e decine di migliaia di attributi (entità, le relazioni e gli attributi sono spesso specifiche dell'applicazione). A un livello superiore, servizio directory e Azure Active Directory sono i contenitori del tenant e dei destinatari e vengono mantenuti sincronizzati utilizzando i protocolli basato sullo stato della replica. Oltre a informazioni di directory acquisite all'interno di Azure Active Directory, ognuno dei servizi sono anche i propri infrastruttura dei servizi directory (ad esempio, servizi Directory di Exchange Online, SharePoint Online Directory Services e così via). 
 
![Sincronizzazione dei dati di Office 365 tenant](media/office-365-isolation-tenant-data-sync.png)

In questo modello, non esiste alcun unica fonte di dati della directory. Tutti i singoli dati appartiene a un sistema specifico, ma non singolo sistema contiene tutti i dati. Servizi di Office 365 collaborano con Azure Active Directory per realizzare il modello di dati. Azure Active Directory è "sistema di verità" per i dati condivisi, che è in genere i dati statici e piccoli spesso utilizzati da ogni servizio. Il modello federato utilizzato all'interno di Office 365 e Azure Active Directory fornisce la visualizzazione dei dati condivisa.

Office 365 utilizza l'archiviazione fisica e l'archiviazione cloud Azure. Exchange Online (inclusi Exchange Online Protection) e Skype per le aziende utilizzano i propri archiviazione per i dati dei clienti. SharePoint Online utilizza archivio SQL Server sia Azure archiviazione, che richiede la necessità di ulteriore isolamento dei dati di analisi a livello di archiviazione.

## <a name="exchange-online"></a>Exchange Online
Exchange Online vengono archiviati i dati dei clienti nelle cassette postali ospitate in database del motore ESE (Extensible Storage) denominati database delle cassette postali. Sono incluse le cassette postali utente, cassette postali collegate, le cassette postali condivise e le cassette postali di cartelle pubbliche. Cassette postali degli utenti siano inclusi salvata Skype per il contenuto di Business, ad esempio le cronologie di conversazione. Il contenuto delle cassette postali utente include messaggi di posta elettronica e allegati di posta elettronica, le informazioni del calendario e libero/occupato, contatti, attività, note, gruppi e dati inferenza.

Ogni database delle cassette postali in Exchange Online include le cassette postali da più tenant. Tutte le cassette postali sono protetti dal codice di autorizzazione, tra cui all'interno di una tenancy. Come per una distribuzione locale di Exchange, per impostazione predefinita solo l'utente assegnato dispone dell'accesso a una cassetta postale. L'elenco di controllo di accesso (ACL) che viene protetto tramite una cassetta postale contiene un'identità autenticata per Azure Active Directory a livello di tenant. Le cassette postali per un determinato tenant sono limitate a identità autenticata in provider di autenticazione del tenant che includono solo gli utenti da tale tenant. Contenuto appartenenti al TenantA non in alcun modo è possibile ottenere dagli utenti in TenantB, a meno che non esplicitamente approvato dal TenantA.

## <a name="skype-for-business"></a>Skype for Business
Skype per le aziende archivia i dati in diverse posizioni:
- E all'account utente dial plan roaming delle impostazioni, lo stato di presenza, elenchi di contatti e così via, di informazioni che include gli endpoint di connessione, ID tenant, viene archiviato in Skype per i server di Active Directory aziendale, nonché in vari Skype per database di Business Server. Se l'utente è abilitato per entrambi i prodotti o in Skype per i server Business se l'utente non è, gli elenchi contatti sono archiviati nella cassetta postale di Exchange Online dell'utente. Skype per i server di database Business non sono partizionata tenant, ma multi-tenancy isolamento dei dati è applicata tramite RBAC.
- Contenuto della riunione, ad esempio gli utenti contenuti caricare durante Skype per le riunioni aziendali, viene archiviato in condivisioni di File System distribuito. Questo contenuto può essere archiviato in Exchange Online anche se è abilitata l'archiviazione. Condivisioni DFS non sono partizionati tenant, ma viene protetto il contenuto con gli elenchi ACL e multi-tenancy è applicate tramite RBAC.
- Registrazioni dei dettagli delle chiamate, ovvero la cronologia di attività, ad esempio cronologia delle chiamate, sessioni di messaggistica Istantanea, condivisione di applicazioni, cronologia di messaggistica immediata e così via, possono inoltre essere archiviati in Exchange Online, ma la maggior parte delle registrazioni dei dettagli delle chiamate vocali vengono temporaneamente archiviati nel server di record (CDR) tutti i dettagli delle chiamate. Contenuto non viene partizionato per tenant, ma multi-tenancy è applicate tramite RBAC.

## <a name="sharepoint-online"></a>SharePoint Online
Esistono diversi meccanismi indipendenti univoci per SharePoint Online che forniscono l'isolamento dei dati. SharePoint Online, gli oggetti vengono memorizzate come astratto codice nel database dell'applicazione. Ad esempio, quando un utente carica un file in SharePoint Online, tale file è disassemblato e convertito nel codice dell'applicazione e archiviati in più tabelle su più database.

Se un utente può ottenere l'accesso diretto all'archiviazione contenente i dati, il contenuto potrebbe non essere interpretato a un utente o un sistema diverso da SharePoint Online. Questi meccanismi includono le proprietà e il controllo degli accessi. Come descritto in precedenza, il codice di autorizzazione e sul criterio RBAC, inclusi all'interno di una tenancy sono protetti tutte le risorse di SharePoint Online. L'elenco di controllo di accesso (ACL) che viene protetto tramite una risorsa contiene un'identità autenticata a livello di tenant. Come con Exchange Online, in SharePoint Online, sono limitati a identità autenticata in provider di autenticazione del tenant che includono solo gli utenti da tale tenant dati per un determinato tenant.

Oltre a ACL, una proprietà a livello tenant che specifica il provider di autenticazione (che specifica del tenant Azure Active Directory), è una sola volta e non può essere modificata dopo l'impostazione. Dopo avere configurata la proprietà tenant provider di autenticazione per un tenant, non può essere modificata utilizzando le API reso disponibile a un tenant.

Un univoco *SubscriptionId* viene utilizzata anche per ogni tenant. Tutti i siti dei clienti e di proprietà di un tenant e che sono assegnati un *SubscriptionId* univoco per il tenant. La proprietà *SubscriptionId* in un sito viene scritta una sola volta e non può essere modificata. Una volta che un sito viene assegnato a un tenant, che non venga spostata a un altro tenant un secondo momento utilizzando l'API dell'archivio del contenuto. *SubscriptionId* è inoltre la chiave che viene utilizzata per creare l'ambito di sicurezza per il provider di autenticazione ed è collegata al tenant.

SharePoint Online utilizza l'archiviazione di SQL Server e Azure per l'archiviazione del contenuto. A livello di SQL, la chiave di partizione per l'archivio del contenuto è *SiteId*. Quando si esegue una query SQL, SharePoint Online utilizza *SiteId* che è stato verificato come parte di un controllo *SubscriptionId* livello di tenant.

SharePoint Online archivi BLOB binari file (ad esempio, i flussi di file) in Microsoft Azure. Ogni farm di SharePoint Online con il proprio account Microsoft Azure e tutti gli oggetti BLOB salvati in Azure sono crittografati singolarmente utilizzando una chiave che viene archiviata nell'archivio del contenuto SQL. La chiave di crittografia non è esposto direttamente agli utenti finali e protetto nel codice dal livello di autorizzazione. Infine, SharePoint Online con il monitoraggio in tempo reale per rilevare quando una richiesta HTTP legge o scrive i dati per più di un tenant. A tale scopo, il *SubscriptionId* dell'identità richiesta con *SubscriptionId* della risorsa viene eseguito l'accesso di verifica. Una richiesta di accedere alle risorse di uno o più tenant mai dovrebbe avvenire dall'utente finale. Può verificarsi per le richieste di assistenza in un ambiente multi-tenant, tuttavia. Ad esempio, il crawler di ricerca utilizza modifiche del contenuto per l'intero database contemporaneamente. In genere comporta la query in siti di uno o più tenant in una richiesta di servizio singolo, viene eseguita per motivi di efficienza.
