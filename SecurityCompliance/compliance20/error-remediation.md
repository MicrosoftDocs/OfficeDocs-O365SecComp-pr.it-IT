---
title: Risoluzione dei problemi di errore durante l'elaborazione dei dati
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 82e6d44ded64d586611f429f9b3eebe4f47e9898
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607946"
---
# <a name="error-remediation-when-processing-data"></a>Risoluzione dei problemi di errore durante l'elaborazione dei dati

Risoluzione dei problemi errore consente agli amministratori di eDiscovery la possibilità di risolvere i problemi di dati che impediscono l'elaborazione correttamente il contenuto eDiscovery avanzate (Preview). Ad esempio, i file protetti da password non possono essere elaborati poiché i file sono bloccati o crittografati. Utilizzo di correzione di errori, gli amministratori di eDiscovery possono scaricare i file con tali errori, rimuovere la password di protezione e caricare i file le.

Utilizzare il flusso di lavoro seguente per correggere i file con errori in casi di eDiscovery avanzate (Preview).

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Creazione di una sessione di risoluzione dei problemi di errore per correggere i file con errori di elaborazione

>[!NOTE]
>Se l'in qualsiasi momento durante la procedura seguente viene chiusa la procedura guidata correzione dei problemi di errore, è possibile restituire alla sessione di risoluzione dei problemi di errore nella scheda **elaborazione** selezionando **rimedi errore** nel menu a discesa **Visualizza** .

1. Selezionare **gli errori** nel menu a discesa **Visualizza** scheda **elaborazione** in un caso eDiscovery avanzate (Preview).

2. Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o tipo di file.  Nell'esempio seguente viene stiamo monitorare e aggiornare un file protetto da password.

3. Fare clic su **+ Nuovo correzione di errore**.

    ![Risoluzione dei problemi di errore](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    La sessione di risoluzione dei problemi di errore inizierà a partire da un passaggio di preparazione dove i file di questo errore relativo ai vengono spostati in una posizione sicura Azure da scaricare.

    ![Preparazione di correzione di errori](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Una volta completata la preparazione, fare clic su **successivo: file di Download** per continuare con il download.

    ![Download dei file](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Per scaricare i file, specificare il **percorso di destinazione per il download**. Questo è il percorso in cui deve essere scaricato il file nel computer locale.  Il percorso predefinito, % USERPROFILE%\Downloads\errors, corrisponde alla cartella di download dell'utente connesso. può essere modificata in base alle esigenze.

    >[!NOTE]
    >È consigliabile utilizzare un percorso di file locale anziché un percorso di rete remota per ottenere prestazioni ottimali.

    > [!NOTE]
    > Se non ancora installato AzCopy, è possibile installare da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. Copiare il comando predefinito fare clic su **Copia negli Appunti**. Avviare un prompt dei comandi di windows, incollare il comando e quindi premere **INVIO**.  

    I file vengono scaricati.

    ![Preparazione di correzione di errori](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > Nel caso di problemi durante l'esecuzione di questo comando, vedere https://go.microsoft.com/fwlink/?linkid=2038117 per la risoluzione dei suggerimenti.

7. Dopo avere scaricato i file, è possibile correggere tali con uno strumento appropriato. Per i file protetti da password, sono disponibili numerosi strumenti che consentono di violazione delle password. Se si conoscono le password per i file, è possibile aprire e rimuovere la password di protezione.
    > [!NOTE]
    > IT è importante mantenere i nomi di file e struttura di directory dei file le quando viene spostato.  Tutte le convenzioni di denominazione utilizzate nei file scaricati e le cartelle consentono di associare i file remdiated originale.

8. A questo punto, tornare a eDiscovery avanzate (Preview) e fare clic su **successivo: caricare i file**.  Questo verrà spostato il passaggio successivo dove è ora possibile caricare i file.

    ![Caricamento dei file](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Specificare il percorso dei file le nella casella di testo **percorso dei file** , quindi fare clic su **Copia su clibpboard**.

10. Incollare il comando in un prompt dei comandi di Windows e premere **INVIO** per caricare i file.

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Infine, tornare a eDiscovery avanzate (Preview) e fare clic su **successivo: elaborazione dei file**.

12. Elaborazione quando è stata completata.  È possibile tornare a working set e visualizzare il file le.

## <a name="what-happens-when-files-are-remediated"></a>Cosa succede quando i file vengono applicati i rimedi

Quando le file vengono caricati, i metadati originali viene mantenuto fatta eccezione per i campi seguenti: 

- DocumentExtractedUrl
- ExtractedTextSize
- HasText
- IsErrorRemediate
- IsParentExtractedUrl
- ItemExtractedUrl
- LoadId
- ProcessingErrorMessage
- StatoElaborazione
- Testo
- WordCount
- WorkingsetId

Per una definizione di tutti i campi di metadati di documenti di eDiscovery avanzate (Preview), vedere [campi di metadati del documento](document-metadata-fields.md).