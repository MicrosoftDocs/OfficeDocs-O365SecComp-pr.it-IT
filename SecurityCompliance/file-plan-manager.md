---
title: Panoramica della gestione del piano file
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: La gestione del piano file fornisce funzionalità avanzate per la gestione di criteri di etichette di conservazione ed etichette di conservazione e consente di attraversare in modo integrato le attività con etichette ed etichetta-a-contenuto per l’intero ciclo di vita del contenuto, dalla creazione alla collaborazione, passando per la dichiarazione del record e la conservazione, all’eliminazione finale.
ms.openlocfilehash: b7d80ff6a7f78e592462fe2723a87383e046015f
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547971"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="edf2c-103">Panoramica della gestione del piano file</span><span class="sxs-lookup"><span data-stu-id="edf2c-103">Overview of file plan manager</span></span>

<span data-ttu-id="edf2c-104">La gestione del piano file fornisce funzionalità avanzate per la gestione di criteri di etichette di conservazione ed etichette di conservazione e consente di attraversare in modo integrato le attività con etichette ed etichetta-a-contenuto per l’intero ciclo di vita del contenuto, dalla creazione alla collaborazione, passando per la dichiarazione del record e la conservazione, all’eliminazione finale.</span><span class="sxs-lookup"><span data-stu-id="edf2c-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Pagina del piano file](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="edf2c-106">Accesso alla gestione del piano file</span><span class="sxs-lookup"><span data-stu-id="edf2c-106">Accessing file plan manager</span></span>

<span data-ttu-id="edf2c-107">I requisiti per accedere al piano file sono due:</span><span class="sxs-lookup"><span data-stu-id="edf2c-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="edf2c-108">Un abbonamento a Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="edf2c-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="edf2c-109">L’utente dispone di uno dei ruoli seguenti nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="edf2c-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="edf2c-110">Responsabile della conservazione</span><span class="sxs-lookup"><span data-stu-id="edf2c-110">Retention Manager</span></span>
    - <span data-ttu-id="edf2c-111">Responsabile della conservazione solo visualizzazione</span><span class="sxs-lookup"><span data-stu-id="edf2c-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="edf2c-112">Etichette di conservazione e criteri di etichetta predefiniti</span><span class="sxs-lookup"><span data-stu-id="edf2c-112">Default retention labels and label policy</span></span>

<span data-ttu-id="edf2c-113">Se non sono presenti etichette conservazione nel Centro Sicurezza e Conformità, la prima volta in cui scegli **Piano file** nel riquadro di spostamento a sinistra, verrà creato un criterio di etichetta denominato **Criterio di pubblicazione di governance dei dati predefinito**.</span><span class="sxs-lookup"><span data-stu-id="edf2c-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="edf2c-114">Questo criterio di etichetta contiene tre etichette di conservazione:</span><span class="sxs-lookup"><span data-stu-id="edf2c-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="edf2c-115">**Procedura operativa**</span><span class="sxs-lookup"><span data-stu-id="edf2c-115">**Operational procedure**</span></span>
- <span data-ttu-id="edf2c-116">**Business general**</span><span class="sxs-lookup"><span data-stu-id="edf2c-116">**Business general**</span></span>
- <span data-ttu-id="edf2c-117">**Accordo contrattuale**</span><span class="sxs-lookup"><span data-stu-id="edf2c-117">**Contract agreement**</span></span>

<span data-ttu-id="edf2c-118">Queste etichette di conservazione vengono configurate solo per conservare il contenuto, non per eliminare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="edf2c-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="edf2c-119">Questo criterio di etichetta verrà pubblicato per l'intera organizzazione e può essere disattivato o rimosso.</span><span class="sxs-lookup"><span data-stu-id="edf2c-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="edf2c-120">È possibile stabilire chi ha aperto la gestione del piano file e avviato la first-run experience esaminando il log di controllo per le attività **Criteri di conservazione creati** e **Configurazione di conservazione creata per un criterio di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="edf2c-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="edf2c-121">A causa di feedback di alcuni clienti, è stata rimossa la funzionalità che consente di creare le etichette di conservazione predefinite e i criteri di etichetta di conservazione indicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="edf2c-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="edf2c-122">Le etichette di conservazione e i criteri per le etichette di conservazione sono visibili solo se è stato aperta la gestione del piano file prima dell'11 aprile 2019.</span><span class="sxs-lookup"><span data-stu-id="edf2c-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="edf2c-123">Esplorare il piano file</span><span class="sxs-lookup"><span data-stu-id="edf2c-123">Navigating your file plan</span></span>

