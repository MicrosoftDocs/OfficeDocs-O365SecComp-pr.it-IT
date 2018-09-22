---
title: Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: 'Esportare i risultati della ricerca da una ricerca di contenuto in Office 365 Security &amp; centro conformità a un computer locale. I risultati della posta elettronica Emaill vengono esportate come file PST. Contenuto di SharePoint e OneDrive per i siti vengono esportati come nativi documenti di Office. '
ms.openlocfilehash: 9b6db129371b234713b5504f5763ee1dc3d7d638
ms.sourcegitcommit: bf70ec8e11b3f75bf45cd4f760cd1a982593dbad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "24962962"
---
# <a name="export-content-search-results-from-the-office-365-security-amp-compliance-center"></a>Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità

Dopo l'esecuzione di una ricerca di contenuto, è possibile esportare i risultati della ricerca in un computer locale. Quando si esportano i risultati di posta elettronica, viene scaricati al computer come file PST. Quando si esporta il contenuto di SharePoint e OneDrive per i siti di Business, vengono esportate le copie dei documenti di Office nativi. Sono disponibili ulteriori documenti e report inclusi con i risultati della ricerca esportato.
  
Inoltre, eventuali messaggi di posta elettronica crittografati con RMS inclusi nei risultati della ricerca di contenuto verranno decrittografati se esportarli (come singoli messaggi). Questa funzionalità decrittografia è abilitata per impostazione predefinita per i membri del gruppo di ruoli di gestione di eDiscovery. Ciò avviene perché il ruolo di gestione di decrittografia RMS viene assegnato a questo gruppo di ruoli. Quando si esportano i risultati della ricerca, vedere la sezione [informazioni](#more-information) per ulteriori informazioni sulla decrittografia RMS. 
  
Esportare i risultati di ricerca di contenuto comporta la preparazione dei risultati e dopo aver scaricato in un computer locale.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per esportare i risultati della ricerca, è necessario disporre del ruolo di gestione di esportazione in Office 365 Security &amp; centro conformità. Questo ruolo viene assegnato al gruppo di ruoli di gestione incorporati eDiscovery. Non è assegnato per impostazione predefinita al gruppo di ruoli Gestione organizzazione. Per ulteriori informazioni, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
    
- Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:
    
  - Windows 7 a 32 o 64 bit e versioni successive
    
  - Microsoft .NET Framework 4.7
    
  - Browser supportato:
    
     - Microsoft Edge
    
        OPPURE
    
     - Microsoft Internet Explorer 10 e versioni successive
    
    **Nota:** Microsoft non produce delle estensioni di terze parti o componenti aggiuntivi per le applicazioni ClickOnce. Esportazione dei risultati della ricerca mediante un browser non supportato con le estensioni di terze parti o componenti aggiuntivi non è supportato. 
    
- Quando si scarica i risultati della ricerca (descritti nel passaggio 2), è possibile aumentare la velocità di download configurando un'impostazione del Registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Per ulteriori informazioni, vedere [aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
    
- Quando si Esporta risultati della ricerca, i dati vengono archiviati temporaneamente in un percorso di archiviazione Microsoft Azure univoco nel cloud Microsoft prima di scaricarlo nel computer locale. Verificare che l'organizzazione può la connessione all'endpoint in Azure, ovvero ** \*. blob.core.windows.net** (il carattere jolly rappresenta un identificatore univoco per l'esportazione). Dati dei risultati della ricerca viene eliminati dalla posizione di archiviazione Azure due settimane dopo averlo creato. 
    
- Se l'organizzazione utilizza un server proxy per comunicare con Internet, è necessario definire le impostazioni del server proxy nel computer utilizzato per esportare i risultati della ricerca (in modo che lo strumento di esportazione può essere autenticato dal server proxy). A tale scopo, aprire il file *Machine. config* nella posizione corrispondente alla versione di Windows. 
    
  - **versione a 32 bit** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
    
  - **64 bit** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
    
    Aggiungere le righe seguenti al file *Machine. config* in un punto qualsiasi tra il `<configuration>` e `</configuration>` tag. È necessario sostituire `ProxyServer` e `Port` con i valori corretti per l'organizzazione; ad esempio `proxy01.contoso.com:80` . 
    
    ```
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="http://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

- Vedere la sezione per una descrizione dei limiti per esportare i risultati della ricerca. 
    
- La dimensione massima di un file PST che può essere esportato è 10 GB. Se si desidera modificare la dimensione predefinita, è possibile modificare il Registro di sistema nel computer utilizzato per esportare i risultati della ricerca. Vedere [Modifica le dimensioni dei file PST durante l'esportazione dei risultati della ricerca eDiscovery](change-the-size-of-pst-files-when-exporting-results.md).
    
## <a name="step-1-prepare-search-results-for-export"></a>Passaggio 1: Preparare i risultati della ricerca per l'esportazione

Il primo passaggio consiste nel preparare i risultati della ricerca per l'esportazione. Quando si preparano risultati, vengono caricati in una posizione di archiviazione Azure nel cloud Microsoft. Si noti che il contenuto disponibile in siti e le cassette postali sono stato caricato una velocità massima di 2 GB all'ora.
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. Nel riquadro a sinistra del Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **Ricerca contenuto**.
    
4. Nella pagina di **ricerca del contenuto** , selezionare una ricerca. 
    
5. Nel riquadro dei dettagli, in **Esporta i risultati in un computer**, fare clic su **Avvia esportazione**.
    
    > [!NOTE]
    > Se i risultati di una ricerca hanno più di 7 giorni, viene chiesto di aggiornare i risultati di ricerca. In tal caso, annullare l'esportazione, fare clic su **Aggiorna i risultati della ricerca** nel riquadro dei dettagli per la ricerca selezionata, quindi avviare l'esportazione dopo l’aggiornamento dei risultati.  
  
6. Nella pagina **esportazione dei risultati della ricerca** , in **includere questi elementi dalla ricerca**, selezionare una delle opzioni seguenti:
    
    - Esportare solo gli elementi indicizzati
    
    - Esportazione di elementi indicizzati e parzialmente indicizzati
    
    - Esportare solo gli elementi indicizzati parzialmente
    
    Vedere la sezione [informazioni](#more-information) per una descrizione sugli elementi come parzialmente indicizzati vengono esportati. Per ulteriori informazioni sugli elementi indicizzati parzialmente, vedere [parzialmente indicizzato gli elementi della funzionalità di ricerca del contenuto](partially-indexed-items-in-content-search.md).
    
7. In **contenuto di Exchange esportare**, selezionare una delle opzioni seguenti:
    
    - **File PST uno per ogni cassetta postale** - consente di esportare un file PST per ciascuna cassetta postale utente che contiene i risultati della ricerca. Risultati dalla cassetta postale di archivio dell'utente sono inclusi nello stesso file PST. Si noti che questa opzione riproduce la struttura di cartelle delle cassette postali dalla cassetta postale di origine. 
    
    - **File di un file PST contenente tutti i messaggi** - consente di esportare un file PST singolo (denominato *Exchange.pst* ) che contiene i risultati della ricerca da tutte le cassette postali di origine incluse nella ricerca. Si noti che questa opzione riproduce la struttura di cartelle delle cassette postali per ciascun messaggio. 
    
    - **File di un file PST contenente tutti i messaggi in una singola cartella** - Esporta risultati della ricerca in un unico file PST in tutti i messaggi, si trovano in una singola cartella principale. Questa opzione consente ai revisori di esaminare gli elementi in ordine cronologico (elementi vengono ordinati per data di invio) senza dover passare la struttura di cartelle delle cassette postali originale per ogni elemento. 
    
    - **Singoli messaggi** - Esporta risultati di ricerca come messaggi di posta elettronica singoli, utilizzando il formato con estensione msg. Se si seleziona questa opzione, i risultati della ricerca di posta elettronica vengono esportati in una cartella del file System. Il percorso della cartella per i singoli messaggi è uguale a quello utilizzato se si esportati i risultati in file PST. 
    
      > [!IMPORTANT]
      > Per decrittografare i messaggi crittografati con RMS quando vengono esportati, è necessario esportare i risultati della ricerca di posta elettronica come singoli messaggi. I messaggi crittografati resterà crittografati se si esportano i risultati della ricerca come file con estensione PST. 
  
8. Selezionare la casella di controllo **Abilita deduplicazione** per escludere i messaggi duplicati. Questa opzione è disponibile solo se le origini di contenuto della ricerca sono incluse le cartelle pubbliche o cassette postali di Exchange. 
    
    Se si seleziona questa opzione, anche se più copie dello stesso messaggio presenti nelle cassette postali in cui sono stati ricerca verrà esportata solo una copia di un messaggio. Report dei risultati di esportazione (Results.csv) conterrà una riga per ogni copia di un messaggio duplicato in modo che sia possibile identificare le cassette postali (o le cartelle pubbliche) che contengono una copia dei messaggi duplicati. Per ulteriori informazioni sulla deduplicazione e gli elementi come duplicati vengono identificati, vedere [deduplicazione nei risultati della ricerca eDiscovery](de-duplication-in-ediscovery-search-results.md).
    
9. Selezionare la casella di controllo **Includi versioni per i documenti di SharePoint** per esportare tutte le versioni dei documenti di SharePoint. Questa opzione è disponibile solo se le origini di contenuto di ricerca include SharePoint o OneDrive per i siti. 
    
10. Fare clic sulla casella **esportare i file in una cartella compressa (zip)** per esportare i risultati della ricerca in cartelle compresse. Questa opzione è disponibile solo quando si sceglie di esportare elementi di Exchange come singoli messaggi e quando i risultati di ricerca includono documenti di SharePoint o OneDrive. Questa opzione viene utilizzata principalmente per aggirare il limite di 260 caratteri nei nomi di percorso file di Windows durante l'esportazione di elementi. I "nomi di file di elementi esportati" nella sezione [ulteriori informazioni](#more-information) , vedere. 
    
11. Fare clic su **Avvia esportazione**.
    
    I risultati della ricerca sono pronti per il download, il che significa che è in fase di caricamento per il percorso di archiviazione Azure nel cloud Microsoft. Quando si è pronti per il download i risultati della ricerca, il collegamento **Download esportare i risultati** viene visualizzato in **esportare i risultati a un computer** nel riquadro dei dettagli. 
  
## <a name="step-2-download-the-search-results"></a>Passaggio 2: Scaricare i risultati della ricerca

Il passaggio successivo consiste nel scaricare i risultati della ricerca dalla posizione di archiviazione Azure nel computer locale.
  
Come indicato in precedenza, è possibile aumentare la velocità di download configurando un'impostazione del Registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Per ulteriori informazioni, vedere [aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
  
1. Nel riquadro dei dettagli per la ricerca di cui è stata avviata l’esportazione, in **Esporta i risultati in un computer**, fare clic su **Scarica i risultati esportati**.
    
    La finestra **Download esportare i risultati** viene visualizzata e contiene le seguenti informazioni sui risultati di ricerca che verrà scaricato nel computer. 
    
    - Il numero di elementi che verranno scaricati.
    
    - La dimensione totale stimata degli elementi che verranno scaricati.
    
    - Se gli elementi esportati saranno indicizzati o non indicizzati. Gli elementi non indicizzati sono elementi che hanno un formato riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi. Per ulteriori informazioni, vedere [Unindexed items in Content Search](partially-indexed-items-in-content-search.md).
    
    - Se verranno scaricate o meno versioni di documenti SharePoint.
    
    - Lo stato del processo di preparazione all’esportazione. È possibile avviare il download dei risultati della ricerca anche se la preparazione dei dati non è stata completata.
    
2. In **Chiave di esportazione**, fare clic su **Copia negli Appunti**. Si utilizzerà questa chiave per scaricare i risultati della ricerca nel passaggio 5.
    
    > [!NOTE]
    > Poiché chiunque può installare e avviare lo strumento di esportazione eDiscovery e quindi utilizzare questa chiave per scaricare i risultati della ricerca, è bene assicurarsi di adottare alcune precauzioni per proteggere la chiave così come si proteggono le password o altre informazioni relative alla sicurezza.  
  
3. Fai clic su **Scarica risultati**.
    
4. Se viene richiesto di installare **Microsoft Office 365 eDiscovery esportare strumento**, fare clic su **Installa**.
    
5. Nello **Strumento di esportazione eDiscovery**, incollare la chiave di esportazione copiata nel passaggio 2 nella casella appropriata.
    
6. Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare i file dei risultati della ricerca. 
    
    > [!NOTE]
    > A causa della quantità elevata di attività del disco (letture e scritture), è necessario scaricare i risultati della ricerca in un'unità disco locale, non scaricare tali un'unità di rete o altro percorso di rete. 
  
1. Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer. 
    
    **EDiscovery dello strumento di esportazione** viene visualizzato il processo di esportazione, con una stima del numero e dimensione degli altri download di informazioni sullo stato. Una volta completato il processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati. 
    

  
## <a name="more-information"></a>Ulteriori informazioni
<a name="moreinfo"> </a>

Di seguito viene ulteriori informazioni sull'esportazione dei risultati di ricerca.
  
[Limiti di esportazione](export-search-results.md#export-limits)
  
[Esportazione dei rapporti](export-search-results.md#export-reports)
  
[Esportazione di elementi indicizzati parzialmente](#exporting-partially-indexed-items)
  
[Esportazione dei singoli messaggi o i file PST](export-search-results.md#Exporting-individual-messages-or-PST-files)
  
[Decrittografia dei messaggi crittografati con RMS](export-search-results.md#Decrypting-RMS-encrypted-messages)
  
[Nomi di file di elementi esportati](export-search-results.md#Filenames-of-exported-items)
  
[Varie](export-search-results.md#miscellaneous)
  
 ### <a name="export-limits"></a>Limiti di esportazione
  
- Esportazione dei risultati della ricerca dal titolo &amp; centro conformità con i limiti seguenti:
    
  - È possibile esportare un massimo di 2 TB di dati da una singola ricerca contenuto. Se i risultati della ricerca sono superiori a 2 TB, è consigliabile utilizzare gli intervalli di data o altri tipi di filtri per ridurre le dimensioni totali dei risultati della ricerca.
    
  - L'organizzazione è possibile esportare un massimo di 2 TB di dati durante un singolo giorno.
    
  - È possibile eseguire un massimo di 10 esportazioni contemporaneamente all'interno dell'organizzazione.
    
  - Un singolo utente può eseguire un massimo di tre esportazioni contemporaneamente.
    
  - Esportazione dei report di ricerca del contenuto non viene conteggiata uno qualsiasi dei limiti di esportazione. 
    
- Come affermato in precedenza, i risultati di ricerca di cassette postali e i siti vengono caricati nel percorso di archiviazione Azure (come descritto in [passaggio 1: preparazione per l'esportazione risultati di ricerca](export-search-results.md#step1)) una velocità massima di 2 GB all'ora.
    
- Per impostazione predefinita, la dimensione massima di un file PST che può essere esportato è 10 GB. Ciò significa che se i risultati della ricerca dalla cassetta postale dell'utente sono superiori a 10 GB, verrà esportati i risultati della ricerca per la cassetta postale in file PST distinti due (o più). Inoltre, se si sceglie di esportare tutti i risultati della ricerca in un unico file PST, il file PST verrà essere consente di dividere in file PST aggiuntivi se le dimensioni totali dei risultati della ricerca sono superiori a 10 GB. Se si desidera modificare la dimensione predefinita, è possibile modificare il Registro di sistema nel computer utilizzato per esportare i risultati della ricerca. Vedere [Modifica le dimensioni dei file PST durante l'esportazione dei risultati della ricerca eDiscovery](change-the-size-of-pst-files-when-exporting-results.md).
    
    Inoltre, i risultati della ricerca da una specifica cassetta postale non essere suddivisi tra più file PST a meno che il contenuto da un'unica cassetta postale è più di 10 GB. Se si sceglie di esportare i risultati della ricerca in un file PST file che contiene tutti i messaggi in una singola cartella e i risultati della ricerca sono superiori a 10 GB, gli elementi sono ancora organizzati in ordine cronologico, in modo che sarà possibile consente di dividere in file PST aggiuntivi basati su d inviati Aggiorna.
     
 ### <a name="export-reports"></a>Esportazione dei rapporti
  
- Quando si Esporta risultati della ricerca, i report seguenti sono inclusi oltre ai risultati della ricerca.
    
  - **Esportazione di riepilogo** Un documento di Excel che contiene un riepilogo dell'esportazione. Sono incluse le informazioni quali il numero di origini di contenuto in cui sono stati ricercati, le dimensioni stimate e scaricate dei risultati della ricerca e il numero di elementi che sono stati esportati stimato e scaricato. 
    
  - **Manifesto** File manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca. 
    
  - **Risultati** Un documento di Excel che contiene informazioni su ogni elemento è disponibile come download come risultato di ricerca. Per la posta elettronica, il registro risultato contiene informazioni su ogni messaggio, tra cui: 
    
      - Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).
        
      - La data in cui è stato inviato o ricevuto il messaggio.
        
      - La riga dell'oggetto del messaggio.
        
      - Il mittente e i destinatari del messaggio.
        
      - Indica se il messaggio è un messaggio duplicato se è abilitata l'opzione deduplicazione per l'esportazione dei risultati della ricerca. I messaggi duplicati dispone di un valore nella colonna **duplicati all'elemento** che identifica il messaggio come duplicato. Il valore nella colonna **duplicati all'elemento** contiene l'identità dell'elemento del messaggio è stato esportato. Per ulteriori informazioni, vedere [deduplicazione nei risultati della ricerca eDiscovery](de-duplication-in-ediscovery-search-results.md).
        
      Per i documenti di SharePoint e OneDrive per i siti di Business, registro risultato contiene informazioni su tutti i documenti, tra cui:
        
      - L'URL per il documento.
        
      - L’URL per la raccolta di siti in cui si trova il documento.
        
      - La data dell'ultima modifica al documento.
        
      - Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).
    
  - **Elementi indicizzati** Un documento di Excel che contiene informazioni su eventuali elementi indicizzati parzialmente inclusi nei risultati della ricerca. Se non si includono elementi indicizzati parzialmente quando si genera il rapporto di risultati di ricerca, questo rapporto verrà scaricato, ma sarà vuoto. 
    
  - **Errori e avvisi** Contiene gli errori e avvisi relativi al file di cui che si è verificati durante l'esportazione. Vedere i dettagli sugli errori per informazioni specifiche per ogni singolo errore o avviso. 
    
  - **Elementi ignorati** Quando si esportano risultati di ricerca di SharePoint e OneDrive per i siti, l'esportazione include in genere un rapporto di elementi ignorati (SkippedItems.csv). Gli elementi citati in questo report sono in genere gli elementi non vengono scaricati, ad esempio una cartella o un documento impostata. Esportazione non questo tipi di elementi è per impostazione predefinita. Per altri elementi che sono state ignorate dal campo 'Dettagli sugli errori' nel rapporto di elementi ignorati 'Errore tipo' Mostra il motivo per l'elemento è stato ignorato e non è stato scaricato con risultati della ricerca. 
    
  - **Registro di traccia** Contiene informazioni dettagliate sulla registrazione delle informazioni relative al processo di esportazione e consentono di individuare i problemi durante l'esportazione. 
    
    > [!NOTE]
    > È possibile esportare i documenti appena senza la necessità di esportare i risultati della ricerca effettiva. Vedere [esportazione di un report di ricerca del contenuto](export-a-content-search-report.md). 
  
 ### <a name="exporting-partially-indexed-items"></a>Esportazione di elementi indicizzati parzialmente
  
- Per l'esportazione di elementi della cassetta postale da una ricerca di contenuto che restituisce tutti gli elementi della cassetta postale nei risultati della ricerca (dal momento che nessun parole chiave dove inclusi nella query di ricerca), gli elementi parzialmente indicizzati non vengono copiati in file PST contenente gli elementi indicizzati. Ciò avviene perché tutti gli elementi, inclusi gli elementi parzialmente indicizzati vengono inclusi automaticamente nei risultati della ricerca regolari. Ciò significa che gli elementi indicizzati parzialmente verranno inclusi in un file PST, o come singoli messaggi, che contiene gli elementi di altri, indicizzati.
    
    Inoltre, se si esportano elementi indicizzati e parzialmente indicizzati o se si esportano solo gli elementi indicizzati da una ricerca di contenuto che restituisce tutti gli elementi, verrà scaricato lo stesso numero di elementi. Ciò avviene anche se i risultati di ricerca stimata per la ricerca del contenuto (visualizzate le statistiche di ricerca nella protezione &amp; centro conformità) ancora includerà una stima distinta per il numero di elementi indicizzati parzialmente. Ad esempio, si supponga che la stima per eseguire una ricerca contenente tutti gli elementi (nessuna parola chiave nella query di ricerca) viene illustrato che sono state trovate 1.000 voci e che sono stati trovati anche 200 oggetti parzialmente indicizzati. In questo caso, 1.000 voci includono gli elementi indicizzati parzialmente dal momento che la ricerca restituisce tutti gli elementi. In altre parole, non esistono 1.000 voci totale restituiti dalla ricerca elementi di e non 1200 (prevedibilmente). Se esportare i risultati della ricerca e scegliere di esportazione indicizzato e parzialmente indicizzato elementi (o elementi indicizzati appena), quindi vengono scaricati 1.000 voci. Nuovamente, ciò avviene perché gli elementi indicizzati parzialmente sono inclusi con i risultati (indicizzati) regolari quando si utilizza una query di ricerca vuoto per restituire tutti gli elementi. In questo esempio stesso, se si sceglie di esportare solo gli elementi indicizzati parzialmente, quindi solo gli elementi non indicizzati 200 download di.
    
    Si noti inoltre che nell'esempio precedente (quando si esportano elementi indicizzati e parzialmente indicizzati o l'esportazione di elementi indicizzati solo), il report di **Riepilogo esportazione** incluso con i risultati della ricerca esportato potrebbe elencare gli elementi stimata 1.000 voci e 1.000 scaricato elementi per i motivi stessi come descritti in precedenza. 
    
- Se la ricerca per l'esportazione dei risultati di ricerca dei percorsi di contenuti specifici o tutti i percorsi di contenuti nell'organizzazione, verranno esportati solo parzialmente gli elementi dai percorsi di contenuti che includono gli elementi che soddisfano i criteri di ricerca. In altre parole, se non viene trovato alcun risultato di ricerca in una cassetta postale o un sito, quindi qualsiasi parzialmente voci indicizzate nella cassetta postale o siti non verranno esportati. Il motivo di ciò è che l'esportazione di elementi indicizzati parzialmente da una quantità elevata di posizioni all'interno dell'organizzazione potrebbe aumentare la probabilità di errori di esportazione e aumentare il tempo che necessario per l'esportazione e scaricare i risultati della ricerca.
    
    Per esportare elementi parzialmente indicizzati da tutti i percorsi di contenuti per eseguire una ricerca, configurare la ricerca per restituire tutti gli elementi (rimuovendo le parole chiave di query di ricerca) e quindi esportare elementi parzialmente indicizzati solo quando si esportano i risultati della ricerca.
    
    ![Utilizzare l'opzione Esporta la terza per esportare solo gli elementi non indicizzati](media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Per l'esportazione dei risultati di ricerca di SharePoint o OneDrive per i siti, è anche la possibilità di esportare elementi indicizzati dipende l'opzione di esportazione selezionato e indica se un sito in cui è stata eseguita la ricerca contiene un elemento indicizzato che soddisfa i criteri di ricerca. Ad esempio, se si ricerca specifici SharePoint o OneDrive per i siti e non viene trovato alcun risultato di ricerca, quindi non elementi indicizzati da tali siti verranno esportati se si sceglie la seconda opzione di esportazione per esportare elementi indicizzati e non indicizzati. Se un elemento con l'indice da un sito corrispondono ai criteri di ricerca, verranno esportati tutti gli elementi indicizzati da tale sito durante l'esportazione di elementi indicizzati e non indicizzati. Nella figura seguente vengono descritte le opzioni di esportazione basate o meno un sito contiene un elemento indicizzato che soddisfa i criteri di ricerca.
    
    ![Scegliere l'opzione di esportazione basata o meno un sito contiene un elemento indicizzato che soddisfa i criteri di ricerca](media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    
    A - solo gli elementi indicizzati che soddisfa i criteri di ricerca vengono esportati. Nessun elemento parzialmente indicizzato viene esportato.
    
    B - se non elementi indicizzati da un sito corrispondono ai criteri di ricerca, non vengono esportati elementi parzialmente indicizzati allo stesso sito. Se gli elementi indicizzati da un sito vengono restituiti nei risultati della ricerca, vengono esportati gli elementi parzialmente indicizzati da tale sito. In altre parole, vengono esportati solo gli elementi indicizzati parzialmente dai siti che contengono gli elementi che soddisfano i criteri di ricerca.
    
    C - tutti gli elementi parzialmente indicizzati da tutti i siti di ricerca vengono esportati, indipendentemente dal fatto se un sito contiene elementi corrispondenti ai criteri di ricerca.
    
    Se si sceglie di esportare elementi indicizzati parzialmente, gli elementi della cassetta postale parzialmente indicizzati vengono esportati in un file PST separato indipendentemente dall'opzione scelta in **contenuto di Exchange di esportazione**.

- Se vengono restituiti gli elementi indicizzati parzialmente nella ricerca risultati (dal momento che le altre proprietà di elementi indicizzati parzialmente corrispondono ai criteri di ricerca), tali parzialmente indicizzati vengono esportati con i risultati della ricerca regolari. Pertanto, se si sceglie di esportare elementi indicizzati ed elementi indicizzati parzialmente (selezionando l'opzione di esportazione di **tutti gli elementi, comprese quelle che hanno il formato non riconosciuto, vengono crittografati o non indicizzati per altri motivi** ), gli elementi indicizzati parzialmente esportato verranno elencati nel rapporto Results.csv con reslts regolare. Non essere elencati nel rapporto items.csv non indicizzate.
    
 ### <a name="exporting-individual-messages-or-pst-files"></a>Esportazione dei singoli messaggi o i file PST
  
- Se il nome del percorso file del messaggio supera il limite massimo di caratteri per Windows, il nome del percorso di file verrà troncato. Ma il nome del percorso file originale verrà elencato nel manifesto e ResultsLog.
    
- Come indicato in precedenza, posta elettronica ricerca i risultati vengono esportati in una cartella del file System. Il percorso della cartella per i singoli messaggi sarebbe replicare il percorso della cartella di cassetta postale dell'utente. Ad esempio, per eseguire una ricerca denominata "ContosoCase101" i messaggi di posta in arrivo dell'utente sono posizionati nel percorso della cartella `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`. 
    
- Se si sceglie di esportare i messaggi di posta elettronica in un file PST contenente tutti i messaggi in una singola cartella, una cartella **Posta eliminata** e una cartella di **Cartelle ricerche** sono inclusi nel livello principale della cartella file PST. Queste cartelle sarà vuote. 
  
 ### <a name="decrypting-rms-encrypted-messages"></a>Decrittografia dei messaggi crittografati con RMS
  
- Come indicato in precedenza, per decrittografare i messaggi crittografati con RMS quando si esporta, è necessario esportare i risultati della ricerca come singoli messaggi. Se si esportano i risultati della ricerca in un file PST, i messaggi crittografati con RMS resterà crittografati.
    
- La funzionalità di decrittografia RMS di ricerca del contenuto non decrittografia i messaggi crittografati con la crittografia messaggi Office 365 (OME) quando si esportano i risultati della ricerca. Tuttavia, se un messaggio crittografato con OME viene inviato da un utente all'interno dell'organizzazione, la copia del messaggio nella cartella Posta inviata dell'utente non viene crittografata e possono essere visualizzata dopo l'esportazione. Tuttavia, se vengono ricevuti messaggi crittografati con OME dagli utenti nell'organizzazione, sono non decrittografati dopo che vengono esportati. Per ulteriori informazioni su OME, vedere [Office 365 Message Encryption](https://go.microsoft.com/fwlink/p/?linkid=844966).
    
- I messaggi decrittografati vengono identificati nel rapporto **ResultsLog** . Questo rapporto contiene una colonna denominata **Decodificare lo stato**e un valore di **Decoded** in questo articolo vengono identificati i messaggi di erano decrittografati. 
    
- Attualmente, questa funzionalità decrittografia non include crittografato contenuto di SharePoint e OneDrive per i siti. Solo i messaggi di posta elettronica crittografati con RMS verranno decrittografati durante l'esportazione.
    
- Se un messaggio di posta elettronica crittografati con RMS è un allegato (ad esempio, un documento o un altro messaggio di posta elettronica) che viene inoltre crittografato, verrà decrittografato solo il messaggio di posta elettronica principale.
    
- Impossibile visualizzare l'anteprima di un messaggio di posta elettronica crittografati con RMS. Per visualizzare un messaggio crittografato, è necessario esportare il certificato.
    
- Se è necessario per impedire ad altri utenti di decrittografia messaggi crittografati con RMS, è necessario creare un gruppo di ruoli personalizzati (copiando eDiscovery gruppo di ruoli di gestione incorporati) e quindi rimuovere il ruolo di gestione di decrittografia RMS dal gruppo di ruolo personalizzato. Aggiungere la persona che non si desidera decrittografare i messaggi con un account membro del gruppo di ruoli personalizzati.
  
 ### <a name="filenames-of-exported-items"></a>Nomi di file di elementi esportati
  
- Non esiste un limite di 260 caratteri (imposto dal sistema operativo) per il nome del percorso completo di messaggi di posta elettronica e documenti del sito esportati nel computer locale. Il nome del percorso completo per gli elementi esportati include la posizione dell'elemento originale e il percorso della cartella nel computer locale dove vengono scaricati i risultati della ricerca. Ad esempio, se si specifica per scaricare i risultati della ricerca per `C:\Users\Admin\Desktop\SearchResults` , nello strumento di esportazione di eDiscovery, il percorso completo per un elemento di posta elettronica scaricato sarà `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`.
    
    Se viene superato il limite di 260 caratteri, il nome del percorso completo per un elemento verrà troncato.
    
  - Se il nome del percorso completo include più di 260 caratteri, il nome del file verrà abbreviato per ottenere sotto il limite; Si noti che il nome del file troncata, esclusa l'estensione di file, non sarà minore di 8 caratteri.
    
  - Se il nome del percorso completo è troppo lungo ancora Dopo Abbreviare il nome del file, l'elemento viene spostato dalla posizione corrente per la cartella padre. Se viene rilevata troppo lungo il percorso e quindi il processo viene ripetuto: abbreviare il nome di file e se è necessario sposta nuovamente la cartella padre. Questo processo viene ripetuto fino a quando non è incluso il percorso completo nel limite di 260 caratteri.
    
  - Se il percorso completo troncato esiste già, verrà aggiunto un numero di versione e la fine del nome del file: ad esempio `statusmessage(2).msg`.
    
    Per ovviare a questo problema, è possibile scaricare i risultati della ricerca in un percorso con un nome di percorso breve. ad esempio il download dei risultati di ricerca in una cartella denominata `C:\Results` potrebbe aggiungere un numero inferiore di caratteri per i nomi dei percorsi di elementi esportati di eseguirne il download in una cartella denominata `C:\Users\Admin\Desktop\Results`.
    
- Quando si esportano documenti del sito, è inoltre possibile che verrà modificato il nome di file originale di un documento. Ciò avviene in modo specifico per i documenti che sono stati eliminati da SharePoint o OneDrive per sito aziendale che è stato messo in attesa. Dopo l'eliminazione di un documento che si trova su un sito in cui è in attesa, il documento eliminato viene spostato automaticamente alla libreria di attesa di conservazione per il sito (che è stato creato quando il sito è stato messo in attesa). Quando il documento eliminato viene spostato alla libreria di attesa di conservazione, viene aggiunto un ID generato casualmente e univoco per il nome del file originale del documento. Ad esempio, se il nome di file per un documento `FY2017Budget.xlsx` e tale documento viene eliminato e spostato la raccolta di attesa di conservazione, il nome del file del documento che viene spostato alla libreria di attesa di conservazione viene modificata per un'operazione di successivamente `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`. Se corrisponde a un documento nella raccolta di attesa di conservazione della query di ricerca di contenuto ed esportare i risultati della ricerca, il file esportato è il nome del file modificato; In questo esempio, potrebbe essere il nome del file del documento esportato `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`.
    
    Inoltre, quando viene modificato in un documento memorizzato su un sito in cui è in attesa e il controllo delle versioni per la raccolta documenti nel sito è stata abilitata, nella libreria di attesa di conservazione viene creata automaticamente una copia del file. In questo caso, un ID univoco e generato casualmente inoltre viene aggiunto al nome del file del documento viene copiato nella raccolta di attesa di conservazione.
    
    Motivo i nomi dei file di documenti che vengono spostati o copiati nella raccolta di attesa di conservazione per evitare i nomi di file in conflitto. Per ulteriori informazioni sull'esecuzione di un'esenzione su siti e la raccolta di attesa di conservazione, vedere [Overview of sul posto archiviazione in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).
    
 ### <a name="miscellaneous"></a>Varie
  
- Tutti i risultati di ricerca e l'esportazione dei rapporti è incluse in una cartella con lo stesso nome di ricerca del contenuto. I messaggi di posta elettronica che sono stati esportati si trovano in una cartella denominata **Exchange**. Documenti si trovano in una cartella denominata **SharePoint**. 
    
- I metadati del file system per i documenti in SharePoint e OneDrive per i siti viene mantenuto quando i documenti vengono esportati nel computer locale. Che indica che le proprietà del documento, ad esempio creato e le date dell'ultima modifica, non vengono modificate quando vengono esportati i documenti.