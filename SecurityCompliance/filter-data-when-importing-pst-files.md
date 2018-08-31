---
title: Filtrare i dati per l'importazione di file PST a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: "Utilizzare la nuova funzionalità di importazione intelligente nel servizio di Office 365 importazione per filtrare gli elementi che in realtà, l'importazione alle cassette postali di destinazione. Importazione intelligente consente di decidere in modo proattivo i dati da importare e sugli aspetti da tralasciare. Importazione intelligente offre anche informativa sui dati che si sta importando a Office 365. "
ms.openlocfilehash: 723a2e05a1f5d256e99bcf8497643435d0c98a23
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530211"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a><span data-ttu-id="e3825-105">Filtrare i dati per l'importazione di file PST a Office 365</span><span class="sxs-lookup"><span data-stu-id="e3825-105">Filter data when importing PST files to Office 365</span></span>

<span data-ttu-id="e3825-p102">Utilizzare la nuova funzionalità di importazione intelligente nel servizio di Office 365 importazione per filtrare gli elementi in file PST in realtà, l'importazione alle cassette postali di destinazione. Ecco come funziona:</span><span class="sxs-lookup"><span data-stu-id="e3825-p102">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes. Here's how it works:</span></span>
  
- <span data-ttu-id="e3825-108">Dopo aver creato e inviare un processo di importazione file PST, i file PST vengono caricati in un'area di archiviazione Azure nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e3825-108">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="e3825-109">Office 365 consente di analizzare i dati in file PST, in modo sicuro e protetto identificando della scadenza di elementi delle cassette postali e i diversi tipi di messaggi inclusi nei file PST.</span><span class="sxs-lookup"><span data-stu-id="e3825-109">Office 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="e3825-p103">Al termine dell'analisi ed sono possibile importare i dati, è possibile importare tutti i dati nei file PST o tagliare i dati importati impostando i filtri che consentono di controllare quali dati vengono importati. Ad esempio, è possibile scegliere di:</span><span class="sxs-lookup"><span data-stu-id="e3825-p103">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported. For example, you can choose to:</span></span>
    
  - <span data-ttu-id="e3825-112">Importare solo gli elementi di una certa data.</span><span class="sxs-lookup"><span data-stu-id="e3825-112">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="e3825-113">Importare i tipi di messaggio selezionato.</span><span class="sxs-lookup"><span data-stu-id="e3825-113">Import selected message types.</span></span>
    
  - <span data-ttu-id="e3825-114">Escludere i messaggi inviati o ricevuti da determinate persone.</span><span class="sxs-lookup"><span data-stu-id="e3825-114">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="e3825-115">Dopo aver configurato le impostazioni del filtro, Office 365 consente di importare solo i dati che soddisfano i criteri di filtro alle cassette postali di destinazione specificate nel processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="e3825-115">After you configure the filter settings, Office 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="e3825-116">Nella figura seguente viene illustrato il processo di importazione intelligente e vengono evidenziate le attività eseguite e le attività eseguite da Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3825-116">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Il processo di importazione intelligente in Office 365](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a><span data-ttu-id="e3825-118">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="e3825-118">Before you begin</span></span>

