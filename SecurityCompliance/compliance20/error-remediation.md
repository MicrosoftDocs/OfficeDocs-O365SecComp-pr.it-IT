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
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="4b7b2-102">Risoluzione dei problemi di errore durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="4b7b2-102">Error remediation when processing data</span></span>

<span data-ttu-id="4b7b2-p101">Risoluzione dei problemi errore consente agli amministratori di eDiscovery la possibilità di risolvere i problemi di dati che impediscono l'elaborazione correttamente il contenuto eDiscovery avanzate (Preview). Ad esempio, i file protetti da password non possono essere elaborati poiché i file sono bloccati o crittografati. Utilizzo di correzione di errori, gli amministratori di eDiscovery possono scaricare i file con tali errori, rimuovere la password di protezione e caricare i file le.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-p101">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery (Preview) from properly processing the content. For example, files that are password protected cannot be processed since the files are locked or encrypted. Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="4b7b2-106">Utilizzare il flusso di lavoro seguente per correggere i file con errori in casi di eDiscovery avanzate (Preview).</span><span class="sxs-lookup"><span data-stu-id="4b7b2-106">Use the following workflow to remediate files with errors in Advanced eDiscovery (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="4b7b2-107">Creazione di una sessione di risoluzione dei problemi di errore per correggere i file con errori di elaborazione</span><span class="sxs-lookup"><span data-stu-id="4b7b2-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="4b7b2-108">Se l'in qualsiasi momento durante la procedura seguente viene chiusa la procedura guidata correzione dei problemi di errore, è possibile restituire alla sessione di risoluzione dei problemi di errore nella scheda **elaborazione** selezionando **rimedi errore** nel menu a discesa **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="4b7b2-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="4b7b2-109">Selezionare **gli errori** nel menu a discesa **Visualizza** scheda **elaborazione** in un caso eDiscovery avanzate (Preview).</span><span class="sxs-lookup"><span data-stu-id="4b7b2-109">On the **Processing** tab in an Advanced eDiscovery (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="4b7b2-p102">Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o tipo di file.  Nell'esempio seguente viene stiamo monitorare e aggiornare un file protetto da password.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-p102">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.  In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="4b7b2-112">Fare clic su **+ Nuovo correzione di errore**.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-112">Click **+ New error remediation**.</span></span>

    ![Risoluzione dei problemi di errore](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="4b7b2-114">La sessione di risoluzione dei problemi di errore inizierà a partire da un passaggio di preparazione dove i file di questo errore relativo ai vengono spostati in una posizione sicura Azure da scaricare.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![Preparazione di correzione di errori](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="4b7b2-116">Una volta completata la preparazione, fare clic su **successivo: file di Download** per continuare con il download.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Download dei file](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="4b7b2-p103">Per scaricare i file, specificare il **percorso di destinazione per il download**. Questo è il percorso in cui deve essere scaricato il file nel computer locale.  Il percorso predefinito, % USERPROFILE%\Downloads\errors, corrisponde alla cartella di download dell'utente connesso. può essere modificata in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-p103">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.  The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="4b7b2-120">È consigliabile utilizzare un percorso di file locale anziché un percorso di rete remota per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b7b2-121">Se non ancora installato AzCopy, è possibile installare da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="4b7b2-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="4b7b2-p104">Copiare il comando predefinito fare clic su **Copia negli Appunti**. Avviare un prompt dei comandi di windows, incollare il comando e quindi premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-p104">Copy the predefined command by clicking **Copy to clipboard**. Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="4b7b2-124">I file vengono scaricati.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-124">The files will be downloaded.</span></span>

    ![Preparazione di correzione di errori](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="4b7b2-126">Nel caso di problemi durante l'esecuzione di questo comando, vedere https://go.microsoft.com/fwlink/?linkid=2038117 per la risoluzione dei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="4b7b2-p105">Dopo avere scaricato i file, è possibile correggere tali con uno strumento appropriato. Per i file protetti da password, sono disponibili numerosi strumenti che consentono di violazione delle password. Se si conoscono le password per i file, è possibile aprire e rimuovere la password di protezione.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-p105">After downloading the files, you can remediate them with an appropriate tool. For password protected files, there are a number of password cracking tools you can use. If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4b7b2-p106">IT è importante mantenere i nomi di file e struttura di directory dei file le quando viene spostato.  Tutte le convenzioni di denominazione utilizzate nei file scaricati e le cartelle consentono di associare i file remdiated originale.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-p106">IT is important that you retain the directory structure and file names of the remediated files in tact.  All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="4b7b2-p107">A questo punto, tornare a eDiscovery avanzate (Preview) e fare clic su **successivo: caricare i file**.  Questo verrà spostato il passaggio successivo dove è ora possibile caricare i file.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-p107">Now, return to Advanced eDiscovery (Preview) and click **Next: Upload files**.  This will move to the next step where you can now upload the files.</span></span>

    ![Caricamento dei file](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="4b7b2-135">Specificare il percorso dei file le nella casella di testo **percorso dei file** , quindi fare clic su **Copia su clibpboard**.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="4b7b2-136">Incollare il comando in un prompt dei comandi di Windows e premere **INVIO** per caricare i file.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="4b7b2-138">Infine, tornare a eDiscovery avanzate (Preview) e fare clic su **successivo: elaborazione dei file**.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-138">Finally, return to Advanced eDiscovery (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="4b7b2-p108">Elaborazione quando è stata completata.  È possibile tornare a working set e visualizzare il file le.</span><span class="sxs-lookup"><span data-stu-id="4b7b2-p108">When processing is complete.  You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="4b7b2-141">Cosa succede quando i file vengono applicati i rimedi</span><span class="sxs-lookup"><span data-stu-id="4b7b2-141">What happens when files are remediated</span></span>

<span data-ttu-id="4b7b2-142">Quando le file vengono caricati, i metadati originali viene mantenuto fatta eccezione per i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b7b2-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="4b7b2-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="4b7b2-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="4b7b2-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="4b7b2-144">ExtractedTextSize</span></span>
- <span data-ttu-id="4b7b2-145">HasText</span><span class="sxs-lookup"><span data-stu-id="4b7b2-145">HasText</span></span>
- <span data-ttu-id="4b7b2-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="4b7b2-146">IsErrorRemediate</span></span>
- <span data-ttu-id="4b7b2-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="4b7b2-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="4b7b2-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="4b7b2-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="4b7b2-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="4b7b2-149">LoadId</span></span>
- <span data-ttu-id="4b7b2-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="4b7b2-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="4b7b2-151">StatoElaborazione</span><span class="sxs-lookup"><span data-stu-id="4b7b2-151">ProcessingStatus</span></span>
- <span data-ttu-id="4b7b2-152">Testo</span><span class="sxs-lookup"><span data-stu-id="4b7b2-152">Text</span></span>
- <span data-ttu-id="4b7b2-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="4b7b2-153">WordCount</span></span>
- <span data-ttu-id="4b7b2-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="4b7b2-154">WorkingsetId</span></span>

<span data-ttu-id="4b7b2-155">Per una definizione di tutti i campi di metadati di documenti di eDiscovery avanzate (Preview), vedere [campi di metadati del documento](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="4b7b2-155">For a definition of all document metadata fields in Advanced eDiscovery (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>