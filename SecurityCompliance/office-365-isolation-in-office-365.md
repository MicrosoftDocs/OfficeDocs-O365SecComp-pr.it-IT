---
title: Isolamento e controllo di accesso di Office 365 in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "Sintesi: una spiegazione dell'isolamento e del controllo di accesso all'interno delle diverse applicazioni di Office 365."
ms.openlocfilehash: 748da21f5b5048bb4ae4c14700ed482fd6d0058c
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402894"
---
# <a name="isolation-and-access-control-in-office-365"></a>Isolamento e controllo di accesso in Office 365

Azure Active Directory e Office 365 utilizzano un modello di dati di elevata complessità che include decine di servizi, centinaia di entità, migliaia di relazioni e decine di migliaia di attributi. A livello elevato, Azure Active Directory e le directory del servizio sono contenitori di tenant e destinatari mantenuti sincronizzati tramite protocolli di replica basati sullo stato. Oltre alle informazioni sulla directory conservate all'interno di Azure Active Directory, ognuno dei carichi di lavoro del servizio dispone di un'infrastruttura di servizi directory.
 
![Sincronizzazione dei dati del tenant di Office 365](media/office-365-isolation-tenant-data-sync.png)

All'interno di questo modello non esiste un'unica origine di dati di directory. I sistemi specifici specificano singoli pezzi di dati, ma nessun singolo sistema contiene tutti i dati. I servizi di Office 365 cooperano con Azure Active Directory in questo modello di dati. Azure Active Directory è il "sistema di verità" per i dati condivisi, che in genere sono dati di piccole dimensioni e statici utilizzati da tutti i servizi. Il modello federato utilizzato all'interno di Office 365 e Azure Active Directory fornisce la visualizzazione condivisa dei dati.

Office 365 utilizza sia l'archiviazione fisica che lo spazio di archiviazione cloud di Azure. Exchange Online (incluso Exchange Online Protection) e Skype for business utilizzano la propria archiviazione per i dati dei clienti. SharePoint Online utilizza l'archiviazione di SQL Server e lo spazio di archiviazione di Azure, quindi la necessità di un ulteriore isolamento dei dati del cliente a livello di archiviazione.

## <a name="exchange-online"></a>Exchange Online

Exchange Online memorizza i dati dei clienti all'interno delle cassette postali. Le cassette postali sono ospitate all'interno dei database ESE (Extensible Storage Engine) chiamati database delle cassette postali Sono incluse le cassette postali utente, le cassette postali collegate, le cassette postali condivise e le cartelle pubbliche. Le cassette postali degli utenti includono il contenuto salvato di Skype for business, ad esempio le storie di conversazione.

Il contenuto della cassetta postale dell'utente include:

- Messaggi di posta elettronica e allegati e-mail
- Informazioni sulla disponibilità e sul calendario
- Contacts
- Attività
- Note
- Gruppi
- Dati di inFerenza

Ogni database delle cassette postali in Exchange Online contiene cassette postali provenienti da più tenant. Un codice di autorizzazione protegge ogni cassetta postale, anche all'interno di una locazione. Per impostazione predefinita, solo l'utente assegnato ha accesso a una cassetta postale. L'elenco di controllo di accesso (ACL, Access Control List) che protegge una cassetta postale contiene un'identità autenticata da Azure Active Directory a livello di tenant. Le cassette postali per ogni tenant sono limitate alle identità autenticate con il provider di autenticazione del tenant, che include solo gli utenti di tale tenant. Il contenuto del tenant a non può in alcun modo essere ottenuto dagli utenti nel tenant B, a meno che non sia esplicitamente approvato dal tenant A.

## <a name="skype-for-business"></a>Skype for Business

Skype for business archivia i dati in vari punti:

