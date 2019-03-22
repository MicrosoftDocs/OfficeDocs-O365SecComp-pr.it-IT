---
title: Indagine automatizzata e risposta (aria) con Office 365 Threat Intelligence
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Informazioni sulle funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection.
ms.openlocfilehash: c2d5acd0bf26dc28b30f26488adf47de2c834fb6
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2019
ms.locfileid: "30736369"
---
# <a name="automated-investigation-and-response-air-with-office-365-threat-intelligence"></a><span data-ttu-id="67d80-103">Indagine automatizzata e risposta (aria) con Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="67d80-103">Automated Investigation and Response (AIR) with Office 365 Threat Intelligence</span></span>

<span data-ttu-id="67d80-104">Indagine automatizzata e risposta (AIR) (prossimamente a [Office 365 Threat Investigation and response capabilities](office-365-ti.md)) consente di eseguire indagini automatizzate e il risanamento di minacce ben note che esistono oggi.</span><span class="sxs-lookup"><span data-stu-id="67d80-104">Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="67d80-105">Leggere questo articolo per ottenere una panoramica di AIR e in che modo può essere utile per l'organizzazione attenuare le minacce in modo più efficace ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="67d80-105">Read this article to get an overview of AIR and how it can help your organization mitigate threats more effectively and efficiently.</span></span> <span data-ttu-id="67d80-106">Per ulteriori informazioni sulla disponibilità dell'aria, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="67d80-106">Tolearn more about when AIR will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="67d80-107">Avvisi</span><span class="sxs-lookup"><span data-stu-id="67d80-107">Alerts</span></span>

<span data-ttu-id="67d80-108">Gli [avvisi](alert-policies.md#viewing-alerts) rappresentano trigger per i flussi di lavoro del team di operazioni di sicurezza per la risposta agli incidenti.</span><span class="sxs-lookup"><span data-stu-id="67d80-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for Security Operations team workflows for incident response.</span></span> <span data-ttu-id="67d80-109">Definire la priorità del set di avvisi corretti per l'analisi e verificare che non vi siano minacce non indirizzate.</span><span class="sxs-lookup"><span data-stu-id="67d80-109">Prioritizing the right set of alerts for investigation while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="67d80-110">Quando le indagini sugli avvisi vengono eseguite manualmente, i team delle operazioni di sicurezza devono cercare e correlare le entità (ad esempio, il contenuto, i dispositivi e gli utenti) a rischio di minacce.</span><span class="sxs-lookup"><span data-stu-id="67d80-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="67d80-111">Tali attività e flussi di lavoro richiedono molto tempo e coinvolgono più strumenti e sistemi.</span><span class="sxs-lookup"><span data-stu-id="67d80-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="67d80-112">Con AIR, l'analisi e la risposta vengono automatizzate in avvisi chiave per la sicurezza e la gestione delle minacce che attivano automaticamente gli schemi di risposta alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="67d80-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="67d80-113">per visualizzare gli avvisi, nel centro conformità & sicurezza di Office 365 scegliere **avvisi** > **visualizza avvisi**.</span><span class="sxs-lookup"><span data-stu-id="67d80-113">To view alerts, in the Office 365 Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span>

![Avvisi relativi al collegamento alle indagini](media/air-alerts-page-details.png) 

<span data-ttu-id="67d80-115">Selezionare un avviso per visualizzare i dettagli, quindi utilizzare il collegamento **Visualizza analisi** per passare all' [analisi](#investigation-graph)corrispondente.</span><span class="sxs-lookup"><span data-stu-id="67d80-115">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span>

## <a name="security-playbooks"></a><span data-ttu-id="67d80-116">Schemi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="67d80-116">Security playbooks</span></span>

<span data-ttu-id="67d80-117">Gli schemi di sicurezza sono criteri di back-end che sono al centro dell'automazione in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="67d80-117">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="67d80-118">Gli schemi di sicurezza forniti in AIR sono basati su scenari comuni di sicurezza del mondo reale.</span><span class="sxs-lookup"><span data-stu-id="67d80-118">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="67d80-119">Un playbook di sicurezza viene avviato automaticamente quando un avviso viene attivato all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="67d80-119">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="67d80-120">Dopo che l'avviso è stato attivato, l'oggetto PlayBook associato viene eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="67d80-120">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="67d80-121">Il PlayBook esegue un'indagine, esaminando tutti i metadati associati (inclusi i messaggi di posta elettronica, gli utenti, i soggetti, i mittenti e così via) e, in base ai risultati, consiglia una serie di azioni che il team di sicurezza dell'organizzazione può intraprendere per il controllo e l'attenuazione la minaccia.</span><span class="sxs-lookup"><span data-stu-id="67d80-121">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.) and, based on its findings, recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="67d80-122">Gli schemi di sicurezza che otterrete con AIR sono studiati per affrontare le minacce più frequenti che le organizzazioni devono affrontare oggi.</span><span class="sxs-lookup"><span data-stu-id="67d80-122">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="67d80-123">Sono basati sull'input dalle operazioni di sicurezza e dai team di risposta agli incidenti, compresi quelli che aiutano a difendere le risorse Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67d80-123">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="67d80-124">Gli schemi di sicurezza vengono implementati in fasi</span><span class="sxs-lookup"><span data-stu-id="67d80-124">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="67d80-125">Come parte di AIR, i PlayBook di sicurezza stanno per essere implementati in fasi</span><span class="sxs-lookup"><span data-stu-id="67d80-125">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="67d80-126">**Fase 1 (2019 aprile)**: i PlayBook includono suggerimenti per la revisione e l'approvazione da parte degli amministratori della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="67d80-126">**Phase 1 (April 2019)**: Playbooks include recommendations that security administrators review and approve.</span></span> 

