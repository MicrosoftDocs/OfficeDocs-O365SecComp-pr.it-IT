---
title: Aggiungere i risultati della ricerca a un set di lavoro
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
ms.openlocfilehash: 7830b483190a69e6055fae369580064c5df42f49
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958287"
---
# <a name="add-search-results-to-a-working-set"></a><span data-ttu-id="15579-102">Aggiungere i risultati della ricerca a un set di lavoro</span><span class="sxs-lookup"><span data-stu-id="15579-102">Add search results to a working set</span></span>

<span data-ttu-id="15579-103">Dopo aver identificato e raccolto le ricerche in Exchange, SharePoint e OneDrive for business, è possibile aggiungere i risultati a un working set.</span><span class="sxs-lookup"><span data-stu-id="15579-103">After you've identified and culled with searches against Exchange, SharePoint and OneDrive for business, you can add the results to a working set.</span></span> <span data-ttu-id="15579-104">I working set rappresentano un insieme statico di documenti che verranno indicizzati per i risultati di ricerca fulminei, analizza per l'identificazione dei thread di posta elettronica, vicino al rilevamento e ai temi duplicati.</span><span class="sxs-lookup"><span data-stu-id="15579-104">Working sets represent a static set of documents that we will index for lightning fast search results, analyze for email thread identification, near duplicate detection and themes.</span></span>  <span data-ttu-id="15579-105">È inoltre possibile aggiungere dati provenienti da origini dati non di Office 365 per vivere affiancati ai dati raccolti da Office 365.</span><span class="sxs-lookup"><span data-stu-id="15579-105">You can also add data from Non-Office 365 data sources to live side by side with the data you collect from Office 365.</span></span>

<span data-ttu-id="15579-106">Per aggiungere dati a un working set, iniziare selezionando una ricerca, nella barra dei risultati di ricerca, fare clic sul pulsante *+ Add results to working set* .</span><span class="sxs-lookup"><span data-stu-id="15579-106">To add data to a working set, start by selecting a search, in the search results fly out, click the *+ Add results to working set* button.</span></span>

![Aggiunta di dati a un working set](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="15579-108">È quindi possibile scegliere di aggiungere a un working set esistente o a un *nuovo working set*.</span><span class="sxs-lookup"><span data-stu-id="15579-108">You can then choose to add to an existing working set or a *New working set*.</span></span>  <span data-ttu-id="15579-109">Se si aggiunge un nuovo working set, specificare il nome e infine fare clic sul pulsante *Aggiungi* .</span><span class="sxs-lookup"><span data-stu-id="15579-109">If adding to a new working set, specify the name and finally click the *Add* button.</span></span>

![Selezionare un working set](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="15579-111">L'aggiunta di dati a un working set è una procedura di esecuzione prolungata, è possibile monitorare lo stato di avanzamento nella scheda processi o nella colonna *stato working set* nella scheda *ricerche* .  Il processo include la raccolta di elementi da Office 365 e infine ingestione dell'inDicizzazione di &.</span><span class="sxs-lookup"><span data-stu-id="15579-111">Adding data to a working set is a long running process, you can either track the progress in the Jobs tab or in the *Working set status* column in the *Searches* tab.  The process includes gathering items from Office 365 and finally Ingestion & Indexing.</span></span>  <span data-ttu-id="15579-112">Una volta completata l'elaborazione del working set, è possibile passare al working set facendo clic sulla scheda *working* sets e quindi su working set.</span><span class="sxs-lookup"><span data-stu-id="15579-112">Once working set processing is completed, you can navigate to the working set by clicking on the *Working Sets* tab and then clicking on the working set.</span></span>  <span data-ttu-id="15579-113">È quindi possibile passare alla ricerca, alla revisione, al tagging e all'esportazione di tutti i dati rilevanti.</span><span class="sxs-lookup"><span data-stu-id="15579-113">You can then move on to searching, reviewing, tagging and exporting any relevant data.</span></span>

## <a name="adding-a-sample-to-a-working-set"></a><span data-ttu-id="15579-114">Aggiunta di un esempio a un working set</span><span class="sxs-lookup"><span data-stu-id="15579-114">Adding a sample to a working set</span></span>

<span data-ttu-id="15579-115">Se si desidera convalidare i risultati della ricerca più thorougly prima di raccogliere tutti i documenti che sono stati recuperati dalla ricerca, è possibile aggiungere un campione casuale dei risultati della ricerca a un working set invece di aggiungere tutto.</span><span class="sxs-lookup"><span data-stu-id="15579-115">If you would like to validate your search results more thorougly before collecting all documents that were retrieved by your search, you can add a random sample of the search results to a working set instead of adding everything.</span></span>

<span data-ttu-id="15579-116">Per aggiungere un esempio a un working set, iniziare selezionando una ricerca, nel riquadro a comparsa dei risultati di ricerca, fare clic su pulsante di *esempio* .</span><span class="sxs-lookup"><span data-stu-id="15579-116">To add a sample to a working set, start by selecting a search, in the search results flyout, click *Sample* button.</span></span>

<span data-ttu-id="15579-117">È quindi possibile scegliere il parametro del campionamento.</span><span class="sxs-lookup"><span data-stu-id="15579-117">You can then choose the parameter of your sampling.</span></span> <span data-ttu-id="15579-118">Esistono due opzioni:</span><span class="sxs-lookup"><span data-stu-id="15579-118">There are two options:</span></span>
- <span data-ttu-id="15579-119">Livello di confidenza e intervallo: le dimensioni del campione verranno scelte per soddisfare i parametri statistici specificati.</span><span class="sxs-lookup"><span data-stu-id="15579-119">Confidence level and interval: sample size will be chosen to satisfy the given statistical parameters.</span></span>
- <span data-ttu-id="15579-120">Percentuale: la dimensione del campione verrà determinata in base al numero di elementi restituiti dalla ricerca e al parametro scelto.</span><span class="sxs-lookup"><span data-stu-id="15579-120">Percentage: sample size will be determined based on the number of items that was returned by the search, and the chosen parameter.</span></span>

<span data-ttu-id="15579-121">Infine, scegliere il working set per aggiungere il campione.</span><span class="sxs-lookup"><span data-stu-id="15579-121">Finally, choose the working set to add the sample to.</span></span> <span data-ttu-id="15579-122">Da qui, è possibile controllare lo stato del processo esattamente come si farebbe per aggiungere un'intera ricerca in un working set.</span><span class="sxs-lookup"><span data-stu-id="15579-122">From there, you can check the status of the process just as you would for adding a whole search into a working set.</span></span> 