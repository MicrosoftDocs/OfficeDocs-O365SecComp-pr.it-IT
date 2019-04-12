---
title: Utilizzare il caricamento di rete per importare i file PST dell'organizzazione in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'Per gli amministratori: informazioni su come utilizzare il caricamento di rete per importare in blocco più file PST nelle cassette postali degli utenti in Office 365.'
ms.openlocfilehash: 73123d5f36a01b31cfc38e6404bd400bb722fb36
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2019
ms.locfileid: "31814087"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>Utilizzare il caricamento di rete per importare i file PST dell'organizzazione in Office 365

> [!NOTE]
> Questo articolo è per gli amministratori. L'utente sta tentando di importare file PST nella propria cassetta postale? Vedere [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
Di seguito sono riportate le istruzioni dettagliate necessarie per utilizzare il caricamento di rete per importare in blocco più file PST nelle cassette postali di Office 365. Per le domande frequenti sull'utilizzo di caricamento di rete per importare in blocco i file PST nelle cassette postali di Office 365, vedere le [domande frequenti su come usare il caricamento di rete per importare i file PST](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).
  
[Passaggio 1: copiare l'URL SAS e installare AzCopy di Azure](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[Passaggio 2: caricare i file PST in Office 365](#step-2-upload-your-pst-files-to-office-365)

[Optional Passaggio 3: visualizzare un elenco dei file PST caricati in Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Passaggio 4: creare il file di mapping di importazione PST](#step-4-create-the-pst-import-mapping-file)

[Passaggio 5: creare un processo di importazione PST in Office 365](#step-5-create-a-pst-import-job-in-office-365)

[Passaggio 6: filtrare i dati e avviare il processo di importazione PST](#step-6-filter-data-and-start-the-pst-import-job)

Tenere presente che è necessario eseguire il passaggio 1 solo una volta per importare i file PST nelle cassette postali di Office 365. Dopo aver eseguito questa procedura, eseguire il passaggio 2 del passaggio 6 ogni volta che si desidera caricare e importare un batch di file PST.

## <a name="before-you-begin"></a>Prima di iniziare
  
- È necessario essere assegnati al ruolo di esportazione delle cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in [Manage Role](https://go.microsoft.com/fwlink/p/?LinkId=730688)groups.
    
    Per creare processi di importazione nel centro sicurezza & Compliance, è inoltre necessario che sia vero uno dei seguenti valori:
    
  - È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Oppure
    
  - È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
  > [!TIP]
    > Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
- L'unico metodo supportato per l'importazione di file PST in Office 365 consiste nell'utilizzare lo strumento AzCopy di Azure, come descritto in questo argomento. Non è possibile utilizzare l'esploratore di archiviazione di Azure per caricare i file PST direttamente nell'area di archiviazione di Azure.
    
- È necessario archiviare i file PST che si desidera importare in Office 365 in un file server o in una cartella condivisa all'interno dell'organizzazione. Nel passaggio 2 verrà eseguito lo strumento di AzCopy di Azure che caricherà i file PST archiviati in questo file server o cartella condivisa in Office 365.
    
- Questa procedura implica la copia e il salvataggio di una copia di un URL contenente un tasto di accesso. Queste informazioni verranno utilizzate nel passaggio 2 per caricare i file PST e nel passaggio 3 Se si desidera visualizzare un elenco dei file PST caricati in Office 365. Assicurarsi di prendere precauzioni per proteggere questo URL come se si proteggessero le password o altre informazioni relative alla sicurezza. Ad esempio, è possibile salvarlo in un documento di Microsoft Word protetto da password o in un'unità USB crittografata. Vedere la sezione [ulteriori informazioni](#more-information) per un esempio di questo URL e chiave combinati. 
    
- È possibile importare i file PST in una cassetta postale inattiva in Office 365. A tale scopo, specificare il GUID della cassetta postale inattiva nel `Mailbox` parametro nel file di mapping di importazione PST. Per informazioni, vedere il passaggio 4 della scheda **istruzioni** di questo argomento. 
    
- In una distribuzione ibrida di Exchange, è possibile importare i file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è in locale. A tale scopo, eseguire le operazioni seguenti nel file di mapping di importazione PST:
    
  - Specificare l'indirizzo di posta elettronica per la cassetta postale locale dell'utente nel `Mailbox` parametro. 
    
  - Specificare il valore **true** nel `IsArchive` parametro. 
    
    Per ulteriori informazioni, vedere [passaggio 4](#step-4-create-the-pst-import-mapping-file) . 
    
- Dopo aver importato i file PST in una cassetta postale di Office 365, l'impostazione di conservazione per la cassetta postale è attivata per una durata indefinita. Questo significa che i criteri di conservazione assegnati alla cassetta postale non verranno elaborati fino a quando non si disattiva il blocco di conservazione o si imposta una data per disattivare il blocco. Perché eseguire questa operazione? Se i messaggi importati in una cassetta postale sono obsoleti, potrebbero essere eliminati definitivamente (eliminati) perché il periodo di conservazione è scaduto in base alle impostazioni di conservazione configurate per la cassetta postale. Se si posiziona la cassetta postale su conservazione, il proprietario della cassetta postale consentirà di gestire i messaggi appena importati o di modificare le impostazioni di conservazione per la cassetta postale. Per suggerimenti sulla gestione del blocco di conservazione, vedere la scheda **altre informazioni** in questo argomento. 
    
- Per impostazione predefinita, le dimensioni massime dei messaggi che possono essere ricevute da una cassetta postale di Office 365 sono 35 MB. Ciò è dovuto al fatto che il valore predefinito per la proprietà *MaxReceiveSize* di una cassetta postale è impostato su 35 MB. Tuttavia, il limite per la dimensione massima di ricezione dei messaggi in Office 365 è 150 MB. Pertanto, se si importa un file PST che contiene un elemento di dimensioni superiori a 35 MB, il servizio di importazione di Office 365 modificherà automaticamente il valore della proprietà *MaxReceiveSize* nella cassetta postale di destinazione a 150 MB. In questo modo i messaggi fino a 150 MB verranno importati nelle cassette postali degli utenti. 
    
    > [!TIP]
    > Per identificare le dimensioni di ricezione dei messaggi per una cassetta postale, è possibile eseguire questo comando in PowerShell `Get-Mailbox <user mailbox> | FL MaxReceiveSize`di Exchange Online:. 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>Passaggio 1: copiare l'URL SAS e installare AzCopy di Azure

Il primo passaggio consiste nel scaricare e installare lo strumento di AzCopy di Azure, che è lo strumento che verrà eseguito nel passaggio 2 per caricare i file PST in Office 365. È inoltre possibile copiare l'URL SAS per la propria organizzazione. Questo URL è una combinazione dell'URL di rete per la posizione di archiviazione di Azure nel cloud Microsoft per l'organizzazione e una chiave di firma di accesso condiviso (SAS). Questa chiave fornisce le autorizzazioni necessarie per caricare i file PST nel percorso di archiviazione di Azure. Assicurarsi di prendere precauzioni per proteggere l'URL SAS. È univoco per l'organizzazione e verrà utilizzato nel passaggio 2.

> [!IMPORTANT]
> Per importare i file PST utilizzando il metodo di caricamento di rete, si consiglia di utilizzare la versione di Azure AzCopy che può essere scaricata nel passaggio 6b nella procedura seguente.
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore nell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro del Centro sicurezza & Compliance fare clic su \> **importazione**di **governance dei dati** .
    
    > [!NOTE]
    > È necessario disporre delle autorizzazioni appropriate per accedere alla pagina di **importazione** nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere la sezione **prima di iniziare** . 
    
3. Nella pagina **Importa** , fare clic ![su Aggiungi](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
    Viene visualizzata la procedura guidata di importazione.
    
4. Digitare un nome per il processo di importazione PST e quindi fare clic su **Avanti**. Utilizzare lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella pagina **si desidera caricare o spedire dati?** , fare clic su **carica i dati** e quindi su **Avanti**.
    
    ![Fare clic su carica i dati per creare un processo di importazione caricamento di rete](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Nella pagina **Importa dati** eseguire le due operazioni seguenti: 
    
    ![Copiare l'URL SAS e scaricare lo strumento di AzCopy di Azure nella pagina Importa dati](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    un. Nel passaggio 2, fare clic su **Mostra URL SAS caricamento di rete**. Dopo aver visualizzato l'URL SAS, fare clic su **copia negli Appunti** e quindi incollarlo e salvarlo in un file in modo che sia possibile accedervi in un secondo momento.
    
    b. Nel passaggio 3, fare clic su **Scarica Azure AzCopy** per scaricare e installare lo strumento di AzCopy di Azure. Nella finestra popup, fare clic su **Esegui** per installare AzCopy. 
    
> [!NOTE]
> È possibile lasciare la pagina **Importa dati** aperta (se è necessario copiare di nuovo l'URL SAS) oppure fare clic su **Annulla** per chiuderla. 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>Passaggio 2: caricare i file PST in Office 365

A questo punto, è possibile utilizzare lo strumento AzCopy. exe per caricare i file PST in Office 365. Questo strumento li carica e li archivia in una posizione di archiviazione di Azure nel cloud Microsoft. Come spiegato in precedenza, il percorso di archiviazione di Azure in cui si caricano i file PST risiede nello stesso datacenter Microsoft regionale in cui si trova l'organizzazione di Office 365. Per completare questo passaggio, è necessario che i file PST siano posizionati in una condivisione file o in un file server dell'organizzazione. In questa procedura, tale posizione viene definita anche come directory di origine. Ogni volta che si esegue lo strumento AzCopy, è possibile specificare una directory di origine diversa. 
  
1. Aprire un prompt dei comandi nel computer locale.
    
2. Accedere alla directory nella quale è stato installato lo strumento AzCopy.exe durante il primo passaggio. Se lo strumento è stato installato nel percorso predefinito, passare a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.
    
3. Eseguire il seguente comando per caricare i file PST in Office 365.

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > È necessario specificare una directory come percorso di origine nel comando precedente. non è possibile specificare un singolo file PST. Tutti i file PST nella directory di origine verranno caricati.
 
    Nella tabella seguente vengono descritti i parametri di AzCopy. exe e i relativi valori necessari. Le informazioni ottenute nel passaggio precedente vengono utilizzate nei valori di questi parametri.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Specifica la directory di origine nell'organizzazione che contiene i file PST che verranno caricati in Office 365.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Specifica l'URL SAS ottenuto nel passaggio 1.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> **Suggerimento:** Optional È possibile specificare una sottocartella nel percorso di archiviazione di Azure in cui caricare i file PST. A tale scopo, aggiungere un percorso di sottocartella (dopo "ingestiondata") nell'URL SAS. Nel primo esempio non viene specificata una sottocartella. Questo significa che il PST verrà caricato nella radice (denominata *ingestiondata* ) del percorso di archiviazione di Azure. Nel secondo esempio vengono caricati i file PST in una sottocartella (denominata *PSTFiles* ) nella radice del percorso di archiviazione di Azure.  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> Oppure  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Produce messaggi di stato dettagliati in un file di registro. Per impostazione predefinita, il file di registro dettagliato è denominato AzCopyVerbose.log in %LocalAppData%\Microsoft\Azure\AzCopy. Se si specifica il percorso di un file esistente per questa opzione, il registro dettagliato verrà aggiunto a tale file.  <br/> Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Questa opzione opzionale consente di specificare la modalità ricorsiva in modo che lo strumento AzCopy copierà i file PST che si trovano in sottocartelle nella directory di origine specificata dal `/Source:` parametro.  <br/> **Nota:** Se si include questo parametro, i file PST nelle sottocartelle avranno un percorso di file diverso nel percorso di archiviazione di Azure dopo che sono stati caricati. È necessario specificare il percorso del file esatto nel file CSV creato nel passaggio 4.  <br/> | `/S` <br/> |
    | `/Y` <br/> |Questa opzione necessaria consente l'utilizzo di token SAS di sola scrittura quando si caricano i file PST nel percorso di archiviazione di Azure. L'URL SAS ottenuto nel passaggio 1 (e specificato in `/Dest:` parameter) è un URL SAS di sola scrittura, che è il motivo per cui è necessario includere questa opzione. Si noti che un URL SAS di sola scrittura non impedirà l'utilizzo di Azure Storage Explorer per visualizzare un elenco dei file PST caricati nel percorso di archiviazione di Azure.  <br/> | `/Y` <br/> |
   
Di seguito è riportato un esempio di sintassi dello strumento AzCopy.exe nella quale verranno utilizzati i valori effettivi di ogni parametro:
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

Una volta eseguito il comando, i messaggi di stato visualizzati riportano informazioni sull'avanzamento del caricamento dei file PST. Nel messaggio finale viene riportato il numero complessivo di file che sono stati caricati. 

> [!TIP]
> Dopo aver eseguito correttamente il comando AzCopy. exe e aver verificato che tutti i parametri siano corretti, salvare una copia della sintassi della riga di comando nello stesso file (protetto) in cui sono state copiate le informazioni ottenute nel passaggio 1. È quindi possibile copiare e incollare il comando in un prompt dei comandi ogni volta che si desidera eseguire lo strumento AzCopy. exe per caricare i file PST in Office 365. L'unico valore che potrebbe essere necessario modificare sono quelli per il `/Source:` parametro. Ciò dipende dalla directory di origine nella quale si trovano i file PST.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Optional Passaggio 3: visualizzare un elenco dei file PST caricati in Office 365

Come passaggio facoltativo, è possibile installare e utilizzare Microsoft Azure Storage Explorer (che è uno strumento gratuito open source) per visualizzare l'elenco dei file PST caricati nel BLOB di Azure. Esistono due validi motivi per eseguire questa operazione:
  
- Verificare che i file PST dalla cartella condivisa o dal server di file dell'organizzazione siano stati correttamente caricati nel BLOB di Azure.
    
- Verificare il nome del file (e il percorso della sottocartella se ne è stato incluso uno) per ognuno di essi. Ciò è particolarmente utile quando si crea il file di mapping PST nel passaggio successivo poiché è necessario specificare sia il nome del file sia il percorso della cartella per ogni file PST. La verifica di questi nomi consente di ridurre i potenziali errori nel file di mapping PST.
    
Microsoft Azure Storage Explorer è in anteprima.
  
> [!IMPORTANT]
> Non è possibile utilizzare l'esploratore di archiviazione di Azure per caricare o modificare i file PST. L'unico metodo supportato per l'importazione di file PST in Office 365 è l'utilizzo di AzCopy. Inoltre, non è possibile eliminare i file PST caricati nel BLOB di Azure. Se si tenta di eliminare un file PST, si riceve un errore relativo all'assenza delle autorizzazioni necessarie. Tenere presente che tutti i file PST vengono eliminati automaticamente dall'area di archiviazione di Azure. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.
  
Per installare Azure Storage Explorer e connettersi all'area di archiviazione di Azure:
  
1. Scaricare e installare lo [strumento Microsoft Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Avviare Microsoft Azure Storage Explorer, fare clic con il pulsante destro del mouse su **account di archiviazione** nel riquadro sinistro, quindi fare clic su **Connetti a spazio di archiviazione di Azure**.
    
    ![Fare clic con il pulsante destro del mouse su account di archiviazione e quindi scegliere Connetti a archiviazione](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Fare clic su **Usa una stringa di connessione o un URI di accesso condiviso** e fare clic su **Avanti**.
    
4. Fare clic su **Usa un URI SAS**, incollare l'URL SAS ottenuto nel passaggio 1 nella casella in **URI**, quindi fare clic su **Avanti**.
    
5. Nella pagina **Riepilogo connessione** è possibile esaminare le informazioni sulla connessione e quindi fare clic su **Connetti**.
    
    Il contenitore **ingestiondata** viene aperto. contiene i file PST caricati nel passaggio 2. Il contenitore di **ingestiondata** si trova in **contenitori BLOB**degli **account** \> di archiviazione **(SAS-Attached Services)** \> . 
    
    ![Esplora archivi di Azure mostra un elenco di file con estensione PST caricati](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Al termine dell'utilizzo di Microsoft Azure Storage Explorer, fare clic con il pulsante destro del mouse su **** **ingestiondata**e quindi scegliere Disconnetti per disconnettersi dall'area di archiviazione di Azure. In caso contrario, verrà visualizzato un errore al successivo tentativo di associazione. 
    
    ![Fare clic con il pulsante destro del mouse sull’inserimento e su Disconnetti per disconnettersi dall'area di archiviazione Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Passaggio 4: creare il file di mapping di importazione PST

Dopo aver caricato i file PST nel percorso di archiviazione di Azure per l'organizzazione di Office 365, il passaggio successivo consiste nel creare un file con valori delimitati da virgole (CSV) che specifichi le cassette postali degli utenti a cui verranno importati i file PST. Questo file CSV verrà inviato al passaggio successivo quando si crea un processo di importazione PST.
  
1. [Scaricare una copia del file di mapping di importazione PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
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

   **Nota:** Non modificare alcuna operazione nella riga di intestazione, inclusi i parametri di SharePoint. verranno ignorate durante il processo di importazione PST. 

 3. Utilizzare le informazioni della tabella per popolare il file CSV con i dati necessari.


    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Specifica il servizio Office 365 in cui verranno importati i dati. Per importare i file PST nelle cassette postali `Exchange`degli utenti, utilizzare.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Specifica il percorso della cartella nel percorso di archiviazione di Azure in cui sono stati caricati i file PST nel passaggio 2.  <br/> Se non è stato incluso un nome di sottocartella facoltativo nell'URL SAS nel `/Dest:` parametro del passaggio 2, lasciare vuoto questo parametro nel file CSV. Se è stato incluso un nome di sottocartella, specificarlo in questo parametro (vedere il secondo esempio). Il valore di questo parametro è distinzione tra maiuscole e minuscole.  <br/> In entrambi i casi, *non* includere "ingestiondata" nel valore del `FilePath` parametro.  <br/><br/> **Importante:** La distinzione tra maiuscole e minuscole per il nome del percorso del file deve corrispondere a quella utilizzata se è stato incluso un nome di sottocartella facoltativo `/Dest:` nell'URL SAS nel parametro del passaggio 2. Ad esempio, se si utilizza `PSTFiles` il nome della sottocartella nel passaggio 2 e quindi si `pstfiles` utilizza il `FilePath` parametro nel file CSV, l'importazione del file PST avrà esito negativo. Assicurarsi di utilizzare lo stesso caso in entrambe le istanze.  <br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Specifica il nome del file PST che verrà importato nella cassetta postale.  Il valore di questo parametro è distinzione tra maiuscole e minuscole.  <br/> <br/>**Importante:** Il caso del nome del file PST nel file CSV deve corrispondere al file PST caricato nel percorso di archiviazione di Azure nel passaggio 2. Ad esempio, se si utilizza `annb.pst` il `Name` parametro nel file CSV, ma il nome del file pst effettivo è `AnnB.pst`, l'importazione per il file PST avrà esito negativo. Assicurarsi che il nome del file PST nel documento CSV utilizzi lo stesso caso del file PST effettivo.  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Specifica l'indirizzo di posta elettronica della cassetta postale nella quale verrà importato il file PST.  Non è possibile specificare una cartella pubblica perché il servizio di importazione PST non supporta l'importazione di file PST nelle cartelle pubbliche.  <br/> Per importare un file PST in una cassetta postale inattiva, è necessario specificare il GUID della cassetta postale per questo parametro. Per ottenere questo GUID, eseguire il seguente comando di PowerShell in Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**Nota:** In alcuni casi, è possibile disporre di più cassette postali con lo stesso indirizzo di posta elettronica, in cui una cassetta postale è una cassetta postale attiva e l'altra è in uno stato di eliminazione temporanea (o inattivo). In questi casi, è necessario specificare il GUID della cassetta postale per identificare in modo univoco la cassetta postale in cui importare il file PST. Per ottenere questo GUID per le cassette postali attive, eseguire il seguente `Get-Mailbox <identity of active mailbox> | FL Guid`comando di PowerShell:. Per ottenere il GUID per le cassette postali eliminate temporaneamente (o inattive), `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`eseguire questo comando.  <br/> | `annb@contoso.onmicrosoft.com` <br/> Oppure  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Specifica se importare o meno il file PST nella cassetta postale di archiviazione dell'utente. Esistono due opzioni:  <br/><br/>**False** -importa il file PST nella cassetta postale principale dell'utente.  <br/> **True** : consente di importare il file PST nella cassetta postale di archiviazione dell'utente. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). <br/><br/>Se si imposta questo parametro su `TRUE` e la cassetta postale di archiviazione dell'utente non è abilitata, l'importazione per tale utente avrà esito negativo. Si noti che se un'importazione ha esito negativo per un utente (perché l'archivio non è abilitato e `TRUE`la proprietà è impostata su), gli altri utenti nel processo di importazione non saranno coinvolti.  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/> <br/>**Nota:** Per importare un file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è in locale `TRUE` , specificare solo per questo parametro e specificare l'indirizzo di posta elettronica per la cassetta postale locale `Mailbox` dell'utente per il parametro.  <br/> | `FALSE` <br/> Oppure  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Specifica la cartella delle cassette postali a cui è stato importato il file PST.  <br/>  Se si omette questo parametro, il file PST verrà importato in una nuova cartella **** denominata importata che si trova a livello di radice della cassetta postale (allo stesso livello della cartella posta in arrivo e delle altre cartelle di cassette postali predefinite).  <br/>  Se si specifica `/`, gli elementi del file pst verranno importati direttamente nella cartella posta in arrivo dell'utente.  <br/><br/>  Se si specifica `/<foldername>`, gli elementi del file pst verranno importati in una cartella denominata * \<\> FolderName* . Ad esempio, se si utilizza `/ImportedPst`, gli elementi verrebbero importati in una cartella denominata **ImportedPst**. Questa cartella si trova nella cassetta postale dell'utente allo stesso livello della cartella posta in arrivo.  <br/><br/> **Suggerimento:** Valutare l'esecuzione di alcuni batch di test per sperimentare questo parametro in modo da poter determinare il percorso della cartella migliore in cui importare i file di PST.  <br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `/` <br/> Oppure  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Questo parametro facoltativo consente di specificare un valore numerico per la tabella codici da utilizzare per l'importazione dei file PST nel formato di file ANSI. Questo parametro viene utilizzato per l'importazione di file PST dalle organizzazioni cinesi, giapponesi e coreane (CJK), in quanto generalmente utilizzano un set di caratteri a doppio byte (DBCS) per la codifica dei caratteri. Se questo parametro non viene utilizzato per importare i file PST per le lingue che utilizzano i caratteri DBCS per i nomi delle cartelle delle cassette postali, i nomi delle cartelle vengono spesso alterati dopo l'importazione.  <br/><br/> Per un elenco dei valori supportati da utilizzare per questo parametro, vedere [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> <br/>**Nota:** Come indicato in precedenza, si tratta di un parametro facoltativo e non è necessario includerlo nel file CSV. In alternativa, è possibile includerla e lasciare il valore vuoto per una o più righe.  <br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `932` (ovvero l'identificatore di tabella codici per ANSI/OEM giapponese)  <br/> |
    | `SPFileContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPManifestContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPSiteUrl` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>Passaggio 5: creare un processo di importazione PST in Office 365

Il passaggio successivo consiste nel creare il processo di importazione PST nel servizio di importazione di Office 365. Come spiegato in precedenza, si invierà il file di mapping di importazione PST creato nel passaggio 4. Dopo aver creato il nuovo processo, Office 365 analizza i dati nei file PST e quindi offre la possibilità di filtrare i dati che vengono effettivamente importati nelle cassette postali specificate nel file di mapping di importazione PST (vedere il [passaggio 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore nell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro del Centro sicurezza & Compliance fare clic su **governaNce dei dati** e quindi fare clic su **Importa**.
    
3. Nella pagina **Importa** , fare clic ![su Aggiungi](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
    **Nota:** Per creare un nuovo processo di importazione, è necessario disporre delle autorizzazioni appropriate per accedere alla pagina di **importazione** nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere la sezione **prima di iniziare** . 
    
4. Digitare un nome per il processo di importazione PST e quindi fare clic su **Avanti**. Utilizzare lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella pagina **si desidera caricare o spedire dati?** , fare clic su **carica i dati** e quindi su **Avanti**.
    
    ![Fare clic su carica i dati per creare un processo di importazione caricamento di rete](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Nel passaggio 4 della pagina **Importa dati** fare clic sul **caricamento dei file** e ho **accesso al file di mapping** , quindi fare clic su **Avanti**.
    
    ![Fare clic sulle due caselle di controllo nel passaggio 4.](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. Nella pagina **selezionare il file di mapping** fare clic su **Seleziona file di mapping** per inviare il file di mapping di importazione PST creato nel passaggio 4. 
    
    ![Fare clic su Seleziona file di mapping per inviare il file CSV creato per il processo di importazione](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Dopo che il nome del file CSV viene visualizzato in **mapping file name**, fare clic su **Validate** per controllare il file CSV per individuare eventuali errori. 
    
    ![Fare clic su convalida per controllare il file CSV per individuare eventuali errori](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Il file CSV deve essere convalidato per creare un processo di importazione PST. Nota il nome del file viene modificato in verde dopo che è stato convalidato correttamente. Se la convalida ha esito negativo, fare clic sul collegamento **Visualizza log** . Viene aperta una segnalazione errori di convalida, con un messaggio di errore per ogni riga del file che ha avuto esito negativo. 
    
9. Dopo che il file di mapping PST è stato convalidato, leggere il documento termini e condizioni e quindi fare clic sulla casella di controllo.
    
10. Fare clic su **Salva** per inviare il processo e quindi fare clic su **Chiudi** dopo che il processo è stato creato correttamente. 
    
    Viene visualizzata una pagina con lo stato dell' **analisi in corso** e il nuovo processo di importazione viene visualizzato nell'elenco nella pagina **Importa** . 
    
11. Fare clic su Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) l'icona Aggiorna per aggiornare le informazioni sullo stato visualizzate nella colonna **stato** . **** ![ Al termine dell'analisi e i dati sono pronti per l'importazione, lo stato viene modificato in **analisi completata**.
    
    È possibile fare clic sul processo di importazione per visualizzare la pagina del riquadro a comparsa di stato, che contiene informazioni più dettagliate sul processo di importazione, ad esempio lo stato di ogni file PST elencato nel file di mapping.
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Passaggio 6: filtrare i dati e avviare il processo di importazione PST

Dopo aver creato il processo di importazione nel passaggio 5, Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) identificando l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST. Al termine dell'analisi e i dati sono pronti per l'importazione, si ha la possibilità di importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando filtri che controllano quali dati vengono importati.
  
1. Nella pagina **Importa** del Centro sicurezza & Compliance fare clic su **pronto per l'importazione in Office 365** per il processo di importazione creato nel passaggio 5. 
    
    ![Fare clic su pronto per l'importazione in Office 365 accanto al processo di importazione creato](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Viene visualizzata una pagina di volo con informazioni sui file PST e altre informazioni sul processo di importazione.
    
2. Nella pagina riquadro a comparsa, fare clic su **Importa in Office 365**.
    
    Viene visualizzata la pagina filtro per i **dati** . Contiene i dati relativi alle informazioni risultanti dall'analisi eseguita sui file PST da Office 365, incluse quelle relative all'età dei dati. A questo punto, si ha la possibilità di filtrare i dati che verranno importati o importare tutti i dati così come sono. 
    
    ![È possibile tagliare i dati nei file PST o importarli tutti](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Eseguire una delle operazioni seguenti:
    
    un. Per tagliare i dati importati, fare clic su **Sì, voglio filtrarlo prima**di eseguire l'importazione.
    
    Per istruzioni dettagliate su come filtrare i dati nei file PST e avviare il processo di importazione, vedere [filtrare i dati quando si importano i file PST in Office 365](filter-data-when-importing-pst-files.md).
    
    Oppure
    
    b. Per importare tutti i dati nei file PST, fare clic su **No, voglio importare tutto** e fare clic su **Avanti**.
    
4. Se si è scelto di importare tutti i dati, fare clic su **Importa dati** per avviare il processo di importazione. 
    
    Lo stato del processo di importazione è visualizzato nella pagina **Importa** . Fare ![clic su](media/O365-MDM-Policy-RefreshIcon.gif) **** aggiorna icona Aggiorna per aggiornare le informazioni sullo stato visualizzate nella colonna **stato** . Fare clic sul processo di importazione per visualizzare la pagina del riquadro a comparsa di stato, in cui vengono visualizzate le informazioni sullo stato di ogni file PST da importare. 

## <a name="how-the-import-process-works"></a>Funzionamento del processo di importazione
  
È possibile utilizzare l'opzione caricamento di rete e il servizio di importazione di Office 365 per importare in blocco i file PST nelle cassette postali degli utenti. Caricamento di rete significa che si caricano i file PST un'area di archiviazione temporanea nel cloud Microsoft. Successivamente, il servizio di importazione di Office 365 copia i file PST dall'area di archiviazione nelle cassette postali degli utenti di destinazione.
  
Ecco un'illustrazione e una descrizione del processo di caricamento di rete per importare i file PST nelle cassette postali in Office 365.
  
![Flusso di lavoro del processo di caricamento di rete per importare i file PST in Office 365](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Scaricare lo strumento di importazione PST e la chiave per la posizione di archiviazione di Azure privata** -il primo passaggio consiste nel scaricare lo strumento da riga di comando di Azure AzCopy e un tasto di accesso utilizzato per caricare i file PST in una posizione di archiviazione di Azure nel cloud Microsoft. Tali dati vengono ottenuti dalla pagina **Importa** del Centro sicurezza & Compliance. La chiave, denominata chiave SAS (Secure Access Signature), fornisce le autorizzazioni necessarie per caricare i file PST in una posizione di archiviazione privata e protetta di Azure. Questo tasto di accesso è univoco per l'organizzazione e consente di impedire l'accesso non autorizzato ai file PST dopo che sono stati caricati nel cloud Microsoft. Si noti che l'importazione di file PST in Office 365 non richiede che l'organizzazione disponga di una sottoscrizione di Azure distinta. 
    
2. **Caricare i file pst nel percorso di archiviazione di Azure** -il passaggio successivo consiste nell'utilizzare lo strumento AzCopy. exe (scaricato nel passaggio 1) per caricare e archiviare i file PST in una posizione di archiviazione di Azure che risiede nello stesso datacenter Microsoft regionale in cui Office 365 l'organizzazione si trova. Per caricarli, i file PST che si desidera importare in Office 365 devono trovarsi in una condivisione file o in un file server nell'organizzazione.
    
    Si noti che è disponibile un passaggio facoltativo che è possibile eseguire per visualizzare l'elenco dei file PST dopo essere stati caricati nel percorso di archiviazione di Azure.
    
3. **Creare un file di mapping di importazione PST** -dopo che i file PST sono stati caricati nel percorso di archiviazione di Azure, il passaggio successivo consiste nel creare un file con valori delimitati da virgole (CSV) che specifichi le cassette postali degli utenti a cui verranno importati i file PST, si noti che un file PST può essere  importato nella cassetta postale principale o nella cassetta postale di archiviazione di un utente. Il servizio di importazione di Office 365 utilizzerà le informazioni contenute nel file CSV per importare i file PST.
    
4. **Creare un processo di importazione PST** -il passaggio successivo consiste nel creare un processo di importazione PST nella pagina **Importa** del centro conformità & sicurezza e nel inviare il file di mapping di importazione PST creato nel passaggio precedente. Dopo aver creato il processo di importazione, Office 365 analizza i dati nei file PST e quindi consente di impostare filtri che controllano quali dati vengono effettivamente importati nelle cassette postali specificate nel file di mapping di importazione PST. 
    
5. **Filtrare i dati pst che verranno** importati nelle cassette postali-dopo la creazione e l'avvio del processo di importazione, Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) identificando l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST . Al termine dell'analisi e i dati sono pronti per l'importazione, si ha la possibilità di importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando filtri che controllano quali dati vengono importati.
    
6. **Avviare il processo di importazione PST** -dopo l'avvio del processo di importazione, Office 365 utilizza le informazioni contenute nel file di mapping di importazione PST per importare i file di PST dal percorso di archiviazione di Azure alle cassette postali degli utenti. Le informazioni sullo stato relative al processo di importazione (incluse le informazioni su ogni file PST importato) vengono visualizzate nella pagina **Importa** del Centro sicurezza & Compliance. Al termine del processo di importazione, lo stato del processo è impostato su **completo**.
  
## <a name="more-information"></a>Altre informazioni

- Perché importare i file PST in Office 365?
    
  - È un ottimo modo per importare i dati della messaggistica di archiviazione dell'organizzazione in Office 365.
    
  - I dati sono disponibili per l'utente da tutti i dispositivi in quanto vengono memorizzati nel cloud.
    
  - Aiuta a soddisfare le esigenze di conformità dell'organizzazione, consentendo di applicare le funzionalità di conformità di Office 365 ai dati dei file PST importati. Ciò include:
    
  - Abilitazione delle [cassette postali](enable-archive-mailboxes.md) di archiviazione e dell' [archiviazione automatica](enable-unlimited-archiving.md) per consentire agli utenti un ulteriore spazio di archiviazione delle cassette postali per archiviare i dati importati. 
    
  - Archiviazione delle cassette postali sul [blocco per controversIa legale](https://go.microsoft.com/fwlink/?linkid=856286) per mantenere i dati importati. 
    
  - Utilizzo [degli strumenti](search-for-content.md) di Microsoft eDiscovery per cercare i dati importati. 
    
  - Utilizzo dei [criteri di conservazione di Office 365](retention-policies.md) per controllare la durata del mantenimento e l'azione da eseguire dopo la scadenza del periodo di conservazione. 
    
  - Ricerca nel [Registro di controllo di Office 365](search-the-audit-log-in-security-and-compliance.md) per gli eventi relativi alle cassette postali che influiscono sui dati importati. 
    
  - Importazione di dati in [cassette postali inattive](create-and-manage-inactive-mailboxes.md) per l'archiviazione dei dati a fini di conformità. 
    
  - Utilizzo [dei criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md) per impedire la fuoriuscita di dati sensibili all'esterno dell'organizzazione. 
  
- Di seguito è riportato un esempio dell'URL della firma di accesso condiviso (SAS) ottenuto nel passaggio 1. In questo esempio viene inoltre contenuta la sintassi del comando eseguito nello strumento AzCopy. exe per caricare i file PST in Office 365. Assicuratevi di prendere precauzioni per proteggere l'URL SAS come si farebbe per proteggere le password o altre informazioni relative alla sicurezza.

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
    
