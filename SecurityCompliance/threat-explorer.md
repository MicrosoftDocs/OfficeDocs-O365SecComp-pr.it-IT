---
title: Esplora minacce (e rilevamenti in tempo reale)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Informazioni su Esplora risorse (e sui rilevamenti in tempo reale) &amp; nel centro sicurezza e conformità.
ms.openlocfilehash: 030f866c5e86daa3dc543bddae7152e19f377d3b
ms.sourcegitcommit: 6c0fcb82178a4ac26375545f328389a6852a81be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2019
ms.locfileid: "34490532"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="287a0-103">Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="287a0-103">Threat Explorer (and real-time detections)</span></span>

<span data-ttu-id="287a0-104">Se l'organizzazione dispone [di office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) ed è necessario disporre delle [autorizzazioni necessarie](#required-licenses-and-permissions), è possibile individuare **esploratori** o rilevamenti in **tempo reale** (in precedenza rapporti in *tempo reale* , [vedere Novità](#new-features-in-real-time-detections)!).</span><span class="sxs-lookup"><span data-stu-id="287a0-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-real-time-detections)!).</span></span> <span data-ttu-id="287a0-105">Nel centro sicurezza & Compliance, passare a **gestione minacce**, quindi scegliere **Esplora risorse** o rilevamenti in **tempo reale**.</span><span class="sxs-lookup"><span data-stu-id="287a0-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** OR **Real-time detections**.</span></span> 

|<span data-ttu-id="287a0-106">Con ATP piano 2, è possibile vedere:</span><span class="sxs-lookup"><span data-stu-id="287a0-106">With ATP Plan 2, you see:</span></span>  |<span data-ttu-id="287a0-107">Con ATP piano 1, è possibile visualizzare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="287a0-107">With ATP Plan 1, you see:</span></span>  |
|---------|---------|
|![Esplora minacce](media/threatmgmt-explorer.png)      |![Rilevamenti in tempo reale](media/threatmgmt-realtimedetections.png)         |

<span data-ttu-id="287a0-110">Con Esplora risorse (o rilevamenti in tempo reale), si dispone di un report potente che consente al team di operazioni di sicurezza di analizzare e rispondere alle minacce in modo efficace ed efficiente e assomiglia all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="287a0-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently, and it resembles the following image:</span></span> 

