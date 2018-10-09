---
title: Domande frequenti sull'importazione di file PST in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: "Domande frequenti per gli amministratori sull'utilizzo del servizio di importazione di Office 365 per importare i file PST di generare alle cassette postali di Office 365. "
ms.openlocfilehash: 7230e68f896766df643f12b2a132f987670e9afa
ms.sourcegitcommit: eecf6f3aafbf460ee2ff9988f2b055e62b1fdb9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454053"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>Domande frequenti sull'importazione di file PST in Office 365

**In questo articolo sia per gli amministratori. Si desidera importare i file PST alla propria cassetta postale? Vedere [posta elettronica di importazione, contatti e calendario da un file pst di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Ecco alcune domande frequenti sull'utilizzo del servizio di importare di Office 365 per l'importazione in blocco dei file PST cassette postali di Office 365. Per ulteriori informazioni su come importare i file PST, vedere [Overview of l'importazione di file PST a Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Utilizzo di caricamento di rete per importare i file PST

Per istruzioni dettagliate, vedere [Utilizzo rete caricare per importare i file PST a Office 365](use-network-upload-to-import-pst-files.md).
  
 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnato il ruolo di importare l'esportazione delle cassette postali di Exchange Online per importare i file PST alle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli di Exchange Online. È possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione. Oppure creare un nuovo gruppo di ruoli, assegnare il ruolo cassette postali importazione/esportazione e quindi aggiungere manualmente o altri utenti con un account membro. Per ulteriori informazioni, vedere "Aggiungere un ruolo da un gruppo di ruoli" o "Creare un gruppo di ruoli" sezioni in [gruppi di ruoli di gestione in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Inoltre, per creare Importa i processi in Office 365 Security &amp; centro conformità, uno dei seguenti devono essere vere:
  
- È necessario assegnare il ruolo destinatari di posta elettronica di Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione dei destinatari.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione Office 365.
    
> [!TIP]
> È consigliabile creare un nuovo gruppo di ruoli in Exchange Online che è progettata in modo specifico per l'importazione di file PST in Office 365. Livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importare l'esportazione delle cassette postali e destinatari di posta elettronica al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove si trova il caricamento di rete disponibile?**
  
Caricamento di rete è attualmente disponibile in Stati Uniti, in Canada, Brasile, Regno Unito, Francia, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia. Caricamento di rete sarà disponibile in aree più breve.
  
 **Che cos'è il prezzo per l'importazione dei file PST utilizzando il caricamento di rete?**
  
Utilizzo di caricamento di rete per importare i file PST è disponibile.
  
Ciò significa inoltre che dopo l'eliminazione dei file PST dall'area di archiviazione Azure, vengono non vengono più visualizzati nell'elenco dei file di un processo di importazione completate nell'interfaccia di amministrazione di Office 365. Anche se un processo di importazione potrebbe ancora essere elencato nella pagina **Importa dati a Office 365** , l'elenco dei file PST può essere vuota quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quale versione del formato di file PST è supportato per l'importazione in Office 365?**
  
Esistono due versioni del formato di file PST: ANSI e Unicode. È consigliabile l'importazione di file che utilizzano il formato di file PST in formato Unicode. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelle per le lingue che utilizzano un carattere DBCS impostato (DBCS), possono essere importati anche a Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 4 nella [rete utilizzo caricare per importare i file PST dell'organizzazione a Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
È inoltre possono importare i file PST di Outlook 2007 e versioni successive a Office 365.
  
 **Dopo che è possibile caricare i file PST all'area di archiviazione Azure, quanto tempo vengono vengono conservati in Azure prima dell'eliminazione è?**
  
Quando si utilizza il metodo di caricamento di rete per importare i file PST, si carica un contenitore di blob Azure denominato **ingestiondata**. Se non esistono alcun processo di importazione in corso nella pagina **importazione** in sicurezza &amp; centro conformità), quindi tutti i file PST nel contenitore **ingestiondata** in Azure vengono eliminati 30 giorni dopo il processo di importazione più recente è stato creato in sicurezza &amp;Centro conformità. Ciò significa inoltre è necessario creare un nuovo processo di importazione per la protezione &amp; file del centro conformità entro 30 giorni di caricamento dei file PST (descritto nel passaggio 5 nelle istruzioni per il caricamento di rete) in Azure. 
  
Ciò significa inoltre che dopo l'eliminazione dei file PST dall'area di archiviazione Azure, vengono non vengono più visualizzati nell'elenco dei file di un processo di importazione completate nel titolo &amp; centro conformità. Anche se un processo di importazione può essere indicato nella pagina **importazione** in sicurezza &amp; centro conformità, l'elenco dei file PST può essere vuota quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Si basa sulle capacità della rete, ma in genere necessario diverse ore per ogni terabyte (TB) di dati da caricare nell'area di archiviazione Azure per la propria organizzazione. Dopo l'area di archiviazione Azure vengono copiati i file PST, viene importato un file PST in una cassetta postale Office 365 pari ad almeno 24 GB per ogni giorno. Se questa velocità non soddisfa le proprie esigenze, è consigliabile altri metodi per la migrazione dei dati di posta elettronica a Office 365. Per ulteriori informazioni, vedere [modi per eseguire la migrazione di più account di posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Se l'importano dei file PST diversi per le cassette postali di destinazione diversi, si verifica il processo di importazione in parallelo; in altre parole, ogni coppia di file PST/cassette postali viene importata contemporaneamente. Allo stesso modo, se la stessa cassetta postale vengono importati più file PST, saranno importate contemporaneamente.
  
 **Esiste una dimensione massima dei messaggi durante l'importazione di file PST?**
  
Sì. Se un file PST contiene una voce di cassetta postale è maggiore di 150 MB, l'elemento viene ignorato durante il processo di importazione.
  
 **Sono proprietà del messaggio, ad esempio quando il messaggio è stato inviato o ricevuto, l'elenco dei destinatari e altre proprietà mantenuta quando si importano file PST in una cassetta postale Office 365?**
  
Sì. I metadati messaggio originale non viene modificato durante il processo di importazione.
  
 **Esiste un limite al numero di livelli in una gerarchia di cartelle di un file PST che desidera importare in una cassetta postale?**
  
Sì. È possibile importare un file PST con 300 o più livelli di cartelle nidificate.
  
 **È possibile utilizzare il caricamento di rete per importare i file PST in una cassetta postale inattiva in Office 365?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile utilizzare il caricamento di rete per importare i file PST in una cassetta postale di archivio online in una distribuzione ibrida di Exchange?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile utilizzare il caricamento di rete per importare i file PST alle cartelle pubbliche in Exchange Online?**
  
No, è possibile importare file PST alle cartelle pubbliche.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Utilizzo di spedizione unità per importare i file PST

Per istruzioni dettagliate, vedere [utilizzo di unità di spedizione per importare i file PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnato il ruolo cassette postali importare esportare per importare i file PST alle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli di Exchange Online. È possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione. Oppure creare un nuovo gruppo di ruoli, assegnare il ruolo cassette postali importazione/esportazione e quindi aggiungere manualmente o altri utenti con un account membro. Per ulteriori informazioni, vedere "Aggiungere un ruolo da un gruppo di ruoli" o "Creare un gruppo di ruoli" sezioni in [gruppi di ruoli di gestione in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Inoltre, per creare Importa i processi in Office 365 Security &amp; centro conformità, uno dei seguenti devono essere vere:
  
- È necessario assegnare il ruolo destinatari di posta elettronica di Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione dei destinatari.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione Office 365.
    
> [!TIP]
> È consigliabile creare un nuovo gruppo di ruoli in Exchange Online che è progettata in modo specifico per l'importazione di file PST in Office 365. Livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importare l'esportazione delle cassette postali e destinatari di posta elettronica al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove unità disponibili disponibili?**
  
Unità shipping è attualmente disponibile in Stati Uniti, in Canada, Brasile, Regno Unito, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia. Unità shipping saranno resi disponibili in altre aree.
  
 **Le condizioni di licenza commerciale supportano shipping unità?**
  
Unità di spedizione per importare i file PST di Office 365 è disponibile tramite Microsoft Enterprise Agreement (EA). Unità di spedizione non è disponibile attraverso un Microsoft Products e servizi contratto (MPSA).
  
 **Che cos'è il prezzo per l'utilizzo di unità di spedizione per importare i file PST di Office 365?**
  
Il costo per utilizzare la distribuzione dei unità per importare i file PST alle cassette postali di Office 365 è 2 dollari per GB di dati. Ad esempio, se si fornisce un disco rigido contenente 1.000 GB (1 TB) dei file PST, il costo è $2.000 EUR. È possibile utilizzare un partner di pagare la quota di importazione. Per informazioni sulla ricerca di un partner, vedere [trovare un partner di Office 365 o rivenditori](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **Quali tipi di dischi rigidi sono supportati per la distribuzione dei unità?**
  
Solo da 2,5 pollici allo stato solido unità (Solid) o 2.5 o da 3,5 pollici SATA II/III dischi rigidi interni sono supportati per l'utilizzo con il servizio Office 365 importazione. È possibile utilizzare dischi rigidi fino a 10 TB. Per i processi di importazione, verrà elaborato solo il primo volume di dati sul disco rigido. Il volume di dati deve essere formattato con NTFS. Durante la copia dei dati in un disco rigido, è possibile allegare direttamente utilizzando un 2,5 pollici SSD o 3.5 o 2,5 pollici connettore SATA II/III o è possibile allegare esternamente utilizzando un esterno da 2,5 pollici SSD o 2.5 o 3.5 adattatore SATA II/III USB pollici.
  
> [!IMPORTANT]
> Unità disco rigido esterne implementati con un adattatore USB incorporato non sono supportate dal servizio di Office 365 importazione. Inoltre, il disco all'interno di maiuscole e minuscole di un'unità disco rigido esterna non può essere utilizzato. Non spedizione dischi rigidi esterni. 
  
 **Il numero di dischi rigidi posso forniti per un processo di importazione singolo**
  
È possibile fornire un massimo di 10 dischi rigidi per un processo di importazione singolo.
  
 **Dopo che è possibile inclusi nel disco rigido, quanto tempo è necessario per ottenere i data center Microsoft?**
  
Ciò dipende da diversi fattori, ad esempio il vicino al data center Microsoft e quale tipo di opzione di spedizione è utilizzato per forniti disco rigido (ad esempio, il giorno successivo, due giorni recapito o recapito suolo). Con la maggior parte dei corrieri, è possibile utilizzare il numero di registrazione per tenere traccia dello stato del recapito.
  
 **Dopo il disco rigido arrivo nel data center Microsoft, quanto tempo è necessario per caricare i file PST in Azure?**
  
Dopo che il disco rigido viene ricevuto nel data center Microsoft, richiede tra 7 a 10 giorni lavorativi per caricare i file PST all'area di archiviazione Microsoft Azure per la propria organizzazione. I file PST verranno caricati in un contenitore di blob Azure denominato **ingestiondata**. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dopo che i file PST vengono caricati nell'area di archiviazione Azure, Office 365 consente di analizzare i dati in file PST (in modo sicuro e protetto) per identificare la validità degli elementi e i diversi tipi di messaggi inclusi nei file PST. Una volta completata questa analisi, è necessario l'opzione per importare tutti i dati in file PST o impostare i filtri che controllano quali dati vengono importati. Dopo aver avviato il processo di importazione, viene importato un file PST in una cassetta postale Office 365 pari ad almeno 24 GB per ogni giorno. Se questa velocità non soddisfa le proprie esigenze, è consigliabile altri metodi per l'importazione dei dati di posta elettronica a Office 365. Per ulteriori informazioni, vedere [modi per eseguire la migrazione di più account di posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Se l'importano dei file PST diversi per le cassette postali di destinazione diversi, si verifica il processo di importazione in parallelo; in altre parole, ogni coppia di file PST/cassette postali viene importata contemporaneamente. Allo stesso modo, se la stessa cassetta postale vengono importati più file PST, saranno importate contemporaneamente.
  
 **Dopo che Microsoft consente di caricare i file PST in Azure, quanto tempo vengono vengono conservati in Azure prima dell'eliminazione è?**
  
Tutti i file PST nella posizione di archiviazione Azure per la propria organizzazione (nel contenitore di blob denominato **ingestiondata** ), vengono eliminati 30 giorni dopo il processo di importazione più recente è stato creato nella pagina **importazione** in sicurezza &amp; centro conformità. 
  
Ciò significa inoltre che dopo l'eliminazione dei file PST dall'area di archiviazione Azure, vengono non vengono più visualizzati nell'elenco dei file di un processo di importazione completate nel titolo &amp; centro conformità. Anche se un processo di importazione può essere indicato nella pagina **importazione** in sicurezza &amp; centro conformità, l'elenco dei file PST può essere vuota quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quale versione del formato di file PST è supportato per l'importazione in Office 365?**
  
Esistono due versioni del formato di file PST: ANSI e Unicode. È consigliabile l'importazione di file che utilizzano il formato di file PST in formato Unicode. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelle per le lingue che utilizzano un carattere DBCS impostato (DBCS), possono essere importati anche a Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 3 di [utilizzare l'unità di spedizione per importare i file PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
È inoltre possono importare i file PST di Outlook 2007 e versioni successive a Office 365.
  
 **Esiste una dimensione massima dei messaggi durante l'importazione di file PST?**
  
Sì. Se un file PST contiene una voce di cassetta postale è maggiore di 150 MB, l'elemento viene ignorato durante il processo di importazione.
  
 **Sono proprietà del messaggio, ad esempio quando il messaggio è stato inviato o ricevuto, l'elenco dei destinatari e altre proprietà mantenuta quando si importano file PST in una cassetta postale Office 365?**
  
Sì. I metadati messaggio originale non viene modificato durante il processo di importazione
  
 **Esiste un limite al numero di livelli in una gerarchia di cartelle di un file PST che desidera importare in una cassetta postale?**
  
Sì. È possibile importare un file PST con 300 o più livelli di cartelle nidificate.
  
 **È possibile utilizzare la distribuzione dei unità per importare i file PST in una cassetta postale inattiva in Office 365?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile utilizzare la distribuzione dei unità per importare i file PST in una cassetta postale di archivio online in una distribuzione ibrida di Exchange?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile utilizzare la distribuzione dei unità per importare i file PST alle cartelle pubbliche in Exchange Online?**
  
No, è possibile importare file PST alle cartelle pubbliche.
  
 **Il Microsoft può distruggere nel disco rigido prima che forniscono al mittente?**
  
No, Microsoft non possono cancellare i dati dischi rigidi prima di distribuirle ai clienti. Unità disco rigido vengono restituite all'utente nello stesso stato che anteriore al vengono ricevuti da Microsoft.
  
 **Microsoft può suddividere nel disco rigido anziché la spedizione al personale?**
  
No, Microsoft non può distruggere il disco rigido. Unità disco rigido vengono restituite all'utente nello stesso stato che anteriore al vengono ricevuti da Microsoft.
  
 **Quali servizi courier sono supportati per la distribuzione dei restituito?**
  
Se si è un cliente negli Stati Uniti o Europa, FedEx Microsoft utilizzato per restituire il disco rigido. Per tutte le altre aree DHL utilizzate da Microsoft.
  
 **Che cosa sono i costi di spedizione restituiti?**
  
Restituisce le spese di spedizione variano a seconda del vicino al data center Microsoft che sono stati inviati il disco rigido. Microsoft verrà fatturato FedEx o DHL per restituire il disco rigido. I costi di spedizione restituito sono responsabilità dell'utente.
  
 **È possibile utilizzare un servizio di spedizione courier personalizzate, ad esempio FedEx personalizzato Shipping, a inclusi nel disco rigido a Microsoft?**
  
Sì.
  
 **Se è necessario inclusi nel disco rigido in un altro paese, esiste qualsiasi operazione da eseguire?**
  
Il disco rigido forniti a Microsoft potrebbe essere necessario oltrepassare i bordi internazionali. In questo caso, si è responsabile di garantire che il disco rigido e i dati in che esso contenuti vengono importati e/o esportati in conformità con le normative vigenti. Prima di un disco rigido di spedizione, verificare con i propri consulenti, per verificare che l'unità e i dati possono essere spediti livello legale per i data center Microsoft specificato. In questo modo per assicurare che raggiunga Microsoft in modo tempestivo.
