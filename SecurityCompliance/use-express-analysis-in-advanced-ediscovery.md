---
title: Usare Analisi rapida in Office 365 Advanced eDiscovery
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Informazioni su come eseguire la modalità di analisi Express di Office 365 avanzate eDiscovery
ms.openlocfilehash: a71e6775b1116e805e455815dca53a727d887809
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530664"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="447a7-103">Usare Analisi rapida in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="447a7-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="447a7-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="447a7-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="447a7-106">È possibile utilizzare **Express analisi** per analizzare rapidamente un caso ed esportare i risultati.</span><span class="sxs-lookup"><span data-stu-id="447a7-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="447a7-p102">È possibile utilizzare analysis express per calcolare quasi duplicati e thread di posta elettronica e calcolare i temi. È inoltre possibile impostare alcuni parametri per i temi, similarità documenti e i file di esportazione in [Impostazioni avanzate per l'analisi Express](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span><span class="sxs-lookup"><span data-stu-id="447a7-p102">You can use express analysis to calculate near-duplicates and email threads and calculate themes. You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="447a7-109">Eseguire l'analisi del Express</span><span class="sxs-lookup"><span data-stu-id="447a7-109">Run Express analysis</span></span>

1. <span data-ttu-id="447a7-110">Nella scheda **analisi Express** (1), selezionare un contenitore per abilitare il * * Express analisi * * (2) e pulsanti **Impostazioni avanzate** .</span><span class="sxs-lookup"><span data-stu-id="447a7-110">In the **Express analysis** (1) tab, select a container to enable the ** Express analysis ** (2), and **Advanced settings** buttons.</span></span> 
    
    ![Cattura di schermata della pagina analisi Express](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="447a7-112">Nella sezione **parametri di analisi**:</span><span class="sxs-lookup"><span data-stu-id="447a7-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="447a7-p103">Se si desidera eseguire l'analisi di controllo **calcolare quasi duplicati e thread di posta elettronica** . È selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="447a7-p103">Check **Calculate near-duplicates and email threads** if you want to run the analysis. It is selected by default.</span></span> 
    
  - <span data-ttu-id="447a7-p104">Controllare **I temi calcolare** per elaborare tutti i file e assegnare loro temi. È selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="447a7-p104">Check **Calculate Themes** to process all files and assign themes to them. It is selected by default.</span></span> 
    
3. <span data-ttu-id="447a7-117">In **destinazione esportare**:</span><span class="sxs-lookup"><span data-stu-id="447a7-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="447a7-118">Controllare **il Download nel computer locale** per il download nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="447a7-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="447a7-119">Se si seleziona **Esporta in definita dall'utente Azure blob** è inoltre possibile specificare un token di URL e SAS contenitore.</span><span class="sxs-lookup"><span data-stu-id="447a7-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="447a7-p105">Una volta che viene archiviato un pacchetto di esportazione per l'utente definito Azure blob, i dati non è più gestiti da eDiscovery avanzate. viene gestita da blob Azure. Di conseguenza, che se si elimina il caso, i file esportati rimangono ancora in Azure blob.</span><span class="sxs-lookup"><span data-stu-id="447a7-p105">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery. it is managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="447a7-123">**Token SAS salvare per sessione di esportazione future**: se selezionato, il token SAS verrà crittografato nel database interno di eDiscovery avanzate per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="447a7-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="447a7-p106">Il token SAS attualmente scade dopo un mese. Se si tenta di scaricare dopo avere più di un mese che è necessario annullare l'ultima sessione, quindi rieseguire l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="447a7-p106">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="447a7-126">Per avviare l'analisi express con predefinito delle impostazioni, scegliere **Express analisi**e verrà visualizzata la pagina **stato attività**</span><span class="sxs-lookup"><span data-stu-id="447a7-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="447a7-127">Nella pagina **stato dell'attività** è possibile espandere le schede **processo**, **analisi** ed **esportare** per visualizzare informazioni dettagliate sull'esecuzione express.</span><span class="sxs-lookup"><span data-stu-id="447a7-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![Cattura di schermata di eDiscovery Express analisi attività stato pagina avanzata](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="447a7-129">Selezionare la pagina **Express analysis riepilogo** per elencare le informazioni dettagliate sull'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="447a7-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="447a7-p107">Nella parte inferiore della pagina **Express analysis riepilogo** , selezionare **Scarica ultima sessione** per scaricare l'elaborazione delle transazioni analisi dei file nel computer locale. Innanzitutto è necessario scaricare dello strumento di esportazione di eDiscovery e incollare la chiave di esportazione per lo strumento di esportazione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="447a7-p107">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer. You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="447a7-132">Impostazioni avanzate per l'analisi Express</span><span class="sxs-lookup"><span data-stu-id="447a7-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="447a7-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="447a7-133"></span></span>

<span data-ttu-id="447a7-134">È anche possibile impostare **le impostazioni avanzate** per modificare i parametri di analisi Express predefiniti.</span><span class="sxs-lookup"><span data-stu-id="447a7-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="447a7-135">Nella sezione **analisi** :</span><span class="sxs-lookup"><span data-stu-id="447a7-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="447a7-136">Nella **quasi duplicati e thread di posta elettronica**, immettere il valore **similarità documento** o accettare il valore predefinito è 65%.</span><span class="sxs-lookup"><span data-stu-id="447a7-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="447a7-p108">Immettere il **numero massimo di temi** o selezionare un valore per il numero di temi per creare. Il valore predefinito è 200.</span><span class="sxs-lookup"><span data-stu-id="447a7-p108">In the **Max number of themes** enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="447a7-p109">L'aumento del numero di temi influisce sulle prestazioni, nonché la possibilità di un tema per generalizzare. Maggiore è il numero di temi, più granulare sono. Se, ad esempio, un insieme di 50 temi includa un tema, ad esempio "Pallacanestro, tramite il, elettrico, Lakers"; 300 temi possono includere i temi separati: "Tramite il", "E", "Lakers". Se si non consapevolezza del tema "Pallacanestro" e utilizzare questa caratteristica per ECA, visualizzando il tema "Pallacanestro" può essere utile. Tuttavia, se l'elaborazione hanno un numero eccessivo di temi, che non venga visualizzato la parola "Pallacanestro" e non possono essere noti che tramite il ed elettrico è buone temi pallacanestro per esaminare, anziché gli elementi da inserire nel viene avviato e utilizzato per fini.</span><span class="sxs-lookup"><span data-stu-id="447a7-p109">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="447a7-p110">Scegliere **Modifica** i suggerimenti tratti tema per controllare l'elaborazione di temi **suggeriti temi** . EDiscovery avanzate verrà occuparsi di queste parole suggerite e tenta di creare uno o più temi rilevanti, in base alle impostazioni "Max numero di temi".</span><span class="sxs-lookup"><span data-stu-id="447a7-p110">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="447a7-p111">Ad esempio, se la parola consigliata è "computer" e specificato "2" come "numero massimo di temi", eDiscovery avanzate tenterà di generare due temi correlate alla parola "computer". Due temi potrebbero essere "computer" hardware e "software", ad esempio.</span><span class="sxs-lookup"><span data-stu-id="447a7-p111">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![Aggiungi tema suggerito](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="447a7-149">**Modalità** Dall'elenco a discesa selezionare un'opzione di **temi** :</span><span class="sxs-lookup"><span data-stu-id="447a7-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="447a7-150">**Creare e applicare modelli**: calcola temi dai modelli da un segmento dei file e quindi distribuisce i file tra loro.</span><span class="sxs-lookup"><span data-stu-id="447a7-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="447a7-p112">**Crea modello**: calcola un modello di temi di un segmento dei file. Il processo di applica della divisione di file è terminato separatamente in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="447a7-p112">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="447a7-p113">**Applica modello**: questa opzione viene visualizzata solo se un modello è stato creato in precedenza e non ancora applicato. Ciò consente di dividere il file in base ai temi.</span><span class="sxs-lookup"><span data-stu-id="447a7-p113">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="447a7-155">Nella sezione **esportazione** :</span><span class="sxs-lookup"><span data-stu-id="447a7-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="447a7-156">Nel **batch di esportazione selezionare**:</span><span class="sxs-lookup"><span data-stu-id="447a7-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="447a7-157">Nell'elenco **Esporta batch** , selezionare il nome del batch o esportare i risultati in batch esportazione 01 (batch predefinito).</span><span class="sxs-lookup"><span data-stu-id="447a7-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="447a7-p114">Per esportare i risultati per i nuovi file aggiunti a un caso esistente, continuare con il batch corrente. Per creare una sessione nel batch, selezionare lo stesso numero di batch e fare clic su **Crea esportare sessione** è possibile utilizzare questa opzione per esportare gli stessi parametri come processo batch precedente, in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="447a7-p114">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="447a7-p115">Per esportare in un nuovo batch, fare clic su **Aggiungi**![aggiungere icona](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) e immettere un nuovo nome nella **casella Nome Batch** (o accettare il valore predefinito) e una descrizione nella **casella Descrizione Batch**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="447a7-p115">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="447a7-162">Per modificare un nome di batch o la descrizione, selezionare il nome di **esportazione batch**, fare clic su **Modifica** ![sull'icona Modifica](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)e quindi modificare i campi.</span><span class="sxs-lookup"><span data-stu-id="447a7-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="447a7-p116">Dopo aver eseguito le sessioni per un batch di esportazione, non possono essere eliminate. Inoltre, solo alcuni parametri possono essere modificati dopo la prima sessione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="447a7-p116">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="447a7-165">Per creare un batch di esportazione duplicati, scegliere **Copia esportazione batch**![creare un'icona di batch esportazione duplicati](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) e immettere un nome e una descrizione per il batch duplicato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="447a7-165">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="447a7-166">Per eliminare un batch di esportazione, scegliere **Elimina**![Elimina un'icona di batch esportazione](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span><span class="sxs-lookup"><span data-stu-id="447a7-166">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="447a7-167">Per visualizzare la cronologia di un batch, scegliere **cronologia Batch**![sull'icona di visualizzazione cronologia](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span><span class="sxs-lookup"><span data-stu-id="447a7-167">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="447a7-p117">In definire p **opulation:** selezionare **includere solo i file sopra punteggio di pertinenza demarcazione** e/o **batch esportazione Affina ricerca** se si desidera ottimizzare le impostazioni per il batch di esportazione. Se si seleziona **includere solo i file sopra punteggio di pertinenza interruzione**, il **problema** è abilitata e se punteggio di pertinenza del file è superiore al punteggio di interruzione per il rilascio selezionato, quindi viene esportato il file. Il file verrà esportato a meno che non viene escluso per il ' filtro **per la revisione** . Se si seleziona **Affina ricerca esportazione batch**, quindi il **deprovisioning dupe** e **Filter by 'Per revisione' campo** sono abilitati i pulsanti di opzione. Se si sceglie **deprovisioning dupe**, quindi i file duplicati verranno essere filtrati in uscita in base ai criteri definiti: [caso livello (impostazione predefinita): da ogni insieme di file duplicati nell'intero caso, sarà deprovisioning duped file tutti tranne uno. Livello depositaria: da ogni insieme di file duplicati della stessa depositaria, sarà deprovisioning duped file tutti tranne uno. Un record di tutti i file duplicati è disponibile nell'output di esportazione. Se si sceglie campo **filtro in base a 'per la revisione'** , selezionare **Modifica in metadati** immettere le impostazioni di campo **'per la revisione'**. Selezionare **Includi file di input**per includere i file di origine di contenuto del pacchetto. È possibile deselezionare questa opzione per accelerare il processo di esportazione. Si noti che i file nativi verranno esportati in qualsiasi caso.</span><span class="sxs-lookup"><span data-stu-id="447a7-p117">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch. If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported. The file will be exported unless it's excluded by the ' **For review** filter. If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled. If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped. A record of all duplicate files is available in export output. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files**to include source files in the package content. You can clear this option to speed up the export process. Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="447a7-179">In **definire metadati**, selezionare le opzioni seguenti nell'elenco **Esporta modello** (una sola volta per sessione).</span><span class="sxs-lookup"><span data-stu-id="447a7-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="447a7-p118">**Standard**: insieme di proprietà, metadati ed elementi di dati di base. Utilizzare questa opzione quando si importa dati è stato già elaborati di eDiscovery avanzate e caricamento di esportare dati a un sistema che già contiene i file. Per impostazione predefinita, esportare modelli colonne vengono create e piena.</span><span class="sxs-lookup"><span data-stu-id="447a7-p118">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="447a7-p119">**Tutti**: insieme completo di metadati standard, inclusi tutti i dati di elaborazione, nonché punteggi Analyze e pertinenza. In questo modello è obbligatorio quando eDiscovery avanzate consente di eseguire l'elaborazione e caricamento di dati dei file a un sistema esterno per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="447a7-p119">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="447a7-185">**Problemi**: consente di selezionare **Tutti i problemi** o selezionare un particolare problema è stato creato.</span><span class="sxs-lookup"><span data-stu-id="447a7-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="447a7-186">Fare clic su **OK**per salvare le impostazioni avanzate, **ripristinare i valori predefiniti** per utilizzare i valori predefiniti o **Annulla** per annullare l'impostazione impostazioni avanzate.</span><span class="sxs-lookup"><span data-stu-id="447a7-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="447a7-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="447a7-187">See also</span></span>
<span data-ttu-id="447a7-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="447a7-188"></span></span>

[<span data-ttu-id="447a7-189">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="447a7-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

