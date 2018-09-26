---
title: Panoramica di importazione dei file PST organizzazione a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: "Per gli amministratori: informazioni sull'utilizzo del servizio di importazione in Office 365 Security &amp; centro conformità al blocco importazione dati di posta elettronica (con estensione PST) alle cassette postali in Exchange Online. In questo argomento vengono fornite le domande frequenti e viene spiegato come funziona il processo di importazione file PST."
ms.openlocfilehash: 2bd58b879d9d4d1ff9d3d2c6c8680a0171d42689
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038019"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Panoramica di importazione dei file PST organizzazione a Office 365

> [!NOTE]
> In questo articolo sia per gli amministratori. Si sta tentando di importare i file PST alla propria cassetta postale? Vedere [posta elettronica di importazione, contatti e calendario da un file pst di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)

È possibile utilizzare il servizio di importazione in Office 365 Security &amp; centro conformità a rapidamente-importazione di massa PST file alle cassette postali di Exchange Online nell'organizzazione Office 365. Esistono due modi è possibile importare file PST in Office 365:
   
- **Caricamento di rete** ![Caricamento cloud](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) -caricare i file PST in rete in un percorso di archiviazione temporanea Azure nel cloud Microsoft. È quindi utilizzare il servizio Office 365 importare per importare i dati PST alle cassette postali nell'organizzazione Office 365. 

- **Unità di spedizione** ![Sul disco rigido](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) : copiare i file PST in un disco rigido crittografati con BitLocker e poi inviare fisicamente unità a Microsoft. Quando Microsoft riceve il disco rigido, personale del centro dati caricare i dati in un percorso di archiviazione temporanea Azure nel cloud Microsoft. È quindi utilizzare il servizio Office 365 importare per importare i dati delle cassette postali nell'organizzazione Office 365.

## <a name="step-by-step-instructions"></a>Istruzioni dettagliate
  
Vedere uno degli argomenti seguenti per istruzioni dettagliate per l'importazione in blocco file PST dell'organizzazione a Office 365. 
   
