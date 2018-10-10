---
title: Visualizzare i report per la protezione rischio avanzate di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: Informazioni su come trovare e utilizzare rapporti per Office 365 avanzate protezione da minacce per la protezione &amp; centro conformità.
ms.openlocfilehash: 4a76c6a5b888142dc4c35af432fa61916145d648
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454303"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="bd118-103">Visualizzare i report per la protezione rischio avanzate di Office 365</span><span class="sxs-lookup"><span data-stu-id="bd118-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="bd118-p101">Se l'organizzazione dispone di [Protezione di Office 365 avanzate rischio](office-365-atp.md) (degli strumenti di analisi) e si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile utilizzare diversi report degli strumenti di analisi della protezione &amp; centro conformità. (Accedere ai **rapporti** \> **Dashboard**.)</span><span class="sxs-lookup"><span data-stu-id="bd118-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![La sicurezza &amp; dashboard centro conformità risulta utile per determinare dove funzioni avanzate Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="bd118-p102">I report degli strumenti di analisi includono [relazione sullo stato di protezione rischio](#threat-protection-status-report), il [rapporto di tipi di File degli strumenti di analisi](#atp-file-types-report)e il [rapporto di disposizione degli strumenti di analisi del messaggio](#atp-message-disposition-report). In questo articolo vengono descritti i report degli strumenti di analisi e include collegamenti a [ulteriori report da visualizzare](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="bd118-p102">ATP reports include the [Threat protection status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report). This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="bd118-109">Relazione sullo stato di protezione rischio</span><span class="sxs-lookup"><span data-stu-id="bd118-109">Threat protection status report</span></span>

<span data-ttu-id="bd118-p103">La relazione **sullo stato di protezione di rischio** è una singola visualizzazione che combina informazioni dannoso contenuto dannoso posta elettronica e rilevato e bloccato da Exchange Online e protezione da minacce avanzate. Il rapporto fornisce un conteggio aggregato univoco dei messaggi di posta con contenuto dannoso (file o URL) bloccato il motore antimalware, [(ZAP) di eliminazione automatica zero ore](zero-hour-auto-purge.md)e caratteristiche di protezione da minacce avanzate, ad esempio [Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md), [degli strumenti di analisi Gli allegati sicuri](atp-safe-attachments.md)e le [funzionalità di protezione anti-phishing degli strumenti di analisi in Office 365](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="bd118-p103">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by Exchange Online and Advanced Threat Protection. The report provides an aggregated count of unique email messages with malicious content (files or URLs) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Advanced Threat Protection features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md).</span></span>
  
<span data-ttu-id="bd118-112">Per visualizzare il report di stato protezione rischio, in sicurezza &amp; centro conformità, passare a **report** \> **Dashboard** \> **lo stato di protezione di rischio**.</span><span class="sxs-lookup"><span data-stu-id="bd118-112">To view the Threat protection status report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat protection status**.</span></span>
  