- <span data-ttu-id="67d80-127">**Fase 2 (2019 giugno)**: gli amministratori della sicurezza avranno la possibilità di consentire ai PlayBook di sicurezza di intervenire automaticamente, senza interazione amministrativa.</span><span class="sxs-lookup"><span data-stu-id="67d80-127">**Phase 2 (June 2019)**: Security administrators will have the option to allow security playbooks to take action automatically, without administrative interaction.</span></span>

<span data-ttu-id="67d80-128">La fase 1 includerà gli schemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="67d80-128">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="67d80-129">Messaggio phishing visualizzato dall'utente</span><span class="sxs-lookup"><span data-stu-id="67d80-129">User-reported phish message</span></span>
- <span data-ttu-id="67d80-130">URL fare clic su modifica verdetto e sostituzione del blocco di collegamenti sicuri ATP</span><span class="sxs-lookup"><span data-stu-id="67d80-130">URL click verdict change and ATP Safe Links block override</span></span>
- <span data-ttu-id="67d80-131">Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="67d80-131">Malware ZAP</span></span>
- <span data-ttu-id="67d80-132">Phishing ZAP</span><span class="sxs-lookup"><span data-stu-id="67d80-132">Phish ZAP</span></span>
- <span data-ttu-id="67d80-133">Indagini manuali (tramite Esplora risorse)</span><span class="sxs-lookup"><span data-stu-id="67d80-133">Manual investigations (using Explorer)</span></span>

<span data-ttu-id="67d80-134">Sono previste diverse altre PlayBook per la fase 2.</span><span class="sxs-lookup"><span data-stu-id="67d80-134">Several more playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="67d80-135">I PlayBook includono analisi e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="67d80-135">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="67d80-136">Ogni PlayBook include:</span><span class="sxs-lookup"><span data-stu-id="67d80-136">Each playbook includes:</span></span> 
- <span data-ttu-id="67d80-137">un'indagine radice,</span><span class="sxs-lookup"><span data-stu-id="67d80-137">a root investigation,</span></span> 
- <span data-ttu-id="67d80-138">passaggi per la ricerca di altre potenziali minacce e</span><span class="sxs-lookup"><span data-stu-id="67d80-138">steps to hunt down other potential threats, and</span></span> 
- <span data-ttu-id="67d80-139">correzione delle minacce consigliate.</span><span class="sxs-lookup"><span data-stu-id="67d80-139">recommended threat remediation.</span></span>

