---
title: Overview of importing your organization PST files to Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: "Per gli amministratori: informazioni sull'utilizzo del servizio di importazione nel centro sicurezza & Compliance per importare in blocco i dati della posta elettronica (file PST) nelle cassette postali degli utenti in Exchange Online. In questo argomento vengono illustrate le domande più frequenti e viene illustrato il funzionamento del processo di importazione PST."
ms.openlocfilehash: ab623c531f5e322a99aef5c8c33f110fc140a6f7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154223"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Overview of importing your organization PST files to Office 365

> [!NOTE]
> Questo articolo è per gli amministratori. L'utente sta tentando di importare file PST nella propria cassetta postale? Vedere [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)

È possibile utilizzare il servizio di importazione nel centro sicurezza & Compliance per importare rapidamente i file PST nelle cassette postali di Exchange Online nell'organizzazione di Office 365. È possibile importare i file PST in Office 365 in due modi:
   
- **Caricamento di rete** ![Caricamento](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) cloud: caricare i file PST sulla rete in una posizione di archiviazione di Azure temporanea nel cloud Microsoft. Successivamente, utilizzare il servizio di importazione di Office 365 per importare i dati PST nelle cassette postali dell'organizzazione di Office 365. 

- **Spedizione di unità** ![Disco](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) rigido: copiare i file PST in un disco rigido crittografato con BitLocker e quindi spedire fisicamente l'unità a Microsoft. Quando Microsoft riceve il disco rigido, il personale del Data Center carica i dati in una posizione di archiviazione di Azure temporanea nel cloud Microsoft. Successivamente, utilizzare il servizio di importazione di Office 365 per importare i dati nelle cassette postali dell'organizzazione di Office 365.

## <a name="step-by-step-instructions"></a>Istruzioni dettagliate
  
Per istruzioni dettagliate su come importare in blocco i file PST dell'organizzazione in Office 365, vedere uno degli argomenti seguenti. 
   
