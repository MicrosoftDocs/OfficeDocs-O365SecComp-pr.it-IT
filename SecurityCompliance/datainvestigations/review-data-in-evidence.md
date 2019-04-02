---
title: Esaminare i dati in evidenza
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 279d2117a69e889f9e605e0ab211c03c5842a59d
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030224"
---
# <a name="review-data-in-evidence"></a><span data-ttu-id="b25ef-102">Esaminare i dati in evidenza</span><span class="sxs-lookup"><span data-stu-id="b25ef-102">Review data in evidence</span></span>

<span data-ttu-id="b25ef-103">**Evidence** è uno snapshot dei risultati della ricerca raccolti.</span><span class="sxs-lookup"><span data-stu-id="b25ef-103">**Evidence** is a snapshot of search results that you collected.</span></span> <span data-ttu-id="b25ef-104">Quando si aggiungono i risultati della ricerca all'evidenza, viene attivato un processo per estrarre file, metadati e testo.</span><span class="sxs-lookup"><span data-stu-id="b25ef-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text.</span></span> <span data-ttu-id="b25ef-105">Successivamente, il sistema genera un nuovo indice di tutti i dati e aggiunge l' **elemento Evidence**.</span><span class="sxs-lookup"><span data-stu-id="b25ef-105">Then, the system builds a new index of all the data and adds to **Evidence**.</span></span> 

<span data-ttu-id="b25ef-106">Per eventuali incidenti sensibili al tempo, in questo modo è possibile contenere rapidamente l'ambiente eliminando i dati nei percorsi originali durante l'analisi delle evidenze ricreate in un ambiente in quarantena.</span><span class="sxs-lookup"><span data-stu-id="b25ef-106">For any time-sensitive incidents, this allows you to quickly contain the environment by deleting data at original locations while investigating re-created evidence in a quarantined environment.</span></span> <span data-ttu-id="b25ef-107">Una volta raccolti i dati, è possibile esaminare singoli documenti nel formato nativo, nel formato di testo o in un formato quasi nativo.</span><span class="sxs-lookup"><span data-stu-id="b25ef-107">Once evidence is collected, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="b25ef-108">Inoltre, è possibile eseguire query per limitare i dati in base a intervallo di tempo, tipi di file, proprietari di dati e molte altre schede di condizione.</span><span class="sxs-lookup"><span data-stu-id="b25ef-108">Additionally, you can run queries to narrow the data by time range, file types, data owners, and many other condition cards.</span></span> <span data-ttu-id="b25ef-109">Utilizzando le schede delle condizioni autore/mittente/destinatario, è possibile esaminare rapidamente gli utenti coinvolti nella fuoriuscita e se sono presenti parti esterne.</span><span class="sxs-lookup"><span data-stu-id="b25ef-109">Using Author/Sender/Recipient condition cards, you can quickly examine who are involved in the spill and if there have been any external shares.</span></span> <span data-ttu-id="b25ef-110">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="b25ef-110">For more information, see:</span></span>

  - [<span data-ttu-id="b25ef-111">Eseguire una query sui dati in evidenza</span><span class="sxs-lookup"><span data-stu-id="b25ef-111">Query the data in evidence</span></span>](evidence-query.md)

<span data-ttu-id="b25ef-112">Per raggruppare i documenti e ottenere assistenza per la revisione, fare clic su **Gestisci evidenza**.</span><span class="sxs-lookup"><span data-stu-id="b25ef-112">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="b25ef-113">Nel riquadro **analisi** fare clic su **analizza**.</span><span class="sxs-lookup"><span data-stu-id="b25ef-113">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="b25ef-114">Verrà eseguito l'analisi avanzata, ad esempio il rilevamento duplicato, il threading di posta elettronica e l'analizzatore dei temi.</span><span class="sxs-lookup"><span data-stu-id="b25ef-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="b25ef-115">Successivamente, è possibile visualizzare i temi generali dei dati e anche organizzare i documenti tramite thread di posta elettronica, duplicati esatti e duplicati quasi per facilitare l'indagine.</span><span class="sxs-lookup"><span data-stu-id="b25ef-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, exact duplicates and near duplicates to facilitate your investigation.</span></span> <span data-ttu-id="b25ef-116">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="b25ef-116">For more information, see:</span></span>

  - [<span data-ttu-id="b25ef-117">Eseguire analisi per analizzare più velocemente</span><span class="sxs-lookup"><span data-stu-id="b25ef-117">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)

