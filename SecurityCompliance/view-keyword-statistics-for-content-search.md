---
title: Visualizzare le statistiche delle parole chiave per i risultati della Ricerca contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Utilizzare la funzionalità di ricerca le statistiche per visualizzare e confrontare le statistiche per le ricerche di contenuto più di sicurezza di Office 365 &amp; centro conformità. È inoltre possibile configurare l'elenco delle parole chiave quando si crea o modifica di una query di ricerca per ottenere le statistiche avanzate che mostra il numero di elementi corrispondenti a ogni parola chiave o una frase parola chiave.
ms.openlocfilehash: 0f0258f228e296e48def8de16aabc068901dffc7
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "27209807"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Visualizzare le statistiche delle parole chiave per i risultati della Ricerca contenuto

Dopo aver creato ed eseguire una ricerca di contenuto, è possibile visualizzare le statistiche relative ai risultati di ricerca stimati. Include un riepilogo dei risultati della ricerca (simili a riepilogo dei risultati di ricerca stimati visualizzato nel riquadro dei dettagli), le statistiche delle query, ad esempio il numero di posizioni contenute con gli elementi che corrispondono alla query di ricerca e il nome dei percorsi di contenuti che contiene elementi più corrispondenti. È possibile visualizzare le statistiche per uno o più ricerche di contenuto. In tal modo si per confrontare i risultati delle ricerche eseguite più rapidamente e prendere decisioni sull'efficacia le query di ricerca.
  
Inoltre, è possibile configurare le ricerche di nuove ed esistenti per restituire le statistiche per ogni parola chiave in una query di ricerca. Consente di confrontare il numero di risultati per ogni parola chiave in una query e per confrontare le statistiche sulle parole chiave da più ricerche.
  
È inoltre possibile scaricare le statistiche di ricerca e statistiche sulle parole chiave in un file CSV. Consente di utilizzare le funzionalità di filtro e ordinamento in Excel per confrontare i risultati e preparare i report dei risultati della ricerca.
  
## <a name="get-statistics-for-content-searches"></a>Ottenere le statistiche per le ricerche di contenuto

Per visualizzare le statistiche per le ricerche di contenuto:
  
1. In Office 365 Security &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca del contenuto**.
    
