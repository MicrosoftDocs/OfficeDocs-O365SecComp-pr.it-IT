---
title: Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: Dopo che sono state impostate e di implementazione della protezione App Cloud di Office 365, è consigliabile eseguire alcune attività per verificare la configurazione sia corretta e che sta preparato per confrontarsi a intervalli regolari.
ms.openlocfilehash: 71b6793f2e325fcba3431ba5157640b29814ad30
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603707"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="b5385-103">Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b5385-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="b5385-104">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b5385-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="b5385-105">Pianificazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b5385-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="b5385-106">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b5385-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="b5385-107">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b5385-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b5385-108">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="b5385-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="b5385-109">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="b5385-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="b5385-110">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="b5385-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="b5385-111">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="b5385-111">You are here!</span></span>  <br/> [<span data-ttu-id="b5385-112">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b5385-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="b5385-p101">Protezione di Office 365 Cloud App è disponibile in Office 365 Enterprise E5. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, protezione di Office 365 Cloud App può essere acquistata come componente aggiuntivo. (Come amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **Aggiungi sottoscrizioni**.) Per ulteriori informazioni, vedere [Office 365 Platform Service Description: protezione di Office 365 &amp; centro conformità](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) e [acquistare o modificare un componente aggiuntivo per Office 365 per aziende](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="b5385-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="b5385-116">Dopo avere impostato e configurato sicurezza App Cloud di Office 365, sarà si desidera eseguire alcune attività di utilizzo come un amministratore globale di Office 365 o un amministratore della sicurezza per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5385-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="b5385-p102">Eseguendo queste attività, si verrà garantire sicurezza di Office 365 Cloud App sia configurato correttamente, i criteri vengono aggiornati e l'organizzazione di realizzazione compreso tra Office 365. Utilizzare questo articolo come guida per la pianificazione per eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="b5385-p102">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365. Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5385-p103">È necessario essere un amministratore globale o sicurezza per eseguire le attività descritte in questo articolo. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b5385-p103">You must be a global administrator or security administrator to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="b5385-121">Attività dopo l'implementazione della protezione di Office 365 Cloud App e la configurazione iniziale</span><span class="sxs-lookup"><span data-stu-id="b5385-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="b5385-122">Una volta configurata e di implementazione, come amministratori della protezione, o un amministratore globale di sicurezza di Office 365 Cloud App sono diversi aspetti da considerare:</span><span class="sxs-lookup"><span data-stu-id="b5385-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="b5385-123">Quali attività è necessario aggiungere al calendario di reparto IT?</span><span class="sxs-lookup"><span data-stu-id="b5385-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="b5385-124">Come possono essere apportate che Office 365 Cloud App sicurezza sia configurato per utilizzare il set di criteri di destro nel tempo?</span><span class="sxs-lookup"><span data-stu-id="b5385-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="b5385-125">Tipi di informazioni di riepilogo deve inviare la catena di gestione IT.</span><span class="sxs-lookup"><span data-stu-id="b5385-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="b5385-126">Brevemente nella tabella seguente vengono riepilogate le attività in corso desiderata per eseguire attività periodica che è consigliabile aggiungerlo al calendario del reparto IT.</span><span class="sxs-lookup"><span data-stu-id="b5385-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="b5385-127">**Attività in corso**</span><span class="sxs-lookup"><span data-stu-id="b5385-127">**Ongoing tasks**</span></span>|<span data-ttu-id="b5385-128">**Attività periodica**</span><span class="sxs-lookup"><span data-stu-id="b5385-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="b5385-129">Monitorare gli account di posta elettronica a cui si inviano messaggi di avviso</span><span class="sxs-lookup"><span data-stu-id="b5385-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="b5385-130">Monitorare settore alla sicurezza informatica newsfeed per informazioni aggiornate sui nuovi attacchi cyber</span><span class="sxs-lookup"><span data-stu-id="b5385-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="b5385-131">Agire avvisi di protezione per identificare e risolvere i rischi e problemi di protezione</span><span class="sxs-lookup"><span data-stu-id="b5385-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="b5385-132">Riepilogare ogni problema di sicurezza e la risoluzione di un registro centrale</span><span class="sxs-lookup"><span data-stu-id="b5385-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="b5385-133">Eseguire le revisioni mensili o trimestrali degli avvisi di protezione di applicazioni di Office 365 Cloud per alterazioni campione e analisi delle tendenze</span><span class="sxs-lookup"><span data-stu-id="b5385-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="b5385-134">Eseguire mensili o trimestrali valutazioni dei criteri di protezione di applicazioni di Office 365 Cloud esistenti da includere miglioramenti nella sicurezza App Cloud di Office 365 e l'indirizzo cyberattacks nuove e le tendenze in alla sicurezza informatica</span><span class="sxs-lookup"><span data-stu-id="b5385-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="b5385-135">A seconda delle dimensioni e interessi di monitoraggio e manutenzione di un levatura di sicurezza dell'organizzazione, è possibile compilare un riepilogo mensile per la catena di gestione IT che include:</span><span class="sxs-lookup"><span data-stu-id="b5385-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="b5385-136">Diversi tipi di problemi di protezione identificati con Office 365 Cloud App protezione</span><span class="sxs-lookup"><span data-stu-id="b5385-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="b5385-137">Riepilogo delle informazioni dal registro centrale dei problemi di protezione, ad esempio numero di problemi rilevati</span><span class="sxs-lookup"><span data-stu-id="b5385-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="b5385-138">Avviso tendenze e come sono stati risolti</span><span class="sxs-lookup"><span data-stu-id="b5385-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="b5385-139">Le ultime tendenze alla sicurezza informatica</span><span class="sxs-lookup"><span data-stu-id="b5385-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="b5385-140">Suggerimenti per le modifiche dei criteri di sicurezza di Office 365 Cloud App e l'impatto sugli utenti finali</span><span class="sxs-lookup"><span data-stu-id="b5385-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="b5385-141">Attività dopo ora dall'implementazione di sicurezza di Office 365 Cloud App</span><span class="sxs-lookup"><span data-stu-id="b5385-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="b5385-142">Se un prolungata periodo di tempo trascorso è inizialmente configurato o mantenere i criteri di protezione di Office 365 Cloud App, eseguire la procedura seguente per ottenere una configurazione che riflette la funzionalità corrente e gli obiettivi di protezione dell'organizzazione di protezione di applicazioni di Office 365 Cloud:</span><span class="sxs-lookup"><span data-stu-id="b5385-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="b5385-143">Determinare la data dell'ultima modifica di configurazione per la protezione di Office 365 Cloud App.</span><span class="sxs-lookup"><span data-stu-id="b5385-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="b5385-p104">Acquisire familiarità con la configurazione di protezione di Office 365 Cloud App corrente e modificare i criteri in base alle esigenze. Ad esempio, assicurarsi di conoscere dove vengono inviati avvisi tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b5385-p104">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed. For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="b5385-146">Poiché è stato configurato ultimo sicurezza App Cloud di Office 365, vedere [What's new in sicurezza App Cloud di Office 365](new-in-office-365-cas.md) per le modifiche di prodotto.</span><span class="sxs-lookup"><span data-stu-id="b5385-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="b5385-147">Eseguire un'analisi dei registri per alterazioni campione e gli avvisi di protezione di applicazioni di Office 365 Cloud e analizzare le tendenze.</span><span class="sxs-lookup"><span data-stu-id="b5385-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="b5385-148">Controllare le tendenze alla sicurezza informatica del settore diventi tenere presenti le minacce alla sicurezza più recente.</span><span class="sxs-lookup"><span data-stu-id="b5385-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="b5385-p105">Eseguire un'analisi delle modifiche che devono essere apportate all'insieme corrente di criteri di protezione di Office 365 Cloud App. Incorporare modifiche delle caratteristiche di protezione di applicazioni di Office 365 Cloud, alterazioni corrente e alla sicurezza informatica tendenze. Consigliabile modifiche ai criteri esistenti o la creazione di nuovi criteri.</span><span class="sxs-lookup"><span data-stu-id="b5385-p105">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies. Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends. Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="b5385-p106">Creare un piano di implementazione delle modifiche dei criteri. Comunicare (socializzare) le conseguenze delle modifiche proposte con gli utenti finali in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b5385-p106">Make a plan for implementing the policy changes. Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="b5385-154">Implementare le modifiche di criteri di sicurezza di Office 365 Cloud App.</span><span class="sxs-lookup"><span data-stu-id="b5385-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="b5385-155">Monitorare i commenti e suggerimenti degli utenti finali e gli avvisi di protezione di applicazioni di Office 365 Cloud e modificare i criteri nel tempo.</span><span class="sxs-lookup"><span data-stu-id="b5385-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="b5385-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b5385-156">Next steps</span></span>

- [<span data-ttu-id="b5385-157">Provare a utilizzare un'attività</span><span class="sxs-lookup"><span data-stu-id="b5385-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="b5385-158">Sospendere o il ripristino di un account utente</span><span class="sxs-lookup"><span data-stu-id="b5385-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="b5385-159">Gestire le app OAuth</span><span class="sxs-lookup"><span data-stu-id="b5385-159">Manage OAuth apps</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="b5385-160">Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b5385-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="b5385-161">Visualizzare un elenco di [origini dati e registri di traffico Web](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b5385-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

