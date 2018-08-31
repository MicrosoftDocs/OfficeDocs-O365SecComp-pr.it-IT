---
title: Crittografia di Office 365 per Skype, OneDrive, SharePoint ed Exchange
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
description: 'Riepilogo: Descrizione di crittografia per Skype, OneDrive, SharePoint ed Exchange Online.'
ms.openlocfilehash: 5b839b8d290306f2334d3ca3278d0d5dac20a56f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530812"
---
# <a name="office-365-encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>Crittografia di Office 365 per Skype for Business, OneDrive for Business, SharePoint Online ed Exchange Online

Office 365 è un ambiente con protezione avanzata che offre una protezione estesa su più livelli: sicurezza, la protezione della rete, sicurezza dall'accesso, protezione delle applicazioni e la protezione dei dati del centro dati fisici.

## <a name="skype-for-business"></a>Skype for Business
Skype per i dati dei clienti aziendali può essere memorizzati statici nel formato di file o le presentazioni che vengono caricate da partecipanti alla riunione. Web Conferencing server consente di crittografare i dati dei clienti utilizzando AES con una chiave di 256 bit. I dati dei clienti crittografato viene archiviati in una condivisione file. Ogni parte dei dati del cliente viene crittografato tramite una chiave di 256 bit generata casualmente diversa. Quando un blocco di dati dei clienti viene condiviso in una conferenza Web Conferencing server fa sì che i client per conferenze per scaricare i dati dei clienti crittografati tramite HTTPS. Invia la chiave corrispondente al client in modo che i dati dei clienti possono essere decrittografati. Web Conferencing server autentica i client per conferenze anche i client per consentire l'accesso ai dati dei clienti di conferenza. Quando si partecipa a una conferenza Web, ogni client per conferenze stabilisce una finestra di dialogo SIP con il componente focus conferenza in esecuzione all'interno del server front-end su TLS prima. Lo stato attivo per conferenze passa al client di conferenza un cookie di autenticazione generato da Web Conferencing server. Il client per conferenze quindi si connette a una presentazione i cookie di autenticazione per essere autenticati da server Web Conferencing server.

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online e OneDrive for Business
Tutti i file dei clienti di SharePoint Online sono protetti da chiavi per ogni file univoco, che sono sempre esclusive per un singolo tenant. Le chiavi sono creati e gestiti dal servizio Online di SharePoint o quando si utilizza chiave cliente, creare e gestire dai clienti. Quando viene caricato un file, la crittografia viene eseguita nel contesto della richiesta per il caricamento da SharePoint Online prima dell'invio di archiviazione Azure. Quando viene scaricato un file, SharePoint Online consente di recuperare il cliente crittografato in base all'identificatore univoco documento e la decrittografia i dati dei clienti prima di inviare all'utente di dati di archiviazione Azure. Archiviazione Azure non è è possibile per decrittografare, o persino identificare o acquisire familiarità con i dati dei clienti. Tutti i crittografia e decrittografia avvengono negli stessi sistemi che impongono l'isolamento del tenant, ovvero Azure Active Directory e SharePoint Online.

