---
title: Esportare il rapporto della Ricerca contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/25/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Invece di esportare i risultati effettivi della ricerca contenuto in Office 365 Security &amp; centro conformità, è possibile esportare solo un rapporto di risultati di ricerca. Il report contiene un riepilogo dei risultati della ricerca e un documento con informazioni dettagliate su ogni elemento che verrà esportata.
ms.openlocfilehash: 45415f25754b4549a919e4ce56853a6ae09a9bdc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530207"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="1f34e-104">Esportare il rapporto della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="1f34e-104">Export a Content Search report</span></span>

<span data-ttu-id="1f34e-105">Invece di esportare il set completo di ricerca di risultati di una ricerca di contenuto in Office 365 Security &amp; centro conformità e da una ricerca del contenuto associato a un caso di eDiscovery, è possibile esportare solo i report stessi sono generati quando si esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="1f34e-105">Instead of exporting the full set of search results from a Content Search in the Office 365 Security &amp; Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="1f34e-p102">Quando si esporta un report, viene scaricato in una cartella che ha lo stesso nome di ricerca del contenuto, ma che viene aggiunto con *_ReportsOnly* . Ad esempio, se la ricerca del contenuto denominata *ContosoCase0815* , il report viene scaricato in una cartella denominata *ContosoCase0815_ReportsOnly* . Per un elenco di documenti che sono inclusi nella relazione, vedere [che cos'è incluso nel report](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="1f34e-p102">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  . For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  . For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1f34e-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="1f34e-109">Before you begin</span></span>

- <span data-ttu-id="1f34e-p103">Per esportare un report di ricerca del contenuto, è necessario disporre del ruolo di gestione ricerca conformità in Office 365 Security &amp; centro conformità. Questo ruolo viene assegnato ai gruppi di ruolo Manager e la gestione dell'organizzazione eDiscovery incorporati. Non è assegnato per impostazione predefinita al gruppo di ruoli Gestione organizzazione. Per ulteriori informazioni, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1f34e-p103">To export a Content Search report, you have to be assigned the Compliance Search management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager and Organization Management role groups. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="1f34e-p104">Quando si esporta un report, i dati vengono archiviati temporaneamente in un'area di archiviazione di Windows Azure univoca nel cloud Microsoft prima di scaricarlo nel computer locale. Verificare che l'organizzazione può la connessione all'endpoint in Azure, ovvero \*\* \*. blob.core.windows.net\*\* (il carattere jolly rappresenta un identificatore univoco per l'esportazione). Dati dei risultati della ricerca viene eliminati dall'area di archiviazione Azure due settimane dopo averlo creato.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p104">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="1f34e-117">Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:</span><span class="sxs-lookup"><span data-stu-id="1f34e-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="1f34e-118">Windows 7 a 32 o 64 bit e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1f34e-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="1f34e-119">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="1f34e-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="1f34e-120">Browser supportato:</span><span class="sxs-lookup"><span data-stu-id="1f34e-120">A supported browser:</span></span>
    
    - <span data-ttu-id="1f34e-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1f34e-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="1f34e-122">oppure</span><span class="sxs-lookup"><span data-stu-id="1f34e-122">or</span></span>
    
    - <span data-ttu-id="1f34e-123">Microsoft Internet Explorer 10 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1f34e-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="1f34e-p105">**Nota:** Microsoft non produce delle estensioni di terze parti o componenti aggiuntivi per le applicazioni ClickOnce. Esportazione dei risultati della ricerca mediante un browser non supportato con le estensioni di terze parti o componenti aggiuntivi non è supportato.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
    
## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="1f34e-126">Generare e scaricare un report di ricerca del contenuto</span><span class="sxs-lookup"><span data-stu-id="1f34e-126">Generate and download a Content Search report</span></span>

<span data-ttu-id="1f34e-127">I passaggi per generare e scaricare un report di ricerca del contenuto sono molto simili ai effettivamente esportazione dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="1f34e-127">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="1f34e-128">Passaggio 1: Generare il report per l'esportazione</span><span class="sxs-lookup"><span data-stu-id="1f34e-128">Step 1: Generate the report for export</span></span>

<span data-ttu-id="1f34e-p106">Il primo passaggio consiste nel preparare il report per il download per l'esportazione di computer. Quando si il report il rapporto di documenti vengono caricati in un'area di archiviazione Azure in Microsoft cloud.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p106">The first step is to prepare the report for downloading to your computer exporting. When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="1f34e-131">Accedere a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="1f34e-131">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="1f34e-132">Accedere a Office 365 utilizzando l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="1f34e-132">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="1f34e-133">Nel riquadro a sinistra del Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **Ricerca contenuto**.</span><span class="sxs-lookup"><span data-stu-id="1f34e-133">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="1f34e-134">Nella pagina di **ricerca del contenuto** , selezionare una ricerca.</span><span class="sxs-lookup"><span data-stu-id="1f34e-134">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="1f34e-135">Nel riquadro dei dettagli, in **Esporta report in un computer**, fare clic su **Genera rapporto**.</span><span class="sxs-lookup"><span data-stu-id="1f34e-135">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1f34e-p107">Se i risultati di ricerca sono anteriori a 7 giorni, verrà richiesto di aggiornare i risultati della ricerca. In questo caso, annullare l'esportazione, fare clic su **risultati della ricerca di aggiornamento** nel riquadro dei dettagli per la ricerca selezionata e quindi avviare di nuovo l'esportazione di report dopo che i risultati vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p107">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="1f34e-138">Nella pagina **esportazione di un report** , in **includere questi elementi dalla ricerca**, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f34e-138">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="1f34e-139">Esportare solo gli elementi indicizzati</span><span class="sxs-lookup"><span data-stu-id="1f34e-139">Export only indexed items</span></span>
    
    - <span data-ttu-id="1f34e-140">Esportare gli elementi indicizzati e non</span><span class="sxs-lookup"><span data-stu-id="1f34e-140">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="1f34e-141">Esportare solo gli elementi non indicizzati</span><span class="sxs-lookup"><span data-stu-id="1f34e-141">Export only unindexed items</span></span>
    
    <span data-ttu-id="1f34e-142">Per ulteriori informazioni sugli elementi non indicizzate, vedere [parzialmente indicizzato gli elementi della funzionalità di ricerca del contenuto](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="1f34e-142">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="1f34e-p108">Scegliere se includere le statistiche di ricerca per tutte le versioni dei documenti di SharePoint. Questa opzione è disponibile solo se le origini di contenuto di ricerca include SharePoint o OneDrive per i siti.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p108">Choose to include search statistics for all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="1f34e-145">Fare clic su **Genera rapporto**.</span><span class="sxs-lookup"><span data-stu-id="1f34e-145">Click **Generate report**.</span></span>
    
    <span data-ttu-id="1f34e-p109">Report dei risultati di ricerca è preparato per il download, ovvero che i documenti report verranno caricati all'area di archiviazione Azure nel cloud Microsoft. Quando il report è pronto per il download, il collegamento **Download rapporto** viene visualizzato in **Esporta report in un computer** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p109">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud. When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1f34e-p110">È inoltre possibile esportare un report per una ricerca del contenuto associato a un caso eDiscovery. A tale scopo, passare a **ricerca &amp; indagini** \> selezionare un caso **eDiscovery**e fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). Nella pagina **ricerche** , selezionare una ricerca e quindi fare clic su **Esporta** ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **esportare un report**.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p110">You can also export a report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="1f34e-151">Passaggio 2: Scaricare i report</span><span class="sxs-lookup"><span data-stu-id="1f34e-151">Step 2: Download the report</span></span>

<span data-ttu-id="1f34e-152">Il passaggio successivo consiste nel scaricare il report dall'area di archiviazione Azure nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="1f34e-152">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="1f34e-153">Nel riquadro dei dettagli per la ricerca generato il rapporto, in **Esporta report in un computer**, fare clic su **Scarica report**.</span><span class="sxs-lookup"><span data-stu-id="1f34e-153">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="1f34e-154">La pagina **Scarica report** viene visualizzata e contiene le seguenti informazioni sul report fino ad essere scaricato nel computer.</span><span class="sxs-lookup"><span data-stu-id="1f34e-154">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="1f34e-155">Il numero di elementi che verranno scaricati.</span><span class="sxs-lookup"><span data-stu-id="1f34e-155">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="1f34e-156">La dimensione totale stimata degli elementi che verranno scaricati.</span><span class="sxs-lookup"><span data-stu-id="1f34e-156">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="1f34e-p111">Se non indicizzati o indicizzato verrà esportato. Elementi indicizzati sono gli elementi che dispongono di un formato riconosciuto, vengono crittografati o non indicizzati per altri motivi.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p111">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="1f34e-159">Se verranno scaricate o meno versioni di documenti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1f34e-159">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="1f34e-p112">Lo stato del processo di esportazione report. È possibile avviare il download del rapporto anche se la preparazione del report non viene completata.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p112">The status of the report export process. You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="1f34e-p113">In **Esporta chiave**, fare clic su **Copia negli Appunti**. Utilizzare questa chiave nel passaggio 5 per scaricare il report.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p113">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1f34e-164">Poiché tutti gli utenti possono installare e avviare lo strumento di esportazione di eDiscovery e quindi utilizzare questa chiave per scaricare il report di ricerca, è necessario adottare alcune precauzioni per proteggere la chiave nello stesso modo in cui è necessario proteggere password o altre informazioni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1f34e-164">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="1f34e-165">Fare clic su **Scarica report**.</span><span class="sxs-lookup"><span data-stu-id="1f34e-165">Click **Download report**.</span></span>
    
4. <span data-ttu-id="1f34e-166">Se viene richiesto di installare **Microsoft Office 365 eDiscovery esportare strumento**, fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="1f34e-166">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="1f34e-167">Nello **Strumento di esportazione eDiscovery**, incollare la chiave di esportazione copiata nel passaggio 2 nella casella appropriata.</span><span class="sxs-lookup"><span data-stu-id="1f34e-167">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="1f34e-168">Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare il report.</span><span class="sxs-lookup"><span data-stu-id="1f34e-168">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="1f34e-169">Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer.</span><span class="sxs-lookup"><span data-stu-id="1f34e-169">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="1f34e-p114">**EDiscovery dello strumento di esportazione** viene visualizzato il processo di esportazione, con una stima del numero e dimensione degli altri download di informazioni sullo stato. Una volta completato il processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p114">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1f34e-p115">È possibile scaricare il report per una ricerca del contenuto associato a un caso eDiscovery. A tale scopo, passare a **ricerca &amp; indagini** \> selezionare un caso **eDiscovery**e fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). Nella pagina **Esporta** selezionare Esporta un report e quindi fare clic su **Scarica report** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p115">You can download the report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="1f34e-175">Che cos'è incluso nel rapporto</span><span class="sxs-lookup"><span data-stu-id="1f34e-175">What's included in the report</span></span>

<span data-ttu-id="1f34e-176">Quando si genera e l'esportazione di un report sui risultati di ricerca di contenuto, vengono scaricati i documenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f34e-176">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="1f34e-p116">**Esportare riepilogo** - documento di Excel che contiene un riepilogo dell'esportazione. Sono incluse informazioni quali il numero di origini di contenuto in cui sono stati ricercati, il numero di risultati di ricerca ogni percorso contenuto, il numero stimato di elementi, il numero effettivo di elementi che potrebbe essere esportate e le dimensioni stimate ed effettiva di elementi che potrebbe essere esportati.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p116">**Export Summary** - An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1f34e-p117">Se si includono gli elementi indicizzati durante l'esportazione del report, il numero di elementi indicizzati viene incluso il numero totale di risultati di ricerca stimati e il numero totale di scaricati i risultati di ricerca (se fosse per esportare i risultati della ricerca) sono elencati nel Esportare il rapporto di riepilogo. In altre parole, il numero totale di elementi che potrebbe essere scaricato è uguale al numero totale di risultati stimati e il numero totale di elementi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p117">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report. In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="1f34e-181">**Manifesto** - un file manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="1f34e-181">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="1f34e-p118">**Risultati** - documento di Excel che contiene una riga con informazioni su ogni elemento indicizzato esportato con i risultati della ricerca. Per la posta elettronica, il registro risultato contiene informazioni su ogni messaggio, tra cui:</span><span class="sxs-lookup"><span data-stu-id="1f34e-p118">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="1f34e-184">Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).</span><span class="sxs-lookup"><span data-stu-id="1f34e-184">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="1f34e-185">La data in cui è stato inviato o ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="1f34e-185">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="1f34e-186">La riga dell'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1f34e-186">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="1f34e-187">Il mittente e i destinatari del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1f34e-187">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="1f34e-188">Per i documenti di SharePoint e OneDrive per i siti, il registro dei risultati contiene informazioni su tutti i documenti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="1f34e-188">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="1f34e-189">L'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="1f34e-189">The URL for the document.</span></span>
    
  - <span data-ttu-id="1f34e-190">L’URL per la raccolta di siti in cui si trova il documento.</span><span class="sxs-lookup"><span data-stu-id="1f34e-190">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="1f34e-191">La data dell'ultima modifica al documento.</span><span class="sxs-lookup"><span data-stu-id="1f34e-191">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="1f34e-192">Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).</span><span class="sxs-lookup"><span data-stu-id="1f34e-192">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1f34e-193">Il numero di righe nel report dei **risultati** deve essere uguale al numero totale dei risultati della ricerca scaricati meno il numero totale di elementi elencati nel rapporto di **Elementi indicizzati** .</span><span class="sxs-lookup"><span data-stu-id="1f34e-193">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="1f34e-p119">**Elementi indicizzati** : documento di Excel che contiene informazioni su eventuali elementi indicizzati inclusi nei risultati della ricerca. Se non si includono gli elementi indicizzati quando si genera il rapporto di risultati di ricerca, questo rapporto verrà scaricato, ma sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="1f34e-p119">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results. If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
