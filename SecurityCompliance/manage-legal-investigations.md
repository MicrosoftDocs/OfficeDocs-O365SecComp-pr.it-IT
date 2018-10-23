---
title: Gestire indagini legale in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: Utilizzare casi di eDiscovery in Office 365 Security &amp; centro conformità per gestire indagini legale dell'organizzazione. Se si dispone di una sottoscrizione E5, è possibile analizzare ulteriormente maiuscole dati utilizzando l'analitica testo, l'apprendimento e funzionalità di codifica predittiva di eDiscovery avanzate.
ms.openlocfilehash: 4e7b9117b3f0cb2fd6d4e70a7767f3cbe7b79724
ms.sourcegitcommit: 01813cb9bbc2400d21bc99144745af953f9356e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2018
ms.locfileid: "25719050"
---
# <a name="manage-legal-investigations-in-office-365"></a>Gestire indagini legale in Office 365

Le organizzazioni sono diversi i motivi per rispondere a un caso legale che coinvolgono determinati dirigenti o altri dipendenti dell'organizzazione. Ciò potrebbe comportare rapidamente la ricerca e la conservazione per un'ulteriore indagini informazioni specifiche nella posta elettronica, documenti, conversazioni di messaggistica immediata e altri percorsi di contenuti utilizzati dagli utenti nelle attività quotidiane. È possibile eseguire queste e molte altre attività simili utilizzando gli strumenti casi di eDiscovery in Office 365 Security &amp; centro conformità.
  
