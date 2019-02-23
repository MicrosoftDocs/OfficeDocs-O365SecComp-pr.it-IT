---
title: Panoramica della gestione del piano file
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: La gestione del piano file fornisce funzionalità avanzate per la gestione di criteri ed etichette di conservazione e consente di attraversare in modo integrato le attività con etichette ed etichetta-a-contenuto per l’intero ciclo di vita del contenuto, dalla creazione alla collaborazione, passando per la dichiarazione del record e la conservazione, all’eliminazione finale.
ms.openlocfilehash: 792729d55f7096114694a59d7202b36fc130e48c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221186"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="73484-103">Panoramica della gestione del piano file</span><span class="sxs-lookup"><span data-stu-id="73484-103">Overview of file plan manager</span></span>

<span data-ttu-id="73484-104">La gestione del piano file fornisce funzionalità avanzate per la gestione di criteri ed etichette di conservazione e consente di attraversare in modo integrato le attività con etichette ed etichetta-a-contenuto per l’intero ciclo di vita del contenuto, dalla creazione alla collaborazione, passando per la dichiarazione del record e la conservazione, all’eliminazione finale.</span><span class="sxs-lookup"><span data-stu-id="73484-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Pagina del piano file](media/file-plan-page.png)

## <a name="important-this-feature-is-currently-available-only-as-part-of-the-office-365-preview-program"></a><span data-ttu-id="73484-106">Importante: questa funzionalità è attualmente disponibile solo come parte del programma Office 365 Preview</span><span class="sxs-lookup"><span data-stu-id="73484-106">Important: This feature is currently available only as part of the Office 365 Preview program</span></span>

<span data-ttu-id="73484-107">Questa caratteristica sarà disponibile nel tenant solo se l'organizzazione è iscritta al programma Office 365 Preview.</span><span class="sxs-lookup"><span data-stu-id="73484-107">You will see this feature in your tenant only if your organization has enrolled in the Office 365 Preview program.</span></span>

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="73484-108">Accesso alla gestione del piano file</span><span class="sxs-lookup"><span data-stu-id="73484-108">Accessing file plan manager</span></span>

<span data-ttu-id="73484-109">I requisiti per accedere al piano file sono due:</span><span class="sxs-lookup"><span data-stu-id="73484-109">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="73484-110">Un abbonamento a Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="73484-110">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="73484-111">L’utente dispone di uno dei ruoli seguenti nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="73484-111">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span> 
    - <span data-ttu-id="73484-112">Responsabile della conservazione</span><span class="sxs-lookup"><span data-stu-id="73484-112">Retention Manager</span></span>
    - <span data-ttu-id="73484-113">Responsabile della conservazione solo visualizzazione</span><span class="sxs-lookup"><span data-stu-id="73484-113">View-only Retention Manager</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="73484-114">Esplorare il piano file</span><span class="sxs-lookup"><span data-stu-id="73484-114">Navigating your file plan</span></span>

<span data-ttu-id="73484-115">La gestione del piano file semplifica la visualizzazione unica delle impostazioni di tutti i criteri e le etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="73484-115">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="73484-116">Si noti che le etichette di conservazione create all'esterno del piano file saranno disponibili nel piano file e viceversa.</span><span class="sxs-lookup"><span data-stu-id="73484-116">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="73484-117">Nella tabella **etichette piano file** sono disponibili le seguenti informazioni e funzionalità aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="73484-117">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="73484-118">Colonne impostazioni etichetta</span><span class="sxs-lookup"><span data-stu-id="73484-118">Label settings columns</span></span>
 
- <span data-ttu-id="73484-p101">**In base a** identifica il tipo di trigger che avvierà il periodo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="73484-p101">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="73484-121">Evento</span><span class="sxs-lookup"><span data-stu-id="73484-121">Event</span></span>
    - <span data-ttu-id="73484-122">Momento della creazione</span><span class="sxs-lookup"><span data-stu-id="73484-122">When created</span></span>
    - <span data-ttu-id="73484-123">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="73484-123">When last modified</span></span>
    - <span data-ttu-id="73484-124">Data etichettatura</span><span class="sxs-lookup"><span data-stu-id="73484-124">When labeled</span></span>
- <span data-ttu-id="73484-p102">**Record** indica se l'elemento diventa un record dichiarato dopo l'applicazione dell'etichetta. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="73484-p102">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="73484-127">No</span><span class="sxs-lookup"><span data-stu-id="73484-127">No</span></span>
    - <span data-ttu-id="73484-128">Sì</span><span class="sxs-lookup"><span data-stu-id="73484-128">Yes</span></span>
    - <span data-ttu-id="73484-129">Sì (normativo)</span><span class="sxs-lookup"><span data-stu-id="73484-129">Yes(Regulatory)</span></span>
- <span data-ttu-id="73484-p103">**Conservazione** identifica il tipo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="73484-p103">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="73484-132">Conservare</span><span class="sxs-lookup"><span data-stu-id="73484-132">Keep</span></span>
    - <span data-ttu-id="73484-133">Conservare ed eliminare</span><span class="sxs-lookup"><span data-stu-id="73484-133">Keep and delete</span></span>
    - <span data-ttu-id="73484-134">Eliminare</span><span class="sxs-lookup"><span data-stu-id="73484-134">Delete</span></span>
