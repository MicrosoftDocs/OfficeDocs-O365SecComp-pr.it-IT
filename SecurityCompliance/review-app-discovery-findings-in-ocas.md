---
title: Esaminare i risultati di App Discovery in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: Esame dei report di individuazione app nella gestione della protezione avanzata consentono di ulteriori informazioni sull'utilizzano di applicazioni basate su cloud persone nell'organizzazione. Dopo aver creato i rapporti di individuazione app utilizzando i file di registro dai firewall e proxy, esaminare i risultati nel dashboard di individuazione applicazioni.
ms.openlocfilehash: 188ef87920b26069e7d99057662b3812be22e46c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530206"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="8fd1c-104">Esaminare i risultati di App Discovery in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8fd1c-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="8fd1c-105">Valutazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="8fd1c-105">****Evaluation** \>**</span></span>|<span data-ttu-id="8fd1c-106">Pianificazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="8fd1c-106">****Planning** \>**</span></span>|<span data-ttu-id="8fd1c-107">Distribuzione * *\>**</span><span class="sxs-lookup"><span data-stu-id="8fd1c-107">****Deployment** \>**</span></span>|<span data-ttu-id="8fd1c-108">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="8fd1c-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="8fd1c-109">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="8fd1c-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="8fd1c-110">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="8fd1c-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="8fd1c-111">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="8fd1c-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="8fd1c-112">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="8fd1c-112">You are here!</span></span>  <br/> [<span data-ttu-id="8fd1c-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8fd1c-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="8fd1c-p102">Il dashboard di individuazione Cloud utilizza i registri di traffico web dell'organizzazione per fornire informazioni dettagliate sull'utilizzo delle app cloud. Se si invia un amministratore globale, l'amministratore della sicurezza o lettore di sicurezza e l'organizzazione ha [creato app individuazione rapporti di protezione di applicazioni di Office 365 Cloud](create-app-discovery-reports-in-ocas.md), è possibile utilizzare il dashboard di individuazione Cloud per comprendere come utenti nel organizzazione utilizza Office 365 e altre applicazioni basate su cloud. (Il dashboard di individuazione Cloud è noto anche come è produttività App Discovery).</span><span class="sxs-lookup"><span data-stu-id="8fd1c-p102">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="8fd1c-117">**A partire da 2018 marzo, il dashboard di individuazione Cloud con nuove funzionalità** che rendono più semplice visualizzare informazioni dettagliate sulla modalità di utilizzo personale della tua organizzazione Office 365 e altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-117">**As of March 2018, the Cloud Discovery dashboard has new features** that make it easier to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![È stato aggiornato il dashboard di individuazione Cloud](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="8fd1c-119">Accedere al dashboard individuazione Cloud</span><span class="sxs-lookup"><span data-stu-id="8fd1c-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="8fd1c-p103">Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. (Si passa alla sicurezza &amp; centro conformità.)</span><span class="sxs-lookup"><span data-stu-id="8fd1c-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="8fd1c-122">In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
    <span data-ttu-id="8fd1c-123">(Se Office 365 Cloud App sicurezza non è ancora abilitato e si è un amministratore globale, di [attivare la protezione di Office 365 Cloud App](turn-on-office-365-cas.md).)</span><span class="sxs-lookup"><span data-stu-id="8fd1c-123">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="8fd1c-124">Scegliere **Vai a Office 365 Cloud App protezione**.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-124">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="8fd1c-125">Accedere a **individuazione** \> **individuazione Cloud dashboard**.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-125">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="8fd1c-126">Vedere utenti principali, gli indirizzi IP, App e livelli di rischio</span><span class="sxs-lookup"><span data-stu-id="8fd1c-126">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="8fd1c-127">Il dashboard di individuazione Cloud viene fornita una panoramica in rapida di applicazioni che vengono utilizzati con Office 365 nell'organizzazione, tutti gli avvisi aperti, utenti principali e livelli di rischio.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-127">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![Cloud individuazione dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="8fd1c-129">Nella scheda **Dashboard** esaminare l'utilizzo di app cloud globale dell'organizzazione nella sezione Panoramica nella parte superiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-129">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="8fd1c-130">Vedere le **categorie di Office 365** per le applicazioni che vengono utilizzati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-130">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="8fd1c-131">Esaminare widget **Discovered App** di visualizzare i dati di utilizzo di Office 365 e altre App in questa visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-131">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="8fd1c-132">Esaminare il widget **utenti principali** e **gli indirizzi IP principali** per identificare gli utenti che utilizzano Office 365 e cloud App maggiormente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-132">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="8fd1c-133">Visualizzazione della posizione App utilizzano persone dalla posizione geografica utilizzando il mapping **sede App** .</span><span class="sxs-lookup"><span data-stu-id="8fd1c-133">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="8fd1c-p104">Sopra l'area di mappe, esaminare il punteggio di rischio delle App rilevati in Panoramica **livelli di rischio** . È possibile esaminare i rischi per i gruppi e categorie utilizzato nell'area **Discovered App** stesso. Ad esempio, è possibile visualizzare la quantità di traffico in ogni raggruppamento è da apps elevato, medio o basso rischio.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-p104">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="8fd1c-137">Approfondisci le informazioni</span><span class="sxs-lookup"><span data-stu-id="8fd1c-137">Dive deeper into the information</span></span>

