---
title: Utilizzare lo strumento PST raccolta per trovare, copiare ed eliminare i file PST all'interno dell'organizzazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Utilizzare lo strumento di raccolta PST Microsoft per la ricerca della rete dell'organizzazione per ottenere un inventario dei file PST sparsi in tutta l'organizzazione. Dopo aver individuato file PST, è possibile utilizzare lo strumento di raccolta di file PST da copiare in una posizione centrale in modo che è possibile importarli a Office 365.
ms.openlocfilehash: 183ab968b894c824f2b23c08e98e671ef85316cc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530746"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>Utilizzare lo strumento PST raccolta per trovare, copiare ed eliminare i file PST all'interno dell'organizzazione

È possibile utilizzare lo strumento Microsoft PST raccolta per la ricerca della rete dell'organizzazione per i file PST. Lo strumento consente di ottenere un inventario dei file PST sparsi in tutta l'organizzazione. Dopo aver individuato file PST, è possibile utilizzare lo strumento PST insieme a copiarli in una posizione centrale. La presenza di file pst in un'unica posizione quindi consente di importare loro di cassette postali Exchange Online (o una singola cassetta postale di Exchange Online), dove è quindi possibile applicare l'ampia gamma di funzionalità di conformità in Office 365. Include l'importazione di file pst in archivio contiene le cassette postali, la ricerca dei messaggi specifici nei file PST che è stato importato utilizzando gli strumenti di ricerca di eDiscovery, conservazione dei messaggi tramite eDiscovery degli utenti e i criteri di conservazione Office 365 e la gestione di tutta la durata ciclo di questi messaggi tramite la messaggistica consente di registrare le funzionalità di gestione di Exchange Online. Se si è certi che i file PST che raccolti aver importato correttamente a Office 365, è possibile utilizzare lo strumento di eliminarli dai rispettivi percorsi originali nella rete. 
  
In alternativa che è possibile eseguire con lo strumento PST raccolta è impedire agli utenti di creare nuovi file PST e la modifica dei file PST esistenti che trova nella rete. Tali funzionalità "bloccare" consentono di trovare, raccogliere e importare un set di file PST noto a Office 365 e impedire la proliferazione futura dei file PST all'interno dell'organizzazione. 
  
## <a name="how-the-pst-collection-tool-works"></a>Come funziona lo strumento PST raccolta

Ecco una rapida panoramica del processo di utilizzando lo strumento PST insieme trovare, controllare, raccogliere ed eliminare i file PST all'interno dell'organizzazione.
  
