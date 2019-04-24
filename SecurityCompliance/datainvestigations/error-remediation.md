---
title: Correzione degli errori durante l'elaborazione dei dati per un'indagine
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: b78a8e45ffb0833dec5116ff637cd0930387ebfe
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258864"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="56acd-102">Correzione degli errori durante l'elaborazione dei dati per un'indagine</span><span class="sxs-lookup"><span data-stu-id="56acd-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="56acd-103">La correzione degli errori consente ai ricercatori la possibilità di correggere i problemi relativi ai dati che impediscono l'elaborazione corretta del contenuto da parte dell'analisi dei dati (Preview).</span><span class="sxs-lookup"><span data-stu-id="56acd-103">Error remediation allows investigators the ability to rectify data issues which prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="56acd-104">Ad esempio, i file protetti da password non possono essere elaborati dopo che i file sono stati bloccati o crittografati.</span><span class="sxs-lookup"><span data-stu-id="56acd-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="56acd-105">Se si utilizza la correzione degli errori, gli investigatori possono scaricare i file con tale errore, rimuovere la protezione dalla password e caricare i file corretti.</span><span class="sxs-lookup"><span data-stu-id="56acd-105">Using error remediation, investigators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="56acd-106">Utilizzare il flusso di lavoro seguente per correggere i file con errori nei casi di analisi dei dati (Preview).</span><span class="sxs-lookup"><span data-stu-id="56acd-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="56acd-107">Creazione di una sessione di correzione degli errori per la correzione dei file con errore di elaborazione</span><span class="sxs-lookup"><span data-stu-id="56acd-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="56acd-108">Se la procedura guidata per la correzione degli errori viene chiusa in qualsiasi momento durante la routine seguente, è possibile tornare alla sessione di correzione degli errori dalla scheda **elaborazione** selezionando **correzioni di errore** nel menu a discesa **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="56acd-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="56acd-109">Nella scheda **elaborazione** di un caso di analisi dei dati (anteprima) selezionare **errori** nel menu a discesa **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="56acd-109">On the **Processing** tab in an Data Investigations (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="56acd-110">Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o al tipo di file.</span><span class="sxs-lookup"><span data-stu-id="56acd-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="56acd-111">Nell'esempio seguente, viene rimediato un file protetto da password.</span><span class="sxs-lookup"><span data-stu-id="56acd-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="56acd-112">Fare clic su **+ nuova correzione degli errori**.</span><span class="sxs-lookup"><span data-stu-id="56acd-112">Click **+ New error remediation**.</span></span>

    ![Correzione degli errori](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="56acd-114">La sessione di correzione degli errori inizierà iniziando con una fase di preparazione in cui i file che hanno subito errori vengono spostati in una posizione di Azure sicura da scaricare.</span><span class="sxs-lookup"><span data-stu-id="56acd-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![Preparazione della correzione degli errori](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="56acd-116">Dopo aver completato la preparazione, fare clic su **Avanti: scaricare i file** per continuare con il download.</span><span class="sxs-lookup"><span data-stu-id="56acd-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Scaricare file](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="56acd-118">Per scaricare i file, specificare il **percorso di destinazione per il download**. si tratta di un percorso del computer locale in cui deve essere scaricato il file.</span><span class="sxs-lookup"><span data-stu-id="56acd-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="56acd-119">Il percorso predefinito,%USERPROFILE%\Downloads\errors, punta alla cartella Downloads dell'utente connesso. Questo può essere modificato in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="56acd-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="56acd-120">È consigliabile utilizzare un percorso di file locale anziché un percorso di rete remoto per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="56acd-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56acd-121">Se non è stato installato AzCopy, è possibile installarlo da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="56acd-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="56acd-122">Copiare il comando predefinito facendo clic su **copia negli Appunti**.</span><span class="sxs-lookup"><span data-stu-id="56acd-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="56acd-123">Avviare un prompt dei comandi di Windows, incollare il comando e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="56acd-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="56acd-124">I file verranno scaricati.</span><span class="sxs-lookup"><span data-stu-id="56acd-124">The files will be downloaded.</span></span>

    ![Preparazione della correzione degli errori](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="56acd-126">In caso di problemi con questo comando, vedere https://go.microsoft.com/fwlink/?linkid=2038117 per suggerimenti per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="56acd-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="56acd-127">Dopo aver scaricato i file, è possibile risolverli con uno strumento appropriato.</span><span class="sxs-lookup"><span data-stu-id="56acd-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="56acd-128">Per i file protetti da password, esistono diversi strumenti di cracking delle password che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="56acd-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="56acd-129">Se si conoscono le password per i file, è possibile aprirle e rimuovere la protezione tramite password.</span><span class="sxs-lookup"><span data-stu-id="56acd-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="56acd-130">È importante mantenere intatte la struttura di directory e i nomi di file dei file corretti.</span><span class="sxs-lookup"><span data-stu-id="56acd-130">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="56acd-131">Tutte le convenzioni di denominazione utilizzate nei file e nelle cartelle scaricati consentono di associare nuovamente i file di remdiated all'originale.</span><span class="sxs-lookup"><span data-stu-id="56acd-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="56acd-132">A questo punto, tornare a indagini sui dati (anteprima) e fare clic su **Avanti: carica file**.</span><span class="sxs-lookup"><span data-stu-id="56acd-132">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="56acd-133">In questo modo si passerà al passaggio successivo, in cui è ora possibile caricare i file.</span><span class="sxs-lookup"><span data-stu-id="56acd-133">This will move to the next step where you can now upload the files.</span></span>

    ![Caricare file](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="56acd-135">Specificare il percorso dei file corretti nella casella di testo **percorso alla posizione dei file** , quindi fare clic su **copia in clibpboard**.</span><span class="sxs-lookup"><span data-stu-id="56acd-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="56acd-136">Incollare il comando in un prompt dei comandi di Windows e premere **invio** per caricare i file.</span><span class="sxs-lookup"><span data-stu-id="56acd-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629F-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="56acd-138">Infine, tornare a indagini sui dati (anteprima) e fare clic su **Avanti: elabora file**.</span><span class="sxs-lookup"><span data-stu-id="56acd-138">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="56acd-139">Quando l'elaborazione è completata.</span><span class="sxs-lookup"><span data-stu-id="56acd-139">When processing is complete.</span></span>  <span data-ttu-id="56acd-140">È possibile tornare al working set e vedere il file correttivo.</span><span class="sxs-lookup"><span data-stu-id="56acd-140">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="56acd-141">Cosa accade quando i file vengono corretti</span><span class="sxs-lookup"><span data-stu-id="56acd-141">What happens when files are remediated</span></span>

<span data-ttu-id="56acd-142">Quando vengono caricati file corretti, i metadati originali vengono mantenuti con l'eccezione dei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="56acd-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="56acd-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="56acd-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="56acd-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="56acd-144">ExtractedTextSize</span></span>
- <span data-ttu-id="56acd-145">HasText</span><span class="sxs-lookup"><span data-stu-id="56acd-145">HasText</span></span>
- <span data-ttu-id="56acd-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="56acd-146">IsErrorRemediate</span></span>
- <span data-ttu-id="56acd-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="56acd-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="56acd-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="56acd-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="56acd-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="56acd-149">LoadId</span></span>
- <span data-ttu-id="56acd-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="56acd-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="56acd-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="56acd-151">ProcessingStatus</span></span>
- <span data-ttu-id="56acd-152">Testo</span><span class="sxs-lookup"><span data-stu-id="56acd-152">Text</span></span>
- <span data-ttu-id="56acd-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="56acd-153">WordCount</span></span>
- <span data-ttu-id="56acd-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="56acd-154">WorkingsetId</span></span>

<span data-ttu-id="56acd-155">Per una definizione di tutti i campi dei metadati del documento in indagini sui dati (Preview), vedere [Document Metadata Fields](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="56acd-155">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>