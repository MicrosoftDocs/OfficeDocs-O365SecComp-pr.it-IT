---
title: Aggiungere tag ai documenti in un set di lavoro
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
ms.openlocfilehash: 1183264f64a74e50f750ee13618f7532ffe04eb7
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455158"
---
# <a name="tag-documents-in-a-working-set"></a><span data-ttu-id="f11d6-102">Aggiungere tag ai documenti in un set di lavoro</span><span class="sxs-lookup"><span data-stu-id="f11d6-102">Tag documents in a working set</span></span>

<span data-ttu-id="f11d6-103">L'organizzazione del contenuto in un working set è importante per completare diversi flussi di lavoro nel processo di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f11d6-103">Organizing content in a working set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="f11d6-104">Ciò include:</span><span class="sxs-lookup"><span data-stu-id="f11d6-104">This includes:</span></span>

-  <span data-ttu-id="f11d6-105">Eliminazione del contenuto non necessario.</span><span class="sxs-lookup"><span data-stu-id="f11d6-105">Culling unnecessary content.</span></span>

- <span data-ttu-id="f11d6-106">Identificare il contenuto pertinente.</span><span class="sxs-lookup"><span data-stu-id="f11d6-106">Identifying relevant content.</span></span>
 
-  <span data-ttu-id="f11d6-107">Identificare il contenuto che deve essere esaminato da un esperto o da un avvocato.</span><span class="sxs-lookup"><span data-stu-id="f11d6-107">Identifying content that must be reviewed by an expert or an attorney.</span></span>

<span data-ttu-id="f11d6-108">Quando esperti, avvocati o altri utenti esaminano il contenuto in un working set, le loro opinioni relative al contenuto possono essere acquisite utilizzando i tag.</span><span class="sxs-lookup"><span data-stu-id="f11d6-108">When experts, attorneys, or other users review content in a working set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="f11d6-109">Ad esempio, se lo scopo è quello di eliminare contenuto non necessario, un utente può contrassegnare i documenti con un tag come "non rispondente".</span><span class="sxs-lookup"><span data-stu-id="f11d6-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="f11d6-110">Dopo la revisione e il tag del contenuto, è possibile creare una ricerca di working set che escluda qualsiasi contenuto contrassegnato come "non reattivo", che elimini questo contenuto dai passaggi successivi del flusso di lavoro di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f11d6-110">After content has been reviewed and tagged, a working set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="f11d6-111">Il riquadro Tag può essere personalizzato per ogni caso, in modo che i tag possano supportare il flusso di lavoro di revisione previsto.</span><span class="sxs-lookup"><span data-stu-id="f11d6-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="f11d6-112">Tipi di tag</span><span class="sxs-lookup"><span data-stu-id="f11d6-112">Tag types</span></span>

<span data-ttu-id="f11d6-113">Advanced eDiscovery (Preview) fornisce due tipi di Tag:</span><span class="sxs-lookup"><span data-stu-id="f11d6-113">Advanced eDiscovery (Preview) provides two types of tags:</span></span>

- <span data-ttu-id="f11d6-114">**Tag a scelta singola** : limita gli utenti a selezionare un singolo tag all'interno di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="f11d6-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="f11d6-115">Questo può essere utile per garantire agli utenti di non selezionare tag in conflitto, ad esempio "reattivi" e "non rispondenti".</span><span class="sxs-lookup"><span data-stu-id="f11d6-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> 

- <span data-ttu-id="f11d6-116">**Tag a scelta multipla** : consente agli utenti di selezionare più tag all'interno di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="f11d6-116">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="f11d6-117">Struttura tag</span><span class="sxs-lookup"><span data-stu-id="f11d6-117">Tag structure</span></span>

<span data-ttu-id="f11d6-118">Oltre ai tipi di tag, è possibile utilizzare la struttura dei tag nell'organizzazione nel pannello Tag per rendere più intuitivi i documenti di tagging.</span><span class="sxs-lookup"><span data-stu-id="f11d6-118">In addition to the tag types, the structure of how tags are organization in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="f11d6-119">I tag vengono raggruppati in base alle sezioni.</span><span class="sxs-lookup"><span data-stu-id="f11d6-119">Tags are grouped by sections.</span></span> <span data-ttu-id="f11d6-120">La ricerca di working set supporta la funzionalità di ricerca in base al tag e alla sezione Tag.</span><span class="sxs-lookup"><span data-stu-id="f11d6-120">Working set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="f11d6-121">Questo significa che è possibile creare una ricerca di working set per recuperare i documenti contrassegnati con un tag qualsiasi in una sezione.</span><span class="sxs-lookup"><span data-stu-id="f11d6-121">This means you can create a working set search to retrieve documents tagged with any tag in a section.</span></span>

![Sezioni dei tag nel pannello Tag](../media/Tagtypes.png)