- [Utilizzare il caricamento di rete per importare i file PST su Office 365](use-network-upload-to-import-pst-files.md)
- [Utilizzare la spedizione dell'unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Come viene utilizzato l'importazione di file PST

Di seguito è riportata un'illustrazione e una descrizione del processo di importazione PST completo. Nella figura viene illustrato il flusso di lavoro principale e vengono evidenziate le differenze tra il caricamento di rete e i metodi di spedizione delle unità.
  
![Flusso di lavoro del processo di importazione PST](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **Scaricare gli strumenti di importazione PST e la chiave per la posizione di archiviazione di Azure privata** -il primo passaggio consiste nel scaricare lo strumento e la chiave di accesso utilizzati per caricare i file PST o copiarli in un disco rigido. Tali dati vengono ottenuti dalla pagina **Importa** del Centro sicurezza & Compliance. La chiave fornisce (o il personale del centro dati Microsoft nel caso di spedizione di unità) con le autorizzazioni necessarie per caricare i file PST in una posizione di archiviazione privata e sicura di Azure. Questo tasto di accesso è univoco per l'organizzazione e consente di impedire l'accesso non autorizzato ai file PST dopo che sono stati caricati nel cloud Microsoft. Si noti che l'importazione di file PST in Office 365 non richiede che l'organizzazione disponga di una sottoscrizione di Azure distinta. 
    
2. **Caricamento o copia dei file PST** -il passaggio successivo varia a seconda che si utilizzi il caricamento di rete o l'unità di spedizione per importare i file PST. In entrambi i casi, è possibile utilizzare lo strumento e la chiave di archiviazione sicura ottenuta nel passaggio precedente.
    
    - **Caricamento di rete** Lo strumento AzCopy. exe, scaricato nel passaggio 1, viene utilizzato per caricare e archiviare i file PST in una posizione di archiviazione di Azure nel cloud Microsoft. Si noti che il percorso di archiviazione di Azure in cui si caricano i file PST risiede nello stesso datacenter Microsoft regionale in cui si trova l'organizzazione di Office 365. 
    
      Per caricarli, i file PST che si desidera importare in Office 365 devono trovarsi in una condivisione file o in un file server nell'organizzazione.
    
    - **Spedizione di unità** Lo strumento WAImportExport. exe, scaricato nel passaggio 1, viene utilizzato per copiare i file PST nell'unità disco rigido. Questo strumento crittografa l'unità disco rigido con BitLocker e quindi copia PST sul disco rigido. Analogamente al caricamento di rete, i file PST che si desidera copiare nell'unità disco rigido devono trovarsi in una condivisione file o in un file server dell'organizzazione.
    
3. **Creare un file di mapping di importazione PST** -dopo che i file PST sono stati caricati nel percorso di archiviazione di Azure o copiati in un disco rigido, il passaggio successivo consiste nel creare un file CSV (comma separated value) che specifichi le cassette postali degli utenti a cui verranno importati i file PST (a ND un file PST può essere importato nella cassetta postale principale o nella cassetta postale di archiviazione di un utente. Il servizio di importazione di Office 365 utilizzerà le informazioni per importare i file PST. 
    
4. **Creare un processo di importazione PST** -il passaggio successivo consiste nel creare un processo di importazione PST nella pagina **Importa** del centro conformità & sicurezza e nel inviare il file di mapping di importazione PST creato nel passaggio precedente. Per il caricamento di rete (perché i file PST sono stati caricati in Azure) Office 365 analizza i dati nei file PST e quindi offre la possibilità di impostare filtri che controllano quali dati vengono effettivamente importati nelle cassette postali specificate nel file di mapping di importazione PST. 
    
    Per la distribuzione di unità, a questo punto del processo si verificano alcune operazioni aggiuntive.
    
    - Spedire fisicamente l'unità disco rigido a un Data Center Microsoft (l'indirizzo di spedizione per il Data Center Microsoft viene visualizzato quando viene creato il processo di importazione)
    
    - Quando Microsoft riceve il disco rigido, il personale del Data Center caricherà i file di PST sul disco rigido nel percorso di archiviazione di Azure per l'organizzazione. Come spiegato in precedenza, i file PST vengono caricati in una posizione di archiviazione di Azure che risiede nello stesso datacenter Microsoft regionale in cui si trova l'organizzazione di Office 365.
    
      > [!NOTE]
      > I file PST sul disco rigido vengono caricati in Azure entro 7 o 10 giorni lavorativi dopo che Microsoft ha ricevuto l'unità disco rigido. 
  
      Analogamente al processo di caricamento di rete, Office 365 analizza i dati nei file PST e offre l'opportunità di impostare filtri che controllano quali dati vengono effettivamente importati nelle cassette postali specificate nel file di mapping di importazione PST.
    
    - Microsoft spedisce il disco rigido di nuovo all'utente. 
    
5. **Filtrare i dati pst che verranno** importati nelle cassette postali-dopo la creazione del processo di importazione (e dopo che i file PST di un processo di spedizione delle unità vengono caricati nel percorso di archiviazione di Azure) Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) da identificare l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST. Al termine dell'analisi e i dati sono pronti per l'importazione, si ha la possibilità di importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando filtri che controllano quali dati vengono importati. 
    
6. **Avviare il processo di importazione PST** -dopo l'avvio del processo di importazione, Office 365 utilizza le informazioni contenute nel file di mapping di importazione PST per importare i file di PST dal percorso di archiviazione di Azure alle cassette postali degli utenti. Le informazioni sullo stato relative al processo di importazione (incluse le informazioni su ogni file PST importato) vengono visualizzate nella pagina **Importa** del Centro sicurezza & Compliance. Al termine del processo di importazione, lo stato del processo è impostato su **completo**.
  
## <a name="why-import-email-data-to-office-365"></a>Perché importare i dati della posta elettronica in Office 365?

- L'importazione di file PST nelle cassette postali degli utenti è uno dei modi per eseguire la migrazione della posta elettronica dell'organizzazione a Office 365.
    
- È possibile utilizzare la caratteristica [Intelligent Import](filter-data-when-importing-pst-files.md) per filtrare gli elementi nei file PST che vengono effettivamente importati nelle cassette postali di destinazione. In questo modo è possibile tagliare i dati importati impostando filtri che consentono di controllare i dati che vengono importati. 
    
- L'importazione dei dati di posta elettronica in Office 365 aiuta a soddisfare le esigenze di conformità dell'organizzazione, consentendo:
    
  - Abilitare le [cassette postali](enable-archive-mailboxes.md) di archiviazione e l' [archiviazione illimitata](unlimited-archiving.md) per offrire agli utenti ulteriore spazio di archiviazione. 
    
  - Posizionare le cassette postali sul [blocco per controversia legale](https://go.microsoft.com/fwlink/?linkid=841243) per mantenere il contenuto. 
    
  - Utilizzare lo [strumento di ricerca contenuto](content-search.md) per cercare il contenuto delle cassette postali. 
    
  - Utilizzo dei [casi di eDiscovery](ediscovery-cases.md) per gestire le indagini legali dell'organizzazione 
    
  - Utilizzare i [criteri di conservazione](retention-policies.md) nel centro sicurezza & Compliance per controllare la durata di conservazione del contenuto delle cassette postali e quindi eliminare il contenuto dopo la scadenza del periodo di mantenimento. 

  - Utilizzare i [criteri](supervision-policies.md) di supervisione per esaminare i messaggi per assicurarsi che siano conformi agli standard dei messaggi e aggiungere un tipo di classificazione.
    
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
  
È necessario essere assegnati al ruolo di esportazione delle cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in Manage role groups [in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Per creare processi di importazione nel centro sicurezza & Compliance, è inoltre necessario che sia vero uno dei seguenti valori:
  
- È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
> [!TIP]
> Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove è disponibile il caricamento di rete?**
  
Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nell'interfaccia di amministrazione di Microsoft 365. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa dati in Office 365** , l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelli relativi alle lingue che utilizzano un set di caratteri a doppio byte (DBCS), possono essere importati anche in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 4 in [use Network upload to Import PST files to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Dopo aver caricato i file PST nell'area di archiviazione di Azure, per quanto tempo sono conservati in Azure prima di essere eliminati?**
  
Quando si utilizza il metodo di caricamento di rete per importare i file PST, è possibile caricarli in un contenitore BLOB di Azure denominato **ingestiondata**. Se non sono presenti processi di importazione in corso nella pagina **Importa** nel centro sicurezza & Compliance, tutti i file pst nel contenitore **ingestiondata** in Azure vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nel & di sicurezza Centro conformità. Questo significa anche che è necessario creare un nuovo processo di importazione nel centro conformità di sicurezza & (descritto nel passaggio 5 nelle istruzioni per il caricamento di rete) entro 30 giorni dal caricamento dei file PST in Azure. 
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nel centro sicurezza & Compliance. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa** del Centro sicurezza & Compliance, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. Dopo aver copiato i file PST nell'area di archiviazione di Azure, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa percentuale non soddisfa le proprie esigenze, è possibile prendere in considerazione altri metodi per la migrazione dei dati di posta elettronica a Office 365. Per ulteriori informazioni, vedere [Modalità di migrazione della posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Analogamente, se più file PST vengono importati nella stessa cassetta postale, verranno importati contemporaneamente.
  
 **Is there a message size limit when importing PST files?**
  
Sì. Se un file PST contiene un elemento della cassetta postale di dimensioni superiori a 150 MB, l'elemento verrà ignorato durante il processo di importazione.
  
 **Sono proprietà del messaggio, ad esempio quando il messaggio è stato inviato o ricevuto, l'elenco di destinatari e altre proprietà, conservate quando i file PST vengono importati in una cassetta postale di Office 365?**
  
Sì. I metadati del messaggio originale non sono cambiati durante il processo di importazione.
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **È possibile utilizzare il caricamento di rete per importare i file PST in cartelle pubbliche in Exchange Online?**
  
No, non è possibile importare i file PST nelle cartelle pubbliche.
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Utilizzo di spedizione unità per importare i file PST

 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnati al ruolo import export delle cassette postali per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in Manage role groups [in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Per creare processi di importazione nel centro sicurezza & Compliance, è inoltre necessario che sia vero uno dei seguenti valori:
  
- È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
> [!TIP]
> Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove è disponibile l'unità di spedizione?**
  
La spedizione di unità è attualmente disponibile negli Stati Uniti, Canada, Brasile, Regno Unito, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia. Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
L'unità di trasporto per importare i file PST in Office 365 è disponibile tramite un contratto Microsoft Enterprise (EA). La distribuzione delle unità non è disponibile tramite un contratto di prodotti e servizi Microsoft (MPSA).
  
 **Qual è il prezzo per l'utilizzo della spedizione delle unità per importare i file PST in Office 365?**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. Per informazioni su come trovare un partner, vedere [Find Your Office 365 partner or Reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **What kind of hard drives are supported for drive shipping?**
  
Solo 2,5 pollici Solid-State Drive (SSD) o 2,5 o 3,5 pollice SATA II/III unità disco rigido interne sono supportate per l'utilizzo con il servizio di importazione di Office 365. You can use hard drives up to 10 TB. Per i processi di importazione, verrà elaborato solo il primo volume di dati nel disco rigido. The data volume must be formatted with NTFS. Quando si copiano i dati su un disco rigido, è possibile collegarlo direttamente usando un connettore SATA II/III da 2,5 pollici o 2,5 o 3,5 pollice oppure è possibile collegarlo esternamente usando un adattatore USB da 2,5 pollici SSD o 2,5 o 3,5 pollici SATA II/III.
  
> [!IMPORTANT]
> Le unità disco rigido esterne che dispongono di un adattatore USB incorporato non sono supportate dal servizio di importazione di Office 365. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Dopo che il disco rigido arriva al Data Center Microsoft, quanto tempo occorre per caricare i file PST in Azure?**
  
Dopo aver ricevuto il disco rigido in Microsoft Data Center, saranno necessari tra 7 e 10 giorni lavorativi per caricare i file PST nell'area di archiviazione di Microsoft Azure per l'organizzazione. I file PST verranno caricati in un contenitore BLOB di Azure denominato `ingestiondata`. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dopo aver caricato i file PST nell'area di archiviazione di Azure, Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) per identificare l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST. Al termine dell'analisi, è possibile importare tutti i dati nei file PST o impostare filtri per controllare i dati che vengono importati. Dopo aver avviato il processo di importazione, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa tariffa non soddisfa le proprie esigenze, è possibile prendere in considerazione altri metodi per importare i dati della posta elettronica in Office 365. Per ulteriori informazioni, vedere [Modalità di migrazione della posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Analogamente, se più file PST vengono importati nella stessa cassetta postale, verranno importati contemporaneamente.
  
 **Dopo che Microsoft carica i file PST in Azure, per quanto tempo vengono conservati in Azure prima di essere eliminati?**
  
Tutti i file PST nel percorso di archiviazione di Azure per l'organizzazione (nel contenitore `ingestiondata`BLOB denominato) vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nella pagina **Import** del Centro sicurezza & Compliance. 
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nel centro sicurezza & Compliance. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa** del Centro sicurezza & Compliance, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelli relativi alle lingue che utilizzano un set di caratteri a doppio byte (DBCS), possono essere importati anche in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 3 in [Use Drive Shipping to import your organization PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
Sì. Se un file PST contiene un elemento della cassetta postale di dimensioni superiori a 150 MB, l'elemento verrà ignorato durante il processo di importazione.
  
 **Sono proprietà del messaggio, ad esempio quando il messaggio è stato inviato o ricevuto, l'elenco di destinatari e altre proprietà, conservate quando i file PST vengono importati in una cassetta postale di Office 365?**
  
Sì. I metadati del messaggio originale non sono cambiati durante il processo di importazione
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **È possibile utilizzare la distribuzione delle unità per importare i file PST nelle cartelle pubbliche in Exchange Online?**
  
No, non è possibile importare i file PST nelle cartelle pubbliche.
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Microsoft può tagliuzzare il disco rigido invece di rispedirlo a me?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Quali servizi di corriere sono supportati per la spedizione di andata e ritorno?**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **Quali sono i costi di spedizione restituiti?**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **È possibile utilizzare un servizio di spedizione corriere personalizzato, ad esempio la spedizione personalizzata FedEx, per spedire l'unità disco rigido a Microsoft?**
  
Sì.
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