<span data-ttu-id="67d80-140">Ogni passaggio di alto livello include numerosi passaggi secondari eseguiti per fornire una risposta profonda, dettagliata ed esaustiva alle minacce.</span><span class="sxs-lookup"><span data-stu-id="67d80-140">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-user-reported-phish-message"></a><span data-ttu-id="67d80-141">Esempio: messaggio phishing riferito dall'utente</span><span class="sxs-lookup"><span data-stu-id="67d80-141">Example: User-reported phish message</span></span>

<span data-ttu-id="67d80-142">Quando un utente dell'organizzazione invia un messaggio di posta elettronica e lo segnala a Microsoft tramite il [componente aggiuntivo segnala messaggio per Outlook o Outlook Web Access](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="67d80-142">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="67d80-143">In questo modo viene attivato un avviso informativo basato sul sistema che avvia automaticamente il PlayBook di analisi.</span><span class="sxs-lookup"><span data-stu-id="67d80-143">This triggers a system-based informational alert that automatically launches the investigation playbook.</span></span>

<span data-ttu-id="67d80-144">Durante la fase di analisi radice, vengono valutati vari aspetti del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="67d80-144">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="67d80-145">Queste funzionalità sono:</span><span class="sxs-lookup"><span data-stu-id="67d80-145">These include:</span></span>
- <span data-ttu-id="67d80-146">Determinazione del tipo di minaccia che potrebbe essere;</span><span class="sxs-lookup"><span data-stu-id="67d80-146">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="67d80-147">Chi lo ha inviato;</span><span class="sxs-lookup"><span data-stu-id="67d80-147">Who sent it;</span></span>
- <span data-ttu-id="67d80-148">In cui è stato inviato il messaggio di posta elettronica (infrastruttura di invio);</span><span class="sxs-lookup"><span data-stu-id="67d80-148">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="67d80-149">Se sono state recapitate o bloccate altre istanze del messaggio di posta elettronica;</span><span class="sxs-lookup"><span data-stu-id="67d80-149">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="67d80-150">Una valutazione dei nostri analisti;</span><span class="sxs-lookup"><span data-stu-id="67d80-150">An assessment from our analysts;</span></span>
- <span data-ttu-id="67d80-151">Se il messaggio di posta elettronica è associato a qualsiasi campagna Nota;</span><span class="sxs-lookup"><span data-stu-id="67d80-151">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="67d80-152">e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="67d80-152">and more.</span></span>

<span data-ttu-id="67d80-153">Dopo aver completato l'analisi radice, il PlayBook fornisce un elenco delle azioni consigliate da eseguire.</span><span class="sxs-lookup"><span data-stu-id="67d80-153">After the root investigation is complete, the playbook provides a list of recommended actions to take.</span></span>
  
<span data-ttu-id="67d80-154">Successivamente, vengono eseguiti diversi passaggi di caccia:</span><span class="sxs-lookup"><span data-stu-id="67d80-154">Next, several hunting steps are executed:</span></span>

