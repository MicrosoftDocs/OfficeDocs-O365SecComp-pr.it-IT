---
title: Approfondimenti sulle regole del flusso di posta lento
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: Gli amministratori possono ottenere informazioni sull'Insight delle regole del flusso di posta lenta nel dashboard del flusso di posta nel centro sicurezza & Compliance.
ms.openlocfilehash: ede12e14f287599cab0e5f39aaf71c38ed519276
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999779"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="9a9b8-103">Approfondimenti sulle regole del flusso di posta lento</span><span class="sxs-lookup"><span data-stu-id="9a9b8-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="9a9b8-104">Inefficienti regole del flusso di posta (note anche come regole di trasporto) possono causare ritardi del flusso di posta per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="9a9b8-105">Questo Insight segnala le regole del flusso di posta che hanno un impatto sul flusso di posta dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="9a9b8-106">Esempi di questi tipi di regole sono:</span><span class="sxs-lookup"><span data-stu-id="9a9b8-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="9a9b8-107">Le condizioni che utilizzano **sono membri di** per gruppi di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="9a9b8-108">Condizioni che utilizzano la corrispondenza del modello di espressione regolare (Regex) complessa.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="9a9b8-109">Condizioni che utilizzano il controllo del contenuto negli allegati.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="9a9b8-110">L'Insight consentirà di identificare e ottimizzare le regole del flusso di posta per contribuire a ridurre i ritardi del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Una panoramica delle regole del flusso di posta lenta nel dashboard del flusso di posta nel centro sicurezza & Compliance](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="9a9b8-112">Quando si fa clic su **Visualizza dettagli**, viene visualizzato un riquadro a comparsa dove è possibile esaminare la regola.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="9a9b8-113">Nel riquadro a comparsa, è anche possibile fare clic su **Visualizza messaggi di esempio** per visualizzare il tipo di messaggi interessati dalla regola.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![Riquadro a comparsa dopo aver fatto clic su Visualizza dettagli in una panoramica delle regole del flusso di posta lenta nel dashboard del flusso di posta](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="see-also"></a><span data-ttu-id="9a9b8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a9b8-115">See also</span></span>

<span data-ttu-id="9a9b8-116">Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security _AMP_ Compliance Center](mail-flow-insights.md).</span><span class="sxs-lookup"><span data-stu-id="9a9b8-116">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
