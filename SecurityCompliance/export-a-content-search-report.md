---
title: Esportare il rapporto della Ricerca contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/25/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Invece di esportare i risultati effettivi della ricerca contenuto in Office 365 Security &amp; centro conformità, è possibile esportare solo un rapporto di risultati di ricerca. Il report contiene un riepilogo dei risultati della ricerca e un documento con informazioni dettagliate su ogni elemento che verrà esportata.
ms.openlocfilehash: 45415f25754b4549a919e4ce56853a6ae09a9bdc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530207"
---
# <a name="export-a-content-search-report"></a>Esportare il rapporto della Ricerca contenuto

Invece di esportare il set completo di ricerca di risultati di una ricerca di contenuto in Office 365 Security &amp; centro conformità e da una ricerca del contenuto associato a un caso di eDiscovery, è possibile esportare solo i report stessi sono generati quando si esportare i risultati della ricerca.
  
Quando si esporta un report, viene scaricato in una cartella che ha lo stesso nome di ricerca del contenuto, ma che viene aggiunto con *_ReportsOnly* . Ad esempio, se la ricerca del contenuto denominata *ContosoCase0815* , il report viene scaricato in una cartella denominata *ContosoCase0815_ReportsOnly* . Per un elenco di documenti che sono inclusi nella relazione, vedere [che cos'è incluso nel report](#whats-included-in-the-report).

## <a name="before-you-begin"></a>Informazioni preliminari

- Per esportare un report di ricerca del contenuto, è necessario disporre del ruolo di gestione ricerca conformità in Office 365 Security &amp; centro conformità. Questo ruolo viene assegnato ai gruppi di ruolo Manager e la gestione dell'organizzazione eDiscovery incorporati. Non è assegnato per impostazione predefinita al gruppo di ruoli Gestione organizzazione. Per ulteriori informazioni, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
    
- Quando si esporta un report, i dati vengono archiviati temporaneamente in un'area di archiviazione di Windows Azure univoca nel cloud Microsoft prima di scaricarlo nel computer locale. Verificare che l'organizzazione può la connessione all'endpoint in Azure, ovvero ** \*. blob.core.windows.net** (il carattere jolly rappresenta un identificatore univoco per l'esportazione). Dati dei risultati della ricerca viene eliminati dall'area di archiviazione Azure due settimane dopo averlo creato. 
    
- Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:
    
  - Windows 7 a 32 o 64 bit e versioni successive
    
  - Microsoft .NET Framework 4.7
    
  - Browser supportato:
    
    - Microsoft Edge
    
      oppure
    
    - Microsoft Internet Explorer 10 e versioni successive
    
    **Nota:** Microsoft non produce delle estensioni di terze parti o componenti aggiuntivi per le applicazioni ClickOnce. Esportazione dei risultati della ricerca mediante un browser non supportato con le estensioni di terze parti o componenti aggiuntivi non è supportato. 
    
## <a name="generate-and-download-a-content-search-report"></a>Generare e scaricare un report di ricerca del contenuto

I passaggi per generare e scaricare un report di ricerca del contenuto sono molto simili ai effettivamente esportazione dei risultati della ricerca.
  
## <a name="step-1-generate-the-report-for-export"></a>Passaggio 1: Generare il report per l'esportazione

Il primo passaggio consiste nel preparare il report per il download per l'esportazione di computer. Quando si il report il rapporto di documenti vengono caricati in un'area di archiviazione Azure in Microsoft cloud.
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. Nel riquadro a sinistra del Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **Ricerca contenuto**.
    
4. Nella pagina di **ricerca del contenuto** , selezionare una ricerca. 
    
5. Nel riquadro dei dettagli, in **Esporta report in un computer**, fare clic su **Genera rapporto**.
    
    > [!NOTE]
    > Se i risultati di ricerca sono anteriori a 7 giorni, verrà richiesto di aggiornare i risultati della ricerca. In questo caso, annullare l'esportazione, fare clic su **risultati della ricerca di aggiornamento** nel riquadro dei dettagli per la ricerca selezionata e quindi avviare di nuovo l'esportazione di report dopo che i risultati vengono aggiornati. 
  
6. Nella pagina **esportazione di un report** , in **includere questi elementi dalla ricerca**, selezionare una delle opzioni seguenti:
    
    - Esportare solo gli elementi indicizzati
    
    - Esportare gli elementi indicizzati e non
    
    - Esportare solo gli elementi non indicizzati
    
    Per ulteriori informazioni sugli elementi non indicizzate, vedere [parzialmente indicizzato gli elementi della funzionalità di ricerca del contenuto](partially-indexed-items-in-content-search.md).
    
7. Scegliere se includere le statistiche di ricerca per tutte le versioni dei documenti di SharePoint. Questa opzione è disponibile solo se le origini di contenuto di ricerca include SharePoint o OneDrive per i siti.
    
8. Fare clic su **Genera rapporto**.
    
    Report dei risultati di ricerca è preparato per il download, ovvero che i documenti report verranno caricati all'area di archiviazione Azure nel cloud Microsoft. Quando il report è pronto per il download, il collegamento **Download rapporto** viene visualizzato in **Esporta report in un computer** nel riquadro dei dettagli. 
    
