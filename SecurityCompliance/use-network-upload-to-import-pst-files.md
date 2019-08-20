---
title: Usare il caricamento in rete per importare file PST dell'organizzazione in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'Per gli amministratori: informazioni su come usare il caricamento in rete per importare più file PST in blocco nelle cassette postali degli utenti in Office 365.'
ms.openlocfilehash: bd15216df69e003a5aaddb2ec21ede4da5c5c312
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854820"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>Usare il caricamento in rete per importare file PST dell'organizzazione in Office 365

> [!NOTE]
> Questo articolo è rivolto agli amministratori. L'utente sta tentando di importare file PST nella propria cassetta postale? Vedere [Importare posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
Di seguito sono riportate le istruzioni dettagliate necessarie per importare più file PST in blocco nelle cassette postali di Office 365 tramite caricamento in rete. Vedere [Domande frequenti su come importare file PST in blocco nelle cassette postali di Office 365 tramite caricamento in rete](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files) per le domande frequenti in merito.
  
[Passaggio 1: Copiare l'URL della firma di accesso condiviso e installare Azure AzCopy](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[Passaggio 2: Caricare i file PST in Office 365](#step-2-upload-your-pst-files-to-office-365)

[(Facoltativo) Passaggio 3: Visualizzare un elenco dei file PST caricati in Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Passaggio 4: Creare il file di mapping dell'importazione PST](#step-4-create-the-pst-import-mapping-file)

[Passaggio 5: Creare un processo di importazione PST in Office 365](#step-5-create-a-pst-import-job-in-office-365)

[Passaggio 6: Filtrare i dati e avviare il processo di importazione PST](#step-6-filter-data-and-start-the-pst-import-job)

Tenere presente che è necessario eseguire il passaggio 1 una sola volta per importare i file PST nelle cassette postali di Office 365. Dopo aver completato questi passaggi, eseguire la procedura dal punto 2 al punto 6 ogni volta che si desidera caricare e importare un batch di file PST.

## <a name="before-you-begin"></a>Prima di iniziare
  
- All'utente deve essere assegnato il ruolo di importazione/esportazione di cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione/importazione cassette postali al gruppo di ruoli Gestione organizzazione. In alternativa, l'utente può creare un nuovo gruppo di ruoli, assegnare il ruolo Esportazione/Importazione cassette postali e infine aggiungersi come membro. Per altre informazioni, vedere le sezioni "Aggiungere un ruolo a un gruppo di ruoli" o "Creare un gruppo di ruoli" in [Gestire i gruppi di ruoli](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Inoltre, per creare processi di importazione nel Centro sicurezza e conformità, una delle seguenti condizioni deve essere vera:
    
  - All'utente deve essere assegnato il ruolo Destinatari di posta in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Gestione destinatari.
    
    Oppure
    
  - L'utente deve essere un amministratore globale nell'organizzazione di Office 365.
    
  > [!TIP]
    > Prendere in considerazione la creazione di un nuovo gruppo di ruoli in Exchange Online appositamente creato per l'importazione dei file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione/esportazione di cassette postali e Destinatari di posta al nuovo gruppo di ruoli, quindi aggiungere i membri. 
  
- L'unico metodo supportato per importare file PST in Office 365 consiste nell'usare lo strumento Azure AzCopy, come descritto in questo argomento. Non è possibile usare Azure Storage Explorer per caricare i file PST direttamente nell'area di archiviazione di Azure.
    
- È necessario archiviare i file PST che si desidera importare in Office365 su un file server o su una cartella condivisa dell'organizzazione. Nel passaggio 2, viene eseguito lo strumento Azure AzCopy che permette di caricare i file PST archiviati nel file server o nella cartella condivisa in Office 365.
    
- Questa procedura implica la copia e il salvataggio di una copia di un URL che contiene una chiave di accesso. Queste informazioni verranno usate nel passaggio 2 per caricare i file PST e nel passaggio 3 se si vuole visualizzare un elenco dei file PST caricati in Office 365. Assicurarsi di adottare alcune precauzioni per proteggere questo URL, come si farebbe con le password o altre informazioni correlate alla sicurezza. È ad esempio possibile salvarle in un documento di Microsoft Word protetto da password oppure in un'unità USB crittografata. Per un esempio di questa combinazione di URL e chiave, vedere la sezione [Altre informazioni](#more-information). 
    
- È possibile importare i file PST in una cassetta postale inattiva di Office 365. A questo scopo, specificare il GUID della cassetta postale inattiva nel parametro `Mailbox` del file di mapping di importazione PST. Per informazioni, vedere il passaggio 4 della scheda **Istruzioni** in questo argomento. 
    
- In una distribuzione ibrida di Exchange è possibile importare i file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale si trova in locale. A questo scopo, procedere come segue nel file di mapping di importazione PST:
    
  - Specificare l'indirizzo di posta elettronica della cassetta postale locale dell'utente nel parametro `Mailbox`. 
    
  - Specificare il valore **TRUE** nel parametro `IsArchive`. 
    
    Per altre informazioni, vedere il [passaggio 4](#step-4-create-the-pst-import-mapping-file). 
    
- Dopo l'importazione dei file PST in una cassetta postale di Office 365, l'impostazione di blocco della conservazione per la cassetta postale viene attivata per una durata indefinita. Questo significa che i criteri di conservazione assegnati alla cassetta postale non vengono elaborati finché non si disattiva il blocco della conservazione o non si imposta una data per disattivare il blocco. Qual è il motivo di questa impostazione? Se i messaggi importati in una cassetta postale sono vecchi, potrebbero essere eliminati in modo definitivo perché il loro periodo di conservazione è scaduto in base alle impostazioni di conservazione configurate per la cassetta postale. L'impostazione di un blocco della conservazione sulla cassetta postale darà al suo proprietario il tempo di gestire questi messaggi appena importati o all'amministratore il tempo di cambiare le impostazioni di conservazione per la cassetta postale. Vedere la scheda **Altre informazioni** in questo argomento per suggerimenti sulla gestione del blocco della conservazione. 
    
- Per impostazione predefinita, 35 MB è la dimensione massima dei messaggi che possono essere ricevuti da una cassetta postale di Office 365, perché il valore predefinito della proprietà *MaxReceiveSize* per una cassetta postale è impostato su 35 MB. Tuttavia, la dimensione massima di ricezione dei messaggi in Office 365 è pari a 150 MB. Quindi, se si importa un file PST che contiene un elemento di dimensioni maggiori ai 35 MB, il servizio di importazione di Office 365 modificherà automaticamente il valore della proprietà *MaxReceiveSize* nella cassetta postale di destinazione in 150 MB. Questo consente di importare messaggi di dimensione fino a 150 MB nelle cassette postali degli utenti. 
    
    > [!TIP]
    > Per identificare la dimensione di ricezione dei messaggi per una cassetta postale, è possibile eseguire il comando `Get-Mailbox <user mailbox> | FL MaxReceiveSize` in Exchange Online PowerShell. 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>Passaggio 1: Copiare l'URL della firma di accesso condiviso e installare Azure AzCopy

Il primo passaggio consiste nello scaricare e installare lo strumento Azure AzCopy, ossia quello che verrà eseguito nel passaggio 2 per caricare i file PST in Office 365. Verrà anche copiato l'URL della firma di accesso condiviso dell'organizzazione. Questo URL è una combinazione dell'URL di rete del percorso di archiviazione di Azure nel cloud Microsoft per l'organizzazione e di una chiave della firma di accesso condiviso. La chiave fornisce le autorizzazioni necessarie per caricare i file PST nel percorso di archiviazione di Azure. Assicurarsi di adottare alcune precauzioni per proteggere l'URL della firma di accesso condiviso, che è univoco per l'organizzazione e verrà usato nel passaggio 2.

> [!IMPORTANT]
> Per importare file PST con il metodo di caricamento in rete, è consigliabile usare la versione di Azure AzCopy che può essere scaricata nel passaggio 6b della procedura seguente.
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore dell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro del Centro sicurezza e conformità, fare clic su **Governance dei dati** \> **Importa**.
    
    > [!NOTE]
    > È necessario avere le autorizzazioni appropriate per accedere alla pagina di importazione**** nel Centro sicurezza e conformità. Per altre informazioni, vedere la sezione **Prima di iniziare**. 
    
3. Nella pagina **Importa**, fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) **Nuovo processo di importazione**.
    
    Viene avviata la procedura guidata per il processo di importazione.
    
4. Digitare un nome per il processo di importazione PST e quindi fare clic su **Avanti**. Usare lettere minuscole, numeri, trattini e caratteri di sottolineatura. Il nome non può contenere lettere maiuscole o spazi.
    
5. Nella pagina **Caricare o spedire i dati?**, fare clic su **Caricamento dei dati**, quindi su **Avanti**.
    
    ![Fare clic su Caricamento dei dati per creare un processo di importazione per il caricamento in rete](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Nella pagina **Importa dati** eseguire le due procedure seguenti: 
    
    ![Copiare l'URL della firma di accesso condiviso e scaricare lo strumento Azure AzCopy nella pagina Importa dati](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a. Nel passaggio 2 fare clic su **Mostra l'URL della firma di accesso condiviso per il caricamento in rete**. Dopo aver visualizzato l'URL della firma di accesso condiviso, fare clic su **Copia negli Appunti** e incollarlo e salvarlo in un file in modo da potervi accedere in un secondo momento.
    
    b. Nel passaggio 3, fare clic su **Scarica Azure AzCopy** per scaricare e installare lo strumento Azure AzCopy. Nella finestra popup fare clic su **Esegui** per installare AzCopy. 
    
> [!NOTE]
> È possibile uscire dalla pagina **Importa dati** aperta (nel caso in cui sia necessario copiare di nuovo l'URL della firma di accesso condiviso) oppure fare clic su **Annulla** per chiuderla. 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>Passaggio 2: Caricare i file PST in Office 365

A questo punto, è possibile utilizzare lo strumento AzCopy.exe per caricare i file PST in Office365. Grazie allo strumento, è possibile caricarli e archiviarli in un percorso di archiviazione di Azure all'interno del cloud Microsoft. Come precedentemente illustrato, il percorso di archiviazione di Azure in cui si caricano i file PST si trova nello stesso datacenter Microsoft locale in cui si trova l'organizzazione di Office 365. Per completare questo passaggio, è necessario che i file PST siano posizionati in una condivisione file o in un file server dell'organizzazione. In questa procedura, tale posizione viene definita directory di origine. Ogni volta che si esegue lo strumento AzCopy.exe, sarà possibile specificare una directory di origine diversa. 
  
1. Aprire un prompt dei comandi nel computer locale.
    
2. Accedere alla directory nella quale è stato installato lo strumento AzCopy.exe durante il primo passaggio. Se lo strumento è stato installato nel percorso predefinito, passare a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.
    
3. Eseguire il comando seguente per caricare i file su Office 365.

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > Specificare una directory come percorso di origine nel comando precedente. Non è possibile specificare un file PST singolo. Tutti i file PST nella directory di origine verranno caricati.
 
    Nella tabella seguente vengono descritti i parametri AzCopy.exe e i relativi valori. Nei valori per questi parametri si usano le informazioni ottenute nel passaggio precedente.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Specifica la directory di origine nell'organizzazione che contiene i file PST che verranno caricati su Office365.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Specifica l'URL della firma di accesso condiviso ottenuto nel passaggio 1.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> **Suggerimento:** (facoltativo) è possibile specificare una sottocartella del percorso di archiviazione di Azure in cui caricare i file PST. A questo scopo, aggiungere un percorso di sottocartella (dopo "ingestiondata") nell'URL della firma di accesso condiviso. Nel primo esempio non viene specificata una sottocartella, quindi i file PST verranno caricati nella radice (*ingestiondata*) del percorso di archiviazione di Azure. Nel secondo esempio i file PST vengono caricati in una sottocartella (*PSTFiles*) nella radice del percorso di archiviazione di Azure.  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> Oppure  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Restituisce messaggi di stato dettagliati in un file di log. Per impostazione predefinita, il file di log dettagliato è denominato AzCopyVerbose.log e si trova in %LocalAppData%\Microsoft\Azure\AzCopy. Se si specifica un percorso di un file esistente per questa opzione, il log dettagliato verrà aggiunto a tale file.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Questa opzione facoltativa specifica la modalità ricorsiva, in modo che lo strumento AzCopy copi i file PST che si trovano nelle sottocartelle nella directory di origine specificata dal parametro `/Source:`.  <br/> **Nota:** se si include questa opzione, i file PST delle cartelle secondarie, una volta caricati, avranno un percorso dei file diverso nel percorso di archiviazione di Azure. È necessario specificare il percorso esatto nel file CSV creato al passaggio 4.  <br/> | `/S` <br/> |
    | `/Y` <br/> |Questo passaggio obbligatorio consente di usare i token SAS di sola scrittura quando si caricano i file PST nel percorso di archiviazione di Azure. L'URL della firma di accesso condiviso ottenuto nel passaggio 1 (e specificato nel parametro `/Dest:`) è un URL della firma di accesso condiviso di sola scrittura, che è il motivo per cui è necessario includere questo passaggio. Tenere presente che un URL della firma di accesso condiviso di sola scrittura non impedisce di usare Azure Storage Explorer per visualizzare un elenco dei file PST caricati nel percorso di archiviazione di Azure.  <br/> | `/Y` <br/> |
   
Di seguito è riportato un esempio di sintassi dello strumento AzCopy.exe nella quale verranno utilizzati i valori effettivi di ogni parametro:
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

Dopo aver eseguito il comando, vengono visualizzati messaggi di stato che indicano lo stato di avanzamento del caricamento dei file PST. Un messaggio di stato finale mostra il numero totale di file caricati correttamente. 

> [!TIP]
> Dopo aver eseguito il comando AzCopy.exe e aver verificato che tutti i parametri siano corretti, salvare una copia della sintassi della riga di comando nello stesso file (protetto) in cui sono state copiate le informazioni ottenute nel passaggio 1. A questo punto, copiare e incollare il comando in un prompt a ogni esecuzione dello strumento AzCopy.exe per caricare i file PST su Office365. Probabilmente, sarà necessario cambiare soltanto i valori del parametro `/Source:`. Ciò dipende dalla directory di origine nella quale si trovano i file PST.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(Facoltativo) Passaggio 3: Visualizzare un elenco dei file PST caricati in Office 365

Come passaggio facoltativo, è possibile installare e utilizzare Microsoft Azure Storage Explorer (uno strumento open source gratuito) per visualizzare l'elenco dei file PST caricati nel BLOB di Azure. Esistono due validi motivi per eseguire questa operazione:
  
- Verificare che i file PST siano stati caricati in modo corretto dalla cartella condivisa o dal file server dell'organizzazione nel BLOB di Azure.
    
- Verificare il nome file (e il percorso della sottocartella, se incluso) per ogni file PST caricato nel BLOB di Azure. Ciò è particolarmente utile quando si crea il file di mapping PST nel passaggio successivo poiché è necessario specificare sia il nome del file sia il percorso della cartella per ogni file PST. La verifica di questi nomi consente di ridurre i potenziali errori nel file di mapping PST.
    
Lo strumento Microsoft Azure Storage Explorer è in anteprima.
  
> [!IMPORTANT]
> Non è possibile usare Azure Storage Explorer per caricare o modificare i file PST. L'unico metodo di importazione dei file PST in Office 365 supportato prevede l'uso di AzCopy. Inoltre, non si possono eliminare i file PST caricati nel BLOB di Azure. Se si tenta di eliminare un file PST, si riceve un errore relativo all'assenza delle autorizzazioni necessarie. Tutti i file PST vengono eliminati automaticamente dall'area di archiviazione di Azure. Se non ci sono processi di importazione in corso, tutti i file PST nel contenitore **ingestiondata** vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente.
  
Per installare Azure Storage Explorer e connettersi all'area di archiviazione di Azure:
  
1. Scaricare e installare lo [strumento Microsoft Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Avviare Microsoft Azure Storage Explorer, fare clic con il pulsante destro del mouse su **Account di archiviazione** nel riquadro sinistro e quindi fare clic su **Connetti ad Archiviazione di Azure**.
    
    ![Fare clic con il pulsante destro del mouse su Account di archiviazione e quindi scegliere Connetti ad Archiviazione di Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Fare clic sul comando **** per usare un URI della firma di accesso condiviso o una stringa di connessione e quindi fare clic su **Avanti**.
    
4. Fare clic sul comando **** per usare un URI della firma di accesso condiviso, incollare l'URL della firma di accesso condiviso ottenuto nel passaggio 1 nella casella sotto **URI** e quindi fare clic su **Avanti**.
    
5. Nella pagina **Riepilogo connessione** è possibile rivedere le informazioni sulla connessione e quindi fare clic su **Connetti**.
    
    Viene aperto il contenitore **ingestiondata**, che contiene i file PST caricati nel passaggio 2. Il contenitore **ingestiondata** si trova in **Account di archiviazione** \> **(SAS-Attached Services)** \> **Contenitori BLOB**. 
    
    ![Azure Storage Explorer mostra un elenco di file con estensione PST caricati](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Al termine dell'utilizzo di Microsoft Azure Storage Explorer, fare clic con il pulsante destro del mouse su **ingestiondata**, quindi selezionare **Disconnetti** per scollegarsi dall'area di archiviazione di Azure. In caso contrario, verrà visualizzato un errore al successivo tentativo di associazione. 
    
    ![Fare clic con il pulsante destro del mouse sull'inserimento e su Disconnetti per disconnettersi dall'area di archiviazione Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Passaggio 4: Creare il file di mapping dell'importazione PST

Una volta caricati i file PST nel percorso di archiviazione di Azure per l'organizzazione di Office 365, il passaggio successivo prevede la creazione di un file CSV che indica in quali cassette postali dell'utente verranno importati i file PST. È necessario inviare il file CSV nel passaggio successivo a quello di creazione del processo di importazione PST.
  
1. [Scaricare una copia del file di mapping dell'importazione PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
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
    Nella prima riga o in quella dell'intestazione del file CSV vengono elencati i parametri che verranno usati dal servizio di importazione PST per importare i file PST nelle cassette postali dell'utente. Ogni nome di parametro è separato da una virgola. Ogni riga al di sotto di quella dell'intestazione riporta i valori del parametro che consentono di importare un file PST in una cassetta postale specifica. È necessaria una riga per ogni file PST da importare nella cassetta postale di un utente. Assicurarsi di sostituire i dati segnaposto nel file di mapping con i dati effettivi.

   **Nota:** non apportare modifiche nella riga di intestazione, compresi i parametri SharePoint. Questi verranno ignorati durante il processo di impostazione PST. 

 3. Utilizzare le informazioni della tabella per popolare il file CSV con i dati necessari.


    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Specifica il servizio di Office365 nel quale verranno importati i dati. Per importare i file PST nelle cassette postali dell'utente, utilizzare `Exchange`.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Specifica la posizione della cartella nel percorso di archiviazione di Azure nel quale sono stati caricati i file PST durante il passaggio 2.  <br/> Se nel parametro `/Dest:` non è stato incluso un nome di sottocartella facoltativo nell'URL della firma di accesso condiviso nel passaggio 2, lasciare vuoto questo parametro nel file CSV. Se invece è stato incluso un nome di sottocartella, specificarlo in questo parametro (vedere il secondo esempio). Per il valore di questo parametro è rilevante la distinzione tra maiuscole e minuscole.  <br/> In entrambi i casi, *non* includere "ingestiondata" nel valore per il parametro `FilePath`.  <br/><br/> **Importante:** la combinazione di maiuscole e minuscole nel percorso file deve corrispondere a quella usata se è stato incluso un nome di sottocartella facoltativo nell'URL della firma di accesso condiviso nel parametro `/Dest:` nel passaggio 2. Ad esempio, se il nome usato per la sottocartella nel passaggio 2 è `PSTFiles` e quindi si usa `pstfiles` nel parametro `FilePath` nel file CSV, l'importazione per il file PST avrà esito negativo. Assicurarsi di usare la stessa combinazione di maiuscole e minuscole in entrambi i casi.  <br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Specifica il nome del file PST che verrà importato nella cassetta postale dell'utente. Per il valore di questo parametro è rilevante la distinzione tra maiuscole e minuscole.  <br/> <br/>**Importante:** la combinazione di maiuscole e minuscole per il nome del file PST nel file CSV deve corrispondere a quella del file PST caricato nel percorso di archiviazione di Azure nel passaggio 2. Ad esempio, se si usa `annb.pst` nel parametro `Name` nel file CSV, ma il nome del file PST effettivo è `AnnB.pst`, l'importazione del file PST avrà esito negativo. Assicurarsi che il nome del file PST nel file CSV contenga la stessa combinazione di maiuscole e minuscole del file PST effettivo.  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Specifica l'indirizzo di posta elettronica della cassetta postale nella quale verrà importato il file PST. Non è possibile specificare una cartella pubblica perché il servizio di importazione PST non supporta l'importazione di file PST nelle cartelle pubbliche.  <br/> Per importare un file PST in una cassetta postale inattiva, è necessario specificare il GUID della cassetta postale in questo parametro. Per ottenere questo GUID, eseguire il comando di PowerShell seguente in Exchange Online: `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**Nota:** in alcuni casi possono essere presenti più cassette postali con lo stesso indirizzo di posta elettronica, dove una cassetta postale è attiva e l'altra è in stato di eliminazione reversibile (o inattiva). In una situazione di questo tipo è necessario specificare il GUID della cassetta postale per identificare in modo univoco la cassetta postale in cui importare il file PST. Per ottenere questo GUID per le cassette postali attive, eseguire il comando di PowerShell seguente: `Get-Mailbox <identity of active mailbox> | FL Guid`. Per ottenere il GUID per le cassette postali con eliminazione reversibile (o inattive), eseguire il comando `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.  <br/> | `annb@contoso.onmicrosoft.com` <br/> Oppure  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Specifica se importare o meno il file PST nella cassetta postale di archiviazione dell'utente. Esistono due opzioni:  <br/><br/>**FALSE**: importa il file PST nella cassetta postale principale dell'utente.  <br/> **TRUE**: importa il file PST nella cassetta postale di archiviazione dell'utente. In questo caso si presuppone che [la cassetta postale di archiviazione dell'utente sia abilitata](enable-archive-mailboxes.md). <br/><br/>Se si imposta questo parametro su `TRUE` e la cassetta postale di archiviazione dell'utente non è abilitata, l'importazione per tale utente non riesce. Tenere presente che se l'importazione per un utente non riesce (perché la sua cassetta postale di archiviazione non è abilitata e questa proprietà è impostata su `TRUE`), gli altri utenti coinvolti nel processo di importazione non ne vengono in alcun modo interessati.  <br/>  Se si lascia vuoto questo parametro, il file PST viene importato nella cassetta postale principale dell'utente.  <br/> <br/>**Nota:** per importare un file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale si trova in locale, basta specificare `TRUE` per questo parametro e fornire l'indirizzo di posta elettronica della cassetta postale locale dell'utente nel parametro `Mailbox`.  <br/> | `FALSE` <br/> Oppure  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Specifica la cartella della casetta postale in cui viene importato il file PST.  <br/>  Se si lascia vuoto questo parametro, il file PST verrà importato in una nuova cartella** **per gli elementi importati, che si trova a livello radice della cassetta postale (lo stesso livello della cartella Posta in arrivo e di altre cartelle predefinite della cassetta postale).  <br/>  Se si specifica `/`, gli elementi nel file PST verranno importati direttamente nella cartella Posta in arrivo dell'utente.  <br/><br/>  Se si specifica `/<foldername>`, gli elementi nel file PST verranno importati in una cartella denominata *\<foldername\>*. Ad esempio, se si usa `/ImportedPst`, gli elementi vengono importati in una cartella denominata **ImportedPst**. Questa cartella si troverà nella cassetta postale dell'utente allo stesso livello della cartella Posta in arrivo.  <br/><br/> **Suggerimento:** eseguire alcuni test per provare il parametro al fine di determinare il percorso migliore per la cartella nella quale importare i file PST.  <br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `/` <br/> Oppure  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Questo parametro facoltativo specifica un valore numerico per la tabella codici da usare per l'importazione dei file PST nel formato ANSI. Questo parametro viene usato per l'importazione di file PST da organizzazioni cinesi, giapponesi e coreane perché queste lingue in genere usano un set di caratteri a due byte (DBCS) per la codifica dei caratteri. Se non si usa questo parametro per importare file PST per le lingue che usano il set di caratteri DBCS per i nomi delle cartelle delle cassette postali, i nomi delle cartelle spesso appaiono illeggibili dopo l'importazione.  <br/><br/> Per un elenco dei valori supportati da usare per questo parametro, vedere la pagina dedicata agli [identificatori delle tabelle codici](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> <br/>**Nota:** come indicato in precedenza, si tratta di un parametro facoltativo che non è necessario inserire nel file CSV. Può anche essere incluso lasciando il valore vuoto per una o più righe.  <br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `932` (identificatore della tabella codici per il giapponese ANSI/OEM)  <br/> |
    | `SPFileContainer` <br/> |Per l'importazione PST, omettere questo parametro.  <br/> |Non applicabile  <br/> |
    | `SPManifestContainer` <br/> |Per l'importazione PST, omettere questo parametro.  <br/> |Non applicabile  <br/> |
    | `SPSiteUrl` <br/> |Per l'importazione PST, omettere questo parametro.  <br/> |Non applicabile  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>Passaggio 5: Creare un processo di importazione PST in Office 365

Il passaggio successivo consiste nella creazione del processo di importazione PST nel servizio di importazione in Office 365. Come descritto in precedenza, verrà inviato il file di mapping di importazione PST creato al passaggio 4. Dopo aver creato il nuovo processo, Office 365 analizza i dati nel file PST e offre la possibilità di filtrare i dati effettivamente importati nelle cassette postali specificate nel file di mapping dell'importazione PST (vedere il [passaggio 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore dell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro del Centro sicurezza e conformità, fare clic su **Governance dei dati**, quindi su **Importa**.
    
3. Nella pagina **Importa**, fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) **Nuovo processo di importazione**.
    
    **Nota:** è necessario avere le autorizzazioni appropriate per accedere alla pagina di importazione**** nel Centro sicurezza e conformità. Per altre informazioni, vedere la sezione **Prima di iniziare**. 
    
4. Digitare un nome per il processo di importazione PST e quindi fare clic su **Avanti**. Usare lettere minuscole, numeri, trattini e caratteri di sottolineatura. Il nome non può contenere lettere maiuscole o spazi.
    
5. Nella pagina **Caricare o spedire i dati?**, fare clic su **Caricamento dei dati**, quindi su **Avanti**.
    
    ![Fare clic su Caricamento dei dati per creare un processo di importazione per il caricamento in rete](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Nella pagina **Importa dati** del passaggio 4, selezionare le caselle di controllo **Ho completato il caricamento dei file** e **Ho accesso al file di mapping** e quindi fare clic su **Avanti**.
    
    ![Selezionare le due caselle di controllo del passaggio 4](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. Nella pagina **Seleziona file di mapping**, fare clic su **Seleziona file di mapping** per inviare il file di mapping dell'importazione PST creato nel passaggio 4. 
    
    ![Fare clic su Seleziona file di mapping per inviare il file CSV creato per il processo di importazione](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Quando il nome del file CSV viene visualizzato nell'elenco, in **Nome file di mapping** fare clic su **Convalida** per verificare che non ci siano errori nel file CSV. 
    
    ![Fare clic su Convalida per verificare la presenza di errori nel file CSV](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Il file CSV deve essere convalidato per creare un processo di importazione PST. Si noti che il nome del file diventa verde dopo la convalida. In caso contrario, fare clic sul collegamento **Visualizza log**. Viene aperto un report di errore di convalida, con un messaggio di errore per ogni riga del file per cui la convalida non è riuscita. 
    
9. Quando il file di mapping PST viene convalidato, leggere il documento di condizioni e quindi fare clic sulla casella di controllo.
    
10. Fare clic su **Salva** per inviare il processo e quindi fare clic su **Chiudi** al termine della creazione del processo. 
    
    Viene visualizzata una pagina di stato a comparsa con lo stato **Analisi in corso ** e il nuovo processo di importazione viene visualizzato nell'elenco nella pagina **Importa**. 
    
11. Fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni visualizzate nella colonna **Stato**. Quando l'analisi è completa e i dati sono pronti per l'importazione, lo stato diventa **Analisi completata**.
    
    È possibile fare clic sul processo di importazione per visualizzare la pagina di stato a comparsa, che contiene informazioni più dettagliate sul processo di importazione, ad esempio lo stato di ogni file PST presente nel file di mapping.
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Passaggio 6: Filtrare i dati e avviare il processo di importazione PST

Dopo avere creato il processo di importazione nel passaggio 5, Office 365 analizza i dati nei file PST in modo sicuro, identificando l'età degli elementi e i diversi tipi di messaggio inclusi nei file PST. Quando l'analisi è completa e i dati sono pronti per l'importazione, si può scegliere di importare tutti i dati nei file PST così come sono oppure filtrare i dati da importare impostando dei filtri.
  
1. Nella pagina **Importa** nel Centro sicurezza e conformità, fare clic su **Pronti a importare in Office 365** per il processo di importazione creato nel passaggio 5. 
    
    ![Fare clic su Pronti a importare in Office 365 accanto al processo di importazione creato](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Viene visualizzata una pagina a comparsa con informazioni sui file PST e sul processo di importazione.
    
2. Nella pagina a comparsa, fare clic su **Importa in Office 365**.
    
    Viene visualizzata la pagina **Filtrare i dati**. Contiene informazioni dettagliate sui dati risultanti dall'analisi eseguita sui file PST da Office 365, incluse le informazioni sulla validità dei dati. A questo punto è possibile filtrare i dati che verranno importati oppure importare tutti i dati. 
    
    ![È possibile tagliare i dati nei file PST o importarli tutti](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Eseguire una delle operazioni seguenti:
    
    a. Per filtrare i dati da importare, fare clic su **Sì, voglio filtrarli prima dell'importazione**.
    
    Per informazioni dettagliate su come filtrare i dati nei file PST e quindi avviare il processo di importazione, vedere [Filtrare i dati durante l'importazione di file PST in Office 365](filter-data-when-importing-pst-files.md).
    
    Oppure
    
    b. Per importare tutti i dati nei file PST, fare clic su **No, voglio importare tutto** e quindi fare clic su **Avanti**.
    
4. Se si sceglie di importare tutti i dati, fare clic su **Importa dati** per avviare il processo di importazione. 
    
    Lo stato del processo di importazione verrà visualizzato nella pagina **Importa**. Fare clic su ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) **Aggiorna** per aggiornare le informazioni visualizzate nella colonna **Stato**. Fare clic sul processo di importazione per visualizzare la pagina di stato a comparsa, che mostra le informazioni sullo stato per ogni file PST importato. 

## <a name="how-the-import-process-works"></a>Come funziona il processo di importazione:
  
È possibile usare l'opzione di caricamento in rete e il servizio di importazione di Office 365 per importare file PST in blocco nelle cassette postali degli utenti. Con il caricamento in rete, i file PST vengono caricati in un'area di archiviazione temporanea nel cloud Microsoft. Il servizio di importazione di Office 365 copia quindi i file PST dall'area di archiviazione alle cassette postali utente di destinazione.
  
Di seguito viene riportata un'illustrazione e una descrizione del processo di caricamento in rete per importare file PST nelle cassette postali di Office 365.
  
![Flusso del processo di caricamento in rete per importare file PST in Office 365](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Scaricare la chiave e lo strumento di importazione PST in un percorso di archiviazione privato di Azure** - Il primo passaggio consiste nello scaricare la chiave di accesso e lo strumento da riga di comando di Azure AzCopy usati per caricare i file PST in un percorso di archiviazione di Azure nel cloud Microsoft. Per ottenerli, usare la pagina di **importazione** nel Centro sicurezza e conformità. La chiave (denominata chiave della firma di accesso condiviso sicuro) fornisce all'utente le autorizzazioni necessarie per caricare i file PST in un percorso di archiviazione di Azure privato e sicuro. Questa chiave di accesso è univoca per l'organizzazione e consente di impedire l'accesso non autorizzato ai file PST dopo il caricamento nel cloud Microsoft. L'importazione di file PST in Office 365 non richiede all'organizzazione di avere un altro abbonamento a Azure. 
    
2. **Caricare file PST nel percorso di archiviazione di Azure** - Il passaggio successivo consiste nell'usare lo strumento AzCopy.exe, scaricato nel passaggio 1, per caricare e archiviare i file PST in un percorso di archiviazione di Azure che si trova nello stesso datacenter Microsoft locale in cui si trova l'organizzazione di Office 365. Per caricarli, i file PST da importare in Office 365 devono trovarsi in una condivisione file o in un file server dell'organizzazione.
    
    Tenere presente che è possibile eseguire un passaggio facoltativo che consente di visualizzare l'elenco dei file PST dopo il caricamento nel percorso di archiviazione di Azure.
    
3. **Creare un file di mapping di importazione PST** - Dopo aver caricato i file PST nel percorso di archiviazione di Azure, il passaggio successivo consiste nel creare un file con valori separati da virgola (CSV) che specifica in quali cassette postali degli utenti verranno importati i file PST. Tenere presente che i file PST possono essere importanti nella cassetta postale principale dell'utente o nella cassetta postale di archiviazione. Il servizio di importazione di Office 365 userà le informazioni contenute nel file CSV per importare i file PST.
    
4. **Creare un processo di importazione PST** - Il passaggio successivo consiste nel creare un processo di importazione PST nella pagina **Importa** del Centro sicurezza e conformità e nell'inviare il file di mapping dell'importazione PST creato nel passaggio precedente. Dopo aver creato il processo di caricamento, Office 365 analizza i dati nei file PST e offre la possibilità di impostare filtri per controllare i dati effettivamente importati nelle cassette postali specificate nel file di mapping dell'importazione PST. 
    
5. **Filtrare i dati PST che verranno importati nelle cassette postali** - Dopo la creazione e l'avvio del processo di importazione, Office 365 analizza i dati nei file PST (in modo sicuro) identificando l'età degli elementi e i diversi tipi di messaggio inclusi nei file PST. Quando l'analisi è completa e i dati sono pronti per l'importazione, si può scegliere di importare tutti i dati nei file PST così come sono oppure filtrare i dati da importare impostando dei filtri.
    
6. **Avviare il processo di importazione PST** - Dopo l'avvio del processo di importazione, Office 365 usa le informazioni nel file di mapping dell'importazione PST per importare i file PST dal percorso di archiviazione di Azure alle cassette postali degli utenti. Le informazioni sullo stato del processo di importazione, incluse quelle relative a ogni file PST da importare, vengono visualizzate nella pagina **Importa** nel Centro sicurezza e conformità. Al termine del processo di importazione, lo stato del processo è impostato su **Completato**.
  
## <a name="more-information"></a>Altre informazioni

- Perché importare i file PST in Office 365
    
  - È opportuno importare i dati di archiviazione della messaggistica dell'organizzazione in Office 365.
    
  - I dati sono disponibili per l'utente da tutti i dispositivi in quanto vengono memorizzati nel cloud.
    
  - Aiuta a soddisfare le esigenze di conformità dell'organizzazione, consentendo di applicare le caratteristiche di conformità di Office 365 ai dati dei file PST importati. Ciò include:
    
  - L'abilitazione di [cassette postali di archiviazione](enable-archive-mailboxes.md) e [l'archiviazione a espansione automatica](enable-unlimited-archiving.md) per fornire agli utenti ulteriore spazio di archiviazione delle cassette postali per archiviare i dati importati. 
    
  - Il blocco delle cassette postali con l'opzione [Blocco per controversia legale](https://go.microsoft.com/fwlink/?linkid=856286) per conservare i dati importati. 
    
  - L'uso degli [strumenti di Microsoft eDiscovery](search-for-content.md) per cercare i dati importati. 
    
  - L'uso dei [criteri di conservazione di Office 365](retention-policies.md) per controllare il periodo di conservazione dei dati importati e l'azione da eseguire dopo la sua scadenza. 
    
  - La ricerca del [log di controllo di Office 365](search-the-audit-log-in-security-and-compliance.md) per gli eventi correlati alle cassette postali che hanno effetto sui dati importati. 
    
  - L'importazione di dati in [cassette postali inattive](create-and-manage-inactive-mailboxes.md) per archiviare dati ai fini di conformità. 
    
  - L'uso di [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) per impedire la perdita di dati sensibili all'esterno dell'organizzazione. 
  
- Ecco un esempio di URL della firma di accesso condiviso ottenuto nel passaggio 1. L'esempio include anche la sintassi del comando che si esegue nello strumento AzCopy.exe per caricare i file PST su Office365. Assicurarsi di adottare alcune precauzioni per proteggere l'URL della firma di accesso condiviso, come si farebbe con le password o altre informazioni correlate alla sicurezza.

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
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is June 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 7/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
