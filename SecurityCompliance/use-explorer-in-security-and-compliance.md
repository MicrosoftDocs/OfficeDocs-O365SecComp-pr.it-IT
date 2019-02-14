---
title: Utilizzare Esplora in sicurezza &amp; centro conformità
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection: M365-security-compliance
description: Informazioni sulle soluzioni (denominato anche Explorer rischio) la sicurezza &amp; centro conformità.
ms.openlocfilehash: 16f5b15c6993301f4f324f4b84c3b6e61f255e0f
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995117"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="742d9-103">Utilizzare Esplora in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="742d9-103">Use Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="742d9-p101">Se l'organizzazione dispone di [Business Intelligence di Office 365 rischio](office-365-ti.md)e si dispone delle autorizzazioni necessarie, è possibile utilizzare Explorer per identificare e l'analisi delle minacce. Ad esempio, è possibile identificare ed eliminare dannoso posta elettronica che è stato recapitato o vedere malware che è stato rilevato dalla funzionalità di protezione di Office 365. Explorer (anche noto come Explorer rischio) è un potente quasi in tempo reale report nella protezione &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="742d9-p101">If your organization has [Office 365 Threat Intelligence](office-365-ti.md), and you have the necessary permissions, you can use Explorer to identify and analyze threats. For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features. Explorer (also referred to as Threat Explorer) is a powerful near real-time report in the Security &amp; Compliance Center.</span></span>
  
