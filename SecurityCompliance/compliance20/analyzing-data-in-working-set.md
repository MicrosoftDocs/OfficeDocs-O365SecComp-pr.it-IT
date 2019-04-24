---
title: Analizzare i dati in un working set in Advanced eDiscovery (Preview)
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
ms.openlocfilehash: e3f3e863423fe4312a944eb6f04a58182e11665c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243237"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="171e4-102">Analizzare i dati in un working set in Advanced eDiscovery (Preview)</span><span class="sxs-lookup"><span data-stu-id="171e4-102">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="171e4-103">Quando il numero di documenti raccolti è di grandi dimensioni, può essere molto difficile rivederli tutti.</span><span class="sxs-lookup"><span data-stu-id="171e4-103">When the number of collected documents is large, it can be quite difficult to review them all.</span></span> <span data-ttu-id="171e4-104">Advanced eDiscovery (Preview) fornisce una serie di strumenti per analizzare i documenti per ridurre il volume dei documenti da rivedere senza perdite di informazioni e per facilitare l'organizzazione dei documenti in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="171e4-104">Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="171e4-105">Per ulteriori informazioni su queste funzionalità, vedere:</span><span class="sxs-lookup"><span data-stu-id="171e4-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="171e4-106">Rilevamento dei documenti simili</span><span class="sxs-lookup"><span data-stu-id="171e4-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="171e4-107">Threading posta elettronica</span><span class="sxs-lookup"><span data-stu-id="171e4-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="171e4-108">Temi</span><span class="sxs-lookup"><span data-stu-id="171e4-108">Themes</span></span>](themes.md)

<span data-ttu-id="171e4-109">Per analizzare i dati in un working set:</span><span class="sxs-lookup"><span data-stu-id="171e4-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="171e4-110">Configurare le impostazioni di analisi per il caso.</span><span class="sxs-lookup"><span data-stu-id="171e4-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="171e4-111">Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="171e4-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="171e4-112">Aprire il working set che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="171e4-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="171e4-113">Andare a "Gestisci working set".</span><span class="sxs-lookup"><span data-stu-id="171e4-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="171e4-114">Fare clic su "analyze".</span><span class="sxs-lookup"><span data-stu-id="171e4-114">Click "Analyze".</span></span>

<span data-ttu-id="171e4-115">È possibile controllare lo stato di avanzamento dell'analisi nella scheda processi del caso.</span><span class="sxs-lookup"><span data-stu-id="171e4-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="171e4-116">Dopo aver completato l'analisi, è possibile visualizzare il report di analisi, eseguire query all'interno del working set su output dell'analisi (per ulteriori informazioni, vedere [query all'interno del working set](working-set-search.md)) e vedere documenti correlati di un documento specifico (per ulteriori informazioni, vedere [ Revisione dei dati in working set](reviewing-data-in-working-set.md)).</span><span class="sxs-lookup"><span data-stu-id="171e4-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="171e4-117">Report di analisi</span><span class="sxs-lookup"><span data-stu-id="171e4-117">Analytics report</span></span>

<span data-ttu-id="171e4-118">Per visualizzare un report di analisi per il working set:</span><span class="sxs-lookup"><span data-stu-id="171e4-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="171e4-119">Aprire il working set.</span><span class="sxs-lookup"><span data-stu-id="171e4-119">Open your working set.</span></span>
2. <span data-ttu-id="171e4-120">Andare a "Gestisci working set".</span><span class="sxs-lookup"><span data-stu-id="171e4-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="171e4-121">Fare clic su "report".</span><span class="sxs-lookup"><span data-stu-id="171e4-121">Click "Report".</span></span>

<span data-ttu-id="171e4-122">Il report ha quattro componenti dall'analisi:</span><span class="sxs-lookup"><span data-stu-id="171e4-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="171e4-123">**Breakdown** : numero di messaggi di posta elettronica, allegati e documenti sciolti presenti nel working set.</span><span class="sxs-lookup"><span data-stu-id="171e4-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="171e4-124">**Documenti (esclusi gli allegati)** -quanti documenti sfusi sono stati pivot, unici in prossimità di duplicati di un pivot o duplicati esatti di un altro documento.</span><span class="sxs-lookup"><span data-stu-id="171e4-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="171e4-125">**Messaggi** di posta elettronica-numero di messaggi di posta elettronica inclusi, copie inclusive, svantaggi inclusi o nessuno di questi.</span><span class="sxs-lookup"><span data-stu-id="171e4-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="171e4-126">**Allegati** : quanti allegati di posta elettronica sono stati univoci o duplicati di un allegato di posta elettronica diverso all'interno del working set.</span><span class="sxs-lookup"><span data-stu-id="171e4-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>