<span data-ttu-id="8fd1c-138">È possibile utilizzare l'individuazione Cloud per rendere una più approfondita App, i sottodomini, indirizzi IP e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-138">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="8fd1c-139">Nel dashboard di individuazione Cloud, fare clic sulla scheda **Discovered App** .</span><span class="sxs-lookup"><span data-stu-id="8fd1c-139">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="8fd1c-140">Utilizzare la sezione filtri per visualizzare le App per nome, categoria, il livello di utilizzo o ultimo considerata data.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-140">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="8fd1c-141">Nell'elenco dei risultati al passaggio del mouse per un nome di applicazione per visualizzare il collegamento **Visualizza i sottodomini** .</span><span class="sxs-lookup"><span data-stu-id="8fd1c-141">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span> 
    
    ![Al passaggio del mouse accanto a un'applicazione per visualizzare un collegamento per visualizzare i dettagli sottodominio](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)
  
    <span data-ttu-id="8fd1c-143">Informazioni dettagliate sull'app selezionata verranno visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-143">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="8fd1c-144">Per visualizzare informazioni dettagliate sugli indirizzi IP, fare clic sulla scheda **indirizzi IP** .</span><span class="sxs-lookup"><span data-stu-id="8fd1c-144">To view details about IP addresses, choose the **IP addresses** tab.</span></span> 
    
    ![Individuazione cloud Visualizza informazioni dettagliate sugli indirizzi IP](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)
  
    <span data-ttu-id="8fd1c-146">Nell'elenco dei risultati, selezionare un singolo indirizzo IP per visualizzare informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-146">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="8fd1c-147">Per visualizzare informazioni dettagliate sugli utenti di Office 365 all'interno dell'organizzazione, fare clic sulla scheda **utenti** .</span><span class="sxs-lookup"><span data-stu-id="8fd1c-147">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span> 
    
    ![Individuazione cloud - informazioni gli utenti](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a><span data-ttu-id="8fd1c-149">Esclude le entità</span><span class="sxs-lookup"><span data-stu-id="8fd1c-149">Exclude entities</span></span>

<span data-ttu-id="8fd1c-150">È possibile escludere alcune gli utenti o gli indirizzi IP per individuare le informazioni più specifiche.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-150">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="8fd1c-151">Fare clic su **Impostazioni** \> **le impostazioni di individuazione Cloud**.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-151">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="8fd1c-152">Scegliere **escludere le entità**.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-152">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="8fd1c-153">Scegliere **gli utenti esclusi** o **gli indirizzi IP esclusi**.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-153">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="8fd1c-154">Specificare gli utenti o gli indirizzi IP e nella casella **commenti** digitare informazioni sui motivi per cui si sono esclusi quegli utenti o gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-154">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="8fd1c-155">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8fd1c-155">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="8fd1c-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8fd1c-156">Next steps</span></span>

- [<span data-ttu-id="8fd1c-157">Leggere ed eseguire l'azione gli avvisi</span><span class="sxs-lookup"><span data-stu-id="8fd1c-157">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="8fd1c-158">Creare i rapporti di individuazione applicazioni</span><span class="sxs-lookup"><span data-stu-id="8fd1c-158">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="8fd1c-159">Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="8fd1c-159">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

