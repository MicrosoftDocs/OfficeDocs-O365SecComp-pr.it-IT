---
title: Overview of importing your organization PST files to Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: "Per gli amministratori: informazioni sull'utilizzo del servizio di importazione nel centro sicurezza &amp; e conformità di Office 365 per importare in blocco i dati della posta elettronica (file PST) nelle cassette postali degli utenti in Exchange Online. In questo argomento vengono illustrate le domande più frequenti e viene illustrato il funzionamento del processo di importazione PST."
ms.openlocfilehash: b6f32a6b5552773c197003ddac41c138539bb6ef
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218046"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Overview of importing your organization PST files to Office 365

> [!NOTE]
> Questo articolo è per gli amministratori. Si sta tentando di importare i file PST nella propria cassetta postale? Vedere [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)

È possibile utilizzare il servizio di importazione nel centro sicurezza &amp; e conformità di Office 365 per importare rapidamente i file PST nelle cassette postali di Exchange Online nell'organizzazione di Office 365. È possibile importare i file PST in Office 365 in due modi:
   
- **Caricamento di rete** ![Caricamento](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) cloud: caricare i file PST sulla rete in una posizione di archiviazione di Azure temporanea nel cloud Microsoft. Successivamente, utilizzare il servizio di importazione di Office 365 per importare i dati PST nelle cassette postali dell'organizzazione di Office 365. 

- **Spedizione di unità** ![Disco](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) rigido: copiare i file PST in un disco rigido crittografato con BitLocker e quindi spedire fisicamente l'unità a Microsoft. Quando Microsoft riceve il disco rigido, il personale del Data Center carica i dati in una posizione di archiviazione di Azure temporanea nel cloud Microsoft. Successivamente, utilizzare il servizio di importazione di Office 365 per importare i dati nelle cassette postali dell'organizzazione di Office 365.

## <a name="step-by-step-instructions"></a>Istruzioni dettagliate
  
Per istruzioni dettagliate su come importare in blocco i file PST dell'organizzazione in Office 365, vedere uno degli argomenti seguenti. 
   
