---
title: Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security
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
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: La revisione dei rapporti di individuazione delle app in Office 365 cloud app Security consente di ottenere ulteriori informazioni sul modo in cui gli utenti dell'organizzazione utilizzano le app cloud. Dopo aver creato i report di individuazione delle app utilizzando i file di log dai firewall e dai proxy, esaminare i risultati nel dashboard di individuazione delle app.
ms.openlocfilehash: fa5ab7c6cd734feb26878cf1a97f7ce708aa1478
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087335"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="f8dc5-104">Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f8dc5-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="f8dc5-105">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f8dc5-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="f8dc5-106">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f8dc5-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="f8dc5-107">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f8dc5-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="f8dc5-108">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="f8dc5-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="f8dc5-109">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="f8dc5-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="f8dc5-110">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="f8dc5-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="f8dc5-111">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="f8dc5-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="f8dc5-112">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="f8dc5-112">You are here!</span></span>  <br/> [<span data-ttu-id="f8dc5-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f8dc5-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="f8dc5-p102">Il dashboard di individuazione cloud è compatibile con i log del traffico web dell'organizzazione per fornire informazioni dettagliate sull'utilizzo delle app cloud. Se si è un amministratore globale, un amministratore della sicurezza o un lettore di sicurezza e l'organizzazione ha [creato rapporti di individuazione delle app in Office 365 cloud app Security](create-app-discovery-reports-in-ocas.md), è possibile utilizzare il dashboard di individuazione cloud per acquisire informazioni sul modo in cui le persone nella propria l'organizzazione utilizza Office 365 e altre app cloud. (Il dashboard di individuazione cloud è noto anche come individuazione delle app per la produttività).</span><span class="sxs-lookup"><span data-stu-id="f8dc5-p102">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="f8dc5-117">Il dashboard di individuazione cloud consente di visualizzare informazioni dettagliate sul modo in cui gli utenti dell'organizzazione utilizzano Office 365 e altre app.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-117">The Cloud Discovery dashboard enables you to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![The Cloud Discovery dashboard è stato aggiornato](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="f8dc5-119">Accedere al dashboard di individuazione cloud</span><span class="sxs-lookup"><span data-stu-id="f8dc5-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="f8dc5-120">Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-120">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="f8dc5-121">Andare a **Discover** \> **cloud Discovery dashboard**.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-121">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="f8dc5-122">Visualizzare gli utenti principali, gli indirizzi IP, le app e i livelli di rischio</span><span class="sxs-lookup"><span data-stu-id="f8dc5-122">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="f8dc5-123">The Cloud Discovery dashboard offre una panoramica delle app che vengono utilizzate con Office 365 nell'organizzazione, eventuali avvisi aperti, utenti principali e livelli di rischio.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-123">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![Dashboaard Discovery cloud](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="f8dc5-125">Nella scheda **Dashboard** , esaminare l'utilizzo globale delle app Cloud nell'organizzazione nella sezione Panoramica nella parte superiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-125">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="f8dc5-126">Vedere le **categorie di Office 365** per le app che vengono utilizzate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-126">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="f8dc5-127">Consultare il widget **Apps individuati** per visualizzare l'utilizzo di Office 365 e di altre app in questa visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-127">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="f8dc5-128">Esaminare gli **utenti principali** e il widget **indirizzi IP principali** per identificare coloro che utilizzano le app di Office 365 e cloud più all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-128">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="f8dc5-129">Vedere dove le app persone stanno usando sono per località geografica usando la mappa del **percorso delle app** .</span><span class="sxs-lookup"><span data-stu-id="f8dc5-129">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="f8dc5-p103">Sopra l'area mappe, esaminare il Punteggio di rischio delle app individuate nella panoramica dei **livelli di rischio** . È possibile esaminare i rischi per gli stessi gruppi e le stesse categorie utilizzati nell'area **app scoperte** . Ad esempio, è possibile visualizzare la quantità di traffico in ogni raggruppamento proveniente da applicazioni di alto, medio o basso rischio.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-p103">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="f8dc5-133">Immergersi più in profondità nelle informazioni</span><span class="sxs-lookup"><span data-stu-id="f8dc5-133">Dive deeper into the information</span></span>

<span data-ttu-id="f8dc5-134">È possibile utilizzare il cloud Discovery per approfondire le app, i sottodomini, gli indirizzi IP e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-134">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="f8dc5-135">Nel dashboard individuazione cloud, scegliere la scheda **app individuate** .</span><span class="sxs-lookup"><span data-stu-id="f8dc5-135">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="f8dc5-136">Utilizzare la sezione filtri per visualizzare le app in base al nome, alla categoria, al livello di utilizzo o alla data dell'ultima visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-136">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="f8dc5-137">Nell'elenco dei risultati, posizionare il puntatore del mouse su un nome di app per rivelare il collegamento **Visualizza** i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-137">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span><br/> <span data-ttu-id="f8dc5-138">![Posizionare il puntatore del mouse accanto a un'app per rivelare un collegamento per visualizzare i dettagli del sottodominio](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-138">![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span></span><br/><span data-ttu-id="f8dc5-139">Verranno visualizzate informazioni dettagliate sull'app selezionata.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-139">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="f8dc5-140">Per visualizzare i dettagli sugli indirizzi IP, scegliere la scheda **indirizzi IP** .</span><span class="sxs-lookup"><span data-stu-id="f8dc5-140">To view details about IP addresses, choose the **IP addresses** tab.</span></span><br/><span data-ttu-id="f8dc5-141">![Individuazione cloud Visualizza informazioni dettagliate sugli indirizzi IP](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-141">![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span></span><br/><span data-ttu-id="f8dc5-142">Nell'elenco dei risultati, selezionare un singolo indirizzo IP per visualizzare informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-142">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="f8dc5-143">Per visualizzare i dettagli relativi agli utenti di Office 365 all'interno dell'organizzazione, scegliere la scheda **utenti** .</span><span class="sxs-lookup"><span data-stu-id="f8dc5-143">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span><br/><span data-ttu-id="f8dc5-144">![Discovery Cloud-informazioni sugli utenti](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-144">![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span></span>
  
## <a name="exclude-entities"></a><span data-ttu-id="f8dc5-145">Escludi entità</span><span class="sxs-lookup"><span data-stu-id="f8dc5-145">Exclude entities</span></span>

<span data-ttu-id="f8dc5-146">È possibile escludere alcuni utenti di sistema o indirizzi IP per concentrarsi su informazioni più specifiche.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-146">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="f8dc5-147">Scegliere Settings **cloud Discovery Settings**. \*\*\*\* \></span><span class="sxs-lookup"><span data-stu-id="f8dc5-147">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="f8dc5-148">Scegliere **Escludi entità**.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-148">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="f8dc5-149">Scegliere **gli utenti esclusi** o **gli indirizzi IP esclusi**.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-149">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="f8dc5-150">Specificare gli utenti o gli indirizzi IP e, nella casella **Commenti** , digitare le informazioni sui motivi per cui si escludono gli utenti o gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-150">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="f8dc5-151">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-151">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="f8dc5-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f8dc5-152">Next steps</span></span>

- [<span data-ttu-id="f8dc5-153">Esaminare e intervenire sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="f8dc5-153">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="f8dc5-154">Creare report di individuazione delle app</span><span class="sxs-lookup"><span data-stu-id="f8dc5-154">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="f8dc5-155">Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-155">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

