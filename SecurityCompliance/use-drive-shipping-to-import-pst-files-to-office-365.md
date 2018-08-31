---
title: Utilizzare la distribuzione dei unità per importare i file PST organizzazione a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: "Per gli amministratori: informazioni su come importare blocco file PST dell'organizzazione per le cassette postali di Office 365 copiando file PST in un disco rigido e a Microsoft per la spedizione. "
ms.openlocfilehash: ebe88918b6c25e18562db7817d22fbf71f05e4c7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530715"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a>Utilizzare la distribuzione dei unità per importare i file PST organizzazione a Office 365

**In questo articolo sia per gli amministratori. Si sta tentando di importare i file PST alla propria cassetta postale? Vedere [posta elettronica di importazione, contatti e calendario da un file pst di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Utilizzare il servizio Office 365 importazione e l'unità di spedizione per l'importazione in blocco dei file PST cassette postali degli utenti. Unità shipping indica copiare i file PST in un'unità disco rigido e quindi forniti fisicamente unità a Microsoft. Quando Microsoft riceve il disco rigido, personale del centro dati copierà i dati dall'unità disco per un'area di archiviazione nel cloud Microsoft. È quindi necessario la possibilità di tagliare i dati PST effettivamente importati alle cassette postali di destinazione impostando i filtri che consentono di controllare quali dati vengono importati. Dopo aver avviato il processo di importazione, il servizio Import Importa i dati PST dall'area di archiviazione per cassette postali degli utenti. L'utilizzo di spedizione unità per importare i file PST di cassette postali degli utenti è possibile eseguire la migrazione di posta elettronica dell'organizzazione a Office 365.
  
Di seguito sono i passaggi necessari per utilizzare la distribuzione dei unità per importare i file PST alle cassette postali di Office 365:
  
[Passaggio 1: Scaricare lo strumento di importazione di file PST e la chiave di archiviazione sicura](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[Passaggio 2: Copiare i file PST nel disco rigido](#step-2-copy-the-pst-files-to-the-hard-drive)

[Passaggio 3: Creare il file di mapping di importazione di file PST](#step-3-create-the-pst-import-mapping-file)

[Passaggio 4: creare un processo di Importazione PST in Office 365](#step-4-create-a-pst-import-job-in-office-365)

[Passaggio 5: inviare l'unità disco rigido a Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[Passaggio 6: Filtrare i dati e avviare il processo di importazione di file PST](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> È necessario eseguire il passaggio 1 una sola volta per verso il basso caricare la chiave di archiviazione sicura e lo strumento di importazione. Dopo aver eseguito queste operazioni, eseguire il passaggio 2 e passaggio 6 ogni volta che si desidera rendere disponibile un disco rigido a Microsoft. 
  
Per domande domande frequenti sull'utilizzo di unità di spedizione per importare i file PST in Office 365, vedere [domande frequenti per l'utilizzo di unità di spedizione per importare i file PST](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files). 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere assegnato il ruolo di importare l'esportazione delle cassette postali di Exchange Online per importare i file PST alle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli di Exchange Online. È possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione. Oppure creare un nuovo gruppo di ruoli, assegnare il ruolo cassette postali importazione/esportazione e quindi aggiungere l'utente come membro. Per ulteriori informazioni, vedere "Aggiungere un ruolo da un gruppo di ruoli" o "Creare un gruppo di ruoli" sezioni in [gruppi di ruoli di gestione](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Inoltre, per creare Importa i processi in Office 365 Security &amp; centro conformità, uno dei seguenti devono essere vere:
    
  - È necessario assegnare il ruolo destinatari di posta elettronica di Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione dei destinatari.
    
    Oppure
    
  - È necessario essere un amministratore globale dell'organizzazione Office 365.
    
    > [!TIP]
    > È consigliabile creare un nuovo gruppo di ruoli in Exchange Online che è progettata in modo specifico per l'importazione di file PST in Office 365. Livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importare l'esportazione delle cassette postali e destinatari di posta elettronica al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
- È necessario archiviare i file PST che si desidera copiare in un disco rigido in un server di file o una cartella condivisa all'interno dell'organizzazione. Nel passaggio 2 consente di eseguire lo strumento Azure importazione/esportazione (WAImportExport.exe) che verrà copiato i file PST che vengono memorizzati nel server di file o cartella sul disco rigido condivisa.
    
- Solo da 2,5 pollici allo stato solido unità (Solid) o 2.5 o da 3,5 pollici SATA II/III dischi rigidi interni sono supportati per l'utilizzo con il servizio Office 365 importazione. È possibile utilizzare dischi rigidi fino a 10 TB. Per i processi di importazione, verrà elaborato solo il primo volume di dati sul disco rigido. Il volume di dati deve essere formattato con NTFS. Durante la copia dei dati in un disco rigido, è possibile allegare direttamente utilizzando un 2,5 pollici SSD o 3.5 o 2,5 pollici connettore SATA II/III o è possibile allegare esternamente utilizzando un esterno da 2,5 pollici SSD o 2.5 o 3.5 adattatore SATA II/III USB pollici.
    
    > [!IMPORTANT]
    > Unità disco rigido esterne implementati con un adattatore USB incorporato non sono supportate dal servizio di Office 365 importazione. Inoltre, il disco all'interno di maiuscole e minuscole di un'unità disco rigido esterna non può essere utilizzato. Non spedizione dischi rigidi esterni. 
  
- Disco rigido in cui copiare i file PST deve essere crittografato con BitLocker. Lo strumento WAImportExport.exe che viene eseguita nel passaggio 2 consentono di configurare BitLocker. Viene inoltre generata una chiave di crittografia BitLocker da Microsoft personale del centro dati verrà utilizzato per accedere all'unità per caricare i file PST all'area di archiviazione Azure nel cloud Microsoft.
    
- Unità shipping è disponibile tramite Microsoft Enterprise Agreement (EA). Unità di spedizione non è disponibile attraverso un Microsoft Products e servizi contratto (MPSA).
    
- Il costo per importare i file PST alle cassette postali di Office 365 utilizzando shipping unità è 2 dollari per GB di dati. Ad esempio, se si fornisce un disco rigido contenente 1.000 GB (1TB) dei file PST, il costo è $2.000 EUR. È possibile utilizzare un partner di pagare la quota di importazione. Per informazioni sulla ricerca di un partner, vedere [trovare un partner di Office 365 o rivenditori](https://go.microsoft.com/fwlink/p/?LinkId=785197).
    
- L'utente o la relativa organizzazione deve disporre di un account FedEx o DHL. 
    
  - Le organizzazioni negli Stati Uniti, Brasile ed Europe devono disporre di account FedEx.
    
  - Le organizzazioni in Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia devono disporre di account DHL.
    
    Microsoft farà ricorso (e addebiterà le spese) a tali account per la restituzione delle unità disco rigido agli utenti. 
    
- L'unità disco rigido inviata a Microsoft potrebbe dover attraversare i confini nazionali. In tal caso, l'utente è tenuto ad accertarsi che l'unità disco rigido e i dati in essa contenuti vengano importati e/o esportati in conformità alle leggi applicabili. Prima dell'invio di un'unità disco rigido, verificare con i propri consulenti che sia legalmente possibile inviare l'unità e i dati al data center Microsoft identificato. Ciò contribuirà a garantire che i supporti raggiungano Microsoft in tempo utile.
    
- Questa procedura è necessario copiare e salvare una chiave di archiviazione sicura e di una chiave di crittografia BitLocker. È necessario adottare alcune precauzioni per proteggere queste sequenze di tasti come si proteggono password o altre informazioni relative alla sicurezza. Ad esempio, si potrebbero salvarli in un documento di Microsoft Word protetti da password o salvarli in un'unità USB crittografata. Vedere la sezione [informazioni](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) per un esempio di queste chiavi. 
    
- Dopo l'importano dei file PST in una cassetta postale Office 365, il mantenimento di impostazione per la cassetta postale è attivata per un periodo indefinito. Ciò significa che il criterio di conservazione assegnato alla cassetta postale non verrà elaborato fino a quando non si consente di disattivare il mantenimento o si imposta una data per disattivare il blocco. Perché questa operazione è necessaria Se i vecchi messaggi importati in una cassetta postale, potrebbe essere eliminati definitivamente (cancellati) perché il periodo di conservazione è scaduto in base alle impostazioni di conservazione configurate per la cassetta postale. Per ottenere l'ora di proprietario della cassetta postale per gestire i messaggi appena importato o fornire il tempo necessario per modificare le impostazioni di conservazione per la cassetta postale, effettuare la cassetta postale in attesa di conservazione. Per suggerimenti sulla gestione di attesa di conservazione, vedere [ulteriori informazioni](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) . 
    
- Per impostazione predefinita, la dimensione massima dei messaggi può ricevere una cassetta postale di Office 365 è 35 MB. Ciò avviene perché il valore predefinito per la proprietà *MaxReceiveSize* per una cassetta postale è impostato su 35 MB. Tuttavia, il limite per la massima dei messaggi di ricezione dimensioni in Office 365 è 150 MB. Quindi, se si importa un file PST contenente un elemento di dimensioni superiore a 35 MB, il servizio Office 365 importare è modificherà automaticamente il valore della proprietà *MaxReceiveSize* nella cassetta postale di destinazione a 150 MB. In questo modo i messaggi fino a 150 MB da importare per cassette postali degli utenti. 
    
    > [!TIP]
    > Per identificare il messaggio venga visualizzato dimensioni di una cassetta postale, è possibile eseguire questo comando in Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`. 
  
- È possibile importare file PST in una cassetta postale inattiva in Office 365. A tale scopo, che specifica il GUID della cassetta postale inattiva nel `Mailbox` parametro nel file di mapping di importazione di file PST. Vedere [passaggio 3: creare il file di mapping di importazione di file PST](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) per ulteriori informazioni. 
    
- In una distribuzione ibrida di Exchange, è possibile importare file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è locale. A tale scopo, eseguire le operazioni seguenti nel file di mapping di importazione di file PST:
    
  - Specificare l'indirizzo di posta elettronica della cassetta postale locale dell'utente nel `Mailbox` parametro. 
    
  - Specificare il valore **TRUE** nel `IsArchive` parametro. 
    
    Vedere [passaggio 3: creare il file di mapping di importazione di file PST](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) per ulteriori informazioni. 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>Passaggio 1: Scaricare lo strumento di importazione di file PST e la chiave di archiviazione sicura

È il primo passaggio per scaricare la chiave di archiviazione sicura e lo strumento e che si utilizzerà nel passaggio 2 per copiare i file PST nel disco rigido.
  
> [!IMPORTANT]
> È necessario utilizzare versione dello strumento di importazione/esportazione Azure 1 (WAimportExportV1) per importare correttamente i file PST utilizzando il metodo di spedizione unità. Non è supportata la versione 2 dello strumento di importazione/esportazione Azure e utilizzarlo, verrà generato in modo non corretto nel disco rigido la preparazione per il processo di importazione. Assicurarsi di scaricare lo strumento di importazione/esportazione Azure la sicurezza &amp; centro conformità eseguendo le procedure descritte in questo passaggio. 
  
1. Accedere a [https://protection.office.com/](https://protection.office.com/) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance dati** \> **importazione**.
    
    > [!NOTE]
    > Come affermato in precedenza, è necessario disporre delle autorizzazioni appropriate per accedere alla pagina di **importazione** per la protezione &amp; centro conformità. 
  
3. Nella pagina **importazione** fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
4. Nell'Importazione guidata processo, digitare un nome per il processo di importazione file PST e quindi fare clic su **Avanti**. Utilizzare le lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella pagina **scegliere il tipo di processo di importazione** fare clic su **unità disco rigido Shipping su uno dei nostri posizioni fisiche** e quindi fare clic su **Avanti**.
    
    ![Fare clic su unità disco rigido Shipping su uno dei nostri posizioni fisiche per creare un'unità di processo di importazione per la distribuzione](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Nella pagina **Importa dati** eseguire le due operazioni seguenti: 
    
    ![Copiare la chiave di archiviazione sicura e scaricare lo strumento di importazione ed esportazione di Azure nella pagina Importa dati](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    r. nel passaggio 2, fare clic su **copiare la chiave di archiviazione sicura**. Dopo che viene visualizzata la chiave di archiviazione, fare clic su **Copia negli Appunti** e incollarlo e salvarla in un file in modo è possibile accedervi più avanti.
    
    b. nel passaggio 3, **scaricare lo strumento di importazione/esportazione Azure** per scaricare e installare lo strumento di importazione/esportazione di Azure (versione 1).
    
    - Nella finestra popup, fare clic su **Salva** \> **Salva** per salvare il file WaImportExportV1.zip in una cartella nel computer locale. 
    
    - Estrarre il file WaImportExportV1.zip.
    
7. Fare clic su **Annulla** per chiudere la procedura guidata. 
    
    Verrà tornare alla schermata **l'importazione** nella protezione &amp; centro conformità quando si crea il processo di importazione nel passaggio 4. 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>Passaggio 2: Copiare i file PST nel disco rigido

Il passaggio successivo è utilizzare lo strumento WAImportExport.exe per copiare i file PST nel disco rigido. Questo strumento consente di crittografare il disco rigido con BitLocker, consente di copiare i file pst nel disco rigido e crea un file del journal che archivia le informazioni sul processo di copia. Per completare questo passaggio, al file PST devono trovarsi in una condivisione file o un file server nella propria organizzazione. Questo è noto come directory di origine nella procedura seguente. 
  
> [!IMPORTANT]
> Dopo aver eseguito lo strumento WAImportExport.exe la prima volta per un'unità disco rigido, è necessario utilizzare una sintassi diversa per ogni tempo in seguito. La sintassi seguente è descritto nel passaggio 4 di questa procedura per copiare i file PST nel disco rigido. 
  
1. Aprire un prompt dei comandi nel computer locale.
    
    > [!TIP]
    > Se si esegue il prompt dei comandi come amministratore (selezionando "Esegui come amministratore" al momento dell’apertura), verranno visualizzati dei messaggi di errore nella finestra del prompt dei comandi. Ciò consente di risolvere i problemi durante l'esecuzione dello strumento WAImportExport.exe. 
  
2. Accedere alla directory nella quale è stato installato lo strumento WAImportExport.exe durante il primo passaggio.
    
3. Eseguire il comando riportato di seguito la prima volta che si utilizza lo strumento WAImportExport.exe per copiare i file PST in un'unità disco rigido.

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    Nella tabella seguente vengono descritti i parametri e i relativi valori.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |Specifica il nome del file journal. Questo file viene salvato nella stessa cartella in cui si trova lo strumento WAImportExport.exe. È necessario che ogni unità disco rigido inviata a Microsoft disponga di un file journal. Ogni volta che si esegue lo strumento WAImportTool.exe per copiare i file PST in un'unità disco rigido, le informazioni verranno aggiunte al file journal per tale unità. 
  <br/> Per associare il disco rigido del processo di importazione creato nel passaggio 4 e caricare i file PST all'area di archiviazione Azure nel cloud Microsoft, personale del centro dati di Microsoft utilizzeranno le informazioni nel file del journal.  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |Specifica la lettera di unità del disco rigido quando è connesso al computer locale.  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |Specifica il nome della sessione di copia. Per sessione si intende ogni singola esecuzione dello strumento WAImportExport.exe per copiare i file nell'unità disco rigido. I file PST vengono copiati in una cartella con il nome di sessione specificato da questo parametro.   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |Specifica la directory di origine all'interno dell'organizzazione che contiene i file PST che saranno copiati durante la sessione. È necessario racchiudere il valore di questo parametro con virgolette doppie ("").  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |Specifica la directory di destinazione nell'area di archiviazione Azure nel cloud Microsoft in cui verrà caricato il file pst. È necessario utilizzare il valore `ingestiondata/`. È necessario racchiudere il valore di questo parametro con virgolette doppie ("").<br/> Facoltativamente, è inoltre possibile aggiungere un percorso di file aggiuntivo sul valore del parametro. Ad esempio, è possibile utilizzare il percorso della directory di origine sul disco rigido (convertito in un formato URL) specificato nel `/srcdir:` parametro. Ad esempio `\\FILESERVER01\PSTs` viene modificata in `FILESERVER01/PSTs`. In questo caso, è comunque necessario includere `ingestiondata` nel percorso del file. In tal caso, in questo esempio, il valore per il `/dstdir:` parametro sarà `"ingestiondata/FILESERVER01/PSTs"`.<br/> Uno dei motivi per aggiungere il percorso aggiuntivo è se sono presenti file file pst con lo stesso nome.  <br/> > [!NOTE]> Se si include il nome del percorso facoltativo, lo spazio dei nomi per un file PST dopo che caricata l'area di archiviazione Azure sarà incluso il percorso e il nome del file PST. ad esempio `FILESERVER01/PSTs/annb.pst`. Se non si include un nome di percorso, lo spazio dei nomi è solo il nome file PST; ad esempio `annb.pst`.           | `/dstdir:"ingestiondata/"` <br/> Oppure  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |Specifica la chiave di account di archiviazione fornito nel passaggio 1. È necessario racchiudere il valore di questo parametro con virgolette doppie ("").  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |Questa opzione attiva BitLocker per l'unità disco rigido. Il parametro è obbligatorio la prima volta che si esegue lo strumento WAImportExport.exe.  <br/> La chiave di crittografia BitLocker viene copiata il file di registro e file di registro creato se si utilizza il `/logfile:` parametro. Come indicato in precedenza, il file di registro viene salvato nella stessa cartella in cui si trova lo strumento WAImportExport.exe.<br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |Questo parametro opzionale consente di specificare una cartella in cui salvare i file registro. Se non specificato, i file di registro sono Salva nella stessa cartella in cui si trova lo strumento WAImportExport.exe. È necessario racchiudere il valore di questo parametro con virgolette doppie ("").  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    Di seguito è riportato un esempio di sintassi dello strumento WAImportExport.exe nella quale vengono utilizzati i valori effettivi di ogni parametro:
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    Una volta eseguito il comando, i messaggi di stato visualizzati riportano informazioni sull'avanzamento della copia dei file PST nell'unità disco rigido. Nel messaggio finale viene riportato il numero complessivo di file che sono stati copiati. 
    
4. Eseguire questo comando ogni volta che verrà eseguito lo strumento WAImportExport.ext per copiare i file PST nella stessa unità disco rigido.

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    Di seguito è riportato un esempio della sintassi necessaria per le sessioni successive per copiare i file PST nella stessa unità disco rigido.  

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>Passaggio 3: Creare il file di mapping di importazione di file PST

Dopo aver personale del centro dati Microsoft caricare i file PST dal disco rigido per l'area di archiviazione Azure, il servizio di importazione verrà utilizzate le informazioni nel file di mapping di importazione di file PST, che corrisponde a un file CSV (valori) separato da virgole, che specifica quali cassette postali degli utenti i file PST i file verranno importati in. In questo file CSV nel passaggio successivo verrà inviato quando si crea un processo di importazione di file PST.
  
1. [Scarica una copia del file di mapping di importazione di file PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Aprire o salvare il file CSV nel computer locale. Nell'esempio seguente viene visualizzato un file di mapping di importazione PST completo (aperto nel Blocco note). È molto più facile usare Microsoft Excel per modificare il file CSV.

    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    La prima riga o una riga di intestazione, del file CSV sono elencati i parametri che verranno utilizzati dal servizio di importazione di file PST per importare i file PST di cassette postali degli utenti. Ogni nome del parametro è separata da una virgola. Ogni riga sotto la riga di intestazione rappresenta i valori dei parametri per l'importazione di un file PST in una cassetta postale specifica. È necessario una riga per ogni file PST copiato nel disco rigido. Assicurarsi di sostituire i segnaposto i dati nel file di mapping con dati effettivi.

    > [!NOTE]
    > Non apportare modifiche nella riga di intestazione, compresi i parametri SharePoint; verranno ignorati durante il processo di impostazione PST. 
  
3. Utilizzare le informazioni della tabella per popolare il file CSV con i dati necessari.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Specifica il servizio di Office 365 per i dati verranno importati. Per importare i file PST di cassette postali degli utenti, utilizzare `Exchange`.<br/> | `Exchange` <br/> |
    | `FilePath` <br/> | Specifica il percorso della cartella nell'area di archiviazione Azure che i file PST verranno copiati quando è inclusa nel disco rigido a Microsoft.  <br/>  In questa colonna nel file CSV è aggiungere dipende elementi specificati per il `/dstdir:` parametro nel passaggio precedente.  <br/>  Se è stato utilizzato `/dstdir:"ingestiondata/"`, quindi lasciare vuoto questo parametro nel file CSV.  <br/>  Se incluso un percorso facoltativo per il valore della `/dstdir:` parametro (ad esempio `/dstdir:"ingestiondata/FILESERVER01/PSTs"`, quindi utilizzare tale percorso (escluso "ingestiondata") per questo parametro nel file CSV. Il valore per questo parametro viene fatta distinzione tra maiuscole e minuscole.<br/>  In entrambi i casi, *non* includere "ingestiondata" nel valore per il `FilePath` parametro. Lasciare vuoto questo parametro o specificare solo il nome del percorso facoltativo.<br/> > [!IMPORTANT]> Caso il nome del percorso file deve essere lo stesso caso specificato nel `/dstdir:` parametro nel passaggio precedente. Ad esempio, se è stato utilizzato `"ingestiondata/FILESERVER01/PSTs"` per il nome della sottocartella nel passaggio precedente, ma utilizzato `fileserver01/psts` nel `FilePath` parametro nel file CSV, l'importazione del file PST avrà esito negativo. Assicurarsi di utilizzare lo stesso caso in entrambi i casi.           |(lasciare vuoto)  <br/> Oppure  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |Specifica il nome del file PST che verrà importato per la cassetta postale utente. Il valore per questo parametro viene fatta distinzione tra maiuscole e minuscole.<br/> > [!IMPORTANT]> Caso il nome del file PST nel file CSV deve essere uguale al file PST che è stato caricato per la posizione di archiviazione Azure nel passaggio 2. Ad esempio, se si utilizza `annb.pst` nel `Name` parametro nel file CSV, ma il nome del file PST è `AnnB.pst`, l'importazione di file PST avrà esito negativo. Assicurarsi che il nome del file PST nel file CSV utilizza lo stesso caso come file PST effettivo.           | `annb.pst` <br/> |
    | `Mailbox` <br/> |Specifica l'indirizzo di posta elettronica della cassetta postale che verrà importato il file PST. Si noti che non è possibile specificare una cartella pubblica perché il servizio di importazione file PST non supporta l'importazione dei file PST alle cartelle pubbliche.<br/> Per importare un file PST di una cassetta postale inattiva, è necessario specificare il GUID della cassetta postale per questo parametro. Per ottenere il GUID, eseguire il seguente comando PowerShell in Exchange Online: "Get-Mailbox <identity of inactive mailbox> - InactiveMailboxOnly | Guid FL` <br/> > [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox<identity of active mailbox> | Guid FL`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> - SoftDeletedMailbox | Guid FL'.           | `annb@contoso.onmicrosoft.com` <br/> Oppure  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Specifica se importare o meno il file PST nella cassetta postale di archiviazione dell'utente. Esistono due opzioni:<br/> **FALSE** Consente di importare il file PST alla cassetta postale principale dell'utente.  <br/> **TRUE** Consente di importare il file PST alla cassetta postale di archivio dell'utente. Si presuppone che la [cassetta postale di archivio dell'utente è abilitata](enable-archive-mailboxes.md). Se questo parametro è impostato su `TRUE` e cassetta postale di archivio dell'utente non è abilitata, l'importazione per l'utente avrà esito negativo. Si noti che se un'importazione non riesce per un utente (perché non è abilitato l'archivio e questa proprietà è impostata su `TRUE`), gli altri utenti nel processo di importazione non subiranno modifiche.<br/>  Se si omette questo parametro, viene importato il file PST alla cassetta postale principale dell'utente.  <br/> **Nota:** Per importare un file PST di una cassetta postale di archiviazione basate su cloud per un utente la cui cassetta postale principale è locale, è sufficiente specificare `TRUE` per questo parametro e specificare l'indirizzo di posta elettronica per la cassetta postale locale dell'utente per il `Mailbox` parametro.  <br/> | `FALSE` <br/> Oppure  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Specifica la cartella delle cassette postali che viene importato il file PST.  <br/>  Se si omette questo parametro, i file PST verranno importate in una nuova cartella denominata **Imported** posizionato a livello radice della cassetta postale (allo stesso livello di cartella Posta in arrivo e le altre cartelle predefinite delle cassette postali).  <br/>  Se si specifica `/`, gli elementi del file PST verranno importati direttamente nella cartella Posta in arrivo dell'utente.  <br/>  Se si specifica `/<foldername>`, gli elementi del file PST verranno importati in una cartella denominata * \<foldername\> * . Ad esempio, se si utilizza `/ImportedPst`, gli elementi potrebbero essere importati in una cartella denominata **ImportedPst**. Questa cartella si trovano nella cassetta postale dell'utente allo stesso livello nella cartella Posta in arrivo.<br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `/` <br/> Oppure  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Questo parametro opzionale specifica un valore numerico per la tabella codici da utilizzare per l'importazione di file PST in formato ANSI. Questo parametro viene utilizzato per l'importazione di file PST di organizzazioni cinese e giapponese, coreano, dal momento che queste lingue utilizzano in genere un set di caratteri a byte doppio (DBCS) per la codifica dei caratteri. Se questo parametro non viene utilizzato per importare i file PST per le lingue che utilizzano DBCS per i nomi delle cartelle delle cassette postali, i nomi delle cartelle sono spesso incomprensibile dopo l'importazione.<br/> Per un elenco di valori supportati da utilizzare per questo parametro, vedere [Identificatori di pagina di codice](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> > [!NOTE]> Come già indicato, questo è un parametro facoltativo e non è necessario includere nel file CSV. Oppure includerlo e lasciare il valore vuoto per una o più righe.           |(lasciare vuoto)  <br/> Oppure  <br/>  `932`(ovvero l'identificatore della tabella codici per ANSI/OEM giapponese)  <br/> |
    | `SPFileContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPManifestContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPSiteUrl` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>Passaggio 4: creare un processo di Importazione PST in Office 365

Il passaggio successivo consiste nel creare il processo di importazione di file PST nel servizio di importazione in Office 365. Come indicato in precedenza, si invierà il file di mapping di importazione di file PST creato nel passaggio 3. Dopo aver creato il nuovo processo, il servizio di importazione utilizzerà le informazioni nel file di mapping per importare i file PST alla cassetta postale utente specificato dopo che i file PST vengono copiati dal disco rigido per l'area di archiviazione Azure e si crea e avvia il processo di importazione.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance di dati** e quindi fare clic su **Importa**.
    
3. Nella pagina **importazione** fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
    > [!NOTE]
    > Come affermato in precedenza, è necessario disporre delle autorizzazioni appropriate per accedere alla pagina di **importazione** per la protezione &amp; centro conformità. 
  
4. Digitare un nome per il processo di importazione file PST e quindi fare clic su **Avanti**. Utilizzare le lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella pagina **scegliere il tipo di processo di importazione** fare clic su **unità disco rigido Shipping su uno dei nostri posizioni fisiche** e quindi fare clic su **Avanti**.
    
    ![Fare clic su unità disco rigido Shipping su uno dei nostri posizioni fisiche per creare un'unità di processo di importazione per la distribuzione](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Nel passaggio 6, fare clic sulle caselle di controllo **si aver predisposto i dischi rigidi e disporre dell'accesso ai file di journal unità necessarie** e **dispongo di accesso al file di mapping** e quindi fare clic su **Avanti**.
    
    ![Fare clic su due caselle di controllo nel passaggio 6](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. Nella pagina **Selezionare il file di unità** , fare clic su **Seleziona file dell'unità**e quindi passare nella stessa cartella in cui si trova lo strumento WAImportExport.exe. In questa cartella è stato copiato il file di journal creata nel passaggio 2.
    
    ![Fare clic su unità selezionare file per inviare il file di registro creato durante l'esecuzione dello strumento WAImportExport.exe](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. Selezionare il file di registro; ad esempio `PSTHDD1.jrn`.
    
    > [!TIP]
    > Durante l'esecuzione dello strumento WAImportExport.exe nel passaggio 2, il nome del file del journal è stato specificato per il `/j:` parametro. 
  
9. Dopo che il nome del file unità visualizzata nella casella **nome file di unità**, fare clic su **convalida** per verificare che il file di unità di errori. 
    
    ![Fare clic su convalida per convalidare il file di unità in cui è stata selezionata](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    Il file unità deve essere convalidato per creare un processo di importazione di file PST. Nota il nome del file viene impostato su verde dopo la convalida. In caso contrario, fare clic sul collegamento **Visualizza registro** . Viene aperto un rapporto di errore di convalida, con un messaggio di errore con le informazioni sui motivi per cui il file non è riuscita. 
    
    > [!NOTE]
    > È necessario aggiungere e convalidare un file di registrazioni per ogni disco rigido forniti a Microsoft. 
  
10. Dopo aver aggiunto e la convalida di un file del journal per ogni disco rigido in cui verranno forniti a Microsoft, fare clic su **Avanti**.
    
11. Fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **selezionare file di mapping** per inviare il file di mapping di importazione di file PST creato nel passaggio 3. 
    
    ![Fare clic su file di mapping selezionare per inviare il file CSV creato per il processo di importazione](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. Dopo il nome del file CSV file viene visualizzato in **nome file di Mapping**, fare clic su **convalida** per verificare che il file CSV per gli errori. 
    
    ![Fare clic su convalida per controllare il file CSV per gli errori](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Il file CSV deve essere convalidato per creare un processo di importazione di file PST. Nota il nome del file viene impostato su verde dopo la convalida. In caso contrario, fare clic sul collegamento **Visualizza registro** . Viene aperto un rapporto di errore di convalida, con un messaggio di errore per ogni riga nel file che non è riuscita. 
    
13. Dopo che il file di mapping PST è stato convalidato, fare clic su **Avanti**.
    
14. Nella pagina **specificare informazioni sul contatti** , digitare le informazioni di contatto nelle caselle applicabile. 
    
    Si noti che viene visualizzato l'indirizzo della posizione di Microsoft verranno inclusi i dischi rigidi per. Questo indirizzo viene generato automaticamente in base alla località centro dati di Office 365. Copiare l'indirizzo di un file o richiedere cattura di schermata.
    
15. Leggere il documento termini e alle condizioni, selezionare la casella di controllo e quindi fare clic su **Salva** per inviare il processo di importazione. 
    
    Durante il processo di importazione sia stato creato, viene visualizzata una pagina di stato che illustra i passaggi successivi dell'unità di processo di distribuzione dei.
    
16. Nella pagina **importazione** fare clic su ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) **l'aggiornamento** a visualizzata l'unità nuova processo di importazione per la distribuzione nell'elenco dei processi di importazione. Si noti che lo stato è impostato su **in attesa per numero di registrazione**. È anche possibile scegliere il processo di importazione per visualizzare la pagina stato comparsa, contenente informazioni più dettagliate sul processo di importazione.
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>Passaggio 5: inviare l'unità disco rigido a Microsoft

Il passaggio successivo consiste nel inclusi il disco rigido da Microsoft e quindi specificare il numero di registrazione per la spedizione e restituire informazioni sulla spedizione per il processo di distribuzione di unità. Unità ricevuto da Microsoft, richiede tra 7-10 giorni lavorativi per i dati di personale del centro per caricare i file PST all'area di archiviazione Azure per la propria organizzazione.
  
> [!NOTE]
> Se non si specifica il numero di verifica e informazioni di spedizione reso entro 14 giorni di creazione del processo di importazione, il processo di importazione verrà scaduto. In questo caso, è necessario creare una nuova unità processo di importazione per la distribuzione (vedere [passaggio 4: creare un processo di importazione di file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) e inviare nuovamente il file di unità e il file di mapping di importazione file PST. 
  
### <a name="ship-the-hard-drive"></a>Spedire l'unità disco rigido

Tenere presente quanto segue in fase di spedizione delle unità a Microsoft:
  
- Non inclusi scheda SATA-USB. è necessario fornire il disco rigido.
    
- Assicurarsi che l'unità sia imballata correttamente, ad esempio, utilizzare una busta antistatica o pluriball.
    
- Utilizzare un corriere di propria scelta per spedire l'unità disco rigido a Microsoft.
    
- Distribuire il disco rigido per l'indirizzo della posizione di Microsoft che è stata visualizzata quando il processo di importazione è stato creato nel passaggio 4. È necessario includere "Office 365 importazione servizio" nella casella Indirizzo di spedizione.
    
- Dopo aver inviato l'unità disco rigido, verificare di aver scritto il nome del corriere e il numero di tracciabilità. Tali informazioni verranno fornite nel prossimo passaggio.
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>Immettere il numero di tracciabilità e altre informazioni sulla spedizione

Dopo aver inviato l'unità disco rigido a Microsoft, completare la procedura seguente nella pagina del servizio di importazione.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro fare clic su **governance di dati** e quindi fare clic su **Importa**.
    
3. Nella pagina **Importa** clic sul processo per la spedizione di unità in cui si desidera immettere il numero di verifica per. 
    
4. Nella pagina stato tendina fare clic su **Immettere il numero di rilevamento**.
    
5. Fornire le seguenti informazioni sulla spedizione:
    
1. **Gestore di recapito** Digitare il nome del gestore telefonico di consegna utilizzato per fornire il disco rigido a Microsoft. 
    
2. **Numero di registrazione** Digitare il numero di verifica per la spedizione di disco rigido. 
    
3. **Account di questo mittente** Digitare il numero di conto dell'organizzazione per portante elencate in **restituire gestore di telefonia**. Microsoft utilizzerà (e ricaricare) questo account per inviare il disco rigido all'utente. Si noti che le organizzazioni in USA ed Europa, deve avere un account con FedEx. Le organizzazioni in Asia e il resto del mondo, devono disporre di un account con DHL.
    
6. Fare clic su **Salva** per salvare queste informazioni per il processo di importazione. 
    
    Nella pagina **importazione** fare clic su ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) **Aggiorna** per aggiornare le informazioni per l'unità di processo di importazione per la distribuzione. Si noti che lo stato sia impostato su **unità in transito**.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Passaggio 6: Filtrare i dati e avviare il processo di importazione di file PST

Disco rigido ricevuto da Microsoft, lo stato del processo di importazione nella pagina **importazione** verrà modificato per **unità ricevuti**. Personale del centro dati utilizzerà le informazioni nel file di registrazioni per caricare i file PST all'area di archiviazione Azure per la propria organizzazione. A questo punto, lo stato verrà modificato per **l'importazione in corso**. Come descritto in precedenza, richiede tra 7 a 10 giorni lavorativi dopo aver ricevuto il disco rigido per caricare i file PST.
  
File PST vengono caricati in Azure, lo stato è cambiato analisi **in corso**. Indica che Office 365 è analisi dei dati in file PST (in modo sicuro e protetto) per identificare la validità degli elementi e i diversi tipi di messaggi inclusi nei file PST. Una volta completata l'analisi ed sono possibile importare i dati, lo stato del processo di importazione viene modificato per **Analisi completata**. A questo punto è possibile importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando i filtri che consentono di controllare quali dati vengono importati.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro fare clic su **governance dati** > **importazione**.
    
3. Nella pagina **importazione** fare clic su **Pronto essere importato a Office 365** per il processo di importazione creata nel passaggio 4. 
    
    ![Fare clic su pronto per importare accanto al processo di importazione che è stato creato a Office 365](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Volo pagina viene visualizzato con informazioni sui file PST e altre informazioni sul processo di importazione.
    
4. Fare clic su **Importa a Office 365**.
    
5. Verrà visualizzata la pagina di **filtrare i dati** . Contiene informazioni dati risultanti dall'analisi eseguita in file PST da Office 365, incluse le informazioni sulla validità dei dati. A questo punto è possibile filtrare i dati verranno importati o importano tutti i dati di esempio è. 
    
    ![È possibile tagliare i dati in file PST o importare tutto](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. Eseguire una delle operazioni seguenti:
    
    r. per tagliare i dati da importare, fare clic su **Sì, desidero filtrarla prima dell'importazione**.
    
    Per istruzioni dettagliate sul filtro dei dati in file PST e quindi avviare il processo di importazione, vedere [filtro di dati durante l'importazione di file PST a Office 365](filter-data-when-importing-pst-files.md).
    
    Oppure
    
    b. per importare tutti i dati in file PST, fare clic su **No, desidera importare tutti gli elementi** e fare clic su **Avanti**.
    
7. Se si è scelto di importare tutti i dati, fare clic su **Importa dati** per avviare il processo di importazione. 
    
    Nella pagina **importazione** viene visualizzato lo stato del processo di importazione. Fare clic su ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) **Aggiorna** per aggiornare le informazioni sullo stato viene visualizzate nella colonna **stato** . Fare clic sul processo di importazione per visualizzare la pagina stato comparsa, che visualizza le informazioni di stato per ogni file PST da importare. Durante l'importazione è stato completato e importazione di file PST alle cassette postali utente, verrà modificato lo stato su **completata**.

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Visualizzare un elenco dei file PST caricato in Office 365

È possibile installare e utilizzare Microsoft Azure archiviazione Explorer (che è uno strumento gratuito, open source) per visualizzare l'elenco dei file PST che è stiamo caricati (dal personale del centro dati Microsoft) per l'area di archiviazione Azure per la propria organizzazione. È possibile eseguire questa operazione per verificare che i file PST di dischi rigidi che è stata inviata a Microsoft sono stati caricati correttamente l'area di archiviazione Azure.
  
Microsoft Azure archiviazione Explorer è in anteprima.
  
 **Importante:** È possibile utilizzare le soluzioni di archiviazione Azure per caricare o modificare il file PST. L'unico metodo supportato per l'importazione di file PST in Office 365 consiste nell'utilizzare AzCopy. Inoltre, è possibile eliminare i file PST che è stato caricato in Azure blob. Se si tenta di eliminare un file PST, viene visualizzato un errore relativo a non disporre delle autorizzazioni necessarie. Si noti che tutti i file PST vengono automaticamente eliminati dall'area di archiviazione Azure. Se sono presenti alcun processo di importazione in corso, quindi tutti i file PST di * * ingestiondata * * contenitore vengono eliminati 30 giorni dopo il processo di importazione più recente è stato creato. 
  
Per installare le soluzioni di archiviazione Azure e connettersi all'area di archiviazione Azure:
  
1. Eseguire la procedura seguente per ottenere l'URL condivisi Access firma (SAS) per l'organizzazione. Questo URL è una combinazione dell'URL di rete per il percorso di archiviazione Azure nel cloud Microsoft per l'organizzazione e un tasto SAS. Questa chiave viene fornita con le autorizzazioni necessarie per accedere al percorso di archiviazione Azure dell'organizzazione.
    
1. Accedere a [https://protection.office.com/](https://protection.office.com/) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance dati** \> **importazione**.
    
3. Nella pagina **importazione** fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
4. Nell'Importazione guidata processo, digitare un nome per il processo di importazione file PST e quindi fare clic su **Avanti**. Utilizzare le lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella pagina **scegliere il tipo di processo di importazione** fare clic su **Carica i dati** e quindi fare clic su **Avanti**.
    
6. Nel passaggio 2, fare clic su **Mostra il caricamento di rete SAS URL**.
    
7. Dopo che viene visualizzato l'URL, copiarlo e salvarlo in un file. Assicurarsi di copiare l'intero URL.
    
    > [!IMPORTANT]
    > È necessario adottare alcune precauzioni per proteggere l'URL SAS. Può essere utilizzato da tutti gli utenti di accedere all'area di archiviazione Azure per la propria organizzazione. 
  
8. Fare clic su **Annulla** per chiudere la procedura guidata processo di importazione. 
    
2. Scaricare e installare lo [strumento di Microsoft Azure archiviazione Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
3. Avviare Microsoft Azure archiviazione Explorer, **Gli account di archiviazione** fare clic nel riquadro sinistro e fare clic su **Connetti per archiviazione Azure**.
    
    ![Il pulsante destro gli account di archiviazione e quindi fare clic su Connetti per archiviazione Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. Fare clic su **utilizza una stringa di connessione o URI firma (SAS) accesso condiviso** e fare clic su **Avanti**.
    
5. Fare clic su **utilizza un URI SAS**, incollare l'URL SAS fornito nel passaggio 1 in nella casella in **URI**e quindi fare clic su **Avanti**.
    
6. Nella pagina **connessione riepilogo** esaminare le informazioni di connessione e quindi fare clic su **Connetti**.
    
    Viene aperto il contenitore **ingestiondata** ; contiene i file PST dal disco rigido. In **Account di archiviazione** si trova il contenitore **ingestiondata** \> **(SAS-Attached servizi)** \> **Contenitori Blob**.
    
    ![Esplora archivi di Azure mostra un elenco di file con estensione PST caricati](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. Una volta terminato di utilizzare Microsoft Azure archiviazione Explorer, destro **ingestiondata**e quindi fare clic su **Scollega** di disconnettersi dall'area di archiviazione Azure. In caso contrario, viene visualizzato un errore al successivo che si cerca di collegare. 
    
    ![Fare clic con il pulsante destro del mouse sull’inserimento e su Disconnetti per disconnettersi dall'area di archiviazione Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a>Suggerimenti per la risoluzione dei problemi
<a name="troubleshootingtips"> </a>

- **Cosa succede se il processo di importazione non riesce a causa di errori nel file di mapping PST importazione CSV?** Se un processo di importazione non riesce a causa di errori nel file di mapping, non è necessario fornire nuovamente il disco rigido a Microsoft per creare un nuovo processo di importazione. Ciò avviene perché i file PST dal disco rigido in cui è stata inviata per il processo di importazione shipping unità già caricati all'area di archiviazione Azure per la propria organizzazione. In questo caso, è sufficiente correggere gli errori nel file di mapping PST importazione CSV e quindi creare un nuovo processo di importazione "caricamento di rete" e inviare il file di mapping CSV revisionato. Per creare e avviare un nuovo processo di importazione per il caricamento di rete, vedere [passaggio 5: creare un processo di importazione di file PST in Office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) e [passaggio 6: filtrare i dati e avviare il processo di importazione di file PST](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) nell'argomento "Caricamento di rete utilizzare per importare i file PST a Office 365". 
    
    > [!NOTE]
    > Per risolvere i file di mapping PST importazione CSV, utilizzare lo strumento di [Soluzioni di archiviazione Azure](#view-a-list-of-the-pst-files-uploaded-to-office-365) per visualizzare la struttura di cartelle nel contenitore **ingestiondata** per i file PST dal disco rigido che sono stati caricati nell'area di archiviazione Azure. Errori dei file di mapping sono in genere causati da un valore non corretto nel parametro FilePath. Questo parametro consente di specificare il percorso di un file PST nell'area di archiviazione Azure. Vedere la descrizione del parametro FilePath nella tabella nel [passaggio 3](#step-3-create-the-pst-import-mapping-file). Come indicato in precedenza è stato specificato il percorso dei file PST nell'area di archiviazione Azure per la `/dstdir:` parametro durante l'esecuzione dello strumento WAImportExport.exe nel [passaggio 2](#step-2-copy-the-pst-files-to-the-hard-drive). 
  

  
## <a name="more-information"></a>Ulteriori informazioni

- Unità shipping è un modo efficace per importare grandi quantità di archiviare i dati di messaggistica per Office 365 per sfruttare le funzionalità di conformità disponibili nell'organizzazione. Dopo l'importazione di dati di archiviazione per cassette postali degli utenti, è possibile:
    
  - Abilitare [l'espansione automatica di archiviazione](enable-unlimited-archiving.md) per fornire agli utenti di spazio di archiviazione delle cassette postali aggiuntive per i dati e [cassette postali di archiviazione](enable-archive-mailboxes.md) . 
    
  - Posizionare le cassette postali di [Conservazione per controversia legale](https://go.microsoft.com/fwlink/?linkid=856286) di conservazione dei dati. 
    
  - Utilizzare [gli strumenti di eDiscovery](search-for-content.md) di Microsoft per cercare i dati. 
    
  - Applicare i [criteri di conservazione di Office 365](retention-policies.md) per controllare quanto tempo i dati verranno mantenuti e l'azione da eseguire dopo la scadenza del periodo di conservazione. 
    
  - Ricerca il [Registro di controllo di Office 365](search-the-audit-log-in-security-and-compliance.md) per gli eventi relativi a tali dati. 
    
  - Importare dati [delle cassette postali inattive](create-and-manage-inactive-mailboxes.md) per archiviare i dati per motivi di conformità. 
    
  - Proteggere l'organizzazione da [perdita di dati](data-loss-prevention-policies.md) di informazioni riservate. 
    
- Di seguito viene riportato un esempio di una chiave dell'account di archiviazione protetta e una chiave di crittografia BitLocker. In questo esempio è riportata la sintassi per il comando WAImportExport.exe da eseguire per copiare i file PST in un'unità disco rigido. Adottare le dovute precauzioni per proteggere tali file nello stesso in modo in cui vengono protette password o altre informazioni di sicurezza.
    

    ```
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```
   
- Come indicato in precedenza, il servizio Office 365 importazione consente di attivare il mantenimento impostazione (per un periodo indefinito) dopo l'importazione dei file PST in una cassetta postale. Ciò significa che la proprietà *RentionHoldEnabled* è impostata su `True` in modo che non verrà elaborato il criterio di conservazione assegnato alla cassetta postale. In questo modo il tempo di proprietario della cassetta postale per gestire i messaggi appena importato impedendo un'eliminazione o criteri di archiviazione dall'eliminazione o l'archiviazione dei messaggi meno recenti. Ecco alcuni passaggi che consentono di gestire il mantenimento: 
    
  - Dopo un determinato periodo di tempo, è possibile disattivare il mantenimento eseguendo il `Set-Mailbox -RetentionHoldEnabled $false` comando. Per ulteriori informazioni, vedere [archiviazione sul posto una cassetta postale di conservazione](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - È possibile configurare il mantenimento in modo che è disattivata per alcuni data in futuro. A tale scopo, che esegue il `Set-Mailbox -EndDateForRetentionHold <date>` comando. Ad esempio, supponendo che la data corrente è il 1 ° luglio 2016 e si desidera che il mantenimento disattivata in 30 giorni, eseguire il comando seguente: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In questo scenario, è opportuno lasciare la proprietà *RentionHoldEnabled* impostata su *True* . Per ulteriori informazioni, vedere [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - È possibile modificare le impostazioni per il criterio di conservazione viene assegnato alla cassetta postale in modo che gli elementi meno recenti che sono stati importati non essere immediatamente eliminati o spostati alla cassetta postale di archivio dell'utente. Ad esempio, è possibile allungare il periodo di conservazione per un criterio di eliminazione o un archivio viene assegnato alla cassetta postale. In questo scenario, potrebbe consente di disattivare il mantenimento per la cassetta postale dopo che sono state modificate le impostazioni dei criteri di conservazione. Per ulteriori informazioni, vedere [impostazione di un criterio di archiviazione e l'eliminazione delle cassette postali nell'organizzazione Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    

  

