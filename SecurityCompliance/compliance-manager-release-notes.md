---
title: Note sulla versione di Microsoft Compliance Manager
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal. Compliance Manager consente di monitorare, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: 5e18445e3f9ad2848f18174788ec6dd40bc4a178
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473116"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="98def-104">Note sulla versione per Compliance Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="98def-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="98def-105">L'anteprima pubblica di Compliance Manager fornisce l'accesso tempestivo alle funzionalità e agli aggiornamenti imminenti.</span><span class="sxs-lookup"><span data-stu-id="98def-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="98def-106">È possibile utilizzare lo strumento di [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) aggiornato nel [Service Trust Portal](https://servicetrust.microsoft.com) per tenere conto, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98def-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="98def-107">Novità di Compliance Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="98def-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="98def-108">**Integrazione con Microsoft Secure Score:** Compliance Manager supporta l'integrazione con [Microsoft Secure Score](microsoft-secure-score.md) tramite la mappaTura delle azioni gestite dai clienti a più di 50 operazioni di valutazione sicure.</span><span class="sxs-lookup"><span data-stu-id="98def-108">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="98def-109">Quando si completa un'azione mappata in Punteggio sicuro, l'azione corrispondente di Compliance Manager viene aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="98def-109">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action is automatically updated.</span></span>

- <span data-ttu-id="98def-110">**Importare valutazioni personalizzate:** Oltre alle valutazioni predefinite, Compliance Manager ora supporta l'importazione di modelli personalizzati, consentendo di creare valutazioni personalizzate per qualsiasi prodotto o servizio, nonché per qualsiasi norma o regolamentazione.</span><span class="sxs-lookup"><span data-stu-id="98def-110">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates, enabling you to create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="98def-111">**Elementi Actions:** Gli elementi azione sono ora singoli elementi e molti includono la raccolta di telemetria dall'API Microsoft Secure Score Graph.</span><span class="sxs-lookup"><span data-stu-id="98def-111">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="98def-112">Se possibile, le raccomandazioni per l'azione tecnica sono ora collegate alla pagina di configurazione applicabile nel servizio Office 365.</span><span class="sxs-lookup"><span data-stu-id="98def-112">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="98def-113">**Gestione tenant:** Nuova interfaccia per la gestione dei nuovi elementi dati in Compliance Manager (Preview):</span><span class="sxs-lookup"><span data-stu-id="98def-113">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="98def-114">**Dimensioni:** Consente di visualizzare, aggiungere e personalizzare i metadati per i modelli, le valutazioni e gli elementi di azione che consentono di creare pivot personalizzati per i filtri.</span><span class="sxs-lookup"><span data-stu-id="98def-114">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="98def-115">**Proprietari:** Specificare un proprietario per ogni elemento di azione.</span><span class="sxs-lookup"><span data-stu-id="98def-115">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="98def-116">**Azioni dei clienti:** Gestire l'elenco completo degli elementi delle azioni inclusi in Compliance Manager (Preview) e abilitare/disabilitare il monitoraggio del Punteggio sicuro per gli elementi di azione che sono integrati con Secure score.</span><span class="sxs-lookup"><span data-stu-id="98def-116">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items that are integrated with Secure Score.</span></span>

- <span data-ttu-id="98def-117">**Punteggio di conformità aggiornato**: la metodologia è stata modificata per supportare la sincronizzazione con Microsoft Secure score.</span><span class="sxs-lookup"><span data-stu-id="98def-117">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="98def-118">Il sistema di Punteggio rimuove i crediti di controllo gestiti da Microsoft e si concentra esclusivamente sul completamento dei controlli gestiti dal cliente.</span><span class="sxs-lookup"><span data-stu-id="98def-118">The scoring system removes the Microsoft-managed control credits and focuses solely on the completion of customer-managed controls.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="98def-119">Problemi noti in Compliance Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="98def-119">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="98def-120">Nelle sezioni seguenti vengono illustrati i problemi noti da risolvere nelle prossime versioni di Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="98def-120">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="98def-121">Punteggio di conformità</span><span class="sxs-lookup"><span data-stu-id="98def-121">Compliance Score</span></span>

- <span data-ttu-id="98def-122">Quando gli elementi azione sono contrassegnati come **non nell'ambito**, il punteggio assegnato all'elemento azione non viene escluso dal calcolo del Punteggio di conformità.</span><span class="sxs-lookup"><span data-stu-id="98def-122">When Action Items are marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="98def-123">Gli elementi azione contrassegnati **non nell'ambito** non devono aumentare il Punteggio di conformità.</span><span class="sxs-lookup"><span data-stu-id="98def-123">Action Items marked **Not in Scope** should not increase your Compliance Score.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="98def-124">Controlli gestiti da Microsoft</span><span class="sxs-lookup"><span data-stu-id="98def-124">Microsoft-managed Controls</span></span>

