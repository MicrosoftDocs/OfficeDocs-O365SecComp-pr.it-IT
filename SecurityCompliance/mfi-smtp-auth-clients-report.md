---
title: Report dei client auth SMTP
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono ottenere informazioni sul rapporto client auth SMTP nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b6698345a89edf52e4ee14cea144cb88ff080583
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252560"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="f7cd9-103">Report dei client auth SMTP</span><span class="sxs-lookup"><span data-stu-id="f7cd9-103">SMTP Auth clients report</span></span>

> [!NOTE]
> <span data-ttu-id="f7cd9-104">Le funzionalità descritte in questo argomento non sono state distribuite in tutte le organizzazioni di Office 365 e sono soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="f7cd9-105">Il rapporto **client auth SMTP** evidenzia l'utilizzo del protocollo di invio client auth SMTP da parte degli utenti o degli account di sistema nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-105">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="f7cd9-106">Questo protocollo legacy (che utilizza l'endpoint smtp.office365.com) offre solo l'autenticazione di base ed è suscettibile di essere utilizzato dagli account compromessi per inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-106">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="f7cd9-107">Questo rapporto consente di verificare la possibilità di attività inusuali.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-107">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="f7cd9-108">Vengono inoltre visualizzati i dati di utilizzo di TLS per client o dispositivi che utilizzano l'autenticazione SMTP.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-108">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="f7cd9-109">Il widget visualizzato nel dashboard del flusso di posta indica il numero di utenti o di account di servizio che hanno utilizzato il protocollo di autenticazione SMTP negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-109">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Report dei client auth SMTP nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="f7cd9-111">Se si fa clic sul widget, verrà aperto un riquadro a comparsa che fornisce una visualizzazione aggregata dell'utilizzo e dei volumi TLS per l'ultima settimana.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-111">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Il riquadro a comparsa nel rapporto client auth SMTP](media/smtp-auth-clients-flyout.png)

<span data-ttu-id="f7cd9-113">Quando si fa clic sul collegamento del **rapporto client auth SMTP** , vengono visualizzati due pivot di dati principali e due visualizzazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-113">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="f7cd9-114">I pivot di dati sono il **volume di invio** e l' **utilizzo di TLS**.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-114">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="f7cd9-115">Le visualizzazioni dati sono il grafico e la tabella details.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-115">The data views are the chart and the details table.</span></span>

<span data-ttu-id="f7cd9-116">La visualizzazione **volume di invio** Mostra il numero di messaggi che sono stati inviati utilizzando l'autenticazione SMTP per l'intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-116">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="f7cd9-117">È possibile modificare l'intervallo facendo clic su **filtri**.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-117">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="f7cd9-118">Il grafico è organizzato dal dominio del mittente.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-118">The chart is organized by sender domain.</span></span> <span data-ttu-id="f7cd9-119">È possibile visualizzare i dati separati per ogni dominio selezionando il dominio nell'elenco a discesa **Mostra dati per** .</span><span class="sxs-lookup"><span data-stu-id="f7cd9-119">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![Invio di volume nel rapporto client auth SMTP](media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="f7cd9-121">È possibile visualizzare informazioni dettagliate sui mittenti e sui relativi conteggi dei messaggi facendo clic su **Visualizza tabella dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-121">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="f7cd9-122">Per tornare al grafico, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-122">To return to the chart, click **View report**.</span></span>

![Tabella dei dettagli per l'invio del volume nel rapporto client auth SMTP](media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="f7cd9-124">Il pivot **utilizzo TLS** è importante a causa dell'imminente deprecazione di TLS 1.0 e TLS 1.1 in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-124">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="f7cd9-125">Molti dispositivi e applicazioni legacy non saranno in grado di inviare messaggi di posta elettronica se sono in grado di utilizzare solo TLS 1.0 con l'autenticazione SMTP. In questo pivot è possibile identificare ed eseguire azioni su utenti e account di sistema che continuano a utilizzare versioni precedenti di TLS.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-125">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![Utilizzo di TLS nel rapporto client auth SMTP](media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="f7cd9-127">È possibile visualizzare informazioni dettagliate sui mittenti, sulle versioni di TLS che utilizzano con l'autenticazione SMTP e sui conteggi dei messaggi facendo clic su **Visualizza tabella dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-127">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="f7cd9-128">Per tornare al grafico, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-128">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="f7cd9-129">È inoltre possibile scaricare una versione più dettagliata del rapporto facendo clic su Richiedi report.</span><span class="sxs-lookup"><span data-stu-id="f7cd9-129">You can also download a more detailed version of the report by clicking Request report.</span></span>

![Tabella dei dettagli per l'utilizzo di TLS nel rapporto client auth SMTP](media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a><span data-ttu-id="f7cd9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7cd9-131">See also</span></span>

<span data-ttu-id="f7cd9-132">Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security _AMP_ Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="f7cd9-132">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
