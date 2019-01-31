---
title: Utilizzare il caricamento di rete per importare i file PST organizzazione a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: "Per gli amministratori: imparare a utilizzare il caricamento di rete per l'importazione in blocco più file PST alle cassette postali utente in Office 365."
ms.openlocfilehash: 81c799a8c820e9d9287f4792fe463d6a99b90e36
ms.sourcegitcommit: 25f1028643d8a20d17306e8b09cafea46eaf7a58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2019
ms.locfileid: "29666156"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>Utilizzare il caricamento di rete per importare i file PST organizzazione a Office 365

> [!NOTE]
> In questo articolo sia per gli amministratori. Si sta tentando di importare i file PST alla propria cassetta postale? Vedere [posta elettronica di importazione, contatti e calendario da un file pst di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
Di seguito sono riportate le procedure dettagliate è necessarie utilizzare il caricamento di rete per l'importazione in blocco più file PST alle cassette postali di Office 365. Per le domande frequenti sull'utilizzo di caricamento di rete per l'importazione in blocco dei file PST cassette postali di Office 365, vedere [domande frequenti per l'utilizzo di caricamento di rete per importare i file PST](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).
  
[Passaggio 1: Copiare l'URL SAS e installare AzCopy Azure](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[Passaggio 2: Caricare i file PST in Office 365](#step-2-upload-your-pst-files-to-office-365)

[(Facoltativo) Passaggio 3: Visualizzare un elenco dei file PST caricato in Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Passaggio 4: Creare il file di mapping di importazione di file PST](#step-4-create-the-pst-import-mapping-file)

[Passaggio 5: creare un processo di Importazione PST in Office 365](#step-5-create-a-pst-import-job-in-office-365)

[Passaggio 6: Filtrare i dati e avviare il processo di importazione di file PST](#step-6-filter-data-and-start-the-pst-import-job)

Si noti che è necessario eseguire il passaggio 1 solo una volta per importare i file PST di cassette postali di Office 365. Dopo aver eseguito queste operazioni, eseguire il passaggio 2 a 6 passaggio ogni volta che si desidera caricare e importare un batch di file PST.

## <a name="before-you-begin"></a>Prima di iniziare
  
- È necessario essere assegnato il ruolo di importare l'esportazione delle cassette postali di Exchange Online per importare i file PST alle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli di Exchange Online. È possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione. Oppure creare un nuovo gruppo di ruoli, assegnare il ruolo cassette postali importazione/esportazione e quindi aggiungere l'utente come membro. Per ulteriori informazioni, vedere "Aggiungere un ruolo da un gruppo di ruoli" o "Creare un gruppo di ruoli" sezioni in [gruppi di ruoli di gestione](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Inoltre, per creare Importa i processi in Office 365 Security &amp; centro conformità, uno dei seguenti devono essere vere:
    
  - È necessario assegnare il ruolo destinatari di posta elettronica di Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione dei destinatari.
    
    Oppure
    
  - È necessario essere un amministratore globale dell'organizzazione Office 365.
    
  > [!TIP]
    > È consigliabile creare un nuovo gruppo di ruoli in Exchange Online che è progettata in modo specifico per l'importazione di file PST in Office 365. Livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importare l'esportazione delle cassette postali e destinatari di posta elettronica al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
- L'unico metodo supportato per l'importazione di file PST in Office 365 è utilizzare lo strumento di Azure AzCopy, come descritto in questo argomento. È possibile utilizzare le soluzioni di archiviazione Azure per caricare i file PST direttamente all'area di archiviazione Azure.
    
- È necessario archiviare i file PST che si desidera importare in Office 365 in un server di file o una cartella condivisa all'interno dell'organizzazione. Nel passaggio 2 si sarà eseguire lo strumento AzCopy Azure che verrà caricato i file PST che vengono memorizzati nel server di file o cartella a Office 365 condivisa.
    
- Questa procedura è necessario copiare e salvare una copia di un URL che contiene un tasto. Tali informazioni verranno utilizzate nel passaggio 2 per caricare i file PST e nel passaggio 3 Se si desidera visualizzare un elenco dei file PST caricato in Office 365. È necessario adottare alcune precauzioni per proteggere questo URL come si proteggono password o altre informazioni relative alla sicurezza. È potrebbe ad esempio salvare un documento di Microsoft Word protetti da password o su un'unità USB crittografata. Vedere che la sezione [informazioni](#more-information) per un esempio di questo insieme URL e la chiave. 
    
- È possibile importare file PST in una cassetta postale inattiva in Office 365. A tale scopo, che specifica il GUID della cassetta postale inattiva nel `Mailbox` parametro nel file di mapping di importazione di file PST. Nella scheda **istruzioni** in questo argomento per informazioni, vedere il passaggio 4. 
    
- In una distribuzione ibrida di Exchange, è possibile importare file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è locale. A tale scopo, eseguire le operazioni seguenti nel file di mapping di importazione di file PST:
    
  - Specificare l'indirizzo di posta elettronica della cassetta postale locale dell'utente nel `Mailbox` parametro. 
    
  - Specificare il valore **TRUE** nel `IsArchive` parametro. 
    
    Per ulteriori informazioni, vedere [il passaggio 4](#step-4-create-the-pst-import-mapping-file) . 
    
- Dopo l'importano dei file PST in una cassetta postale Office 365, il mantenimento di impostazione per la cassetta postale è attivata per un periodo indefinito. Ciò significa che il criterio di conservazione assegnato alla cassetta postale non verrà elaborato fino a quando non si consente di disattivare il mantenimento o si imposta una data per disattivare il blocco. Perché questa operazione è necessaria Se i vecchi messaggi importati in una cassetta postale, potrebbe essere eliminati definitivamente (cancellati) perché il periodo di conservazione è scaduto in base alle impostazioni di conservazione configurate per la cassetta postale. Per ottenere l'ora di proprietario della cassetta postale per gestire i messaggi appena importato o fornire il tempo necessario per modificare le impostazioni di conservazione per la cassetta postale, effettuare la cassetta postale in attesa di conservazione. Vedere scheda **ulteriori informazioni** in questo argomento per suggerimenti sulla gestione di mantenimento. 
    
- Per impostazione predefinita, la dimensione massima dei messaggi può ricevere una cassetta postale di Office 365 è 35 MB. Ciò avviene perché il valore predefinito per la proprietà *MaxReceiveSize* per una cassetta postale è impostato su 35 MB. Tuttavia, il limite per la massima dei messaggi di ricezione dimensioni in Office 365 è 150 MB. Quindi, se si importa un file PST contenente un elemento di dimensioni superiore a 35 MB, il servizio Office 365 importare è modificherà automaticamente il valore della proprietà *MaxReceiveSize* nella cassetta postale di destinazione a 150 MB. In questo modo i messaggi fino a 150 MB da importare per cassette postali degli utenti. 
    
    > [!TIP]
    > Per identificare il messaggio venga visualizzato dimensioni di una cassetta postale, è possibile eseguire questo comando in Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`. 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>Passaggio 1: Copiare l'URL SAS e installare AzCopy Azure

Il primo passaggio è necessario scaricare e installare lo strumento AzCopy Azure, che rappresenta lo strumento verrà eseguito nel passaggio 2 per il caricamento di file PST a Office 365. È inoltre sarà copiare l'URL SAS per l'organizzazione. Questo URL è una combinazione dell'URL di rete per il percorso di archiviazione Azure nel cloud Microsoft per l'organizzazione e una chiave di firma condivise di Access (SAS). Questa chiave viene fornita con le autorizzazioni necessarie per caricare i file PST la posizione di archiviazione Azure. È necessario adottare alcune precauzioni per proteggere l'URL SAS. È univoco nell'organizzazione e verranno utilizzata nel passaggio 2.

> [!IMPORTANT]
> Per importare i file PST modalità di caricamento di file, utilizzare la rete, è consigliabile utilizzare la versione di Azure AzCopy che può essere scaricato nel passaggio 6b nella procedura seguente.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance dati** \> **importazione**.
    
    > [!NOTE]
    > È necessario disporre delle autorizzazioni appropriate per accedere alla pagina di **importazione** per la protezione &amp; centro conformità. Vedere la sezione **operazioni preliminari** per ulteriori informazioni. 
    
3. Nella pagina **importazione** fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
    Viene visualizzata la procedura guidata processo di importazione.
    
4. Digitare un nome per il processo di importazione file PST e quindi fare clic su **Avanti**. Utilizzare le lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella **si desidera caricare o inclusi dati?** di pagina, fare clic su **Carica i dati** e quindi fare clic su **Avanti**.
    
    ![Fare clic su Carica processo di importazione dei dati per creare un caricamento di rete](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Nella pagina **Importa dati** eseguire le due operazioni seguenti: 
    
    ![Copiare l'URL SAS e scaricare lo strumento AzCopy Azure nella pagina Importa dati](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    r. nel passaggio 2, fare clic su **Mostra il caricamento di rete SAS URL**. Dopo che l'URL SAS viene visualizzato, fare clic su **Copia negli Appunti** e incollarlo e salvarla in un file in modo è possibile accedervi più avanti.
    
    b. nel passaggio 3, fare clic su **Download AzCopy Azure** per scaricare e installare lo strumento AzCopy Azure. Nella finestra popup, fare clic su **Esegui** per installare AzCopy. 
    
> [!NOTE]
> È possibile lasciare la pagina **Importa dati** aperta (nel caso in cui si desidera copiare l'URL SAS nuovamente) oppure fare clic su **Annulla** per chiudere la finestra. 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>Passaggio 2: Caricare i file PST in Office 365

A questo punto si è pronti per utilizzare lo strumento AzCopy.exe per caricare i file PST in Office 365. Questo strumento consente di caricare e li archivia in un percorso di archiviazione Azure nel cloud Microsoft. Come indicato in precedenza, il percorso di archiviazione Azure che il caricamento dei file PST di cui si trova nello stesso datacenter Microsoft internazionali in cui si trova l'organizzazione Office 365. Per completare questo passaggio, al file PST devono trovarsi in una condivisione file o un file server nella propria organizzazione. Questo è noto come directory di origine nella procedura seguente. Ogni volta che si esegue lo strumento AzCopy, è possibile specificare una directory di origine diversa. 
  
1. Aprire un prompt dei comandi nel computer locale.
    
2. Passare alla directory in cui è installato lo strumento AzCopy.exe nel passaggio 1. Se è stato installato lo strumento nel percorso predefinito, vedere `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.
    
3. Eseguire il comando seguente per caricare i file PST in Office 365.

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    Nella tabella seguente vengono descritti i parametri e i relativi valori necessari. Si noti che le informazioni ottenute nel passaggio precedente viene utilizzate nei valori di questi parametri.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Specifica la directory di origine all'interno dell'organizzazione che contiene i file PST che verranno caricati in Office 365.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Specifica l'URL SAS fornito nel passaggio 1.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> **Suggerimento:** (Facoltativo) È possibile specificare una sottocartella nella posizione di archiviazione Azure per caricare i file PST. Ottenere questo risultato mediante l'aggiunta di un percorso sottocartella (dopo "ingestiondata") nell'URL SAS. Nel primo esempio non consente di specificare una sottocartella. Ciò significa che viene caricato il file pst nella directory principale (denominato *ingestiondata* ) della posizione di archiviazione Azure. Nel secondo esempio carica i file PST in una sottocartella (denominato *PSTFiles* ) nella radice della posizione di archiviazione Azure.<br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> Oppure  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Produce messaggi di stato dettagliati in un file di registro. Per impostazione predefinita, il file di registro dettagliato è denominato AzCopyVerbose.log in %LocalAppData%\Microsoft\Azure\AzCopy. Se si specifica il percorso di un file esistente per questa opzione, il registro dettagliato verrà aggiunto a tale file.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Questo parametro facoltativo specifica la modalità ricorsiva in modo che lo strumento AzCopy verrà copiato i file di file pst che si trovano nelle sottocartelle nella directory di origine specificato dal `/Source:` parametro.  <br/> **Nota:** Se si include questo parametro, i file PST in sottocartelle avrà un percorso di file diverso nella posizione di archiviazione Azure dopo essere state caricate. È necessario specificare il percorso esatto nel file CSV creato nel passaggio 4.<br/> | `/S` <br/> |
    | `/Y` <br/> |Questo parametro obbligatorio consente l'utilizzo dei token SAS in sola lettura quando si carica i file PST nella posizione di archiviazione Azure. L'URL SAS ottenuto nel passaggio 1 (e specificato in `/Dest:` parametro) è un URL di SAS in sola lettura, per questo motivo, è necessario includere questo commutatore. Si noti che un URL SAS in sola lettura non sarà possibile utilizzando le soluzioni di archiviazione Azure per visualizzare un elenco dei file PST caricati nella posizione di archiviazione Azure.<br/> | `/Y` <br/> |
   
Di seguito è riportato un esempio di sintassi dello strumento AzCopy.exe nella quale verranno utilizzati i valori effettivi di ogni parametro:
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

Una volta eseguito il comando, i messaggi di stato visualizzati riportano informazioni sull'avanzamento del caricamento dei file PST. Nel messaggio finale viene riportato il numero complessivo di file che sono stati caricati. 

> [!TIP]
> Dopo aver correttamente, eseguire il comando AzCopy.exe e verificare che tutti i parametri siano corretti, Salva una copia della sintassi della riga di comando per lo stesso file (protetto) in cui è stato copiato le informazioni fornito nel passaggio 1. È quindi possibile copiare e incollare il comando nel prompt dei comandi ogni volta che si desidera eseguire lo strumento AzCopy.exe per caricare i file PST in Office 365. L'unico valore potrebbe essere necessario modificare sono quelle per le `/Source:` parametro. Dipende dalle directory di origine in cui si trovano i file PST.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(Facoltativo) Passaggio 3: Visualizzare un elenco dei file PST caricato in Office 365

Come un'operazione facoltativa, è possibile installare e utilizzare Microsoft Azure archiviazione Explorer (che è uno strumento gratuito, open source) per visualizzare l'elenco dei file PST in cui è stato caricato in Azure blob. Esistono due motivi per eseguire questa operazione:
  
- Verificare che i file PST da un file server nella propria organizzazione o la cartella condivisa sono stati caricati correttamente blob Azure.
    
- Verificare il nome del file (e il nome del percorso sottocartella se è stato incluso uno) per ogni file PST caricati blob Azure. Ciò è davvero utile quando si crea il file PST mapping file nel passaggio successivo, poiché non è necessario specificare il percorso di cartella e nome di file per ogni file PST. Verifica tali nomi consente di ridurre i potenziali errori nel file di mapping di file PST.
    
Microsoft Azure archiviazione Explorer è in anteprima.
  
> [!IMPORTANT]
> È possibile utilizzare le soluzioni di archiviazione Azure per caricare o modificare il file PST. L'unico metodo supportato per l'importazione di file PST in Office 365 consiste nell'utilizzare AzCopy. Inoltre, è possibile eliminare i file PST che è stato caricato in Azure blob. Se si tenta di eliminare un file PST, viene visualizzato un errore relativo a non disporre delle autorizzazioni necessarie. Si noti che tutti i file PST vengono automaticamente eliminati dall'area di archiviazione Azure. Se sono presenti alcun processo di importazione in corso, tutti i file PST fare nel contenitore **ingestiondata** non viene eliminato 30 giorni dopo il processo di importazione più recente è stato creato.
  
Per installare le soluzioni di archiviazione Azure e connettersi all'area di archiviazione Azure:
  
1. Scaricare e installare lo [strumento di Microsoft Azure archiviazione Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Avviare Microsoft Azure archiviazione Explorer, **Gli account di archiviazione** fare clic nel riquadro sinistro e fare clic su **Connetti per archiviazione Azure**.
    
    ![Il pulsante destro gli account di archiviazione e quindi fare clic su Connetti per archiviazione Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Fare clic su **utilizza una stringa di connessione o URI firma (SAS) accesso condiviso** e fare clic su **Avanti**.
    
4. Fare clic su **utilizza un URI SAS**, incollare l'URL SAS fornito nel passaggio 1 nella casella **URI**e quindi fare clic su **Avanti**.
    
5. Nella pagina **connessione riepilogo** esaminare le informazioni di connessione e quindi fare clic su **Connetti**.
    
    Viene aperto il contenitore **ingestiondata** ; contiene i file PST caricato nel passaggio 2. In **Account di archiviazione** si trova il contenitore **ingestiondata** \> **(SAS-Attached servizi)** \> **Contenitori Blob**. 
    
    ![Esplora archivi di Azure mostra un elenco di file con estensione PST caricati](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Una volta terminato di utilizzare Microsoft Azure archiviazione Explorer, destro **ingestiondata**e quindi fare clic su **Scollega** di disconnettersi dall'area di archiviazione Azure. In caso contrario, viene visualizzato un errore al successivo che si cerca di collegare. 
    
    ![Fare clic con il pulsante destro del mouse sull’inserimento e su Disconnetti per disconnettersi dall'area di archiviazione Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Passaggio 4: Creare il file di mapping di importazione di file PST

Dopo che i file PST sono stati caricati nella posizione di archiviazione Azure per la propria organizzazione Office 365, il passaggio successivo è per creare una virgola separati file CSV (valori) che specifica quali cassette postali degli utenti saranno importati per i file PST. Il file CSV nel passaggio successivo viene verrà inviato quando si crea un processo di importazione di file PST.
  
1. [Scarica una copia del file di mapping di importazione di file PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Aprire o salvare il file CSV nel computer locale. Nell'esempio seguente viene visualizzato un file di mapping di importazione PST completo (aperto nel Blocco note). È molto più facile usare Microsoft Excel per modificare il file CSV.


    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```
    La prima riga o una riga di intestazione, del file CSV sono elencati i parametri che verranno utilizzati dal servizio di importazione di file PST per importare i file PST di cassette postali degli utenti. Ogni nome del parametro è separata da una virgola. Ogni riga sotto la riga di intestazione rappresenta i valori dei parametri per l'importazione di un file PST in una cassetta postale specifica. È necessario una riga per ogni file PST che si desidera importare una cassetta postale utente. Assicurarsi di sostituire i segnaposto i dati nel file di mapping con dati effettivi.

   **Nota:** Effettuare le modifiche nella riga di intestazione, includendo i parametri di SharePoint; essi verranno ignorati durante il processo di importazione di file PST. 

 3. Utilizzare le informazioni della tabella per popolare il file CSV con i dati necessari.


    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Specifica il servizio di Office 365 per i dati verranno importati. Per importare i file PST di cassette postali degli utenti, utilizzare `Exchange`.<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Specifica il percorso della cartella nel percorso di archiviazione Azure caricato i file PST nel passaggio 2.  <br/> Se si non includere un nome della sottocartella facoltativo nell'URL SAS nel `/Dest:` parametro nel passaggio 2, lasciare vuoto questo parametro nel file CSV. Se è stato incluso un nome della sottocartella, specificare in questo parametro (vedere il secondo esempio). Il valore per questo parametro viene fatta distinzione tra maiuscole e minuscole.<br/> In entrambi i casi, *non* includere "ingestiondata" nel valore per il `FilePath` parametro.  <br/><br/> **Importante:** Deve essere analogo a quello utilizzato se è stato incluso un nome della sottocartella facoltativo URL SAS nel caso il nome del percorso file di `/Dest:` parametro nel passaggio 2. Ad esempio, se è stato utilizzato `PSTFiles` per la sottocartella nome nel passaggio 2 e quindi utilizzare `pstfiles` nel `FilePath` parametro nel file CSV, l'importazione del file PST avrà esito negativo. Assicurarsi di utilizzare lo stesso caso in entrambi i casi.<br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Specifica il nome del file PST che verrà importato per la cassetta postale utente. Il valore per questo parametro viene fatta distinzione tra maiuscole e minuscole.<br/> <br/>**Importante:** Caso il nome del file PST nel file CSV deve essere uguale al file PST che è stato caricato per la posizione di archiviazione Azure nel passaggio 2. Ad esempio, se si utilizza `annb.pst` nel `Name` parametro nel file CSV, ma il nome del file PST è `AnnB.pst`, l'importazione di file PST avrà esito negativo. Assicurarsi che il nome del file PST nel file CSV utilizza lo stesso caso come file PST effettivo.<br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Specifica l'indirizzo di posta elettronica della cassetta postale che verrà importato il file PST. Si noti che non è possibile specificare una cartella pubblica perché il servizio di importazione file PST non supporta l'importazione dei file PST alle cartelle pubbliche.<br/> Per importare un file PST di una cassetta postale inattiva, è necessario specificare il GUID della cassetta postale per questo parametro. Per ottenere il GUID, eseguire il seguente comando PowerShell in Exchange Online: "Get-Mailbox <identity of inactive mailbox> - InactiveMailboxOnly | Guid FL` <br/> <br/>**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox<identity of active mailbox> | Guid FL`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox <identity of soft-deleted or inactive mailbox> - SoftDeletedMailbox | Guid FL'.  <br/> | `annb@contoso.onmicrosoft.com` <br/> Oppure  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Specifica se importare o meno il file PST nella cassetta postale di archiviazione dell'utente. Esistono due opzioni:<br/><br/>**FALSE** - consente di importare il file PST alla cassetta postale principale dell'utente.  <br/> **TRUE** - consente di importare il file PST alla cassetta postale di archivio dell'utente. Si presuppone che la [cassetta postale di archivio dell'utente è abilitata](enable-archive-mailboxes.md).<br/><br/>Se questo parametro è impostato su `TRUE` e cassetta postale di archivio dell'utente non è abilitata, l'importazione per l'utente avrà esito negativo. Si noti che se un'importazione non riesce per un utente (perché non è abilitato l'archivio e questa proprietà è impostata su `TRUE`), gli altri utenti nel processo di importazione non subiranno modifiche.<br/>  Se si omette questo parametro, viene importato il file PST alla cassetta postale principale dell'utente.  <br/> <br/>**Nota:** Per importare un file PST di una cassetta postale di archiviazione basate su cloud per un utente la cui cassetta postale principale è locale, è sufficiente specificare `TRUE` per questo parametro e specificare l'indirizzo di posta elettronica per la cassetta postale locale dell'utente per il `Mailbox` parametro.  <br/> | `FALSE` <br/> Oppure  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Specifica la cartella delle cassette postali che viene importato il file PST.  <br/>  Se si omette questo parametro, i file PST verranno importate in una nuova cartella denominata **Imported** posizionato a livello radice della cassetta postale (allo stesso livello di cartella Posta in arrivo e le altre cartelle predefinite delle cassette postali).  <br/>  Se si specifica `/`, gli elementi del file PST verranno importati direttamente nella cartella Posta in arrivo dell'utente.  <br/><br/>  Se si specifica `/<foldername>`, gli elementi del file PST verranno importati in una cartella denominata * \<foldername\> * . Ad esempio, se si utilizza `/ImportedPst`, gli elementi potrebbero essere importati in una cartella denominata **ImportedPst**. Questa cartella si trovano nella cassetta postale dell'utente allo stesso livello nella cartella Posta in arrivo.<br/><br/> **Suggerimento:** Si consiglia di eseguire alcuni test batch per provare a questo parametro è quindi possibile determinare il percorso della cartella indicato da importare file di file pst.  <br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `/` <br/> Oppure  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Questo parametro opzionale specifica un valore numerico per la tabella codici da utilizzare per l'importazione di file PST in formato ANSI. Questo parametro viene utilizzato per l'importazione di file PST di organizzazioni cinese e giapponese, coreano, dal momento che queste lingue utilizzano in genere un set di caratteri a byte doppio (DBCS) per la codifica dei caratteri. Se questo parametro non viene utilizzato per importare i file PST per le lingue che utilizzano DBCS per i nomi delle cartelle delle cassette postali, i nomi delle cartelle sono spesso incomprensibile dopo l'importazione.<br/><br/> Per un elenco di valori supportati da utilizzare per questo parametro, vedere [Identificatori di pagina di codice](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> <br/>**Nota:** Come già indicato, questo è un parametro facoltativo e non è necessario includere nel file CSV. Oppure includerlo e lasciare il valore vuoto per una o più righe.<br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `932`(ovvero l'identificatore della tabella codici per ANSI/OEM giapponese)  <br/> |
    | `SPFileContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPManifestContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPSiteUrl` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>Passaggio 5: creare un processo di Importazione PST in Office 365

Il passaggio successivo consiste nel creare il processo di importazione di file PST nel servizio di importazione in Office 365. Come indicato in precedenza, si invierà il file di mapping di importazione di file PST creato nel passaggio 4. Dopo aver creato il nuovo processo, Office 365 consente di analizzare i dati in file PST e offre la possibilità per filtrare i dati importati effettivamente Ottiene alle cassette postali specificate nel file di mapping di importazione file PST (vedere [passaggio 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance di dati** e quindi fare clic su **Importa**.
    
3. Nella pagina **importazione** fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
    **Nota:** È necessario disporre delle autorizzazioni appropriate per accedere alla pagina **importazione** in sicurezza &amp; centro conformità per creare un nuovo processo di importazione. Vedere la sezione **operazioni preliminari** per ulteriori informazioni. 
    
4. Digitare un nome per il processo di importazione file PST e quindi fare clic su **Avanti**. Utilizzare le lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella **si desidera caricare o inclusi dati?** di pagina, fare clic su **Carica i dati** e quindi fare clic su **Avanti**.
    
    ![Fare clic su Carica processo di importazione dei dati per creare un caricamento di rete](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Nel passaggio 4 nella pagina **Importa dati** scegliere il **operazione completata caricamento dei file** e **dispongo di accesso al file di mapping** di caselle di controllo e quindi fare clic su **Avanti**.
    
    ![Fare clic su due caselle di controllo nel passaggio 4](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. Nella pagina **Selezionare il file di mapping** , fare clic su **selezionare file di mapping** per inviare il file di mapping di importazione di file PST creato nel passaggio 4. 
    
    ![Fare clic su file di mapping selezionare per inviare il file CSV creato per il processo di importazione](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Dopo il nome del file CSV file viene visualizzato in **nome file di Mapping**, fare clic su **convalida** per verificare che il file CSV per gli errori. 
    
    ![Fare clic su convalida per controllare il file CSV per gli errori](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Il file CSV deve essere convalidato per creare un processo di importazione di file PST. Nota il nome del file viene impostato su verde dopo la convalida. In caso contrario, fare clic sul collegamento **Visualizza registro** . Viene aperto un rapporto di errore di convalida, con un messaggio di errore per ogni riga nel file che non è riuscita. 
    
9. Dopo che il file di mapping PST è stato convalidato, leggere il documento termini e le condizioni e quindi selezionare la casella di controllo.
    
10. Fare clic su **Salva** per inviare il processo e quindi fare clic su **Chiudi** dopo il processo sia stato creato. 
    
    Viene visualizzata una pagina di comparsa stato, con lo stato **dell'analisi in corso** e il nuovo processo di importazione viene visualizzato nell'elenco nella pagina **importazione** . 
    
11. Fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni sullo stato viene visualizzate nella colonna **stato** . Quando sono pronti per essere importati i dati dell'analisi, lo stato viene modificato per **Analisi completata**.
    
    È possibile scegliere il processo di importazione per visualizzare la pagina stato comparsa, contenente informazioni più dettagliate sul processo di importazione, ad esempio lo stato di tutti i file PST elencati nel file di mapping.
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Passaggio 6: Filtrare i dati e avviare il processo di importazione di file PST

Dopo aver creato il processo di importazione nel passaggio 5, Office 365 consente di analizzare i dati in file PST (in modo sicuro e protetto) identificando validità degli elementi e i diversi tipi di messaggi inclusi nei file PST. Una volta completata l'analisi ed sono possibile importare i dati, è possibile importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando i filtri che consentono di controllare quali dati vengono importati.
  
1. Nella pagina **importazione** in sicurezza &amp; centro conformità, fare clic su **Pronto essere importato a Office 365** per il processo di importazione creata nel passaggio 5. 
    
    ![Fare clic su pronto per importare accanto al processo di importazione che è stato creato a Office 365](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Volo pagina viene visualizzato con informazioni sui file PST e altre informazioni sul processo di importazione.
    
2. Nella pagina tendina fare clic su **Importa a Office 365**.
    
    Verrà visualizzata la pagina di **filtrare i dati** . Contiene informazioni dati risultanti dall'analisi eseguita in file PST da Office 365, incluse le informazioni sulla validità dei dati. A questo punto è possibile filtrare i dati verranno importati o importano tutti i dati di esempio è. 
    
    ![È possibile tagliare i dati in file PST o importare tutto](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Eseguire una di queste operazioni:
    
    r. per tagliare i dati da importare, fare clic su **Sì, desidero filtrarla prima dell'importazione**.
    
    Per istruzioni dettagliate sul filtro dei dati in file PST e quindi avviare il processo di importazione, vedere [filtro di dati durante l'importazione di file PST a Office 365](filter-data-when-importing-pst-files.md).
    
    Oppure
    
    b. per importare tutti i dati in file PST, fare clic su **No, desidera importare tutti gli elementi** e fare clic su **Avanti**.
    
4. Se si è scelto di importare tutti i dati, fare clic su **Importa dati** per avviare il processo di importazione. 
    
    Lo stato del processo di importazione è visualizzato nella pagina **importazione** . Fare clic su ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) **Aggiorna** per aggiornare le informazioni sullo stato viene visualizzate nella colonna **stato** . Fare clic sul processo di importazione per visualizzare la pagina stato comparsa, che visualizza le informazioni di stato per ogni file PST da importare. 

## <a name="how-the-import-process-works"></a>Come funziona il processo di importazione
  
È possibile utilizzare l'opzione per il caricamento di rete e il servizio Office 365 importare per l'importazione in blocco dei file PST cassette postali degli utenti. Caricamento di rete si intende caricare i file PST area di archiviazione temporanea nel cloud Microsoft. Il servizio Office 365 importazione quindi copiati i file PST dall'area di archiviazione alle cassette postali utente di destinazione.
  
Ecco una figura e una descrizione del processo di caricamento di rete per importare i file PST alle cassette postali in Office 365.
  
![Flusso di lavoro della rete caricare processo per importare i file PST a Office 365](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Scarica i file PST importare strumento e il percorso di archiviazione Azure chiavi su private** - il primo passaggio consiste nel scaricare lo strumento da riga di comando AzCopy Azure e un tasto consente di caricare i file PST in una posizione di archiviazione Azure nel cloud Microsoft. Per ottenere tali nella pagina **importazione** in Office 365 Security &amp; centro conformità. Il tasto (denominato una chiave di firma (SAS) di protezione dell'accesso, vengono fornite le autorizzazioni necessarie per i file PST di caricamento per privato e la protezione di percorso di archiviazione Azure. Questo tasto di scelta rapida è univoco nell'organizzazione e consente di impedire l'accesso non autorizzato ai file PST dopo essere state caricate nel cloud Microsoft. Si noti che l'importazione di file PST in Office 365 non richiede l'organizzazione disporre di una sottoscrizione di Azure separata. 
    
2. **Caricare i file PST nella posizione di archiviazione Azure** - il passaggio successivo consiste nell'utilizzare lo strumento AzCopy.exe (scaricato nel passaggio 1) per caricare e archiviare i file PST in un percorso di archiviazione Azure che si trova nello stesso datacenter Microsoft internazionali in Office 365 organizzazione si trova. Per caricare li, i file PST che si desidera importare in Office 365 devono trovarsi in una condivisione file o un file server nella propria organizzazione.
    
    Si noti che non vi è un'operazione facoltativa che è possibile eseguire per visualizzare l'elenco dei file PST dopo essere state caricate nel percorso di archiviazione Azure.
    
3. **Creare un file di mapping di importazione file PST** - dopo i file PST sono stati caricati nella posizione di archiviazione Azure, il passaggio successivo consiste nel creare un file virgole (CSV) virgola che specifica quali cassette postali degli utenti al file PST verrà importato in un file PST può essere  importazione di cassetta postale principale dell'utente o loro cassetta postale di archiviazione. Il servizio Office 365 importare utilizzerà le informazioni nel file CSV per importare i file PST.
    
4. **Processo di importazione crea un file PST** , il passaggio successivo consiste nel creare un processo di importazione file PST nella pagina **importazione** in sicurezza &amp; centro conformità e inviare il file di mapping di importazione di file PST creato nel passaggio precedente. Dopo aver creato il processo di importazione, Office 365 consente di analizzare i dati in file PST e offre la possibilità di impostare i filtri che consentono di controllare quali dati ottiene effettivamente importati alle cassette postali specificate nel file di mapping di importazione file PST. 
    
5. **Filtro dati PST che verranno importati alle cassette postali** - dopo aver creato e avviato il processo di importazione, Office 365 consente di analizzare i dati in file PST (in modo sicuro e in modo sicuro) identificando validità degli elementi e i diversi tipi di messaggi inclusi nei file PST . Una volta completata l'analisi ed sono possibile importare i dati, è possibile importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando i filtri che consentono di controllare quali dati vengono importati.
    
6. **Avviare il processo di importazione file PST** - dopo l'inizio del processo di importazione, Office 365 utilizza le informazioni nel file di mapping di importazione file PST per importare i file pst dalla posizione di archiviazione Azure egli cassette postali degli utenti. Informazioni sullo stato del processo di importazione, incluse quelle relative a ogni file PST da importare, viene visualizzate nella pagina **importazione** in sicurezza &amp; centro conformità. Al termine del processo di importazione, lo stato del processo è impostato su **completo**.
  
## <a name="more-information"></a>Ulteriori informazioni

- Il motivo per cui importare i file PST a Office 365?
    
  - È un modo efficace per importare i dati dell'organizzazione archiviazione messaggistica per Office 365.
    
  - I dati sono disponibili per l'utente da tutti i dispositivi in quanto vengono memorizzati nel cloud.
    
  - Vengono fornite informazioni utili soddisfare esigenze di conformità dell'organizzazione grazie alla possibilità di applicare le caratteristiche di Office 365 conformità ai dati dei file PST importato. Includono:
    
  - Abilitazione delle [cassette postali di archiviazione](enable-archive-mailboxes.md) e [l'espansione automatica di archiviazione](enable-unlimited-archiving.md) per fornire agli utenti di spazio di archiviazione delle cassette postali aggiuntive per archiviare i dati importati. 
    
  - Posizionare le cassette postali di [Conservazione per controversia legale](https://go.microsoft.com/fwlink/?linkid=856286) per mantenere i dati importati. 
    
  - Utilizzo di Microsoft [gli strumenti di eDiscovery](search-for-content.md) per cercare i dati importati. 
    
  - Utilizzare [criteri di conservazione di Office 365](retention-policies.md) per controllare la durata verranno mantenuti i dati importati e l'azione da eseguire dopo la scadenza del periodo di conservazione. 
    
  - Ricerca il [Registro di controllo di Office 365](search-the-audit-log-in-security-and-compliance.md) per gli eventi relativi alla cassetta postale che influiscono sui dati importati. 
    
  - Importazione dei dati [delle cassette postali inattive](create-and-manage-inactive-mailboxes.md) per archiviare i dati per motivi di conformità. 
    
  - Utilizzo di [criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md) per evitare che i dati sensibili vengano perdute all'esterno dell'organizzazione. 
  
- Di seguito è riportato un esempio dell'URL condivisi Access firma (SAS) ottenuto nel passaggio 1. In questo esempio contiene anche la sintassi del comando che viene eseguita nello strumento di AzCopy.exe per il caricamento di file PST a Office 365. È necessario adottare alcune precauzioni per proteggere l'URL SAS nello stesso modo in cui è necessario proteggere password o altre informazioni relative alla sicurezza.

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  **True** so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the **Set-Mailbox -RetentionHoldEnabled $false** command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 8/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