<span data-ttu-id="edf2c-124">La gestione del piano file semplifica la visualizzazione unica delle impostazioni di tutti i criteri e le etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="edf2c-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="edf2c-125">Si noti che le etichette di conservazione create all'esterno del piano file saranno disponibili nel piano file e viceversa.</span><span class="sxs-lookup"><span data-stu-id="edf2c-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="edf2c-126">Nella tabella **etichette piano file** sono disponibili le seguenti informazioni e funzionalità aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="edf2c-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="edf2c-127">Colonne impostazioni etichetta</span><span class="sxs-lookup"><span data-stu-id="edf2c-127">Label settings columns</span></span>

- <span data-ttu-id="edf2c-p103">**In base a** identifica il tipo di trigger che avvierà il periodo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="edf2c-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="edf2c-130">Evento</span><span class="sxs-lookup"><span data-stu-id="edf2c-130">Event</span></span>
    - <span data-ttu-id="edf2c-131">Momento della creazione</span><span class="sxs-lookup"><span data-stu-id="edf2c-131">When created</span></span>
    - <span data-ttu-id="edf2c-132">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="edf2c-132">When last modified</span></span>
    - <span data-ttu-id="edf2c-133">Data etichettatura</span><span class="sxs-lookup"><span data-stu-id="edf2c-133">When labeled</span></span>
- <span data-ttu-id="edf2c-p104">**Record** indica se l'elemento diventa un record dichiarato dopo l'applicazione dell'etichetta. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="edf2c-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="edf2c-136">No</span><span class="sxs-lookup"><span data-stu-id="edf2c-136">No</span></span>
    - <span data-ttu-id="edf2c-137">Sì</span><span class="sxs-lookup"><span data-stu-id="edf2c-137">Yes</span></span>
    - <span data-ttu-id="edf2c-138">Sì (normativo)</span><span class="sxs-lookup"><span data-stu-id="edf2c-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="edf2c-p105">**Conservazione** identifica il tipo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="edf2c-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="edf2c-141">Conservare</span><span class="sxs-lookup"><span data-stu-id="edf2c-141">Keep</span></span>
    - <span data-ttu-id="edf2c-142">Conservare ed eliminare</span><span class="sxs-lookup"><span data-stu-id="edf2c-142">Keep and delete</span></span>
    - <span data-ttu-id="edf2c-143">Eliminare</span><span class="sxs-lookup"><span data-stu-id="edf2c-143">Delete</span></span>
- <span data-ttu-id="edf2c-p106">**Disposizione** identifica cosa succederà al contenuto alla fine del periodo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="edf2c-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="edf2c-146">null</span><span class="sxs-lookup"><span data-stu-id="edf2c-146">null</span></span>
    - <span data-ttu-id="edf2c-147">Nessuna azione</span><span class="sxs-lookup"><span data-stu-id="edf2c-147">No action</span></span>
    - <span data-ttu-id="edf2c-148">Eliminazione automatica</span><span class="sxs-lookup"><span data-stu-id="edf2c-148">Auto-delete</span></span>
    - <span data-ttu-id="edf2c-149">Revisione obbligatoria (ovvero revisione della disposizione)</span><span class="sxs-lookup"><span data-stu-id="edf2c-149">Review required (aka Disposition review)</span></span>

![Impostazioni delle etichette nel piano file](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="edf2c-151">Colonne dei descrittori del piano file delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="edf2c-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="edf2c-p107">È ora possibile includere altre informazioni nella configurazione delle etichette di conservazione. L’inserimento di descrittori del piano file nelle etichette di conservazione migliora la gestibilità e l'organizzazione del piano file.</span><span class="sxs-lookup"><span data-stu-id="edf2c-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="edf2c-p108">Per iniziare, la gestione del piano file fornisce alcuni valori predefiniti per: funzione/reparto, categoria, tipo di autorità e disposizione/citazione. È possibile aggiungere nuovi valori al descrittore del piano file quando si crea o si modifica un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="edf2c-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="edf2c-156">Ecco una visualizzazione del passaggio dei descrittori del piano file quando si crea o modifica un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="edf2c-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Descrittori del piano file](media/file-plan-descriptors.png)

