---
title: Usare Analisi rapida in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Informazioni su come eseguire la modalità di analisi Express di Office 365 Advanced eDiscovery
ms.openlocfilehash: e306aa03962c646ce4083b7385e527b523e86fd6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217626"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="fa3a2-103">Usare Analisi rapida in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fa3a2-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="fa3a2-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="fa3a2-106">È possibile utilizzare l' **analisi Express** per analizzare rapidamente un caso ed esportare i risultati.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="fa3a2-p102">È possibile utilizzare l'analisi Express per calcolare quasi duplicati e thread di posta elettronica e calcolare i temi. È inoltre possibile impostare alcuni parametri per i temi, la somiglianza dei documenti e i file di esportazione nelle [Impostazioni avanzate per l'analisi espressa](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p102">You can use express analysis to calculate near-duplicates and email threads and calculate themes. You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="fa3a2-109">Eseguire l'analisi Express</span><span class="sxs-lookup"><span data-stu-id="fa3a2-109">Run Express analysis</span></span>

1. <span data-ttu-id="fa3a2-110">Nella scheda **Express Analysis** (1) selezionare un contenitore per abilitare i pulsanti \* \* Express Analysis \* \* (2) e **Advanced Settings** .</span><span class="sxs-lookup"><span data-stu-id="fa3a2-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span></span> 
    
    ![Schermata della pagina di analisi rapida](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="fa3a2-112">In **Analyze Parameters**:</span><span class="sxs-lookup"><span data-stu-id="fa3a2-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="fa3a2-p103">Selezionare **Calcola quasi duplicati e thread di posta elettronica** se si desidera eseguire l'analisi. È selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p103">Check **Calculate near-duplicates and email threads** if you want to run the analysis. It is selected by default.</span></span> 
    
  - <span data-ttu-id="fa3a2-p104">Controllare il **calcolo dei temi** per elaborare tutti i file e assegnargli i temi. È selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p104">Check **Calculate Themes** to process all files and assign themes to them. It is selected by default.</span></span> 
    
3. <span data-ttu-id="fa3a2-117">In **destinazione esportazione**:</span><span class="sxs-lookup"><span data-stu-id="fa3a2-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="fa3a2-118">Controllare il download del computer **locale** per il download nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="fa3a2-119">Se si seleziona **Esporta in Azure BLOB definito dall'utente** , è anche possibile specificare un URL del contenitore e un token SAS.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fa3a2-p105">Dopo l'archiviazione di un pacchetto di esportazione nell'oggetto BLOB di Azure definito dall'utente, i dati non vengono più gestiti da Advanced eDiscovery. viene gestito dal BLOB di Azure. Questo significa che, se si elimina il caso, i file esportati rimarranno sempre sul BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p105">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery. it is managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="fa3a2-123">**Save SAS token for future Export Session**: se selezionata, il token SAS verrà crittografato nel database interno di Advanced eDiscovery per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa3a2-p106">Attualmente il token SAS scade dopo un mese. Se si tenta di eseguire il download dopo più di un mese, è necessario annullare l'ultima sessione e quindi riesportarla.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p106">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="fa3a2-126">Per avviare l'analisi Express con le impostazioni predefinite, scegliere **analisi espressa**e la pagina **stato attività** verrà visualizzata</span><span class="sxs-lookup"><span data-stu-id="fa3a2-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="fa3a2-127">Nella pagina **stato attività** è possibile espandere le schede **Process**, **Analyze** and **Export** per visualizzare i dettagli relativi all'esecuzione espressa.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![Schermata della pagina di stato attività di analisi avanzata di eDiscovery Express](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="fa3a2-129">Scegliere la pagina **Riepilogo analisi Express** per elencare informazioni dettagliate sull'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="fa3a2-p107">Nella parte inferiore della pagina **Riepilogo analisi rapida** scegliere **Scarica ultima sessione** per scaricare i file di analisi TP del computer locale. Per prima cosa è necessario scaricare lo strumento di esportazione di eDiscovery e incollare la chiave Export per lo strumento di esportazione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p107">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer. You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="fa3a2-132">Impostazioni avanzate per l'analisi espressa</span><span class="sxs-lookup"><span data-stu-id="fa3a2-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="fa3a2-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="fa3a2-133"></span></span>

<span data-ttu-id="fa3a2-134">Facoltativamente, è possibile impostare **Impostazioni avanzate** per modificare i parametri di analisi Express predefiniti.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="fa3a2-135">Nella sezione **Analyze** :</span><span class="sxs-lookup"><span data-stu-id="fa3a2-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="fa3a2-136">Nelle **quasi duplicati e nei thread di posta elettronica**, immettere il valore di somigliaNza del **documento** oppure accettare l'impostazione predefinita 65%.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="fa3a2-p108">Nel **numero massimo di temi** immettere o selezionare un valore per il numero di temi da creare. Il valore predefinito è 200.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p108">In the **Max number of themes** enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fa3a2-p109">L'aumento del numero di temi influenza le prestazioni e la possibilità di generalizzare un tema. Maggiore è il numero di temi, maggiore è il livello di granularità. Ad esempio, se un insieme di temi 50 include un tema come "basket, Spurs, Clippers, Lakers"; 300 temi possono includere temi distinti: "Spurs", "Clippers", "Lakers". Se non si ha consapevolezza del tema "basket" e si utilizza questa funzionalità per ECA, è possibile utilizzare il tema "basket". Tuttavia, se l'elaborazione ha avuto troppi temi, potrebbe non essere possibile visualizzare la parola "basket" e potrebbe non essere in grado di riconoscere che gli Spurs e i Clippers sono buoni temi di basket da rivedere, anziché elementi che vengono utilizzati per i capelli.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p109">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="fa3a2-p110">Nei **temi suggeriti** scegliere **modifica** per suggerire le parole del tema per controllare l'elaborazione dei temi. Advanced eDiscovery si concentrerà su queste parole suggerite e cercherà di creare uno o più temi rilevanti, in base alle impostazioni "numero massimo di temi".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p110">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="fa3a2-p111">Ad esempio, se la parola suggerita è "computer" e si specifica "2" come "numero massimo di temi", Advanced eDiscovery proverà a generare due temi correlati alla parola "computer". I due temi potrebbero essere, ad esempio, "software per computer" e "hardware del computer".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p111">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![Aggiungi tema suggerito](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="fa3a2-149">**Modalità** Nell'elenco a discesa selezionare un'opzione **temi** :</span><span class="sxs-lookup"><span data-stu-id="fa3a2-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="fa3a2-150">**Create and Apply Model**: calcola i temi in base ai modelli da un segmento dei file e quindi distribuisce i file tra di essi.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="fa3a2-p112">**Create Model**: consente di calcolare un modello di temi da un segmento dei file. Il processo di applicazione della divisione dei file viene effettuato separatamente in un altro momento.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p112">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="fa3a2-p113">**Applicazione modello**: questa opzione viene visualizzata solo se un modello è stato creato in precedenza e non è stato ancora applicato. In questo modo i file verranno divisi in base ai temi.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p113">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="fa3a2-155">Nella sezione **Export** :</span><span class="sxs-lookup"><span data-stu-id="fa3a2-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="fa3a2-156">Nel **batch di esportazione selezionare**:</span><span class="sxs-lookup"><span data-stu-id="fa3a2-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="fa3a2-157">Nell'elenco **Esporta batch** selezionare il nome del batch o esportare i risultati in batch di esportazione 01 (il batch predefinito).</span><span class="sxs-lookup"><span data-stu-id="fa3a2-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="fa3a2-p114">Per esportare i risultati per i nuovi file aggiunti a un caso esistente, continuare con il batch corrente. Per creare una sessione nel batch, selezionare lo stesso numero di batch e fare clic su **Crea sessione di esportazione** è possibile utilizzare questa opzione per esportare gli stessi parametri del batch precedente, in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p114">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="fa3a2-p115">Per esportare in un nuovo batch, fare \*\*\*\*![clic su Aggiungi](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icona e immettere un nuovo nome in **batch Name** (o accettare il valore predefinito) e una descrizione in **batch Description**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p115">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="fa3a2-162">Per modificare un nome o una descrizione in batch, selezionare il nome in **batch di esportazione**, fare](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)clic su **modifica** ![icona modifica e quindi modificare i campi.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa3a2-p116">Dopo aver eseguito le sessioni per un batch di esportazione, non è possibile eliminarle. Inoltre, solo alcuni parametri possono essere modificati dopo l'esecuzione della prima sessione.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p116">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="fa3a2-165">Per creare un batch di esportazione duplicato, scegliere **Duplica esportazione batch**![creare un'icona](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) del batch di esportazione duplicata e immettere un nome e una descrizione per il batch duplicato nel pannello.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-165">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="fa3a2-166">Per eliminare un batch di esportazione, scegliere **Delete**![Delete an export batch](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)Icon.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-166">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="fa3a2-167">Per visualizzare la cronologia di un batch, fare clic su cronologia **batch**![Visualizza](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)cronologia.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-167">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="fa3a2-p117">In define p **opulation:** selezionare **Includi solo i file sopra il Punteggio** di rilevanza e/o il **batch di esportazione** se si desidera ottimizzare le impostazioni per il batch di esportazione. Se si seleziona **Includi solo i file sopra il Punteggio**di rilevanza, il **problema** è abilitato e se il Punteggio di pertinenza del file è superiore al Punteggio di taglio del problema selezionato, il file viene esportato. Il file verrà esportato a meno che non sia stato escluso dal filtro **per la revisione** . Se si seleziona **affina esportazione batch**, i pulsanti di \*\*\*\* opzione deduplica e **Filtra in base a' per la revisione '** sono abilitati. Se si sceglie \*\*\*\* deduplicazione, i file duplicati verranno filtrati in base al criterio definito: [livello case (impostazione predefinita): da ogni set di file duplicati nell'intero caso, tutti tranne un file verranno deselezionati. Livello di custode: da ogni serie di file duplicati dello stesso custode, tutti tranne un file verranno deduplicati. Un record di tutti i file duplicati è disponibile nell'output di esportazione. Se si sceglie **Filtra per campo ' per la revisione '** , selezionare **modifica in metadati** per immettere le impostazioni del campo **' per la revisione '**. Selezionare **Includi file di input**per includere i file di origine nel contenuto del pacchetto. È possibile cancellare questa opzione per velocizzare il processo di esportazione. Si noti che i file nativi verranno esportati in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p117">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch. If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported. The file will be exported unless it's excluded by the ' **For review** filter. If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled. If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped. A record of all duplicate files is available in export output. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files**to include source files in the package content. You can clear this option to speed up the export process. Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="fa3a2-179">In **Definisci metadati**selezionare una delle opzioni seguenti nell'elenco **modello di esportazione** (una volta per sessione).</span><span class="sxs-lookup"><span data-stu-id="fa3a2-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="fa3a2-p118">**Standard**: set di elementi di dati, metadati e proprietà di base. Utilizzare questa opzione quando i dati di importazione sono già stati elaborati in Advanced eDiscovery e i dati di esportazione vengono caricati in un sistema che già contiene i file. Per impostazione predefinita, le colonne dei modelli di esportazione vengono create e riempite.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p118">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="fa3a2-p119">**All**: set completo di metadati standard, inclusi tutti i dati di elaborazione, nonché analisi e punteggi di pertinenza. Questo modello è necessario quando Advanced eDiscovery esegue l'elaborazione e i dati dei file vengono caricati su un sistema esterno per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-p119">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="fa3a2-185">**Problemi**: selezionare **tutti i problemi** o selezionare un particolare problema creato.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="fa3a2-186">Scegliere **OK**per salvare le impostazioni avanzate, **ripristinare** i valori predefiniti per l'utilizzo del valore predefinito oppure **Annulla** per annullare l'impostazione delle impostazioni avanzate.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fa3a2-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa3a2-187">See also</span></span>
<span data-ttu-id="fa3a2-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="fa3a2-188"></span></span>

[<span data-ttu-id="fa3a2-189">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fa3a2-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