![Passare a gestione rischio \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="742d9-108">Utilizzare Esplora, in sicurezza &amp; centro conformità, passare a **gestione delle minacce** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="742d9-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="742d9-p102">A partire da febbraio 2019 e distribuzione sui prossimi mesi, Business Intelligence di Office 365 rischio sta diventando Office 365 avanzate Threat Protection piano 2, le funzionalità di protezione aggiuntive rischio. Per ulteriori informazioni, vedere [i piani Office 365 avanzate Threat Protection e i prezzi](https://products.office.com/exchange/advance-threat-protection) e [Office 365 avanzate Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="742d9-p102">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="742d9-111">Panoramica delle soluzioni</span><span class="sxs-lookup"><span data-stu-id="742d9-111">Explorer overview</span></span>

<span data-ttu-id="742d9-p103">Explorer vengono visualizzate informazioni su sospetto malware nella posta elettronica e i file in Office 365, nonché altri minacce per la protezione e rischi per la propria organizzazione. Quando si apre Explorer, la visualizzazione predefinita mostra i rilevamenti di malware da antivirus per gli ultimi 7 giorni. Explorer è anche possibile visualizzare sicurezza funzionalità di protezione in Office 365, inclusi [Collegamenti sicuri](atp-safe-links.md) e [Gli allegati sicuri](atp-safe-attachments.md) e possono essere modificati per visualizzare i dati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="742d9-p103">Explorer displays information about suspected malware in email and files in Office 365, as well as other security threats and risks to your organization. When you first open Explorer, the default view shows malware detections from antivirus for the past 7 days. Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span>
  
![Explorer consente di visualizzare informazioni su malware principali e gli utenti di destinazione](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
<span data-ttu-id="742d9-116">Utilizzare il menu Visualizza per modificare le informazioni da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="742d9-116">Use the View menu to change what information is displayed.</span></span>
  
![Dal menu Visualizza per elenco delle cartelle](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
<span data-ttu-id="742d9-p104">Explorer filtro diverse e l'esecuzione di query funzionalità che consentono di penetrare nei dettagli, ad esempio inizio destinate agli utenti, le famiglie di malware principali e altro ancora. Ogni tipo di rapporto sono disponibili diversi modi per visualizzare ed esplorare dati.</span><span class="sxs-lookup"><span data-stu-id="742d9-p104">Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, and more. Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="742d9-p105">Non utilizzare caratteri jolly, ad esempio un asterisco (\*) o un punto interrogativo (?), con Explorer. Quando esegue una ricerca nel campo oggetto per i messaggi di posta elettronica, Explorer eseguirà corrispondenza e rendimento risultati parziali simili a una ricerca con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="742d9-p105">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), with Explorer. When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

## <a name="email--malware"></a><span data-ttu-id="742d9-122">Messaggio di posta elettronica \> Malware</span><span class="sxs-lookup"><span data-stu-id="742d9-122">Email \> Malware</span></span>

<span data-ttu-id="742d9-123">Consente di visualizzare i messaggi di posta elettronica identificati come contenente malware.</span><span class="sxs-lookup"><span data-stu-id="742d9-123">This view shows email messages identified as containing malware.</span></span>  

<span data-ttu-id="742d9-124">Visualizzare le informazioni del grafico dalla tecnologia di rilevamento (come malware rilevato), dominio mittente, mittente IP, lo stato di protezione (azioni effettuate dal criteri in Office 365 e funzionalità di protezione di rischio) e dalla famiglia di malware.</span><span class="sxs-lookup"><span data-stu-id="742d9-124">View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).</span></span>  

![Visualizzare i dati relativi a malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

<span data-ttu-id="742d9-126">Sotto il grafico, visualizzare i dettagli relativi famiglie di malware principali, top destinate agli utenti e ulteriori dettagli sui messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="742d9-126">Below the chart, view details about top malware families, top targeted users, and more details about specific messages.</span></span> 

## <a name="email--phish"></a><span data-ttu-id="742d9-127">Messaggio di posta elettronica \> Rilevatore attività</span><span class="sxs-lookup"><span data-stu-id="742d9-127">Email \> Phish</span></span>

<span data-ttu-id="742d9-128">Consente di visualizzare i messaggi di posta elettronica identificati come tentativi di phishing.</span><span class="sxs-lookup"><span data-stu-id="742d9-128">This view shows email messages identified as phishing attempts.</span></span>  

<span data-ttu-id="742d9-129">Visualizzare le informazioni sul dominio mittente, IP mittente e lo stato di protezione (azioni effettuate dal criteri in Office 365 e funzionalità di protezione di rischio).</span><span class="sxs-lookup"><span data-stu-id="742d9-129">View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).</span></span> 

![Visualizzare i dati sulla posta identificata come tentativi di phishing](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

<span data-ttu-id="742d9-131">Sotto il grafico consente di visualizzare ulteriori dettagli sui messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="742d9-131">Below the chart, view more details about specific messages.</span></span> 

## <a name="email--user-reported"></a><span data-ttu-id="742d9-132">Messaggio di posta elettronica \> segnalati dagli utenti</span><span class="sxs-lookup"><span data-stu-id="742d9-132">Email \> User-reported</span></span>

<span data-ttu-id="742d9-133">Consente di visualizzare messaggio di posta elettronica che gli utenti hanno segnalato come posta indesiderata, non indesiderata o posta elettronica di phishing.</span><span class="sxs-lookup"><span data-stu-id="742d9-133">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>  

<span data-ttu-id="742d9-134">Consente di visualizzare informazioni per il tipo di report (determinazione dell'utente che è stata la posta indesiderata, non indesiderata o per attività di phishing) e per motivi di recapito (motivi per cui sono diventato posta elettronica in una posizione specifica, ad esempio un criterio di filtro posta indesiderata, una regola del flusso di posta, un elenco di mittenti bloccati, un elenco dei mittenti, ecc.).</span><span class="sxs-lookup"><span data-stu-id="742d9-134">View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).</span></span>  

![Visualizzare i dati sugli utenti di posta elettronica segnalati come posta indesiderata, non indesiderata o phishing](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

<span data-ttu-id="742d9-136">Sotto il grafico consente di visualizzare ulteriori dettagli sui messaggi di posta elettronica specifico, ad esempio l'oggetto del messaggio, indirizzo IP del mittente, l'utente che ha segnalato il messaggio come posta indesiderata, non posta indesiderata, o per attività di phishing e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="742d9-136">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

## <a name="email--all-mail"></a><span data-ttu-id="742d9-137">Messaggio di posta elettronica \> tutta la posta</span><span class="sxs-lookup"><span data-stu-id="742d9-137">Email \> All mail</span></span>

<span data-ttu-id="742d9-138">Questo visualizzazioni Mostra una visualizzazione di tutti i backup delle attività di posta elettronica, incluso posta identificata come dannose scadenza phishing o malware, e di tutti i messaggi non intenzionale (normale posta elettronica, posta indesiderata e posta elettronica in blocco).</span><span class="sxs-lookup"><span data-stu-id="742d9-138">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="742d9-139">Se si verifica un errore indicante **Too quantità di dati da visualizzare**, aggiungere un filtro e, se necessario, limitare l'intervallo di date si stanno visualizzando.</span><span class="sxs-lookup"><span data-stu-id="742d9-139">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="742d9-p106">Per applicare un filtro, scegliere **mittente**, selezionare un elemento nell'elenco e quindi fare clic sul pulsante Aggiorna. In questo esempio viene utilizzata **la tecnologia di rilevamento** come filtro (sono disponibili diverse opzioni disponibili). Visualizzare le informazioni di mittente, dominio del mittente, destinatari, subject, nome del file allegato, famiglia di malware, lo stato di protezione (azioni effettuate dal criteri in Office 365 e funzionalità di protezione di rischio), la tecnologia di rilevamento (come malware rilevato), e ulteriori.</span><span class="sxs-lookup"><span data-stu-id="742d9-p106">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button. In our example, we used **Detection technology** as a filter (there are several options available). View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![Visualizzare i dati sulla posta elettronica rilevato dalla tecnologia di rilevamento](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="742d9-144">Sotto il grafico consente di visualizzare ulteriori dettagli sui messaggi di posta elettronica specifico, ad esempio l'oggetto del messaggio, destinatario, mittente, lo stato e così via.</span><span class="sxs-lookup"><span data-stu-id="742d9-144">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="742d9-145">Contenuto \> Malware</span><span class="sxs-lookup"><span data-stu-id="742d9-145">Content \> Malware</span></span>

<span data-ttu-id="742d9-146">Consente di visualizzare i file che sono stati identificati come dannoso in SharePoint Online, OneDrive for Business e Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="742d9-146">This view shows files that were identified as malicious in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="742d9-147">Visualizza informazioni dalla tecnologia di rilevamento della famiglia, malware (come malware rilevato) e il carico di lavoro (OneDrive, SharePoint o team).</span><span class="sxs-lookup"><span data-stu-id="742d9-147">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![Visualizzare i dati relativi a malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="742d9-149">Sotto il grafico consente di visualizzare ulteriori informazioni sui file specifici, ad esempio il nome del file allegato, carico di lavoro, le dimensioni del file che ha modificato il file e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="742d9-149">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="new-click-to-filter-capabilities"></a><span data-ttu-id="742d9-150">(Nuovo)! Fare clic su filtro a funzionalità</span><span class="sxs-lookup"><span data-stu-id="742d9-150">(New!) Click-to-filter capabilities</span></span>

<span data-ttu-id="742d9-p107">Nuova a soluzioni è la possibilità di fare clic su per filtrare l'elenco. A partire da ritardo 2018 maggio, quando si fa clic su un elemento nella legenda, che l'elemento diventa un filtro per il report. Si supponga ad esempio che siamo la visualizzazione di Malware in soluzioni:</span><span class="sxs-lookup"><span data-stu-id="742d9-p107">New to Explorer is the ability to click to filter. Beginning in late May 2018, when you click an item in the legend, that item becomes a filter for the report. For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![Passare a gestione rischio \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="742d9-155">Fare clic su **Detonazione degli strumenti di analisi** nei risultati grafico in una visualizzazione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="742d9-155">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![Explorer filtrato in modo da visualizzare solo i risultati detonazione ATO](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="742d9-p108">In questa visualizzazione ora stiamo dati per i file che sono stati detonated per [Gli allegati sicuri di Office 365 degli strumenti di analisi](atp-safe-attachments.md). Sotto il grafico, è possibile visualizzare i dettagli relativi messaggi di posta elettronica specifico con allegati che sono stati rilevati per gli allegati sicuri degli strumenti di analisi.</span><span class="sxs-lookup"><span data-stu-id="742d9-p108">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![Informazioni specifiche sui messaggi di posta elettronica con allegati rilevati](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="742d9-160">Selezionando uno o più elementi viene attivato il menu **Azioni** , che è disponibili diverse opzioni per la scelta per gli elementi selezionati da.</span><span class="sxs-lookup"><span data-stu-id="742d9-160">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![Seleziona una voce attiva dal menu Azioni](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="742d9-162">La possibilità di filtrare un clic e accedere a informazioni specifiche possibile evitare molto tempo nell'analisi dei rischi.</span><span class="sxs-lookup"><span data-stu-id="742d9-162">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>
  
## <a name="how-do-i-get-explorer"></a><span data-ttu-id="742d9-163">Come ottenere Explorer</span><span class="sxs-lookup"><span data-stu-id="742d9-163">How do I get Explorer?</span></span>

<span data-ttu-id="742d9-164">Soluzioni sono incluse funzionalità di [Business Intelligence di Office 365 rischio](office-365-ti.md).</span><span class="sxs-lookup"><span data-stu-id="742d9-164">Explorer is included in [Office 365 Threat Intelligence](office-365-ti.md).</span></span> 

<span data-ttu-id="742d9-p109">È necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o lettore di sicurezza, per poter visualizzare e utilizzare Explorer. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="742d9-p109">You must have appropriate permissions, such as those granted to a security administrator or security reader, in order to view and use Explorer. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="742d9-167">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="742d9-167">Related topics</span></span>

[<span data-ttu-id="742d9-168">Report e sui concetti di Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="742d9-168">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="742d9-169">Trovare e analizzare dannoso posta elettronica che è stato recapitato (Business Intelligence rischio di Office 365)</span><span class="sxs-lookup"><span data-stu-id="742d9-169">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
  
[<span data-ttu-id="742d9-170">Protezione antispam e antimalware in Office 365</span><span class="sxs-lookup"><span data-stu-id="742d9-170">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  