![Relazione sullo stato di protezione rischio degli strumenti di analisi](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="bd118-114">Per ottenere informazioni dettagliate sullo stato di un giorno, al passaggio del mouse sopra il grafico.</span><span class="sxs-lookup"><span data-stu-id="bd118-114">To get detailed status for a day, hover over the graph.</span></span>
  
![Dati relativi allo stato di protezione rischio degli strumenti di analisi di un giorno](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="bd118-p104">Per impostazione predefinita, il rapporto di stato protezione rischio Mostra dati per gli ultimi sette giorni. Tuttavia, è possibile scegliere di **filtri** e modificare l'intervallo di date per visualizzare i dati per un massimo di 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="bd118-p104">By default, the Threat protection status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![Filtri di stato di protezione di rischio degli strumenti di analisi](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="bd118-119">È inoltre possibile utilizzare il menu di **visualizzare i dati da** per modificare le informazioni visualizzate nel report.</span><span class="sxs-lookup"><span data-stu-id="bd118-119">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Opzioni di visualizzazione per la relazione sullo stato di protezione rischio degli strumenti di analisi](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="bd118-121">Report di tipi di File degli strumenti di analisi</span><span class="sxs-lookup"><span data-stu-id="bd118-121">ATP File Types report</span></span>

<span data-ttu-id="bd118-122">Nel rapporto di **Tipi di File degli strumenti di analisi** viene visualizzato il tipo di file rilevato come dannoso per [Gli allegati sicuri degli strumenti di analisi](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="bd118-122">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="bd118-123">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Tipi di File degli strumenti di analisi**.</span><span class="sxs-lookup"><span data-stu-id="bd118-123">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Report di tipi di File degli strumenti di analisi](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="bd118-125">Quando si sposta su un giorno particolare, è possibile visualizzare la suddivisione dei tipi di file dannosi rilevati per [Gli allegati sicuri degli strumenti di analisi](atp-safe-attachments.md) e [anti-spam &amp; protezione anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="bd118-125">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Dati del report di tipi di File degli strumenti di analisi di un giorno](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="bd118-127">Report di disposizione degli strumenti di analisi del messaggio</span><span class="sxs-lookup"><span data-stu-id="bd118-127">ATP Message Disposition report</span></span>

<span data-ttu-id="bd118-128">Il rapporto di **Disposizione degli strumenti di analisi del messaggio** Mostra le azioni eseguite per i messaggi di posta elettronica che sono stati rilevati con contenuto dannoso.</span><span class="sxs-lookup"><span data-stu-id="bd118-128">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="bd118-129">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Disposizione degli strumenti di analisi del messaggio**.</span><span class="sxs-lookup"><span data-stu-id="bd118-129">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Rapporto di eliminazione degli strumenti di analisi messaggi](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="bd118-131">Quando passa il mouse su una barra nel grafico, è possibile visualizzare le azioni eseguite per la posta elettronica rilevato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="bd118-131">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Dati del Report di eliminazione degli strumenti di analisi messaggio per un giorno](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="bd118-133">Altri report per visualizzare</span><span class="sxs-lookup"><span data-stu-id="bd118-133">Additional reports to view</span></span>

<span data-ttu-id="bd118-p105">Oltre ai rapporti degli strumenti di analisi descritti in questo articolo, sono disponibili nel titolo [rapporti sulla protezione posta elettronica](view-email-security-reports.md) &amp; centro conformità. Rapporti sulla protezione posta elettronica includono un [rapporto di destinatari e mittenti principali](view-email-security-reports.md#top-senders-and-recipients-report), un [rapporto di spoofing posta](view-email-security-reports.md#spoof-mail-report), un [rapporto sui rilevamenti di posta indesiderata](view-email-security-reports.md#spam-detections-report)e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="bd118-p105">In addition to the ATP reports described in this article, [email security reports](view-email-security-reports.md) are available in the Security &amp; Compliance Center. Email security reports include a [Top Senders and Recipients report](view-email-security-reports.md#top-senders-and-recipients-report), a [Spoof Mail report](view-email-security-reports.md#spoof-mail-report), a [Spam Detections report](view-email-security-reports.md#spam-detections-report), and more.</span></span>
  
<span data-ttu-id="bd118-136">E, se l'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md), è anche possibile [utilizzare Esplora nella protezione &amp; centro conformità](use-explorer-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="bd118-136">And, if your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can also [Use Explorer in the Security &amp; Compliance Center](use-explorer-in-security-and-compliance.md).</span></span>
  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="bd118-137">Autorizzazioni necessarie per visualizzare i report degli strumenti di analisi?</span><span class="sxs-lookup"><span data-stu-id="bd118-137">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="bd118-138">Per visualizzare e utilizzare i rapporti descritti in questo articolo, è necessario disporre di un ruolo appropriato assegnato nella protezione &amp; centro conformità e nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd118-138">In order to view and use the reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.</span></span>
  
|<span data-ttu-id="bd118-139">**Gruppo di ruoli**</span><span class="sxs-lookup"><span data-stu-id="bd118-139">**Role group**</span></span>|<span data-ttu-id="bd118-140">**Dove assegnato**</span><span class="sxs-lookup"><span data-stu-id="bd118-140">**Where assigned**</span></span>|<span data-ttu-id="bd118-141">**Altre informazioni**</span><span class="sxs-lookup"><span data-stu-id="bd118-141">**Learn more**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="bd118-142">Uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd118-142">One of the following:</span></span>  <br/>  <span data-ttu-id="bd118-143">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="bd118-143">Organization Management</span></span>  <br/>  <span data-ttu-id="bd118-144">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="bd118-144">Security Administrator</span></span>  <br/>  <span data-ttu-id="bd118-145">Lettore di sicurezza</span><span class="sxs-lookup"><span data-stu-id="bd118-145">Security Reader</span></span>  <br/> |<span data-ttu-id="bd118-146">Protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="bd118-146">Security &amp; Compliance Center</span></span>  <br/> |[<span data-ttu-id="bd118-147">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="bd118-147">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) <br/> |
| <span data-ttu-id="bd118-148">Uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd118-148">One of the following:</span></span>  <br/>  <span data-ttu-id="bd118-149">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="bd118-149">Organization Management</span></span>  <br/>  <span data-ttu-id="bd118-150">Gestione organizzazione sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="bd118-150">View-only Organization Management</span></span>  <br/>  <span data-ttu-id="bd118-151">Ruolo destinatari di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="bd118-151">View-Only Recipients role</span></span>  <br/>  <span data-ttu-id="bd118-152">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="bd118-152">Compliance Management</span></span>  <br/> |<span data-ttu-id="bd118-153">Centro amministrativo di Exchange</span><span class="sxs-lookup"><span data-stu-id="bd118-153">Exchange Admin Center</span></span>  <br/> |[<span data-ttu-id="bd118-154">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bd118-154">Feature permissions in Exchange Online</span></span>](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="bd118-155">Se il report non vengono visualizzate dati?</span><span class="sxs-lookup"><span data-stu-id="bd118-155">What if the reports aren't showing data?</span></span>

<span data-ttu-id="bd118-p106">Se non si possono visualizzare dati nei report, verificare che i criteri siano configurati correttamente. L'organizzazione deve disporre [degli strumenti di analisi collegamenti sicuro politiche](set-up-atp-safe-links-policies.md) e [gli allegati sicuri degli strumenti di analisi criteri](set-up-atp-safe-attachments-policies.md) definiti nell'ordine indicato per la protezione degli strumenti di analisi in locale. Vedere anche [protezione antispam e antimalware in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="bd118-p106">If you are not seeing data in your reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bd118-159">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bd118-159">Related topics</span></span>

[<span data-ttu-id="bd118-160">Report e sui concetti di Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="bd118-160">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="bd118-161">Creare una pianificazione per un report nella protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="bd118-161">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="bd118-162">Impostare e scaricare un report personalizzato per la protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="bd118-162">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

