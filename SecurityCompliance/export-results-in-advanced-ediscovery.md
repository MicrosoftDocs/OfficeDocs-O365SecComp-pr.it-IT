---
title: Esportare i risultati in Office 365 Advanced eDiscovery
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
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: "Informazioni su come definire le opzioni per l'esportazione dei risultati da Office 365 avanzate eDiscovery, compresa la procedura per specificare i parametri per un batch di esportazione. "
ms.openlocfilehash: 92ee107ad096393fbccbc9a3dbe81d8e7dd28da9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531392"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ebdf7-103">Esportare i risultati in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ebdf7-103">Export results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="ebdf7-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ebdf7-106">In questo argomento vengono descritte le opzioni di installazione esportazione eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="ebdf7-107">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="ebdf7-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="ebdf7-108">Definizione dei batch di esportazione e sessioni</span><span class="sxs-lookup"><span data-stu-id="ebdf7-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="ebdf7-109">Esporta incrementali e aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ebdf7-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="ebdf7-110">Impostare i parametri di esportazione batch</span><span class="sxs-lookup"><span data-stu-id="ebdf7-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="ebdf7-111">Esportare i file di output di report</span><span class="sxs-lookup"><span data-stu-id="ebdf7-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="ebdf7-112">Definizione dei batch di esportazione e sessioni</span><span class="sxs-lookup"><span data-stu-id="ebdf7-112">Defining export batches and sessions</span></span>
<span data-ttu-id="ebdf7-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="ebdf7-113"></span></span>

<span data-ttu-id="ebdf7-p102">Un batch di esportazione consente l'elaborazione di esportazione utilizzando un set di parametri definiti. EDiscovery avanzate consente di definire batch per personalizzare ogni esportazione.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p102">An export batch allows export processing using a set of defined parameters. Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="ebdf7-p103">I parametri sono definiti per il batch di esportazione. Per impostazione predefinita per il primo batch di un caso, viene creato un batch denominato "Export batch 01". È inoltre possibile modificare il nome del batch e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p103">Parameters are defined per export batch. A batch named "Export batch 01" is created by default for the first batch of a case. You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="ebdf7-119">Una sessione di esportazione è un'esecuzione dell'esportazione di eDiscovery avanzate all'interno di un batch di esportazione.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="ebdf7-120">Esporta incrementali e aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ebdf7-120">Incremental and additional exports</span></span>
<span data-ttu-id="ebdf7-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="ebdf7-121"></span></span>

<span data-ttu-id="ebdf7-p104">È possibile eseguire più sessioni di esportazione all'interno di un batch di esportazione, per assicurare risultati coerenti basati sul modello di esportazione stesso e parametri. Per ogni sessione all'interno di un batch, è possibile esportare analitica per elaborare dati maiuscole appena ed elaborare ogni "in modo incrementale."</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p104">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters. For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="ebdf7-p105">Per esportare utilizzando un diverso set di parametri, è necessario innanzitutto creare un nuovo batch. La prima sessione il nuovo batch produrrà risultati per file elaborati nel caso finora, indipendentemente dal fatto questi file sono stati importati ed elaborati su una o più importazioni. Ogni blocco Ricalcola pivot, similarità, inclusives e così via. Sessioni di utilizzano i parametri definiti per il batch di e non vengono ricalcolate pivot, similarità, inclusives e così via per ogni esecuzione di sessione.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p105">In order to export using a different set of parameters, you first need to create a new batch. The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports. Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="ebdf7-p106">Si supponga ad esempio un caso è stato importato e analizzare i relativi dati. Per poter recuperare quasi duplicati e i risultati Threading posta elettronica per i dati incrementali, fare clic su **Crea esportare sessione** nello stesso batch che è stato utilizzato per esportare i dati.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p106">For example, assume a case was imported and its data analyzed. In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="ebdf7-129">Impostare i parametri di esportazione batch</span><span class="sxs-lookup"><span data-stu-id="ebdf7-129">Set up batch export parameters</span></span>
<span data-ttu-id="ebdf7-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="ebdf7-130"></span></span>