2. Nell'elenco delle ricerche, selezionare uno o più ricerche e quindi fare clic su **statistiche ricerca**![pulsante statistiche ricerca](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png).
    
    ![Selezionare più ricerche e quindi fare clic su statistiche ricerca](media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. Nella pagina **informazioni statistiche sulla ricerca** fare clic su uno dei collegamenti seguenti per visualizzare le statistiche sulle ricerche selezionati. 
    
    **Riepilogo**
    
    In questa pagina consente di visualizzare le statistiche simili a quelli visualizzati nel riquadro dei dettagli della pagina di **ricerca del contenuto** . Vengono visualizzate le statistiche per tutte le ricerche selezionate. Si noti che è possibile inoltre eseguire di nuovo ricerche selezionati da questa pagina per aggiornare le statistiche. 
    
    ![Riepilogo delle statistiche per le ricerche selezionati](media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    r. il nome di ricerca del contenuto. Come descritto in precedenza, è possibile visualizzare e confrontare le statistiche per le ricerche più.
    
    b. il tipo di percorso contenuto che è stata eseguita la ricerca. Ogni riga vengono visualizzate le statistiche per cassette postali, i siti e le cartelle pubbliche di ricerca specificata.
    
    c. il numero di elementi che corrispondono alla query di ricerca contenente i percorsi di contenuti. Per le cassette postali, questa statistica include anche il numero di cassette postali di archiviazione che contengono gli elementi che corrispondono alla query di ricerca.
    
    d. il numero totale di elementi di specificato tutti i percorsi di contenuti che corrispondono alla query di ricerca. Ad esempio tipi di elementi di messaggi di posta elettronica, gli elementi del calendario e documenti. Se un elemento contiene più istanze di una parola chiave che viene ricercato, si è conteggiato una sola volta nel numero totale di elementi. Ad esempio, se si esegue la ricerca per le parole "stock" o "false" e un messaggio di posta elettronica include tre occorrenze della parola "stock", si è conteggiato una sola volta nella colonna **elementi** . 
    
    e. la dimensione totale di tutti gli elementi che sono state trovate nel percorso del contenuto specificato che corrispondono alla query di ricerca. 
    
    **Query**
    
    In questa pagina vengono visualizzate le statistiche sulle query di ricerca.
    
    ![Statistiche sulle query di ricerca per le ricerche selezionati](media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    r. nome della ricerca contenente la riga le statistiche delle query per contenuto.
    
    b. il tipo di percorso contenuto non applicabili per le statistiche delle query.
    
    c. questa colonna indica quale parte della query di ricerca sono applicabili per le statistiche. **Principale** indica la query di ricerca intero. Se si utilizza un elenco delle parole chiave quando si crea o modifica di una query di ricerca, le statistiche per ogni componente di query sono inclusi in questa tabella. Vedere la sezione [ottenere statistiche sulle parole chiave per le ricerche di contenuto](#get-keyword-statistics-for-content-searches) in questo articolo per ulteriori informazioni. 
    
    d. questa colonna contiene la ricerca effettiva delle query eseguite dallo strumento di ricerca del contenuto. Si noti che lo strumento aggiunge automaticamente alcuni componenti aggiuntivi per la query creati personalmente. 

    - La ricerca per tutto il contenuto nelle cassette postali (se non si specifica una qualsiasi parola chiave), la query effettivo parola chiave è `size>=0` in modo che vengano restituiti tutti gli elementi. 
    
     - Quando si cerca i siti di SharePoint Online e OneDrive, vengono aggiunti i due componenti seguenti:
    
          **Non IsExternalContent:1** - esclude qualsiasi contenuto da un'organizzazione di SharePoint locale. 
    
          **Non IsOneNotePage:1** - consente di escludere tutti i file di OneNote in quanto tali documenti sono duplicati di qualsiasi documento che corrisponda alla query di ricerca. 

    
    e il numero di percorsi di contenuto (specificato dal * * tipo di posizione * * colonna) che contengono gli elementi che corrispondono alla query di ricerca elencata nella colonna di **Query** . 
    
    f. il numero di elementi (dal percorso specificato contenuto) che corrispondono alla query di ricerca elencata nella colonna di **Query** . Come indicato in precedenza, se un elemento contiene più istanze di una parola chiave che viene ricercato, viene conteggiato una sola volta in questa colonna. 
    
    g. le dimensioni totali di tutti gli elementi che sono state trovate (nel percorso specificato contenuto) che corrispondono alla query di ricerca nella colonna di **Query** . 
    
    **Percorsi principali**
    
    In questa pagina vengono visualizzate le statistiche sul numero di elementi che corrispondono alla query di ricerca in ogni sito di contenuto che è stata eseguita la ricerca. Vengono visualizzate le posizioni prime 1000. Se visualizzare le statistiche per le ricerche più, vengono visualizzate le posizioni di 1.000 superiore di ogni ricerca. Si noti che un percorso di contenuto non è incluso in questa pagina se non contiene gli elementi che corrispondono alla query di ricerca.
    
    ![Statistiche sul numero di elementi presenti nei percorsi contenuti in cui sono stati ricerca](media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    r. il nome del percorso di contenuto.
    
    b. il tipo di percorso contenuto che si applicano alle statistiche di posizione.
    
    c. sono presenti colonne per ogni che si sta visualizzando le statistiche per la ricerca. Questa colonna Visualizza il numero e dimensioni totali degli elementi che corrispondono alla query di ricerca in ogni punto del contenuto. Si noti che, quando si sta visualizzando le statistiche per le ricerche più, "NA" in questa colonna indica che il percorso del contenuto non è stato incluso nella ricerca. 

## <a name="get-keyword-statistics-for-content-searches"></a>Ottenere statistiche sulle parole chiave per le ricerche di contenuto

Precedente come spiegato, nella pagina **delle query** vengono visualizzati la query di ricerca e il numero e dimensione degli elementi che corrispondono alla query. Se si utilizza un elenco delle parole chiave quando si crea o modifica di una query di ricerca, è possibile ottenere le statistiche avanzate che mostra il numero di elementi corrispondenti a ogni parola chiave o una frase parola chiave. Ciò consente di identificare rapidamente le parti della query sono il massimo (e almeno) efficaci. Ad esempio, se una parola chiave restituisce un numero elevato di elementi, è possibile restringere la query con parole chiave per restringere i risultati della ricerca. Quando si crea o modifica di una ricerca di contenuto, è possibile impostare un elenco delle parole chiave. 




  
Per creare un elenco delle parole chiave e visualizzare statistiche sulle parole chiave per la ricerca del contenuto:
  
1. In Office 365 Security &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca del contenuto**.
    
2. Nell'elenco delle ricerche di contenuto, fare clic su e una ricerca e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).
    
3. Fare clic su **Query** e quindi eseguire le operazioni seguenti: 
    
    ![Selezionare la casella di controllo Mostra elenco parola chiave e digitare una parola chiave in ogni riga](media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    r. selezionare la casella di controllo **Mostra elenco di parole chiave** . 
    
    b. digitare una parola chiave o fase parola chiave di una riga della tabella di parole chiave. Ad esempio, digitare **budget** nella prima riga e quindi digitare **protezione** nella seconda riga. 
    
4. Dopo aver aggiunto le parole chiave che si desidera cercare e ottenere le statistiche per, fare clic su **ricerca** per eseguire la ricerca revisionata. 
    
5. Al termine della ricerca, selezionare nell'elenco delle ricerche e quindi fare clic su **statistiche ricerca** ![pulsante statistiche ricerca](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png). È anche possibile visualizzare e confrontare le statistiche sulle parole chiave per le ricerche più.
    
6. Nella pagina **informazioni statistiche sulla ricerca** fare clic su **Query** per visualizzare le statistiche sulle parole chiave per le ricerche selezionati. 
    
    ![Vengono visualizzate le statistiche per ogni parola chiave per le ricerche selezionati](media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Come illustrato nella figura precedente, vengono visualizzate le statistiche per ogni parola chiave. includono: 
    
    - Statistiche sulle parole chiave per ogni tipo di percorso contenuto inclusa nella ricerca.
    
    - Query di ricerca effettivo per ogni parola chiave, che include tutte le condizioni di query di ricerca. 
    
    - La query di ricerca completi (identificati come **primario** nella colonna **parte** ) e le statistiche per la query completa. Si noti che queste sono le stesse statistiche visualizzate nella pagina **Riepilogo** . 

> [!NOTE]
> Per contribuire alla riduzione problemi causati da elenchi di grandi dimensioni parole chiave, l'utente è ora solo per un massimo di 20 righe nell'elenco delle parole chiave di una query di ricerca.
