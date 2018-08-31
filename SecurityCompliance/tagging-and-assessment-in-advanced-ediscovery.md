---
title: Aggiunta di tag e valutazione in Office 365 Advanced eDiscovery
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Rivedere i passaggi per eseguire la formazione Assessment, inclusi i file di tagging ed esaminare i risultati della valutazione di Office 365 avanzate eDiscovery. '
ms.openlocfilehash: 0f67dd4780a29536888231f556c18fe887f230ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530669"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a>Aggiunta di tag e valutazione in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In questa sezione viene descritta la procedura per il modulo di valutazione della pertinenza eDiscovery avanzate. 
  
## <a name="performing-assessment-training-and-analysis"></a>Esecuzione di analisi e formazione di valutazione

1. Nella **pertinenza \> traccia** fare clic su **Assessment** per avviare assessment maiuscole. 
    
    Ad esempio ai fini di questa procedura, viene creato un set di valutazione di esempio di 500 file e viene visualizzata la scheda **Tag** , che contiene il pannello di Tagging, il contenuto del file visualizzato e altre opzioni tagging. 
    
    ![Scheda Tag pertinenza per la valutazione](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Ogni file di esempio di leggere, determinare la pertinenza del file per ogni problema di maiuscole e contrassegnare il file utilizzando il Relevance (R) non pertinenti (NR) ed evitare i pulsanti nel riquadro **Pannello Tagging** . 
    
    > [!NOTE]
    >  Valutazione richiede 500 file contrassegnati. Se i file sono "ignorati", si riceverà più file al tag. 
  
3. Dopo aver tagging tutti i file nel modello, fare clic su **Calcola**. 
    
    Il margine di errore corrente di valutazione e complessità vengono calcolate e visualizzate nella scheda **Tenere traccia di pertinenza** , con informazioni dettagliate espanse per ogni problema, come illustrato di seguito. Ulteriori informazioni su questa finestra di dialogo sono descritti nella sezione successiva "Risultati valutazioni revisioni". 
    
    ![Traccia di pertinenza: valutazione](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > Per impostazione predefinita, è consigliabile che procedere al passaggio successivo predefinito al termine, l'indicatore di stato di valutazione per il problema per indicare che è stato rivisto il codice di esempio di valutazione e relativi file sufficienti sono stati contrassegnati. > In caso contrario, se si desidera visualizzare i risultati della scheda di **tenere traccia** e controllo margine di errore e il passaggio successivo, fare clic su **Modifica** accanto al **Passaggio successivo**, selezionare **continua valutazione**e quindi fare clic su **OK**. 
  
1. Fare clic su **Modifica** a destra della casella di controllo **Assessment** per visualizzare e specificare i parametri di valutazione per ogni problema. Verrà visualizzata una finestra di dialogo **livello di valutazione** per ogni problema, come illustrato nell'esempio seguente: 
    
    ![Problema relativo al livello di valutazione per il caso](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    I parametri seguenti per il rilascio vengono calcolati e visualizzati nella finestra di dialogo **livello di valutazione** : 
    
    **Margine di errore di destinazione per il richiamo stima**: in base a questo valore, viene calcolato il numero stimato di file aggiuntivi necessari per la revisione. Il margine utilizzato per il richiamo è maggiore di con un livello di probabilità 95% e 75%. 
    
    **I file di valutazione aggiuntive necessarie**: indica il numero di file ulteriori è necessario se non sono stati soddisfatti i requisiti del margine di errore corrente. 
    
2. Per regolare il margine di errore corrente e verificare l'effetto dei margini di errore diverso (per ogni problema):
    
1. Nell'elenco **Selezionare problema** , selezionare un problema. 
    
2. Nel **margine di errore di destinazione per il richiamo stima**, immettere un nuovo valore.
    
3. Fare clic su **Aggiorna i valori** per visualizzare l'impatto delle modifiche. 
    
3. Fare clic su **Avanzate** nella finestra di dialogo **livello di valutazione** per vedere i seguenti parametri aggiuntivi e i dettagli: 
    
    ![Visualizzazione avanzata dei problemi relativi al livello di valutazione per il caso](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    **Complessità stimata**: stimato complessità in base ai risultati della valutazione corrente
    
    **Per il richiamo assunto**: per impostazione predefinita, il margine di errore di destinazione si applica per richiamare il 75%. Se si desidera modificare questo parametro e controllare il margine di errore in un intervallo di valori richiamo diverso, fare clic su **Modifica** . 
    
    **Livello di probabilità**: per impostazione predefinita, il margine di errore consigliato per la probabilità è 95%. Se si desidera modificare questo parametro, fare clic su **Modifica** . 
    
    **Margine di errore previsto complessità**: dati i valori aggiornati, si tratta il margine di errore della completezza previsto dopo vengono esaminati tutti i file di valutazione aggiuntive.
    
    **I file di valutazione aggiuntive necessarie**: in base ai valori aggiornati, il numero di valutazione aggiuntive file che devono essere esaminato per raggiungere la destinazione.
    
    **Valutazione totale file necessari**: dati i valori aggiornati, in totale file assessment necessari per la revisione.
    
    **Numero previsto di file rilevanti nella valutazione**: in base ai valori aggiornati, il numero previsto di file rilevanti nell'intera valutazione dopo che tutti i file di valutazione aggiuntive vengono esaminati.
    
4. Fare clic su **Ricalcola valori**, se sono stati modificati parametri. Al termine, se non esiste un problema, fare clic su **OK** per salvare le modifiche (o **successiva** quando sono presenti più problemi per leggere o modificare, quindi **completare la**). 
    
    Quando sono presenti più problemi, dopo che tutti i problemi sono stati esaminati o modificati, un **livello di valutazione: riepilogo** finestra di dialogo visualizzata come illustrato nell'esempio seguente. 
    
    ![Riepilogo del livello di valutazione](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Dopo il completamento della valutazione, passare alla fase successiva di formazione di pertinenza.
    
## <a name="reviewing-assessment-results"></a>Esaminare i risultati della valutazione

Dopo che è contrassegnato come un esempio di valutazione, i risultati della valutazione vengono calcolati e visualizzati nella scheda tenere traccia di pertinenza.
  
I risultati seguenti vengono visualizzati nella visualizzazione della traccia espansa: 
  
- Margine di errore corrente di valutazione per le stime richiamo
    
- Complessità stimato
    
- File di valutazione aggiuntive necessari (per revisione)
    
Il margine di errore Assessment corrente è il margine di errore consigliato da eDiscovery avanzate. Il numero visualizzato per i file di valutazione aggiuntive"necessari" corrisponde a tale suggerimento.
  
L'indicatore di stato Assessment Mostra il livello di completamento della valutazione, in base al margine di errore corrente. Durante la valutazione è in corso, l'utente verrà contrassegnare un ulteriore esempio di valutazione.
  
Quando l'indicatore di stato assessment viene indicato anche come completata, significa che è stata completata la revisione di esempio valutazione e relativi file sufficienti sono stati contrassegnati. 
  
Visualizzazione della traccia espansa viene illustrato il passaggio successivo consigliato, le statistiche di valutazione e l'accesso a risultati dettagliati.
  
Quando è molto ridotta complessità, il numero di file di valutazione aggiuntive necessarie per raggiungere un numero minimo di file rilevanti per generare statistiche utili è molto alto. EDiscovery avanzate consiglierà quindi passare alla formazione. L'indicatore di stato assessment è ombreggiato e statistiche non sarà disponibile. 
  
In assenza di forma statistica base stabilizzazione, ci sarà risultati con un livello inferiore del livello di affidabilità e accuratezza. Tuttavia, questi risultati possono essere utilizzati per individuare i file necessari quando non è necessario conoscere la percentuale di trovare i file necessari. Analogamente, questo stato utilizzabile per formare problemi con complessità bassa, dove punteggio di pertinenza in grado di accelerare l'accesso ai file rilevanti per un problema specifico.
  
> [!TIP]
> Nella **pertinenza \> traccia** scheda visualizzazione problema espansa, sono disponibili le seguenti opzioni di visualizzazione: > passaggio successivo consigliato, ad esempio **passaggio successivo: Tagging** può essere ignorata (per ogni problema) fare clic sul pulsante **Modifica** per il relativo destra e quindi selezionare un altro passaggio nel **passaggio successivo**. Se l'indicatore di stato assessment non è stata completata, valutazione sarà l'opzione consigliata successivo, tag più file di valutazione e aumentare l'accuratezza statistiche. > È possibile modificare il margine di errore e valutarne l'impatto, fare clic su **Modifica**e nella finestra di **dialogo livello Assessment**modifica il **margine di errore di destinazione per il richiamo stima**e facendo clic su **valori di aggiornamento**. Inoltre, questa finestra di dialogo è possibile visualizzare le opzioni avanzate, facendo clic su **Avanzate**. > È possibile visualizzare le statistiche a livello di valutazione aggiuntive e l'impatto facendo clic su **Visualizza**. Nella finestra di dialogo risultati dettagli visualizzata le statistiche sono disponibili per ogni problema, quando sono presenti file assessment contrassegnati almeno 500 e i file di almeno 18 contrassegnati come relativo per il problema. 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione di pertinenza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e formazione di pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analisi di pertinenza di verifica](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Stabilire in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Test di analisi di pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

