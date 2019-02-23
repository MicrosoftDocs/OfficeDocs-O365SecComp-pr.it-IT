---
title: DOMANDE frequenti sull'importazione di file PST in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: "Domande frequenti per gli amministratori sull'utilizzo del servizio di importazione di Office 365 per importare i file PST di Organizaiton in cassette postali di Office 365. "
ms.openlocfilehash: 9ca2e206a1d06c1398181c51e41b4dc68d8d965c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218406"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>DOMANDE frequenti sull'importazione di file PST in Office 365

**Questo articolo è per gli amministratori. Si desidera importare i file PST nella propria cassetta postale? Vedere [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Di seguito sono riportate alcune domande frequenti sull'utilizzo del servizio di importazione di Office 365 per importare in blocco i file PST nelle cassette postali di Office 365. Per ulteriori informazioni su come importare i file PST, vedere [Overview of import PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Utilizzo del caricamento di rete per importare i file PST

Per istruzioni dettagliate, vedere [usare il caricamento di rete per importare i file PST in Office 365](use-network-upload-to-import-pst-files.md).
  
 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnati al ruolo di esportazione delle cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere se stessi o altri utenti come membri. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in Manage role groups [in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Per creare processi di importazione nel centro sicurezza &amp; e conformità di Office 365, è inoltre necessario che sia vero uno dei seguenti valori:
  
- È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione destinatari.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
> [!TIP]
> Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove è disponibile il caricamento di rete?**
  
Il caricamento di rete è attualmente disponibile negli Stati Uniti, Canada, Brasile, Regno Unito, Francia, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia. Il caricamento di rete sarà disponibile presto in più aree geografiche.
  
 **Qual è il prezzo per l'importazione di file PST tramite caricamento di rete?**
  
L'utilizzo del caricamento di rete per importare i file PST è gratuito.
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nell'interfaccia di amministrazione di Office 365. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa dati in Office 365** , l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **Quale versione del formato di file PST è supportata per l'importazione in Office 365?**
  
Sono disponibili due versioni del formato di file PST: ANSI e Unicode. Si consiglia di importare i file che utilizzano il formato di file PST Unicode. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelli relativi alle lingue che utilizzano un set di caratteri a doppio byte (DBCS), possono essere importati anche in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 4 in [use Network upload to import your organization ' s PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
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
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Utilizzo di spedizione unità per importare i file PST

Per istruzioni dettagliate, vedere [Use Drive Shipping to Import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
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
  
Dopo aver ricevuto il disco rigido in Microsoft Data Center, saranno necessari tra 7 e 10 giorni lavorativi per caricare i file PST nell'area di archiviazione di Microsoft Azure per l'organizzazione. I file PST verranno caricati in un contenitore BLOB di Azure denominato **ingestiondata**. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dopo aver caricato i file PST nell'area di archiviazione di Azure, Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) per identificare l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST. Al termine dell'analisi, è possibile importare tutti i dati nei file PST o impostare filtri per controllare i dati che vengono importati. Dopo aver avviato il processo di importazione, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa tariffa non soddisfa le proprie esigenze, è possibile prendere in considerazione altri metodi per importare i dati della posta elettronica in Office 365. Per ulteriori informazioni, vedere [modalità di migrazione di più account di posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Se sono stati importati diversi file PST in cassette postali di destinazione diverse, il processo di importazione viene eseguito in parallelo. in altre parole, ogni coppia di PST/cassette postali viene importata contemporaneamente. Analogamente, se più file PST vengono importati nella stessa cassetta postale, verranno importati contemporaneamente.
  
 **Dopo che Microsoft carica i file PST in Azure, per quanto tempo vengono conservati in Azure prima di essere eliminati?**
  
Tutti i file PST nel percorso di archiviazione di Azure per l'organizzazione (nel contenitore BLOB denominato **ingestiondata** ) vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nella pagina **Importa** nel centro &amp; sicurezza e conformità. 
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non sono più visualizzati nell'elenco dei file per un processo di importazione completato nel centro &amp; sicurezza e conformità. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa** nel centro &amp; sicurezza e conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **Quale versione del formato di file PST è supportata per l'importazione in Office 365?**
  
Sono disponibili due versioni del formato di file PST: ANSI e Unicode. Si consiglia di importare i file che utilizzano il formato di file PST Unicode. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelli relativi alle lingue che utilizzano un set di caratteri a doppio byte (DBCS), possono essere importati anche in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 3 in [Use Drive Shipping to Import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
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