<span data-ttu-id="ebdf7-p107">EDiscovery esportare strumento viene utilizzato per esportare i risultati della ricerca di eDiscovery avanzata del computer locale. Per aumentare la velocità effettiva di trasferimento dati e velocizzare il processo di esportazione, è possibile configurare un'impostazione del Registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Se si desidera aumentare la velocità di download, configurare l'impostazione del Registro di sistema prima di impostare i parametri di esportazione. Per ulteriori informazioni, vedere [aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p107">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer. To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results. If you'd like to increase the download speed, configure the registry setting before you set up the export parameters. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="ebdf7-135">In eDiscovery avanzate, selezionare un caso e fare clic su **Esporta** \> **il programma di installazione**.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
  - <span data-ttu-id="ebdf7-136">Nell'elenco **Esporta batch** , selezionare il nome del batch o esportare i risultati in batch esportazione 01 (batch predefinito).</span><span class="sxs-lookup"><span data-stu-id="ebdf7-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="ebdf7-p108">Per esportare i risultati per i nuovi file aggiunti a un caso esistente, continuare con il batch corrente. Per creare una sessione nel batch, selezionare lo stesso numero di batch e fare clic su **Crea esportare sessione** è possibile utilizzare questa opzione per esportare gli stessi parametri come processo batch precedente, in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p108">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="ebdf7-p109">Per esportare in un nuovo batch, fare clic su **Aggiungi**![aggiungere icona](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)e immettere un nuovo nome nella **casella Nome Batch** (o accettare il valore predefinito) e una descrizione nella **casella Descrizione Batch**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p109">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="ebdf7-141">Per modificare un nome di batch o la descrizione, selezionare il nome di **esportazione batch**, fare clic su **Modifica** ![sull'icona Modifica](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)e quindi modificare i campi.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebdf7-p110">Dopo aver eseguito le sessioni per un batch di esportazione, non possono essere eliminate. Inoltre, solo alcuni parametri possono essere modificati dopo la prima sessione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p110">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="ebdf7-144">Per creare un batch di esportazione duplicati, scegliere **Copia esportazione batch**![creare un'icona di batch esportazione duplicati](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) e immettere un nome e una descrizione per il batch duplicato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-144">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="ebdf7-145">Per eliminare un batch di esportazione, scegliere **Elimina**![Elimina un'icona di batch esportazione](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span><span class="sxs-lookup"><span data-stu-id="ebdf7-145">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="ebdf7-146">Per visualizzare la cronologia di un batch, scegliere **cronologia Batch**![sull'icona di visualizzazione cronologia](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span><span class="sxs-lookup"><span data-stu-id="ebdf7-146">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="ebdf7-147">In **popolazione**, selezionare **includere solo i file sopra punteggio di pertinenza demarcazione** e/o **batch esportazione Affina ricerca** se si desidera ottimizzare le impostazioni per il batch di esportazione.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-147">Under **Population**,Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="ebdf7-p111">Se si seleziona **includere solo i file sopra punteggio di pertinenza interruzione**, il **problema** è abilitata. Se punteggio di pertinenza del file è superiore al punteggio di interruzione per il rilascio selezionato, a meno che non viene escluso dal filtro 'per la revisione' verrà esportato il file.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p111">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled. If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
<span data-ttu-id="ebdf7-p112">Se si seleziona **Affina ricerca esportazione batch**, il **deprovisioning dupe** e filtrare per 'Per revisione' sono abilitati i pulsanti di campo. Se si sceglie **deprovisioning dupe**, quindi i file duplicati verranno filtrati in base ai criteri definiti [caso livello (impostazione predefinita): da ogni insieme di file duplicati nell'intero caso, sarà deprovisioning duped file tutti tranne uno. Livello depositaria: da ogni insieme di file duplicati della stessa depositaria, file tutti tranne uno sarà deprovisioning duped.] L'output export contiene un record di tutti i file duplicati. Se si sceglie campo **filtro in base a 'per la revisione'** , selezionare **Modifica in metadati** immettere le impostazioni di campo **'per la revisione'** . Selezionare **Includi file di input** per includere i file di origine di contenuto del pacchetto. È possibile deselezionare questa impostazione per accelerare il processo di esportazione. Si noti che i file nativi verranno esportati in qualsiasi caso.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p112">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled. If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files** to include source files in the package content. You can clear this setting to speed up the export process. Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="ebdf7-157">In **metadati**, selezionare le opzioni seguenti nell'elenco **Esporta modello** (una sola volta per sessione).</span><span class="sxs-lookup"><span data-stu-id="ebdf7-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="ebdf7-p113">**Standard**: insieme di proprietà, metadati ed elementi di dati di base. Utilizzare questa opzione quando si importa dati è stato già elaborati di eDiscovery avanzate e caricamento di esportare dati a un sistema che già contiene i file. Per impostazione predefinita, esportare modelli colonne vengono create e piena.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p113">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="ebdf7-p114">**Tutti**: insieme completo di metadati standard, inclusi tutti i dati di elaborazione, nonché punteggi Analyze e pertinenza. In questo modello è obbligatorio quando eDiscovery avanzate consente di eseguire l'elaborazione e caricamento di dati dei file a un sistema esterno per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p114">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="ebdf7-163">**Problemi**: consente di selezionare **Tutti i problemi** o selezionare un particolare problema è stato creato.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="ebdf7-164">Nella sezione **destinazione**:</span><span class="sxs-lookup"><span data-stu-id="ebdf7-164">Under **Destination**:</span></span>
    
  - <span data-ttu-id="ebdf7-165">**Scaricare nel computer locale**</span><span class="sxs-lookup"><span data-stu-id="ebdf7-165">**Download to local machine**</span></span>
    
  - <span data-ttu-id="ebdf7-166">**Esporta in definita dall'utente blob Azure**: se questa opzione è selezionata, è possibile specificare un token di URL e SAS contenitore.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebdf7-p115">Una volta che viene archiviato un pacchetto di esportazione per l'utente definito blob Azure, i dati non è più gestiti da avanzate eDiscovery; viene gestita da blob Azure. Di conseguenza, che se si elimina il caso, i file esportati rimangono ancora in Azure blob.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p115">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="ebdf7-169">**Token SAS salvare per sessione di esportazione future**: se selezionato, il token SAS verrà crittografato nel database interno di eDiscovery avanzate per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebdf7-p116">Il token SAS attualmente scade dopo un mese. Se si tenta di scaricare dopo avere più di un mese che è necessario annullare l'ultima sessione, quindi rieseguire l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p116">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="ebdf7-172">Fare clic su **Modifica** per impostare il "per la revisione ' Impostazioni campo.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-172">Click **Modify** to set the "for review' field settings.</span></span> 
    
> ![Impostare per la revisione campo impostazioni per un batch di esportazione](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
    In **For review field settings** panel, in **Select scenario**, select the scenario and scope of the review. The settings are displayed based on your selection.
    
    **Review all** (default): All emails, attachments, and documents are selected by default. 
    
    **Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.
    
    **Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. 
    
    If you select custom, you can then customize the settings for emails, documents, attachments and miscellaneous.
    
> <span data-ttu-id="ebdf7-174">Selezionare i messaggi di posta elettronica che si desidera esportare **messaggi di posta elettronica** :</span><span class="sxs-lookup"><span data-stu-id="ebdf7-174">In **Emails** select the emails you want to export:</span></span> 
    
    **All emails**: (default) All emails are selected.
    
    **Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.
    
    **Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .
    
> <span data-ttu-id="ebdf7-175">Selezionare i documenti che si desidera esportare **documenti** :</span><span class="sxs-lookup"><span data-stu-id="ebdf7-175">In **Documents** select the documents you want to export:</span></span> 
    
    **All documents**: (default) All documents are selected.
    
    **Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.
    
    **Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).
    
> <span data-ttu-id="ebdf7-176">Selezionare gli allegati che si desidera esportare **gli allegati**</span><span class="sxs-lookup"><span data-stu-id="ebdf7-176">In **Attachments** select the attachments you want to export</span></span> 
    
    **All attachments**: (default) All attachments are selected.
    
    **Unique attachment in case level**: Unique attachment files within the specified case.
    
    **Unique attachment in email set level**: Unique attachment files within the specified email case.
    
> <span data-ttu-id="ebdf7-p117">In **Micellaneous** è possibile scegliere di **trattare allegati come documenti**, **considera i messaggi di posta elettronica come documenti**o **Espandi per includere i file della famiglia**. Quando si sceglie **Expand per includere i file della famiglia**, per ogni file è contrassegnato per la revisione, tutti i file della stessa famiglia inoltre essere contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p117">In **Micellaneous** you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**. When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
    Choose **Save** to save the settings. 
    
7. <span data-ttu-id="ebdf7-179">Dopo avere specificato i parametri di esportazione, per avviare il batch di esportazione, fare clic su **Crea esportare sessione**.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-179">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="ebdf7-p118">Durante l'esportazione, lo stato viene visualizzato lo stato delle **attività**. I risultati vengono visualizzati **nell'esportazione riepilogo**.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p118">During export, the status is displayed in **Task status**. The results are displayed in **Export summary**.</span></span>
    
8. <span data-ttu-id="ebdf7-182">Nella finestra **Download file** fare clic su **Copia negli Appunti** per copiare la chiave di esportazione.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-182">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![Download dei file](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
9. <span data-ttu-id="ebdf7-184">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-184">Click **Close**.</span></span> 
    
    <span data-ttu-id="ebdf7-185">Strumento di esportazione di eDiscovery è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-185">The eDiscovery Export Tool is started.</span></span>
    
    ![Strumento di esportazione di eDiscovery](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
10. <span data-ttu-id="ebdf7-187">In **eDiscovery esportare strumento**:</span><span class="sxs-lookup"><span data-stu-id="ebdf7-187">In the **eDiscovery Export Tool**:</span></span>
    
1. <span data-ttu-id="ebdf7-188">In **incollare la firma di accesso condiviso che verrà utilizzato per la connessione all'origine**, incollare la chiave di esportazione che youcopied negli Appunti nel passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-188">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
2. <span data-ttu-id="ebdf7-189">Fare clic su **Sfoglia** per selezionare il percorso di destinazione per archiviare i file di esportazione scaricato nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-189">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
11. <span data-ttu-id="ebdf7-p119">Fare clic su **Start**. Esportare i file vengono scaricati nel computer locale. Se si sceglie **Esporta in blob Azure definita dall'utente** nel passaggio 4, la sessione viene esportata in una destinazione di URL di archiviazione Blob di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p119">Click **Start**.The export files are downloaded to the local machine. If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span> 
    
<span data-ttu-id="ebdf7-192">Per una descrizione completa dei campi del rapporto di esportazione, vedere [esportare i campi del report](export-report-fields-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="ebdf7-192">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="ebdf7-193">Esportare i file di output di report</span><span class="sxs-lookup"><span data-stu-id="ebdf7-193">Export report output files</span></span>
<span data-ttu-id="ebdf7-194"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="ebdf7-194"></span></span>

<span data-ttu-id="ebdf7-195">Nella tabella seguente sono elencati i file di output generati durante l'esecuzione di un batch di esportazione.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-195">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="ebdf7-196">**Nome di file**</span><span class="sxs-lookup"><span data-stu-id="ebdf7-196">**File name**</span></span>|<span data-ttu-id="ebdf7-197">**Tipo file**</span><span class="sxs-lookup"><span data-stu-id="ebdf7-197">**File type**</span></span>|<span data-ttu-id="ebdf7-198">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ebdf7-198">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ebdf7-199">Riepilogo di esportazione</span><span class="sxs-lookup"><span data-stu-id="ebdf7-199">Export summary</span></span>  <br/> |<span data-ttu-id="ebdf7-200">CSV</span><span class="sxs-lookup"><span data-stu-id="ebdf7-200">csv</span></span>  <br/> |<span data-ttu-id="ebdf7-201">File di registro generato dallo strumento di esportazione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-201">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="ebdf7-202">Traccia</span><span class="sxs-lookup"><span data-stu-id="ebdf7-202">Trace</span></span>  <br/> |<span data-ttu-id="ebdf7-203">txt</span><span class="sxs-lookup"><span data-stu-id="ebdf7-203">txt</span></span>  <br/> |<span data-ttu-id="ebdf7-204">File di registro generato dallo strumento di esportazione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-204">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="ebdf7-205">File di testo estratto</span><span class="sxs-lookup"><span data-stu-id="ebdf7-205">Extracted text files</span></span>  <br/> |<span data-ttu-id="ebdf7-206">Cartella del file</span><span class="sxs-lookup"><span data-stu-id="ebdf7-206">File folder</span></span>  <br/> |<span data-ttu-id="ebdf7-207">Cartella che contiene i file di testo estratto del file esportati.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-207">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="ebdf7-208">File nativi o input</span><span class="sxs-lookup"><span data-stu-id="ebdf7-208">Input or native files</span></span>  <br/> |<span data-ttu-id="ebdf7-209">Cartella del file</span><span class="sxs-lookup"><span data-stu-id="ebdf7-209">File folder</span></span>  <br/> |<span data-ttu-id="ebdf7-210">Cartella che contiene i file nativi e di input del file esportati.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-210">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="ebdf7-211">Esporta elenco</span><span class="sxs-lookup"><span data-stu-id="ebdf7-211">Export list</span></span>  <br/> |<span data-ttu-id="ebdf7-212">xlsx</span><span class="sxs-lookup"><span data-stu-id="ebdf7-212">xlsx</span></span>  <br/> |<span data-ttu-id="ebdf7-p120">Metadati file esportato in formato xlsx. Campi nei file vengono fornite in base al modello utente seleziona da esportare. Se necessario, vengono creati file diversi, ognuno contiene righe 100-150 KB. Se un determinato valore contiene più caratteri di una cella di Excel può contenere (attualmente il limite è 32.767 caratteri), quindi il valore viene ritagliato per la lunghezza massima consentita. Se un valore viene tagliato, il colore di sfondo della cella è rosso a indicare che si all'utente." I partecipanti di posta elettronica"sono un esempio di un campo che può superare il limite di lunghezza, se è stato inviato il messaggio di posta elettronica a una distribuzione di grandi dimensioni. Per informazioni dettagliate sui campi di output, vedere [esportare i campi del report](export-report-fields-in-advanced-ediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p120">Exported files metadata in xlsx format. Fields in files are according to template user selects to export. If needed, several files are created, each contains 100-150K rows. If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed. If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution. See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.  </span></span><br/> |
|<span data-ttu-id="ebdf7-219">File di caricamento</span><span class="sxs-lookup"><span data-stu-id="ebdf7-219">Load file</span></span>  <br/> |<span data-ttu-id="ebdf7-220">CSV</span><span class="sxs-lookup"><span data-stu-id="ebdf7-220">csv</span></span>  <br/> |<span data-ttu-id="ebdf7-p121">Metadati file esportato in formato csv per il caricamento in un'altra applicazione. Campi nei file vengono fornite in base al modello utente seleziona da esportare.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p121">Exported files metadata in csv format for loading into a different application. Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="ebdf7-223">Indicatore di operazione riuscita</span><span class="sxs-lookup"><span data-stu-id="ebdf7-223">Success indicator</span></span>  <br/> |<span data-ttu-id="ebdf7-224">txt</span><span class="sxs-lookup"><span data-stu-id="ebdf7-224">txt</span></span>  <br/> |<span data-ttu-id="ebdf7-p122">Create solo per l'esportazione per un 3rd parti blob Azure. Se l'esportazione completata correttamente, verrà creato il file. In caso di errore, o parziale esito positivo del file non verrà creato. Verrà creato il file nella cartella radice, consentendo di rilevamento automatico in diversi stati batch/sessioni di esportazione. Si tratta di un file vuoto. È il nome: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span><span class="sxs-lookup"><span data-stu-id="ebdf7-p122">Only created when exporting to a 3rd party Azure blob. If export succeed completely, the file will be created. In case of failure, or partial success the file will not be created. File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses. This is an empty file. Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ebdf7-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebdf7-231">See also</span></span>
<span data-ttu-id="ebdf7-232"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="ebdf7-232"></span></span>

[<span data-ttu-id="ebdf7-233">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ebdf7-233">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ebdf7-234">Visualizzazione della cronologia batch e l'esportazione dei risultati passati</span><span class="sxs-lookup"><span data-stu-id="ebdf7-234">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="ebdf7-235">Impostazione rapida di Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ebdf7-235">Quick setup for Office 365 Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="ebdf7-236">Esportare i campi del report</span><span class="sxs-lookup"><span data-stu-id="ebdf7-236">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ebdf7-237">Aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365</span><span class="sxs-lookup"><span data-stu-id="ebdf7-237">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)
