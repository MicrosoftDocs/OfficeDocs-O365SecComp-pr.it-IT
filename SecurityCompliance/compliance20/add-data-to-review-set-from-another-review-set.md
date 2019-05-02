---
title: Aggiungere dati da un set di revisione a un altro set di Revisione
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
ms.openlocfilehash: 025fd90373313f762ce1d1dab8d48286e32e3cbb
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527204"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="b6eaa-102">Aggiungere dati a un set di revisione da un altro set di Revisione</span><span class="sxs-lookup"><span data-stu-id="b6eaa-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="b6eaa-103">In alcuni casi, potrebbe essere necessario ripartire una parte di documenti da un set di revisione e utilizzarli singolarmente in un altro set di revisione.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="b6eaa-104">Questo è particolarmente utile se si è abbattuti contenuti in un set di revisione e si vuole eseguire l'analisi del sottoinsieme di dati.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="b6eaa-105">Utilizzare il flusso di lavoro seguente per aggiungere contenuto da un set di revisione a un altro.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-105">Use the following workflow to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b6eaa-106">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="b6eaa-106">Before you begin</span></span>

<span data-ttu-id="b6eaa-107">Prima di iniziare, è necessario creare un nuovo set di revisione a cui aggiungere i dati.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="b6eaa-108">È possibile aggiungere un nuovo set di revisione nella scheda **revisione dei set** del caso.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="b6eaa-109">Per ulteriori informazioni, vedere [gestire i set di revisione](managing-review-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b6eaa-109">For more information, see [Manage review sets](managing-review-sets.md).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="b6eaa-110">Passaggio 1: identificare il contenuto da aggiungere a un altro set di Revisione</span><span class="sxs-lookup"><span data-stu-id="b6eaa-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="b6eaa-111">È possibile aggiungere contenuto a un set di revisione selezionando messaggi di posta elettronica e documenti nella griglia del documento o in tutti gli elementi di un risultato di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-111">You can add content to a review set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="b6eaa-112">Se si sceglie di aggiungere elementi selezionati, selezionare gli elementi, fare clic su **azione**, quindi fare clic su **Aggiungi a un altro set di revisione**.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-112">If choosing to add selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![Aggiungi a un altro set di Revisione](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="b6eaa-114">Passaggio 2: specificare le opzioni per l'aggiunta a un altro set di Revisione</span><span class="sxs-lookup"><span data-stu-id="b6eaa-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="b6eaa-115">Nella pagina **Aggiungi a un altro** riquadro a comparsa del set di revisione scegliere il set di revisione a cui si desidera aggiungere gli elementi.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-115">In the **Add to another review set** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="b6eaa-116">Scegliere se aggiungere **tutti i risultati di ricerca** o **gli elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="b6eaa-117">Altre informazioni forniscono opzioni per includere tutti i metadati dagli elementi e, infine, se i tag del documento devono essere inclusi nel nuovo set di revisione.</span><span class="sxs-lookup"><span data-stu-id="b6eaa-117">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new review set.</span></span>  <span data-ttu-id="b6eaa-118">Dopo aver fatto clic su **OK** , verrà creato un nuovo processo per aggiungere il contenuto a un set di revisione. è possibile monitorare lo stato di avanzamento del processo nella scheda **processo** . Per ulteriori informazioni, vedere [gestire i processi](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="b6eaa-118">After clicking **Ok** a new job will be created to add the content to a review set; you can monitor the progress of that job on the **Job** tab. For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>

![Aggiungi a un altro set di Revisione](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)