- <span data-ttu-id="e3825-p104">I passaggi descritti in questo argomento si presuppongono che sia stato creato un processo di importazione file PST nel servizio di Office 365 importazione utilizzando il caricamento di rete o della spedizione di unità. Per istruzioni dettagliate, vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3825-p104">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping. For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="e3825-121">Utilizzare il caricamento di rete per importare i file PST su Office 365</span><span class="sxs-lookup"><span data-stu-id="e3825-121">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="e3825-122">Utilizzare la spedizione dell'unità per importare file PST in Office 365</span><span class="sxs-lookup"><span data-stu-id="e3825-122">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="e3825-p105">Dopo aver creato un processo di importazione utilizzando il caricamento di rete, lo stato del processo di importazione per l'importazione di pagina in Office 365 Security &amp; centro conformità è impostata su **analisi in corso**, il che significa che Office 365 è analisi dei dati in file PST che si caricato. Fare clic su **Aggiorna**![aggiornamento](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) per aggiornare lo stato del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="e3825-p105">After you create an import job by using network upload, the status for the import job on the Import page in Office 365 Security &amp; Compliance Center is set to **Analysis in progress**, which means that Office 365 is analyzing the data in the PST files that you uploaded. Click **Refresh**![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="e3825-125">Per l'unità di distribuzione dei processi di importazione, i dati verranno analizzati da Office 365 dopo personale del centro dati Microsoft visualizzato nel disco rigido e caricare i file PST all'area di archiviazione Azure per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3825-125">For drive shipping import jobs, the data will be analyzed by Office 365 after Microsoft data center personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="e3825-126">Filtrare i dati importati per le cassette postali</span><span class="sxs-lookup"><span data-stu-id="e3825-126">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="e3825-127">Dopo aver creato un file PST processo di importazione, eseguire la procedura seguente per filtrare i dati prima di importare a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3825-127">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="e3825-128">Accedere a [https://protection.office.com/](https://protection.office.com/) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3825-128">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="e3825-129">Nel riquadro sinistro di Office 365 Security &amp; centro conformità, fare clic su **governance dati** \> **importazione**.</span><span class="sxs-lookup"><span data-stu-id="e3825-129">In the left pane of the Office 365 Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    <span data-ttu-id="e3825-p106">Nella pagina **importazione** sono elencati i processi di importazione per la propria organizzazione. Si noti che il valore **Analisi completata** nella colonna **stato** indica i processi di importazione che sono stati analizzati da Office 365 e si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="e3825-p106">The import jobs for your organization are listed on the **Import** page. Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Office 365 and are ready for you to import.</span></span> 
    
    ![Indica lo stato di completamento analisi che Office 365 dispone di analizzare i dati in file PST](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="e3825-133">Fare clic su **Pronto essere importato a Office 365** per il processo di importazione che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="e3825-133">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="e3825-134">Volo pagina viene visualizzato con informazioni sui file PST e altre informazioni sul processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="e3825-134">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="e3825-135">Fare clic su **Importa a Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e3825-135">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="e3825-p107">Verrà visualizzata la pagina di **filtrare i dati** . Contiene informazioni dati sui dati in file PST per il processo di importazione, incluse le informazioni sulla validità dei dati.</span><span class="sxs-lookup"><span data-stu-id="e3825-p107">The **Filter your data** page is displayed. It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![Il filtro per la pagina di dati Mostra sui concetti di dati dei file PST per il processo di importazione](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="e3825-139">Se si desidera tagliare i dati importati per Office 365, in base **si desidera filtrare i dati?**, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3825-139">Based on whether or not you want to trim the data that's imported to Office 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="e3825-p108">r. fare clic su **Sì, desidero filtrarla prima dell'importazione** per tagliare i dati da importare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e3825-p108">a. Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="e3825-142">Verrà visualizzata la pagina **Importa dati alla pagina di Office 365** con sui concetti di dati dettagliati dall'analisi eseguita Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3825-142">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Office 365 performed.</span></span> 
    
    ![Office 365 consente di visualizzare informazioni dettagliate dati dall'analisi dei file PST](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="e3825-p109">Il grafico in questa pagina Mostra la quantità di dati che verranno importati. Nel grafico vengono visualizzate informazioni su ogni tipo di messaggio disponibile in file PST. È possibile posizionare il cursore su ogni barra per visualizzare informazioni specifiche su tale tipo di messaggio. È inoltre disponibile un elenco a discesa con valori di durata diversi in base all'analisi dei file PST. Quando si seleziona un periodo nell'elenco a discesa, il grafico viene aggiornato per visualizzare la quantità di dati verranno importati per l'età selezionato.</span><span class="sxs-lookup"><span data-stu-id="e3825-p109">The graph on this page shows the amount of data that will be imported. Information about each message type found in the PST files is displayed in the graph. You can hover the cursor over each bar to display specific information about that message type. There is also a drop-down list with different age values based on the analysis of the PST files. When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="e3825-p110">b. per configurare i filtri di aggiunta per ridurre la quantità di dati importati, fare clic su **ulteriori opzioni di filtro**.</span><span class="sxs-lookup"><span data-stu-id="e3825-p110">b. To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![Configurare i filtri nella pagina ulteriori opzioni per ridurre i dati importati](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="e3825-152">È possibile configurare questi filtri:</span><span class="sxs-lookup"><span data-stu-id="e3825-152">You can configure these filters:</span></span>
    
      - <span data-ttu-id="e3825-p111">**Validità** - selezionare un'età in modo che solo gli elementi che sono più recente di validità specificata verrà importata. Vedere la sezione [informazioni](filter-data-when-importing-pst-files.md#moreinfo) per una descrizione su come Office 365 determina i bucket di validità per il filtro di **validità** .</span><span class="sxs-lookup"><span data-stu-id="e3825-p111">**Age** - Select an age so only items that are newer than the specified age will be imported. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a description about how Office 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="e3825-p112">**Tipo** : in questa sezione vengono illustrati tutti i tipi di messaggio che sono stati rilevati nei file PST per il processo di importazione. È possibile deselezionare una casella accanto a un tipo di messaggio che si desidera escludere. Si noti che non è possibile escludere il tipo di messaggio. Vedere la sezione [informazioni](filter-data-when-importing-pst-files.md#moreinfo) per un elenco di elementi delle cassette postali inclusi nella categoria.</span><span class="sxs-lookup"><span data-stu-id="e3825-p112">**Type** - This section shows all the message types that were found in the PST files for the import job. You can uncheck a box next to a message type that you want to exclude. Note that you can't exclude the Other message type. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="e3825-p113">**Gli utenti** , è possibile escludere messaggi inviati o ricevuti da determinate persone. Escludere gli utenti che vengono visualizzati nella From: campo a: campo o Cc: campo dei messaggi, fare clic su **Escludi utenti** accanto a tale tipo di destinatario. Digitare l'indirizzo di posta elettronica (indirizzo SMTP) della persona, fare clic su **Aggiungi**![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) per aggiungerli all'elenco di utenti esclusi per quel tipo di destinatario e quindi fare clic su **Salva** per salvare l'elenco di utenti esclusi.</span><span class="sxs-lookup"><span data-stu-id="e3825-p113">**Users** - You can exclude messages that are sent or received by specific people. To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type. Type the email address (SMTP address) of the person, click **Add**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="e3825-p114">Office 365 non viene visualizzata sui concetti di dati restituiti dall'impostazione del filtro di **persone** . Tuttavia, se si imposta questo filtro per escludere i messaggi inviati o ricevuti da determinate persone, i messaggi vengono esclusi durante il processo di importazione effettivo.</span><span class="sxs-lookup"><span data-stu-id="e3825-p114">Office 365 doesn't show data insights that result from setting the **People** filter. However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="e3825-p115">c. fare clic su **Applica** in tempo reale **le opzioni di filtro più** pagina per salvare le impostazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="e3825-p115">c. Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="e3825-p116">I dati sui concetti nella pagina **Importa dati a Office 365** vengono aggiornati in base alle impostazioni di filtro, tra cui la quantità totale di dati che verranno importati in base alle impostazioni del filtro. Si noti che anche è riportato un riepilogo delle impostazioni del filtro. È possibile fare clic su **Edit** accanto a un filtro per modificare l'impostazione se necessario.</span><span class="sxs-lookup"><span data-stu-id="e3825-p116">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings. Note that a summary of the filter settings is also shown. You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![Approfondimenti dati vengono aggiornati in base alle impostazioni di filtro](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="e3825-p117">d. scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e3825-p117">d. Click **Next**.</span></span>
    
    <span data-ttu-id="e3825-p118">Viene visualizzata una pagina di stato che mostra le impostazioni di filtro. Nuovamente, è possibile modificare le impostazioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="e3825-p118">A status page is displayed showing your filter settings. Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="e3825-p119">Fare clic su **Importa dati** per avviare l'importazione. Si noti che viene visualizzata la quantità totale di dati che verranno importati.</span><span class="sxs-lookup"><span data-stu-id="e3825-p119">e. Click **Import data** to start the import . Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="e3825-177">Oppure</span><span class="sxs-lookup"><span data-stu-id="e3825-177">Or</span></span>
    
    <span data-ttu-id="e3825-p120">r. fare clic su **No, desidera importare tutti gli elementi** per importare tutti i dati in file PST di Office 365 e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e3825-p120">a. Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="e3825-p121">b. nella pagina **Importa dati a Office 365** , fare clic su **Importa dati** per avviare l'importazione. Si noti che viene visualizzata la quantità totale di dati che verranno importati.</span><span class="sxs-lookup"><span data-stu-id="e3825-p121">b. On the **Import data to Office 365** page, click **Import data** to start the import. Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="e3825-p122">Nella pagina **importazione** fare clic su **Aggiorna** ![aggiornamento](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). Nella colonna **stato** viene visualizzato lo stato del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="e3825-p122">On the **Import** page, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="e3825-185">Fare clic su Importa il processo per visualizzare informazioni più dettagliate, ad esempio lo stato di ogni file PST e le impostazioni del filtro che è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="e3825-185">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="e3825-186">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e3825-186">More information</span></span>

- <span data-ttu-id="e3825-p123">In che modo Office 365 determinare gli incrementi di filtro per la validità? Quando Office 365 consente di analizzare un file PST, esamina il timestamp inviato o ricevuto di ogni elemento (se un elemento contiene un timestamp inviato e ricevuto, la data meno recente è selezionata). Office 365 quindi cerca il valore dell'anno per tale data/ora e viene confrontata con la data corrente per determinare la validità dell'elemento. Questi età vengono quindi utilizzate come valori nell'elenco a discesa per il filtro di **validità** . Ad esempio, se un file PST con i messaggi provenienti da 2016, 2015 e 2014, quindi i valori di filtro **intervallo** sarà **anno 1**, **2 anni**e **3 anni**.</span><span class="sxs-lookup"><span data-stu-id="e3825-p123">How does Office 365 determine the increments for the age filter? When Office 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected). Then Office 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item. These ages are then used as the values in the drop-down list for the **Age** filter. For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="e3825-p124">Nella tabella seguente sono elencati i tipi di messaggi inclusi nella **categoria il filtro di **tipo** in tempo reale **altre opzioni** pagina** (vedere 5b passaggio nella procedura precedente). Attualmente, non è possibile escludere gli elementi nella categoria "" quando si importano i file pst a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3825-p124">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure). Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="e3825-194">**ID classe messaggio**</span><span class="sxs-lookup"><span data-stu-id="e3825-194">**Message class ID**</span></span>|<span data-ttu-id="e3825-195">**Elementi delle cassette postali che utilizzano questa classe messaggio**</span><span class="sxs-lookup"><span data-stu-id="e3825-195">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e3825-196">IPM. Attività</span><span class="sxs-lookup"><span data-stu-id="e3825-196">IPM.Activity</span></span>  <br/> |<span data-ttu-id="e3825-197">Voci del diario</span><span class="sxs-lookup"><span data-stu-id="e3825-197">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="e3825-198">IPM. Documento</span><span class="sxs-lookup"><span data-stu-id="e3825-198">IPM.Document</span></span>  <br/> |<span data-ttu-id="e3825-199">Documenti e i file (non è associati a un messaggio di posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="e3825-199">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="e3825-200">IPM. File</span><span class="sxs-lookup"><span data-stu-id="e3825-200">IPM.File</span></span>  <br/> |<span data-ttu-id="e3825-201">(stesso IPM. Documento)</span><span class="sxs-lookup"><span data-stu-id="e3825-201">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="e3825-202">IPM. Note.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="e3825-202">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="e3825-203">Report tramite Internet Mail Connect è il gateway Internet del Server di Exchange</span><span class="sxs-lookup"><span data-stu-id="e3825-203">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="e3825-204">IPM. Note.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="e3825-204">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="e3825-205">Messaggi fax</span><span class="sxs-lookup"><span data-stu-id="e3825-205">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="e3825-206">IPM. Note.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="e3825-206">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="e3825-207">Messaggi di risposta automatica fuori sede</span><span class="sxs-lookup"><span data-stu-id="e3825-207">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="e3825-208">IPM. Note.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="e3825-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="e3825-209">Risposte inviate da una regola di posta in arrivo</span><span class="sxs-lookup"><span data-stu-id="e3825-209">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="e3825-210">IPM. OLE. Classe</span><span class="sxs-lookup"><span data-stu-id="e3825-210">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="e3825-211">Eccezioni per una serie ricorrente</span><span class="sxs-lookup"><span data-stu-id="e3825-211">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="e3825-212">IPM. Recall.Report</span><span class="sxs-lookup"><span data-stu-id="e3825-212">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="e3825-213">Rapporti richiamo messaggio</span><span class="sxs-lookup"><span data-stu-id="e3825-213">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="e3825-214">IPM. Remoto</span><span class="sxs-lookup"><span data-stu-id="e3825-214">IPM.Remote</span></span>  <br/> |<span data-ttu-id="e3825-215">Messaggi di posta remota</span><span class="sxs-lookup"><span data-stu-id="e3825-215">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="e3825-216">IPM. Report</span><span class="sxs-lookup"><span data-stu-id="e3825-216">IPM.Report</span></span>  <br/> |<span data-ttu-id="e3825-217">Relazioni sullo stato elemento</span><span class="sxs-lookup"><span data-stu-id="e3825-217">Item status reports</span></span>  <br/> |
