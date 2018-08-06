---
title: Creazione di rapporti e traccia dei messaggi in Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft (EOP) Exchange Online Protection offre diversi rapporti che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità. Nella tabella seguente vengono descritti i report e gli strumenti per la risoluzione dei problemi disponibili per gli amministratori di EOP.
ms.openlocfilehash: 01a09b2b4b72161352af3793686c6cc888e44e29
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027143"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="27e11-105">Creazione di rapporti e traccia dei messaggi in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="27e11-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="27e11-p102">Microsoft Exchange Online Protection (EOP) sono disponibili numerose diversi report che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti che consentono di risoluzione dei problemi relativi ad eventi specifici (ad esempio un messaggio in arrivo non per il destinatario) e rapporti di controllo per semplificare lo con i requisiti di conformità.</span><span class="sxs-lookup"><span data-stu-id="27e11-p102">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization. There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span> 

## <a name="usage-reports"></a><span data-ttu-id="27e11-108">Report sull'uso</span><span class="sxs-lookup"><span data-stu-id="27e11-108">Usage reports</span></span>

<span data-ttu-id="27e11-109">**Attività di Gruppi di Office 365** Consente di visualizzare informazioni sul numero di Gruppi di Office 365 creati e utilizzati.</span><span class="sxs-lookup"><span data-stu-id="27e11-109">**Office 365 groups activity** View information about the number of Office 365 groups that are created and used.</span></span>  

<span data-ttu-id="27e11-110">**Attività di posta elettronica** Consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="27e11-110">**Email activity** View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>  

<span data-ttu-id="27e11-p103">**Utilizzo di app di posta elettronica** Consente di visualizzare informazioni sulle app di posta elettronica utilizzati. Ciò include il numero totale di connessioni delle applicazioni e le versioni di Outlook che si connettono.</span><span class="sxs-lookup"><span data-stu-id="27e11-p103">**Email app usage** View information about the email apps that are used. This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>  

