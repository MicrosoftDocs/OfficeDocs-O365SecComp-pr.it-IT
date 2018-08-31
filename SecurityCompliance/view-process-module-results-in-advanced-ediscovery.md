---
title: Visualizzare i risultati del modulo di processo in Office 365 Advanced eDiscovery
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'Informazioni su come trovare i risultati di un modulo di processo di esecuzione di eDiscovery Office 365 avanzate, tra cui lo stato delle attività e processo di riepilogo.  '
ms.openlocfilehash: 01093b0230aaf78ab7ccf1235f0874a0b69aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530215"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a>Visualizzare i risultati del modulo di processo in Office 365 Advanced eDiscovery

Dopo aver **Prepare** \> **processo** viene avviato, è possibile visualizzare stato e i risultati. 
  
> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="process-task-status"></a>Stato processo attività

In **Prepara** \> **processo** \> **risultati**, nella pagina viene visualizzato lo stato corrente (se processo è in esecuzione) o lo stato dell'ultimo processo stato attività come illustrato nell'esempio seguente.
  
![Stato delle attività del modulo processo](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
Attività visualizzate possono variare in base alle opzioni di processo selezionate. 
  
- **Inventario**: eDiscovery avanzate consente di scorrere tutti i file selezionati per processo ed esegue la raccolta dei dati di base.
    
- **Calcola firme**: consente di calcolare le firme digitali MD5.
    
- **Estrazione composti**: estratti interni o contenuti file ricorsivo dai file composti (ad esempio file PST, ZIP, MSG). Vengono archiviati i file estratti nella cartella maiuscole del case.
    
- **Database di sincronizzazione**: processo di database interno.
    
- **Copia del file**: file di processo copie. Questa operazione viene sempre visualizzata, anche quando è selezionata l'opzione file copia avanzata.
    
- **Estrazione di testo**: quando sono presenti file nativi, eDiscovery avanzate estrae il testo da tali file utilizzando DTSearch. Il testo di questi file estratto viene archiviato come file di testo nella cartella maiuscole.
    
- **Aggiornamento dei metadati**: elabora i metadati caricato. 
    
- **Finalizing**: elaborazione interna che consente di finalizzare dati di caricamento file casi (ad esempio, identificare i file di errore e l'esito positivo). 
    
Stato delle attività: visualizzato dopo il completamento dell'attività. Durante l'esecuzione di attività, viene visualizzata la durata di esecuzione.
  
> [!NOTE]
> Le attività completate possono anche includere totali per l'elaborazione è stata completata o file con errori. 
  
> [!TIP]
> "Annulla" è disponibile l'opzione di rollback per arrestare l'esecuzione del processo e quindi eseguire il rollback al popolamento dati precedente o i dati trasformati salvati. Rollback Cancella i dati trasformati tutti. Se non si desidera i dati trasformati persi (ad esempio, si prevede di ricaricare questi file), opzione selezionare "Annulla" in questa finestra per non si desidera eseguire il rollback. 
  
## <a name="process-summary"></a>Riepilogo processo

In Prepara \> processo \> risultati \> Process riepilogo, una suddivisione dei risultati di file caricato viene visualizzata in base ai risultati elabora e il file ha esito positivo.
  
Riquadri di presentano una visualizzazione grafica delle statistiche di file importato, come indicato di seguito:
  
- **Processo di riepilogo vengono accumulati**: d: tutti i file nel caso.
    
- **Riepilogo del processo ultima**: i file caricati dall'ultima sessione o azione. 
    
- **Ultima famiglie**: informazioni famiglia nel caso (se esistenti).
    
- Se sono stati aggiunti i file di **seeding** , il numero di file di seeding viene elencato per un problema che è stato definito per i file. 
    
    Se il contrassegno di **seeding** file non è riuscita, che viene inoltre specificato. 
    
- Se sono stati aggiunti file **pre-contrassegnati** , è riportato il numero di file pre-contrassegnati per un problema che è stato definito per i file. 
    
    Se il contrassegno di **pre-contrassegnato come** file non è riuscita, che viene inoltre specificato. 
    
![Riepilogo modulo processo](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>Riepilogo processo accumulati e l'ultima grafici

La barra sinistra include i file estratti + origine: ovvero tutti i file disponibili. 
  
Destra della barra, elaborate, include:
  
- File con errori di carico
    
- File caricati correttamente, che possono includere: 
    
  - **Esistente**: i file che sono stati caricati prima e ora caricati nuovamente (compresi i duplicati).
    
  - **Testo**: file univoci con testo.
    
  - **Il testo non**: svuotare i file di testo, i file di testo nativa vuoto, file non testuali nativi. 
    
  - **Duplicare**s: Duplicate file di testo.
    
## <a name="last-process-errors"></a>Ultimi errori dei processi

In Prepara \> processo \> risultati \> ultimi errori dei processi, i dettagli degli errori nell'ultima azione eseguita o sessione vengono visualizzati.
  
![Errori modulo processo](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[In esecuzione il modulo di processo e il caricamento dei dati](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

