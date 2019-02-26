---
title: Utilizzo di Esplora risorse nel &amp; Centro sicurezza e conformità
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
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Informazioni su Explorer (denominato anche Esplora minacce) nel centro sicurezza &amp; e conformità.
ms.openlocfilehash: 4a28626d0e643d7a7b96a34656e7678c71a86c66
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241968"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="37a1a-103">Utilizzo di Esplora risorse nel &amp; Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="37a1a-103">Use Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="37a1a-p101">Se l'organizzazione dispone di [Office 365 Threat Intelligence](office-365-ti.md)ed è necessario disporre delle autorizzazioni necessarie, è possibile utilizzare Esplora risorse per identificare e analizzare le minacce. Ad esempio, è possibile identificare ed eliminare messaggi di posta elettronica dannosi che sono stati recapitati oppure vedere malware rilevati dalle funzionalità di sicurezza di Office 365. Explorer (noto anche come Threat Explorer) è un rapporto potente in tempo reale vicino al centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="37a1a-p101">If your organization has [Office 365 Threat Intelligence](office-365-ti.md), and you have the necessary permissions, you can use Explorer to identify and analyze threats. For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features. Explorer (also referred to as Threat Explorer) is a powerful near real-time report in the Security &amp; Compliance Center.</span></span>
  