- <span data-ttu-id="73484-p104">**Disposizione** identifica cosa succederà al contenuto alla fine del periodo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="73484-p104">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="73484-137">null</span><span class="sxs-lookup"><span data-stu-id="73484-137">null</span></span>
    - <span data-ttu-id="73484-138">Nessuna azione</span><span class="sxs-lookup"><span data-stu-id="73484-138">No action</span></span>
    - <span data-ttu-id="73484-139">Eliminazione automatica</span><span class="sxs-lookup"><span data-stu-id="73484-139">Auto-delete</span></span>
    - <span data-ttu-id="73484-140">Revisione obbligatoria (ovvero revisione della disposizione)</span><span class="sxs-lookup"><span data-stu-id="73484-140">Review required (aka Disposition review)</span></span>

![Impostazioni delle etichette nel piano file](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="73484-142">Etichettare le colonne dei descrittori del piano file</span><span class="sxs-lookup"><span data-stu-id="73484-142">Label file plan descriptors columns</span></span>

<span data-ttu-id="73484-p105">È ora possibile includere altre informazioni nella configurazione delle etichette di conservazione. L’inserimento di descrittori del piano file nelle etichette migliora la gestibilità e l'organizzazione del piano file.</span><span class="sxs-lookup"><span data-stu-id="73484-p105">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="73484-p106">Per iniziare, la gestione del piano file fornisce alcuni valori predefiniti per: funzione/reparto, categoria, tipo di autorità e disposizione/citazione. È possibile aggiungere nuovi valori al descrittore del piano file quando si crea o si modifica un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="73484-p106">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="73484-147">Ecco una visualizzazione del passaggio dei descrittori del piano file quando si crea o modifica un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="73484-147">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Descrittori del piano file](media/file-plan-descriptors.png)

<span data-ttu-id="73484-149">Ecco una visualizzazione delle colonne dei descrittori del piano file nella scheda etichette della gestione del piano file.</span><span class="sxs-lookup"><span data-stu-id="73484-149">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="73484-151">Esportare le etichette dal piano file</span><span class="sxs-lookup"><span data-stu-id="73484-151">Export labels out of your file plan</span></span>

<span data-ttu-id="73484-152">Dalla gestione del piano file, è possibile esportare i dettagli di tutte le etichette di conservazione in un file CSV per agevolare le analisi di conformità periodiche con le parti interessate responsabili della governance dei dati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="73484-152">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="73484-153">Per esportare tutte le etichette di conservazione, passare a **gestione del piano file** \> **azioni del piano file** \> **esporta etichette**.</span><span class="sxs-lookup"><span data-stu-id="73484-153">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Opzione per esportare il piano file](media/file-plan-export-labels-option.png)

<span data-ttu-id="73484-155">Verrà aperto un file CSV che contiene tutte le etichette di conservazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="73484-155">A \*.csv file containing all existing retention labels will open.</span></span>

![File CSV con tutte le etichette di conservazione](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="73484-157">Importare le etichette nel piano file</span><span class="sxs-lookup"><span data-stu-id="73484-157">Import labels into your file plan</span></span>

<span data-ttu-id="73484-158">Dalla gestione del piano file, è possibile importare in blocco nuove etichette nonché modificare le etichette di conservazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="73484-158">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="73484-159">Per importare nuove etichette di conservazione e aggiornare le etichette esistenti, passare a **gestione del piano file** \> **azioni del piano file** \> **importa etichette**.</span><span class="sxs-lookup"><span data-stu-id="73484-159">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Opzione per importare il piano file](media/file-plan-import-labels-option.png)

![Opzione per scaricare un modello di piano file vuoto](media/file-plan-blank-template-option.png)

<span data-ttu-id="73484-162">Scaricare un modello vuoto (o creare a partire da un'esportazione del piano file corrente).</span><span class="sxs-lookup"><span data-stu-id="73484-162">Download a blank template (or start from an export of your current file plan).</span></span>

![Modello di piano file vuoto aperto in Excel](media/file-plan-blank-template.png)

<span data-ttu-id="73484-164">Compilare il modello (presto disponibili le informazioni di riferimento sui valori validi per le voci).</span><span class="sxs-lookup"><span data-stu-id="73484-164">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![Modello del piano file compilato con le informazioni](media/file-plan-filled-out-template.png)

<span data-ttu-id="73484-166">Caricare il modello compilato e la gestione del piano file convaliderà le voci e visualizzerà le statistiche di importazione.</span><span class="sxs-lookup"><span data-stu-id="73484-166">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Statistiche di importazione del piano file](media/file-plan-import-statistics.png)

<span data-ttu-id="73484-168">Al termine dell'importazione, tornare alla gestione del piano file per assegnare nuove etichette ai criteri nuovi o esistenti.</span><span class="sxs-lookup"><span data-stu-id="73484-168">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Opzione per pubblicare le etichette](media/file-plan-publish-labels-option.png)

