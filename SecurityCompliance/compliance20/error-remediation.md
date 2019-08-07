---
title: Correzione degli errori durante l'elaborazione dei dati
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
ms.openlocfilehash: efcee812b6082a7f7ee36e6aea0ecb7ed0243077
ms.sourcegitcommit: 6122eb026c558a5126c40845e656fbb0c40cb32a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36168134"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="093fe-102">Correzione degli errori durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="093fe-102">Error remediation when processing data</span></span>

<span data-ttu-id="093fe-103">La correzione degli errori consente agli amministratori di eDiscovery di correggere i problemi relativi ai dati che impediscono al eDiscovery avanzato di elaborare correttamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="093fe-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="093fe-104">Ad esempio, i file protetti da password non possono essere elaborati dopo che i file sono stati bloccati o crittografati.</span><span class="sxs-lookup"><span data-stu-id="093fe-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="093fe-105">Se si utilizza la correzione degli errori, gli amministratori di eDiscovery possono scaricare i file con tale errore, rimuovere la protezione tramite password e quindi caricare i file corretti.</span><span class="sxs-lookup"><span data-stu-id="093fe-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="093fe-106">Utilizzare il flusso di lavoro seguente per correggere i file con errori nei casi avanzati di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="093fe-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="093fe-107">Creare una sessione di correzione degli errori per rimediare i file con errore di elaborazione</span><span class="sxs-lookup"><span data-stu-id="093fe-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="093fe-108">Se la procedura guidata per la correzione degli errori viene chiusa in qualsiasi momento durante la routine seguente, è possibile tornare alla sessione di correzione degli errori dalla scheda **elaborazione** selezionando **correzioni di errore** nel menu a discesa **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="093fe-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="093fe-109">Nella scheda **elaborazione** in un caso avanzato di eDiscovery, selezionare **errori** nel menu a discesa **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="093fe-109">On the **Processing** tab in an Advanced eDiscovery case, select **Errors** in the **View** drop-down menu.</span></span>

