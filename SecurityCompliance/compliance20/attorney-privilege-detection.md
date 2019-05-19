---
title: Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ee5f2257e73467c50a0ecc296d8d3b70b7c3d0f8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155188"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a><span data-ttu-id="027a8-102">Set up Attorney-Client Privilege Detection (Preview) in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="027a8-102">Set up attorney-client privilege detection (preview) in Advanced eDiscovery</span></span>

<span data-ttu-id="027a8-103">Un aspetto importante e costoso della parte di revisione di qualsiasi processo di individuazione consiste nell'esaminare il contenuto con privilegi.</span><span class="sxs-lookup"><span data-stu-id="027a8-103">A major and costly aspect of the review portion of any discovery process is reviewing for privileged content.</span></span> <span data-ttu-id="027a8-104">Advanced eDiscovery fornisce un rilevamento basato sui contenuti con privilegi AI nel caso in cui è possibile rendere più efficiente questo processo.</span><span class="sxs-lookup"><span data-stu-id="027a8-104">Advanced eDiscovery provides an AI-based detection of privileged content in your case so that you can make this process more efficient.</span></span> <span data-ttu-id="027a8-105">Poiché questa funzionalità è attualmente in fase di beta, un amministratore di eDiscovery deve scegliere la funzionalità per utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="027a8-105">As this feature is currently in beta, an eDiscovery Administrator has to opt into the feature to use it.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="027a8-106">Funzionamento.</span><span class="sxs-lookup"><span data-stu-id="027a8-106">How does it work?</span></span>

<span data-ttu-id="027a8-107">Quando la funzionalità è attivata, quando si analizza un set di revisione all'interno di un caso, tutti i documenti vengono eseguiti tramite il modello di rilevamento dei privilegi avvocato-client.</span><span class="sxs-lookup"><span data-stu-id="027a8-107">With the feature turned on, when you analyze a review set within a case, all documents run through the attorney-client privilege detection model.</span></span> <span data-ttu-id="027a8-108">Il modello analizza due elementi:</span><span class="sxs-lookup"><span data-stu-id="027a8-108">The model looks at two things:</span></span>

- <span data-ttu-id="027a8-109">Content: il modello ML determina la probabilità che il contenuto del documento sia di natura legale.</span><span class="sxs-lookup"><span data-stu-id="027a8-109">Content: the ML model determines the likelihood of the document's content being legal in nature.</span></span>

- <span data-ttu-id="027a8-110">Partecipanti: se è presente un elenco di avvocati caricato dall'utente per il tenant, il modello Confronta i partecipanti del documento in base all'elenco per determinare se il documento ha almeno un partecipante all'avvocato.</span><span class="sxs-lookup"><span data-stu-id="027a8-110">Participants: if there is a user-uploaded list of attorneys for the tenant, the model compares the participants of the document against the list to determine whether the document has at least one attorney participant.</span></span>
<span data-ttu-id="027a8-111">Il modello restituisce tre valori per ogni documento, che saranno tutti ricercabili all'interno di un set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="027a8-111">The model outputs three values for every document, all of which will be searchable within a review set:</span></span>

- <span data-ttu-id="027a8-112">Punteggio contenuto: la probabilità che il documento sia di natura legale (Punteggio compreso tra 0 e 1)</span><span class="sxs-lookup"><span data-stu-id="027a8-112">Content score: the likelihood of the document being legal in nature (score between 0 and 1)</span></span>

- <span data-ttu-id="027a8-113">Ha un avvocato: true se uno dei partecipanti è presente nell'elenco dei procuratori caricati, false in caso contrario o se non è presente un elenco di avvocati.</span><span class="sxs-lookup"><span data-stu-id="027a8-113">Has Attorney: True if one of the participants is found in the uploaded attorney list, false otherwise, or if there is no attorney list.</span></span>

-  <span data-ttu-id="027a8-114">Potenzialmente privilegiato: true se il Punteggio di contenuto è al di sopra della soglia o ha un partecipante all'avvocato, false in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="027a8-114">Potentially Privileged: True if content score is above threshold or has an attorney participant, false otherwise.</span></span>

## <a name="opting-into-attorney-client-privilege-detection"></a><span data-ttu-id="027a8-115">Scelta del rilevamento dei privilegi del procuratore-client</span><span class="sxs-lookup"><span data-stu-id="027a8-115">Opting into Attorney-client privilege detection</span></span>

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a><span data-ttu-id="027a8-116">Passaggio 1: opt-in Attorney-Client Privilege Detection (eDiscovery admin)</span><span class="sxs-lookup"><span data-stu-id="027a8-116">Step 1: Opt into Attorney-client privilege detection (eDiscovery Admin)</span></span>

<span data-ttu-id="027a8-117">Poiché il rilevamento dei privilegi di avvocato-client è una funzionalità di anteprima, l'amministratore di eDiscovery deve scegliere di rendere disponibile la funzionalità nei casi.</span><span class="sxs-lookup"><span data-stu-id="027a8-117">Because Attorney-client privilege detection is a preview feature, your eDiscovery Administrator needs to opt in to make the feature available in your cases.</span></span>

- <span data-ttu-id="027a8-118">Passare a "configurare le funzionalità sperimentali" dalla pagina eDiscovery avanzata</span><span class="sxs-lookup"><span data-stu-id="027a8-118">Go to "Configure experimental features" from Advanced eDiscovery page</span></span>

- <span data-ttu-id="027a8-119">Fare clic su "Gestisci rilevamento dei privilegi di avvocato-client".</span><span class="sxs-lookup"><span data-stu-id="027a8-119">Click on "Manage Attorney-Client Privilege detection".</span></span>

