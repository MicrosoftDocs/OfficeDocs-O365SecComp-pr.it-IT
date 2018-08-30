---
title: Preparare i risultati di ricerca per Office 365 Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/10/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: Informazioni su come preparare i risultati di una ricerca di contenuto in Office 365 Security &amp; centro conformità per un'ulteriore analisi con lo strumento eDiscovery avanzate.
ms.openlocfilehash: 4e5668c88d62e99f7a5f40ed2e17f4687a7e9adb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531470"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a>Preparare i risultati di ricerca per Office 365 Advanced eDiscovery

Dopo una ricerca associata a un caso eDiscovery in Office 365 Security &amp; centro conformità viene eseguito correttamente, è possibile preparare i risultati della ricerca per un'ulteriore analisi con Office 365 avanzate eDiscovery, che consente di analizzare grandi dimensioni, dati non strutturati impostato e ridurre la quantità di dati pertinenti per una controversia legale. Le funzionalità avanzate di eDiscovery includono:
  
- **Riconoscimento ottico dei caratteri** - quando si preparano automaticamente i risultati di ricerca per eDiscovery avanzata, la funzionalità di riconoscimento ottico dei caratteri (OCR) estrae il testo da immagini e ciò include con i risultati della ricerca che vengono caricati in a Avanzate eDiscovery per l'analisi. OCR è supportato per file separati, gli allegati di posta elettronica e immagini incorporate. In questo modo è possibile applicare le funzionalità analitiche testo di eDiscovery avanzate (quasi duplicati, posta elettronica threading, temi e la scrittura di codice predittiva) per il contenuto del testo nei file di immagine. 
    
- **Rilevamento quasi duplicati** - è possibile strutturare esaminare dati in modo più efficiente, in modo che una persona viene esaminato un gruppo di documenti simili. Si evita che più revisori la necessità di visualizzare le diverse versioni dello stesso documento. 
    
- **Messaggio di posta elettronica threading** - consente di identificare i messaggi univoci in un thread di posta elettronica in modo che è possibile concentrare l'attenzione sulle nuove informazioni in ogni messaggio. In un thread di posta elettronica, il secondo messaggio contiene il primo messaggio. Allo stesso modo, i messaggi successivi contengono tutti i messaggi precedenti. Messaggio di posta elettronica threading consente di rimuovere la necessità di esaminare ogni messaggio nella sua interezza in un thread di posta elettronica. 
    
- **Temi** - informazioni utili per comprendere i dati di là solo statistiche sulle parole chiave ricerca. Temi Guida indagini raggruppando i documenti correlati in modo che è possibile esaminare i documenti nel contesto. Quando si utilizzano i temi, visualizzare i temi correlati per un set di documenti, determinare qualsiasi sovrapposizione e quindi identificare le sezioni trasversali di dati correlati. 
    
- **Scrittura di codice predittiva** - consente di formare il sistema su ciò che sta cercando, consentendo di decidere (se un elemento è rilevante o non) su un numero ridotto di documenti. EDiscovery avanzata quindi viene applicato tale apprendimento, basato sulla Guida sui, durante l'analisi di tutti i documenti nel set di dati. Basata su tale apprendimento, eDiscovery avanzate fornisce una classificazione della pertinenza in modo che è possibile decidere quali documenti per la revisione in base a quale documento sono probabilmente pertinente al caso. 
    
- **Esportazione dei dati per esaminare le applicazioni** - è possibile esportare dati da eDiscovery avanzate e Office 365 dopo aver completato l'analisi e ridurre il set di dati. Il pacchetto di esportazione include un file CSV che contiene le proprietà dal contenuto esportato e metadati analitica. Il pacchetto di esportazione può quindi essere importato per un'applicazione di revisione eDiscovery. 
    
## <a name="before-you-begin"></a>Informazioni preliminari

- Per analizzare i dati dell'utente tramite eDiscovery avanzate, l'utente (depositaria dei dati) deve essere assegnato una licenza di Office 365 E5. In alternativa, gli utenti con una licenza di Office 365 E1 o E3 è possibile assegnare una licenza autonoma eDiscovery avanzate. Gli amministratori e responsabili della conformità assegnati ai casi e utilizzare eDiscovery avanzate per analizzare i dati non è necessario una licenza E5. 
    
