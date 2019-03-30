---
title: Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: Dopo aver configurato e implementato Office 365 cloud app Security, è necessario eseguire alcune attività per assicurarsi che la configurazione sia corretta e che si sia preparato per le revisioni regolari.
ms.openlocfilehash: 232de4df1d1eb4debdddcee2c1d8672d1aeb4b21
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999949"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="c4fd4-103">Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c4fd4-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="c4fd4-104">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c4fd4-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="c4fd4-105">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c4fd4-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="c4fd4-106">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c4fd4-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="c4fd4-107">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="c4fd4-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="c4fd4-108">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="c4fd4-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="c4fd4-109">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="c4fd4-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="c4fd4-110">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="c4fd4-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="c4fd4-111">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="c4fd4-111">You are here!</span></span>  <br/> [<span data-ttu-id="c4fd4-112">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c4fd4-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="c4fd4-113">Office 365 cloud app Security è disponibile in Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-113">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="c4fd4-114">Se l'organizzazione utilizza un altro abbonamento a Office 365 Enterprise, Office 365 cloud app Security può essere acquistato come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-114">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="c4fd4-115">(come amministratore globale, nell'interfaccia di amministrazione di Microsoft 365, scegliere **fatturazione** \> **aggiungi abbonamenti**). Per ulteriori informazioni, vedere [office 365 Platform Service Description: office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) e [acquistare o modificare un componente aggiuntivo per Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="c4fd4-115">(As a global administrator, in the Microsoft 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="c4fd4-116">Dopo aver installato e configurato Office 365 cloud app Security, è necessario eseguire alcune attività di utilizzo come amministratore globale di Office 365 o amministratore della protezione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="c4fd4-117">Eseguendo queste attività, è possibile garantire che Office 365 cloud app Security sia configurato correttamente, che i criteri siano aggiornati e che l'organizzazione realizzi il valore da Office 365.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-117">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365.</span></span> <span data-ttu-id="c4fd4-118">Utilizzare questo articolo come guida per pianificare queste attività.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-118">Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4fd4-119">È necessario essere un amministratore globale o un amministratore della sicurezza per eseguire le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-119">You must be a global administrator or security administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="c4fd4-120">Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c4fd4-120">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="c4fd4-121">Attività dopo la configurazione iniziale e la distribuzione di Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="c4fd4-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="c4fd4-122">Dopo aver configurato e implementato Office 365 cloud app Security, come amministratore globale o amministratori della sicurezza, sono disponibili diverse considerazioni:</span><span class="sxs-lookup"><span data-stu-id="c4fd4-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="c4fd4-123">Quali attività devono essere aggiunte al calendario del reparto IT?</span><span class="sxs-lookup"><span data-stu-id="c4fd4-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="c4fd4-124">Come si può verificare che Office 365 cloud app Security sia configurato in modo da utilizzare il set di criteri corretto nel tempo?</span><span class="sxs-lookup"><span data-stu-id="c4fd4-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="c4fd4-125">Quali tipi di informazioni di riepilogo è necessario inviare alla catena di gestione IT?</span><span class="sxs-lookup"><span data-stu-id="c4fd4-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="c4fd4-126">Nella tabella seguente vengono riepilogate brevemente le attività da eseguire e le attività periodiche che è consigliabile aggiungere al calendario del reparto IT.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="c4fd4-127">**Attività in uscita**</span><span class="sxs-lookup"><span data-stu-id="c4fd4-127">**Ongoing tasks**</span></span>|<span data-ttu-id="c4fd4-128">**Attività periodiche**</span><span class="sxs-lookup"><span data-stu-id="c4fd4-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="c4fd4-129">Monitorare gli account di posta elettronica a cui vengono inviati i messaggi di avviso</span><span class="sxs-lookup"><span data-stu-id="c4fd4-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="c4fd4-130">Monitor Industry Cybersecurity News Feeds per le ultime informazioni sui nuovi attacchi informatici</span><span class="sxs-lookup"><span data-stu-id="c4fd4-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="c4fd4-131">Agire sugli avvisi di sicurezza per identificare e risolvere gli incidenti di sicurezza e i rischi</span><span class="sxs-lookup"><span data-stu-id="c4fd4-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="c4fd4-132">Riepilogare ogni evento di sicurezza e risoluzione in un registro centrale</span><span class="sxs-lookup"><span data-stu-id="c4fd4-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="c4fd4-133">Eseguire revisioni mensili o trimestrali degli avvisi di sicurezza di Office 365 cloud app per individuare le anomalie e analizzare le tendenze</span><span class="sxs-lookup"><span data-stu-id="c4fd4-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="c4fd4-134">Eseguire revisioni mensili o trimestrali dei criteri di sicurezza di Office 365 cloud app esistenti per includere miglioramenti in Office 365 cloud app Security e indirizzare nuove attacchi cibernetici e tendenze in Cybersecurity</span><span class="sxs-lookup"><span data-stu-id="c4fd4-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="c4fd4-135">A seconda della dimensione dell'organizzazione e dell'interesse per il monitoraggio e il mantenimento di una statura di sicurezza, è possibile compilare un riepilogo mensile per la catena di gestione IT che include:</span><span class="sxs-lookup"><span data-stu-id="c4fd4-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="c4fd4-136">I diversi tipi di incidenti di sicurezza identificati con Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="c4fd4-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="c4fd4-137">Informazioni di riepilogo del registro centrale degli incidenti di sicurezza, ad esempio il numero di incidenti rilevati</span><span class="sxs-lookup"><span data-stu-id="c4fd4-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="c4fd4-138">Tendenze di avviso e modalità di indirizzamento</span><span class="sxs-lookup"><span data-stu-id="c4fd4-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="c4fd4-139">Le ultime tendenze di Cybersecurity</span><span class="sxs-lookup"><span data-stu-id="c4fd4-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="c4fd4-140">Suggerimenti per le modifiche ai criteri di sicurezza di Office 365 cloud app e il loro impatto sugli utenti finali</span><span class="sxs-lookup"><span data-stu-id="c4fd4-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="c4fd4-141">Attività dopo il tempo trascorso dall'implementazione di Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="c4fd4-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="c4fd4-142">Se è trascorso un periodo di tempo prolungato dopo aver configurato o mantenuto i criteri di sicurezza dell'app cloud di Office 365, eseguire la procedura seguente per tornare a una configurazione che rispecchi gli obiettivi di sicurezza dell'organizzazione e le funzionalità correnti. di Office 365 cloud app Security:</span><span class="sxs-lookup"><span data-stu-id="c4fd4-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="c4fd4-143">Determinare la data dell'Ultima modifica di configurazione per Office 365 cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="c4fd4-144">Comprendere la configurazione di sicurezza delle app di Office 365 Cloud corrente e regolare tali criteri in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-144">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed.</span></span> <span data-ttu-id="c4fd4-145">Ad esempio, accertarsi di sapere dove vengono inviati gli avvisi tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-145">For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="c4fd4-146">Vedere [What ' s New in office 365 cloud app Security](new-in-office-365-cas.md) per le modifiche al prodotto dopo l'ultima configurazione di Office 365 cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="c4fd4-147">Eseguire un'analisi dei registri e degli avvisi di sicurezza di Office 365 cloud app per individuare anomalie e analizzare le tendenze.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="c4fd4-148">Controllare le tendenze del settore Cybersecurity per conoscere le ultime minacce alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="c4fd4-149">Eseguire un'analisi delle modifiche che devono essere apportate all'insieme corrente dei criteri di sicurezza delle app cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-149">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies.</span></span> <span data-ttu-id="c4fd4-150">Incorporare modifiche alla funzionalità di sicurezza delle app cloud di Office 365, anomalie correnti e tendenze di Cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-150">Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends.</span></span> <span data-ttu-id="c4fd4-151">Consigliare le modifiche apportate ai criteri esistenti o la creazione di nuovi criteri.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-151">Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="c4fd4-152">Preparare un piano per l'implementazione delle modifiche ai criteri.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-152">Make a plan for implementing the policy changes.</span></span> <span data-ttu-id="c4fd4-153">Comunicare (socializzare) le conseguenze delle modifiche proposte con gli utenti finali in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-153">Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="c4fd4-154">Implementare le modifiche apportate ai criteri di protezione delle app di Office 365 cloud.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="c4fd4-155">Monitorare gli avvisi sulla sicurezza degli utenti finali e di Office 365 cloud app Security e regolare i criteri nel tempo.</span><span class="sxs-lookup"><span data-stu-id="c4fd4-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="c4fd4-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c4fd4-156">Next steps</span></span>

- [<span data-ttu-id="c4fd4-157">Esaminare un'attività</span><span class="sxs-lookup"><span data-stu-id="c4fd4-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="c4fd4-158">Sospendere o ripristinare un account utente</span><span class="sxs-lookup"><span data-stu-id="c4fd4-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="c4fd4-159">Gestire le app OAuth</span><span class="sxs-lookup"><span data-stu-id="c4fd4-159">Manage OAuth apps</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="c4fd4-160">Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c4fd4-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="c4fd4-161">Visualizzare un elenco di [log del traffico Web e origini dati](web-traffic-logs-and-data-sources-for-ocas.md) supportate</span><span class="sxs-lookup"><span data-stu-id="c4fd4-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

