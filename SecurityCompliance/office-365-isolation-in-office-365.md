---
title: Isolamento e controllo di accesso di Office 365 in Office 365
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
description: "Sintesi: una spiegazione dell'isolamento e del controllo di accesso all'interno delle diverse applicazioni di Office 365."
ms.openlocfilehash: a03b2807be4044fa7d9f9d702e148a34377fa56c
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090868"
---
# <a name="isolation-and-access-control-in-office-365"></a>Isolamento e controllo di accesso in Office 365

Azure Active Directory e Office 365 utilizzano un modello di dati di elevata complessità che include decine di servizi, centinaia di entità, migliaia di relazioni e decine di migliaia di attributi (le entità, le relazioni e gli attributi sono spesso specifiche dell'applicazione). A livello elevato, Azure Active Directory e le directory del servizio sono contenitori di tenant e destinatari e vengono mantenuti sincronizzati utilizzando i protocolli di replica basati sullo stato. Oltre alle informazioni sulla directory tenute all'interno di Azure Active Directory, ognuno dei servizi dispone anche di un'infrastruttura di servizi directory (ad esempio, servizi directory di Exchange Online, servizi directory di SharePoint Online e così via). 
 
![Sincronizzazione dei dati del tenant di Office 365](media/office-365-isolation-tenant-data-sync.png)

All'interno di questo modello non esiste un'unica origine di dati di directory. Ogni singolo elemento di dati è di proprietà di un sistema specifico, ma nessun singolo sistema contiene tutti i dati. I servizi di Office 365 cooperano con Azure Active Directory per la realizzazione del modello di dati. Azure Active Directory è il "sistema di verità" per i dati condivisi, che in genere sono dati di piccole dimensioni e statici usati spesso da ogni servizio. Il modello federato utilizzato all'interno di Office 365 e Azure Active Directory fornisce la visualizzazione condivisa dei dati.

Office 365 utilizza sia l'archiviazione fisica che lo spazio di archiviazione cloud di Azure. Exchange Online (incluso Exchange Online Protection) e Skype for business utilizzano la propria archiviazione per i dati dei clienti. SharePoint Online sfrutta sia l'archiviazione di SQL Server che lo spazio di archiviazione di Azure, che richiede la necessità di un ulteriore isolamento dei dati del cliente a livello di archiviazione.

## <a name="exchange-online"></a>Exchange Online
Exchange Online memorizza i dati dei clienti all'interno delle cassette postali ospitate all'interno di database ESE (Extensible Storage Engine) chiamati database delle cassette postali. Sono incluse le cassette postali utente, le cassette postali collegate, le cassette postali condivise e quelle pubbliche. Le cassette postali degli utenti possono includere anche il contenuto di Skype for business salvato, ad esempio le storie di conversazione. Il contenuto delle cassette postali degli utenti include messaggi di posta elettronica e allegati, calendari e informazioni sulla disponibilità, contatti, attività, note, gruppi e dati di inferenza.

Ogni database delle cassette postali in Exchange Online contiene cassette postali provenienti da più tenant. Tutte le cassette postali sono protette dal codice di autorizzazione, anche all'interno di una locazione. Come per la distribuzione locale di Exchange, per impostazione predefinita solo l'utente assegnato ha accesso a una cassetta postale. L'elenco di controllo di accesso (ACL, Access Control List) che protegge una cassetta postale contiene un'identità autenticata da Azure Active Directory a livello di tenant. Le cassette postali per un determinato tenant sono limitate alle identità autenticate con il provider di autenticazione del tenant, che include solo gli utenti di tale tenant. Il contenuto che appartiene a Tenanta non può in alcun modo essere ottenuto dagli utenti in TenantB, a meno che non sia esplicitamente approvato dal Tenanta.

## <a name="skype-for-business"></a>Skype for Business
Skype for business archivia i dati in vari punti:
- Le informazioni sull'utente e sugli account, che includono gli endpoint di connessione, gli ID tenant, i dial plan, le impostazioni di roaming, lo stato di presenza, gli elenchi di contatti e così via, vengono archiviati nei server Skype for business Active Directory, così come in vari database Skype for business. Server. Gli elenchi di contatti vengono archiviati nella cassetta postale di Exchange Online dell'utente se l'utente è abilitato per entrambi i prodotti o su server Skype for business se l'utente non lo è. I server di database di Skype for business non sono partizionati per-tenant, ma l'isolamento dei dati in più locazioni viene applicato tramite RBAC.
- Il contenuto delle riunioni, ad esempio il caricamento degli utenti di contenuto durante le riunioni di Skype for business, viene archiviato in condivisioni di file System distribuite. Questo contenuto può anche essere archiviato nell'archiviazione di Exchange Online fornita è abilitato. Le condivisioni DFS non sono partizionate per-tenant, ma il contenuto è protetto con gli elenchi di controllo di accesso e la multi-locazione viene applicata tramite RBAC.
- I record dettagli chiamata, ovvero la cronologia delle attività, ad esempio la cronologia delle chiamate, le sessioni di messaggistica istantanea, la condivisione di applicazioni, la cronologia di messaggistica istantanea e così via, possono essere archiviati anche in Exchange Online, ma la maggior parte dei record dettagli chiamata è temporaneamente memorizzata nei server registrazione dettagli chiamata (CDR). Il contenuto non viene partizionato per tenant, ma viene applicato tramite RBAC.

## <a name="sharepoint-online"></a>SharePoint Online
Sono disponibili diversi meccanismi indipendenti per SharePoint Online che forniscono l'isolamento dei dati. SharePoint Online archivia gli oggetti come codice astratto all'interno dei database dell'applicazione. Ad esempio, quando un utente carica un file in SharePoint Online, tale file viene disassemblato e convertito in codice dell'applicazione e archiviato in più tabelle tra più database.

Se un utente può accedere direttamente allo spazio di archiviazione contenente i dati, il contenuto non può essere interpretato da un essere umano o da un sistema diverso da SharePoint Online. Tali meccanismi includono il controllo dell'accesso alla sicurezza e le proprietà. Come descritto in alto, tutte le risorse di SharePoint Online sono protette dal codice di autorizzazione e dai criteri RBAC, anche all'interno di una locazione. L'elenco di controllo di accesso (ACL, Access Control List) che protegge una risorsa contiene un'identità autenticata a livello di tenant. Come con Exchange Online, in SharePoint Online, i dati per un determinato tenant sono limitati alle identità autenticate con il provider di autenticazione del tenant, che include solo gli utenti di tale tenant.

Oltre agli elenchi ACL, una proprietà a livello di tenant che specifica il provider di autenticazione (ovvero Azure Active Directory specifica del tenant) viene scritta una sola volta e non può essere modificata dopo l'impostazione. Dopo aver impostato la proprietà tenant del provider di autenticazione per un tenant, non è possibile modificarla utilizzando le API esposte a un tenant.

Un *SubscriptionId* univoco viene utilizzato anche per ogni tenant. Tutti i siti dei clienti sono di proprietà di un tenant e sono assegnati a un *SubscriptionId* univoco per il tenant. La proprietà *SubscriptionId* di un sito viene scritta una sola volta e non può essere modificata. Dopo aver assegnato un sito a un tenant, non è possibile spostarlo in un altro tenant in un secondo momento utilizzando l'API dell'archivio di contenuto. *SubscriptionId* è inoltre la chiave utilizzata per creare l'ambito di sicurezza per il provider di autenticazione ed è associato al tenant.

SharePoint Online utilizza SQL Server e lo spazio di archiviazione di Azure per l'archiviazione del contenuto. A livello di SQL, la chiave di partizione per l'archivio di contenuto è *siteID*. Quando si esegue una query SQL, SharePoint Online utilizza un *siteID* che è stato verificato come parte di un controllo *SubscriptionId* a livello di tenant.

SharePoint Online archivia BLOB binari file (ad esempio, i flussi di file) in Microsoft Azure. Ogni farm di SharePoint Online dispone di un proprio account di Microsoft Azure e tutti gli oggetti BLOB salvati in Azure vengono crittografati singolarmente utilizzando una chiave archiviata nell'archivio di contenuto SQL. La chiave di crittografia non viene esposta direttamente all'utente finale ed è protetta in codice dal livello di autorizzazione. Infine, SharePoint Online ha il monitoraggio in tempo reale sul posto per rilevare quando una richiesta HTTP legge o scrive i dati per più di un tenant. Tale operazione viene eseguita monitorando la *SubscriptionId* dell'identità della richiesta rispetto alla *SubscriptionId* della risorsa a cui si accede. Una richiesta di accesso alle risorse di più tenant non dovrebbe mai verificarsi per l'utente finale. Tuttavia, può verificarsi per le richieste di servizio in un ambiente multi-tenant. Ad esempio, il crawler di ricerca estrae tutte le modifiche del contenuto per un intero database contemporaneamente. Questo comporta di solito l'esecuzione di query su siti di più tenant in una singola richiesta di servizio, operazione eseguita per motivi di efficienza.
