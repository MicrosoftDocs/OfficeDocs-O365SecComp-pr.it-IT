---
title: Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection: M365-security-compliance
description: Informazioni su come trovare e utilizzare i report sulla sicurezza della posta elettronica per l'organizzazione con Office 365 Enterprise. I report sulla sicurezza della posta elettronica sono &amp; disponibili nel centro sicurezza e conformità.
ms.openlocfilehash: 809bfbdfdda8bd1ed9b88c9bca7e9ce14d774868
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216416"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="89ee7-104">Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="89ee7-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="89ee7-p102">Una serie di rapporti sulla sicurezza della posta elettronica sono disponibili nel [Centro sicurezza &amp; e conformità](https://security.microsoft.com) per vedere come le funzionalità di protezione da posta indesiderata e antimalware in Office 365 proteggono l'organizzazione. Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare questi report nel centro sicurezza &amp; e conformità accedendo al \*\*\*\* \> **Dashboard**dei report.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p102">A variety of email security reports are available in the [Security &amp; Compliance Center](https://security.microsoft.com) to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![Il dashboard &amp; del Centro sicurezza e conformità consente di individuare la modalità di funzionamento di Advanced Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="89ee7-108">I rapporti di sicurezza della posta elettronica includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="89ee7-108">Your email security reports include the following:</span></span>
  
- [<span data-ttu-id="89ee7-109">Rapporto sullo stato della protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="89ee7-109">Threat Protection Status report</span></span>](view-email-security-reports.md#tps) 
    
- [<span data-ttu-id="89ee7-110">Rapporto riLevamenti malware</span><span class="sxs-lookup"><span data-stu-id="89ee7-110">Malware Detections report</span></span>](view-email-security-reports.md#maldet)
    
- [<span data-ttu-id="89ee7-111">Rapporto malware principale</span><span class="sxs-lookup"><span data-stu-id="89ee7-111">Top Malware report</span></span>](#top-malware-report)
    
- [<span data-ttu-id="89ee7-112">Report mittenti e destinatari principali</span><span class="sxs-lookup"><span data-stu-id="89ee7-112">Top Senders and Recipients report</span></span>](view-email-security-reports.md#topsenders)
    
- [<span data-ttu-id="89ee7-113">Report di posta contraffatta</span><span class="sxs-lookup"><span data-stu-id="89ee7-113">Spoof Mail report</span></span>](#spoof-mail-report)
    
- [<span data-ttu-id="89ee7-114">Rapporto rilevamento posta inDesiderata</span><span class="sxs-lookup"><span data-stu-id="89ee7-114">Spam Detections report</span></span>](#spam-detections-report)
    
- [<span data-ttu-id="89ee7-115">Report di posta elettronica inviati e ricevuti</span><span class="sxs-lookup"><span data-stu-id="89ee7-115">Sent and received email report</span></span>](view-email-security-reports.md#sentreceivedemail)
    
- <span data-ttu-id="89ee7-116">[Report dei messaggi segnalaTi dall'utente](view-email-security-reports.md#userreported) (nuovo!)</span><span class="sxs-lookup"><span data-stu-id="89ee7-116">[User-reported messages report](view-email-security-reports.md#userreported) (new!)</span></span> 
    
## <a name="threat-protection-status-report"></a><span data-ttu-id="89ee7-117">Rapporto sullo stato della protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="89ee7-117">Threat Protection Status report</span></span>

<span data-ttu-id="89ee7-p103">Il nuovo rapporto **sullo stato di protezione dalle minacce** è uno smart report che indica che la posta elettronica dannosa è stata rilevata e bloccata da Exchange Online Protection. Questo report Visualizza informazioni su messaggi di posta elettronica identificati come malware o su un tentativo di phishing.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p103">The new **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt.</span></span> 

> [!NOTE]
> <span data-ttu-id="89ee7-p104">Un rapporto sullo stato della protezione dalle minacce è disponibile per i clienti che dispongono di [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto sullo stato di protezione di minacce per i clienti ATP probabilmente conterranno dati diversi da quelli che potrebbero essere visualizzati dai clienti di EOP. Ad esempio, i clienti di EOP possono visualizzare informazioni sui malware rilevati tramite posta elettronica, ma non informazioni sui [file dannosi rilevati in SharePoint Online, OneDrive o Microsoft teams](atp-for-spo-odb-and-teams.md), una funzionalità specifica del trifosfato di adenosina. (Ulteriori[informazioni sui rapporti ATP](view-reports-for-atp.md)).</span><span class="sxs-lookup"><span data-stu-id="89ee7-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md), an ATP-specific capability. ([Learn more about ATP reports](view-reports-for-atp.md).)</span></span>
  
<span data-ttu-id="89ee7-123">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **segnala** \> \*\*\*\* \> **lo stato di protezione delle minacce**del dashboard.</span><span class="sxs-lookup"><span data-stu-id="89ee7-123">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Rapporto sullo stato della protezione dalle minacce](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="89ee7-p105">Quando si apre per la prima volta il rapporto sullo stato di protezione dalle minacce, il report Visualizza i dati per i sette giorni scorsi per impostazione predefinita. Tuttavia, è possibile fare clic su **filtri** e modificare l'intervallo di date fino a 90 giorni di dettaglio. Questo report è utile per visualizzare l'efficacia e l'impatto delle funzionalità di Exchange Online Protection dell'organizzazione e per i trend a più lungo termine.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p105">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending.</span></span> 
  
![Filtri del rapporto sullo stato di protezione dalle minacce](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="89ee7-128">È anche possibile scegliere se visualizzare i dati per la posta elettronica identificati come messaggi dannosi, identificati come tentativi di phishing o come messaggi di posta elettronica identificati come contenenti malware.</span><span class="sxs-lookup"><span data-stu-id="89ee7-128">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Opzioni di visualizzazione del rapporto sullo stato di protezione dalle minacce](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="89ee7-130">Rapporto riLevamenti malware</span><span class="sxs-lookup"><span data-stu-id="89ee7-130">Malware Detections report</span></span>

<span data-ttu-id="89ee7-131">Il rapporto **rilevamento malware** indica il numero di messaggi in ingresso e in uscita che sono stati rilevati come contenenti malware per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89ee7-131">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="89ee7-132">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **report** \> di **rilevamento di malware**del **Dashboard** \> .</span><span class="sxs-lookup"><span data-stu-id="89ee7-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Esempio di rapporto riLevamenti malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="89ee7-p106">Analogamente ad altri rapporti, come il rapporto sullo stato della protezione dalle minacce, il report Visualizza i dati per i sette giorni scorsi per impostazione predefinita. Tuttavia, è possibile scegliere **filtri** per modificare l'intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p106">Similar to other reports, like the Threat Protection Status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="89ee7-136">Rapporto malware principale</span><span class="sxs-lookup"><span data-stu-id="89ee7-136">Top Malware report</span></span>

<span data-ttu-id="89ee7-137">Il rapporto **malware principale** Visualizza i vari tipi di malware rilevati da Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="89ee7-137">The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online.</span></span> 
  
<span data-ttu-id="89ee7-138">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), andare a **Reports** \> **Dashboard** \> **Top malware**.</span><span class="sxs-lookup"><span data-stu-id="89ee7-138">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC-EOP Top malware](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="89ee7-140">Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi che sono stati rilevati come aventi quel malware.</span><span class="sxs-lookup"><span data-stu-id="89ee7-140">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="89ee7-141">Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="89ee7-141">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Questo rapporto Visualizza la parte superiore di malware rilevata per l'organizzazione](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="89ee7-143">Al di sotto del grafico, verrà visualizzato un elenco di malware rilevato e il numero di messaggi che sono stati rilevati con malware.</span><span class="sxs-lookup"><span data-stu-id="89ee7-143">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="89ee7-144">Report mittenti e destinatari principali</span><span class="sxs-lookup"><span data-stu-id="89ee7-144">Top Senders and Recipients report</span></span>

<span data-ttu-id="89ee7-145">Il report **mittenti e destinatari principali** è un grafico a torta che mostra i mittenti di posta elettronica principali.</span><span class="sxs-lookup"><span data-stu-id="89ee7-145">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="89ee7-146">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), andare a **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span><span class="sxs-lookup"><span data-stu-id="89ee7-146">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità andare a Reports \> dashboard \> Top Senders and Recipients](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="89ee7-148">Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il numero di messaggi inviati o ricevuti.</span><span class="sxs-lookup"><span data-stu-id="89ee7-148">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="89ee7-149">Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="89ee7-149">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="89ee7-p107">Utilizzare l'elenco **Mostra dati per** scegliere se visualizzare i dati per i mittenti principali, i destinatari, gli utenti di posta indesiderata e i destinatari di malware. È inoltre possibile visualizzare gli utenti che hanno ricevuto malware rilevati da Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p107">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection.</span></span> 
  
![Utilizzare l'elenco Mostra dati per visualizzare informazioni specifiche](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="89ee7-153">Al di sotto del grafico, si vedrà chi sono i mittenti di posta elettronica o i destinatari principali, insieme a un numero di messaggi inviati o ricevuti per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="89ee7-153">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-mail-report"></a><span data-ttu-id="89ee7-154">Report di posta contraffatta</span><span class="sxs-lookup"><span data-stu-id="89ee7-154">Spoof Mail report</span></span>

<span data-ttu-id="89ee7-155">Il report di **posta spoof** Visualizza quanti messaggi di posta elettronica contraffatti sono stati rilevati e di quelli, quali sono stati considerati "buoni" (la posta contraffatta è stata realizzata per motivi aziendali legittimi).</span><span class="sxs-lookup"><span data-stu-id="89ee7-155">The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="89ee7-156">Per visualizzare questo report, nel [centro conformità &amp; sicurezza](https://protection.office.com)accedere a **report** \> di **posta**indesiderata del **Dashboard** \> .</span><span class="sxs-lookup"><span data-stu-id="89ee7-156">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità, accedere a report \> di \> posta indesiderata del dashboard](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="89ee7-158">Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile visualizzare il numero di messaggi di posta elettronica contraffatti.</span><span class="sxs-lookup"><span data-stu-id="89ee7-158">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="89ee7-159">Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="89ee7-159">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="89ee7-160">Rapporto rilevamento posta inDesiderata</span><span class="sxs-lookup"><span data-stu-id="89ee7-160">Spam Detections report</span></span>

<span data-ttu-id="89ee7-161">Il rapporto sui riLevamenti di **posta** indesiderata consente di visualizzare tutti i contenuti di posta indesiderata bloccati</span><span class="sxs-lookup"><span data-stu-id="89ee7-161">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> 
  
<span data-ttu-id="89ee7-162">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere ai rilevamenti di **posta**indesiderata del **Dashboard** \> dei **report** \> .</span><span class="sxs-lookup"><span data-stu-id="89ee7-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità, accedere a report \> dashboard \> EOP spam detections](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="89ee7-p108">Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile vedere quanti elementi sono stati bloccati quel giorno, così come gli elementi sono categorizzati. Ad esempio, è possibile visualizzare il numero di messaggi di posta indesiderata filtrati e il numero di elementi provenienti da un indirizzo IP (Internet Protocol) bloccato.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p108">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="89ee7-166">Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="89ee7-166">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Il rapporto sui riLevamenti di posta inDesiderata indica il numero di messaggi di posta indesiderata bloccati o eliminati](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="89ee7-p109">Al di sotto del grafico, verrà visualizzato un elenco di elementi di posta indesiderata che sono stati rilevati. Selezionare un elemento per visualizzare informazioni aggiuntive, ad esempio se l'elemento di posta indesiderata è in ingresso o in uscita, il relativo ID messaggio e il relativo destinatario.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p109">Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="89ee7-170">Report di posta elettronica inviati e ricevuti</span><span class="sxs-lookup"><span data-stu-id="89ee7-170">Sent and received email report</span></span>

<span data-ttu-id="89ee7-171">Il rapporto **messaggi di posta elettronica inviati e ricevuti** è un report Smart che contiene informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona".</span><span class="sxs-lookup"><span data-stu-id="89ee7-171">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="89ee7-172">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **Reports** \> **Dashboard** \> **sent and received email**.</span><span class="sxs-lookup"><span data-stu-id="89ee7-172">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità, accedere a \> Reports \> dashboard sent and received email](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="89ee7-p110">Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile visualizzare il numero di messaggi in arrivo e il modo in cui i messaggi vengono categorizzati. Ad esempio, è possibile vedere quanti messaggi sono stati rilevati come contenenti malware e quante sono stati identificati come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p110">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="89ee7-176">Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="89ee7-176">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="89ee7-177">È possibile utilizzare l'elenco a **discesa** per visualizzare le informazioni per tipo o per direzione (in ingresso e in uscita).</span><span class="sxs-lookup"><span data-stu-id="89ee7-177">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Utilizzare l'elenco a discesa per visualizzare le informazioni in base al tipo o alla direzione](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="89ee7-p111">Al di sotto del grafico verrà visualizzato un elenco di categorie di posta elettronica, ad esempio **GoodMail**, **SpamContentFiltered**e così via. Selezionare una categoria per visualizzare altre informazioni, ad esempio le azioni che sono state intraprese per il malware, e se la posta elettronica è in ingresso o in uscita.</span><span class="sxs-lookup"><span data-stu-id="89ee7-p111">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![Questo rapporto fornisce informazioni sull'antimalware, la protezione da posta indesiderata e altri rilevamenti dei messaggi](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a><span data-ttu-id="89ee7-182">Report dei messaggi segnalati dall'utente (nuovo!)</span><span class="sxs-lookup"><span data-stu-id="89ee7-182">User-reported messages report (new!)</span></span>

<span data-ttu-id="89ee7-183">Il rapporto **messaggi segnalaTi dall'utente** Visualizza informazioni sui messaggi di posta elettronica segnalati dagli utenti come posta indesiderata, tentativi di phishing o una buona corrispondenza tramite il [componente aggiuntivo segnala messaggio](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="89ee7-183">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
<span data-ttu-id="89ee7-p112">I dettagli sono disponibili per ogni messaggio, incluso il motivo del recapito, una regola di protezione da posta indesiderata o un flusso di posta configurata per l'organizzazione. Per visualizzare i dettagli, selezionare un elemento nell'elenco User-Reports e quindi visualizzare le informazioni nelle schede **Riepilogo** e **Dettagli** .</span><span class="sxs-lookup"><span data-stu-id="89ee7-p112">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![Il rapporto messaggi segnalati dall'utente Visualizza i messaggi che gli utenti sono contrassegnati come posta indesiderata, non indesiderata o tentativi di phishing.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="89ee7-187">Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com)eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89ee7-187">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="89ee7-188">Accedere a **messaggi segnalati dall'utente**del \> **Dashboard** \> di **gestione delle minacce** .</span><span class="sxs-lookup"><span data-stu-id="89ee7-188">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="89ee7-189">Passare a **gestione** \> minacce **esaminare** \> **i messaggi segnalati dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="89ee7-189">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![Nel centro sicurezza &amp; e conformità, scegliere messaggi segnalati dall'utente di Threat Management \> Review \>](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="89ee7-p113">Affinché il rapporto messaggi segnalati dall'utente funzioni correttamente, **è necessario che la registrazione di controllo sia attivata** per l'ambiente Office 365. Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online. Per ulteriori informazioni, vedere [attivazione o disattivaZione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="89ee7-p113">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="89ee7-194">Quali autorizzazioni sono necessarie per visualizzare i rapporti?</span><span class="sxs-lookup"><span data-stu-id="89ee7-194">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="89ee7-195">Per visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato per il Centro sicurezza &amp; e l'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="89ee7-195">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="89ee7-196">Per il centro &amp; sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="89ee7-196">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="89ee7-197">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="89ee7-197">Organization Management</span></span>
    - <span data-ttu-id="89ee7-198">Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()</span><span class="sxs-lookup"><span data-stu-id="89ee7-198">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="89ee7-199">Lettore di sicurezza</span><span class="sxs-lookup"><span data-stu-id="89ee7-199">Security Reader</span></span>

- <span data-ttu-id="89ee7-200">Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="89ee7-200">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="89ee7-201">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="89ee7-201">Organization Management</span></span>
    - <span data-ttu-id="89ee7-202">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="89ee7-202">View-only Organization Management</span></span>
    - <span data-ttu-id="89ee7-203">Ruolo Destinatari di sola lettura</span><span class="sxs-lookup"><span data-stu-id="89ee7-203">View-Only Recipients role</span></span>
    - <span data-ttu-id="89ee7-204">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="89ee7-204">Compliance Management</span></span>

<span data-ttu-id="89ee7-205">Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="89ee7-205">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="89ee7-206">Autorizzazioni nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="89ee7-206">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="89ee7-207">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="89ee7-207">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="89ee7-208">Cosa succede se i rapporti non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="89ee7-208">What if the reports aren't showing data?</span></span>

<span data-ttu-id="89ee7-p114">Se i dati non vengono visualizzati nei rapporti, verificare che i criteri siano configurati correttamente. Per ulteriori informazioni, vedere [protezione da posta indesiderata e anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="89ee7-p114">If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="89ee7-211">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="89ee7-211">Related topics</span></span>

[<span data-ttu-id="89ee7-212">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="89ee7-212">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="89ee7-213">Report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="89ee7-213">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="89ee7-214">Creare una pianificazione per un report nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="89ee7-214">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="89ee7-215">Configurare e scaricare un report personalizzato nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="89ee7-215">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