- È necessario essere una eDiscovery Manager o un'amministratore di Office 365 protezione eDiscovery &amp; centro conformità per preparare i risultati della ricerca eDiscovery avanzate. Una ricerca eDiscovery Manager è un membro del gruppo di ruoli di gestione di eDiscovery. Una ricerca eDiscovery amministratore è anche membro del gruppo di ruoli di gestione di eDiscovery, ma è stato assegnato privilegi aggiuntivi eDiscovery. Per istruzioni sull'assegnazione delle autorizzazioni di amministratore di eDiscovery, vedere il passaggio 1 in [casi di eDiscovery nel centro conformità protezione di Office 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>Passaggio 1: Preparare risultati di ricerca per eDiscovery avanzate

È possibile preparare i risultati della ricerca associato a un caso eDiscovery. Quando si prepara i risultati della ricerca eDiscovery avanzate, i dati vengono caricati e temporaneamente archiviati in un'area di archiviazione di Windows Azure univoca nel cloud Microsoft. È a questo punto che la funzionalità OCR estrae il testo da immagini nei risultati della ricerca. In [passaggio 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), il testo e altri ricerca dati risultanti viene caricati in caso di eDiscovery avanzate.
  
1. In sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Accanto al caso in cui si desidera preparare i risultati della ricerca per l'analisi di eDiscovery avanzate fare clic su **Apri** . 
    
3. Nella Home **page per il case,** fare clic su **Cerca**e quindi selezionare la ricerca.
    
4. Nel riquadro dei dettagli **dei risultati di analisi con eDiscovery avanzate**, fare clic su **Risultati preparazione per l'analisi**.
    
    > [!NOTE]
    > Se i risultati di una ricerca hanno più di 7 giorni, viene chiesto di aggiornarli. 
  
5. Nella pagina **Prepara i risultati per l'analisi**, eseguire le operazioni seguenti:  
    
    - Scegliere di preparazione per l'analisi di eDiscovery avanzate elementi indicizzati, gli elementi indicizzati e non indicizzati o solo gli elementi indicizzati.
    
    - Scegliere se includere tutte le versioni dei documenti disponibili in SharePoint che soddisfano i criteri di ricerca. Questa opzione è disponibile solo se le origini di contenuto per la ricerca include siti.
    
    - Consente di specificare se si desidera che un messaggio di notifica inviato o copiata una persona quando viene completato il processo di preparazione e i dati sono pronti per l'elaborazione di eDiscovery avanzate.
    
6. Fare clic su **Prepara**.
    
    I risultati della ricerca vengono preparati per l'analisi con eDiscovery avanzate.
    
7. Nel riquadro dei dettagli fare clic su **verificare lo stato di preparazione** per visualizzare le informazioni sul processo di preparazione. Al termine del processo di preparazione, è possibile accedere al caso di eDiscovery avanzate per elaborare i dati per l'analisi. 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>Passaggio 2: Aggiungere i dati dei risultati della ricerca per il caso di eDiscovery avanzate
<a name="step2"> </a>

Al termine della preparazione, il passaggio successivo è passare a eDiscovery avanzate e caricare i dati dei risultati di ricerca (che sono stati caricati in un'area di archiviazione Azure nel cloud Microsoft) per il caso di eDiscovery avanzate. Come precedentemente illustrato, per accedere a eDiscovery avanzata è necessario essere un'amministratore per la protezione di eDiscovery &amp; centro conformità o da un amministratore di eDiscovery avanzate.
  
> [!NOTE]
> Il tempo necessario per i dati dal titolo &amp; centro conformità sia disponibile per aggiungere a un caso di eDiscovery avanzate varia, a seconda delle dimensioni dei risultati della ricerca eDiscovery. 
  
1. In sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
2. Accanto al caso in cui si desidera caricare i dati di eDiscovery avanzate fare clic su **Apri** . 
    
3. Nella Home **page per il case,** fare clic su **Avanzate eDiscovery**. 
    
    ![Fare clic su passa a eDiscovery avanzate per aprire il caso di eDiscovery avanzate](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Viene visualizzato l'indicatore di stato di **connessione avanzate eDiscovery** . Quando si è connessi a eDiscovery avanzate, viene visualizzato un elenco dei contenitori nella pagina installazione per il case. 
    
    ![Viene visualizzato il caso di eDiscovery avanzate](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Questi contenitori rappresentano i risultati della ricerca preparati per l'analisi di eDiscovery avanzata nel passaggio 1. Si noti che il nome del contenitore ha lo stesso nome di ricerca nel caso della protezione &amp; centro conformità. I contenitori nell'elenco sono quelli preparato. Se un utente diverso preparato risultati della ricerca eDiscovery avanzate, i contenitori corrispondenti non vengono inclusi nell'elenco. 
    
4. Per caricare i dati dei risultati di ricerca da un contenitore in caso di eDiscovery avanzate, selezionare un contenitore e quindi fare clic su **processo**.
    
## <a name="next-steps"></a>Passaggi successivi

Dopo avere i risultati di una ricerca eDiscovery ricerca vengono aggiunti a un caso, il passaggio successivo consiste nell'utilizzare gli strumenti di eDiscovery avanzate per analizzare i dati e identificare il contenuto che risponde a una causa legale. Per informazioni sull'utilizzo di eDiscovery avanzate, vedere [eDiscovery avanzate di Office 365](office-365-advanced-ediscovery.md).
  
## <a name="more-information"></a>Ulteriori informazioni

Eventuali messaggi di posta elettronica crittografati con RMS inclusi nei risultati della ricerca verranno decrittografati durante la preparazione per l'analisi di eDiscovery avanzate. Questa funzionalità decrittografia è abilitata per impostazione predefinita per i membri del gruppo di ruoli di gestione di eDiscovery. Ciò avviene perché il ruolo di gestione di decrittografia RMS viene assegnato a questo gruppo di ruoli. Tenere presenti sulla decrittografia dei messaggi di posta elettronica i seguenti aspetti:
  
- Attualmente, questa funzionalità decrittografia non include crittografato contenuto di SharePoint e OneDrive per i siti. Solo i messaggi di posta elettronica crittografati con RMS verranno decrittografati durante l'esportazione.
    
- Se un messaggio di posta elettronica crittografati con RMS è un allegato (ad esempio, un documento o un altro messaggio di posta elettronica) che viene inoltre crittografato, verrà decrittografato solo il messaggio di posta elettronica principale.
    
- Se è necessario per impedire la decrittografia dei messaggi crittografati con RMS durante la preparazione di risultati della ricerca per l'analisi di eDiscovery avanzate, è necessario creare un gruppo di ruoli personalizzati (copiando eDiscovery gruppo di ruoli di gestione incorporati) e quindi rimuovere il RMS Decrittografare il ruolo di gestione dal gruppo di ruolo personalizzato. Aggiungere la persona che non si desidera decrittografare i messaggi con un account membro del gruppo di ruoli personalizzati.