- Le informazioni sull'utente e sugli account, che includono gli endpoint di connessione, gli ID tenant, i dial plan, le impostazioni di roaming, lo stato di presenza, gli elenchi di contatti e così via, vengono archiviati nei server Skype for business Active Directory e in vari server di database di Skype for business. Gli elenchi di contatti vengono archiviati nella cassetta postale di Exchange Online dell'utente se l'utente è abilitato per entrambi i prodotti o su server Skype for business se l'utente non lo è. I server di database di Skype for business non sono partizionati per-tenant, ma l'isolamento dei dati in più locazioni viene applicato tramite il controllo di accesso basato sui ruoli (RBAC).
- Il contenuto delle riunioni e i dati caricati sono archiviati in condivisioni di file System (DFS) distribuiti. Questo contenuto può anche essere archiviato in Exchange Online se abilitato. Le condivisioni DFS non sono partizionate per-tenant. il contenuto è protetto con gli elenchi di controllo di accesso e la multilocazione viene applicata tramite RBAC.
- I record dettagli chiamata, ovvero la cronologia delle attività, ad esempio la cronologia delle chiamate, le sessioni di messaggistica istantanea, la condivisione di applicazioni, la cronologia di messaggistica istantanea e così via, possono essere archiviati anche in Exchange Online, ma la maggior parte dei record dettagli chiamata è temporaneamente memorizzata nei server registrazione dettagli chiamata (CDR). Il contenuto non viene partizionato per tenant, ma viene applicato tramite RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online dispone di diversi meccanismi indipendenti che forniscono l'isolamento dei dati. Archivia gli oggetti come codice astratto all'interno dei database dell'applicazione. Ad esempio, quando un utente carica un file in SharePoint Online, il file viene disassemblato, convertito nel codice dell'applicazione e archiviato in più tabelle tra più database.

Se un utente può accedere direttamente allo spazio di archiviazione contenente i dati, il contenuto non può essere interpretato da un essere umano o da un sistema diverso da SharePoint Online. Tali meccanismi includono il controllo dell'accesso alla sicurezza e le proprietà. Tutte le risorse di SharePoint Online sono protette dal codice di autorizzazione e dai criteri RBAC, anche all'interno di una locazione. L'elenco di controllo di accesso (ACL, Access Control List) che protegge una risorsa contiene un'identità autenticata a livello di tenant. I dati di SharePoint Online per un tenant sono limitati alle identità autenticate dal provider di autenticazione per il tenant.

Oltre agli elenchi ACL, una proprietà a livello di tenant che specifica il provider di autenticazione (ovvero Azure Active Directory specifica del tenant) viene scritta una sola volta e non può essere modificata dopo l'impostazione. Dopo aver impostato la proprietà tenant del provider di autenticazione per un tenant, non è possibile modificarla utilizzando le API esposte a un tenant.

Per ogni tenant viene utilizzato un *SubscriptionId* univoco. Tutti i siti dei clienti sono di proprietà di un tenant e sono assegnati a un *SubscriptionId* univoco per il tenant. La proprietà *SubscriptionId* di un sito viene scritta una volta ed è permanente. Una volta assegnata a un tenant, un sito non può essere spostato in un altro tenant. *SubscriptionId* è la chiave utilizzata per creare l'ambito di sicurezza per il provider di autenticazione ed è associato al tenant.

SharePoint Online utilizza SQL Server e lo spazio di archiviazione di Azure per l'archiviazione dei metadati del contenuto. La chiave di partizione per l'archivio di contenuto è *siteID* in SQL. Quando si esegue una query SQL, SharePoint Online utilizza un *siteID* verificato come parte di un controllo *SubscriptionId* a livello di tenant.

SharePoint Online archivia il contenuto del file crittografato nei BLOB di Microsoft Azure. Ogni farm di SharePoint Online dispone di un proprio account di Microsoft Azure e tutti gli oggetti BLOB salvati in Azure vengono crittografati singolarmente con una chiave memorizzata nell'archivio di contenuto SQL. La chiave di crittografia protetta nel codice dal livello di autorizzazione e non esposta direttamente all'utente finale. SharePoint Online ha Monitoring in tempo reale per rilevare quando una richiesta HTTP legge o scrive i dati per più di un tenant. La richiesta Identity *SubscriptionId* viene registrata in base alla *SubscriptionId* della risorsa a cui si accede. Le richieste di accesso alle risorse di più tenant non devono mai essere eseguite dagli utenti finali. Le richieste di servizio in un ambiente multi-tenant sono l'unica eccezione. Ad esempio, il crawler di ricerca estrae tutte le modifiche del contenuto per un intero database contemporaneamente. Questo comporta di solito l'esecuzione di query su siti di più tenant in una singola richiesta di servizio, operazione eseguita per motivi di efficienza.
