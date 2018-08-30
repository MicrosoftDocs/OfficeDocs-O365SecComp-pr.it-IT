---
title: Tener traccia dell’analisi di Rilevanza in Office 365 Advanced eDiscovery
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Informazioni su come visualizzare e interpretare i risultati per i problemi casi di eDiscovery avanzate di Office 365 e lo stato di formazione di pertinenza.  '
ms.openlocfilehash: a19f7eaabf5dc15eefaa7209ded8261020d0d557
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531455"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a>Tener traccia dell’analisi di Rilevanza in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In eDiscovery avanzate, la scheda di tenere traccia di pertinenza Mostra la validità calcolata di formazione pertinenza eseguita nella scheda Tag e indica il passaggio successivo da eseguire nel processo di formazione iterativo pertinenza. 
  
## <a name="tracking-relevance-training-status"></a>Monitorare lo stato di formazione di pertinenza

1. Visualizzare i dettagli seguenti in pertinenza traccia dei problemi di maiuscole, come illustrato nell'esempio seguente di una finestra di dialogo **nome problema** riportata di seguito. 
    
  - **Valutazione**: questo indicatore di stato indica in quale misura la pertinenza formazione eseguite fino a questo punto ha raggiunto la destinazione di valutazione in termini di margine di errore. Viene visualizzato anche di sfruttare i risultati di formazione di pertinenza. 
    
  - **Formazione**: in questo corso caratterizzata indicatore e descrizione comando è visualizzato il formazione pertinenza dei risultati di stabilità e contrassegnati per ogni problema di una scala numerica indicante il numero di campioni di formazione di pertinenza. Esperto consente di monitorare lo stato di avanzamento del processo di training pertinenza iterativo. 
    
  - **Calcolo batch**: questo indicatore di stato vengono fornite informazioni relative al completamento del calcolo Batch.
    
  - **Passaggio successivo**: viene visualizzato il suggerimento per il passaggio successivo da eseguire. 
    
    Nell'esempio viene visualizzata una valutazione completata correttamente a un problema indicato dall'indicatore di stato completato colore e il segno di spunta. Tagging è in corso, ma il caso viene considerato ancora instabile (come mostrato nella descrizione comando stato stabilità). L'indicazione di passaggio successivo è "Training". 
    
    ![Fase 1 del corso di formazione sulla traccia di pertinenza](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    La visualizzazione espansa Mostra opzioni e le informazioni aggiuntive. Il margine di errore visualizzato corrente è il margine di errore di richiamo nello stato corrente della valutazione, dato i file assessment (già contrassegnati) esistenti.
    
    > [!NOTE]
    >  È possibile ignorare la fase di valutazione, deselezionare la casella di controllo di **valutazione** per ogni problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non ci sarà alcun le statistiche per questo problema. > Deselezionando la casella di controllo **Assessment** può essere eseguita solo prima dell'esecuzione di valutazione. Quando sono presenti più problemi in un caso, valutazione viene ignorato solo se la casella di controllo è deselezionata per ogni problema 
  
    Al termine della valutazione non con assessment potrebbe essere il passaggio successivo per il tagging più file nel primo esempio viene impostata dei file. 
    
    In **pertinenza** \> **traccia**, l'indicatore di stato di formazione e descrizione comando specificare il numero stimato di esempi aggiuntivi necessari per raggiungere la stabilità. Questa stima vengono fornite linee guida per la formazione aggiuntiva necessaria.
    
    ![Corso di formazione sulla traccia di pertinenza](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Una volta tagging fine e se è necessario continuare la formazione, fare clic su **formazione**. Un altro insieme di file di esempio è generato da impostare per la formazione aggiuntiva del file caricato. Vengono restituiti la scheda Tag per contrassegnare e formazione più file.
    
### <a name="reaching-stable-training-levels"></a>Sta per raggiungere i livelli di formazione stabili

I file di valutazione hanno raggiunto un livello stabile del corso di formazione, eDiscovery avanzate è pronto per il calcolo Batch.
  
> [!NOTE]
> In genere dopo tre stabile esempi di formazione, il passaggio successivo è "Calcolo Batch". Potrebbero esserci eccezioni, ad esempio, quando sono state eseguite modifiche per il tagging del file da esempi precedenti o in cui sono stati aggiunti i file di seeding. 
  
### <a name="performing-batch-calculation"></a>Esecuzione di calcolo Batch

Calcolo batch viene eseguito il passaggio successivo al termine formazione correttamente (quando lo stato stabile formazione viene visualizzato dall'indicatore di stato, un segno di spunta e lo stato stabile nella descrizione comando.) Calcolo batch applica le conoscenze acquisite durante la formazione di pertinenza per popolazione intero file, per valutare la pertinenza i file e assegnare punteggio di pertinenza.
  
Quando sono presenti più di un problema, Batch il calcolo viene eseguito per ogni problema. Durante il calcolo Batch, stato di avanzamento viene monitorato durante l'elaborazione di tutti i file. 
  
In questo caso, il passaggio successivo consigliato è "None", che non indica che nessuna formazione pertinenza iterativa aggiuntiva necessaria a questo punto. Fase successiva è il **pertinenza \> stabilire** scheda. 
  
Se si desidera importare nuovi file dopo il calcolo Batch, l'amministratore può aggiungere i file importati a un carico di nuovo.
  
> [!NOTE]
> Se si sceglie **Annulla** durante il calcolo Batch, il processo di Salva quali è stato già eseguito. Se si esegue nuovamente calcolo Batch, il processo verrà completato l'ultimo punto eseguita. 
  
### <a name="assessing-tagging-consistency"></a>Valutazione della coerenza tagging

Se nel file tagging sono presenti incongruenze, può influire l'analisi. Consente di eDiscovery avanzate tagging processo coerenza quando i risultati non sono ottimali o coerenza è in dubbio. Viene restituito un elenco dei file in modo incoerente contrassegnati possibili e può essere esaminati e nuovamente contrassegnati da tag, in base alle esigenze.
  
> [!NOTE]
> Dopo aver sette o più Arrotonda formazione assessment seguente, la coerenza di tagging possono essere visualizzati in **pertinenza** \> **traccia** \> **problema** \> **risultati dettagliati** \> **corso di formazione**. Questa verifica viene eseguita per un problema alla volta. 
  
1. In **pertinenza \> traccia**, espandere la riga del problema.
    
2. A destra del **passaggio successivo**, fare clic su **Modifica**.
    
3. Selezionare **le incoerenze di Tag** all'opzione **passaggio successivo** , dopo aver sette esempi di formazione e fare clic su **OK**.
    
4. Selezionare **le incoerenze di Tag**. Viene visualizzata la scheda **Tag** un elenco di incongruenze nuovamente contrassegnare in base alle esigenze. 
    
5. Fare clic su **Calcola** per inviare le modifiche. Il passaggio successivo tagging incoerenze è "Training". 
    
## <a name="viewing-and-using-relevance-results"></a>Visualizzazione e utilizzo dei risultati di pertinenza

Nella **pertinenza \> traccia** la scheda, espandere la riga del problema e accanto a **risultati dettagliati**, fare clic su **Visualizza**. I riquadri risultati dettagliati sono visualizzate, come illustrato e descritto di seguito.
  
![Risultati dettagliati della formazione sulla pertinenza](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Tagging di riepilogo

 Nell'esempio riportato di seguito, il **Riepilogo utilizzo dei tag** vengono visualizzati i totali per ognuno di valutazione, formazione e file di aggiornamento contrassegno processi. 
  
![Riepilogo tagging della traccia di pertinenza](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Parole chiave

Una parola chiave è una stringa univoca, word, frase o sequenza di parole in un file identificato da eDiscovery avanzate come indicatore significativo se di un file è pertinente. Le colonne "Include" elencano pesi nei file contrassegnati come relativo e parola chiave e le colonne "Escludere" sono elencate le parole chiave e spessori nei file contrassegnati come non rilevanti.
  
EDiscovery avanzate assegna dei valori di peso parola chiave positiva o negativa. Più è alto il peso, maggiore sarà la probabilità che un file in cui viene visualizzata la parola chiave viene assegnato un punteggio di pertinenza durante il calcolo Batch. 
  
L'elenco di eDiscovery avanzata delle parole chiave può essere utilizzato per integrare un elenco creato da un esperto o come un test di integrità indiretti in qualsiasi punto nel file del processo di revisione.
  
### <a name="training-progress"></a>Corso di formazione

Nel riquadro di **Corso di formazione** include una formazione stato grafico e qualità indicatore display, come illustrato nell'esempio riportato di seguito. 
  
![Stato di avanzamento del corso di formazione sulla traccia di pertinenza](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 **Formazione indicatore di qualità**: la classificazione della coerenza tagging come indicato di seguito:
  
- **Buona**: file contrassegnati in modo coerente. (Verde chiaro visualizzati)
    
- **Medio**: alcuni file possono essere contrassegnati in modo incoerente. (Visualizzato di colore giallo chiaro)
    
- **Avviso**: numero di file potrebbe essere contrassegnati in modo incoerente. (Spia rossa visualizzata)
    
 **Grafico di corso di formazione**: viene illustrato il grado di stabilità della formazione pertinenza dopo un numero di cicli di formazione di pertinenza rispetto a quando il valore di misura F. Si sposta da sinistra a destra sul grafico, consente di restringere l'intervallo di confidenza e viene utilizzata insieme F-misura, da eDiscovery avanzate pertinenza per determinare la stabilità sono ottimizzate quando la formazione pertinenza dei risultati.
  
> [!NOTE]
> Pertinenza utilizza F2, una metrica F misura in cui richiamo riceve del doppio spessore come precisione doppia. Per i casi con complessità alta (oltre 25%), viene utilizzata la pertinenza F1 (rapporto 1:1). Il rapporto F misura può essere configurato nelle **impostazioni di pertinenza** \> **Impostazioni avanzate**. 
  
### <a name="batch-calculation-results"></a>Risultati del calcolo batch

Riquadro **dei risultati di calcolo Batch** include il numero di file che sono stati punteggio di pertinenza, come indicato di seguito: 
  
- **Success**
    
- **Vuoto**: non contiene testo, ad esempio, solo gli spazi/schede
    
- **Operazione non riuscita**: a causa di dimensioni eccessive o non è stato possibile leggere
    
- **Ignored**: a causa di dimensioni eccessive
    
- **Nebulous**: contiene testo privo di significato o nessuna funzionalità pertinente al problema
    
> [!NOTE]
> Vuoto, non superato, Ignored o Nebulous riceverà un punteggio di pertinenza-1. 
  
### <a name="training-statistics"></a>Statistiche di formazione

Il riquadro delle **statistiche di formazione** consente di visualizzare le statistiche e grafici in base ai risultati di formazione di pertinenza eDiscovery avanzate. 
  
![Statistiche del corso di formazione sulla traccia di pertinenza](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Consente di visualizzare le operazioni seguenti:
  
- **Rapporto richiamo revisione**: confronto tra i risultati in base alla pertinenza punteggi una revisione registrare lineare. Richiamo stima assegnato il set di dimensioni di set di revisione.
    
- **Parametro**: cumulativo calcolate le statistiche relative alla revisione imposta in relazione alla popolazione di file per il case intero.
    
- **Esaminare**: percentuale di file da esaminare basato su questo limite.
    
- **Richiamo**: percentuale del relativo file nel set di revisione. 
    
- **Distribuzione per punteggio di pertinenza**: file visualizzati in grigio scuro a sinistra nella sono sotto il limite punteggio. Descrizione comando viene visualizzato il punteggio di pertinenza e la percentuale correlata dei file nel file di revisione impostato in base al numero totale di file.
    
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione di pertinenza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Esecuzione e la revisione di valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Esecuzione di formazione di pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Le decisioni basate sui risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Test di analisi di pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