<span data-ttu-id="edf2c-158">Ecco una visualizzazione delle colonne dei descrittori del piano file nella scheda etichette della gestione del piano file.</span><span class="sxs-lookup"><span data-stu-id="edf2c-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="edf2c-160">Esportare tutte le etichette di conservazione esistenti per analizzare e/o eseguire le revisioni offline</span><span class="sxs-lookup"><span data-stu-id="edf2c-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="edf2c-161">Dalla gestione del piano file, è possibile esportare i dettagli di tutte le etichette di conservazione in un file CSV per agevolare le analisi di conformità periodiche con le parti interessate responsabili della governance dei dati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="edf2c-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="edf2c-162">Per esportare tutte le etichette di conservazione, passare a **gestione del piano file** \> **azioni del piano file** \> **esporta etichette**.</span><span class="sxs-lookup"><span data-stu-id="edf2c-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Opzione per esportare il piano file](media/file-plan-export-labels-option.png)

<span data-ttu-id="edf2c-164">Verrà aperto un file CSV che contiene tutte le etichette di conservazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="edf2c-164">A \*.csv file containing all existing retention labels will open.</span></span>

![File CSV con tutte le etichette di conservazione](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="edf2c-166">Importare le etichette di conservazione nel piano file</span><span class="sxs-lookup"><span data-stu-id="edf2c-166">Import labels into your file plan</span></span>

<span data-ttu-id="edf2c-167">Dalla gestione del piano file, è possibile importare in blocco nuove etichette di conservazione nonché modificare le etichette di conservazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="edf2c-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="edf2c-168">Per importare nuove etichette di conservazione e aggiornare le etichette di conservazione esistenti, passare a **gestione del piano file** \> **azioni del piano file** \> **importa etichette**.</span><span class="sxs-lookup"><span data-stu-id="edf2c-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Opzione per importare il piano file](media/file-plan-import-labels-option.png)

![Opzione per scaricare un modello di piano file vuoto](media/file-plan-blank-template-option.png)

<span data-ttu-id="edf2c-171">Scaricare un modello vuoto (o creare a partire da un'esportazione del piano file corrente).</span><span class="sxs-lookup"><span data-stu-id="edf2c-171">Download a blank template (or start from an export of your current file plan).</span></span>

![Modello di piano file vuoto aperto in Excel](media/file-plan-blank-template.png)

<span data-ttu-id="edf2c-173">Compilare il modello (presto disponibile: informazioni di riferimento sulle combinazioni di valori validi per una singola etichetta di conservazione).</span><span class="sxs-lookup"><span data-stu-id="edf2c-173">Fill-out the template (coming soon: reference information about valid value combinations for a single retention label).</span></span>

![Modello del piano file compilato con le informazioni](media/file-plan-filled-out-template.png)

<span data-ttu-id="edf2c-175">Caricare il modello compilato e la gestione del piano file convaliderà le voci e visualizzerà le statistiche di importazione.</span><span class="sxs-lookup"><span data-stu-id="edf2c-175">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Statistiche di importazione del piano file](media/file-plan-import-statistics.png)

<span data-ttu-id="edf2c-177">Se è presente un errore di convalida, l'importazione del piano file continuerà a convalidare ogni voce nel file di importazione e visualizzerà tutti gli errori che fanno riferimento a numeri di linea o riga nel file di importazione, copierà i risultati degli errori visualizzati in modo che sia possibile facilmente tornare al file di importazione e correggere gli errori.</span><span class="sxs-lookup"><span data-stu-id="edf2c-177">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="edf2c-178">Al termine dell'importazione, tornare alla gestione del piano file per associare le nuove etichette di conservazione ai criteri nuovi o esistenti delle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="edf2c-178">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Opzione per pubblicare le etichette](media/file-plan-publish-labels-option.png)