Diversi carichi di lavoro in Office 365 archiviare i dati in SharePoint Online, tra cui Microsoft Teams, che archivia tutti i file in SharePoint Online e OneDrive for Business, che utilizza SharePoint Online per l'archiviazione. Tutti i dati dei clienti archiviati in SharePoint Online è crittografato (con uno o più tasti AES 256 bit) e distribuiti nel datacenter come indicato di seguito. (Ogni fase del processo di crittografia è FIPS 140-2 livello 2 convalidato. Per ulteriori informazioni sulla conformità FIPS 140-2, vedere [la conformità FIPS 140-2](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).)
- Ogni file viene suddiviso in uno o più blocchi, a seconda delle dimensioni dei file. Ogni blocco viene crittografato tramite il proprio chiave AES 256 bit univoca.
- Quando viene aggiornato un file, l'aggiornamento viene gestita allo stesso modo: la modifica viene suddiviso in uno o più parti e ogni blocco è crittografato con una chiave univoca separata.
- Tali blocchi – i file, tipi di file e aggiornamento delta – archiviati come BLOB in Azure di archiviazione in modo casuale distribuiti in più account di archiviazione Azure. 
- Il set di chiavi di crittografia per i blocchi di dati dei clienti è crittografata.
   - I tasti utilizzati per crittografare i BLOB vengono archiviati nel Database del contenuto di SharePoint Online.
   - Il Database del contenuto viene protetta tramite i controlli di accesso database e la crittografia statici. Crittografia viene eseguita utilizzando [Transparent Data Encryption](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde) (TDE) nel [Database di SQL Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview). (Database di SQL azure è un servizio di utilizzo generale database relazionale in Microsoft Azure che supporta le strutture, ad esempio dati relazionali, JSON spaziale e XML). Questi segreti sono a livello di servizio SharePoint Online, non a livello di tenant. Questi segreti (detto anche le chiavi principali) sono archiviati in un archivio sicuro separato denominato archivio chiave. TDE offre una protezione statici per il database attivo e il backup dei database e i registri delle transazioni. 
   - Quando i clienti forniscono la chiave facoltativa, la chiave cliente viene archiviata in Azure chiave cassaforte e il servizio utilizza per crittografare una chiave tenant, che viene utilizzata per crittografare la chiave del sito che verrà utilizzata per crittografare le chiavi di livello di file. In pratica, viene introdotta una nuova gerarchia di chiavi quando il cliente fornisce una chiave.
- Specifica il mapping utilizzato per assemblare nuovamente il file viene archiviato nel Database del contenuto e le chiavi crittografate, separatamente dalla chiave master necessari per decrittografare i file.
- Ogni account di archiviazione Azure dispone di credenziali univoche per ogni tipo di accesso (lettura, scrittura, consente di enumerare ed eliminare). Ogni insieme di credenziali tenute nella chiave di archiviazione sicura e si aggiorna regolarmente. Come descritto in precedenza, esistono tre diversi tipi di archivi, ognuno con una funzione distinta:
- Dati relativi ai clienti viene archiviata come BLOB crittografato in archiviazione Azure. Il tasto per ogni blocco di dati dei clienti è crittografato e archiviare separatamente nel Database del contenuto. I dati dei clienti stesso non contiene alcuna indicazione per quanto riguarda la modalità possono essere decrittografato.
- Il Database del contenuto è un database di SQL Server. Contiene il mapping necessario per individuare e riunire i BLOB di dati dei clienti tenuti in archiviazione Azure, nonché le chiavi necessarie per crittografare i BLOB. Tuttavia, l'insieme dei tasti è stesso crittografati (come descritto sopra) e tenute in un archivio separato chiave.
- L'archivio chiave è fisicamente separato dal sistema di archiviazione Database del contenuto e Azure. Contiene le credenziali per ogni contenitore di archiviazione Azure e la chiave master per il set di chiavi crittografate contenute nel Database del contenuto.

Ognuno di questi tre componenti di archiviazione – archivio blob Azure, il Database del contenuto e l'archivio chiave – è fisicamente distinto. Le informazioni contenute in uno dei componenti sono utilizzabile in modo autonomo. In assenza di accedere a tutti e tre, è possibile recuperare i tasti per i blocchi, decrittografare le chiavi per renderli utilizzabile, associare i tasti con loro blocchi corrispondente, decrittografare ogni blocco o ricostruire un documento dalle parti costitutive.

Certificati BitLocker, che proteggono i volumi del disco fisico in computer nel centro dati, vengono archiviati in un archivio sicuro (archivio segreta SharePoint Online) protetto tramite la chiave della Farm.

Le chiavi TDE proteggere le chiavi per blob vengono archiviate in due posizioni:
- L'archivio sicuro, che ospita i certificati BitLocker e viene protetta tramite la chiave di Farm. e
- In un archivio sicuro gestito dal Database SQL Azure.

