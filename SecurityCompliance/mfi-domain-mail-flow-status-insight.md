---
title: Informazioni sullo stato del flusso di posta principale del dominio
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono ottenere informazioni sulla panoramica dello stato del flusso di posta di dominio principale nel dashboard del flusso di posta nel centro sicurezza & Compliance.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: baa69c3373623d4742d6d957a5022012fb60f7e7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32267037"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="ea8f1-103">Informazioni sullo stato del flusso di posta principale del dominio</span><span class="sxs-lookup"><span data-stu-id="ea8f1-103">Top domain mail flow status insight</span></span>

> [!NOTE]
> <span data-ttu-id="ea8f1-104">Le funzionalità descritte in questo argomento non sono state distribuite in tutte le organizzazioni di Office 365 e sono soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="ea8f1-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="ea8f1-105">L'Insight **sullo stato del flusso di posta di dominio principale** offre lo stato corrente dei domini dell'organizzazione in termini di flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="ea8f1-105">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="ea8f1-106">Questo Insight consente di identificare e risolvere i problemi relativi ai domini che si verificano problemi di ***flusso di posta*** (ad esempio, non è possibile ricevere messaggi di posta elettronica esterni), in particolare le scadenze o i domini di dominio con record MX non corretti.</span><span class="sxs-lookup"><span data-stu-id="ea8f1-106">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Informazioni sullo stato del flusso di dominio superiore nel dashboard del flusso di posta nel centro sicurezza & Compliance](media/domain-mail-flow-status-selected.png)

<span data-ttu-id="ea8f1-108">Quando si fa clic su **Visualizza dettagli** nell'Insight, viene visualizzato un riquadro a comparsa per visualizzare ulteriori dettagli sullo stato di ciascun dominio.</span><span class="sxs-lookup"><span data-stu-id="ea8f1-108">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="ea8f1-109">Un segno di spunta verde per un dominio indica che il record MX corrente (quando si è visualizzato il dashboard per la visualizzazione del flusso di posta) corrisponde al valore che abbiamo registrato e che il dominio ha ricevuto la posta elettronica nelle ultime due ore.</span><span class="sxs-lookup"><span data-stu-id="ea8f1-109">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="ea8f1-110">Una x rossa per un dominio indica che il record MX è stato modificato e che il dominio non ha ricevuto messaggi di posta elettronica nelle ultime 6 ore.</span><span class="sxs-lookup"><span data-stu-id="ea8f1-110">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="ea8f1-111">Questo indica probabilmente che il dominio è scaduto o che il record MX è stato aggiornato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="ea8f1-111">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="ea8f1-112">Verificare con il registrar o con il servizio di hosting DNS se il dominio è scaduto o se il record MX del dominio non è corretto.</span><span class="sxs-lookup"><span data-stu-id="ea8f1-112">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![Il riquadro a comparsa dettagli nell'Insight sullo stato del flusso di dominio superiore](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="ea8f1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea8f1-114">See also</span></span>

<span data-ttu-id="ea8f1-115">Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security _AMP_ Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="ea8f1-115">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