![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="287a0-112">Con questo rapporto, è possibile:</span><span class="sxs-lookup"><span data-stu-id="287a0-112">With this report, you can:</span></span>
- [<span data-ttu-id="287a0-113">Vedere malware rilevato dalle funzionalità di sicurezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="287a0-113">See malware detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="287a0-114">Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto</span><span class="sxs-lookup"><span data-stu-id="287a0-114">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="287a0-115">[Avviare un processo di analisi e risposta automatizzato da una visualizzazione in Esplora risorse](#start-automated-investigation-and-response) (Solo ATP piano 2)</span><span class="sxs-lookup"><span data-stu-id="287a0-115">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="287a0-116">... [Esaminare messaggi di posta elettronica dannosi e altro ancora](#more-ways-to-use-explorer-or-real-time-detections)!</span><span class="sxs-lookup"><span data-stu-id="287a0-116">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="new-features-in-real-time-detections"></a><span data-ttu-id="287a0-117">Nuove funzionalità nei rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="287a0-117">New features in real-time detections</span></span>

<span data-ttu-id="287a0-118">Per i clienti di Office 365 ATP Plan 1, il rapporto sui rilevamenti in *tempo reale* è stato precedentemente definito *rapporti in tempo reale*.</span><span class="sxs-lookup"><span data-stu-id="287a0-118">For Office 365 ATP Plan 1 customers, the *real-time detections* report was previously referred to as *real-time reports*.</span></span> <span data-ttu-id="287a0-119">Oltre alla modifica del nome, vengono implementate diverse nuove funzionalità e miglioramenti:</span><span class="sxs-lookup"><span data-stu-id="287a0-119">In addition to the name change, several new features and enhancements are rolling out:</span></span>

- <span data-ttu-id="287a0-120">Nella visualizzazione phishing, è possibile visualizzare ulteriori dettagli sugli URL rilevati tramite [collegamenti sicuri di ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="287a0-120">In the Phish view, you can see more details about detected URLs through [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="287a0-121">I nuovi dettagli e funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="287a0-121">New details and capabilities include:</span></span>
  - <span data-ttu-id="287a0-122">URL nei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="287a0-122">URLs in email messages</span></span>
  - <span data-ttu-id="287a0-123">Filtro in base alle informazioni sull'URL</span><span class="sxs-lookup"><span data-stu-id="287a0-123">Filtering based on URL information</span></span>
  - <span data-ttu-id="287a0-124">Informazioni sugli URL visualizzati nei grafici dati</span><span class="sxs-lookup"><span data-stu-id="287a0-124">URL information displayed in data graphs</span></span>
  - <span data-ttu-id="287a0-125">Data e ora di clic dei dati relativi ai clic nei messaggi</span><span class="sxs-lookup"><span data-stu-id="287a0-125">Time-of-click data about clicks in messages</span></span>

- <span data-ttu-id="287a0-126">Ogni volta che c'è una modifica in un URL fare clic su verdetto, verrà visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="287a0-126">Whenever there's a change in a URL click verdict, you'll see an alert.</span></span> <span data-ttu-id="287a0-127">URL fare clic su verdetti possono variare quando la reputazione di un URL cambia dopo la detonazione o quando un utente protetto da collegamenti sicuri ATP sostituisce un [avviso di collegamenti sicuri ATP](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="287a0-127">URL click verdicts can change when a URL’s reputation changes post-detonation, or when a user who's protected by ATP Safe Links overrides an [ATP Safe Links warning](atp-safe-links-warning-pages.md).</span></span>  
 
<span data-ttu-id="287a0-128">Questi miglioramenti consentono agli amministratori della sicurezza dell'organizzazione di visualizzare più dettagli rispetto a prima.</span><span class="sxs-lookup"><span data-stu-id="287a0-128">These enhancements enable your organization's security administrators to view more details than before.</span></span> <span data-ttu-id="287a0-129">Gli amministratori della sicurezza possono visualizzare le informazioni sui domini URL, gli URL mancanti, fare clic su verdetti e altro ancora, quindi regolare i criteri ATP di Office 365 in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="287a0-129">Security administrators can view information about URL domains, missed URLs, click verdicts, and more, and then adjust Office 365 ATP policies appropriately.</span></span>

> [!NOTE]
> <span data-ttu-id="287a0-130">Anche se queste funzionalità sono in anteprima, i dati URL saranno disponibili per un numero limitato di giorni.</span><span class="sxs-lookup"><span data-stu-id="287a0-130">While these features are in preview, URL data will be available for a limited number of days.</span></span> 

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="287a0-131">Vedere malware rilevato in posta elettronica dalla tecnologia</span><span class="sxs-lookup"><span data-stu-id="287a0-131">See malware detected in email by technology</span></span>

<span data-ttu-id="287a0-132">Si supponga di voler vedere il malware rilevato nella posta elettronica, tramite la tecnologia Office 365.</span><span class="sxs-lookup"><span data-stu-id="287a0-132">Suppose you want to see malware detected in email, by Office 365 technology.</span></span> <span data-ttu-id="287a0-133">A tale scopo, utilizzare la visualizzazione malware di > per la [posta elettronica](threat-explorer-views.md#email--malware) di Esplora risorse (o rilevamenti in tempo reale).</span><span class="sxs-lookup"><span data-stu-id="287a0-133">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="287a0-134">Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > \*\*\*\* minacce (o rilevamenti in **tempo reale**).</span><span class="sxs-lookup"><span data-stu-id="287a0-134">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="287a0-135">In questo esempio viene utilizzato Esplora.</span><span class="sxs-lookup"><span data-stu-id="287a0-135">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="287a0-136">Scegliere**malware** **tramite posta elettronica** > dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="287a0-136">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="287a0-137">![Menu Visualizza per Esplora risorse](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="287a0-137">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>

3. <span data-ttu-id="287a0-138">Fare clic su **mittente**e quindi scegliere**tecnologia di rilevamento**di **base** > .</span><span class="sxs-lookup"><span data-stu-id="287a0-138">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="287a0-139">Le tecnologie di rilevamento sono ora disponibili come filtri per il report.</span><span class="sxs-lookup"><span data-stu-id="287a0-139">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="287a0-140">![Tecnologie di rilevamento di malware](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="287a0-140">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 

4. <span data-ttu-id="287a0-141">Selezionare un'opzione e quindi fare clic sul pulsante **Aggiorna** per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="287a0-141">Select an option, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="287a0-142">![Tecnologia di rilevamento selezionata](media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="287a0-142">![Selected detection technology](media/ExplorerEmailMalwareDetectionTechATP.png)</span></span><br/> 

<span data-ttu-id="287a0-143">Il rapporto viene aggiornato per visualizzare i risultati rilevati dal malware nella posta elettronica, utilizzando l'opzione di tecnologia selezionata.</span><span class="sxs-lookup"><span data-stu-id="287a0-143">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="287a0-144">Da qui, è possibile eseguire un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="287a0-144">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="287a0-145">Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto</span><span class="sxs-lookup"><span data-stu-id="287a0-145">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="287a0-146">Si supponga di voler visualizzare i tentativi di phishing tramite URL nella posta elettronica, incluso un elenco di URL consentiti, bloccati e ignorati.</span><span class="sxs-lookup"><span data-stu-id="287a0-146">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="287a0-147">L'identificazione degli URL che sono stati cliccati richiede la configurazione di [collegamenti sicuri ATP](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="287a0-147">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="287a0-148">Assicurarsi di aver configurato i criteri per i [collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) per la protezione e la registrazione di un clic dei verdetti da ATP Safe Links.</span><span class="sxs-lookup"><span data-stu-id="287a0-148">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span> 

<span data-ttu-id="287a0-149">Per esaminare gli URL di phishing nei messaggi e fare clic su URL nei messaggi di phishing, utilizzare la visualizzazione [phishing > di posta elettronica](threat-explorer-views.md#email--phish) di Esplora risorse (o rilevamenti in tempo reale).</span><span class="sxs-lookup"><span data-stu-id="287a0-149">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="287a0-150">Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > \*\*\*\* minacce (o rilevamenti in **tempo reale**).</span><span class="sxs-lookup"><span data-stu-id="287a0-150">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="287a0-151">In questo esempio viene utilizzato Esplora.</span><span class="sxs-lookup"><span data-stu-id="287a0-151">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="287a0-152">Nel menu **Visualizza** scegliere **posta elettronica** > **phishing**.</span><span class="sxs-lookup"><span data-stu-id="287a0-152">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="287a0-153">![Menu Visualizza per Esplora risorse](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="287a0-153">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>

3. <span data-ttu-id="287a0-154">Fare clic su **sender**e quindi scegliere **urls** > \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="287a0-154">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="287a0-155">Selezionare una o più opzioni, ad esempio **bloccate** e **bloccate**, e quindi fare clic sul pulsante **Aggiorna** che si trova nella stessa riga delle opzioni per applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="287a0-155">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="287a0-156">(Non aggiornare la finestra del browser.)</span><span class="sxs-lookup"><span data-stu-id="287a0-156">(Don't refresh your browser window.)</span></span><br/><span data-ttu-id="287a0-157">![URL e fare clic su verdetti](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="287a0-157">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

    <span data-ttu-id="287a0-158">Il rapporto viene aggiornato per visualizzare due diverse tabelle URL nella scheda URL del rapporto:</span><span class="sxs-lookup"><span data-stu-id="287a0-158">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   1. <span data-ttu-id="287a0-159">Gli URL **principali** sono gli URL contenuti nei messaggi che sono stati filtrati fino a e l'azione di recapito della posta elettronica conta per ogni URL.</span><span class="sxs-lookup"><span data-stu-id="287a0-159">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="287a0-160">Nella visualizzazione posta elettronica di phishing, in genere l'elenco conterrà URL legittimi.</span><span class="sxs-lookup"><span data-stu-id="287a0-160">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="287a0-161">I pirati informatici includono una combinazione di URL buoni e cattivi nei messaggi per cercare di farli recapitare, ma renderà i collegamenti dannosi più interessanti per l'utente da fare clic su.</span><span class="sxs-lookup"><span data-stu-id="287a0-161">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="287a0-162">La tabella degli URL è ordinata in base al numero totale di messaggi di posta elettronica (Nota: questa colonna non viene visualizzata per semplificare la visualizzazione).</span><span class="sxs-lookup"><span data-stu-id="287a0-162">The table of URLs is sorted by total email count (NOTE: This column is not shown to simplify the view).</span></span>

   2. <span data-ttu-id="287a0-163">I **clic principali** sono gli URL con collegamenti sicuri che sono stati selezionati, ordinati in base al numero di clic totale (la colonna non viene visualizzata per semplificare la visualizzazione).</span><span class="sxs-lookup"><span data-stu-id="287a0-163">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="287a0-164">Numeri totali per colonna indicano i collegamenti sicuri fare clic su conteggio verdetto per ogni URL selezionato.</span><span class="sxs-lookup"><span data-stu-id="287a0-164">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="287a0-165">Nella visualizzazione posta elettronica di phishing, questi sono più spesso URL sospetti o dannosi, ma possono includere URL puliti presenti nei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="287a0-165">In the phish email view, these are more often suspicious or malicious URLs, but could include clean URLs that are in phish messages.</span></span> <span data-ttu-id="287a0-166">Gli URL che fanno clic su collegamenti non spostati non verranno visualizzati qui.</span><span class="sxs-lookup"><span data-stu-id="287a0-166">URL clicks on unwrapped links will not show up here.</span></span>
   
   <span data-ttu-id="287a0-167">Le due tabelle degli URL mostrano gli URL principali nei messaggi di posta elettronica di phishing tramite l'azione e la posizione di recapito e visualizzano gli URL che sono stati bloccati (o sono stati visitati nonostante un avviso), in modo da poter capire quali potenziali collegamenti non validi sono stati ricevuti dagli utenti e interagito con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="287a0-167">The two URLs tables show top URLs in phishing emails by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="287a0-168">Da qui, è possibile eseguire un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="287a0-168">From here, you can conduct further analysis.</span></span> <span data-ttu-id="287a0-169">Ad esempio, al di sotto del grafico, è possibile visualizzare gli URL principali nei messaggi di posta elettronica bloccati nell'ambiente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="287a0-169">For example, below the chart, you can see the top URLs in emails that were blocked in your organization's environment.</span></span>
   
   ![URL di Esplora risorse bloccati](media/ExplorerPhishClickVerdictURLs.png)
   
   <span data-ttu-id="287a0-171">Selezionare un URL per visualizzare informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="287a0-171">Select a URL to view more detailed information.</span></span> <span data-ttu-id="287a0-172">Si noti che nella finestra di dialogo URL a comparsa, il filtro nei messaggi di posta elettronica viene rimosso per visualizzare la visualizzazione completa dell'esposizione dell'URL nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="287a0-172">Note that in the URL flyout dialog, the filtering on emails is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="287a0-173">In questo modo è possibile filtrare i messaggi di posta elettronica in Esplora risorse a quelli di cui si è preoccupati, individuare URL specifici che sono potenziali minacce e quindi espandere la propria comprensione dell'esposizione all'URL nell'ambiente (tramite la finestra di dialogo Dettagli URL) senza dover aggiungere filtri URL al Visualizzazione di Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="287a0-173">This lets you filter down emails in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="287a0-174">Esaminare i messaggi di posta elettronica segnalati dagli utenti</span><span class="sxs-lookup"><span data-stu-id="287a0-174">Review email messages reported by users</span></span>

<span data-ttu-id="287a0-175">Si supponga di voler visualizzare i messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come posta indesiderata, non indesiderata o phishing tramite il [componente aggiuntivo per Outlook e Outlook sul Web](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="287a0-175">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="287a0-176">A tale scopo, utilizzare la visualizzazione del [messaggio di posta elettronica > visualizzato dall'utente](threat-explorer-views.md#email--user-reported) di Esplora risorse (o rilevamenti in tempo reale).</span><span class="sxs-lookup"><span data-stu-id="287a0-176">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="287a0-177">Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > \*\*\*\* minacce (o rilevamenti in **tempo reale**).</span><span class="sxs-lookup"><span data-stu-id="287a0-177">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="287a0-178">In questo esempio viene utilizzato Esplora.</span><span class="sxs-lookup"><span data-stu-id="287a0-178">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="287a0-179">Nel menu **Visualizza** scegliere la **posta elettronica** > **segnalata dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="287a0-179">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="287a0-180">![Menu Visualizza per Esplora risorse](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="287a0-180">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>

3. <span data-ttu-id="287a0-181">Fare clic su **mittente**e quindi scegliere**tipo di report**di **base** > .</span><span class="sxs-lookup"><span data-stu-id="287a0-181">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="287a0-182">Selezionare un'opzione, ad esempio **phishing**, e quindi fare clic sul pulsante **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="287a0-182">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="287a0-183">![Phishing segnalati dall'utente](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="287a0-183">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="287a0-184">Il rapporto viene aggiornato per visualizzare i dati relativi ai messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come tentativo di phishing.</span><span class="sxs-lookup"><span data-stu-id="287a0-184">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="287a0-185">È possibile utilizzare queste informazioni per eseguire un'ulteriore analisi e, se necessario, regolare i [criteri di anti-phishing ATP](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="287a0-185">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="287a0-186">Avviare l'analisi e la risposta automatizzata</span><span class="sxs-lookup"><span data-stu-id="287a0-186">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="287a0-187">Le funzionalità di ricerca e risposta automatizzate sono disponibili in **office 365 ATP piano 2** e **Office 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="287a0-187">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="287a0-188">(Nuovo!) L' [analisi e la risposta automatizzate](automated-investigation-response-office.md) sono in grado di salvare il team delle operazioni di sicurezza molto tempo e sforzi per analizzare e mitigare gli attacchi cibernetici.</span><span class="sxs-lookup"><span data-stu-id="287a0-188">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="287a0-189">Oltre a configurare gli avvisi che possono attivare un PlayBook per la sicurezza, è possibile avviare un processo di analisi e risposta automatizzato da una visualizzazione di Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="287a0-189">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="287a0-190">Per ulteriori informazioni, vedere [esempio: un amministratore della sicurezza attiva un'analisi da Esplora risorse](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span><span class="sxs-lookup"><span data-stu-id="287a0-190">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="287a0-191">Altre modalità di utilizzo di Esplora risorse (o rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="287a0-191">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="287a0-192">Oltre agli scenari descritti in questo articolo, sono disponibili molte altre opzioni per la creazione di report con Esplora risorse (o rilevamenti in tempo reale).</span><span class="sxs-lookup"><span data-stu-id="287a0-192">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span> 
- [<span data-ttu-id="287a0-193">Identificare e analizzare i messaggi di posta elettronica dannosi recapitati</span><span class="sxs-lookup"><span data-stu-id="287a0-193">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="287a0-194">Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="287a0-194">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="287a0-195">Ottenere una panoramica delle visualizzazioni in Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="287a0-195">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="287a0-196">Licenze e autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="287a0-196">Required licenses and permissions</span></span>

<span data-ttu-id="287a0-197">È necessario disporre di [Office 365 ATP](office-365-atp.md) per ottenere rilevamenti di Esplora risorse o in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="287a0-197">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>
- <span data-ttu-id="287a0-198">Explorer è incluso in Office 365 ATP piano 2.</span><span class="sxs-lookup"><span data-stu-id="287a0-198">Explorer is included in Office 365 ATP Plan 2.</span></span> 
- <span data-ttu-id="287a0-199">Il rapporto sui rilevamenti in tempo reale è incluso in Office 365 ATP Plan 1.</span><span class="sxs-lookup"><span data-stu-id="287a0-199">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>

<span data-ttu-id="287a0-200">Per visualizzare e utilizzare esplorazioni o rilevamenti in tempo reale, è necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o a un lettore di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="287a0-200">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="287a0-201">Per il centro &amp; sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="287a0-201">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="287a0-202">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="287a0-202">Organization Management</span></span>
    - <span data-ttu-id="287a0-203">Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ())</span><span class="sxs-lookup"><span data-stu-id="287a0-203">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="287a0-204">Lettore di sicurezza</span><span class="sxs-lookup"><span data-stu-id="287a0-204">Security Reader</span></span>

- <span data-ttu-id="287a0-205">Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="287a0-205">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="287a0-206">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="287a0-206">Organization Management</span></span>
    - <span data-ttu-id="287a0-207">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="287a0-207">View-only Organization Management</span></span>
    - <span data-ttu-id="287a0-208">Ruolo Destinatari di sola lettura</span><span class="sxs-lookup"><span data-stu-id="287a0-208">View-Only Recipients role</span></span>
    - <span data-ttu-id="287a0-209">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="287a0-209">Compliance Management</span></span>

<span data-ttu-id="287a0-210">Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="287a0-210">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="287a0-211">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="287a0-211">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="287a0-212">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="287a0-212">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  