## <a name="view-documents-in-evidence"></a><span data-ttu-id="b25ef-118">Visualizzare i documenti in evidenza</span><span class="sxs-lookup"><span data-stu-id="b25ef-118">View documents in evidence</span></span>

<span data-ttu-id="b25ef-119">L'analisi dei dati (Preview) Visualizza il contenuto tramite diversi visualizzatori ognuno con diversi scopi.</span><span class="sxs-lookup"><span data-stu-id="b25ef-119">Data investigation (Preview) displays content via several viewers each with different purposes.</span></span> <span data-ttu-id="b25ef-120">È possibile utilizzare i diversi visualizzatori facendo clic su qualsiasi documento in **evidenza**.</span><span class="sxs-lookup"><span data-stu-id="b25ef-120">The various viewers can be used by clicking on any document in **Evidence**.</span></span> <span data-ttu-id="b25ef-121">I visualizzatori attualmente forniti sono:</span><span class="sxs-lookup"><span data-stu-id="b25ef-121">The viewers currently provided are:</span></span>

- <span data-ttu-id="b25ef-122">Metadati dei file</span><span class="sxs-lookup"><span data-stu-id="b25ef-122">File metadata</span></span>
- <span data-ttu-id="b25ef-123">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="b25ef-123">Native view</span></span>
- <span data-ttu-id="b25ef-124">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="b25ef-124">Text view</span></span>
- <span data-ttu-id="b25ef-125">Visualizzazione anNotazioni</span><span class="sxs-lookup"><span data-stu-id="b25ef-125">Annotate view</span></span>
- <span data-ttu-id="b25ef-126">Visualizzazione convertita</span><span class="sxs-lookup"><span data-stu-id="b25ef-126">Converted view</span></span>

## <a name="file-metadata"></a><span data-ttu-id="b25ef-127">Metadati dei file</span><span class="sxs-lookup"><span data-stu-id="b25ef-127">File metadata</span></span>

<span data-ttu-id="b25ef-128">Questo pannello può essere attivato/disattivato per visualizzare i vari metadati associati al documento.</span><span class="sxs-lookup"><span data-stu-id="b25ef-128">This panel can be toggled on/off to display various metadata associated with the document.</span></span> <span data-ttu-id="b25ef-129">Anche se la griglia dei risultati di ricerca può essere personalizzata per la visualizzazione di metadati specifici, è possibile che lo scorrimento orizzontale possa essere difficoltoso durante la revisione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b25ef-129">Although the search results grid can be customized to display specific metadata, there are instances where scrolling horizontally can be difficult while reviewing data.</span></span> <span data-ttu-id="b25ef-130">Il pannello metadati file consente a un utente di alternare una visualizzazione all'interno del visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="b25ef-130">The File metadata panel allows a user to toggle on a view within the viewer.</span></span>

