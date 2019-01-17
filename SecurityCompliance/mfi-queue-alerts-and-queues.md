---
title: Gli avvisi di coda e le code
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Gli amministratori possono venire a conoscenza degli avvisi di coda e le code nel dashboard di flusso della posta in & la protezione di Office 365 centro conformità.
ms.openlocfilehash: fe750e32136af095bb0ccff8544306db76a7a667
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685501"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="11c85-103">Gli avvisi di coda e le code</span><span class="sxs-lookup"><span data-stu-id="11c85-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="11c85-104">Avvisi di coda</span><span class="sxs-lookup"><span data-stu-id="11c85-104">Queue alerts</span></span>

<span data-ttu-id="11c85-p101">Quando non è possibile inviare messaggi dall'organizzazione Office 365 per locale o server di posta elettronica partner utilizzando i connettori, i messaggi vengono accodati in Office 365. Esempi comuni che causano questa condizione sono:</span><span class="sxs-lookup"><span data-stu-id="11c85-p101">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365. Common examples that cause this condition are:</span></span>

- <span data-ttu-id="11c85-107">Il connettore è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="11c85-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="11c85-108">Sono state apportate modifiche di rete o del firewall nell'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="11c85-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="11c85-p102">Office 365 continuerà a tentativi di recapito per 48 ore. Dopo 48 ore, i messaggi scadranno e verranno restituiti ai mittenti nei rapporti di mancato recapito (noto anche come rapporti di mancato recapito o messaggi di rimbalzo).</span><span class="sxs-lookup"><span data-stu-id="11c85-p102">Office 365 will continue to retry to delivery for 48 hours. After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="11c85-p103">Se il volume di posta elettronica in coda supera la soglia predefinita (il valore predefinito è messaggi 2000), gli avvisi è disponibili nel dashboard di flusso della posta a **avvisi recenti**e gli amministratori riceverà una notifica tramite posta elettronica (per l'indirizzo di posta elettronica alternativi) . Per configurare la soglia di avviso, limite giornaliero notifica e/o i destinatari dell'avviso, vedere la sezione **avvisi coda Personalizza** riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="11c85-p103">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address). To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Avvisi di coda nell'area di avvisi recenti del dashboard di flusso della posta in & la protezione di Office 365 centro conformità](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="11c85-114">Personalizzare gli avvisi di coda</span><span class="sxs-lookup"><span data-stu-id="11c85-114">Customize queue alerts</span></span>

<span data-ttu-id="11c85-p104">Sui concetti del flusso di posta elettronica creare un criterio di avviso denominata **messaggi sono in ritardo** (la casella di controllo **Invia notifiche di posta elettronica** nella schermata riportato di seguito di sotto) trovato negli **avvisi** \> **Criteri di avviso**. È possibile modificare i destinatari della soglia e avviso facendo clic sul criterio.</span><span class="sxs-lookup"><span data-stu-id="11c85-p104">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**. You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Spostamento degli avvisi](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="11c85-118">Verrà visualizzato un nuovo blade informazioni criterio, è ora possibile fare clic su **Modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="11c85-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Criterio di modifica ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="11c85-p105">Blade informazioni verrà modificate in **Modifica criteri**. È ora possibile modificare i destinatari di avviso tramite posta elettronica, il limite al numero di notifiche inviate al giorno e la soglia minima per attivare l'avviso (200 o più).</span><span class="sxs-lookup"><span data-stu-id="11c85-p105">The information blade will change to the **Edit Policy**. You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Modificare criteri Blade](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="11c85-123">Dettagli dell'avviso coda</span><span class="sxs-lookup"><span data-stu-id="11c85-123">Queue alert details</span></span>

<span data-ttu-id="11c85-124">Quando si fa clic sull'avviso, in un riquadro comparsa vengono visualizzati i dettagli dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="11c85-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Selezionare un avviso relativo alla coda nell'area di avvisi recenti del dashboard di flusso della posta in & la protezione di Office 365 centro conformità](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![La coda avviso dettagli menu mobile & la protezione di Office 365 centro conformità](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="11c85-127">È possibile fare clic su **Visualizza coda** nei dettagli dell'avviso per visualizzare i dettagli della coda, problemi e collegamenti alle correzioni disponibili in un nuovo riquadro comparsa.</span><span class="sxs-lookup"><span data-stu-id="11c85-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![La coda avviso dettagli menu mobile & la protezione di Office 365 centro conformità](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Visualizza coda nei dettagli dell'avviso](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="11c85-130">Code</span><span class="sxs-lookup"><span data-stu-id="11c85-130">Queues</span></span>

<span data-ttu-id="11c85-p106">Anche se il volume di messaggi in coda non sia stata superata la soglia, è possibile utilizzare ancora l'area delle **code** del dashboard di flusso di posta elettronica per visualizzare i messaggi che sono stati accodati per più di un'ora. È possibile utilizzare l'area delle **code** per monitorare il numero di messaggi in coda (il valore 0 indica che il flusso della posta OK) ed eseguire azioni prima che il numero di messaggi in coda diventi troppo grande.</span><span class="sxs-lookup"><span data-stu-id="11c85-p106">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour. You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Code nel dashboard di flusso della posta in & la protezione di Office 365 centro conformità](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="11c85-134">Quando si sceglie il numero di messaggi nelle **code**, i dettagli di coda e istruzioni su come risolvere un problema saranno visualizzati in un riquadro tendina (tendina stesso visualizzata fare clic su **Visualizza coda** i dettagli di un avviso relativo alla coda).</span><span class="sxs-lookup"><span data-stu-id="11c85-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Dettagli coda](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)
