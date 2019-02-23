---
title: Preparare i risultati di ricerca per Office 365 Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: Informazioni su come preparare i risultati di una ricerca di contenuto nel centro sicurezza &amp; e conformità di Office 365 per un'ulteriore analisi con lo strumento eDiscovery avanzato.
ms.openlocfilehash: 04de96064f400f8055d0e477bf41ed1c7cb1b35f
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223845"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a>Preparare i risultati di ricerca per Office 365 Advanced eDiscovery

Dopo aver eseguito correttamente una ricerca associata a un caso di eDiscovery nel centro sicurezza &amp; e conformità di Office 365, è possibile preparare i risultati della ricerca per un'ulteriore analisi con Office 365 Advanced eDiscovery, che consente di analizzare i dati di grandi dimensioni set di dati non strutturati e riduzione della quantità di dati rilevanti per un caso legale. Le funzionalità avanzate di eDiscovery includono:
  
- **Riconoscimento ottico dei caratteri** -quando si preparano i risultati della ricerca per Advanced eDiscovery, la funzionalità OCR (Optical Character Recognition) estrae automaticamente il testo dalle immagini e lo include con i risultati di ricerca caricati in Advanced eDiscovery per l'analisi. OCR è supportato per file sciolti, allegati di posta elettronica e immagini incorporate. In questo modo è possibile applicare le funzionalità analitiche del testo avanzate di eDiscovery (quasi duplicati, Threading di posta elettronica, temi e codifica predittiva) al contenuto di testo nei file di immagine. Advanced eDiscovery OCR supporta i formati seguenti per i file di immagine:

    - GIF
    - JPEG
    - JPG
    - PNG
    - TIFF
    
- **Rilevamento quasi duplicato** : consente di strutturare la revisione dei dati in modo più efficiente, quindi una persona esamina un gruppo di documenti simili. In questo modo è possibile impedire a più revisori di visualizzare versioni diverse dello stesso documento. 
    
- **Threading della posta elettronica** -consente di identificare i messaggi univoci in un thread di posta elettronica in modo da poter concentrarsi solo sulle nuove informazioni in ogni messaggio. In un thread di posta elettronica, il secondo messaggio contiene il primo messaggio. Analogamente, i messaggi successivi contengono tutti i messaggi precedenti. Il threading della posta elettronica rimuove la necessità di esaminare tutti i messaggi nella sua interezza in un thread di posta elettronica. 
    
- **Temi** -informazioni utili per ottenere informazioni importanti sui dati oltre alle statistiche di ricerca di parole chiave. I temi sono utili per l'analisi del raggruppamento di documenti correlati, in modo che sia possibile esaminare i documenti in un contesto. Quando si utilizzano i temi, è possibile visualizzare i temi correlati per un set di documenti, determinare qualsiasi sovrapposizione e quindi identificare sezioni incrociate di dati correlati. 
    
- **Codifica predittiva** : consente di formare il sistema su quello che si sta cercando, consentendo di prendere decisioni (se qualcosa è pertinente o meno) su un set di documenti di piccole dimensioni. Advanced eDiscovery applica quindi l'apprendimento (in base alle linee guida) quando si analizzano tutti i documenti del set di dati. In base a tale apprendimento, Advanced eDiscovery fornisce una classificazione di pertinenza in modo da poter decidere quali documenti esaminare in base a quale documento sono più probabili rilevanti per il caso. 
    
- **Esportazione dei dati per le applicazioni di revisione** : è possibile esportare i dati da Advanced eDiscovery e Office 365 dopo aver completato l'analisi e aver ridotto il set di dati. Il pacchetto di esportazione include un file CSV che contiene le proprietà del contenuto esportato e dei metadati di analisi. Questo pacchetto di esportazione può quindi essere importato in un'applicazione di revisione di eDiscovery. 
    
## <a name="before-you-begin"></a>Informazioni preliminari

- Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata. Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5. 
    
- È necessario essere un Manager di eDiscovery o un amministratore di eDiscovery nel centro sicurezza &amp; e conformità di Office 365 per preparare i risultati della ricerca per Advanced eDiscovery. Un Manager di eDiscovery è un membro del gruppo di ruoli Gestione eDiscovery. Un amministratore di eDiscovery è anche membro del gruppo di ruoli di eDiscovery Manager, ma sono stati assegnati ulteriori privilegi di eDiscovery. Per istruzioni sull'assegnazione delle autorizzazioni di amministratore di eDiscovery, vedere il passaggio 1 in [eDiscovery Cases in the Office 365 Security _AMP_ Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>Passaggio 1: preparare i risultati della ricerca per Advanced eDiscovery

È possibile preparare i risultati di una ricerca associata a un caso di eDiscovery. Quando si preparano i risultati della ricerca per Advanced eDiscovery, i dati vengono caricati e archiviati temporaneamente in un'area di archiviazione di Windows Azure univoca nel cloud Microsoft. È a questo punto che la funzionalità OCR estrae il testo dalle immagini nei risultati della ricerca. Nel [passaggio 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), il testo e gli altri dati dei risultati di ricerca vengono caricati nel caso di Advanced eDiscovery.
  
1. Nel Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **eDiscovery** per visualizzare l'elenco di casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. 
    
3. Nella **Home** page del caso, fare clic su **ricerca**, quindi selezionare la ricerca.
    