![<span data-ttu-id="b25ef-131">Pannello metadati file</span><span class="sxs-lookup"><span data-stu-id="b25ef-131">File metadata panel</span></span>
](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="b25ef-132">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="b25ef-132">Native view</span></span>

<span data-ttu-id="b25ef-133">Il Visualizzatore nativo Visualizza la visualizzazione più ricca di un documento.</span><span class="sxs-lookup"><span data-stu-id="b25ef-133">The Native viewer displays the richest view of a document.</span></span> <span data-ttu-id="b25ef-134">Supporta centinaia di tipi di file e ha lo scopo di visualizzare l'esperienza più vera e nativa possibile.</span><span class="sxs-lookup"><span data-stu-id="b25ef-134">It supports hundreds of file types and is meant to display the truest to native experience possible.</span></span> <span data-ttu-id="b25ef-135">Per i file di Microsoft Office, ad esempio, il visualizzatore utilizza Office Online per visualizzare contenuti quali commenti a documenti, formule di Excel, righe/colonne nascoste, note di PowerPoint e così via. Per ulteriori informazioni sui visualizzatori di Office Online, visitare \[il collegamento necessario\]</span><span class="sxs-lookup"><span data-stu-id="b25ef-135">For Microsoft Office files, for example, the viewer leverages Office Online in order to display content such as document comments, Excel formulas, hidden rows/columns, PowerPoint notes, etc. For more information regarding the Office Online viewers, visit here \[need link\]</span></span>

![<span data-ttu-id="b25ef-136">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="b25ef-136">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="b25ef-137">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="b25ef-137">Text view</span></span>

<span data-ttu-id="b25ef-138">Il Visualizzatore di testo consente di visualizzare il testo estratto di un file.</span><span class="sxs-lookup"><span data-stu-id="b25ef-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="b25ef-139">Ignora tutte le immagini e la formattazione incorporate, ma sarà una visualizzazione molto perFormante se un utente cerca di comprendere rapidamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b25ef-139">It ignores any embedded images and formatting but will be a very performant view if a user is trying to understand the content quickly.</span></span> <span data-ttu-id="b25ef-140">La visualizzazione testo include anche altre caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="b25ef-140">Text view also includes other features:</span></span>

  - <span data-ttu-id="b25ef-141">Il contatore linea rende più facile fare riferimento a parti specifiche di un documento</span><span class="sxs-lookup"><span data-stu-id="b25ef-141">Line counter makes it easier to reference specific portions of a document</span></span>

  - <span data-ttu-id="b25ef-142">Evidenziazione hit Search che evidenzierà i termini all'interno del documento e la barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="b25ef-142">Search hit highlighting that will highlight terms within the document as well as the scrollbar</span></span>

  - <span data-ttu-id="b25ef-143">La visualizzazione diff fornisce una visualizzazione di confronto che evidenzia le differenze testuali quando si visualizza vicino a documenti duplicati</span><span class="sxs-lookup"><span data-stu-id="b25ef-143">Diff view provides a comparison view that highlights textual differences when viewing Near Duplicate documents</span></span>

![<span data-ttu-id="b25ef-144">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="b25ef-144">Text view</span></span>
](../media/Reviewimage4.png)

![<span data-ttu-id="b25ef-145">Visualizzazione diff</span><span class="sxs-lookup"><span data-stu-id="b25ef-145">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="b25ef-146">Visualizzazione anNotazioni</span><span class="sxs-lookup"><span data-stu-id="b25ef-146">Annotate view</span></span>

<span data-ttu-id="b25ef-147">La visualizzazione anNotazioni fornisce caratteristiche che consentono agli utenti di applicare il markup su un documento durante le indagini, tra cui:</span><span class="sxs-lookup"><span data-stu-id="b25ef-147">The Annotate view provides features that allow users to apply markup on a document during investigation including:</span></span>

  - <span data-ttu-id="b25ef-148">Redazioni area: gli utenti possono disegnare una casella del documento per nascondere i contenuti sensibili</span><span class="sxs-lookup"><span data-stu-id="b25ef-148">Area redactions – users can draw a box on the document in order to hide sensitive content</span></span>

  - <span data-ttu-id="b25ef-149">Matita: gli utenti possono disegnare a mano libera su un documento per portare l'attenzione su determinate parti di un documento.</span><span class="sxs-lookup"><span data-stu-id="b25ef-149">Pencil – users can free-hand draw on a document in order to bring attention to certain portions of a document</span></span>

  - <span data-ttu-id="b25ef-150">Seleziona annotazioni: gli utenti possono selezionare le annotazioni di un documento per eliminare</span><span class="sxs-lookup"><span data-stu-id="b25ef-150">Select annotations - users can select annotations on a document in order to delete</span></span>

  - <span data-ttu-id="b25ef-151">Toggle trasparenza annotazione – rende le annotazioni semitrasparenti per visualizzare il contenuto dietro l'annotazione</span><span class="sxs-lookup"><span data-stu-id="b25ef-151">Toggle annotation transparency – makes annotations semi-transparent in order to view the content behind the annotation</span></span>

  - <span data-ttu-id="b25ef-152">Pagina precedente – consente di accedere alla pagina precedente</span><span class="sxs-lookup"><span data-stu-id="b25ef-152">Previous page – navigates to previous page</span></span>

  - <span data-ttu-id="b25ef-153">Pagina successiva – passa alla pagina successiva</span><span class="sxs-lookup"><span data-stu-id="b25ef-153">Next page – navigates to the next page</span></span>

  - <span data-ttu-id="b25ef-154">Vai a pagina-l'utente può immettere un numero di pagina specifico per passare a</span><span class="sxs-lookup"><span data-stu-id="b25ef-154">Go to page – user can enter a specific page number to navigate to</span></span>

  - <span data-ttu-id="b25ef-155">Zoom – impostare il livello di zoom per la visualizzazione annotazioni</span><span class="sxs-lookup"><span data-stu-id="b25ef-155">Zoom – set zoom level for annotate view</span></span>

  - <span data-ttu-id="b25ef-156">Ruota – l'utente può ruotare il documento in senso orario</span><span class="sxs-lookup"><span data-stu-id="b25ef-156">Rotate – user can rotate document clockwise</span></span>

  - <span data-ttu-id="b25ef-157">Search: l'utente può eseguire una ricerca in un documento e passare ai vari successi all'interno del documento</span><span class="sxs-lookup"><span data-stu-id="b25ef-157">Search – user can search within a document and navigate to the various hits within the document</span></span>
    
    ![<span data-ttu-id="b25ef-158">Visualizzazione anNotazioni</span><span class="sxs-lookup"><span data-stu-id="b25ef-158">Annotate view</span></span>
    ](../media/Reviewimage1.png)

<span data-ttu-id="b25ef-159">Si noti che queste annotazioni sono su dati raccolti come elementi di prova, non nel relativo percorso originale in Live System.</span><span class="sxs-lookup"><span data-stu-id="b25ef-159">Note that these annotations are on data collected as evidence, not at its original location in live system.</span></span> 

## <a name="more-information"></a><span data-ttu-id="b25ef-160">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b25ef-160">More information</span></span>

<span data-ttu-id="b25ef-161">Nella tabella seguente sono elencati i limiti per le evidenze nelle indagini sui dati (Preview).</span><span class="sxs-lookup"><span data-stu-id="b25ef-161">The following table lists the limits for evidence in Data Investigations (Preview).</span></span>  <span data-ttu-id="b25ef-162">Tutti gli elementi che superano i valori massimi dei singoli file verranno visualizzati come errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="b25ef-162">Any items that exceed the single file maximums will show up as processing errors.</span></span>
    
  |<span data-ttu-id="b25ef-163">**Descrizione del limite**</span><span class="sxs-lookup"><span data-stu-id="b25ef-163">**Description of limit**</span></span>|<span data-ttu-id="b25ef-164">**Tipo di limite**</span><span class="sxs-lookup"><span data-stu-id="b25ef-164">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="b25ef-165">Numero massimo di raccolte di prove</span><span class="sxs-lookup"><span data-stu-id="b25ef-165">Maximum number of evidence collections</span></span>  <br/> |<span data-ttu-id="b25ef-166">50</span><span class="sxs-lookup"><span data-stu-id="b25ef-166">50</span></span>  <br/> |
  |<span data-ttu-id="b25ef-167">Numero totale di documenti che possono essere ingeriti in un caso (per tutte le raccolte di evidenze nell'inchiesta)</span><span class="sxs-lookup"><span data-stu-id="b25ef-167">Total number of documents that can be ingested into a case (for all evidence collections in the investigation)</span></span>  <br/> |<span data-ttu-id="b25ef-168">1 milione</span><span class="sxs-lookup"><span data-stu-id="b25ef-168">1 million</span></span>  <br/> |
  |<span data-ttu-id="b25ef-169">Dimensioni totali dei file per carico</span><span class="sxs-lookup"><span data-stu-id="b25ef-169">Total file size per load</span></span>  <br/> |<span data-ttu-id="b25ef-170">100 GB</span><span class="sxs-lookup"><span data-stu-id="b25ef-170">100 GB</span></span>  <br/> |
  |<span data-ttu-id="b25ef-171">Dimensioni massime di un singolo file</span><span class="sxs-lookup"><span data-stu-id="b25ef-171">Maximum size of single file</span></span>   <br/> |<span data-ttu-id="b25ef-172">100 MB</span><span class="sxs-lookup"><span data-stu-id="b25ef-172">100 MB</span></span>  <br/> |
  |<span data-ttu-id="b25ef-173">Numero massimo di caratteri estratti da un singolo file</span><span class="sxs-lookup"><span data-stu-id="b25ef-173">Maximum number of characters extracted from a single file</span></span>  <br/> |<span data-ttu-id="b25ef-174">10 milioni</span><span class="sxs-lookup"><span data-stu-id="b25ef-174">10 million</span></span>  <br/> |
  |<span data-ttu-id="b25ef-175">Profondità degli elementi incorporati in un documento</span><span class="sxs-lookup"><span data-stu-id="b25ef-175">Depth of embedded items in a document</span></span>  <br/> |<span data-ttu-id="b25ef-176">25</span><span class="sxs-lookup"><span data-stu-id="b25ef-176">25</span></span>  <br/> |
  