- <span data-ttu-id="98def-125">La data di test per i controlli gestiti da Microsoft non viene visualizzata nell'interfaccia utente, anche se inclusa nella valutazione.</span><span class="sxs-lookup"><span data-stu-id="98def-125">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="98def-126">Per visualizzare le informazioni relative alla data di test, è necessario esportare la valutazione.</span><span class="sxs-lookup"><span data-stu-id="98def-126">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="98def-127">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="98def-127">Customization</span></span>

- <span data-ttu-id="98def-128">L'aggiunta di controlli personalizzati consente di aggiungere un nuovo controllo a una famiglia di controlli esistente, ma non consente di aggiungere una nuova famiglia di controlli.</span><span class="sxs-lookup"><span data-stu-id="98def-128">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="98def-129">Questa versione non supporta il collegamento di elementi azione o l'aggiunta di elementi o controlli di azioni a una valutazione.</span><span class="sxs-lookup"><span data-stu-id="98def-129">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="98def-130">Se si crea un'azione personalizzata, non è possibile modificarla o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="98def-130">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="98def-131">Famiglie di controllo non visualizzate nelle valutazioni</span><span class="sxs-lookup"><span data-stu-id="98def-131">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="98def-132">Quando si importa un modello, tutte le valutazioni basate su tale modello riflettono tutte le famiglie di controlli facenti parte del modello.</span><span class="sxs-lookup"><span data-stu-id="98def-132">When you import a Template, all Assessments based on that Template will reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="98def-133">Tuttavia, se si aggiungono nuove famiglie di controlli al modello, tutte le valutazioni esistenti non riflettono le modifiche.</span><span class="sxs-lookup"><span data-stu-id="98def-133">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="98def-134">Solo le nuove valutazioni create al di fuori del modello aggiornato riflettono le modifiche.</span><span class="sxs-lookup"><span data-stu-id="98def-134">Only new Assessments created off the updated Template will reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="98def-135">Filtri</span><span class="sxs-lookup"><span data-stu-id="98def-135">Filters</span></span>

- <span data-ttu-id="98def-136">Il filtro sugli elementi o sui controlli di azione non produce in modo coerente risultati corretti.</span><span class="sxs-lookup"><span data-stu-id="98def-136">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="98def-137">Modelli</span><span class="sxs-lookup"><span data-stu-id="98def-137">Templates</span></span>

- <span data-ttu-id="98def-138">I modelli archiviati sono modificabili e non devono essere modificabili.</span><span class="sxs-lookup"><span data-stu-id="98def-138">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="98def-139">I modelli bloccati consentono la creazione di una valutazione quando non dovrebbero.</span><span class="sxs-lookup"><span data-stu-id="98def-139">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="98def-140">Il blocco di un modello deve impedire che venga utilizzato per creare valutazioni.</span><span class="sxs-lookup"><span data-stu-id="98def-140">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="98def-141">Esportazione</span><span class="sxs-lookup"><span data-stu-id="98def-141">Export</span></span>

- <span data-ttu-id="98def-142">L'esportazione dei modelli in JSON ha esito negativo quando lo stato del modello è impostato su **importazione** o **in attesa di approvazione**.</span><span class="sxs-lookup"><span data-stu-id="98def-142">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="98def-143">Browser supportati</span><span class="sxs-lookup"><span data-stu-id="98def-143">Supported browsers</span></span>

- <span data-ttu-id="98def-144">Sono supportate le versioni più recenti di Microsoft Edge, Chrome e Safari.</span><span class="sxs-lookup"><span data-stu-id="98def-144">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="98def-145">Possono verificarsi casi in cui i dati aggiornati non vengono visualizzati fino a quando il browser non viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="98def-145">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="98def-146">La versione di anteprima di Microsoft Edge non è supportata ma non ha problemi noti.</span><span class="sxs-lookup"><span data-stu-id="98def-146">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="98def-147">Internet Explorer non è supportato.</span><span class="sxs-lookup"><span data-stu-id="98def-147">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="98def-148">Timeout sessione</span><span class="sxs-lookup"><span data-stu-id="98def-148">Session timeout</span></span>

- <span data-ttu-id="98def-149">Quando si verifica un timeout di una sessione, potrebbe essere visualizzato un errore "qualcosa è andato storto".</span><span class="sxs-lookup"><span data-stu-id="98def-149">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="98def-150">Per risolvere il caso, passare a [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) e accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="98def-150">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>