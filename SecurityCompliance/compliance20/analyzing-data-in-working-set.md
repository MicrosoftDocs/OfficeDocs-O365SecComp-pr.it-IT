---
title: Analizzare i dati in un working set di eDiscovery avanzate (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 68a8b7586700a9bffe78f2b3a4ff419a1f85ba8a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695142"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="feed8-102">Analizzare i dati in un working set di eDiscovery avanzate (Preview)</span><span class="sxs-lookup"><span data-stu-id="feed8-102">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="feed8-p101">Quando il numero di raccolti documenti di grandi dimensioni, può essere molto difficile esaminare tutte. EDiscovery avanzate (Preview) offre una serie di strumenti per analizzare i documenti in modo da ridurre il volume di documenti per la revisione senza perdita di informazioni e che consentono di organizzare i documenti in modo coerente. Per ulteriori informazioni su queste funzionalità, vedere:</span><span class="sxs-lookup"><span data-stu-id="feed8-p101">When the number of collected documents is large, it can be quite difficult to review them all. Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner. To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="feed8-106">Rilevamento dei documenti simili</span><span class="sxs-lookup"><span data-stu-id="feed8-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="feed8-107">Threading posta elettronica</span><span class="sxs-lookup"><span data-stu-id="feed8-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="feed8-108">Temi</span><span class="sxs-lookup"><span data-stu-id="feed8-108">Themes</span></span>](themes.md)

<span data-ttu-id="feed8-109">Per analizzare i dati in un gruppo di lavoro:</span><span class="sxs-lookup"><span data-stu-id="feed8-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="feed8-p102">Configurare le impostazioni di analitica per il case. Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analitica](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="feed8-p102">Configure analytics settings for your case. For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="feed8-112">Aprire il set di lavoro che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="feed8-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="feed8-113">Passare a "Gestisci working set".</span><span class="sxs-lookup"><span data-stu-id="feed8-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="feed8-114">Fare clic su "Analizzare".</span><span class="sxs-lookup"><span data-stu-id="feed8-114">Click "Analyze".</span></span>

<span data-ttu-id="feed8-115">È possibile controllare lo stato di avanzamento dell'analisi della scheda processi nel caso specifico.</span><span class="sxs-lookup"><span data-stu-id="feed8-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="feed8-116">Al termine dell'analisi, è possibile visualizzare report analitica, le query eseguite all'interno di lavoro è impostata su output dell'analisi (per ulteriori informazioni, vedere [Query all'interno del working set](working-set-search.md)) e visualizzare i documenti correlati di un determinato documento (per ulteriori informazioni, vedere [ Analisi dei dati nel working set](reviewing-data-in-working-set.md)).</span><span class="sxs-lookup"><span data-stu-id="feed8-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="feed8-117">Rapporto Analitica</span><span class="sxs-lookup"><span data-stu-id="feed8-117">Analytics report</span></span>

<span data-ttu-id="feed8-118">Per visualizzare un report analitica per set in uso:</span><span class="sxs-lookup"><span data-stu-id="feed8-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="feed8-119">Aprire il working set.</span><span class="sxs-lookup"><span data-stu-id="feed8-119">Open your working set.</span></span>
2. <span data-ttu-id="feed8-120">Passare a "Gestisci working set".</span><span class="sxs-lookup"><span data-stu-id="feed8-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="feed8-121">Fare clic su "Report".</span><span class="sxs-lookup"><span data-stu-id="feed8-121">Click "Report".</span></span>

<span data-ttu-id="feed8-122">Il report include quattro componenti di analisi:</span><span class="sxs-lookup"><span data-stu-id="feed8-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="feed8-123">**Suddivisione** - quanti messaggi di posta elettronica, gli allegati e documenti espansa sono state trovate nel set di lavoro.</span><span class="sxs-lookup"><span data-stu-id="feed8-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="feed8-124">**Documenti (escluso allegati)** - numero di documenti espansa sono stati pivot univoco quasi duplicati di rotazione o un duplicato esatto di un altro documento.</span><span class="sxs-lookup"><span data-stu-id="feed8-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="feed8-125">**Messaggi di posta elettronica** - quanti messaggi di posta elettronica sono state inclusives, inclusi copie, inclusi svantaggi o nessuna delle precedenti.</span><span class="sxs-lookup"><span data-stu-id="feed8-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="feed8-126">**Allegati** - quante gli allegati di posta elettronica sono state univoci o duplicati di un allegato di posta elettronica diverso all'interno del working set.</span><span class="sxs-lookup"><span data-stu-id="feed8-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>