> [!NOTE]
> È inoltre possibile esportare un report per una ricerca del contenuto associato a un caso eDiscovery. A tale scopo, passare a **ricerca &amp; indagini** \> selezionare un caso **eDiscovery**e fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). Nella pagina **ricerche** , selezionare una ricerca e quindi fare clic su **Esporta** ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **esportare un report**. 
  
## <a name="step-2-download-the-report"></a>Passaggio 2: Scaricare i report

Il passaggio successivo consiste nel scaricare il report dall'area di archiviazione Azure nel computer locale.
  
1. Nel riquadro dei dettagli per la ricerca generato il rapporto, in **Esporta report in un computer**, fare clic su **Scarica report**.
    
    La pagina **Scarica report** viene visualizzata e contiene le seguenti informazioni sul report fino ad essere scaricato nel computer. 
    
    - Il numero di elementi che verranno scaricati.
    
    - La dimensione totale stimata degli elementi che verranno scaricati.
    
    - Se non indicizzati o indicizzato verrà esportato. Elementi indicizzati sono gli elementi che dispongono di un formato riconosciuto, vengono crittografati o non indicizzati per altri motivi.
    
    - Se verranno scaricate o meno versioni di documenti SharePoint.
    
    - Lo stato del processo di esportazione report. È possibile avviare il download del rapporto anche se la preparazione del report non viene completata.
    
2. In **Esporta chiave**, fare clic su **Copia negli Appunti**. Utilizzare questa chiave nel passaggio 5 per scaricare il report.
    
    > [!IMPORTANT]
    > Poiché tutti gli utenti possono installare e avviare lo strumento di esportazione di eDiscovery e quindi utilizzare questa chiave per scaricare il report di ricerca, è necessario adottare alcune precauzioni per proteggere la chiave nello stesso modo in cui è necessario proteggere password o altre informazioni relative alla sicurezza. 
  
3. Fare clic su **Scarica report**.
    
4. Se viene richiesto di installare **Microsoft Office 365 eDiscovery esportare strumento**, fare clic su **Installa**.
    
5. Nello **Strumento di esportazione eDiscovery**, incollare la chiave di esportazione copiata nel passaggio 2 nella casella appropriata.
    
6. Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare il report. 
    
7. Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer. 
    
    **EDiscovery dello strumento di esportazione** viene visualizzato il processo di esportazione, con una stima del numero e dimensione degli altri download di informazioni sullo stato. Una volta completato il processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati. 
    
> [!NOTE]
> È possibile scaricare il report per una ricerca del contenuto associato a un caso eDiscovery. A tale scopo, passare a **ricerca &amp; indagini** \> selezionare un caso **eDiscovery**e fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). Nella pagina **Esporta** selezionare Esporta un report e quindi fare clic su **Scarica report** nel riquadro dei dettagli. 
  
## <a name="whats-included-in-the-report"></a>Che cos'è incluso nel rapporto

Quando si genera e l'esportazione di un report sui risultati di ricerca di contenuto, vengono scaricati i documenti seguenti:
  
- **Esportare riepilogo** - documento di Excel che contiene un riepilogo dell'esportazione. Sono incluse informazioni quali il numero di origini di contenuto in cui sono stati ricercati, il numero di risultati di ricerca ogni percorso contenuto, il numero stimato di elementi, il numero effettivo di elementi che potrebbe essere esportate e le dimensioni stimate ed effettiva di elementi che potrebbe essere esportati. 
    
    > [!NOTE]
    > Se si includono gli elementi indicizzati durante l'esportazione del report, il numero di elementi indicizzati viene incluso il numero totale di risultati di ricerca stimati e il numero totale di scaricati i risultati di ricerca (se fosse per esportare i risultati della ricerca) sono elencati nel Esportare il rapporto di riepilogo. In altre parole, il numero totale di elementi che potrebbe essere scaricato è uguale al numero totale di risultati stimati e il numero totale di elementi indicizzati. 
  
- **Manifesto** - un file manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca. 
    
- **Risultati** - documento di Excel che contiene una riga con informazioni su ogni elemento indicizzato esportato con i risultati della ricerca. Per la posta elettronica, il registro risultato contiene informazioni su ogni messaggio, tra cui: 
    
  - Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).
    
  - La data in cui è stato inviato o ricevuto il messaggio.
    
  - La riga dell'oggetto del messaggio.
    
  - Il mittente e i destinatari del messaggio.
    
    Per i documenti di SharePoint e OneDrive per i siti, il registro dei risultati contiene informazioni su tutti i documenti, tra cui:
    
  - L'URL per il documento.
    
  - L’URL per la raccolta di siti in cui si trova il documento.
    
  - La data dell'ultima modifica al documento.
    
  - Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).
    
    > [!NOTE]
    > Il numero di righe nel report dei **risultati** deve essere uguale al numero totale dei risultati della ricerca scaricati meno il numero totale di elementi elencati nel rapporto di **Elementi indicizzati** . 
  
- **Elementi indicizzati** : documento di Excel che contiene informazioni su eventuali elementi indicizzati inclusi nei risultati della ricerca. Se non si includono gli elementi indicizzati quando si genera il rapporto di risultati di ricerca, questo rapporto verrà scaricato, ma sarà vuoto.
