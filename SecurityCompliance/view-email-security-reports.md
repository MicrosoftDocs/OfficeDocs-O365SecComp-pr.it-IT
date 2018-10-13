---
title: Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità
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
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: Informazioni su come trovare e utilizzare i rapporti di protezione posta elettronica per l'organizzazione con Office 365 Enterprise. Rapporti sulla protezione posta elettronica sono disponibili nel titolo &amp; centro conformità.
ms.openlocfilehash: ea5d60393809ef924d51435b695062fe51e772bd
ms.sourcegitcommit: e0c6f99d5514d8da8a70d9bd3616d1a1c0851254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2018
ms.locfileid: "25552394"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="8cc91-104">Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="8cc91-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="8cc91-p102">Protezione della posta elettronica diversi report sono disponibili per la protezione &amp; centro conformità che consentono di vedere modalità di protezione antispam e antimalware caratteristiche di Office 365 dell'organizzazione. Se si dispone [delle autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare questi rapporti in sicurezza &amp; centro conformità accedendo ai **rapporti** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p102">A variety of email security reports are available in the Security &amp; Compliance Center to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![La sicurezza &amp; dashboard centro conformità risulta utile per determinare dove funzioni avanzate Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="8cc91-108">I rapporti di protezione posta elettronica includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8cc91-108">Your email security reports include the following:</span></span>
  
- <span data-ttu-id="8cc91-109">[Relazione sullo stato di protezione di rischio](view-email-security-reports.md#tps) (nuovo)!</span><span class="sxs-lookup"><span data-stu-id="8cc91-109">[Threat Protection Status report](view-email-security-reports.md#tps) (new!)</span></span> 
    
- [<span data-ttu-id="8cc91-110">Rapporto sui rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="8cc91-110">Malware Detections report</span></span>](view-email-security-reports.md#maldet)
    
- [<span data-ttu-id="8cc91-111">Rapporto Malware principale</span><span class="sxs-lookup"><span data-stu-id="8cc91-111">Top Malware report</span></span>](#top-malware-report)
    
- [<span data-ttu-id="8cc91-112">Report di destinatari e mittenti principali</span><span class="sxs-lookup"><span data-stu-id="8cc91-112">Top Senders and Recipients report</span></span>](view-email-security-reports.md#topsenders)
    
- [<span data-ttu-id="8cc91-113">Consentire l'accesso ai report di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="8cc91-113">Spoof Mail report</span></span>](#spoof-mail-report)
    
- [<span data-ttu-id="8cc91-114">Rapporto sui rilevamenti di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="8cc91-114">Spam Detections report</span></span>](#spam-detections-report)
    
- [<span data-ttu-id="8cc91-115">Report di posta elettronica inviati e ricevuti</span><span class="sxs-lookup"><span data-stu-id="8cc91-115">Sent and received email report</span></span>](view-email-security-reports.md#sentreceivedemail)
    
- <span data-ttu-id="8cc91-116">[Rapporto messaggi segnalati dagli utenti](view-email-security-reports.md#userreported) (nuovo)!</span><span class="sxs-lookup"><span data-stu-id="8cc91-116">[User-reported messages report](view-email-security-reports.md#userreported) (new!)</span></span> 
    
## <a name="threat-protection-status-report-new"></a><span data-ttu-id="8cc91-117">Minacce relazione sullo stato di protezione (nuovo)!</span><span class="sxs-lookup"><span data-stu-id="8cc91-117">Threat Protection Status report (new!)</span></span>

<span data-ttu-id="8cc91-p103">La nuova relazione **Sullo stato di protezione di rischio** è un rapporto intelligente che mostra dannoso posta elettronica che è stato rilevato e bloccato da Exchange Online Protection. Questo rapporto vengono visualizzate informazioni sulla posta elettronica identificato come malware o un tentativo di phishing.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p103">The new **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt.</span></span> 

> [!NOTE]
> <span data-ttu-id="8cc91-p104">Una relazione sullo stato di protezione di rischio è disponibile per i clienti che dispongono di [Strumenti di analisi di Office 365](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto di stato di protezione di rischio per i clienti degli strumenti di analisi probabile che conterrà dati diversi rispetto a ciò che potrebbe essere visualizzato EOP customers. Ad esempio clienti EOP possono visualizzare informazioni su malware rilevato nel messaggio di posta elettronica, ma non informazioni sui [file dannosi rilevato in SharePoint Online, OneDrive o team Microsoft che](atp-for-spo-odb-and-teams.md), una funzionalità specifiche degli strumenti di analisi. ([Ulteriori informazioni sui report degli strumenti di analisi](view-reports-for-atp.md)).</span><span class="sxs-lookup"><span data-stu-id="8cc91-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md), an ATP-specific capability. ([Learn more about ATP reports](view-reports-for-atp.md).)</span></span>
  
<span data-ttu-id="8cc91-123">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Lo stato di protezione di rischio**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-123">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Relazione sullo stato di protezione di rischio](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="8cc91-p105">Quando si apre la relazione sullo stato di protezione di rischio, il report mostra i dati per gli ultimi sette giorni per impostazione predefinita. Tuttavia, è possibile fare clic su **filtri** e modificare l'intervallo di date per un massimo di 90 giorni di dettaglio. In questo report è utile per visualizzare l'efficacia e l'impatto delle funzionalità di Exchange Online Protection dell'organizzazione e per l'analisi delle tendenze più lungo termine.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p105">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending.</span></span> 
  
![Filtri del rapporto sullo stato di protezione rischio](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="8cc91-128">È anche possibile scegliere se visualizzare i dati per la posta elettronica identificato come dannose, posta identificata come tentativi di phishing, o posta elettronica identificato come contenente malware.</span><span class="sxs-lookup"><span data-stu-id="8cc91-128">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Visualizzare le opzioni di rischio di protezione report](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="8cc91-130">Rapporto sui rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="8cc91-130">Malware Detections report</span></span>

<span data-ttu-id="8cc91-131">Nel rapporto **Rilevamenti di Malware** viene visualizzato il numero di messaggi in ingresso e in uscita sono stato rilevato come contenente malware per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8cc91-131">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="8cc91-132">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Rilevamenti di Malware**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-132">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Esempio di rapporto sui rilevamenti di malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="8cc91-p106">Simile ad altri report, ad esempio il rapporto di stato di protezione di rischio, i report vengono visualizzati dati per gli ultimi sette giorni per impostazione predefinita. Tuttavia, è possibile scegliere di **filtri** per modificare l'intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p106">Similar to other reports, like the Threat Protection Status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="8cc91-136">Rapporto Malware principale</span><span class="sxs-lookup"><span data-stu-id="8cc91-136">Top Malware report</span></span>

<span data-ttu-id="8cc91-137">Il rapporto **Malware principali** Mostra i vari tipi di malware rilevato da Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8cc91-137">The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online.</span></span> 
  
<span data-ttu-id="8cc91-138">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Malware principali**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-138">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![Controllo del codice sorgente - EOP Malware principali](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="8cc91-140">Quando si sposta su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi sono stato rilevato con tale malware.</span><span class="sxs-lookup"><span data-stu-id="8cc91-140">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="8cc91-141">Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="8cc91-141">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![In questo rapporto viene visualizzato il malware principali rilevato per l'organizzazione](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="8cc91-143">Sotto il grafico verrà visualizzato un elenco di malware rilevato e il numero di messaggi sono stato rilevato con tale malware.</span><span class="sxs-lookup"><span data-stu-id="8cc91-143">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="8cc91-144">Report di destinatari e mittenti principali</span><span class="sxs-lookup"><span data-stu-id="8cc91-144">Top Senders and Recipients report</span></span>

<span data-ttu-id="8cc91-145">Il report **primi mittenti e destinatari** è un grafico a torta che mostra i mittenti di posta elettronica principali.</span><span class="sxs-lookup"><span data-stu-id="8cc91-145">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="8cc91-146">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **primi mittenti e destinatari**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-146">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Per visualizzare il report nella protezione &amp; centro conformità, passare a report \> Dashboard \> primi mittenti e destinatari](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="8cc91-148">Quando si sposta su un cuneo nel grafico a torta, è possibile visualizzare un numero di messaggi inviati o ricevuti.</span><span class="sxs-lookup"><span data-stu-id="8cc91-148">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="8cc91-149">Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="8cc91-149">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="8cc91-p107">Utilizzare l'elenco di **visualizzare i dati relativi** a scegliere se si desidera visualizzare i dati per i mittenti principali, ricevitori, destinatari di posta indesiderata e destinatari di malware. Puoi anche vedere che ha ricevuto malware rilevato dal avanzate per la protezione rischio.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p107">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection.</span></span> 
  
![Utilizzare l'elenco Mostra dati per visualizzare informazioni specifiche](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="8cc91-153">Sotto il grafico, si vedrà che i mittenti di posta elettronica principale o i destinatari sono stati, insieme a un numero di messaggi inviati o ricevuti per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="8cc91-153">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-mail-report"></a><span data-ttu-id="8cc91-154">Consentire l'accesso ai report di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="8cc91-154">Spoof Mail report</span></span>

<span data-ttu-id="8cc91-155">Nel rapporto di **Posta elettronica di spoofing** viene visualizzato il numero dei messaggi di posta elettronica spoofing sono stato rilevato e di quelli, quelli che sono state esaminate "good" (SteadyState motivi aziendali legittimi mail spoofing).</span><span class="sxs-lookup"><span data-stu-id="8cc91-155">The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="8cc91-156">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Spoofing posta**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-156">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![Per visualizzare il report nella protezione &amp; centro conformità, passare a report \> Dashboard \> spoofing posta](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="8cc91-158">Quando si sposta su un giorno del grafico, è possibile visualizzare il numero dei messaggi di posta elettronica spoofing sia il risultato.</span><span class="sxs-lookup"><span data-stu-id="8cc91-158">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="8cc91-159">Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="8cc91-159">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="8cc91-160">Rapporto sui rilevamenti di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="8cc91-160">Spam Detections report</span></span>

<span data-ttu-id="8cc91-161">Il rapporto **Sui rilevamenti di posta indesiderata** Visualizza tutto il contenuto di posta indesiderata bloccato da Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8cc91-161">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> 
  
<span data-ttu-id="8cc91-162">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Rilevamenti di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-162">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Per visualizzare il report nella protezione &amp; centro conformità, passare a report \> Dashboard \> EOP i rilevamenti di posta indesiderata](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="8cc91-p108">Quando si sposta su un giorno del grafico, è possibile visualizzare il numero di elementi sono stato bloccato quel giorno il modo in cui sono suddivise in tali elementi. Ad esempio, è possibile visualizzare il numero di messaggi di posta indesiderata sono stato filtrato e il numero di elementi proviene da un indirizzo IP (Internet Protocol) bloccati.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p108">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="8cc91-166">Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="8cc91-166">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Il rapporto sui rilevamenti di posta indesiderata indica il numero di messaggi di posta indesiderata sono stato bloccato o filtrato](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="8cc91-p109">Sotto il grafico verrà visualizzato un elenco di elementi di posta indesiderata che sono stati rilevati. Selezionare una voce per visualizzare informazioni aggiuntive, ad esempio se l'elemento di posta indesiderata è stato in ingresso e in uscita, l'ID messaggio e il destinatario.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p109">Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="8cc91-170">Report di posta elettronica inviati e ricevuti</span><span class="sxs-lookup"><span data-stu-id="8cc91-170">Sent and received email report</span></span>

<span data-ttu-id="8cc91-171">Il rapporto **Sent e posta elettronica ricevuta** è un referente smart che mostra informazioni sulla posta elettronica in arrivo e in uscita, tra cui i rilevamenti di posta indesiderata, malware e posta elettronica identificato come "buona".</span><span class="sxs-lookup"><span data-stu-id="8cc91-171">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="8cc91-172">Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **inviati e ricevuto posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-172">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Per visualizzare il report nella protezione &amp; centro conformità, passare a report \> Dashboard \> Sent e posta elettronica ricevuta](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="8cc91-p110">Quando si sposta su un giorno del grafico, è possibile visualizzare il numero di messaggi è stato ricevuto e come i messaggi sono classificati. Ad esempio, è possibile visualizzare il numero di messaggi sono stato rilevato come contenente malware e sono stati identificati come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p110">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="8cc91-176">Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="8cc91-176">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="8cc91-177">È possibile utilizzare l'elenco **suddivisione per** visualizzare informazioni dal tipo o dalla direzione (in ingresso e in uscita).</span><span class="sxs-lookup"><span data-stu-id="8cc91-177">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Utilizzare l'elenco interruzioni verso il basso da per visualizzare le informazioni dal tipo o la direzione](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="8cc91-p111">Sotto il grafico verrà visualizzato un elenco delle categorie di posta elettronica, ad esempio **GoodMail**, **SpamContentFiltered**e così via. Selezionare una categoria di visualizzare informazioni aggiuntive, ad esempio azioni intraprese per malware e di posta elettronica se è stato in ingresso o in uscita.</span><span class="sxs-lookup"><span data-stu-id="8cc91-p111">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![Questo rapporto fornisce le informazioni sulla protezione anti-malware, protezione da posta indesiderata e rilevamenti altri messaggi](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a><span data-ttu-id="8cc91-182">Report di messaggi segnalati dagli utenti (nuovo)!</span><span class="sxs-lookup"><span data-stu-id="8cc91-182">User-reported messages report (new!)</span></span>

<span data-ttu-id="8cc91-183">Il report **specificato dall'utente i messaggi** vengono visualizzate informazioni sui messaggi di posta elettronica che gli utenti hanno segnalato come posta indesiderata, tentativi di phishing o posta legittima utilizzando il [componente aggiuntivo di report](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="8cc91-183">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
<span data-ttu-id="8cc91-p112">Sono disponibili dettagli per ogni messaggio, inclusi il motivo di recapito, ad esempio un eccezione di criteri di posta indesiderata o regola flusso di posta elettronica configurati per l'organizzazione. Per visualizzare i dettagli, selezionare un elemento nell'elenco report utente e quindi visualizzare le informazioni nelle schede **Riepilogo** e **Dettagli** .</span><span class="sxs-lookup"><span data-stu-id="8cc91-p112">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![Il rapporto di messaggi User-Reported Mostra agli utenti i messaggi contrassegnati come posta indesiderata, non indesiderata o phishing tentativi.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="8cc91-187">Per visualizzare il report nella protezione &amp; centro conformità, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cc91-187">To view this report, in the Security &amp; Compliance Center, do one of the following:</span></span>
  
- <span data-ttu-id="8cc91-188">Passare a **gestione rischio** \> **Dashboard** \> **messaggi segnalati dagli utenti**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-188">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="8cc91-189">Passare a **gestione rischio** \> **revisione** \> **messaggi segnalati dagli utenti**.</span><span class="sxs-lookup"><span data-stu-id="8cc91-189">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![In sicurezza &amp; centro conformità, scegliere Threat management \> revisione \> messaggi specificato dall'utente](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="8cc91-p113">Per consentire il rapporto di messaggi segnalati dagli utenti per il corretto funzionamento di **deve essere attivata la registrazione di controllo** per l'ambiente Office 365. Questo viene in genere eseguito da un utente che disponga del ruolo registri di controllo assegnato in Exchange Online. Per ulteriori informazioni, vedere [attivare Office 365 ricerca dei registri di controllo attivato o disattivato](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="8cc91-p113">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="8cc91-194">Autorizzazioni necessarie per visualizzare questi rapporti?</span><span class="sxs-lookup"><span data-stu-id="8cc91-194">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="8cc91-195">Per visualizzare e utilizzare i rapporti di protezione posta elettronica descritti in questo articolo, è necessario disporre di un ruolo appropriato assegnato nella protezione &amp; centro conformità e nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="8cc91-195">In order to view and use the email security reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.</span></span>
  
|<span data-ttu-id="8cc91-196">**Gruppo di ruoli**</span><span class="sxs-lookup"><span data-stu-id="8cc91-196">**Role group**</span></span>|<span data-ttu-id="8cc91-197">**Dove assegnato**</span><span class="sxs-lookup"><span data-stu-id="8cc91-197">**Where assigned**</span></span>|<span data-ttu-id="8cc91-198">**Altre informazioni**</span><span class="sxs-lookup"><span data-stu-id="8cc91-198">**Learn more**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="8cc91-199">Uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cc91-199">One of the following:</span></span>  <br/><br/><span data-ttu-id="8cc91-200">-Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="8cc91-200">--Organization Management</span></span>  <br/><span data-ttu-id="8cc91-201">-- Sicurezza amministratore</span><span class="sxs-lookup"><span data-stu-id="8cc91-201">--Security Administrator</span></span>  <br/><span data-ttu-id="8cc91-202">-- Protezione lettore</span><span class="sxs-lookup"><span data-stu-id="8cc91-202">--Security Reader</span></span>  <br/> |<span data-ttu-id="8cc91-203">Protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="8cc91-203">Security &amp; Compliance Center</span></span>  <br/> |[<span data-ttu-id="8cc91-204">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="8cc91-204">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) <br/> |
| <span data-ttu-id="8cc91-205">Uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cc91-205">One of the following:</span></span>  <br/><br/><span data-ttu-id="8cc91-206">-Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="8cc91-206">--Organization Management</span></span>  <br/><span data-ttu-id="8cc91-207">-Gestione organizzazione sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="8cc91-207">--View-only Organization Management</span></span>  <br/><span data-ttu-id="8cc91-208">-Ruolo destinatari View-Only</span><span class="sxs-lookup"><span data-stu-id="8cc91-208">--View-Only Recipients role</span></span>  <br/><span data-ttu-id="8cc91-209">: Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="8cc91-209">--Compliance Management</span></span>  <br/> |<span data-ttu-id="8cc91-210">Interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="8cc91-210">Exchange Admin Center</span></span>  <br/> |[<span data-ttu-id="8cc91-211">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8cc91-211">Feature permissions in Exchange Online</span></span>](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="8cc91-212">Se il report non vengono visualizzate dati?</span><span class="sxs-lookup"><span data-stu-id="8cc91-212">What if the reports aren't showing data?</span></span>

<span data-ttu-id="8cc91-p114">Se non si possono visualizzare dati nei report, verificare che i criteri siano configurati correttamente. Per ulteriori informazioni, vedere [protezione antispam e antimalware in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="8cc91-p114">If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8cc91-215">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8cc91-215">Related topics</span></span>

[<span data-ttu-id="8cc91-216">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="8cc91-216">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="8cc91-217">Report e sui concetti di Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="8cc91-217">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="8cc91-218">Creare una pianificazione per un report nella protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="8cc91-218">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="8cc91-219">Impostare e scaricare un report personalizzato per la protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="8cc91-219">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

