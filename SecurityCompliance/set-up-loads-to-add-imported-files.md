---
title: Configurare i gruppi di file per aggiungere i file importati in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: "Rivedere i passaggi per aggiungere i file importati all'ultimo caricamento definita o blocco dei file prima di eseguire formazione pertinenza di Office 365 avanzate eDiscovery.  "
ms.openlocfilehash: 2c986578b969b671351930fd6939a90e3a821dc2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531323"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a>Configurare i gruppi di file per aggiungere i file importati in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In eDiscovery avanzate, un carico è un nuovo batch di file aggiunti a un caso. Per impostazione predefinita, viene definito un carico e tutti i file importati vengono aggiunti a esso. Prima di eseguire formazione pertinenza, file importati devono essere aggiunti al carico. 
  
Prendere in considerazione i seguenti scenari:
  
- Nuovi file sono noti per essere simile al file precedenti caricati nel database maiuscole oppure il caricamento dei file precedente è incluso un insieme casuale dall'insieme di file. In questo caso, aggiungere i file importati per il caricamento del file corrente.
    
- Nuovi file sono diversi da quelli precedenti (ad esempio, da un'origine diversa) o non si conoscono precedenti che utilizzano simili o diversi carichi precedenti. In questo scenario, aggiungere i file importati a un nuovo caricamento di file. EDiscovery avanzate la riconosce come scenario carichi in sequenza, consente di richiamare un processo di aggiornamento, blocca calcoli Batch e formazione di pertinenza fino al completamento dell'aggiornamento e il carico nuovo è integrato e addestrato. 
    
## <a name="adding-imported-files-to-the-current-load"></a>Aggiunta di file importati per il carico corrente

Tutti i file importati devono essere aggiunti a un carico di elaborazione di eDiscovery avanzate. I file importati vengono aggiunte all'ultimo caricamento definito. Se successivamente si importano i file aggiuntivi, devono essere aggiunti anche al carico.
  
1. Nella **pertinenza \> il programma di installazione di pertinenza** selezionare **carichi**.
    
    ![Scheda dei caricamenti per la configurazione di pertinenza](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. **File di inclusione**: selezionare un'opzione per i file da includere. Per impostazione predefinita, l'aggiunta di file per il carico corrente si basa popolazione "Tutti i file".
    
    > [!TIP]
    > Caricare tutti i file riformati disponibili in pertinenza. Se si prevede di caricare solo un sottoinsieme di file disponibili, innanzitutto consultare grazie al supporto, come il caricamento sottoinsiemi può influire negativamente sulle formazione di pertinenza. 
  
3. **Gestione dei carichi**, selezionare un carico.
    
4. Fare clic su **Aggiungi file**. I file vengono aggiunti al carico e viene visualizzato un messaggio di conferma. 
    
5. Fare clic su **OK**.
    
Ora, è possibile elaborare i file di eDiscovery avanzate pertinenza per i file di formazione.
  
## <a name="editing-a-load-name-within-a-case"></a>Un nome di carico all'interno di un caso di modifica

Se la modifica del nome del carico, è consigliabile utilizzare un nome significativo al caso.
  
1. Nella **pertinenza \> il programma di installazione di pertinenza** selezionare **carichi**.
    
2. Dall'elenco di **gestione di carichi** , selezionare un carico e fare clic sull'icona **Modifica** . Viene visualizzata la finestra di modifica del carico. 
    
3. Immettere le modifiche e quindi fare clic su **OK**.
    
## <a name="adding-imported-files-to-a-new-load"></a>Aggiunta di file importato a un nuovo caricamento

Dopo aver avviato formazione pertinenza o la conduzione di calcolo di blocco, è possibile importare ed elaborare un insieme di file aggiuntivo. 
  
Durante l'aggiornamento, possono creare, tag e analizzare l'insieme di aggiornamento. EDiscovery avanzate confronta la valutazione dei file relativo e Non relativo il carico di nuovo a quelli di carichi precedenti. In base ai risultati, viene chiesto di prendere decisioni di aggiornamento, se necessario e avanzata eDiscovery vengono forniti suggerimenti sulla base delle informazioni di pertinenza maturate. 
  
Ripristino dello stato carichi e funzionalità di aggiornamento varia nel modo seguente: 
  
- Quando si importa un nuovo caricamento file dopo il calcolo Batch, eDiscovery avanzate determina in quale misura i file rientrano in una delle categorie seguenti:
    
  - Analogamente (omogenei): non è richiesto un arrotondamento personalizzata del corso di formazione pertinenza e la conoscenza di attribuzione dal carico precedente può essere applicata "così com'è" per il carico di nuovo. 
    
  - DISTINCT (eterogenee): è necessario un arrotondamento personalizzata del corso di formazione pertinenza e la conoscenza di attribuzione dal carico precedente non è possibile applicare. 
    
    Queste condizioni, fare riferimento a livello di similarità dei file tra i carichi di e non all'interno del caricamento. 
    
- Quando si importa un nuovo caricamento di file durante la formazione di pertinenza (prima del calcolo Batch), aggiornamento consente di continuare formazione pertinenza sul set di file united. EDiscovery avanzate non vengono valutati se il carico nuovo è simile a o diverso dal carico precedente. Raccoglie informazioni sulla nuova carico semplicemente e consente la pertinenza di formazione continuare nella nuova e precedente imposta dei file. 
    
- Quando sono presenti più problemi di formazione di pertinenza e problemi dopo il calcolo Batch, il processo di aggiornamento viene eseguito una volta per tutti i problemi e i risultati vengono calcolati e visualizzati per ogni problema.
    
> [!NOTE]
> La dimensione del campione aggiornamento può variare. Dipende dalle dimensioni dei nuovo carico rispetto al caricamento della precedente e al numero di campioni completati prima di aggiungere il nuovo carico. Nell'esempio di aggiornamento in genere è un insieme di file 200 a 2.000 il carico di nuovo. 
  
> [!TIP]
> Aggiornamento degli smette di altre attività e richiede singolo file tagging e revisione. Di conseguenza, è possibile ridurre il sovraccarico quando si aggiungono nuovi file in grandi batch. 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a>Aggiunta di un nuovo caricamento di file tramite aggiornamento e in sequenza carica

1. Nella **pertinenza \> il programma di installazione di pertinenza** selezionare **carichi**.
    
2. **Gestione dei carichi**fare clic sul **+** icona per aggiungere un carico. Viene visualizzato un messaggio di conferma. 
    
3. Fare clic su **Sì** per continuare. Viene visualizzata la finestra di dialogo **Aggiungi nuovo carico** . 
    
    > [!NOTE]
    > È possibile aggiungere un nuovo caricamento solo se le azioni eseguite al carico precedente. 
  
4. Nella finestra di dialogo **Aggiungi nuovo carico** digitare l'informazione da **caricare il nome** e **Descrizione** e quindi fare clic su **OK**. EDiscovery avanzate consente di aggiungere un nuovo caricamento.
    
5. Per importare il nuovo file di carico, fare clic su **Aggiungi file**. Tutti i nuovi file vengono aggiunti a questo carico. Dopo aver eDiscovery avanzate consente di importare i file, riconosce lo scenario di carichi in sequenza e indica aggiornamento come il passaggio successivo.
    
6. Fare clic su **aggiornamento** nella parte inferiore della finestra di dialogo per l'esecuzione dello scenario. 
    
    Un singolo insieme di aggiornamento, in genere che contiene il file di 200 a 2.000 dal carico nuovo, viene creato per tutti i problemi consentire file simultanee tagging.
    
    Vengono fornite informazioni dettagliate su se carichi sono simili o distinti, che eDiscovery avanzate unite o dividere automaticamente i carichi e informazioni per quanto riguarda l'elaborazione nel passaggio successivo.
    
    È possibile quindi contrassegnare i file ed eseguire un'operazione di calcolo. Il contrassegno consente di abilitare pertinenza determinare se i carichi sono simili o distinti e per continuare con il nuovo set di file.
    
7. Una volta viene esaminato il set di aggiornamento, visualizzare **pertinenza \> traccia** per i risultati di aggiornamento. 
    
1. Se durante la formazione di pertinenza è stato aggiunto il nuovo caricamento del file, ovvero, il problema non è stato ancora inviato calcolo Batch, **formazione continua** è il passaggio successivo, indipendentemente dal fatto i risultati di aggiornamento. 
    
    I carichi di nuovi e precedenti vengono elaborati come un caricamento e formazione di pertinenza continua sul set di united. È stata completata con questa procedura e possono continuare formazione pertinenza. 
    
2. Se il carico nuovo è stato aggiunto dopo il calcolo Batch, procedere con la procedura seguente.
    
8. Per i caricamenti di nuovi aggiunti dopo il calcolo Batch, eDiscovery avanzate determina se il carico nuovo è simile a o diverso dal precedente viene caricato, come indicato di seguito:
    
1. Se sono stati trovati carichi simile: non è necessaria alcun formazione aggiuntiva di pertinenza. Viene illustrato il dashboard deve eseguire il passaggio successivo consigliato * * Batch calcolo * * per calcolare i punteggi pertinenza per il carico di nuovo. Carichi sono stati trovati per essere simile, in modo che l'analisi classificatore precedente può essere eseguito sui nuovi file. 
    
2. Se sono stati trovati carichi distinto: formazione di maggiore rilevanza è necessaria e il passaggio successivo consiste decisione di aggiornamento. Selezionare una decisione di aggiornamento nel modo seguente:
    
    Se si seleziona **unire carichi**, eDiscovery avanzate consente di unire i carichi precedenti e nuovi per il set di formazione. Anche se il primo caricamento è stato sottoposto a calcolo Batch, è necessario ulteriore formazione. Continuare formazione insieme carichi nuovi e precedenti. Calcolo batch verrà quindi eseguito nuovamente e devono essere ignorati i punteggi calcolo Batch precedenti. Selezionare questa opzione quando può ricalcolato punteggio di pertinenza del carichi esistenti, ad esempio, quando non è stata avviata esame dei caricamenti di file esistente.
    
    Se si seleziona **diviso carica**, procedere formazione pertinenza solo il carico di nuovo. In questo caso, i punteggi di calcolo Batch precedenti verrà modificata. Scegliere questa opzione quando esistente punteggio di pertinenza del carichi esistenti non possa essere ricalcolato, ad esempio, se è già iniziato esame dei carichi di esistenti. Punteggio di pertinenza viene gestiti separatamente da questo punto in poi e non può essere unite.
    
3. Fare clic su **Continua formazione**.
    
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Definizione dei problemi e assegnazione di utenti](define-issues-and-assign-users.md)
  
[Definizione evidenziate le parole chiave e avanzate opzioni](define-highlighted-keywords-and-advanced-options.md)