<span data-ttu-id="f11d6-123">I tag possono essere ulteriormente organizzati annidando questi all'interno di una sezione.</span><span class="sxs-lookup"><span data-stu-id="f11d6-123">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="f11d6-124">Ad esempio, se si intende identificare e contrassegnare il contenuto con privilegi, è possibile utilizzare la nidificazione per specificare che un utente può contrassegnare un documento come "privilegiato" e selezionare il tipo di privilegio selezionando il tag nidificato appropriato.</span><span class="sxs-lookup"><span data-stu-id="f11d6-124">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![Tag annidati all'interno di una sezione Tag](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="f11d6-126">Applicazione di tag</span><span class="sxs-lookup"><span data-stu-id="f11d6-126">Applying tags</span></span>

<span data-ttu-id="f11d6-127">Esistono diversi modi per applicare un tag al contenuto.</span><span class="sxs-lookup"><span data-stu-id="f11d6-127">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="f11d6-128">Tagging di un singolo documento</span><span class="sxs-lookup"><span data-stu-id="f11d6-128">Tagging a single document</span></span>

<span data-ttu-id="f11d6-129">Quando si visualizza un documento in un working set, è possibile visualizzare i tag che possono essere utilizzati da una recensione facendo clic su **Pannello di codifica**.</span><span class="sxs-lookup"><span data-stu-id="f11d6-129">When viewing a document in a working set, you can display the tags that a review can use by clicking **Coding panel**.</span></span>

![Fare clic su pannello Tag per visualizzare il pannello Tag](../media/Singledoctag.png)

<span data-ttu-id="f11d6-131">Ciò consentirà di applicare i tag al documento visualizzato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f11d6-131">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="f11d6-132">Tag di massa</span><span class="sxs-lookup"><span data-stu-id="f11d6-132">Bulk tagging</span></span>

<span data-ttu-id="f11d6-133">Il tagging di massa può essere ottenuto selezionando più file nella griglia dei risultati e quindi utilizzando i tag del **riquadro di codifica** in modo analogo al tagging dei singoli documenti.</span><span class="sxs-lookup"><span data-stu-id="f11d6-133">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Coding panel** similar to tagging single documents.</span></span> <span data-ttu-id="f11d6-134">Non è possibile eseguire un tagging in blocco selezionando due volte i tag; il primo clic applicherà il tag e la seconda selezione assicurerà che il tag sia deselezionato per tutti i file selezionati.</span><span class="sxs-lookup"><span data-stu-id="f11d6-134">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Schermata di una descrizione del telefono cellulare generata automaticamente](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="f11d6-136">Quando si esegue il tagging in blocco, nel riquadro di tagging viene visualizzato il numero di file contrassegnati per ogni tag nel pannello.</span><span class="sxs-lookup"><span data-stu-id="f11d6-136">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="f11d6-137">Tagging in altri pannelli di Revisione</span><span class="sxs-lookup"><span data-stu-id="f11d6-137">Tagging in other review panels</span></span>

<span data-ttu-id="f11d6-138">Quando si esaminano i documenti, è possibile utilizzare gli altri pannelli di revisione per esaminare altre caratteristiche dei documenti nella griglia dei risultati.</span><span class="sxs-lookup"><span data-stu-id="f11d6-138">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="f11d6-139">Questo include la revisione di altri documenti correlati, i thread di posta elettronica, la presenza di duplicati e duplicati hash.</span><span class="sxs-lookup"><span data-stu-id="f11d6-139">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="f11d6-140">Ad esempio, quando si esaminano i documenti correlati (tramite il riquadro Revisione **famiglia documenti** ), è possibile ridurre in modo significativo il tempo di revisione tramite la codifica in blocco dei documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="f11d6-140">For example, when your reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="f11d6-141">Ad esempio, se un messaggio di posta elettronica dispone di più allegati e si desidera garantire che l'intera famiglia sia contrassegnata in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="f11d6-141">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="f11d6-142">Ad esempio, ecco come visualizzare il pannello di **codifica** quando si utilizza il pannello Revisione **famiglia documenti** :</span><span class="sxs-lookup"><span data-stu-id="f11d6-142">For example, here's how to display the **Coding panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="f11d6-143">Se si apre il pannello di controllo per un documento selezionato, ad esempio l'elenco di contenuto correlato nel pannello Revisione **famiglia** documenti, fare clic su **documenti di codice** nella parte superiore del riquadro Revisione corrente.</span><span class="sxs-lookup"><span data-stu-id="f11d6-143">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Code documents** at the top of the current review panel.</span></span>

   <span data-ttu-id="f11d6-144">Il pannello di codifica viene visualizzato come finestra popup.</span><span class="sxs-lookup"><span data-stu-id="f11d6-144">The Coding panel is displayed is a pop-up window.</span></span>

2. <span data-ttu-id="f11d6-145">Scegliere uno o più tag per applicare il documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="f11d6-145">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="f11d6-146">Per contrassegnare tutti i documenti, selezionare tutti i documenti nel riquadro **famiglia** documenti, fare clic su **documenti di codice**e quindi scegliere i tag da applicare all'intera famiglia di documenti.</span><span class="sxs-lookup"><span data-stu-id="f11d6-146">To tag all documents, select all documents in the **Document family** panel, click **Code documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Schermata di una descrizione di social media post generata automaticamente](../media/Relatedtag.png)
