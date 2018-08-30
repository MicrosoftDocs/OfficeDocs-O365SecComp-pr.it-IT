---
title: Eseguire il modulo di processo in Office 365 Advanced eDiscovery
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: "Scopri le linee guida per maiuscole preparazione dei file di dati di Office 365 per l'analisi con Office 365 avanzate eDiscovery.  "
ms.openlocfilehash: 52b1dce9fb778c6628d90c39135f0c93f08134d7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531351"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a>Eseguire il modulo di processo in Office 365 Advanced eDiscovery

File maiuscole vengono caricati in eDiscovery avanzate durante **Prepara** \> **processo**. 
  
> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>Linee guida: Preparazione dei dati per eDiscovery avanzate

- **Qualità**: identificare chiaramente popolazione file maiuscole pertinenti al caso.
    
- **Carichi**: caricare i file in un percorso accessibile a eDiscovery avanzate.
    
- **ID del file**: un identificatore di file univoco di eDiscovery avanzate. Se nessun identificatore file importato, eDiscovery avanzate genera automaticamente l'ID. Se si eseguire il mapping dell'ID nel caricamento processo successivo e mappare un percorso diverso dal carico di processo iniziale, eDiscovery avanzate verrà sostituire il percorso (anziché aggiungere una nuova voce del file). Consente l'ID come riferimento nel processo di esportazione. Il valore ID non deve essere "-1".
    
- **MD5**: la firma viene utilizzata per distinguere i file (due file non sono considerati duplicati a meno che non hanno la stessa MD5). Per impostazione predefinita, eDiscovery avanzate calcola MD5 dei file. Quando i file caricati sono file di testo, è consigliabile per caricare e mappare il valore MD5 originale anziché il calcolo di eDiscovery avanzate.
    
- **Nome e tipo di file**:
    
  - Avanzate eDiscovery può del processo di diversi formati file ed estrarre i file di nativi caricati in un formato standard, ad esempio \*. TXT, HTML o. XML. l'elaborazione dei file di testo è più rapido rispetto ai file nativi. File di testo estratto vengono archiviati nella cartella maiuscole.
    
  - Non caricare i file che non possono essere estratti, ad esempio i file di sistema o immagini grafiche. Questi file potrebbero ritardare l'elaborazione.
    
  - Verificare che i nomi di file in modo significativo sono denominati e percorsi siano corretti.
    
- **Percorso del file**: avanzate eDiscovery può caricare file con le lunghezze dei percorsi fino a 400 caratteri.
    
- **Estrazione di testo**: anche estratto durante l'estrazione di testo dal file nativi, oltre al testo normale, le operazioni seguenti: colonne di testo nascosto, Excel e file con estensione doc, nascosta (Excel), tenere traccia delle modifiche (con estensione doc), gli oggetti di Lotus notes (con estensione ppt) incorporato altoparlante (ad esempio, Oggetti di Excel in un file con estensione ppt). Questi possono essere visualizzati nell'editor di testo.
    
- **Ignora testo**: questa funzionalità facoltativa è definita dopo l'esecuzione di processo e prima dell'analisi. Ignora testo deve essere utilizzato con attenzione perché il suo utilizzo può consentire una riduzione delle prestazioni di analisi del file.
    
- **Testo multilingue**: eDiscovery avanzate non è attualmente la nomi in più lingue per i tag, depositaria e problemi.
    
- **Metadati**: determinare se esiste metadati che si desidera salvare nel database di maiuscole per riferimento futuro, ad esempio l'intervallo di date, dimensioni dei file, tipo di file, depositaria e del soggetto. Metadati possono essere caricati dopo che i file sono stati già caricati senza eseguire nuovamente l'inventario o aggiunta di rielaborare sovraccarico. 
    
  - Se i file di origine sono stati caricati dal percorso, eseguire il mapping nella colonna percorso durante l'importazione di metadati più avanti. È possibile fare riferimento al file in base all'ID ed eseguire il mapping di un percorso diverso. Si tratta di uno scenario utile quando modificano i percorsi dei file.
    
  - Se i file di origine sono stati caricati in base all'ID di File, eseguire il mapping della colonna ID durante il caricamento dei metadati. Per il riferimento al file path (anziché ID) determinerà i file da caricare nuovamente con un ID diverso. EDiscovery avanzate consente di creare copie dei file piuttosto che il caricamento metadati dei file esistenti.
    
- **Famiglie**: non è possibile caricare una famiglia senza padre (testa della famiglia). 
    
- **Dimensione del file**: non esiste alcun limite le dimensioni dei file caricato in eDiscovery avanzate. Per l'analisi (analisi, pertinenza e così via), il limite è 5.242.880 caratteri del testo estratto. File di dimensioni maggiori vengono ignorato (ad esempio, di pertinenza, i file non fanno parte del processo di formazione di pertinenza e non ricevono un punteggio di pertinenza dopo il calcolo batch).
    
- **Quantità di file**: non esiste alcun limite consigliato al numero di file che possono essere gestiti in un singolo caso. Le prestazioni dipendono le risorse del sistema. 
    
## <a name="filtering-files"></a>Il filtraggio dei file

Un'etichetta definita dall'utente può essere associata a un insieme di file da escludere loro dal processo o altre attività. Ogni sessione processo è associato un ID batch. Sebbene l'ID del blocco non è visibile all'esperto di pertinenza, questa operazione può essere eseguita utilizzando un'utilità di ricerca aggiungendo un filtro per il batch corrente e tagging tutti i file appropriati con un'etichetta definita dall'utente. 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[In esecuzione il modulo di processo e il caricamento dei dati](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[Visualizzazione dei risultati modulo processo](view-process-module-results-in-advanced-ediscovery.md)

