---
title: Visualizzare i report per Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i report per Office 365 Advanced Threat Protection nel centro &amp; sicurezza e conformità.
ms.openlocfilehash: c2c1e1134d72bc8c786e0dd783d22adcebeed79b
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2019
ms.locfileid: "30242108"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="56bff-103">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="56bff-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="56bff-p101">Se l'organizzazione dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) ed è necessario disporre delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile utilizzare diversi rapporti ATP nel &amp; Centro sicurezza e conformità. (Andare al \*\*\*\* \> **Dashboard**di report).</span><span class="sxs-lookup"><span data-stu-id="56bff-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![Il dashboard &amp; del Centro sicurezza e conformità consente di individuare la modalità di funzionamento di Advanced Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="56bff-p102">I rapporti ATP includono il rapporto [sullo stato della protezione dalle minacce](#threat-protection-status-report), il rapporto [tipi di file ATP](#atp-file-types-report)e il [rapporto disposizione dei messaggi ATP](#atp-message-disposition-report). In questo articolo vengono descritti i rapporti ATP e sono inclusi i collegamenti a [report aggiuntivi da visualizzare](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="56bff-p102">ATP reports include the [Threat Protection Status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report). This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="56bff-109">Rapporto sullo stato della protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="56bff-109">Threat Protection Status report</span></span>

<span data-ttu-id="56bff-p103">Il rapporto **sullo stato della protezione dalle minacce** è una singola visualizzazione che raggruppa informazioni su contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) e [Office 365 ATP](office-365-atp.md). Il rapporto fornisce un numero aggregato di messaggi di posta elettronica univoci con contenuto dannoso (file o indirizzi sito Web (URL)) bloccati dal motore antimalware, [zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md)e caratteristiche ATP, ad esempio [collegamenti sicuri ATP](atp-safe-links.md), [ATP Safe Allegati](atp-safe-attachments.md)e [funzionalità di anti-phishing ATP](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="56bff-p103">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md). The report provides an aggregated count of unique email messages with malicious content (files or website addresses (URLs)) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="56bff-p104">Un rapporto sullo stato della protezione dalle minacce è disponibile per i clienti che dispongono di [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto sullo stato di protezione di minacce per i clienti ATP probabilmente conterranno dati diversi da quelli che potrebbero essere visualizzati dai clienti di EOP. Ad esempio, il rapporto sullo stato della protezione dalle minacce per i clienti ATP conterrà informazioni sui [file dannosi rilevati in SharePoint Online, OneDrive o Microsoft teams](atp-for-spo-odb-and-teams.md). Tali informazioni sono specifiche di ATP, quindi i clienti che hanno EOP ma non ATP non vedranno tali dettagli nella loro relazione sullo stato di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="56bff-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md). Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="56bff-115">Per visualizzare il rapporto sullo stato di protezione dalle minacce, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **segnala** \> \*\*\*\* \> **lo stato di protezione delle minacce**del dashboard.</span><span class="sxs-lookup"><span data-stu-id="56bff-115">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Rapporto sullo stato di protezione ATP con minacce](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="56bff-117">Per ottenere lo stato dettagliato per un giorno, posizionare il puntatore del mouse sul grafico.</span><span class="sxs-lookup"><span data-stu-id="56bff-117">To get detailed status for a day, hover over the graph.</span></span>
  
![Dati sullo stato della protezione da ATP per un giorno](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="56bff-p105">Per impostazione predefinita, il rapporto sullo stato della protezione dalle minacce Visualizza i dati negli ultimi sette giorni. Tuttavia, è possibile scegliere **filtri** e modificare l'intervallo di date per visualizzare i dati fino a 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="56bff-p105">By default, the Threat Protection Status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![Filtri di stato di protezione da minacce ATP](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="56bff-122">È inoltre possibile utilizzare il menu **Visualizza dati in base** a per modificare le informazioni visualizzate nel report.</span><span class="sxs-lookup"><span data-stu-id="56bff-122">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Opzioni di visualizzazione per il rapporto sullo stato della protezione da ATP](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="56bff-124">Rapporto tipi di file ATP</span><span class="sxs-lookup"><span data-stu-id="56bff-124">ATP File Types report</span></span>

<span data-ttu-id="56bff-125">Il rapporto **tipi di file ATP** Visualizza il tipo di file rilevati come dannosi dagli [allegati sicuri di ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="56bff-125">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="56bff-126">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **Reports** \> **Dashboard** \> **ATP types**.</span><span class="sxs-lookup"><span data-stu-id="56bff-126">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Rapporto tipi di file ATP](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="56bff-128">Quando si posiziona il puntatore del mouse su un determinato giorno, è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri ATP](atp-safe-attachments.md) e dalla [protezione anti-malware antispamming &amp; in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="56bff-128">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![I tipi di file ATP riportano i dati per un giorno](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="56bff-130">Rapporto di disposizione del messaggio ATP</span><span class="sxs-lookup"><span data-stu-id="56bff-130">ATP Message Disposition report</span></span>

<span data-ttu-id="56bff-131">Il rapporto di **disposizione dei messaggi ATP** indica le azioni eseguite per i messaggi di posta elettronica rilevati come contenuti dannosi.</span><span class="sxs-lookup"><span data-stu-id="56bff-131">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="56bff-132">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **disposizione dei messaggi**per il **Dashboard** \> dei **report** \> ATP.</span><span class="sxs-lookup"><span data-stu-id="56bff-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Rapporto di disposizione del messaggio ATP](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="56bff-134">Quando si posiziona il puntatore del mouse su una barra del grafico, è possibile vedere quali azioni sono state eseguite per il messaggio di posta elettronica rilevato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="56bff-134">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Dati del rapporto disposizione dei messaggi ATP per un giorno](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="56bff-136">Report aggiuntivi da visualizzare</span><span class="sxs-lookup"><span data-stu-id="56bff-136">Additional reports to view</span></span>

<span data-ttu-id="56bff-137">Oltre ai report ATP descritti in questo articolo, sono disponibili diversi altri report, come descritto nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="56bff-137">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="56bff-138">Tipo di rapporto</span><span class="sxs-lookup"><span data-stu-id="56bff-138">Report type</span></span>  |<span data-ttu-id="56bff-139">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="56bff-139">Learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="56bff-140">Report di **protezione della posta elettronica**, ad esempio un report mittenti e destinatari principali, un report di posta indesiderata e un report di rilevaMenti di spam.</span><span class="sxs-lookup"><span data-stu-id="56bff-140">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="56bff-141">Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="56bff-141">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="56bff-142">**Gestione risorse** (noto anche come Esplora minacce, è incluso in [Office 365 Threat Intelligence](office-365-ti.md))</span><span class="sxs-lookup"><span data-stu-id="56bff-142">**Explorer** (also referred to as Threat Explorer, this is included in [Office 365 Threat Intelligence](office-365-ti.md))</span></span>     | [<span data-ttu-id="56bff-143">Utilizzo di Esplora risorse nel &amp; Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="56bff-143">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)        |
|<span data-ttu-id="56bff-p106">**Risultati di EOP e ATP** (Si tratta di un report personalizzato generato tramite PowerShell). Questo report contiene informazioni, ad esempio dominio, data, tipo di evento, direzione, azione e numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="56bff-p106">**EOP and ATP results** (This is a custom report you generate by using PowerShell). This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="56bff-146">Informazioni di riferimento sui cmdlet Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="56bff-146">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="56bff-p107">**Rilevamenti di EOP e ATP** (Si tratta di un report personalizzato generato tramite PowerShell). Questo report contiene informazioni dettagliate su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.</span><span class="sxs-lookup"><span data-stu-id="56bff-p107">**EOP and ATP detections** (This is a custom report you generate by using PowerShell). This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="56bff-149">Informazioni di riferimento sui cmdlet Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="56bff-149">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="56bff-150">Quali autorizzazioni sono necessarie per visualizzare i report ATP?</span><span class="sxs-lookup"><span data-stu-id="56bff-150">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="56bff-151">Per visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato per il Centro sicurezza &amp; e l'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="56bff-151">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="56bff-152">Per il centro &amp; sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="56bff-152">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="56bff-153">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="56bff-153">Organization Management</span></span>
    - <span data-ttu-id="56bff-154">Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ())</span><span class="sxs-lookup"><span data-stu-id="56bff-154">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="56bff-155">Lettore di sicurezza</span><span class="sxs-lookup"><span data-stu-id="56bff-155">Security Reader</span></span>

- <span data-ttu-id="56bff-156">Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="56bff-156">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="56bff-157">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="56bff-157">Organization Management</span></span>
    - <span data-ttu-id="56bff-158">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="56bff-158">View-only Organization Management</span></span>
    - <span data-ttu-id="56bff-159">Ruolo Destinatari di sola lettura</span><span class="sxs-lookup"><span data-stu-id="56bff-159">View-Only Recipients role</span></span>
    - <span data-ttu-id="56bff-160">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="56bff-160">Compliance Management</span></span>

<span data-ttu-id="56bff-161">Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="56bff-161">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="56bff-162">Autorizzazioni nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="56bff-162">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="56bff-163">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="56bff-163">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="56bff-164">Cosa succede se i rapporti non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="56bff-164">What if the reports aren't showing data?</span></span>

<span data-ttu-id="56bff-p108">Se i dati non vengono visualizzati nei rapporti ATP, verificare che i criteri siano configurati correttamente. L'organizzazione deve disporre di [criteri dei collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) e di criteri per gli [allegati sicuri ATP](set-up-atp-safe-attachments-policies.md) definiti in modo che la protezione da ATP sia sul posto. Vedere anche [protezione da posta indesiderata e anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="56bff-p108">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="56bff-168">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="56bff-168">Related topics</span></span>

[<span data-ttu-id="56bff-169">Report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="56bff-169">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="56bff-170">Creare una pianificazione per un report nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="56bff-170">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="56bff-171">Configurare e scaricare un report personalizzato nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="56bff-171">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