- <span data-ttu-id="67d80-155">Vengono ricercati messaggi di posta elettronica simili in altri cluster di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="67d80-155">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="67d80-156">Il segnale viene condiviso con altre piattaforme, ad esempio [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="67d80-156">The signal is shared with other platforms, such as [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="67d80-157">Si determina se gli utenti hanno fatto clic sul messaggio di posta elettronica sospetti.</span><span class="sxs-lookup"><span data-stu-id="67d80-157">A determination is made on whether any users have clicked through on the suspicious email message.</span></span>
- <span data-ttu-id="67d80-158">Viene effettuato un controllo tra Office 365 [EOP](eop/exchange-online-protection-eop.md) e [ATP](office-365-atp.md) per verificare se sono presenti altri messaggi simili segnalati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="67d80-158">A check is done across Office 365 [EOP](eop/exchange-online-protection-eop.md) and [ATP](office-365-atp.md) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="67d80-159">Viene effettuato un controllo per verificare se un utente è stato compromesso.</span><span class="sxs-lookup"><span data-stu-id="67d80-159">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="67d80-160">Questa verifica utilizza i segnali in [Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security) e [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlando eventuali eventi o avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="67d80-160">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related events or alerts.</span></span> 

<span data-ttu-id="67d80-161">Durante la fase di caccia, i rischi e le minacce sono assegnati a vari passaggi di caccia.</span><span class="sxs-lookup"><span data-stu-id="67d80-161">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>  

<span data-ttu-id="67d80-162">La correzione è la fase finale del PlayBook.</span><span class="sxs-lookup"><span data-stu-id="67d80-162">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="67d80-163">Durante questa fase, vengono eseguite le operazioni di correzione, in base alle fasi di theinvestigation e di caccia.</span><span class="sxs-lookup"><span data-stu-id="67d80-163">During this phase, remediation steps are taken, based on theinvestigation and hunting phases.</span></span>  

## <a name="getting-started"></a><span data-ttu-id="67d80-164">Introduzione</span><span class="sxs-lookup"><span data-stu-id="67d80-164">Getting started</span></span>

<span data-ttu-id="67d80-165">Per accedere alle indagini, come amministratore globale o amministratore di sicurezza di Office 365, passare a Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="67d80-165">To access your investigations, as an Office 365 global administrator or security administrator, Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="67d80-166">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="67d80-166">Then, do one of the following:</span></span>

- <span data-ttu-id="67d80-167">Nella barra di spostamento a sinistra, andare a > **indagini**sulla **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="67d80-167">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="67d80-168">oppure</span><span class="sxs-lookup"><span data-stu-id="67d80-168">or</span></span>

- <span data-ttu-id="67d80-169">Visitare il dashboard di gestione delle minacce (nel centro sicurezza e conformità di &, accedere a **Threat Management** > **Dashboard**).</span><span class="sxs-lookup"><span data-stu-id="67d80-169">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![Widget aria](media/air-widgets.png)

<span data-ttu-id="67d80-171">I widget aria verranno visualizzati nella parte superiore del dashboard di [sicurezza](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="67d80-171">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="67d80-172">Selezionare un widget per iniziare.</span><span class="sxs-lookup"><span data-stu-id="67d80-172">Select a widget to get started.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="67d80-173">Indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="67d80-173">Automated investigations</span></span>

<span data-ttu-id="67d80-174">Nella pagina indagini automatizzate vengono visualizzate le indagini dell'organizzazione e gli stati correnti.</span><span class="sxs-lookup"><span data-stu-id="67d80-174">The automated investigations page shows your organization's investigations and their current states.</span></span>

![Pagina di ricerca principale per AIR](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="67d80-176">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-176">You can:</span></span>
- <span data-ttu-id="67d80-177">Passare direttamente a un'indagine (selezionare un **ID di ricerca**).</span><span class="sxs-lookup"><span data-stu-id="67d80-177">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="67d80-178">Applicare filtri.</span><span class="sxs-lookup"><span data-stu-id="67d80-178">Apply filters.</span></span> <span data-ttu-id="67d80-179">Scegliere tra il **tipo di analisi**, l'intervallo di **tempo**, **lo stato**o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="67d80-179">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="67d80-180">Esportare i dati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="67d80-180">Export the data to a CSV file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="67d80-181">Grafico di analisi</span><span class="sxs-lookup"><span data-stu-id="67d80-181">Investigation graph</span></span>

<span data-ttu-id="67d80-182">Quando si apre una specifica indagine, viene visualizzata la pagina del grafico delle indagini.</span><span class="sxs-lookup"><span data-stu-id="67d80-182">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="67d80-183">In questa pagina vengono illustrate tutte le diverse entità: messaggi di posta elettronica, utenti (e loro attività) e dispositivi che sono stati analizzati automaticamente come parte dell'avviso che è stato attivato.</span><span class="sxs-lookup"><span data-stu-id="67d80-183">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![Pagina del grafico dell'indagine AEREa](media/air-investigationgraphpage.png)

<span data-ttu-id="67d80-185">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-185">You can:</span></span>
- <span data-ttu-id="67d80-186">Ottenere una panoramica visiva dell'indagine corrente.</span><span class="sxs-lookup"><span data-stu-id="67d80-186">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="67d80-187">Visualizzare un riepilogo dei tempi di analisi.</span><span class="sxs-lookup"><span data-stu-id="67d80-187">View a summary of the investigation timings.</span></span>
- <span data-ttu-id="67d80-188">Selezionare un nodo nella visualizzazione per visualizzare i dettagli per il nodo.</span><span class="sxs-lookup"><span data-stu-id="67d80-188">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="67d80-189">Selezionare una scheda all'interno della parte superiore per visualizzare i dettagli per tale scheda.</span><span class="sxs-lookup"><span data-stu-id="67d80-189">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="67d80-190">Indagine sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="67d80-190">Alert investigation</span></span>

<span data-ttu-id="67d80-191">Nella scheda **avvisi** per un'indagine, è possibile visualizzare tutti gli avvisi rilevanti per l'indagine.</span><span class="sxs-lookup"><span data-stu-id="67d80-191">On the **Alerts** tab for an investigation, you can see all of the alerts relevant to the investigation.</span></span> <span data-ttu-id="67d80-192">I dettagli includono l'avviso che ha attivato l'indagine e altri avvisi, ad esempio l'accesso a rischio, il download di massa e così via, che sono correlati all'inchiesta.</span><span class="sxs-lookup"><span data-stu-id="67d80-192">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="67d80-193">Da questa pagina, un analista di sicurezza può anche visualizzare ulteriori dettagli sui singoli avvisi.</span><span class="sxs-lookup"><span data-stu-id="67d80-193">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![Pagina avvisi aria](media/air-investigationalertspage.png)

<span data-ttu-id="67d80-195">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-195">You can:</span></span>
- <span data-ttu-id="67d80-196">Ottenere una panoramica visiva dell'avviso di attivazione corrente e degli eventuali avvisi associati.</span><span class="sxs-lookup"><span data-stu-id="67d80-196">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="67d80-197">Selezionare un avviso nell'elenco per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.</span><span class="sxs-lookup"><span data-stu-id="67d80-197">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="67d80-198">Indagine tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="67d80-198">Email investigation</span></span>

<span data-ttu-id="67d80-199">Nella scheda **posta elettronica** per un'indagine, è possibile visualizzare tutti i cluster di posta elettronica identificati come parte dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="67d80-199">On the **Email** tab for an investigation, you can see all the email clusters identified as part of the investigation.</span></span> 

<span data-ttu-id="67d80-200">Dato il volume totale di messaggi di posta elettronica che gli utenti di un'organizzazione inviano e ricevono, il processo di</span><span class="sxs-lookup"><span data-stu-id="67d80-200">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="67d80-201">clustering dei messaggi di posta elettronica basati su attributi simili provenienti da un'intestazione, un corpo, un URL e un allegato del messaggio;</span><span class="sxs-lookup"><span data-stu-id="67d80-201">clustering email messages based on similar attributes from a message header, body, URL and attachment;</span></span> 
- <span data-ttu-id="67d80-202">separazione di messaggi di posta elettronica dannosi dal buon messaggio di posta elettronica; e</span><span class="sxs-lookup"><span data-stu-id="67d80-202">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="67d80-203">esecuzione di un'azione su messaggi di posta elettronica dannosi</span><span class="sxs-lookup"><span data-stu-id="67d80-203">taking action on malicious email messages</span></span> 

<span data-ttu-id="67d80-204">può richiedere molte ore.</span><span class="sxs-lookup"><span data-stu-id="67d80-204">can take many hours.</span></span> <span data-ttu-id="67d80-205">AIR ora automatizza questo processo, salvando il tempo e lo sforzo del team di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="67d80-205">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="67d80-206">Si consideri, ad esempio, l'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="67d80-206">As an example, consider the following image.</span></span> <span data-ttu-id="67d80-207">Il primo gruppo di tre messaggi di posta elettronica è stato ritenuto phishing.</span><span class="sxs-lookup"><span data-stu-id="67d80-207">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="67d80-208">Un altro gruppo di messaggi simili con lo stesso IP e l'oggetto è stato trovato ed è considerato dannoso, in quanto alcuni di essi sono stati identificati come phishing durante il rilevamento iniziale.</span><span class="sxs-lookup"><span data-stu-id="67d80-208">Another cluster of similar messages with the same IP and subject was found and is considered to be malicious, as some of them were identified as phish during initial detection.</span></span> 

![Pagina di ricerca della posta elettronica AEREa](media/air-investigationemailpage.png)

<span data-ttu-id="67d80-210">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-210">You can:</span></span>
- <span data-ttu-id="67d80-211">Ottenere una panoramica visiva dei risultati del clustering corrente e delle minacce trovate.</span><span class="sxs-lookup"><span data-stu-id="67d80-211">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="67d80-212">Fare clic su un'entità cluster o su un elenco di minacce per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.</span><span class="sxs-lookup"><span data-stu-id="67d80-212">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>

![Messaggi di posta elettronica di analisi AEREa con dettagli a comparsa](media/air-investigationemailpageflyoutdetails.png)

### <a name="user-investigation"></a><span data-ttu-id="67d80-214">Analisi degli utenti</span><span class="sxs-lookup"><span data-stu-id="67d80-214">User investigation</span></span>

<span data-ttu-id="67d80-215">Nella scheda **utenti** è possibile visualizzare tutti gli utenti identificati come parte dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="67d80-215">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> 

<span data-ttu-id="67d80-216">Ad esempio, nell'immagine seguente, l'aria ha identificato indicatori di compromesso e anomalie basate su una nuova regola di posta in arrivo che è stata creata.</span><span class="sxs-lookup"><span data-stu-id="67d80-216">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="67d80-217">Ulteriori dettagli (prova) dell'indagine sono disponibili tramite visualizzazioni dettagliate all'interno di questa scheda.</span><span class="sxs-lookup"><span data-stu-id="67d80-217">Additional details (evidence) of the investigation are available through detailed views within this tab.</span></span>

![Pagina utenti di analisi AEREa](media/air-investigationuserspage.png)

<span data-ttu-id="67d80-219">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-219">You can:</span></span>
- <span data-ttu-id="67d80-220">Ottenere una panoramica visiva dei risultati e dei rischi individuati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="67d80-220">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="67d80-221">Selezionare un utente per l'apertura di una pagina di fly-out che Visualizza i dettagli degli avvisi completi.</span><span class="sxs-lookup"><span data-stu-id="67d80-221">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="67d80-222">Indagine del computer</span><span class="sxs-lookup"><span data-stu-id="67d80-222">Machine investigation</span></span>

<span data-ttu-id="67d80-223">Nella scheda **computer** , è possibile visualizzare tutti i computer identificati come parte dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="67d80-223">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![Pagina macchina dell'analisi AEREa](media/air-investigationmachinepage.png)

<span data-ttu-id="67d80-225">Nell'ambito dell'inchiesta, AIR correla le minacce alla posta elettronica ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="67d80-225">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="67d80-226">Ad esempio, un'analisi passa un hash di file su [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) per esaminare.</span><span class="sxs-lookup"><span data-stu-id="67d80-226">For example, an investigation passes a file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate.</span></span> <span data-ttu-id="67d80-227">Questo consente l'analisi automatizzata delle macchine rilevanti per gli utenti e contribuisce a garantire che le minacce vengano affrontate sia nel cloud che nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="67d80-227">This allows for automated investigation of relevant machines for your users and helps to ensure that threats are addressed both in the cloud and across your devices.</span></span> 

<span data-ttu-id="67d80-228">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-228">You can:</span></span>
- <span data-ttu-id="67d80-229">Ottenere una panoramica visiva dei computer e delle minacce correnti trovati.</span><span class="sxs-lookup"><span data-stu-id="67d80-229">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="67d80-230">Selezionare un computer per aprire una visualizzazione che si riferisce alle [indagini di Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)correlate.</span><span class="sxs-lookup"><span data-stu-id="67d80-230">Select a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection).</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="67d80-231">Indagine su entità</span><span class="sxs-lookup"><span data-stu-id="67d80-231">Entity investigation</span></span>

<span data-ttu-id="67d80-232">Nella scheda **entità** , è possibile visualizzare tutti i computer identificati come parte dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="67d80-232">On the **Entities** tab, you can see all the machines identified as part of the investigation.</span></span> 

<span data-ttu-id="67d80-233">In questa sezione, è possibile visualizzare le entità indagate.</span><span class="sxs-lookup"><span data-stu-id="67d80-233">Here, you can see the investigated entities.</span></span> <span data-ttu-id="67d80-234">È possibile visualizzare i dettagli dei tipi di entità, ad esempio i messaggi di posta elettronica, i cluster, gli indirizzi IP, gli utenti e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="67d80-234">You can see details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="67d80-235">È inoltre possibile vedere quante entità sono state analizzate e le minacce che sono state associate a ognuna di esse.</span><span class="sxs-lookup"><span data-stu-id="67d80-235">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![Pagina delle entità di indagine AEREa](media/air-investigationentitiespage.png)

<span data-ttu-id="67d80-237">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-237">You can:</span></span>
- <span data-ttu-id="67d80-238">Ottenere una panoramica visiva delle entità investigative e delle minacce trovate.</span><span class="sxs-lookup"><span data-stu-id="67d80-238">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="67d80-239">Selezionare un'entità per aprire una pagina di volo che Visualizza il dettaglio dell'entità correlata.</span><span class="sxs-lookup"><span data-stu-id="67d80-239">Select an entity to open a fly-out page that shows the related entity detail.</span></span>

![Dettagli sulle entità di indagine AEREa](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="67d80-241">Registro PlayBook</span><span class="sxs-lookup"><span data-stu-id="67d80-241">Playbook log</span></span>

<span data-ttu-id="67d80-242">Nella scheda **log** , è possibile visualizzare tutti i passaggi del PlayBook che si sono verificati durante l'indagine.</span><span class="sxs-lookup"><span data-stu-id="67d80-242">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="67d80-243">Il log acquisisce un inventario completo di tutte le azioni completate dalle funzionalità di business intelligence di Office 365 come parte di AIR.</span><span class="sxs-lookup"><span data-stu-id="67d80-243">The log captures a complete inventory of all actions completed by Office 365 Threat Intelligence capabilities as part of AIR.</span></span> <span data-ttu-id="67d80-244">Viene fornita una chiara visualizzazione di tutti i passaggi, tra cui l'azione stessa, una descrizione e la durata dell'effettiva dall'inizio alla fine.</span><span class="sxs-lookup"><span data-stu-id="67d80-244">It provides a clear view of all the steps taken, including the Action itself, a description and the duration of the actual from start to finish.</span></span> 

![Pagina del registro delle indagini AEREe](media/air-investigationlogpage.png)

<span data-ttu-id="67d80-246">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-246">You can:</span></span>
- <span data-ttu-id="67d80-247">Ottenere una panoramica visiva dei passaggi di PlayBook eseguiti.</span><span class="sxs-lookup"><span data-stu-id="67d80-247">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="67d80-248">Esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="67d80-248">Export the results to a CSV file.</span></span>
- <span data-ttu-id="67d80-249">Filtrare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="67d80-249">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="67d80-250">Azioni consigliate</span><span class="sxs-lookup"><span data-stu-id="67d80-250">Recommended actions</span></span>

<span data-ttu-id="67d80-251">Nella scheda **azioni** , è possibile visualizzare tutte le azioni di PlayBook consigliate per la correzione dopo il completamento dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="67d80-251">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="67d80-252">Azioni acquisire un elenco completo di tutti i passaggi consigliati da Microsoft al termine di un'indagine.</span><span class="sxs-lookup"><span data-stu-id="67d80-252">Actions capture a complete list of all the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="67d80-253">È possibile eseguire le azioni di correzione selezionando una o più azioni.</span><span class="sxs-lookup"><span data-stu-id="67d80-253">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="67d80-254">Se si fa clic su **approva** , verrà avviata la correzione.</span><span class="sxs-lookup"><span data-stu-id="67d80-254">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="67d80-255">(Potrebbe essere necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="67d80-255">(Appropriate permissions might be required.</span></span> <span data-ttu-id="67d80-256">Ad esempio, un lettore di sicurezza è in grado di visualizzare le azioni, ma non di approvarle.</span><span class="sxs-lookup"><span data-stu-id="67d80-256">For example, a Security Reader can view actions but not approve them.)</span></span>  

![Pagina azione indagini AEREe](media/air-investigationactionspage.png)

<span data-ttu-id="67d80-258">È possibile:</span><span class="sxs-lookup"><span data-stu-id="67d80-258">You can:</span></span>
- <span data-ttu-id="67d80-259">Ottenere una panoramica visiva delle azioni consigliate in PlayBook.</span><span class="sxs-lookup"><span data-stu-id="67d80-259">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="67d80-260">Selezionare una singola azione o più azioni.</span><span class="sxs-lookup"><span data-stu-id="67d80-260">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="67d80-261">Approva le azioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="67d80-261">Approve recommended actions.</span></span> <span data-ttu-id="67d80-262">Questi vengono avviati immediatamente con i commenti.</span><span class="sxs-lookup"><span data-stu-id="67d80-262">(These are started immediately with comments.)</span></span>
- <span data-ttu-id="67d80-263">Esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="67d80-263">Export the results to a CSV file.</span></span>
- <span data-ttu-id="67d80-264">Filtrare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="67d80-264">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="67d80-265">Come ottenere aria</span><span class="sxs-lookup"><span data-stu-id="67d80-265">How to get AIR</span></span>

<span data-ttu-id="67d80-266">Attualmente, l'aria è in anteprima.</span><span class="sxs-lookup"><span data-stu-id="67d80-266">Currently, AIR is in preview.</span></span> <span data-ttu-id="67d80-267">Quando viene rilasciato, AIR verrà incluso nelle sottoscrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="67d80-267">When released, AIR will be included in the following subscriptions:</span></span>

- <span data-ttu-id="67d80-268">Microsoft 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="67d80-268">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="67d80-269">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="67d80-269">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="67d80-270">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="67d80-270">Microsoft Threat Protection</span></span>
- <span data-ttu-id="67d80-271">Office 365 Advanced Threat Protection piano 2</span><span class="sxs-lookup"><span data-stu-id="67d80-271">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="67d80-272">Per ulteriori informazioni sulla disponibilità delle funzionalità, visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="67d80-272">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
