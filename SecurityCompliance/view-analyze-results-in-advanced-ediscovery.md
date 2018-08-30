---
title: Visualizzare Analizza i risultati in Office 365 Advanced eDiscovery
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Acquisire familiarità con la posizione in cui visualizzare i risultati del processo di analisi di eDiscovery Office 365 avanzate, tra cui le definizioni delle opzioni attività visualizzata.  '
ms.openlocfilehash: 8f1de53e5548c8721f8fbfdb83374edb18379114
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531186"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>Visualizzare Analizza i risultati in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In eDiscovery avanzate, stato e i risultati per il processo di analisi possono essere visualizzati in una vasta gamma di vengono visualizzate come descritto di seguito.
  
## <a name="view-analyze-task-status"></a>Visualizzare lo stato dell'attività di analisi

In **Prepare \> Analizza \> risultati \> stato delle attività**, lo stato viene visualizzato durante e dopo l'esecuzione del processo di analisi. 
  
![Analizzare lo stato delle attività](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
Le attività visualizzate possono variare in base alle opzioni selezionate. 
  
- **ND/ET: il programma di installazione**: consente di preparare per l'esecuzione, ad esempio, imposta i parametri di esecuzione e maiuscole.
    
- **ND/ET: calcolo ND**: analisi quasi duplicati dei processi dei file.
    
- **ND/ET: calcolo ET**: analisi dei Thread di posta elettronica esegue sul set di posta elettronica intero.
    
- **ND/ET: tabelle pivot e le analogie**: esegue pivot ed elaborazione similarità file.
    
- **ND/ET: aggiornamento dei metadati**: consente di finalizzare i nuovi dati raccolti nei file di database.
    
- **Temi: calcolo temi**: esegue l'analisi dei temi. (Visualizzata solo se è selezionata)
    
- **Stato attività**: questa riga viene visualizzata dopo il completamento dell'attività. Durante l'esecuzione di attività, viene visualizzata la durata di esecuzione.
    
> [!NOTE]
> I risultati di analisi di quasi duplicati e thread di posta elettronica (ND ed ED) si applica al numero di documenti da elaborare. Non include i file duplicati esatti. 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>Visualizzare lo stato quasi duplicati e thread di posta elettronica

I risultati di **destinazione** della popolazione visualizzano il numero di documenti, messaggi di posta elettronica, gli allegati e gli errori della popolazione di destinazione. 
  
I risultati di **documenti di** visualizzano il numero di tabelle pivot, univoci quasi duplicati e i file duplicati esatti. 
  
I risultati **tramite posta elettronica** di visualizzare il numero di inclusi, inclusi meno copie inclusi univoche e il resto dei messaggi di posta elettronica. Diversi tipi di risultati di posta elettronica sono: 
  
- **Inclusivo**: un messaggio di posta elettronica inclusivo è il nodo finale in un thread di posta elettronica e contiene tutta la cronologia precedente di thread. Di conseguenza, il revisore in modo sicuro può concentrarsi sulla posta elettronica inclusivo, senza la necessità di leggere i messaggi precedenti nel thread. 
    
- **Inclusivo meno**: un messaggio di posta elettronica inclusivo viene designato come sottrazione inclusi se esistono uno o più allegati diversi associati a elementi padre del messaggio inclusivo. In questo contesto, il termine che padre viene utilizzato per i messaggi posizionati verso l'alto nel thread di posta elettronica o conversazioni incluso in tale posta elettronica inclusivo specifico. Il revisore può utilizzare inclusi meno indicazione come un segnale che anche se potrebbero non essere necessaria controllare il contenuto di elementi padre di posta elettronica inclusi, potrebbe essere utile esaminare gli allegati associati i padri percorso inclusi. 
    
- **Copia inclusivo**: un messaggio di posta elettronica inclusivo viene designato come copia inclusivo in questo caso la copia di un altro messaggio contrassegnato come inclusi o inclusi meno. In altre parole, il messaggio ha lo stesso oggetto e il corpo sotto forma di un altro messaggio inclusivo e, in quanto tale, condivisa si trova nello stesso nodo. Dal momento che i messaggi inclusi copia contengono lo stesso contenuto, è possibile saltare in genere nel processo di revisione. 
    
- **Nella parte restante**: indica posta elettronica che non contiene alcun contenuto univoco e pertanto non possono essere suddivisi in uno dei tre categorie precedenti. Questi messaggi di posta elettronica non necessario per la revisione. Se il messaggio contiene un allegato che non è in una versione successiva inclusivo messaggio di posta elettronica, l'allegato potrebbe essere necessario per la revisione. In questo caso viene l'esistenza di un inclusi meno posta elettronica all'interno del thread.
    
I risultati di **allegati** Mostra il numero di allegati, in base a tale tipo come univoci e duplicati. 
  
![Risultati quasi duplicati e thread di posta elettronica](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sui similarità documento](understand-document-similarity-in-advanced-ediscovery.md)
  
[Impostazione delle opzioni di analisi](set-analyze-options-in-advanced-ediscovery.md)
  
[Impostazione Ignora testo](set-ignore-text-in-advanced-ediscovery.md)
  
[Impostazioni avanzate di analisi di impostazione](view-analyze-results-in-advanced-ediscovery.md)