![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="37a1a-108">Per utilizzare Esplora risorse, nel centro &amp; sicurezza e conformità, accedere a **gestione** \> \*\*\*\* minacce.</span><span class="sxs-lookup"><span data-stu-id="37a1a-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37a1a-p102">A partire da febbraio 2019 e distribuita nei prossimi mesi, Office 365 Threat Intelligence sta diventando Office 365 Advanced Threat Protection Plan 2, con ulteriori funzionalità di protezione dalle minacce. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="37a1a-p102">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="37a1a-111">Panoramica di Esplora risorse</span><span class="sxs-lookup"><span data-stu-id="37a1a-111">Explorer overview</span></span>

<span data-ttu-id="37a1a-p103">In Esplora risorse vengono visualizzate informazioni relative al sospetto di malware nei messaggi di posta elettronica e nei file di Office 365, nonché altre minacce e rischi per la sicurezza per l'organizzazione. Quando si apre Explorer per la prima volta, la visualizzazione predefinita Visualizza i rilevamenti di malware provenienti da antivirus negli ultimi 7 giorni. Esplora risorse può anche mostrare le funzionalità di protezione della sicurezza in Office 365, inclusi i [collegamenti sicuri](atp-safe-links.md) e gli [allegati sicuri](atp-safe-attachments.md) e può essere modificato in modo da visualizzare i dati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="37a1a-p103">Explorer displays information about suspected malware in email and files in Office 365, as well as other security threats and risks to your organization. When you first open Explorer, the default view shows malware detections from antivirus for the past 7 days. Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span>
  
![Explorer visualizza informazioni sui principali utenti di malware e di destinazione](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
<span data-ttu-id="37a1a-116">Utilizzare il menu Visualizza per modificare le informazioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="37a1a-116">Use the View menu to change what information is displayed.</span></span>
  
![Menu Visualizza per Esplora risorse](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
<span data-ttu-id="37a1a-p104">In Esplora sono disponibili diverse funzionalità di filtro e query che consentono di eseguire il drill-down nei dettagli, ad esempio gli utenti più mirati, le famiglie di malware principali e altro ancora. Ogni tipo di report offre una vasta gamma di modi per visualizzare ed esplorare i dati.</span><span class="sxs-lookup"><span data-stu-id="37a1a-p104">Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, and more. Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37a1a-p105">Non utilizzare caratteri jolly, ad esempio un asterisco (\*) o un punto interrogativo (?), con Esplora risorse. Quando si esegue una ricerca nel campo Subject per i messaggi di posta elettronica, Explorer eseguirà una corrispondenza parziale e restituisce risultati simili a quelli di una ricerca con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="37a1a-p105">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), with Explorer. When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

## <a name="email--malware"></a><span data-ttu-id="37a1a-122">Malware \> per la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="37a1a-122">Email \> Malware</span></span>

<span data-ttu-id="37a1a-123">Questa visualizzazione Mostra i messaggi di posta elettronica identificati come contenenti malware.</span><span class="sxs-lookup"><span data-stu-id="37a1a-123">This view shows email messages identified as containing malware.</span></span>  

<span data-ttu-id="37a1a-124">Visualizzare le informazioni nel grafico per la famiglia di malware, il dominio del mittente, l'IP del mittente, lo stato di protezione (azioni intraprese dalle caratteristiche e i criteri di protezione dalle minacce in Office 365) e la tecnologia di rilevamento (come è stato rilevato il malware).</span><span class="sxs-lookup"><span data-stu-id="37a1a-124">View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).</span></span>  

![Visualizzare i dati relativi al malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

<span data-ttu-id="37a1a-126">Al di sotto del grafico, visualizzare i dettagli relativi alle famiglie di malware principali, agli utenti più mirati e maggiori dettagli su messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="37a1a-126">Below the chart, view details about top malware families, top targeted users, and more details about specific messages.</span></span> 

## <a name="email--phish"></a><span data-ttu-id="37a1a-127">Phishing \> di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="37a1a-127">Email \> Phish</span></span>

<span data-ttu-id="37a1a-128">Questa visualizzazione Mostra i messaggi di posta elettronica identificati come tentativi di phishing.</span><span class="sxs-lookup"><span data-stu-id="37a1a-128">This view shows email messages identified as phishing attempts.</span></span>  

<span data-ttu-id="37a1a-129">Visualizzare le informazioni in base al dominio del mittente, all'IP del mittente e allo stato di protezione (azioni intraprese dalle caratteristiche e dai criteri di protezione delle minacce in Office 365).</span><span class="sxs-lookup"><span data-stu-id="37a1a-129">View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).</span></span> 

![Visualizzare i dati relativi alla posta elettronica identificata come tentativi di phishing](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

<span data-ttu-id="37a1a-131">Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="37a1a-131">Below the chart, view more details about specific messages.</span></span> 

## <a name="email--user-reported"></a><span data-ttu-id="37a1a-132">Messaggio \> di posta elettronica visualizzato dall'utente</span><span class="sxs-lookup"><span data-stu-id="37a1a-132">Email \> User-reported</span></span>

<span data-ttu-id="37a1a-133">Questa visualizzazione Mostra la posta elettronica che gli utenti hanno segnalato come posta indesiderata, non indesiderata o phishing.</span><span class="sxs-lookup"><span data-stu-id="37a1a-133">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>  

<span data-ttu-id="37a1a-134">Visualizzare le informazioni in base al tipo di rapporto (la determinazione dell'utente che il messaggio di posta elettronica è stato indesiderato, non indesiderato o phishing) e per motivo di recapito (motivi per cui la posta elettronica è stata indirizzata a una posizione specifica, ad esempio un criterio di filtro per la posta indesiderata, una regola del flusso, un elenco dei mittenti bloccati ecc.).</span><span class="sxs-lookup"><span data-stu-id="37a1a-134">View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).</span></span>  

![Visualizzare i dati relativi agli utenti di posta elettronica riportati come posta indesiderata, non indesiderata o phishing](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

<span data-ttu-id="37a1a-136">Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, l'indirizzo IP del mittente, l'utente che ha segnalato il messaggio come posta indesiderata, non indesiderata o phishing e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="37a1a-136">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

## <a name="email--all-mail"></a><span data-ttu-id="37a1a-137">Posta \> elettronica tutti i messaggi</span><span class="sxs-lookup"><span data-stu-id="37a1a-137">Email \> All mail</span></span>

<span data-ttu-id="37a1a-138">Questa visualizzazione Mostra una panoramica completa dell'attività di posta elettronica, inclusi i messaggi di posta elettronica identificati come dannosi a causa di phishing o malware, nonché tutti i messaggi non dannosi (posta elettronica normale, posta indesiderata e messaggi in blocco).</span><span class="sxs-lookup"><span data-stu-id="37a1a-138">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="37a1a-139">Se viene visualizzato un messaggio di errore in cui vengono letti **troppi dati da visualizzare**, aggiungere un filtro e, se necessario, limitare l'intervallo di date che si sta visualizzando.</span><span class="sxs-lookup"><span data-stu-id="37a1a-139">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="37a1a-p106">Per applicare un filtro, scegliere **mittente**, selezionare un elemento nell'elenco e quindi fare clic sul pulsante Aggiorna. In questo esempio, è stata utilizzata la **tecnologia di rilevamento** come filtro (sono disponibili diverse opzioni). Visualizzare le informazioni per mittente, dominio del mittente, destinatari, oggetto, nome file allegato, famiglia di malware, stato di protezione (azioni intraprese dalle caratteristiche e dai criteri di protezione dalle minacce in Office 365), tecnologia di rilevamento (come è stato rilevato il malware) e più.</span><span class="sxs-lookup"><span data-stu-id="37a1a-p106">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button. In our example, we used **Detection technology** as a filter (there are several options available). View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![Visualizzare i dati relativi alla posta elettronica individuata mediante tecnologia di rilevamento](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="37a1a-144">Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, il destinatario, il mittente, lo stato e così via.</span><span class="sxs-lookup"><span data-stu-id="37a1a-144">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="37a1a-145">Malware \> contenuto</span><span class="sxs-lookup"><span data-stu-id="37a1a-145">Content \> Malware</span></span>

<span data-ttu-id="37a1a-146">Questa visualizzazione Mostra i file che sono stati identificati come dannosi in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="37a1a-146">This view shows files that were identified as malicious in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="37a1a-147">Consente di visualizzare le informazioni per la famiglia di malware, la tecnologia di rilevamento (come è stato rilevato il malware) e il carico di lavoro (OneDrive, SharePoint o Teams).</span><span class="sxs-lookup"><span data-stu-id="37a1a-147">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![Visualizzare i dati relativi al malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="37a1a-149">Al di sotto del grafico, visualizzare ulteriori dettagli sui file specifici, ad esempio il nome del file degli allegati, il carico di lavoro, le dimensioni, l'ultimo che ha modificato il file e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="37a1a-149">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="new-click-to-filter-capabilities"></a><span data-ttu-id="37a1a-150">(Nuovo!) Funzionalità di clic su filtro</span><span class="sxs-lookup"><span data-stu-id="37a1a-150">(New!) Click-to-filter capabilities</span></span>

<span data-ttu-id="37a1a-p107">Nuovo in Esplora risorse è la possibilità di fare clic per filtrare. A partire dalla fine di maggio 2018, quando si fa clic su un elemento nella legenda, l'elemento diventa un filtro per il report. Si supponga, ad esempio, di esaminare la visualizzazione malware in Esplora risorse:</span><span class="sxs-lookup"><span data-stu-id="37a1a-p107">New to Explorer is the ability to click to filter. Beginning in late May 2018, when you click an item in the legend, that item becomes a filter for the report. For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="37a1a-155">Facendo clic su **detonaZione ATP** in questo grafico viene visualizzato un risultato simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="37a1a-155">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![Filtro Esplora risorse per visualizzare solo i risultati di detonazione ATO](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="37a1a-p108">In questa visualizzazione, vengono ora esaminati i dati per i file che sono stati detonati da [allegati sicuri di Office 365 ATP](atp-safe-attachments.md). Al di sotto del grafico, è possibile visualizzare i dettagli relativi a messaggi di posta elettronica specifici che sono stati rilevati da allegati sicuri di ATP.</span><span class="sxs-lookup"><span data-stu-id="37a1a-p108">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![Dettagli specifici sui messaggi di posta elettronica con allegati rilevati](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="37a1a-160">La selezione di uno o più elementi attiva il menu **azioni** , che offre diverse opzioni tra cui scegliere per gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="37a1a-160">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![La selezione di un elemento attiva il menu azioni](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="37a1a-162">La possibilità di filtrare i dati in un clic e di passare a dettagli specifici consente di risparmiare molto tempo nell'analisi delle minacce.</span><span class="sxs-lookup"><span data-stu-id="37a1a-162">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>
  
## <a name="how-do-i-get-explorer"></a><span data-ttu-id="37a1a-163">Come è possibile ottenere Esplora risorse?</span><span class="sxs-lookup"><span data-stu-id="37a1a-163">How do I get Explorer?</span></span>

<span data-ttu-id="37a1a-164">Explorer è incluso in [Office 365 Threat Intelligence](office-365-ti.md).</span><span class="sxs-lookup"><span data-stu-id="37a1a-164">Explorer is included in [Office 365 Threat Intelligence](office-365-ti.md).</span></span> 

<span data-ttu-id="37a1a-p109">Per visualizzare e utilizzare Esplora risorse, è necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o a un lettore di sicurezza. Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="37a1a-p109">You must have appropriate permissions, such as those granted to a security administrator or security reader, in order to view and use Explorer. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="37a1a-167">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="37a1a-167">Related topics</span></span>

[<span data-ttu-id="37a1a-168">Report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="37a1a-168">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="37a1a-169">Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Threat Intelligence)</span><span class="sxs-lookup"><span data-stu-id="37a1a-169">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
  
[<span data-ttu-id="37a1a-170">Protezione antispam e antimalware in Office 365</span><span class="sxs-lookup"><span data-stu-id="37a1a-170">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  