![Panoramica del processo di strumento PST insieme](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[Passaggio 1: individuazione dei file PST nella rete](#step-1-find-pst-files-on-your-network)** - quando si esegue lo strumento per trovare i file PST, si specifica un percorso, ad esempio un'unità organizzativa che contiene gli oggetti di Active Directory per i computer client e server. È inoltre possibile cercare computer specifici o condivisioni di file di rete. Quando si esegue lo strumento, una "leggero" insieme che viene installato nei computer di destinazione. L'agente Cerca computer di destinazione per i file PST e quindi invia informazioni allo strumento PST raccolta su qualsiasi file PST individuato. Lo strumento crea i file di registro che contiene informazioni sui file PST rilevati nei percorsi specificati. Questi file vengono utilizzati quando si esegue lo strumento nei passaggi successivi. 
    
2. **[(Facoltativo) passaggio 2: controllare l'accesso ai file PST](#optional-step-2-control-access-to-pst-files)** -lo strumento crea un oggetto Criteri di gruppo (GPO) con le impostazioni che impedisce agli utenti di creare o modificare i file PST. Questo oggetto Criteri di gruppo viene applicato a tutti gli utenti nel dominio. Questo passaggio facoltativo consente di "bloccare" i file PST che sono state trovate nel passaggio 1 in modo che è possibile raccogliere, importare ed eliminarli senza la necessità di nuovi file PST creati o modificati i file PST esistenti. 
    
3. **[Passaggio 3: copiare i file PST in un percorso raccolta](#step-3-copy-the-pst-files-to-a-collection-location)** -consente di raccogliere i file PST in un'unica posizione, in modo che è possibile importarli alle cassette postali di Exchange Online tramite il servizio Office 365 importare nel passaggio 4. Quando si esegue lo strumento in modalità "raccogliere", ogni agente insieme copia i file PST dal computer di destinazione che è installato l'agente al percorso raccolta. 
    
4. **[Passaggio 4: importare i file PST in Office 365](#step-4-import-the-pst-files-to-office-365)** -dopo aver copiato i file PST in un percorso, si è pronti per importarli alle cassette postali di Exchange Online. 
    
5. **[Passaggio 5: Elimina i file PST trovati nella rete](#step-5-delete-the-pst-files-found-on-your-network)** - dopo che i file PST di file che è stato individuato e raccolti sono stati importati alle cassette postali di Exchange Online in Office 365, è possibile utilizzare lo strumento PST raccolta per eliminare i file PST da posizioni originale in cui sono state trovate nel passaggio 1. 

## <a name="before-you-begin"></a>Informazioni preliminari

- Eseguire la procedura seguente per scaricare lo strumento PST raccolta nel computer locale. 
    
    1. [Scaricare lo strumento PST insieme](https://aka.ms/pstcollectiontool).
    
    2. Nella finestra popup, fare clic su **Salva** \> **Salva** per salvare il file PSTCollectionTool.zip in una cartella nel computer locale. 
    
    3. Estrarre il file PSTCollectionTool.zip in una cartella nel computer locale. il nome della cartella predefinita è PSTCollectionTool.
    
- Per eseguire lo strumento PST raccolta in qualsiasi modalità (Find, blocca, copia o eliminazione), è necessario essere membri del gruppo Domain Admins nel dominio di Active Directory. 

## <a name="step-1-find-pst-files-on-your-network"></a>Passaggio 1: Individuazione dei file PST nella rete

Il primo passaggio consiste nell'eseguire lo strumento PST raccolta per trovare i file PST all'interno dell'organizzazione. È possibile utilizzare lo strumento ricerca i seguenti tipi di percorsi. 
  
- Unità organizzative (OU) in un dominio di Active Directory locale. Lo strumento Cerca in tutti i computer contenuti dell'unità Organizzativa specificata. 
    
- Computer client e server. Lo strumento ricerca i computer specificati. 
    
- Condivisioni di rete. Lo strumento ricerca le condivisioni di file di rete specificata. 
    
Vedere la descrizione per il `Locations` parametro nella tabella nella procedura seguente per alcuni esempi di sintassi da utilizzare per ognuno di questi tipi di posizione. 
  
> [!IMPORTANT]
> È necessario Esegui lo strumento PST raccolta in modalità trova prima di poter eseguire altre operazioni, ad esempio il blocco, la raccolta o eliminare i file PST. 
  
1. Aprire un prompt dei comandi (Esegui come amministratore) nel computer locale.
    
2. Passare alla cartella PSTCollectionTool (o la cartella in cui sono stati estratti i file PSTCollectionTool.zip).
    
3. Passare alla directory DataCollectorMaster.
    
4. Eseguire il comando seguente per trovare i file PST in una posizione specificata.
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    Nella tabella seguente vengono descritti i parametri e i relativi valori necessari quando si esegue il comando DataCollectorMaster.exe per trovare i file PST. 
    
    |Parametro * * *|****Description****|Esempi * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Specifica il tipo di dati da cercare. Attualmente, è possibile utilizzare lo strumento PST raccolta per cercare i file PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Specifica il tipo di operazione verrà eseguita. Utilizzare il valore `Find` per individuare i file PST nei percorsi specificati. Si noti che lo strumento può individuare e ottenere informazioni sui file PST che sono aperte in file PST e Outlook connessi a profili di Outlook.<br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |Specifica il nome del processo di raccolta di file PST. Quando si esegue lo strumento PST insieme bloccare, raccogliere ed eliminare i file PST disponibili quando si esegue lo strumento per trovare i file PST, si utilizzeranno questo stesso nome del processo. Il nome del processo verrà aggiunto anche ai nomi di file registro e la configurazione.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | Specifica uno o più percorsi per cercare i file PST. Se si specifica più di una posizione, utilizzare un punto e virgola (;) per separare i singoli percorsi. È necessario racchiudere i singoli valori di questo parametro con virgolette doppie ("").<br/><br/>   Di seguito è riportato il formato di valore identity necessari per i tipi di percorsi che è possibile eseguire la ricerca.  <br/><br/>        **Unità organizzative** - utilizzare il nome distinto (DN) per identificare le unità organizzative; Per esempio:`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> Non è possibile specificare il contenitore computer incorporato (ad esempio, CN = Computers, DC = contoso, DC = com ") dal momento che non è un'unità organizzativa.<br/> <br/> **Macchine** - utilizzare il nome distinto o il nome di dominio completo (FQDN) per identificare i computer client e server nella rete. Per esempio:  <br/>  NOME DISTINTO:`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  Oppure  <br/>  FQDN:`"FILESERVER01.contoso.com"` <br/><br/>  **Condivisioni di file di rete** - utilizzare un nome UNC per identificare le condivisioni di file di rete; Per esempio`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |Specifica la cartella in cui verranno copiati i file di registro. Se la cartella non esiste, verrà creato quando si esegue lo strumento.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |Specifica la cartella in cui verrà copiato il file configuration. Xml. Questo file contiene informazioni su ogni file PST che si trova quando si esegue lo strumento. Questo file sarà utilizzato quando si esegue lo strumento nel passaggio 3 per copiare i file PST disponibili.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |Questo parametro opzionale specifica percorsi per ignorare la durante un'operazione di ricerca. È possibile escludere le unità organizzative specifiche, computer e condivisioni di file di rete. Ad esempio, è possibile escludere macchine, ad esempio computer configurato come un server SQL server (o altri tipi di server applicazioni), che gli utenti non dispongono dell'accesso a. Se si specifica più di una stessa posizione da escludere, utilizzare un punto e virgola (;) per separare i singoli percorsi. È necessario racchiudere i singoli valori di questo parametro con virgolette doppie ("").  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |Questo parametro opzionale consente di eseguire lo strumento in modalità di ricerca per un processo di raccolta PST esistente. Quando si utilizza il `ForceRestart` passare, i risultati dell'operazione di ricerca precedente per il processo verrà eliminato e lo strumento analizzerà nuovamente i percorsi specificati e creano nuovi file di registro e la configurazione.<br/> | `-ForceRestart` <br/> |
   
    Ecco un esempio di sintassi per il comando DataCollectorMaster.exe utilizzando i valori effettivi per ogni parametro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    Dopo aver eseguito il comando, vengono visualizzati messaggi di stato dettagliato che mostrano lo stato di avanzamento di individuazione file PST nei percorsi specificati. Dopo un po' di tempo, verrà visualizzato un messaggio di stato finale il numero totale di file PST che sono state trovate, se il processo è stato completato e se si sono verificati errori di. Il file di log vengono copiati gli stessi messaggi di stato.
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>Risultati dell'esecuzione DataCollectorMaster.exe nella modalità di ricerca

Dopo aver eseguito lo strumento PST raccolta la modalità di ricerca, i file seguenti vengono creati e memorizzati nelle cartelle specificate per il `LogLocation` e `ConfigurationLocation` parametri. 
  
- **\<Specificare nome di processo\>_trovare_\<DateTimeStamp\>. log** -il file di registro contiene i messaggi di stato che sono stati visualizzati. Questo file viene creato nella cartella specificata per il `LogLocation` parametro. 
    
- **\<Specificare nome di processo\>_trovare_\<DateTimeStamp\>. csv** -file CSV The contiene una riga per ogni file PST che è stato trovato. Le informazioni per ogni file PST includono i computer in cui è stato trovato il file PST, il percorso completo del file del file PST, il proprietario del file PST e la dimensione del file PST (in kilobyte, KB). Questo file viene creato nella cartella specificata per il `LogLocation` parametro. 
    
    > [!TIP]
    > Utilizzare lo strumento AutoSum in Excel per calcolare la dimensione totale (in KB) dei file PST elencati nel file CSV. Quindi è possibile utilizzare un calcolo di conversione per convertire le dimensioni totali in megabyte (MB) o gigabyte (GB). 
  
- **\<Specificare nome di processo\>_trovare_\<DateTimeStamp\>. XML** -il file XML contiene informazioni sui valori dei parametri del che dove utilizzato durante l'esecuzione dello strumento in modalità di ricerca. Questo file contiene inoltre informazioni su tutti i file PST che è stato trovato. I dati in questo file viene utilizzati quando si esegue eseguire di nuovo lo strumento per lo stesso processo di blocco, raccogliere o Elimina i file PST i file che sono stati rilevati. Questo file viene creato nella cartella specificata per il `ConfigurationLocation` parametro. 
    
    > [!IMPORTANT]
    > Non rinominare, modificare o spostare il file. Viene utilizzato per lo strumento PST raccolta quando eseguire di nuovo lo strumento in blocco, copia, o eliminare la modalità per lo stesso processo. 

## <a name="optional-step-2-control-access-to-pst-files"></a>(Facoltativo) Passaggio 2: Controllare l'accesso ai file PST

Consente di passaggio facoltativo è "bloccare" i file PST che sono state trovate nel passaggio 1 in modo che sia possibile raccogliere e importare un set di file PST noto a Office 365. Quando si esegue lo strumento PST raccolta nella modalità di blocco, eseguire le operazioni seguenti: 
  
- Lo strumento crea un oggetto di criteri di gruppo (GPO) denominata *Controlli relativi all'utilizzo PST* . Questo oggetto Criteri di gruppo è collegato al dominio e si applica a tutti gli utenti autenticati nell'organizzazione. 
    
- L'oggetto Criteri di gruppo controlli utilizzo PST crea le impostazioni del Registro di sistema sui computer all'interno dell'organizzazione. In base al parametro utilizzabile, è possibile creare un'impostazione del Registro di sistema per impedire agli utenti di creare nuovi file PST e un'impostazione del Registro di sistema che impedisce agli utenti di modificare i file PST esistenti.
    
> [!NOTE]
> Se il controllo dell'accesso ai file PST è troppo eccesso per l'organizzazione, è possibile ignorare questo passaggio ed eseguire il passaggio 3 per copiare i file PST in una posizione centrale. Quindi è possibile ripetere il passaggio 1 del processo stesso (utilizzando il `ForceRestart` parametro) per individuare i file del file pst aggiuntivi che sono stati creati dopo aver copiato i file pst nella posizione di raccolta. Se vengono rilevati nuovi file PST, è possibile copiare nel percorso della raccolta. Quando si utilizza il `ForceRestart` parametro quando si eseguita di nuovo lo strumento in modalità di ricerca, verranno eliminati i risultati da precedente operazione di ricerca di un processo e lo strumento analizza nuovamente i percorsi specificati. 

Per bloccare l'accesso ai file PST:

1. Aprire un prompt dei comandi (Esegui come amministratore) nel computer locale.
    
2. Passare alla directory in cui è stato scaricato lo strumento PST insieme a.
    
3. Eseguire il comando seguente per bloccare l'accesso ai file PST trovato nel passaggio 1.

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    Nella tabella seguente vengono descritti i parametri e i relativi valori necessari quando si esegue il comando DataCollectorMaster.exe per bloccare la creazione e modifica dei file PST. 
    
    |Parametro * * *|****Description****|Esempi * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Specifica il tipo di dati da cercare. Attualmente, è possibile utilizzare lo strumento PST raccolta per cercare i file PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Specifica il tipo di operazione verrà eseguita. Utilizzare il valore `Block` per impedire agli utenti di creare nuovi file PST e apportare modifiche ai file PST esistenti.<br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |Specifica il nome di un processo di raccolta PST esistente. È necessario utilizzare questo stesso nome di processo utilizzato durante l'esecuzione dello strumento in modalità di ricerca nel passaggio 1. Il nome del processo viene anche aggiunto il nome del file di registro creato quando si esegue lo strumento in modalità di blocco.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Specifica che la cartella contenente il file configuration. XML è stato creato durante l'esecuzione dello strumento in modalità di ricerca. Utilizzare lo stesso valore utilizzato per questo parametro nel passaggio 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Specifica la cartella in cui verrà copiato il file di registro per l'operazione di blocco. Si tratta di un parametro facoltativo. Se non viene incluso, il file di registro viene copiato nella cartella in cui è stato scaricato lo strumento PST insieme a. È consigliabile utilizzare lo stesso percorso registro utilizzato durante l'esecuzione dello strumento in modalità di ricerca nel passaggio 1 in modo che tutti i file di registro vengono salvati nella stessa cartella.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |Utilizzare questa opzione per impedire agli utenti di modificare un file PST. Quando si utilizza questa opzione, viene creata la voce del Registro di sistema seguente: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` e il valore dei dati è impostato su 1. Questa impostazione del Registro di sistema viene creata in computer all'interno dell'organizzazione per l'oggetto Criteri di gruppo che viene creato quando si esegue lo strumento PST raccolta nella modalità di blocco.<br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |Utilizzare questa opzione per impedire agli utenti di creazione di nuovi file PST, apertura e l'importazione di file PST in Outlook e l'esportazione file PST di Outlook. Quando si utilizza questa opzione, viene creata la voce del Registro di sistema seguente: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` e il valore dei dati è impostato su 1. Questa impostazione del Registro di sistema viene creata in computer all'interno dell'organizzazione per l'oggetto Criteri di gruppo che viene creato quando si esegue lo strumento PST raccolta nella modalità di blocco.<br/> | `-BlockNewFiles` <br/> |
   
    Ecco un esempio di sintassi per il comando DataCollectorMaster.exe utilizzando i valori effettivi per ogni parametro:

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    Viene chiesto di confermare che si desidera bloccare nuovi file PST o le modifiche apportate al file PST esistenti. Dopo avere verificato che si desidera continuare e il comando viene eseguito correttamente, verrà visualizzato un messaggio che informa che è stato creato un nuovo oggetto Criteri di gruppo, denominato "PST sull'utilizzo di controlli".
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>Passaggio 3: Copiare i file PST in un percorso raccolta

Il passaggio successivo consiste nel copiare i file PST di file che dove trovare quando è stato eseguito lo strumento PST raccolta nella modalità di ricerca. Consente di raccogliere i file PST in un'unica posizione, in modo che è possibile importare in seguito a Office 365. Prima di copiare i file PST in percorso raccolta, prendere in considerazione per determinare la quantità totale di spazio di archiviazione è obbligatorio. È possibile ottenere questo risultato utilizzando il file CSV creato nel passaggio 1 per calcolare la dimensione totale di tutti i file PST.
  
> [!NOTE]
> Dopo aver importato i file PST in Office 365 e sono stati eliminati dal percorso originale, è possibile eliminarli dalla posizione insieme sono stati copiati per questo passaggio. 
  
1. Aprire un prompt dei comandi (Esegui come amministratore) nel computer locale.
    
2. Passare alla directory in cui è stato scaricato lo strumento PST insieme a.
    
3. Eseguire il comando seguente per copiare i file PST in un percorso specificato.
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    Nella tabella seguente vengono descritti i parametri e i relativi valori necessari quando si esegue il comando DataCollectorMaster.exe per copiare i file PST. 
    
    |Parametro * * *|****Description****|Esempi * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Specifica il tipo di dati da cercare. Attualmente, è possibile utilizzare lo strumento PST raccolta per cercare i file PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Specifica il tipo di operazione verrà eseguita. Utilizzare il valore `Collect` per copiare che i file PST che sono state trovate al momento dell'esecuzione per lo strumento in modalità di ricerca. Si noti che lo strumento è in grado di copiare i file di file PST aperti in Outlook e copiare i file PST connessi ai profili di Outlook.<br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |Specifica il nome di un processo di raccolta PST esistente. È necessario utilizzare questo stesso nome di processo utilizzato durante l'esecuzione dello strumento in modalità di ricerca nel passaggio 1. Il nome del processo viene anche aggiunto il nome del file di registro creato quando si esegue lo strumento in modalità di raccolta.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |Utilizzare lo stesso valore utilizzato per il `Locations` parametro nel passaggio 1. Si dispone include questo parametro quando si esegue lo strumento in modalità Collect se si desidera eseguire di nuovo lo strumento per eliminare i file PST dal percorso di origine nel passaggio 5.<br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |Specifica la cartella che contiene il file di configurazione XML che è stato creato durante l'esecuzione dello strumento in modalità di ricerca. Utilizzare lo stesso valore utilizzato per questo parametro nel passaggio 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |Specifica il percorso raccolta in cui si desidera copiare i file PST. È possibile copiare i file per un file server, una condivisione di file di rete o un disco rigido. Il percorso deve esistere prima di eseguire lo strumento in modalità di raccolta. Lo strumento non crea il percorso e restituirà un errore indicante che non esiste.  <br/> Inoltre, è necessario scrivere le autorizzazioni nel percorso di insieme specificato da questo parametro.  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |Specifica la cartella in cui verrà copiato il file di registro per la modalità di raccolta. Si tratta di un parametro facoltativo. Se non viene incluso, il file di registro viene copiato nella cartella in cui è stato scaricato lo strumento PST insieme a. È consigliabile utilizzare lo stesso percorso registro utilizzato durante l'esecuzione dello strumento in modalità di ricerca nel passaggio 1 in modo che tutti i file di registro vengono salvati nella stessa cartella.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Questo parametro opzionale consente di eseguire di nuovo lo strumento in modalità di raccolta per un processo di raccolta PST esistente. Se già stato eseguito lo strumento in modalità di raccolta, ma quindi eseguito nuovamente lo strumento in modalità di ricerca con il `ForceRestart` opzione per eseguire nuovamente l'analisi percorsi per i file PST, è possibile utilizzare questa opzione per eseguire di nuovo lo strumento in modalità di raccolta e nuovamente copiare i file PST non vi sono stati trovati quando il ripetizione dell'analisi le posizioni. Quando si utilizza il `ForceRestart` opzione in modalità di raccolta, lo strumento di ignorare eventuali operazioni insieme precedente e tenta di copiare i file PST da zero.<br/> | `-ForceRestart` <br/> |
   
    Ecco un esempio di sintassi per lo strumento DataCollectorMaster.exe utilizzando i valori effettivi per ogni parametro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Dopo aver eseguito il comando, vengono visualizzati messaggi di stato dettagliato che mostrano lo stato di avanzamento di raggruppare i file PST che sono stati trovati nel passaggio 1. Dopo un po' di tempo, verrà visualizzato un messaggio di stato finale se si sono gli eventuali errori e percorso in cui viene copiato nel registro. Il file di log vengono copiati gli stessi messaggi di stato.
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>Risultati dell'esecuzione DataCollectorMaster.exe nella modalità di raccolta

Dopo aver eseguito DataCollectorMaster.exe nella modalità di raccolta, i file seguenti vengono creati e memorizzati nelle cartelle specificate per il `LogLocation` e `ConfigurationLocation` parametri. 
  
- **\<Specificare nome di processo\>_raccogliere_\<DateTimeStamp\>. log** -il file di registro contiene i messaggi di stato che sono stati visualizzati. Questo file viene creato nella cartella specificata per il `LogLocation` parametro. 
    
- **\<Specificare nome di processo\>_raccogliere_\<DateTimeStamp\>. XML** -il file XML contiene solo le informazioni sui valori dei parametri dove usato per lo strumento è stato eseguito nella modalità di raccolta. I dati in questo file viene utilizzati quando si esegue lo strumento DataCollectorMaster.exe per eliminare i file PST, eseguire di nuovo vedere [il passaggio 5](#step-5-delete-the-pst-files-found-on-your-network).
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>Passaggio 4: Importare i file PST in Office 365

Dopo aver raccolto i file PST trovati nel passaggio 1, il passaggio successivo consiste nel importarli alle cassette postali in Office 365. Come parte o il processo di importazione, sarà necessario creare un file di mapping CSV che contiene una riga di ogni file PST che si desidera importare. Informazioni di ogni riga specifica il nome del file PST, indirizzo di posta elettronica dell'utente e se si desidera importare il file PST all'utente principale o archiviazione delle cassette postali. Utilizzare le informazioni contenute nel **specificare nome di processo\>_trovare_\<DateTimeStamp.csv** file (creati al passaggio) 1 che consentono di creare il file di mapping CSV. 
  
Per istruzioni dettagliate importare i file PST a Office 365, vedere uno degli argomenti seguenti:
  
- [Utilizzare il caricamento di rete per importare i file PST su Office 365](use-network-upload-to-import-pst-files.md)
    
- [Utilizzare la spedizione dell'unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>Passaggio 5: Eliminare i file PST trovati nella rete

Dopo aver importati i file PST che è stato individuato e raccolti alle cassette postali di Exchange Online in Office 365, è possibile utilizzare lo strumento PST raccolta per eliminare i file PST dai percorsi di origine originale dove sono state trovate nel passaggio 1. 
  
1. Aprire un prompt dei comandi (Esegui come amministratore) nel computer locale.
    
2. Passare alla directory in cui è stato scaricato lo strumento PST insieme a.
    
3. Eseguire il comando seguente per eliminare i file PST.

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    Nella tabella seguente vengono descritti i parametri e i relativi valori necessari quando si esegue il comando DataCollectorMaster.exe per eliminare i file PST. 
    
    |Parametro * * *|****Description****|Esempi * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Specifica il tipo di dati da cercare. Attualmente, è possibile utilizzare lo strumento PST raccolta per cercare i file PST. ![spaziatore](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Specifica il tipo di operazione verrà eseguita. Utilizzare il valore `Delete` da eliminare che i file PST che sono state trovate al momento dell'esecuzione per lo strumento in modalità di ricerca.<br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |Specifica il nome di un processo di raccolta PST esistente. È necessario utilizzare questo stesso nome di processo utilizzato durante l'esecuzione dello strumento in modalità Trova e la raccolta nel passaggio 1 e passaggio 3. Il nome del processo viene anche aggiunto il nome del file di registro creato quando si esegue lo strumento in modalità di eliminazione.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Specifica la cartella che contiene il file di configurazione XML che è stato creato durante l'esecuzione dello strumento in modalità di raccolta. Utilizzare lo stesso valore utilizzato per questo parametro nel passaggio 3.  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Specifica la cartella in cui verrà copiato il file di registro per la modalità di eliminazione. Si tratta di un parametro facoltativo. Se non viene incluso, il file di registro viene copiato nella cartella in cui è stato scaricato lo strumento PST insieme a. È consigliabile utilizzare lo stesso percorso registro utilizzato durante l'esecuzione dello strumento Trova e modalità di raccogliere in passaggio 1 e passaggio 3 in modo che tutti i file di registro vengono salvati nella stessa cartella.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Questo parametro opzionale consente di eseguire di nuovo lo strumento in modalità di eliminazione per un processo di raccolta PST esistente. Se già stato eseguito lo strumento in modalità di eliminazione, ma quindi eseguito nuovamente lo strumento in modalità di ricerca con il `ForceRestart` opzione per eseguire nuovamente l'analisi percorsi per i file PST, è possibile utilizzare questa opzione per eseguire di nuovo lo strumento in modalità di eliminazione ed eliminare i file PST non vi sono stati trovati quando il sca r nned le posizioni. Quando si utilizza il `ForceRestart` opzione in modalità di eliminazione, lo strumento di ignorare eventuali operazioni di eliminazione precedente e tenta di eliminare i file PST nuovamente.<br/> | `-ForceRestart` <br/> 

    Ecco un esempio di sintassi per lo strumento DataCollectorMaster.exe utilizzando i valori effettivi per ogni parametro:
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    Dopo aver eseguito il comando, vengono visualizzati messaggi di stato dettagliato che mostrano lo stato di eliminazione dei file PST che sono stati trovati nel passaggio 1 e raccolte nel passaggio 3. Dopo un po' di tempo, verrà visualizzato un messaggio di stato finale se si sono gli eventuali errori e percorso in cui viene copiato nel registro. Il file di log vengono copiati gli stessi messaggi di stato.
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>Risultati dell'esecuzione DataCollectorMaster.exe in modalità di eliminazione

Dopo aver eseguito DataCollectorMaster.exe in modalità di eliminazione, i file seguenti vengono creati e archiviati nella cartella specificata per il `LogLocation` e `ConfigurationLocation` parametri. 
  
- **\<Specificare nome di processo\>_eliminare_\<DateTimeStamp\>. log** -il file di registro contiene i messaggi di stato che sono stati visualizzati. Questo file viene creato nella cartella specificata per il `LogLocation` parametro. 
    
- **\<Specificare nome di processo\>_eliminare_\<DateTimeStamp\>. XML** -il file XML contiene solo le informazioni sui valori dei parametri dove usato per lo strumento è stato eseguito in modalità di eliminazione. Vengono inoltre elencati il nome e il percorso di ogni file PST che è stato eliminato. Questo file viene creato nella cartella specificata per il `ConfigurationLocation` parametro. 
