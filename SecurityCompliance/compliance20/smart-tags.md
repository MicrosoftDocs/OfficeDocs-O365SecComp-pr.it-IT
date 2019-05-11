---
title: Configurare gli smart tag per il rilevamento dei privilegi avvocato-client in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 721426f23aec862bcefbd13b8e61415dac3aeb27
ms.sourcegitcommit: aa8ea45d5854f8906714e0a407937585ec7993ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2019
ms.locfileid: "33951701"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a><span data-ttu-id="85e87-102">Configurare gli smart tag per la revisione con supporto ML in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="85e87-102">Set up smart tags for ML-assisted review in Advanced eDiscovery</span></span>

<span data-ttu-id="85e87-103">Le funzionalità di apprendimento automatico in Advanced eDiscovery devono contribuire a rendere più efficienti i processi decisionali sui documenti.</span><span class="sxs-lookup"><span data-stu-id="85e87-103">Machine learning capabilities in Advanced eDiscovery are meant to help make decision process on documents more efficient.</span></span> <span data-ttu-id="85e87-104">Smart tag è un modo per portare le funzionalità di apprendimento automatico in cui vengono registrate le decisioni: Tag e gruppi di tag.</span><span class="sxs-lookup"><span data-stu-id="85e87-104">Smart tags is a way to bring the machine learning capabilities into where the decisions are recorded: tags and tag groups.</span></span> <span data-ttu-id="85e87-105">Quando si crea un gruppo di smart tag, le decisioni del modello ML mappate al gruppo verranno mostrate in linea con i tag del gruppo in modo da visualizzare le informazioni in linea, in cui sono contestualemente più sensate.</span><span class="sxs-lookup"><span data-stu-id="85e87-105">When you create a smart tag group, then the decisions of the ML model mapped to the group will be shown in-line with the tags in the group to help you see the information in-line, where they contextually make most sense.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="85e87-106">Come configurare un gruppo di smart tag</span><span class="sxs-lookup"><span data-stu-id="85e87-106">How to set up a smart tag group</span></span>

1. <span data-ttu-id="85e87-107">In un set di revisione, andare a **Manage Review set** -> **gestire i tag**.</span><span class="sxs-lookup"><span data-stu-id="85e87-107">In a review set, go to **Manage review set** -> **Manage tags**.</span></span>

2. <span data-ttu-id="85e87-108">Fare clic sul menu a discesa accanto a **Aggiungi tag gruppo** e selezionare **Aggiungi smart tag Group**.</span><span class="sxs-lookup"><span data-stu-id="85e87-108">Click on the drop-down next to **Add tag group** and select **Add smart tag group**.</span></span>

3. <span data-ttu-id="85e87-109">Selezionare il modello che si desidera mappare a questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="85e87-109">Select the model you want to map to this group.</span></span> <span data-ttu-id="85e87-110">Verrà creata una sezione Tag e N tag figlio, dove N è il numero di output possibili del modello.</span><span class="sxs-lookup"><span data-stu-id="85e87-110">This will create a tag section and N child tags, where N is the number of possible outputs of the model.</span></span> <span data-ttu-id="85e87-111">Ad esempio, il modello di rilevamento dei privilegi avvocato-client ha due possibili output-privilegiati e non privilegiati; Se si seleziona questo modello, verranno creati due tag figlio nel set di revisione, ognuno corrispondente a uno dei possibili output.</span><span class="sxs-lookup"><span data-stu-id="85e87-111">For instance, attorney-client privilege detection model has two possible outputs - privileged and not privileged; selecting this model will create two child tags in the review set, each corresponding to one of the possible outputs.</span></span>

4. <span data-ttu-id="85e87-112">Rinominare il gruppo di tag e i tag come si può vedere in forma.</span><span class="sxs-lookup"><span data-stu-id="85e87-112">Rename the tag group and tags as you see fit.</span></span>

## <a name="how-to-use-a-smart-tag-group"></a><span data-ttu-id="85e87-113">Come usare un gruppo di smart tag</span><span class="sxs-lookup"><span data-stu-id="85e87-113">How to use a smart tag group</span></span>

<span data-ttu-id="85e87-114">Quando si esamina un documento, i risultati del modello verranno esposti accanto al valore del tag appropriato.</span><span class="sxs-lookup"><span data-stu-id="85e87-114">When reviewing a document, the model's results will be exposed next to the appropriate tag value.</span></span> <span data-ttu-id="85e87-115">Ad esempio, se si dispone di un gruppo di smart tag per il rilevamento dei privilegi avvocato-client e si esamina un documento che il modello ha deciso è potenzialmente privilegiato, verrà visualizzato il motivo accanto al tag appropriato.</span><span class="sxs-lookup"><span data-stu-id="85e87-115">For instance, if you have a smart tag group for attorney-client privilege detection and you review a document that the model has decided is potentially privileged, you will see the reason for that next to the appropriate tag.</span></span> <span data-ttu-id="85e87-116">È importante tenere presente che il tag non viene applicato automaticamente. per tutti gli effetti, i tag all'interno di un gruppo di smart tag agiscono esattamente come i tag normali, tranne per il fatto che espongono i risultati del modello accanto a essi, se necessario.</span><span class="sxs-lookup"><span data-stu-id="85e87-116">It is important to note that the tag is not automatically applied; for all intents and purposes, tags within a smart tag group act just like normal tags, except that they expose the model results next to them when appropriate.</span></span>