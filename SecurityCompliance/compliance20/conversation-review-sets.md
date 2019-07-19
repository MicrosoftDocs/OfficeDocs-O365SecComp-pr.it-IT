---
title: Esaminare le conversazioni in Advanced eDiscovery
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
ms.openlocfilehash: f88bdcfc4ac7ed31ec44a7d18bd74cc2a1842bc5
ms.sourcegitcommit: 2560a3ecc6a5e3b8b79bbf56a157b66c7553682e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35795582"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="20f5e-102">Esaminare le conversazioni in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="20f5e-102">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="20f5e-103">La messaggistica istantanea rappresenta un modo pratico per fare domande, condividere idee o comunicare rapidamente tra gruppi di destinatari di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="20f5e-103">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="20f5e-104">Poiché le piattaforme di messaggistica istantanea, come Microsoft teams, diventano fondamentali per la collaborazione aziendale, le organizzazioni devono valutare in che modo il flusso di lavoro di eDiscovery affronta queste nuove forme di comunicazione e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-104">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="20f5e-105">La funzionalità di ricostruzione della conversazione in Advanced eDiscovery è progettata per identificare il contenuto contestuale e produrre visualizzazioni di conversazione distinte.</span><span class="sxs-lookup"><span data-stu-id="20f5e-105">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="20f5e-106">Questa funzionalità consente di esaminare in modo efficiente e rapido le conversazioni complete dei messaggi istantanei (denominate anche *conversazioni filettate*) generate in piattaforme come Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="20f5e-106">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="20f5e-107">Con la ricostruzione della conversazione, è possibile utilizzare le funzionalità predefinite per ricostruire, rivedere ed esportare conversazioni filettate.</span><span class="sxs-lookup"><span data-stu-id="20f5e-107">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="20f5e-108">Utilizzare la ricostruzione avanzata della conversazione di eDiscovery per:</span><span class="sxs-lookup"><span data-stu-id="20f5e-108">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="20f5e-109">Preservare i metadati a livello di messaggio univoci in tutti i messaggi all'interno di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-109">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="20f5e-110">Raccogliere messaggi contestuali attorno ai risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="20f5e-110">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="20f5e-111">Esaminare, annotare e redigere conversazioni filettate.</span><span class="sxs-lookup"><span data-stu-id="20f5e-111">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="20f5e-112">Esportare singoli messaggi o conversazioni filettate</span><span class="sxs-lookup"><span data-stu-id="20f5e-112">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="20f5e-113">Terminologia</span><span class="sxs-lookup"><span data-stu-id="20f5e-113">Terminology</span></span>

<span data-ttu-id="20f5e-114">Di seguito sono riportate alcune definizioni che consentono di iniziare a utilizzare la ricostruzione delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="20f5e-114">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="20f5e-115">**Messaggi:** Rappresentano la più piccola unità di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-115">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="20f5e-116">I messaggi possono variare in base alle dimensioni, alla struttura e ai metadati.</span><span class="sxs-lookup"><span data-stu-id="20f5e-116">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="20f5e-117">**Conversazione:** Rappresenta un raggruppamento di uno o più messaggi.</span><span class="sxs-lookup"><span data-stu-id="20f5e-117">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="20f5e-118">Tra diverse applicazioni, le conversazioni possono essere rappresentate in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="20f5e-118">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="20f5e-119">In alcune applicazioni è presente un'azione esplicita che risulta dalla risposta a un messaggio esistente.</span><span class="sxs-lookup"><span data-stu-id="20f5e-119">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="20f5e-120">Le conversazioni sono formate in modo esplicito a causa di questa azione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="20f5e-120">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="20f5e-121">Ad esempio, ecco uno screenshot di una conversazione di canale in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="20f5e-121">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Conversazione canale Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="20f5e-123">In altre app (ad esempio i messaggi di chat di 1xN in teams), non esiste una catena di risposta formale e i messaggi vengono visualizzati come un "fiume di messaggi Flat" all'interno di un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="20f5e-123">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="20f5e-124">Nelle app di questo tipo, le conversazioni vengono desunte da un gruppo di messaggi che si verificano entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="20f5e-124">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="20f5e-125">Questo "soft-grouping" dei messaggi (invece di una catena di risposta) rappresenta la conversazione "avanti e indietro" su un argomento specifico di interesse.</span><span class="sxs-lookup"><span data-stu-id="20f5e-125">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="20f5e-126">Passaggio 1: eseguire una ricerca</span><span class="sxs-lookup"><span data-stu-id="20f5e-126">Step 1: Run a search</span></span>

