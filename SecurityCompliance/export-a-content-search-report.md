---
title: Esportare il rapporto della Ricerca contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Invece di esportare i risultati effettivi di una ricerca contenuto nel centro sicurezza &amp; e conformità di Office 365, è possibile esportare solo un rapporto sui risultati di ricerca. Il report contiene un riepilogo dei risultati della ricerca e un documento con informazioni dettagliate su ogni elemento che verrebbe esportato.
ms.openlocfilehash: d98f70d4f38f524de8751aecb197d0f85ee7f088
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295979"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="65fb9-104">Esportare il rapporto della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="65fb9-104">Export a Content Search report</span></span>

<span data-ttu-id="65fb9-105">Invece di esportare il set completo di risultati della ricerca da una ricerca di contenuto nel centro sicurezza &amp; e conformità di Office 365 (e da una ricerca di contenuto associata a un caso di eDiscovery), è possibile esportare solo gli stessi rapporti che vengono generati quando si esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="65fb9-105">Instead of exporting the full set of search results from a Content Search in the Office 365 Security &amp; Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="65fb9-p102">Quando si esporta un report, viene scaricato in una cartella con lo stesso nome della ricerca di contenuto, ma accodato con *_ReportsOnly* . Ad esempio, se la ricerca di contenuto è denominata *ContosoCase0815* , il report viene scaricato in una cartella denominata *ContosoCase0815_ReportsOnly* . Per un elenco dei documenti inclusi nel report, vedere [What ' s incluso nel report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="65fb9-p102">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  . For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  . For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="65fb9-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="65fb9-109">Before you begin</span></span>

- <span data-ttu-id="65fb9-p103">Per esportare un rapporto di ricerca contenuto, è necessario che il ruolo di gestione della ricerca di conformità sia assegnato al &amp; Centro sicurezza e conformità di Office 365. Questo ruolo viene assegnato ai gruppi di ruoli di gestione eDiscovery e dell'organizzazione incorporati. Non viene assegnato per impostazione predefinita al gruppo di ruoli Gestione organizzazione. Per ulteriori informazioni, vedere [assegnare le autorizzazioni di eDiscovery nel centro sicurezza &amp; e conformità di Office 365](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="65fb9-p103">To export a Content Search report, you have to be assigned the Compliance Search management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager and Organization Management role groups. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="65fb9-p104">Quando si esporta un report, i dati vengono temporaneamente archiviati in un'area di archiviazione di Windows Azure univoca nel cloud Microsoft prima che vengano scaricati nel computer locale. verificare che l'organizzazione sia in grado di connettersi all'endpoint in Azure, che è \*\* \*. blob.core.windows.net\*\* (il carattere jolly rappresenta un identificatore univoco per l'esportazione). I dati dei risultati della ricerca vengono eliminati dall'area di archiviazione di Azure due settimane dopo la sua creazione.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p104">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="65fb9-117">Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:</span><span class="sxs-lookup"><span data-stu-id="65fb9-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="65fb9-118">Windows 7 a 32 o 64 bit e versioni successive</span><span class="sxs-lookup"><span data-stu-id="65fb9-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="65fb9-119">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="65fb9-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="65fb9-120">Browser supportato:</span><span class="sxs-lookup"><span data-stu-id="65fb9-120">A supported browser:</span></span>
    
    - <span data-ttu-id="65fb9-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="65fb9-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="65fb9-122">oppure</span><span class="sxs-lookup"><span data-stu-id="65fb9-122">or</span></span>
    
    - <span data-ttu-id="65fb9-123">Microsoft Internet Explorer 10 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="65fb9-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="65fb9-p105">**Nota:** Microsoft non produce estensioni o componenti aggiuntivi di terze parti per le applicazioni ClickOnce. L'esportazione dei risultati di ricerca utilizzando un browser non supportato con le estensioni di terze parti o i componenti aggiuntivi non è supportata.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="65fb9-p106">Se la dimensione totale stimata dei risultati restituiti da una ricerca di contenuto supera&nbsp;i 20 TB, l'esportazione del rapporto avrà esito negativo. Per esportare correttamente il report, provare a restringere l'ambito ed eseguire di nuovo la ricerca in modo che la dimensione stimata dei risultati&nbsp;sia inferiore a 20 TB.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p106">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail. To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

- <span data-ttu-id="65fb9-p107">L'esportazione dei rapporti di ricerca del contenuto conta sul numero massimo di esportazioni in esecuzione contemporaneamente e sul numero massimo di esportazioni che un singolo utente può eseguire. Per ulteriori informazioni sui limiti di esportazione, vedere [Export content search results from the Office 365 Security _AMP_ Compliance Center](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="65fb9-p107">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run. For more information about export limits, see [Export Content Search results from the Office 365 Security & Compliance Center](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="65fb9-130">Generare e scaricare un report di ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="65fb9-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="65fb9-131">La procedura per generare e scaricare un rapporto di ricerca contenuto è molto simile all'esportazione dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="65fb9-131">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="65fb9-132">Passaggio 1: generare il report per l'esportazione</span><span class="sxs-lookup"><span data-stu-id="65fb9-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="65fb9-p108">Il primo passaggio consiste nel preparare il report per il download nel computer che esporta. Quando si esegue il report, i documenti del report vengono caricati in un'area di archiviazione di Azure nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p108">The first step is to prepare the report for downloading to your computer exporting. When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="65fb9-135">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="65fb9-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="65fb9-136">Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="65fb9-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="65fb9-137">Nel riquadro a sinistra del Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **Ricerca contenuto**.</span><span class="sxs-lookup"><span data-stu-id="65fb9-137">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="65fb9-138">Nella pagina **Ricerca contenuto** selezionare una ricerca.</span><span class="sxs-lookup"><span data-stu-id="65fb9-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="65fb9-139">Nel riquadro dei dettagli, in **Esporta rapporto in un computer**, fare clic su **genera report**.</span><span class="sxs-lookup"><span data-stu-id="65fb9-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="65fb9-p109">Se i risultati di una ricerca risalgono a più di 7 giorni, viene richiesto di aggiornare i risultati della ricerca. In tal caso, annullare l'esportazione, fare clic su **Aggiorna i risultati della ricerca** nel riquadro dei dettagli per la ricerca selezionata e quindi avviare di nuovo l'esportazione del rapporto dopo l'aggiornamento dei risultati.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p109">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="65fb9-142">Nella pagina **Esporta un report** , in **Includi questi elementi della ricerca**, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="65fb9-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="65fb9-143">Esportare solo gli elementi indicizzati</span><span class="sxs-lookup"><span data-stu-id="65fb9-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="65fb9-144">Esportare gli elementi indicizzati e non</span><span class="sxs-lookup"><span data-stu-id="65fb9-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="65fb9-145">Esportare solo gli elementi non indicizzati</span><span class="sxs-lookup"><span data-stu-id="65fb9-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="65fb9-146">Per ulteriori informazioni sugli elementi non indicizzati, vedere [elementi indicizzaTi parzialmente nella ricerca contenuto](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="65fb9-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="65fb9-p110">Scegliere di includere le statistiche di ricerca per tutte le versioni dei documenti di SharePoint. Questa opzione viene visualizzata solo se le origini di contenuto della ricerca includono i siti di SharePoint o OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p110">Choose to include search statistics for all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="65fb9-149">Fare clic su **genera report**.</span><span class="sxs-lookup"><span data-stu-id="65fb9-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="65fb9-p111">Il report dei risultati della ricerca è pronto per il download, il che significa che i documenti del rapporto verranno caricati nell'area di archiviazione di Azure nel cloud Microsoft. Quando il report è pronto per il download, il collegamento del **rapporto di download** viene visualizzato in **Esporta rapporto in un computer** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p111">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud. When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="65fb9-p112">È inoltre possibile esportare un report per una ricerca di contenuto associata a un caso di eDiscovery. A tale scopo, andare a **Search &amp; Investigation** \> **eDiscovery**, selezionare un caso, quindi fare \*\*\*\* ![clic su modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)icona modifica. Nella pagina **ricerche** selezionare una ricerca e quindi fare clic su \*\*\*\* ![Esporta esportazione dei risultati della ricerca](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **l'icona Esporta un report**.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p112">You can also export a report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="65fb9-155">Passaggio 2: scaricare il report</span><span class="sxs-lookup"><span data-stu-id="65fb9-155">Step 2: Download the report</span></span>

<span data-ttu-id="65fb9-156">Il passaggio successivo consiste nel scaricare il report dall'area di archiviazione di Azure nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="65fb9-156">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="65fb9-157">Nel riquadro dei dettagli per la ricerca per la quale è stato generato il report, in **Esporta rapporto in un computer**, fare clic su **Scarica report**.</span><span class="sxs-lookup"><span data-stu-id="65fb9-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="65fb9-158">Viene visualizzata la pagina del **rapporto di download** contenente le seguenti informazioni sul rapporto finché non vengono scaricati nel computer.</span><span class="sxs-lookup"><span data-stu-id="65fb9-158">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="65fb9-159">Il numero di elementi che verranno scaricati.</span><span class="sxs-lookup"><span data-stu-id="65fb9-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="65fb9-160">La dimensione totale stimata degli elementi che verranno scaricati.</span><span class="sxs-lookup"><span data-stu-id="65fb9-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="65fb9-p113">Se verranno esportati o meno indicizzati. Gli elementi non indicizzati sono elementi che hanno un formato riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p113">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="65fb9-163">Se verranno scaricate o meno versioni di documenti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="65fb9-163">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="65fb9-p114">Lo stato del processo di esportazione del report. È possibile iniziare a scaricare il report anche se la preparazione del report non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p114">The status of the report export process. You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="65fb9-p115">In **Esporta chiave**, fare clic su **copia negli Appunti**. Questo tasto verrà utilizzato nel passaggio 5 per scaricare il report.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p115">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="65fb9-168">Poiché tutti gli utenti possono installare e avviare lo strumento di esportazione di eDiscovery e quindi utilizzare questa chiave per scaricare il report di ricerca, assicurarsi di prendere precauzioni per proteggere questa chiave come se si proteggessero le password o altre informazioni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="65fb9-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="65fb9-169">Fare clic su **download report**.</span><span class="sxs-lookup"><span data-stu-id="65fb9-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="65fb9-170">Se viene richiesto di installare lo **strumento di esportazione di MicrosoftOffice 365 eDiscovery**, fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="65fb9-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="65fb9-171">Nello **Strumento di esportazione eDiscovery**, incollare la chiave di esportazione copiata nel passaggio 2 nella casella appropriata.</span><span class="sxs-lookup"><span data-stu-id="65fb9-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="65fb9-172">Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare il report.</span><span class="sxs-lookup"><span data-stu-id="65fb9-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="65fb9-173">Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer.</span><span class="sxs-lookup"><span data-stu-id="65fb9-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="65fb9-p116">Lo **strumento di esportazione di eDiscovery** Visualizza le informazioni sullo stato relative al processo di esportazione, inclusa una stima del numero e delle dimensioni degli elementi restanti da scaricare. Al termine del processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p116">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="65fb9-p117">È possibile scaricare il report per una ricerca di contenuto associata a un caso di eDiscovery. A tale scopo, andare a **Search &amp; Investigation** \> **eDiscovery**, selezionare un caso, quindi fare \*\*\*\* ![clic su modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)icona modifica. Nella pagina \*\*\*\* esportazioni selezionare l'esportazione di un report e quindi fare clic su **Scarica report** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p117">You can download the report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="65fb9-179">Elementi inclusi nel report</span><span class="sxs-lookup"><span data-stu-id="65fb9-179">What's included in the report</span></span>

<span data-ttu-id="65fb9-180">Quando si genera ed esporta un report sui risultati di una ricerca di contenuto, vengono scaricati i documenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="65fb9-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="65fb9-p118">**Riepilogo di esportazione** -documento di Excel che contiene un riepilogo dell'esportazione. Sono incluse informazioni quali il numero di origini di contenuto di cui è stata eseguita la ricerca, il numero di risultati di ricerca di ogni percorso del contenuto, il numero stimato di elementi, il numero effettivo di elementi che verrebbero esportati e le dimensioni stimate e effettive degli elementi. che verrebbe esportato.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p118">**Export Summary** - An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="65fb9-p119">Se si includono gli elementi non indicizzati durante l'esportazione del report, il numero di elementi non indicizzati viene incluso nel numero totale di risultati della ricerca stimati e nel numero totale di risultati della ricerca scaricati (se si desidera esportare i risultati della ricerca) elencati nel Esporta rapporto riepilogativo. In altre parole, il numero totale di elementi che verrebbero scaricati è uguale al numero totale di risultati stimati e al numero totale di elementi non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p119">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report. In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="65fb9-185">**Manifest** -file manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="65fb9-185">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="65fb9-p120">**Results** -un documento di Excel che contiene una riga contenente informazioni su ogni elemento indicizzato che verrebbe esportato con i risultati della ricerca. Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui:</span><span class="sxs-lookup"><span data-stu-id="65fb9-p120">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="65fb9-188">Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).</span><span class="sxs-lookup"><span data-stu-id="65fb9-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="65fb9-189">La data in cui è stato inviato o ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="65fb9-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="65fb9-190">La riga dell'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="65fb9-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="65fb9-191">Il mittente e i destinatari del messaggio.</span><span class="sxs-lookup"><span data-stu-id="65fb9-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="65fb9-192">Per i documenti provenienti da siti di SharePoint e OneDrive for business, il registro dei risultati contiene informazioni su ogni documento, tra cui:</span><span class="sxs-lookup"><span data-stu-id="65fb9-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="65fb9-193">L'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="65fb9-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="65fb9-194">L’URL per la raccolta di siti in cui si trova il documento.</span><span class="sxs-lookup"><span data-stu-id="65fb9-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="65fb9-195">La data dell'ultima modifica al documento.</span><span class="sxs-lookup"><span data-stu-id="65fb9-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="65fb9-196">Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).</span><span class="sxs-lookup"><span data-stu-id="65fb9-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="65fb9-197">Il numero di righe del rapporto **risultati** deve essere uguale al numero totale di risultati della ricerca da scaricare meno il numero totale di elementi elencati nel rapporto **elementi** non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="65fb9-197">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="65fb9-p121">**Elementi** non indicizzati: documento di Excel contenente informazioni su eventuali elementi non indicizzati che verrebbero inclusi nei risultati della ricerca. Se non si includono gli elementi non indicizzati durante la generazione del report dei risultati della ricerca, il report verrà comunque scaricato, ma sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="65fb9-p121">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results. If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