4. Nel riquadro dei dettagli, in **Analyze results with Advanced eDiscovery**, fare clic su **prepara i risultati per l'analisi**.
    
    > [!NOTE]
    > Se i risultati di una ricerca hanno più di 7 giorni, viene chiesto di aggiornarli. 
  
5. Nella pagina **Prepara i risultati per l'analisi**, eseguire le operazioni seguenti:  
    
    - Scegliere di preparare gli elementi indicizzati, gli elementi indicizzati e non indicizzati oppure solo gli elementi non indicizzati per l'analisi in Advanced eDiscovery.
    
    - Scegliere se includere tutte le versioni dei documenti trovati in SharePoint che soddisfano i criteri di ricerca. Questa opzione viene visualizzata solo se le origini di contenuto per la ricerca includono siti.
    
    - Specificare se si desidera che un messaggio di notifica venga inviato (o copiato) a una persona al termine del processo di preparazione e che i dati siano pronti per essere elaborati in Advanced eDiscovery.
    
6. Fare clic su **Prepara**.
    
    I risultati della ricerca sono pronti per l'analisi con Advanced eDiscovery.
    
7. Nel riquadro dei dettagli, fare clic su **Controlla stato preparazione** per visualizzare le informazioni sul processo di preparazione. Al termine del processo di preparazione, è possibile passare al caso in Advanced eDiscovery per elaborare i dati per l'analisi. 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>Passaggio 2: aggiungere i dati dei risultati della ricerca al caso in Advanced eDiscovery
<a name="step2"> </a>

Al termine della preparazione, il passaggio successivo consiste nell'accedere a Advanced eDiscovery e caricare i dati dei risultati della ricerca (che sono stati caricati in un'area di archiviazione di Azure nel cloud Microsoft) nel caso in Advanced eDiscovery. Come spiegato in precedenza, per accedere a Advanced eDiscovery è necessario essere un amministratore di eDiscovery nel &amp; centro conformità sicurezza o un amministratore in Advanced eDiscovery.
  
> [!NOTE]
> Il tempo necessario per la disponibilità dei dati del centro &amp; conformità di sicurezza per l'aggiunta a un caso in Advanced eDiscovery varia a seconda delle dimensioni dei risultati della ricerca di eDiscovery. 
  
1. Nel Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **eDiscovery** per visualizzare l'elenco di casi nell'organizzazione. 
    
2. Fare clic su **Apri** accanto al caso in cui si desidera caricare i dati in Advanced eDiscovery. 
    
3. Nella **Home** page del caso, fare clic su **Advanced eDiscovery**. 
    
    ![Fare clic su passa a Advanced eDiscovery per aprire il caso in Advanced eDiscovery](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Viene visualizzata la barra **di avanzamento per la connessione a Advanced eDiscovery** . Quando si è connessi a Advanced eDiscovery, viene visualizzato un elenco di contenitori nella pagina di installazione del caso. 
    
    ![Il caso viene visualizzato in Advanced eDiscovery](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Questi contenitori rappresentano i risultati della ricerca preparati per l'analisi in Advanced eDiscovery nel passaggio 1. Si noti che il nome del contenitore ha lo stesso nome della ricerca nel caso nel centro sicurezza &amp; e conformità. I contenitori presenti nell'elenco sono quelli che sono stati preparati. Se un utente diverso ha preparato i risultati della ricerca per Advanced eDiscovery, i contenitori corrispondenti non verranno inclusi nell'elenco. 
    
4. Per caricare i dati dei risultati di ricerca da un contenitore al caso in Advanced eDiscovery, selezionare un contenitore e quindi fare clic su **processo**.
    
## <a name="next-steps"></a>Passaggi successivi

Dopo aver aggiunto i risultati di una ricerca di eDiscovery a un caso, il passaggio successivo consiste nell'utilizzare gli strumenti avanzati di eDiscovery per analizzare i dati e identificare i contenuti rispondenti a un caso legale specifico. Per informazioni sull'utilizzo di Advanced eDiscovery, vedere [Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md).
  
## <a name="more-information"></a>Ulteriori informazioni

Tutti i messaggi di posta elettronica crittografati con RMS inclusi nei risultati della ricerca verranno decrittografati durante la preparazione per l'analisi in Advanced eDiscovery. Questa funzionalità di decrittografia è abilitata per impostazione predefinita per i membri del gruppo di ruoli eDiscovery Manager. Ciò è dovuto al fatto che il ruolo di gestione deCrypt RMS è assegnato a questo gruppo di ruoli. Tenere presenti le considerazioni seguenti sulla decrittografia dei messaggi di posta elettronica:
  
- Attualmente, questa funzionalità di decrittografia non include il contenuto crittografato dei siti di SharePoint e OneDrive for business. Quando vengono esportati, solo i messaggi di posta elettronica crittografati con RMS verranno decrittografati.
    
- Se un messaggio di posta elettronica crittografato con RMS ha un allegato, ad esempio un documento o un altro messaggio di posta elettronica crittografato, viene decrittografato solo il messaggio di posta elettronica di primo livello.
    
- Se è necessario impedire a un utente di decrittografare i messaggi crittografati con RMS durante la preparazione dei risultati di ricerca per l'analisi in Advanced eDiscovery, sarà necessario creare un gruppo di ruoli personalizzato (copiando il gruppo di ruoli di eDiscovery Manager incorporato) e quindi rimuovere il server RMS DeCrittografare il ruolo di gestione dal gruppo di ruoli personalizzato. Aggiungere quindi la persona che non si desidera decrittografare i messaggi come membro del gruppo di ruoli personalizzato.
