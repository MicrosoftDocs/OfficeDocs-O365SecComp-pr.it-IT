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
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="fdddd-103">Visualizzare i risultati del modulo di processo in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fdddd-103">View Process module results in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="fdddd-104">Dopo aver **Prepare** \> **processo** viene avviato, è possibile visualizzare stato e i risultati.</span><span class="sxs-lookup"><span data-stu-id="fdddd-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fdddd-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="fdddd-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="fdddd-107">Stato processo attività</span><span class="sxs-lookup"><span data-stu-id="fdddd-107">Process task status</span></span>

<span data-ttu-id="fdddd-108">In **Prepara** \> **processo** \> **risultati**, nella pagina viene visualizzato lo stato corrente (se processo è in esecuzione) o lo stato dell'ultimo processo stato attività come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fdddd-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![Stato delle attività del modulo processo](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="fdddd-110">Attività visualizzate possono variare in base alle opzioni di processo selezionate.</span><span class="sxs-lookup"><span data-stu-id="fdddd-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="fdddd-111">**Inventario**: eDiscovery avanzate consente di scorrere tutti i file selezionati per processo ed esegue la raccolta dei dati di base.</span><span class="sxs-lookup"><span data-stu-id="fdddd-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="fdddd-112">**Calcola firme**: consente di calcolare le firme digitali MD5.</span><span class="sxs-lookup"><span data-stu-id="fdddd-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="fdddd-p102">**Estrazione composti**: estratti interni o contenuti file ricorsivo dai file composti (ad esempio file PST, ZIP, MSG). Vengono archiviati i file estratti nella cartella maiuscole del case.</span><span class="sxs-lookup"><span data-stu-id="fdddd-p102">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG). Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="fdddd-115">**Database di sincronizzazione**: processo di database interno.</span><span class="sxs-lookup"><span data-stu-id="fdddd-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="fdddd-p103">**Copia del file**: file di processo copie. Questa operazione viene sempre visualizzata, anche quando è selezionata l'opzione file copia avanzata.</span><span class="sxs-lookup"><span data-stu-id="fdddd-p103">**File copy**: Copies Process files. This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="fdddd-p104">**Estrazione di testo**: quando sono presenti file nativi, eDiscovery avanzate estrae il testo da tali file utilizzando DTSearch. Il testo di questi file estratto viene archiviato come file di testo nella cartella maiuscole.</span><span class="sxs-lookup"><span data-stu-id="fdddd-p104">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch. The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="fdddd-120">**Aggiornamento dei metadati**: elabora i metadati caricato.</span><span class="sxs-lookup"><span data-stu-id="fdddd-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="fdddd-121">**Finalizing**: elaborazione interna che consente di finalizzare dati di caricamento file casi (ad esempio, identificare i file di errore e l'esito positivo).</span><span class="sxs-lookup"><span data-stu-id="fdddd-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="fdddd-p105">Stato delle attività: visualizzato dopo il completamento dell'attività. Durante l'esecuzione di attività, viene visualizzata la durata di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fdddd-p105">Task status: Displayed after task completion. While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fdddd-124">Le attività completate possono anche includere totali per l'elaborazione è stata completata o file con errori.</span><span class="sxs-lookup"><span data-stu-id="fdddd-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="fdddd-p106">"Annulla" è disponibile l'opzione di rollback per arrestare l'esecuzione del processo e quindi eseguire il rollback al popolamento dati precedente o i dati trasformati salvati. Rollback Cancella i dati trasformati tutti. Se non si desidera i dati trasformati persi (ad esempio, si prevede di ricaricare questi file), opzione selezionare "Annulla" in questa finestra per non si desidera eseguire il rollback.</span><span class="sxs-lookup"><span data-stu-id="fdddd-p106">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data. Rollback clears all processed data. If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="fdddd-128">Riepilogo processo</span><span class="sxs-lookup"><span data-stu-id="fdddd-128">Process summary</span></span>

<span data-ttu-id="fdddd-129">In Prepara \> processo \> risultati \> Process riepilogo, una suddivisione dei risultati di file caricato viene visualizzata in base ai risultati elabora e il file ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fdddd-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="fdddd-130">Riquadri di presentano una visualizzazione grafica delle statistiche di file importato, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fdddd-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="fdddd-131">**Processo di riepilogo vengono accumulati**: d: tutti i file nel caso.</span><span class="sxs-lookup"><span data-stu-id="fdddd-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="fdddd-132">**Riepilogo del processo ultima**: i file caricati dall'ultima sessione o azione.</span><span class="sxs-lookup"><span data-stu-id="fdddd-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="fdddd-133">**Ultima famiglie**: informazioni famiglia nel caso (se esistenti).</span><span class="sxs-lookup"><span data-stu-id="fdddd-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="fdddd-134">Se sono stati aggiunti i file di **seeding** , il numero di file di seeding viene elencato per un problema che è stato definito per i file.</span><span class="sxs-lookup"><span data-stu-id="fdddd-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="fdddd-135">Se il contrassegno di **seeding** file non è riuscita, che viene inoltre specificato.</span><span class="sxs-lookup"><span data-stu-id="fdddd-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="fdddd-136">Se sono stati aggiunti file **pre-contrassegnati** , è riportato il numero di file pre-contrassegnati per un problema che è stato definito per i file.</span><span class="sxs-lookup"><span data-stu-id="fdddd-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="fdddd-137">Se il contrassegno di **pre-contrassegnato come** file non è riuscita, che viene inoltre specificato.</span><span class="sxs-lookup"><span data-stu-id="fdddd-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![Riepilogo modulo processo](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="fdddd-139">Riepilogo processo accumulati e l'ultima grafici</span><span class="sxs-lookup"><span data-stu-id="fdddd-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="fdddd-140">La barra sinistra include i file estratti + origine: ovvero tutti i file disponibili.</span><span class="sxs-lookup"><span data-stu-id="fdddd-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="fdddd-141">Destra della barra, elaborate, include:</span><span class="sxs-lookup"><span data-stu-id="fdddd-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="fdddd-142">File con errori di carico</span><span class="sxs-lookup"><span data-stu-id="fdddd-142">Files with load errors</span></span>
    
- <span data-ttu-id="fdddd-143">File caricati correttamente, che possono includere:</span><span class="sxs-lookup"><span data-stu-id="fdddd-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="fdddd-144">**Esistente**: i file che sono stati caricati prima e ora caricati nuovamente (compresi i duplicati).</span><span class="sxs-lookup"><span data-stu-id="fdddd-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="fdddd-145">**Testo**: file univoci con testo.</span><span class="sxs-lookup"><span data-stu-id="fdddd-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="fdddd-146">**Il testo non**: svuotare i file di testo, i file di testo nativa vuoto, file non testuali nativi.</span><span class="sxs-lookup"><span data-stu-id="fdddd-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="fdddd-147">**Duplicare**s: Duplicate file di testo.</span><span class="sxs-lookup"><span data-stu-id="fdddd-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="fdddd-148">Ultimi errori dei processi</span><span class="sxs-lookup"><span data-stu-id="fdddd-148">Last process errors</span></span>

<span data-ttu-id="fdddd-149">In Prepara \> processo \> risultati \> ultimi errori dei processi, i dettagli degli errori nell'ultima azione eseguita o sessione vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="fdddd-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![Errori modulo processo](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="fdddd-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdddd-151">See also</span></span>

[<span data-ttu-id="fdddd-152">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fdddd-152">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="fdddd-153">In esecuzione il modulo di processo e il caricamento dei dati</span><span class="sxs-lookup"><span data-stu-id="fdddd-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