- [Utilizzare il caricamento di rete per importare i file PST su Office 365](use-network-upload-to-import-pst-files.md)
- [Utilizzare la spedizione dell'unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Come viene utilizzato l'importazione di file PST

Di seguito è riportata un'illustrazione e una descrizione del processo di importazione PST completo. Nella figura viene illustrato il flusso di lavoro principale e vengono evidenziate le differenze tra il caricamento di rete e i metodi di spedizione delle unità.
  
![Flusso di lavoro del processo di importazione PST](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **Scaricare gli strumenti di importazione PST e la chiave per la posizione di archiviazione di Azure privata** -il primo passaggio consiste nel scaricare lo strumento e la chiave di accesso utilizzati per caricare i file PST o copiarli in un disco rigido. Tali dati vengono ottenuti dalla pagina **Importa** nel centro sicurezza &amp; e conformità di Office 365. La chiave fornisce (o il personale del centro dati Microsoft nel caso di spedizione di unità) con le autorizzazioni necessarie per caricare i file PST in una posizione di archiviazione privata e sicura di Azure. Questo tasto di accesso è univoco per l'organizzazione e consente di impedire l'accesso non autorizzato ai file PST dopo che sono stati caricati nel cloud Microsoft. Si noti che l'importazione di file PST in Office 365 non richiede che l'organizzazione disponga di una sottoscrizione di Azure distinta. 
    
2. **Caricamento o copia dei file PST** -il passaggio successivo varia a seconda che si utilizzi il caricamento di rete o l'unità di spedizione per importare i file PST. In entrambi i casi, è possibile utilizzare lo strumento e la chiave di archiviazione sicura ottenuta nel passaggio precedente.
    
    - **Caricamento di rete** Lo strumento AzCopy. exe, scaricato nel passaggio 1, viene utilizzato per caricare e archiviare i file PST in una posizione di archiviazione di Azure nel cloud Microsoft. Si noti che il percorso di archiviazione di Azure in cui si caricano i file PST risiede nello stesso datacenter Microsoft regionale in cui si trova l'organizzazione di Office 365. 
    
      Per caricarli, i file PST che si desidera importare in Office 365 devono trovarsi in una condivisione file o in un file server nell'organizzazione.
    
    - **Spedizione di unità** Lo strumento WAImportExport. exe, scaricato nel passaggio 1, viene utilizzato per copiare i file PST nell'unità disco rigido. Questo strumento crittografa l'unità disco rigido con BitLocker e quindi copia PST sul disco rigido. Analogamente al caricamento di rete, i file PST che si desidera copiare nell'unità disco rigido devono trovarsi in una condivisione file o in un file server dell'organizzazione.
    
3. **Creare un file di mapping di importazione PST** -dopo che i file PST sono stati caricati nel percorso di archiviazione di Azure o copiati in un disco rigido, il passaggio successivo consiste nel creare un file CSV (comma separated value) che specifichi le cassette postali degli utenti a cui verranno importati i file PST (a ND un file PST può essere importato nella cassetta postale principale o nella cassetta postale di archiviazione di un utente. Il servizio di importazione di Office 365 utilizzerà le informazioni per importare i file PST. 
    
4. **Creare un processo di importazione PST** -il passaggio successivo consiste nel creare un processo di importazione PST nella pagina **Importa** nel centro &amp; conformità sicurezza e nel inviare il file di mapping di importazione PST creato nel passaggio precedente. Per il caricamento di rete (perché i file PST sono stati caricati in Azure) Office 365 analizza i dati nei file PST e quindi offre la possibilità di impostare filtri che controllano quali dati vengono effettivamente importati nelle cassette postali specificate nel file di mapping di importazione PST. 
    
    Per la distribuzione di unità, a questo punto del processo si verificano alcune operazioni aggiuntive.
    
    - Spedire fisicamente l'unità disco rigido a un Data Center Microsoft (l'indirizzo di spedizione per il Data Center Microsoft viene visualizzato quando viene creato il processo di importazione)
    
    - Quando Microsoft riceve il disco rigido, il personale del Data Center caricherà i file di PST sul disco rigido nel percorso di archiviazione di Azure per l'organizzazione. Come spiegato in precedenza, i file PST vengono caricati in una posizione di archiviazione di Azure che risiede nello stesso datacenter Microsoft regionale in cui si trova l'organizzazione di Office 365.
    
      > [!NOTE]
      > I file PST sul disco rigido vengono caricati in Azure entro 7 o 10 giorni lavorativi dopo che Microsoft ha ricevuto l'unità disco rigido. 
  
      Analogamente al processo di caricamento di rete, Office 365 analizza i dati nei file PST e offre l'opportunità di impostare filtri che controllano quali dati vengono effettivamente importati nelle cassette postali specificate nel file di mapping di importazione PST.
    
    - Microsoft spedisce il disco rigido di nuovo all'utente. 
    
5. **Filtrare i dati pst che verranno** importati nelle cassette postali-dopo la creazione del processo di importazione (e dopo che i file PST di un processo di spedizione delle unità vengono caricati nel percorso di archiviazione di Azure) Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) da identificare l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST. Al termine dell'analisi e i dati sono pronti per l'importazione, si ha la possibilità di importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando filtri che controllano quali dati vengono importati. 
    
6. **Avviare il processo di importazione PST** -dopo l'avvio del processo di importazione, Office 365 utilizza le informazioni contenute nel file di mapping di importazione PST per importare i file di PST dal percorso di archiviazione di Azure alle cassette postali degli utenti. Le informazioni sullo stato relative al processo di importazione (incluse le informazioni su ogni file PST importato **** ) vengono visualizzate nella pagina &amp; importa del Centro sicurezza e conformità. Al termine del processo di importazione, lo stato del processo è impostato su **completo**.
  
## <a name="why-import-email-data-to-office-365"></a>Perché importare i dati della posta elettronica in Office 365?

- L'importazione di file PST nelle cassette postali degli utenti è uno dei modi per eseguire la migrazione della posta elettronica dell'organizzazione a Office 365.
    
- È possibile utilizzare la caratteristica [Intelligent Import](filter-data-when-importing-pst-files.md) per filtrare gli elementi nei file PST che vengono effettivamente importati nelle cassette postali di destinazione. In questo modo è possibile tagliare i dati importati impostando filtri che consentono di controllare i dati che vengono importati. 
    
- L'importazione dei dati di posta elettronica in Office 365 aiuta a soddisfare le esigenze di conformità dell'organizzazione, consentendo:
    
  - Abilitare le [cassette postali](enable-archive-mailboxes.md) di archiviazione e l' [archiviazione illimitata](unlimited-archiving.md) per offrire agli utenti ulteriore spazio di archiviazione. 
    
  - Posizionare le cassette postali sul [blocco per controversIa legale](https://go.microsoft.com/fwlink/?linkid=841243) per mantenere il contenuto. 
    
  - Utilizzare lo [strumento di ricerca contenuto](content-search.md) per cercare il contenuto delle cassette postali. 
    
  - Utilizzo dei [casi di eDiscovery](ediscovery-cases.md) per gestire le indagini legali dell'organizzazione 
    
  - Utilizzare i [criteri di conservazione](retention-policies.md) nel &amp; Centro sicurezza e conformità per controllare la durata di conservazione dei contenuti delle cassette postali e quindi eliminare il contenuto dopo la scadenza del periodo di mantenimento. 
    
- L'importazione di dati in Office 365 consente di evitare la perdita di dati. I dati di posta elettronica importati in Office 365 ereditano le funzionalità di disponibilità elevata di Exchange Online.
    
- I dati di posta elettronica in Office 365 sono disponibili per gli utenti da tutti i dispositivi perché sono archiviati nel cloud.
    
## <a name="importing-sharepoint-data-to-office-365"></a>Importazione di dati di SharePoint in Office 365

È inoltre possibile importare file e documenti nei siti di SharePoint e negli account di OneDrive nell'organizzazione di Office 365. Per ulteriori informazioni, vedere gli articoli seguenti:

- [Eseguire la migrazione a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [Introduzione allo Strumento di migrazione di SharePoint](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [Eseguire la migrazione a SharePoint Online con PowerShell](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [Eseguire la migrazione del contenuto della condivisione di file in SharePoint Online tramite la casella di dati di Azure](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>Domande frequenti sull'importazione di file PST in Office 365
  
Di seguito sono riportate alcune domande frequenti sull'utilizzo del servizio di importazione di Office 365 per importare in blocco i file PST nelle cassette postali di Office 365. 
  
- [Utilizzo del caricamento di rete per importare i file PST](#using-network-upload-to-import-pst-files)
  
- [Utilizzo di spedizione unità per importare i file PST](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Utilizzo del caricamento di rete per importare i file PST

 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnati al ruolo di esportazione delle cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere se stessi o altri utenti come membri. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in Manage role groups [in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Per creare processi di importazione nel centro sicurezza &amp; e conformità di Office 365, è inoltre necessario che sia vero uno dei seguenti valori:
  
- È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione destinatari.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
> [!TIP]
> Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove è disponibile il caricamento di rete?**
  
Il caricamento di rete è attualmente disponibile negli Stati Uniti, Canada, Brasile, Regno Unito, Europa, India, est asiatico, sud-est asiatico, Giappone, Repubblica di Corea e Australia. Il caricamento di rete sarà disponibile presto in più aree geografiche.
  
 **Qual è il prezzo per l'importazione di file PST tramite caricamento di rete?**
  
L'utilizzo del caricamento di rete per importare i file PST è gratuito.
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nell'interfaccia di amministrazione di Office 365. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa dati in Office 365** , l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **Quale versione del formato di file PST è supportata per l'importazione in Office 365?**
  
Sono disponibili due versioni del formato di file PST: ANSI e Unicode. Si consiglia di importare i file che utilizzano il formato di file PST Unicode. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelli relativi alle lingue che utilizzano un set di caratteri a doppio byte (DBCS), possono essere importati anche in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 4 in [use Network upload to Import PST files to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).
  
Inoltre, i file PST di Outlook 2007 e versioni successive possono essere importati in Office 365.
  
 **Dopo aver caricato i file PST nell'area di archiviazione di Azure, per quanto tempo sono conservati in Azure prima di essere eliminati?**
  
Quando si utilizza il metodo di caricamento di rete per importare i file PST, è possibile caricarli in un contenitore BLOB di Azure denominato **ingestiondata**. Se non sono presenti processi di importazione in corso nella pagina **Importa** nel centro sicurezza &amp; e conformità, tutti i file pst nel contenitore **ingestiondata** in Azure vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nella sicurezza &amp;Centro conformità. Questo significa anche che è necessario creare un nuovo processo di importazione nel centro &amp; conformità di sicurezza (descritto nel passaggio 5 nelle istruzioni per il caricamento di rete) entro 30 giorni dal caricamento dei file PST in Azure. 
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non sono più visualizzati nell'elenco dei file per un processo di importazione completato nel centro &amp; sicurezza e conformità. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa** nel centro &amp; sicurezza e conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dipende dalla capacità della rete, ma in genere richiede diverse ore per ogni terabyte di dati da caricare nell'area di archiviazione di Azure per l'organizzazione. Dopo aver copiato i file PST nell'area di archiviazione di Azure, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa percentuale non soddisfa le proprie esigenze, è possibile prendere in considerazione altri metodi per la migrazione dei dati di posta elettronica a Office 365. Per ulteriori informazioni, vedere [modalità di migrazione di più account di posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Se sono stati importati diversi file PST in cassette postali di destinazione diverse, il processo di importazione viene eseguito in parallelo. in altre parole, ogni coppia di PST/cassette postali viene importata contemporaneamente. Analogamente, se più file PST vengono importati nella stessa cassetta postale, verranno importati contemporaneamente.
  
 **Esiste un limite per la dimensione dei messaggi durante l'importazione dei file PST?**
  
Sì. Se un file PST contiene un elemento della cassetta postale di dimensioni superiori a 150 MB, l'elemento verrà ignorato durante il processo di importazione.
  
 **Sono proprietà del messaggio, ad esempio quando il messaggio è stato inviato o ricevuto, l'elenco di destinatari e altre proprietà, conservate quando i file PST vengono importati in una cassetta postale di Office 365?**
  
Sì. I metadati del messaggio originale non sono cambiati durante il processo di importazione.
  
 **Esiste un limite per il numero di livelli in una gerarchia di cartelle per un file PST che si desidera importare in una cassetta postale?**
  
Sì. Non è possibile importare un file PST con 300 o più livelli di cartelle nidificate.
  
 **È possibile utilizzare il caricamento di rete per importare i file PST in una cassetta postale inattiva in Office 365?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile utilizzare il caricamento di rete per importare i file PST in una cassetta postale di archiviazione online in una distribuzione ibrida di Exchange?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile utilizzare il caricamento di rete per importare i file PST in cartelle pubbliche in Exchange Online?**
  
No, non è possibile importare i file PST nelle cartelle pubbliche.
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Utilizzo di spedizione unità per importare i file PST

 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnati al ruolo import export delle cassette postali per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere se stessi o altri utenti come membri. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in Manage role groups [in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Per creare processi di importazione nel centro sicurezza &amp; e conformità di Office 365, è inoltre necessario che sia vero uno dei seguenti valori:
  
- È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione destinatari.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
> [!TIP]
> Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove è disponibile l'unità di spedizione?**
  
La spedizione di unità è attualmente disponibile negli Stati Uniti, Canada, Brasile, Regno Unito, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia. La spedizione delle unità sarà disponibile in più aree presto.
  
 **Quali contratti di licenza commerciale supportano la spedizione di unità?**
  
L'unità di trasporto per importare i file PST in Office 365 è disponibile tramite un contratto Microsoft Enterprise (EA). La distribuzione delle unità non è disponibile tramite un contratto di prodotti e servizi Microsoft (MPSA).
  
 **Qual è il prezzo per l'utilizzo della spedizione delle unità per importare i file PST in Office 365?**
  
Il costo per l'utilizzo della spedizione delle unità per importare i file PST nelle cassette postali di Office 365 è $2 USD per GB di dati. Ad esempio, se si spedisce un disco rigido che contiene 1.000 GB (1 TB) di file PST, il costo è $2.000 USD. È possibile collaborare con un partner per pagare la quota di importazione. Per informazioni su come trovare un partner, vedere [Find Your Office 365 partner or Reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **Quali tipi di dischi rigidi sono supportati per la distribuzione di unità?**
  
Solo 2,5 pollici Solid-State Drive (SSD) o 2,5 o 3,5 pollice SATA II/III unità disco rigido interne sono supportate per l'utilizzo con il servizio di importazione di Office 365. È possibile utilizzare dischi rigidi fino a 10 TB. Per i processi di importazione, verrà elaborato solo il primo volume di dati nel disco rigido. Il volume di dati deve essere formattato con NTFS. Quando si copiano i dati su un disco rigido, è possibile collegarlo direttamente usando un connettore SATA II/III da 2,5 pollici o 2,5 o 3,5 pollice oppure è possibile collegarlo esternamente usando un adattatore USB da 2,5 pollici SSD o 2,5 o 3,5 pollici SATA II/III.
  
> [!IMPORTANT]
> Le unità disco rigido esterne che dispongono di un adattatore USB incorporato non sono supportate dal servizio di importazione di Office 365. Non è inoltre possibile utilizzare il disco all'interno dell'involucro di un disco rigido esterno. Non inviare unità disco rigido esterne. 
  
 **Quante unità disco rigido è possibile spedire per un singolo processo di importazione?**
  
È possibile spedire fino a un massimo di 10 unità disco rigido per un singolo processo di importazione.
  
 **Dopo aver spedito il disco rigido, quanto tempo occorre per accedere al Data Center Microsoft?**
  
Questo dipende da alcune operazioni, ad esempio la vicinanza al Data Center Microsoft e il tipo di opzione di spedizione utilizzata per spedire l'unità disco rigido (ad esempio, il giorno successivo, il recapito di due giorni o la consegna a terra). Con la maggior parte dei corrieri, è possibile utilizzare il numero di tracciabilità per tenere traccia dello stato del recapito.
  
 **Dopo che il disco rigido arriva al Data Center Microsoft, quanto tempo occorre per caricare i file PST in Azure?**
  
Dopo aver ricevuto il disco rigido in Microsoft Data Center, saranno necessari tra 7 e 10 giorni lavorativi per caricare i file PST nell'area di archiviazione di Microsoft Azure per l'organizzazione. I file PST verranno caricati in un contenitore BLOB di Azure denominato `ingestiondata`. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dopo aver caricato i file PST nell'area di archiviazione di Azure, Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) per identificare l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST. Al termine dell'analisi, è possibile importare tutti i dati nei file PST o impostare filtri per controllare i dati che vengono importati. Dopo aver avviato il processo di importazione, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa tariffa non soddisfa le proprie esigenze, è possibile prendere in considerazione altri metodi per importare i dati della posta elettronica in Office 365. Per ulteriori informazioni, vedere [modalità di migrazione di più account di posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Se sono stati importati diversi file PST in cassette postali di destinazione diverse, il processo di importazione viene eseguito in parallelo. in altre parole, ogni coppia di PST/cassette postali viene importata contemporaneamente. Analogamente, se più file PST vengono importati nella stessa cassetta postale, verranno importati contemporaneamente.
  
 **Dopo che Microsoft carica i file PST in Azure, per quanto tempo vengono conservati in Azure prima di essere eliminati?**
  
Tutti i file PST nel percorso di archiviazione di Azure per l'organizzazione (nel contenitore `ingestiondata`BLOB denominato) vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nella pagina **Importa** nel centro &amp; sicurezza e conformità. 
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non sono più visualizzati nell'elenco dei file per un processo di importazione completato nel centro &amp; sicurezza e conformità. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa** nel centro &amp; sicurezza e conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **Quale versione del formato di file PST è supportata per l'importazione in Office 365?**
  
Sono disponibili due versioni del formato di file PST: ANSI e Unicode. Si consiglia di importare i file che utilizzano il formato di file PST Unicode. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelli relativi alle lingue che utilizzano un set di caratteri a doppio byte (DBCS), possono essere importati anche in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 3 in [Use Drive Shipping to import your organization PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Inoltre, i file PST di Outlook 2007 e versioni successive possono essere importati in Office 365.
  
 **Esiste un limite per la dimensione dei messaggi durante l'importazione dei file PST?**
  
Sì. Se un file PST contiene un elemento della cassetta postale di dimensioni superiori a 150 MB, l'elemento verrà ignorato durante il processo di importazione.
  
 **Sono proprietà del messaggio, ad esempio quando il messaggio è stato inviato o ricevuto, l'elenco di destinatari e altre proprietà, conservate quando i file PST vengono importati in una cassetta postale di Office 365?**
  
Sì. I metadati del messaggio originale non sono cambiati durante il processo di importazione
  
 **Esiste un limite per il numero di livelli in una gerarchia di cartelle per un file PST che si desidera importare in una cassetta postale?**
  
Sì. Non è possibile importare un file PST con 300 o più livelli di cartelle nidificate.
  
 **È possibile utilizzare la distribuzione delle unità per importare i file PST in una cassetta postale inattiva in Office 365?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile utilizzare il trasporto unità per importare i file PST in una cassetta postale di archiviazione online in una distribuzione ibrida di Exchange?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile utilizzare la distribuzione delle unità per importare i file PST nelle cartelle pubbliche in Exchange Online?**
  
No, non è possibile importare i file PST nelle cartelle pubbliche.
  
 **Microsoft può cancellare il disco rigido prima di rispedirlo all'utente?**
  
No, Microsoft non è in grado di cancellare dischi rigidi prima di rispedirli ai clienti. Le unità disco rigido vengono restituite all'utente nello stesso stato in cui si trovavano quando sono state ricevute da Microsoft.
  
 **Microsoft può tagliuzzare il disco rigido invece di rispedirlo a me?**
  
No, Microsoft non è in grado di distruggere l'unità disco rigido. Le unità disco rigido vengono restituite all'utente nello stesso stato in cui si trovavano quando sono state ricevute da Microsoft.
  
 **Quali servizi di corriere sono supportati per la spedizione di andata e ritorno?**
  
Se si è clienti negli Stati Uniti o in Europa, Microsoft utilizza FedEx per restituire il disco rigido. Microsoft utilizza DHL per tutte le altre aree geografiche.
  
 **Quali sono i costi di spedizione restituiti?**
  
I costi di spedizione restituiti variano in base alla prossimità al Data Center Microsoft a cui è stato inviato il disco rigido. Microsoft fattura l'account FedEx o DHL per restituire l'unità disco rigido. Il costo della spedizione di andata e ritorno è una tua responsabilità.
  
 **È possibile utilizzare un servizio di spedizione corriere personalizzato, ad esempio la spedizione personalizzata FedEx, per spedire l'unità disco rigido a Microsoft?**
  
Sì.
  
 **Se è necessario inviare l'unità disco rigido a un altro paese, è necessario eseguire le operazioni desiderate?**
  
Il disco rigido che si desidera inviare a Microsoft potrebbe dover attraversare i confini internazionali. In questo caso, l'utente è responsabile di verificare che l'unità disco rigido e i dati in esso contenuti siano importati e/o esportati in conformità con le leggi vigenti. Prima di inviare un disco rigido, verificare con i consulenti di verificare che l'unità e i dati possano essere inviati legalmente al Data Center Microsoft specificato. Ciò contribuirà a garantire che raggiunga Microsoft in modo tempestivo.