- <span data-ttu-id="027a8-120">Fare clic sull'interruttore per attivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="027a8-120">Click on the toggle to turn the feature on.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="027a8-121">Passaggio 2: caricare un elenco di avvocati (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="027a8-121">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="027a8-122">Per sfruttare al meglio il rilevamento dei privilegi di avvocato-client, è consigliabile fornire un elenco di indirizzi di posta elettronica avvocati o persone giuridiche che lavorano per la società.</span><span class="sxs-lookup"><span data-stu-id="027a8-122">In order to take full advantage of attorney-client privilege detection we recommend providing a list of email addresses lawyers or legal personas who work for the company.</span></span> <span data-ttu-id="027a8-123">L'elenco deve essere un formato CSV senza intestazione, con un solo indirizzo di posta elettronica per riga.</span><span class="sxs-lookup"><span data-stu-id="027a8-123">The list should be a header-less CSV, with one email address per line.</span></span>

## <a name="leveraging-attorney-client-privilege-detection"></a><span data-ttu-id="027a8-124">Utilizzo del rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="027a8-124">Leveraging attorney-client privilege detection</span></span> 

### <a name="step-1-analyze-a-review-set"></a><span data-ttu-id="027a8-125">Passaggio 1: analizzare un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="027a8-125">Step 1: Analyze a review set</span></span>

<span data-ttu-id="027a8-126">Quando si analizza il set di revisione, verrà eseguito anche il rilevamento dei privilegi del procuratore-client.</span><span class="sxs-lookup"><span data-stu-id="027a8-126">When you analyze your review set, attorney-client privilege detection will be run as well.</span></span> <span data-ttu-id="027a8-127">Per ulteriori informazioni sull'analisi dei dati nel set di revisione, fare riferimento a [analyze data in a Review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="027a8-127">To learn more about analyzing data in review set, please refer to [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="027a8-128">Passaggio 2: creare un gruppo di smart tag con il modello di rilevamento dei privilegi avvocato-client</span><span class="sxs-lookup"><span data-stu-id="027a8-128">Step 2: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="027a8-129">Uno dei modi principali in cui è possibile utilizzare i risultati del rilevamento dei privilegi di avvocato-client nel processo di revisione è l'utilizzo di un gruppo di smart tag.</span><span class="sxs-lookup"><span data-stu-id="027a8-129">One of the main ways you can consume the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="027a8-130">I gruppi di smart tag prevedono i risultati di un modello ML e mostrano i risultati del modello in linea accanto ai tag, in modo da poter facilmente utilizzare i risultati del modello, se necessario, e usare i tag del processo di revisione come se si trattasse di qualsiasi altro tag nel pannello di tagging.</span><span class="sxs-lookup"><span data-stu-id="027a8-130">Smart tag groups take the results of an ML model and show the results of the model in-line next to the tags, so that you can easily consume the results of the model where relevant, and use the tags in your review process as you would any other tags in your tagging panel.</span></span> <span data-ttu-id="027a8-131">Per ulteriori informazioni, fare riferimento a [impostare gli smart tag per la revisione ml-assistita in Advanced eDiscovery](smart-tags.md) .</span><span class="sxs-lookup"><span data-stu-id="027a8-131">Please refer to [Set up smart tags for ML-assisted review in Advanced eDiscovery](smart-tags.md) for more information.</span></span>

- <span data-ttu-id="027a8-132">In "Gestisci tag", fare clic su "Aggiungi sezione Smart tag".</span><span class="sxs-lookup"><span data-stu-id="027a8-132">In "Manage tags", click on "Add smart tag section".</span></span>

- <span data-ttu-id="027a8-133">Selezionare "rilevamento dei privilegi del procuratore dei clienti".</span><span class="sxs-lookup"><span data-stu-id="027a8-133">Select "Attorney-client privilege detection".</span></span> <span data-ttu-id="027a8-134">Si vedrà che sono stati creati un gruppo di tag e due tag, corrispondenti ai possibili risultati del modello.</span><span class="sxs-lookup"><span data-stu-id="027a8-134">You will see that a tag group and two tags, corresponding to the possible results of the model, have been created.</span></span>

- <span data-ttu-id="027a8-135">Rinominare il gruppo di tag e i tag come riesci a vedere adatta per la tua recensione.</span><span class="sxs-lookup"><span data-stu-id="027a8-135">Rename the tag group and tags as you see fit for your review.</span></span>

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a><span data-ttu-id="027a8-136">Passaggio 3: utilizzare il gruppo smart tag per la revisione dei privilegi</span><span class="sxs-lookup"><span data-stu-id="027a8-136">Step 3: Use the smart tag group for privilege review</span></span>

<span data-ttu-id="027a8-137">Quando si esamina un documento, se il modello ha determinato che il documento è potenzialmente privilegiato, lo smart tag corrispondente esporrà il risultato:</span><span class="sxs-lookup"><span data-stu-id="027a8-137">When you review a document, if the model has determined that the document is potentially privileged, the corresponding smart tag will expose the result:</span></span>

- <span data-ttu-id="027a8-138">Se il documento contiene contenuto che potrebbe essere di natura legale, accanto allo smart tag corrispondente verrà visualizzata un'etichetta "contenuto legale".</span><span class="sxs-lookup"><span data-stu-id="027a8-138">If the document has content that may be legal in nature, a "Legal content" label will appear next to the corresponding smart tag.</span></span>

- <span data-ttu-id="027a8-139">Se il documento ha un partecipante che si trova nell'elenco dei procuratori caricati, accanto allo smart tag corrispondente verrà visualizzata un'etichetta "procuratore".</span><span class="sxs-lookup"><span data-stu-id="027a8-139">If the document has a participant that is found in the uploaded attorney list, an "Attorney" label will appear next to the corresponding smart tag.</span></span>