- [Utilizzare il caricamento di rete per importare i file PST su Office 365](use-network-upload-to-import-pst-files.md)
- [Utilizzare la spedizione dell'unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Funzionamento dell'importazione dei file PST

Ecco una figura e una descrizione del processo di importazione completato PST. Nella figura viene illustrato il flusso di lavoro principale e vengono evidenziate le differenze tra il caricamento di rete e l'unità metodi di spedizione.
  
![Flusso di lavoro del processo di importazione file PST](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **Scarica i file PST importare strumenti e il percorso di archiviazione Azure chiavi su private** - il primo passaggio consiste nel download il tasto strumento e access utilizzato per caricare i file PST o copiarli in un disco rigido. Per ottenere tali nella pagina **importazione** in Office 365 Security &amp; centro conformità. Il tasto fornisce si (o personale del centro dati di Microsoft in caso di spedizione unità) con le autorizzazioni necessarie per caricare i file PST in un percorso privata e Azure di archiviazione sicura. Questo tasto di scelta rapida è univoco nell'organizzazione e consente di impedire l'accesso non autorizzato ai file PST dopo essere state caricate nel cloud Microsoft. Si noti che l'importazione di file PST in Office 365 non richiede l'organizzazione disporre di una sottoscrizione di Azure separata. 
    
2. **Per il caricamento o copiare i file PST file** - il passaggio successivo dipende se si utilizza il caricamento di rete o della spedizione di unità per importare i file PST. In entrambi i casi, si utilizzerà lo strumento e la chiave di archiviazione sicura fornito nel passaggio precedente.
    
    - **Caricamento di rete** Lo strumento AzCopy.exe (scaricato nel passaggio 1) consente di caricare e archiviare i file PST in una posizione di archiviazione Azure nel cloud Microsoft. Si noti che il percorso di archiviazione Azure che il caricamento dei file PST a cui si trova nello stesso datacenter Microsoft internazionali in cui si trova l'organizzazione Office 365. 
    
      Per caricare li, i file PST che si desidera importare in Office 365 devono trovarsi in una condivisione file o un file server nella propria organizzazione.
    
    - **Unità di spedizione** Lo strumento WAImportExport.exe (scaricato nel passaggio 1) viene utilizzato per copiare i file PST nel disco rigido. Questo strumento consente di crittografare il disco rigido con BitLocker e quindi viene copiato il file pst nel disco rigido. Ad esempio il caricamento di rete, i file PST che si desidera copiare nel disco rigido devono trovarsi in una condivisione file o un file server nella propria organizzazione.
    
3. **Creare un file di mapping di importazione file PST** - dopo che sono stati caricati nella posizione di archiviazione Azure o copiati in un disco rigido i file PST, il passaggio successivo consiste nel creare un file virgole (CSV) virgola che specifica quali file i file PST cassette postali utente verrà importati per (a ND un file PST possono essere importati per cassetta postale principale dell'utente o loro cassetta postale di archiviazione). Il servizio Office 365 importare utilizzerà le informazioni per importare i file PST. 
    
4. **Processo di importazione crea un file PST** , il passaggio successivo consiste nel creare un processo di importazione file PST nella pagina **importazione** in sicurezza &amp; centro conformità e inviare il file di mapping di importazione di file PST creato nel passaggio precedente. Per il caricamento di rete (dal momento che i file PST sono stati caricati in Azure) Office 365 consente di analizzare i dati in file PST e offre la possibilità di impostare i filtri che consentono di controllare quali dati ottiene effettivamente importati alle cassette postali specificate nel file di mapping di importazione file PST. 
    
    Per la spedizione di unità, alcuni altri fattori effettuato a questo punto il processo.
    
    - Si forniti fisicamente il disco rigido in un data center Microsoft (l'indirizzo di spedizione per data center Microsoft viene visualizzata quando viene creato il processo di importazione)
    
    - Quando Microsoft riceve il disco rigido, personale del centro dati verrà caricare i file di file pst sul disco rigido per il percorso di archiviazione Azure per la propria organizzazione. Come indicato in precedenza, i file PST vengono caricati in un percorso di archiviazione Azure che si trova nello stesso datacenter Microsoft internazionali in cui si trova l'organizzazione Office 365.
    
      > [!NOTE]
      > I file PST sul disco rigido vengono caricati in Azure entro 7 a 10 giorni dopo che Microsoft ha ricevuto il disco rigido. 
  
      Ad esempio il processo di caricamento di rete, Office 365 consente di analizzare i dati in file PST e offre la possibilità di impostare i filtri che consentono di controllare quali dati ottiene effettivamente importati alle cassette postali specificate nel file di mapping di importazione del file PST.
    
    - Microsoft fornisce il disco rigido all'utente. 
    
5. **Filtro dati PST che verranno importati alle cassette postali** - dopo aver creato il processo di importazione (e dopo che i file PST da un processo di spedizione vengono caricati nel percorso di archiviazione Azure) Office 365 consente di analizzare i dati in file PST (in modo sicuro e in modo sicuro) con identificare la validità degli elementi e i diversi tipi di messaggi inclusi nei file PST. Una volta completata l'analisi ed sono possibile importare i dati, è possibile importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando i filtri che consentono di controllare quali dati vengono importati. 
    
6. **Avviare il processo di importazione file PST** - dopo l'inizio del processo di importazione, Office 365 utilizza le informazioni nel file di mapping di importazione file PST per importare i file pst dalla posizione di archiviazione Azure egli cassette postali degli utenti. Informazioni sullo stato del processo di importazione, incluse quelle relative a ogni file PST da importare, viene visualizzate nella pagina **importazione** in sicurezza &amp; centro conformità. Al termine del processo di importazione, lo stato del processo è impostato su **completo**.
  
## <a name="why-import-email-data-to-office-365"></a>Perché importare dati di posta elettronica a Office 365?

- Importazione di file PST di cassette postali degli utenti è possibile eseguire la migrazione di posta elettronica dell'organizzazione a Office 365.
    
- È possibile utilizzare la caratteristica di [Importazione intelligente](filter-data-when-importing-pst-files.md) per filtrare gli elementi in file PST in realtà, l'importazione alle cassette postali di destinazione. Consente troncare i dati importati tramite l'impostazione di filtri controllano quali dati vengono importati. 
    
- Importazione di dati di posta elettronica a Office 365 consente di soddisfare esigenze di conformità dell'organizzazione grazie alla possibilità di:
    
  - Abilitare [cassette postali di archiviazione](enable-archive-mailboxes.md) e fornire agli utenti di spazio di archiviazione aggiuntivi delle cassette postali di [archiviazione illimitato](unlimited-archiving.md) . 
    
  - Posizionare le cassette postali di [Conservazione per controversia legale](https://go.microsoft.com/fwlink/?linkid=841243) per conservare il contenuto. 
    
  - Utilizzare lo [strumento di ricerca di contenuto](content-search.md) di ricerca del contenuto delle cassette postali. 
    
  - Utilizzare i [casi di eDiscovery](ediscovery-cases.md) a Gestisci indagini legale dell'organizzazione 
    
  - Utilizzare [criteri di conservazione](retention-policies.md) nella protezione &amp; centro conformità per controllare la durata viene conservato il contenuto delle cassette postali e quindi eliminare il contenuto dopo la scadenza del periodo di conservazione. 
    
- Importazione di dati in Office 365 contribuisce a proteggere la perdita di dati. Dati di posta elettronica che viene importati in Office 365 ereditano le caratteristiche di disponibilità elevata di Exchange Online.
    
- Dati di posta elettronica in Office 365 sono disponibili per gli utenti da tutti i dispositivi perché è memorizzato nel cloud.
    
## <a name="importing-sharepoint-data-to-office-365"></a>Importazione di dati di SharePoint a Office 365

È inoltre possibile importare file e documenti agli account OneDrive e siti di SharePoint nella propria organizzazione Office 365. Per ulteriori informazioni, vedere [il caricamento di contenuto locale in SharePoint Online mediante i cmdlet di PowerShell](https://docs.microsoft.com/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>Domande frequenti sull'importazione di file PST in Office 365
  
Ecco alcune domande frequenti sull'utilizzo del servizio Office 365 importare per l'importazione in blocco dei file PST cassette postali di Office 365. 
  
- [Utilizzo di caricamento di rete per importare i file PST](#using-network-upload-to-import-pst-files)
  
- [Utilizzo di spedizione unità per importare i file PST](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Utilizzo di caricamento di rete per importare i file PST

 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnato il ruolo di importare l'esportazione delle cassette postali di Exchange Online per importare i file PST alle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli di Exchange Online. È possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione. Oppure creare un nuovo gruppo di ruoli, assegnare il ruolo cassette postali importazione/esportazione e quindi aggiungere manualmente o altri utenti con un account membro. Per ulteriori informazioni, vedere "Aggiungere un ruolo da un gruppo di ruoli" o "Creare un gruppo di ruoli" sezioni in [gruppi di ruoli di gestione in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Inoltre, per creare Importa i processi in Office 365 Security &amp; centro conformità, uno dei seguenti devono essere vere:
  
- È necessario assegnare il ruolo destinatari di posta elettronica di Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione dei destinatari.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione Office 365.
    
> [!TIP]
> È consigliabile creare un nuovo gruppo di ruoli in Exchange Online che è progettata in modo specifico per l'importazione di file PST in Office 365. Livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importare l'esportazione delle cassette postali e destinatari di posta elettronica al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove si trova il caricamento di rete disponibile?**
  
Caricamento di rete è attualmente disponibile in Stati Uniti, in Canada, Brasile, Regno Unito, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia. Caricamento di rete sarà disponibile in aree più breve.
  
 **Che cos'è il prezzo per l'importazione dei file PST utilizzando il caricamento di rete?**
  
Utilizzo di caricamento di rete per importare i file PST è disponibile.
  
Ciò significa inoltre che dopo l'eliminazione dei file PST dall'area di archiviazione Azure, vengono non vengono più visualizzati nell'elenco dei file di un processo di importazione completate nell'interfaccia di amministrazione di Office 365. Anche se un processo di importazione potrebbe ancora essere elencato nella pagina **Importa dati a Office 365** , l'elenco dei file PST può essere vuota quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quale versione del formato di file PST è supportato per l'importazione in Office 365?**
  
Esistono due versioni del formato di file PST: ANSI e Unicode. È consigliabile l'importazione di file che utilizzano il formato di file PST in formato Unicode. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelle per le lingue che utilizzano un carattere DBCS impostato (DBCS), possono essere importati anche a Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 4 nella [rete utilizzo caricare per importare i file PST a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).
  
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
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Utilizzo di spedizione unità per importare i file PST

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
  
Dopo che il disco rigido viene ricevuto nel data center Microsoft, richiede tra 7 a 10 giorni lavorativi per caricare i file PST all'area di archiviazione Microsoft Azure per la propria organizzazione. I file PST verranno caricati in un contenitore di blob Azure denominato `ingestiondata`. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dopo che i file PST vengono caricati nell'area di archiviazione Azure, Office 365 consente di analizzare i dati in file PST (in modo sicuro e protetto) per identificare la validità degli elementi e i diversi tipi di messaggi inclusi nei file PST. Una volta completata questa analisi, è necessario l'opzione per importare tutti i dati in file PST o impostare i filtri che controllano quali dati vengono importati. Dopo aver avviato il processo di importazione, viene importato un file PST in una cassetta postale Office 365 pari ad almeno 24 GB per ogni giorno. Se questa velocità non soddisfa le proprie esigenze, è consigliabile altri metodi per l'importazione dei dati di posta elettronica a Office 365. Per ulteriori informazioni, vedere [modi per eseguire la migrazione di più account di posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Se l'importano dei file PST diversi per le cassette postali di destinazione diversi, si verifica il processo di importazione in parallelo; in altre parole, ogni coppia di file PST/cassette postali viene importata contemporaneamente. Allo stesso modo, se la stessa cassetta postale vengono importati più file PST, saranno importate contemporaneamente.
  
 **Dopo che Microsoft consente di caricare i file PST in Azure, quanto tempo vengono vengono conservati in Azure prima dell'eliminazione è?**
  
Tutti i file PST nella posizione di archiviazione Azure per la propria organizzazione (nel contenitore di blob denominato `ingestiondata`), vengono eliminati a 30 giorni dopo il processo di importazione più recente è stato creato nella pagina **importazione** in sicurezza &amp; centro conformità. 
  
Ciò significa inoltre che dopo l'eliminazione dei file PST dall'area di archiviazione Azure, vengono non vengono più visualizzati nell'elenco dei file di un processo di importazione completate nel titolo &amp; centro conformità. Anche se un processo di importazione può essere indicato nella pagina **importazione** in sicurezza &amp; centro conformità, l'elenco dei file PST può essere vuota quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quale versione del formato di file PST è supportato per l'importazione in Office 365?**
  
Esistono due versioni del formato di file PST: ANSI e Unicode. È consigliabile l'importazione di file che utilizzano il formato di file PST in formato Unicode. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelle per le lingue che utilizzano un carattere DBCS impostato (DBCS), possono essere importati anche a Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 3 di [utilizzare l'unità di spedizione per importare i file PST organizzazione a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
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