2. <span data-ttu-id="093fe-110">Selezionare gli errori che si desidera correggere facendo clic sul pulsante di opzione accanto al tipo di errore o al tipo di file.</span><span class="sxs-lookup"><span data-stu-id="093fe-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="093fe-111">Nell'esempio seguente, viene rimediato un file protetto da password.</span><span class="sxs-lookup"><span data-stu-id="093fe-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="093fe-112">Fare clic su **nuova correzione degli errori**.</span><span class="sxs-lookup"><span data-stu-id="093fe-112">Click **New error remediation**.</span></span>

    ![Correzione degli errori](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="093fe-114">La sessione di correzione dei problemi inizia con una fase di preparazione in cui i file con errori vengono copiati in una posizione di archiviazione di Azure fornita da Microsoft in modo da poterli scaricare nel computer locale per correggere il problema.</span><span class="sxs-lookup"><span data-stu-id="093fe-114">The error remediation session starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Preparazione della correzione degli errori](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="093fe-116">Al termine della preparazione, fare clic su **Avanti: scaricare i file** per continuare con il download.</span><span class="sxs-lookup"><span data-stu-id="093fe-116">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Scaricare file](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="093fe-118">Per scaricare i file, specificare il **percorso di destinazione per il download**.</span><span class="sxs-lookup"><span data-stu-id="093fe-118">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="093fe-119">Si tratta di un percorso del computer locale in cui viene scaricato il file.</span><span class="sxs-lookup"><span data-stu-id="093fe-119">This is a path on your local computer where the file is downloaded.</span></span>  <span data-ttu-id="093fe-120">Il percorso predefinito,%USERPROFILE%\Downloads\errors, punta alla cartella Downloads dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="093fe-120">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="093fe-121">Se necessario, è possibile modificare questo percorso.</span><span class="sxs-lookup"><span data-stu-id="093fe-121">You can change this path if necessary.</span></span> <span data-ttu-id="093fe-122">In caso contrario, si consiglia di utilizzare un percorso di file locale per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="093fe-122">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="093fe-123">Non utilizzare un percorso di rete remoto.</span><span class="sxs-lookup"><span data-stu-id="093fe-123">Don't use a remote network path.</span></span>

6. <span data-ttu-id="093fe-124">Copiare il comando predefinito facendo clic su **copia negli Appunti**.</span><span class="sxs-lookup"><span data-stu-id="093fe-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="093fe-125">Avviare un prompt dei comandi di Windows, incollare il comando e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="093fe-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="093fe-126">I file vengono scaricati.</span><span class="sxs-lookup"><span data-stu-id="093fe-126">The files are downloaded.</span></span>

    ![Preparare la correzione per gli errori](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="093fe-128">È necessario utilizzare AzCopy v 8.1 per utilizzare correttamente il comando disponibile nella pagina **Scarica file** .</span><span class="sxs-lookup"><span data-stu-id="093fe-128">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="093fe-129">È inoltre necessario utilizzare AzCopy v 8.1 per caricare i file nel passaggio 10 seguente.</span><span class="sxs-lookup"><span data-stu-id="093fe-129">You also must use AzCopy v8.1 to upload the files in step 10 below.</span></span> <span data-ttu-id="093fe-130">Per installare questa versione di AzCopy, vedere [Transfer Data with the AzCopy v 8.1 in Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="093fe-130">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="093fe-131">Se il comando AzCopy fornito ha esito negativo, vedere [risolvere i problemi relativi a AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="093fe-131">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="093fe-132">Dopo aver scaricato i file, è possibile risolverli con uno strumento appropriato.</span><span class="sxs-lookup"><span data-stu-id="093fe-132">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="093fe-133">Per i file protetti da password, esistono diversi strumenti di cracking delle password che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="093fe-133">For password-protected files, there several password cracking tools you can use.</span></span> <span data-ttu-id="093fe-134">Se si conoscono le password per i file, è possibile aprirle e rimuovere la protezione tramite password.</span><span class="sxs-lookup"><span data-stu-id="093fe-134">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="093fe-135">È importante mantenere intatte la struttura di directory e i nomi di file dei file corretti.</span><span class="sxs-lookup"><span data-stu-id="093fe-135">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="093fe-136">Tutte le convenzioni di denominazione utilizzate nei file e nelle cartelle scaricati consentono di associare nuovamente i file di remdiated all'originale.</span><span class="sxs-lookup"><span data-stu-id="093fe-136">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="093fe-137">A questo punto, tornare a Advanced eDiscovery e fare clic su **Next: upload files**.</span><span class="sxs-lookup"><span data-stu-id="093fe-137">Now, return to Advanced eDiscovery and click **Next: Upload files**.</span></span>  <span data-ttu-id="093fe-138">In questo modo si passerà al passaggio successivo, in cui è ora possibile caricare i file.</span><span class="sxs-lookup"><span data-stu-id="093fe-138">This will move to the next step where you can now upload the files.</span></span>

    ![Caricare file](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="093fe-140">Specificare il percorso dei file corretti nella casella di testo **percorso alla posizione dei file** e quindi fare clic su **copia negli Appunti**.</span><span class="sxs-lookup"><span data-stu-id="093fe-140">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="093fe-141">Incollare il comando in un prompt dei comandi di Windows e premere **invio** per caricare i file.</span><span class="sxs-lookup"><span data-stu-id="093fe-141">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629F-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="093fe-143">Tornare a Advanced eDiscovery e fare clic su **Next: Process files**.</span><span class="sxs-lookup"><span data-stu-id="093fe-143">Return to Advanced eDiscovery and click **Next: Process files**.</span></span>

12. <span data-ttu-id="093fe-144">Quando l'elaborazione è completata.</span><span class="sxs-lookup"><span data-stu-id="093fe-144">When processing is complete.</span></span> <span data-ttu-id="093fe-145">È possibile tornare al set di revisione e vedere il file di correzione.</span><span class="sxs-lookup"><span data-stu-id="093fe-145">You can return to the review set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="093fe-146">Cosa accade quando i file vengono corretti</span><span class="sxs-lookup"><span data-stu-id="093fe-146">What happens when files are remediated</span></span>

<span data-ttu-id="093fe-147">Quando i file corretti vengono caricati, vengono conservati i metadati originali, ad eccezione dei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="093fe-147">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="093fe-148">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="093fe-148">ExtractedTextSize</span></span>
- <span data-ttu-id="093fe-149">HasText</span><span class="sxs-lookup"><span data-stu-id="093fe-149">HasText</span></span>
- <span data-ttu-id="093fe-150">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="093fe-150">IsErrorRemediate</span></span>
- <span data-ttu-id="093fe-151">LoadId</span><span class="sxs-lookup"><span data-stu-id="093fe-151">LoadId</span></span>
- <span data-ttu-id="093fe-152">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="093fe-152">ProcessingErrorMessage</span></span>
- <span data-ttu-id="093fe-153">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="093fe-153">ProcessingStatus</span></span>
- <span data-ttu-id="093fe-154">Testo</span><span class="sxs-lookup"><span data-stu-id="093fe-154">Text</span></span>
- <span data-ttu-id="093fe-155">WordCount</span><span class="sxs-lookup"><span data-stu-id="093fe-155">WordCount</span></span>
- <span data-ttu-id="093fe-156">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="093fe-156">WorkingsetId</span></span>

<span data-ttu-id="093fe-157">Per una definizione di tutti i campi dei metadati in Advanced eDiscovery, vedere [Document Metadata Fields](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="093fe-157">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
