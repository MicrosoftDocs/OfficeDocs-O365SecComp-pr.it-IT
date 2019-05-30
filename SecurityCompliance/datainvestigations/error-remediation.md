---
title: Correzione degli errori durante l'elaborazione dei dati per un'indagine
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f8e253a3d38f0f4846485e3b88ea09914d9978ce
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547951"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a>Correzione degli errori durante l'elaborazione dei dati per un'indagine

La correzione degli errori consente ai ricercatori la possibilità di correggere i problemi relativi ai dati che impediscono l'elaborazione corretta del contenuto da parte dell'analisi dei dati (Preview). Ad esempio, i file protetti da password non possono essere elaborati dopo che i file sono stati bloccati o crittografati. Se si utilizza la correzione degli errori, gli investigatori possono scaricare i file con tale errore, rimuovere la protezione dalla password e caricare i file corretti.

Utilizzare il flusso di lavoro seguente per correggere i file con errori nei casi di analisi dei dati (Preview).

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Creazione di una sessione di correzione degli errori per la correzione dei file con errore di elaborazione

>[!NOTE]
>Se la procedura guidata per la correzione degli errori viene chiusa in qualsiasi momento durante la routine seguente, è possibile tornare alla sessione di correzione degli errori dalla scheda **elaborazione** selezionando **correzioni di errore** nel menu a discesa **Visualizza** .

1. Nella scheda **elaborazione** di un caso di analisi dei dati (anteprima) selezionare **errori** nel menu a discesa **Visualizza** .

2. Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o al tipo di file.  Nell'esempio seguente, viene rimediato un file protetto da password.

3. Fare clic su **+ nuova correzione degli errori**.

    ![Correzione degli errori](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    La sessione di correzione degli errori inizierà, iniziando con una fase di preparazione in cui i file con errore vengono copiati in una posizione sicura di Azure in modo che possano essere scaricati.

    ![Preparazione della correzione degli errori](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Dopo aver completato la preparazione, fare clic su **Avanti: scaricare i file** per continuare con il download.

    ![Scaricare file](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Per scaricare i file, specificare il **percorso di destinazione per il download**. si tratta di un percorso del computer locale in cui deve essere scaricato il file.  Il percorso predefinito,%USERPROFILE%\Downloads\errors, punta alla cartella Downloads dell'utente connesso. Questo può essere modificato in base alle esigenze.

    >[!NOTE]
    >È consigliabile utilizzare un percorso di file locale anziché un percorso di rete remoto per ottenere prestazioni ottimali.

    > [!NOTE]
    > Se non è stato installato AzCopy, è possibile installarlo da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. Copiare il comando predefinito facendo clic su **copia negli Appunti**. Avviare un prompt dei comandi di Windows, incollare il comando e quindi premere **invio**.  

    I file verranno scaricati.

    ![Preparazione della correzione degli errori](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > In caso di problemi con questo comando, vedere [Troubleshoot AzCopy in Advanced eDiscovery](../compliance20/troubleshooting-azcopy.md).

7. Dopo aver scaricato i file, è possibile risolverli con uno strumento appropriato. Per i file protetti da password, esistono diversi strumenti di cracking delle password che è possibile utilizzare. Se si conoscono le password per i file, è possibile aprirle e rimuovere la protezione tramite password.
    
   > [!NOTE]
    > È importante mantenere intatte la struttura di directory e i nomi di file dei file corretti.  Tutte le convenzioni di denominazione utilizzate nei file e nelle cartelle scaricati consentono di associare nuovamente i file di remdiated all'originale.

8. A questo punto, tornare a indagini sui dati (anteprima) e fare clic su **Avanti: carica file**.  In questo modo si passerà al passaggio successivo, in cui è ora possibile caricare i file.

    ![Caricare file](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Specificare il percorso dei file corretti nella casella di testo **percorso alla posizione dei file** e quindi fare clic su **copia negli Appunti**.

10. Incollare il comando in un prompt dei comandi di Windows e premere **invio** per caricare i file.

    ![ff2ff691-629F-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Infine, tornare a indagini sui dati (anteprima) e fare clic su **Avanti: elabora file**.

12. Quando l'elaborazione è completata.  È possibile tornare al working set e vedere il file correttivo.

## <a name="what-happens-when-files-are-remediated"></a>Cosa accade quando i file vengono corretti

Quando vengono caricati file corretti, i metadati originali vengono mantenuti con l'eccezione dei campi seguenti: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Testo
- WordCount
- WorkingsetId

Per una definizione di tutti i campi dei metadati del documento in indagini sui dati (Preview), vedere [Document Metadata Fields](document-metadata-fields.md).