---
title: Eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Informazioni su come utilizzare la protezione di Office 365 &amp; centro conformità per accedere a Office 365 avanzate eDiscovery ed eseguire il modulo di processo per un caso.  '
ms.openlocfilehash: 32052bccc37d20c8707a1efb0592f7c93daf3590
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530811"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="48f21-103">Eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="48f21-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="48f21-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="48f21-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="48f21-106">In questa sezione viene descritta la funzionalità del modulo del processo eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="48f21-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="48f21-p102">Oltre ai dati dei file, metadati, ad esempio tipo di file, estensione, posizione o percorso, la data di creazione e ora, autore, depositaria e argomento, è possibile caricare in avanzate eDiscovery e salvata per ciascun caso. Alcuni metadati viene calcolato dal eDiscovery avanzate, ad esempio, quando vengono caricati file nativi.</span><span class="sxs-lookup"><span data-stu-id="48f21-p102">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case. Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="48f21-p103">EDiscovery avanzate fornisce sistema i valori dei metadati, ad esempio raggruppamenti quasi duplicati o punteggio di pertinenza. È possibile aggiungere altri metadati, ad esempio le annotazioni di file, l'amministratore.</span><span class="sxs-lookup"><span data-stu-id="48f21-p103">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores. Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="48f21-111">Processo in esecuzione</span><span class="sxs-lookup"><span data-stu-id="48f21-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="48f21-p104">I numeri batch sono assegnati a un file nel corso per consentire la registrazione dei file. Il numero di batch consente inoltre l'identificazione dei processi batch per le opzioni di rielaborazione. Filtri aggiuntivi sono disponibili per il filtro per le sessioni e il numero di batch.</span><span class="sxs-lookup"><span data-stu-id="48f21-p104">Batch numbers are assigned to a file during Process to allow the tracking of files. The batch number also enables identification of Process batches for reprocessing options. Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="48f21-115">Eseguire la procedura seguente per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="48f21-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="48f21-116">[Aprire la protezione di Office 365 &amp; centro conformità](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="48f21-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="48f21-117">Accedere a **ricerca &amp; indagini** \> **eDiscovery** e quindi fare clic su **Vai a eDiscovery avanzate**.</span><span class="sxs-lookup"><span data-stu-id="48f21-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="48f21-118">In eDiscovery avanzate, selezionare il caso appropriato nella pagina visualizzata **casi** e fare clic su **Vai a caso**.</span><span class="sxs-lookup"><span data-stu-id="48f21-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="48f21-119">In **Prepara** \> **processo** \> **il programma di installazione**, selezionare un contenitore dall'elenco dei contenitori disponibili.</span><span class="sxs-lookup"><span data-stu-id="48f21-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![Fare clic su processo per aggiungere i risultati di ricerca al caso](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="48f21-121">Se si desidera aggiungere il contenitore come file di seeding o file pre-contrassegnati, fare clic su **Impostazioni avanzate** .</span><span class="sxs-lookup"><span data-stu-id="48f21-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="48f21-p105">Seeding i file utilizzati per velocizzare la formazione per i problemi con complessità bassa (in genere 2%, massimo). Per i file di seeding, è consigliabile selezionare l'unità relativi file ed elaborare su 20-50 semi per ogni problema (Troppi file seeding possono variare i risultati di pertinenza). Dalla stessa persona verrà formare il problema, è consigliabile leggere i file di seeding.</span><span class="sxs-lookup"><span data-stu-id="48f21-p105">Use seed files to accelerate training for issues with low richness (usually 2%, or less). For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results). Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="48f21-p106">Utilizzare i file di pre-contrassegnati per automatizzare la formazione di pertinenza. Contrassegnare i file di almeno 1.500 e mantenere la proporzione di interesse per i file non rilevanti corrispondono a quelli insieme aggiunti alla pertinenza. Questi file devono essere contrassegnati manualmente, e devono essere certi della qualità del contrassegno.</span><span class="sxs-lookup"><span data-stu-id="48f21-p106">Use pre-tagged files to automate Relevance training. You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance. These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![Cattura di schermata di avanzate della pagina Impostazioni per l'elaborazione in batch i file](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="48f21-129">Nella sezione **seeding** :</span><span class="sxs-lookup"><span data-stu-id="48f21-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="48f21-p107">Scegliere **Contrassegna come file di seeding** per contrassegnare il contenitore come file di seeding. È inoltre necessario scegliere assegnarli al problema da **per problema di** elenco a discesa. Scegliere **relativo** o **non rilevanti** dall'elenco a discesa **Tag** .</span><span class="sxs-lookup"><span data-stu-id="48f21-p107">Choose **Mark as seed files** to mark the container as seed files. You also need choose to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="48f21-133">Dopo aver impostato i file come **seeding**, è possibile contrassegnare come **pre-contrassegnati**.</span><span class="sxs-lookup"><span data-stu-id="48f21-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="48f21-134">Nella sezione **file pre-tag** :</span><span class="sxs-lookup"><span data-stu-id="48f21-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="48f21-p108">Scegliere **Contrassegna come file pre-contrassegnati** per contrassegnare il contenitore come file pre-contrassegnati. È inoltre necessario assegnarli al problema da **per problema di** elenco a discesa. Scegliere **relativo** o **non rilevanti** dall'elenco a discesa **Tag** .</span><span class="sxs-lookup"><span data-stu-id="48f21-p108">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files. You also need to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="48f21-138">Dopo aver impostato i file come **pre-contrassegnati**, è possibile contrassegnare come **seeding**.</span><span class="sxs-lookup"><span data-stu-id="48f21-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="48f21-p109">Nella sezione **posta elettronica tagging** . insieme quale parte di un messaggio di posta elettronica elaborato devono essere contrassegnati come router di inizializzazione o pre-contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="48f21-p109">In the **Email tagging** section. set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="48f21-p110">Per iniziare, fare clic su **processo**. Al termine, vengono visualizzati i risultati di processo.</span><span class="sxs-lookup"><span data-stu-id="48f21-p110">To begin, click **Process**. When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="48f21-143">(Facoltativo) Se si desidera assegnare le origini dati a un depositaria specifico, è possibile aggiungere e modificare i nomi depositaria in **depositari** \> **Gestisci** e assegna depositari in **depositari** \> **assegnare**.</span><span class="sxs-lookup"><span data-stu-id="48f21-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="48f21-144">Se si aggiunge il caso, quindi è possibile elaborare nuovamente.</span><span class="sxs-lookup"><span data-stu-id="48f21-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="48f21-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48f21-145">See also</span></span>

[<span data-ttu-id="48f21-146">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="48f21-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="48f21-147">Visualizzazione dei risultati modulo processo</span><span class="sxs-lookup"><span data-stu-id="48f21-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