<span data-ttu-id="20f5e-127">Dopo aver identificato i depositari e i percorsi di contenuto rilevanti, è possibile creare una ricerca per trovare contenuti potenzialmente rilevanti.</span><span class="sxs-lookup"><span data-stu-id="20f5e-127">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="20f5e-128">Nella scheda **ricerche** del caso Advanced eDiscovery, è possibile creare una ricerca facendo clic su **nuova ricerca** e seguendo la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="20f5e-128">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="20f5e-129">Per informazioni sulla creazione di una ricerca, la creazione di una query di ricerca e la visualizzazione dei risultati della ricerca, vedere [Collect Data for a case](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="20f5e-129">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="20f5e-130">Passaggio 2: creare un set di revisione della conversazione</span><span class="sxs-lookup"><span data-stu-id="20f5e-130">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="20f5e-131">In un set di revisione è possibile eseguire ricerche, tag, annotazioni e documenti di redigere, messaggi di posta elettronica e conversazioni chat.</span><span class="sxs-lookup"><span data-stu-id="20f5e-131">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="20f5e-132">In Advanced eDiscovery, è possibile personalizzare la revisione delle conversazioni, in base ai singoli messaggi o alle conversazioni filettate.</span><span class="sxs-lookup"><span data-stu-id="20f5e-132">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="20f5e-133">Questo è determinato dal tipo di revisione impostato in cui si aggiungono i risultati della ricerca creata al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="20f5e-133">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="20f5e-134">Sono disponibili due diversi tipi di set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="20f5e-134">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="20f5e-135">**Set di revisione standard:** I messaggi nelle conversazioni vengono elaborati e visualizzati come singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="20f5e-135">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="20f5e-136">**Set di revisione della conversazione:** I messaggi nelle conversazioni vengono elaborati singolarmente ma visualizzati in una visualizzazione conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-136">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="20f5e-137">In un set di revisione della conversazione, è possibile annotare, contrassegnare e redigere i messaggi in una visualizzazione di conversazione filettata.</span><span class="sxs-lookup"><span data-stu-id="20f5e-137">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="20f5e-138">Per ulteriori informazioni su come esaminare e gestire il contenuto in un set di recensioni, vedere [Manage Review sets](managing-review-sets.md).</span><span class="sxs-lookup"><span data-stu-id="20f5e-138">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="20f5e-139">Passaggio 3: abilitare le opzioni di recupero delle conversazioni</span><span class="sxs-lookup"><span data-stu-id="20f5e-139">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="20f5e-140">Dopo aver esaminato e completato la query di ricerca, è possibile aggiungere i risultati della ricerca a un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-140">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="20f5e-141">Quando si aggiungono i risultati della ricerca in un set di revisione, i dati originali vengono copiati in un'area di archiviazione di Azure per semplificare il processo di revisione e analisi.</span><span class="sxs-lookup"><span data-stu-id="20f5e-141">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="20f5e-142">Per ulteriori informazioni sull'aggiunta dei risultati di ricerca a un set di revisione, vedere [Add Search results to a Review set](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="20f5e-142">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="20f5e-143">Quando si aggiungono dati dalle conversazioni a un set di revisione, è possibile utilizzare le opzioni di recupero delle conversazioni per espandere la ricerca e includere i messaggi contestuali.</span><span class="sxs-lookup"><span data-stu-id="20f5e-143">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="20f5e-144">Dopo aver impostato le opzioni di recupero delle conversazioni, è possibile che si verifichino le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="20f5e-144">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Recupero delle conversazioni](../media/messagesandconversations.png)
  
1. <span data-ttu-id="20f5e-146">Utilizzando una query di parole chiave e intervallo di date, la ricerca ha restituito un hit sul *messaggio 3*.</span><span class="sxs-lookup"><span data-stu-id="20f5e-146">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="20f5e-147">Questo messaggio è stato parte di una conversazione più grande, illustrata da *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="20f5e-147">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="20f5e-148">Quando si aggiungono i dati in un set di revisione e si abilitano le opzioni di recupero delle conversazioni, Advanced eDiscovery torna indietro e raccoglie altri elementi in *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="20f5e-148">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="20f5e-149">Dopo aver aggiunto gli elementi al set di revisione, è possibile esaminare tutti i singoli messaggi da *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="20f5e-149">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 



<span data-ttu-id="20f5e-150">Per abilitare il recupero delle conversazioni:</span><span class="sxs-lookup"><span data-stu-id="20f5e-150">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="20f5e-151">Nella scheda **ricerche** del caso Advanced eDiscovery, selezionare una ricerca, quindi fare clic su **Aggiungi al set di revisione** nella pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="20f5e-151">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="20f5e-152">Selezionare un set di revisione esistente o creare un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-152">Select an existing review set or create a review set.</span></span> <span data-ttu-id="20f5e-153">È possibile configurare le opzioni di recupero quando si aggiungono i risultati di ricerca a un set di revisione standard o di conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-153">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="20f5e-154">In **Opzioni di raccolta**configurare le opzioni di recupero delle conversazioni per le origini di contenuto che si desidera espandere nella ricerca, quindi fare clic su **Aggiungi** per avviare il processo.</span><span class="sxs-lookup"><span data-stu-id="20f5e-154">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="20f5e-155">Dopo aver completato il processo **di installazione del set di revisione** nella scheda **processi** , è possibile iniziare a rivedere le conversazioni.</span><span class="sxs-lookup"><span data-stu-id="20f5e-155">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-conversations-in-the-review-set"></a><span data-ttu-id="20f5e-156">Passaggio 4: esaminare le conversazioni nel set di Revisione</span><span class="sxs-lookup"><span data-stu-id="20f5e-156">Step 4: Review conversations in the review set</span></span>

<span data-ttu-id="20f5e-157">Dopo che il contenuto è stato elaborato e aggiunto al set di revisione, è possibile iniziare a visualizzare i dati nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-157">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="20f5e-158">Le funzionalità di revisione sono diverse a seconda che il contenuto sia stato aggiunto a un set di revisione standard o a un set di recensioni di conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-158">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="20f5e-159">Revisione delle conversazioni in un set di riesame standard</span><span class="sxs-lookup"><span data-stu-id="20f5e-159">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="20f5e-160">In un set di revisione standard, i messaggi vengono elaborati e visualizzati come singoli elementi, analogamente a come vengono archiviati in una cartella delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="20f5e-160">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="20f5e-161">In questo flusso di lavoro, ogni messaggio viene elaborato come elemento separato.</span><span class="sxs-lookup"><span data-stu-id="20f5e-161">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="20f5e-162">Di conseguenza, le opzioni di riepilogo e esportazione filettate non sono disponibili in un set di analisi standard.</span><span class="sxs-lookup"><span data-stu-id="20f5e-162">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Set di revisione standard](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="20f5e-164">Revisione delle conversazioni in un set di recensioni di conversazione</span><span class="sxs-lookup"><span data-stu-id="20f5e-164">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="20f5e-165">In un set di revisione della conversazione, i singoli messaggi vengono configurati insieme e presentati come conversazioni.</span><span class="sxs-lookup"><span data-stu-id="20f5e-165">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="20f5e-166">In questo modo è possibile esaminare ed esportare conversazioni contestuali.</span><span class="sxs-lookup"><span data-stu-id="20f5e-166">This lets you review and export contextual conversations.</span></span> 

  ![Set di revisione della conversazione](../media/ConversationRSOptions.PNG)

<span data-ttu-id="20f5e-168">Nelle sezioni seguenti viene descritta la revisione e l'esportazione delle conversazioni in un set di recensioni di conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-168">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="20f5e-169">Revisione delle conversazioni</span><span class="sxs-lookup"><span data-stu-id="20f5e-169">Reviewing conversations</span></span>

<span data-ttu-id="20f5e-170">In un set di recensioni di conversazione è possibile utilizzare le opzioni seguenti per semplificare il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-170">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="20f5e-171">**Raggruppamento per conversazione:** Raggruppa i messaggi all'interno della stessa conversazione per consentire agli utenti di semplificare e velocizzare il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-171">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="20f5e-172">**Visualizzazione Riepilogo:** Visualizza la conversazione filettata.</span><span class="sxs-lookup"><span data-stu-id="20f5e-172">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="20f5e-173">In questa visualizzazione, è possibile visualizzare l'intera conversazione e accedere anche ai metadati per ogni singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="20f5e-173">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="20f5e-174">Visualizzare i metadati per i singoli messaggi</span><span class="sxs-lookup"><span data-stu-id="20f5e-174">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="20f5e-175">Scaricare singoli messaggi</span><span class="sxs-lookup"><span data-stu-id="20f5e-175">Download individual messages</span></span>

- <span data-ttu-id="20f5e-176">**Visualizzazione testo:** Fornisce il testo estratto per l'intera conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-176">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="20f5e-177">**Visualizzazione annotazioni:** Consente di markup di una visualizzazione con thread della conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-177">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="20f5e-178">Tutti i messaggi della conversazione condividono lo stesso documento con annotazioni.</span><span class="sxs-lookup"><span data-stu-id="20f5e-178">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="20f5e-179">**Tagging:** Quando si visualizzano le conversazioni in un set di revisione, è possibile visualizzare e applicare i tag facendo clic su **tagging** nel pannello di codifica.</span><span class="sxs-lookup"><span data-stu-id="20f5e-179">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="20f5e-180">**Rieseguire la conversione della conversazione:** Quando i messaggi vengono aggiunti a un set di revisione della conversazione, viene eseguito automaticamente un processo di conversione per creare il riepilogo filettato e le visualizzazioni annotazioni.</span><span class="sxs-lookup"><span data-stu-id="20f5e-180">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="20f5e-181">Se il processo di ricostruzione della conversazione ha esito negativo, è possibile rieseguire questo processo facendo clic su **azione > creare file PDF di conversazione** nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-181">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>


#### <a name="exporting-conversations"></a><span data-ttu-id="20f5e-182">Esportazione di conversazioni</span><span class="sxs-lookup"><span data-stu-id="20f5e-182">Exporting conversations</span></span>

<span data-ttu-id="20f5e-183">In un set di recensioni di conversazione è possibile impostare le opzioni seguenti per esportare le conversazioni:</span><span class="sxs-lookup"><span data-stu-id="20f5e-183">In a conversation review set, you can set the following options to export conversations:</span></span>

![Esportazione](../media/export.png)

<span data-ttu-id="20f5e-185">un.</span><span class="sxs-lookup"><span data-stu-id="20f5e-185">a.</span></span> <span data-ttu-id="20f5e-186">Opzioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="20f5e-186">Metadata options</span></span>

   - <span data-ttu-id="20f5e-187">**Carica file:** I metadati sono inclusi per ogni singolo messaggio, indirizzo di posta elettronica e documento.</span><span class="sxs-lookup"><span data-stu-id="20f5e-187">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="20f5e-188">In una conversazione è presente una riga per ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="20f5e-188">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="20f5e-189">**Tag:** I tag del processo di revisione sono inclusi nel file di metadati.</span><span class="sxs-lookup"><span data-stu-id="20f5e-189">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="20f5e-190">I messaggi in una conversazione condividono gli stessi tag.</span><span class="sxs-lookup"><span data-stu-id="20f5e-190">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="20f5e-191">b.</span><span class="sxs-lookup"><span data-stu-id="20f5e-191">b.</span></span> <span data-ttu-id="20f5e-192">Opzioni di conversazione</span><span class="sxs-lookup"><span data-stu-id="20f5e-192">Conversation options</span></span>
  
   - <span data-ttu-id="20f5e-193">**File di conversazione:** Quando si esportano file di conversazione, la visualizzazione con annotazioni viene convertita in un file PDF e scaricata nella cartella Export.</span><span class="sxs-lookup"><span data-stu-id="20f5e-193">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="20f5e-194">I messaggi in un file di conversazione puntano alla versione PDF dello stesso file di conversazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-194">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="20f5e-195">**Messaggi di chat individuali:** Quando si esportano singoli messaggi, ciascun messaggio univoco nella conversazione viene esportato come elemento autonomo.</span><span class="sxs-lookup"><span data-stu-id="20f5e-195">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="20f5e-196">Il file viene esportato nello stesso formato in cui è stato salvato come nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="20f5e-196">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="20f5e-197">Per una conversazione specifica, si ricevono più file. msg.</span><span class="sxs-lookup"><span data-stu-id="20f5e-197">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="20f5e-198">Se le annotazioni sono state applicate al file di conversazione, queste annotazioni non verranno trasferite ai singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="20f5e-198">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="20f5e-199">c.</span><span class="sxs-lookup"><span data-stu-id="20f5e-199">c.</span></span> <span data-ttu-id="20f5e-200">Altre opzioni</span><span class="sxs-lookup"><span data-stu-id="20f5e-200">Other options</span></span>

   - <span data-ttu-id="20f5e-201">**Generare file di testo per tutto il contenuto esportato:** Genera un file di testo per ogni conversazione esportata dal set di revisione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-201">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="20f5e-202">**Sostituire il contenuto esportato con file PDF redatti:** Se durante il processo di revisione vengono generati file di conversazione redatti, questi file sono disponibili durante l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="20f5e-202">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="20f5e-203">È possibile decidere se esportare solo i file nativi (non selezionando questa opzione) o sostituire i file nativi con le versioni redatte dei file nativi (selezionando questa opzione), che vengono esportati come file PDF.</span><span class="sxs-lookup"><span data-stu-id="20f5e-203">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="20f5e-204">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="20f5e-204">More information</span></span>

<span data-ttu-id="20f5e-205">Per ulteriori informazioni su come esaminare i dati dei casi in Advanced eDiscovery, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="20f5e-205">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="20f5e-206">Visualizzare i dati dei casi</span><span class="sxs-lookup"><span data-stu-id="20f5e-206">View case data</span></span>](view-documents-in-review-set.md) 

- [<span data-ttu-id="20f5e-207">Analizzare i dati del caso</span><span class="sxs-lookup"><span data-stu-id="20f5e-207">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="20f5e-208">Esportare i dati del caso</span><span class="sxs-lookup"><span data-stu-id="20f5e-208">Export case data</span></span>](exporting-data-ediscover20.md)