<span data-ttu-id="27e11-113">**Utilizzo delle cassette postali** Consente di visualizzare informazioni sull'archiviazione usata, sul consumo di quota, sul numero di elementi e sull'ultima attività (invio o lettura) per le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="27e11-113">**Mailbox usage** View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="27e11-114">Vedere le risorse seguenti per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="27e11-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="27e11-115">Rapporti di Office 365 nell'interfaccia di amministrazione - gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="27e11-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [<span data-ttu-id="27e11-116">Report di Office 365 nell'interfaccia di amministrazione - Attività di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="27e11-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [<span data-ttu-id="27e11-117">Report di Office 365 nell'interfaccia di amministrazione - Utilizzo delle applicazioni di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="27e11-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [<span data-ttu-id="27e11-118">Report di Office 365 nell'interfaccia di amministrazione - Utilizzo delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="27e11-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a><span data-ttu-id="27e11-119">Protezione &amp; conformità rapporti nell'interfaccia di amministrazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="27e11-119">Security &amp; compliance reports in the Office 365 admin center</span></span>

<span data-ttu-id="27e11-120">Questi rapporti avanzati offrono un'esperienza di creazione di rapporti interattiva per gli amministratori EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="27e11-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>  

<span data-ttu-id="27e11-121">**Protezione avanzata dalle minacce (ATP, Advanced Threat Protection)** Consente di visualizzare informazioni sui collegamenti sicuri e sugli allegati sicuri che fanno parte di ATP.</span><span class="sxs-lookup"><span data-stu-id="27e11-121">**Advanced Threat Protection (ATP)** View information about safe links and safe attachments that are part of ATP.</span></span>  

<span data-ttu-id="27e11-122">**EOP** Visualizzare informazioni sui rilevamenti di malware, posta spoofing, i rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="27e11-122">**EOP** View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>  

[<span data-ttu-id="27e11-123">Visualizzare i report per la protezione di rischio avanzate ed Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="27e11-123">View reports for Advanced Threat Protection and Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="27e11-124">Rapporti personalizzati tramite Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="27e11-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="27e11-125">Creare a livello di programmazione report in cui sono disponibili nell'interfaccia di amministrazione di Office 365 utilizzando Microsoft Graph, vedere gli argomenti di [utilizzo dei report di utilizzo di Office 365 in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span><span class="sxs-lookup"><span data-stu-id="27e11-125">Programmatically create reports that are available in the Office 365 admin center by using Microsoft Graph  See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span></span> 

##<a name="custom-reports-using-reporting-web-services"></a><span data-ttu-id="27e11-126">Rapporti personalizzati tramite servizi Web Reporting</span><span class="sxs-lookup"><span data-stu-id="27e11-126">Custom reports using reporting web services</span></span>

<span data-ttu-id="27e11-127">Creare a livello di programmazione report da disponibili Exchange Online Protection PowerShell cmdlet di segnalazione tramite REST/ODATA2 filtro di query.</span><span class="sxs-lookup"><span data-stu-id="27e11-127">Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.</span></span>

<span data-ttu-id="27e11-128">Vedere [Web di Office 365 Reporting Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span><span class="sxs-lookup"><span data-stu-id="27e11-128">See [Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span></span> 

##<a name="message-trace"></a><span data-ttu-id="27e11-129">Traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="27e11-129">Message trace</span></span>

<span data-ttu-id="27e11-p104">Segue della posta elettronica messaggi quando passano attraverso EOP. È possibile determinare se un messaggio di posta elettronica è stato ricevuto, rifiutato, rinviato o distribuito tramite il servizio. Viene inoltre le azioni eseguite nel messaggio prima che raggiunto il relativo stato finale.</span><span class="sxs-lookup"><span data-stu-id="27e11-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>  

<span data-ttu-id="27e11-133">È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.</span><span class="sxs-lookup"><span data-stu-id="27e11-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>  

<span data-ttu-id="27e11-134">Vedere [traccia di un messaggio di posta elettronica](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span><span class="sxs-lookup"><span data-stu-id="27e11-134">See [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span></span> 

## <a name="audit-logging"></a><span data-ttu-id="27e11-135">Registrazione di controllo</span><span class="sxs-lookup"><span data-stu-id="27e11-135">Audit logging</span></span>

<span data-ttu-id="27e11-p105">Tiene traccia delle specifiche delle modifiche apportate dagli amministratori dell'organizzazione. Questi rapporti consentono di risolvere i problemi di configurazione o trovare la causa di problemi relativi alla conformità o sicurezza.  vedere [rapporti di controllo in EOP](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="27e11-p105">Tracks specific changes made by admins to your organization. These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.  see [Auditing reports in EOP](auditing-reports-in-eop.md)</span></span> 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="27e11-139">Rapporti e latenza e disponibilità dei dati dei messaggi</span><span class="sxs-lookup"><span data-stu-id="27e11-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="27e11-140">La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.</span><span class="sxs-lookup"><span data-stu-id="27e11-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="27e11-141">**Tipo di rapporto**</span><span class="sxs-lookup"><span data-stu-id="27e11-141">**Report type**</span></span> <br/> |<span data-ttu-id="27e11-142">**Dati disponibili per (periodo passato)**</span><span class="sxs-lookup"><span data-stu-id="27e11-142">**Data available for (look back period)**</span></span> <br/> |<span data-ttu-id="27e11-143">**Latenza**</span><span class="sxs-lookup"><span data-stu-id="27e11-143">**Latency**</span></span> <br/> |
|<span data-ttu-id="27e11-144">Rapporti di riepilogo di protezione della posta</span><span class="sxs-lookup"><span data-stu-id="27e11-144">Mail protection summary reports</span></span>  <br/> |<span data-ttu-id="27e11-145">90 giorni</span><span class="sxs-lookup"><span data-stu-id="27e11-145">90 days</span></span>  <br/> |<span data-ttu-id="27e11-p106">L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="27e11-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>  <br/> |
|<span data-ttu-id="27e11-148">Rapporti dettagliati di protezione della posta</span><span class="sxs-lookup"><span data-stu-id="27e11-148">Mail protection detail reports</span></span>  <br/> |<span data-ttu-id="27e11-149">90 giorni</span><span class="sxs-lookup"><span data-stu-id="27e11-149">90 days</span></span>  <br/> |<span data-ttu-id="27e11-p107">Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="27e11-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span>  <br/> <span data-ttu-id="27e11-152">Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="27e11-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
|<span data-ttu-id="27e11-153">Dati di traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="27e11-153">Message trace data</span></span>  <br/> |<span data-ttu-id="27e11-154">90 giorni</span><span class="sxs-lookup"><span data-stu-id="27e11-154">90 days</span></span>  <br/> |<span data-ttu-id="27e11-155">Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="27e11-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span>  <br/> <span data-ttu-id="27e11-156">Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="27e11-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="27e11-157">La latenza e la disponibilità dei dati è la stessa a prescindere che la richiesta venga effettuata tramite interfaccia di amministrazione di Office 365 o PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="27e11-157">Data availability and latency is the same whether requested via the Office 365 admin center or remote PowerShell.</span></span> 
  