Le credenziali utilizzate per accedere ai contenitori di archiviazione Azure sono inoltre tenute in SharePoint Online segreto archiviare e delegato per ogni farm di SharePoint Online in base alle esigenze. Queste credenziali sono firme SAS archiviazione Azure, con credenziali separate consente di leggere o scrivere dati e i criteri applicati in modo che auto-scadenza ogni 60 giorni. Diverse credenziali vengono utilizzate per leggere o scrivere dati (non entrambi) e farm di SharePoint Online non vengono concesse le autorizzazioni per enumerare.

> I clienti governo nota per Office 365 degli Stati Uniti, oggetti BLOB di dati vengono archiviati in archiviazione gli Stati Uniti Azure. Inoltre, l'accesso alle chiavi SharePoint Online in Office 365 Uniti è limitata al personale di Office 365 che hanno viene analizzato in modo specifico. Azure personale governo degli Stati Uniti non ha accesso all'archivio SharePoint Online chiave che viene utilizzato per crittografare i BLOB di dati.

Per ulteriori informazioni sulla crittografia dei dati in SharePoint Online e OneDrive for Business, vedere [Crittografia dei dati in OneDrive for Business e SharePoint Online](https://technet.microsoft.com/en-us/library/dn905447.aspx).

### <a name="list-items-in-sharepoint-online"></a>Elementi di elenco in SharePoint Online
Voci di elenco sono piccole del cliente dati creati ad hoc o che possono live in modo più dinamico in un sito, ad esempio singoli post di blog di SharePoint Online o voci all'interno di una pagina wiki di SharePoint Online, righe in un elenco creato dall'utente. Voci di elenco sono archiviate nel Database del contenuto (Database di SQL Azure) e protetta con TDE.

## <a name="encryption-of-data-in-transit"></a>Crittografia dei dati in transito
In OneDrive for Business e SharePoint Online, esistono due scenari in cui i dati entrano ed escono dai data center.
- **Client di comunicare con il server** - comunicazione a OneDrive for Business via Internet vengono utilizzate connessioni TLS/SSL. Tutte le connessioni SSL vengono stabilite utilizzando le chiavi a 2048 bit.
- **Spostamento dei dati tra Data Center** - il motivo principale per spostare i dati tra Data Center è per la replica geografica consentire il ripristino di emergenza. Ad esempio, i registri delle transazioni SQL Server e delta di archiviazione blob viaggio lungo questa pipe. Quando questi dati vengono trasmessi già tramite una rete privata, sono ulteriormente protetti con crittografia ottimale in classe.


## <a name="exchange-online"></a>Exchange Online
Exchange Online utilizza BitLocker tutti i dati delle cassette postali e la configurazione di BitLocker è descritto in [BitLocker per la crittografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md). Livello di servizio vengono crittografati tutti i dati delle cassette postali a livello di cassetta postale. 

Oltre a servizio di crittografia, Office 365 supporta la chiave di clienti, che si basano sul servizio di crittografia. Chiave cliente è un'opzione di chiave gestite Microsoft per la crittografia del servizio Exchange Online che è disponibile anche nella Guida di orientamento di Microsoft. Questo metodo di crittografia offre maggiore protezione non conferita dal BitLocker in quanto consente di separare gli amministratori del server e le chiavi di crittografia per la decrittografia dei dati e in quanto la crittografia viene applicata direttamente ai dati ( contrasto con BitLocker, che applica crittografia un volume del disco logico) i dati dei clienti copiati da un server di Exchange rimangano crittografati.

L'ambito per la crittografia del servizio Exchange Online è cliente i dati archiviati statici in Exchange Online. (Skype per le aziende archivia quasi tutto generato dall'utente il contenuto della cassetta postale di Exchange Online dell'utente e pertanto eredita la funzionalità di crittografia del servizio di Exchange Online).