[Gestire indagini legali con casi di eDiscovery](#manage-legal-investigations-with-ediscovery-cases)
  
[Analisi dei dati maiuscole con Office 365 avanzate eDiscovery](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**Desidera conoscere il modo in cui Microsoft gestisce le ricerche eDiscovery?** Ecco un [white paper tecnico](https://go.microsoft.com/fwlink/?linkid=852161) che è possibile scaricare in cui viene illustrato come è utilizzare gli stessi strumenti di ricerca e analisi di Office 365 per gestire i flussi di lavoro di eDiscovery interno.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gestire indagini legali con casi di eDiscovery

eDiscovery casi consentono di controllare chi può creare, accedere e gestire casi di eDiscovery nell'organizzazione. Casi di utilizzo per aggiungere membri e controllo quali tipi di azioni può eseguire, impostare un blocco sui percorsi di contenuti rilevanti per una controversia legale e utilizzare lo strumento di ricerca di contenuto per i percorsi di ricerca in attesa per il contenuto che potrebbe essere risponde al caso. È quindi possibile esportare e scaricare i risultati per un'analisi più approfondita dai revisori esterni. Se l'organizzazione Office 365 dispone di una sottoscrizione E5, è inoltre possibile preparare i risultati della ricerca per l'analisi di eDiscovery avanzate.
  
- [Gestisci flusso di lavoro eDiscovery](ediscovery-cases.md) dalla creazione e utilizzo dei casi di eDiscovery per ogni persona indagini l'organizzazione dispone di intraprendere 
    
- [Assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md) per controllare chi può creare e gestire casi di eDiscovery nell'organizzazione 
    
- [Separazione di conformità](set-up-compliance-boundaries.md) per controllare l'utente i percorsi di contenuti che possono eseguire ricerche eDiscovery Manager 
    
- [Ricerca di contenuto](search-for-content.md) all'interno dell'organizzazione 
    
- [Prepara il contenuto sociale eDiscovery avanzate](prepare-search-results-for-advanced-ediscovery.md) non è possibile eseguire analisi dell'utilizzo potenti analitico strumenti di eDiscovery avanzati, ad esempio riconoscimento ottico dei caratteri, threading posta elettronica e la scrittura di codice predittiva 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Utilizzare gli script per scenari avanzati

Come la sezione precedente elencati gli script per gli scenari di ricerca del contenuto, abbiamo inoltre creato alcuni sicurezza &amp; script di PowerShell centro conformità per la gestione dei casi eDiscovery.
  
- [Crea un eDiscovery report esenzioni](create-a-report-on-holds-in-ediscovery-cases.md) che contiene informazioni su tutti i contiene associato ai casi di eDiscovery nell'organizzazione 
    
- [Aggiunta delle cassette postali e percorsi di OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) per un elenco di utenti di una ricerca eDiscovery archiviazione 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>Analisi dei dati maiuscole con Office 365 avanzate eDiscovery

EDiscovery avanzate di Office 365 si basa sulle funzionalità di ricerca ed eDiscovery contenuta descritta nelle sezioni precedenti. Dopo aver creato un caso di eDiscovery, posto depositaria in attesa e raccogliere dati che potrebbero essere risponde al caso, è quindi possibile ulteriormente analizzare i dati utilizzando analitica testo, la macchina di apprendimento e le funzionalità di codifica predittive di avanzate eDiscovery. Ciò consente all'organizzazione elaborare rapidamente migliaia di messaggi di posta elettronica, documenti e altri tipi di dati per trovare solo gli elementi che sono probabilmente più rilevanti per un caso specifico. Ed è stata unificata avanzata eDiscovery e la gestione dei casi in modo che è possibile gestire facilmente lo stesso caso all'interno della protezione &amp; centro conformità.
  
> [!NOTE]
> Per analizzare i dati dell'utente tramite eDiscovery avanzate, l'utente (depositaria dei dati) deve essere assegnato una licenza di Office 365 E5. In alternativa, gli utenti con una licenza di Office 365 E1 o E3 è possibile assegnare una licenza autonoma eDiscovery avanzate. Gli amministratori e responsabili della conformità assegnati ai casi e utilizzare eDiscovery avanzate per analizzare i dati non è necessario una licenza E5. 
  
### <a name="get-started"></a>Per iniziare

Il modo più rapido per iniziare a utilizzare eDiscovery avanzate consiste nel creare un caso e preparare i risultati della ricerca in sicurezza &amp; centro conformità, caricare i risultati di eDiscovery avanzate e quindi eseguire analisi Express per l'analisi che caso dati ed esportare il risultati per la revisione esterna.
  
- [Viene fornita una rapida panoramica](quick-setup-for-advanced-ediscovery.md) del flusso di lavoro eDiscovery avanzate 
    
- [Impostare gli utenti e dei casi](set-up-users-and-cases-in-advanced-ediscovery.md) eDiscovery avanzate mediante la creazione di un caso, l'assegnazione di autorizzazioni di eDiscovery e aggiungendo caso membri, tutte le utilizzando la protezione &amp; centro conformità 
    
- [Preparazione e carico cercare i dati](prepare-data-for-advanced-ediscovery.md) in caso di eDiscovery avanzate 
    
- [Caricare i dati non Office 365](import-non-office-365-data-into-advanced-ediscovery.md) in un caso per l'analisi di eDiscovery avanzate 
    
- [Analisi dell'uso Express](use-express-analysis-in-advanced-ediscovery.md) per analizzare rapidamente i dati in un caso ed esportare facilmente i risultati 
    
### <a name="analyze-data"></a>Analisi dei dati

Dopo il caricamento di dati di ricerca in caso di eDiscovery avanzate, si utilizzerà la funzionalità di analisi per avviare l'analisi. La prima parte del processo di analisi è costituita organizzazione dei file in gruppi di file univoci, duplicati e quasi duplicati (noto anche come similarità documento). Quindi verrà organizzare nuovamente i dati in gruppi struttura gerarchica dei thread di posta elettronica e temi e, facoltativamente, set ignorare filtri di testo da escludere determinato testo dall'analisi. Si verrà quindi eseguire l'analisi e visualizzare i risultati.
  
- [Informazioni sui similarità documento](understand-document-similarity-in-advanced-ediscovery.md) per prepararsi per l'analisi dei dati di eDiscovery avanzate 
    
- [Impostare le opzioni](set-analyze-options-in-advanced-ediscovery.md) per quasi duplicati, temi e posta elettronica threading e quindi eseguire la funzionalità di analisi 
    
- [Impostare i filtri Ignora testo](set-ignore-text-in-advanced-ediscovery.md) per escludere il testo e stringhe di testo da analizzata; Questi filtri ignorerà testo anche quando si esegue l'analisi di pertinenza 
    
- [Visualizzare i risultati](view-analyze-results-in-advanced-ediscovery.md) del processo di analisi 
    
- [Configurare le impostazioni avanzate](set-analyze-advanced-settings-in-advanced-ediscovery.md) per l'elaborazione dell'analisi 
    
### <a name="set-up-relevance-training"></a>Configurazione di formazione di pertinenza

Stima la scrittura di codice (denominata pertinenza) nella scheda Avanzate eDiscovery consente di formare il sistema su ciò che sta cercando grazie alla possibilità di per decidere (se un elemento è rilevante o non) su un numero ridotto di documenti.
  
- [Informazioni sull'impostazione di formazione di pertinenza](manage-relevance-setup-in-advanced-ediscovery.md) , file di interesse per un caso di tagging e la definizione case dei problemi 
    
- [Definire case problemi](define-issues-and-assign-users.md) e assegnare ogni problema a un utente che di formare i file 
    
- [Aggiungere i file importati a carico corrente o nuovo](set-up-loads-to-add-imported-files.md) che verrà aggiunto alla formazione pertinenza; un carico è un nuovo batch di file che vengono aggiunti a un caso e quindi utilizzati per la formazione di pertinenza 
    
- [Definire evidenziate le parole chiave](define-highlighted-keywords-and-advanced-options.md) che è possibile aggiungere alla formazione pertinenza; Consente di identificare meglio i file di interesse per un caso 
    
### <a name="run-the-relevance-module"></a>Eseguire la funzionalità di pertinenza

Dopo aver set di backup di formazione, si è pronti per eseguire la funzionalità di pertinenza e valutare l'efficacia delle impostazioni di formazione il risultato è una classificazione per pertinenza che consente di stabilire se è necessario eseguire formazione aggiuntiva oppure se si è pronti per avviare tagging come file rilevanti al caso.
  
- [Informazioni sul processo di pertinenza](use-relevance-in-advanced-ediscovery.md) e il processo di valutazione iterativo, tagging, analisi e formazione nuovamente in base insieme di file di esempio 
    
- [Informazioni sulla valutazione](assessment-in-relevance-in-advanced-ediscovery.md) , dove esperto con il caso viene esaminata una serie di file sociale e determina l'efficacia della formazione pertinenza 
    
- [Valutare i file maiuscole](tagging-and-assessment-in-advanced-ediscovery.md) per calcolare l'efficacia (denominato *complessità* ) di impostazioni di formazione e file tag come rilevanti o non rilevanti per il case; Consente di determinare se la formazione corrente è sufficiente oppure se è necessario regolare le impostazioni di formazione. 
    
- [Esegui la formazione pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md) dopo la valutazione è stato completato e quindi ancora una volta tag file come rilevanti o non rilevanti per i problemi che è stato definito per il case 
    
- Processo di [tenere traccia dell'analisi di pertinenza](track-relevance-analysis-in-advanced-ediscovery.md) per determinare se formazione pertinenza ha raggiunto la destinazione assessment (noto come è *stato stabile addestramento* ) o se è necessaria ulteriore formazione; è inoltre possibile visualizzare i risultati di pertinenza per ogni problema di maiuscole 
    
- [Prendere decisioni basate sull'analisi di pertinenza](decision-based-on-the-results-in-advanced-ediscovery.md) per determinare che le dimensioni del set di risultante del case file che possono essere esportati per la revisione 
    
- [La qualità dell'analisi della pertinenza di test](test-relevance-analysis-in-advanced-ediscovery.md) per convalidare l'eliminazione selettiva decisioni prese durante il processo di pertinenza 
    
### <a name="export-results"></a>Esportare i risultati

Il passaggio finale di analisi dei dati sui casi di eDiscovery avanzate è per esportare i risultati dell'analisi per la revisione esterna.
  
- [Informazioni sull'esportazione di dati maiuscole](export-case-data-in-advanced-ediscovery.md)
    
- [Esportare dati maiuscole](export-results-in-advanced-ediscovery.md)
    
- [Visualizzare la cronologia di blocco e l'esportazione dei risultati passati](view-batch-history-and-export-past-results.md)
    
- [Esportare i campi del report](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>Altri strumenti di eDiscovery avanzate

EDiscovery avanzate sono disponibili ulteriori strumenti e le funzionalità più analisi dei dati maiuscole, analisi di pertinenza ed esportazione di dati.
  
- [I rapporti di eDiscovery avanzate](run-reports-in-advanced-ediscovery.md)
    
- [Definire le impostazioni di maiuscole e minuscole e tenant](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [Utilità di eDiscovery avanzate](use-advanced-ediscovery-utilities.md)
