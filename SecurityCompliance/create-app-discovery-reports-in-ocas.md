---
title: Creare i report dell’individuazione di app con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Creare report con Office 365 cloud app Security che consentano di comprendere in che modo gli utenti dell'organizzazione utilizzano Office 365 e altre app.
ms.openlocfilehash: e0d515ddd9b08aa4a70276177060f273cc89949e
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087295"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="e08e7-103">Creare i report dell’individuazione di app con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e08e7-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="e08e7-104">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e08e7-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e08e7-105">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e08e7-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e08e7-106">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e08e7-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e08e7-107">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="e08e7-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e08e7-108">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="e08e7-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e08e7-109">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="e08e7-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e08e7-110">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="e08e7-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="e08e7-111">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="e08e7-111">You are here!</span></span>  <br/> [<span data-ttu-id="e08e7-112">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e08e7-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="e08e7-p101">Office 365 cloud app Security consente agli amministratori globali, agli amministratori della sicurezza e ai lettori di sicurezza di acquisire informazioni sui servizi cloud che sono in uso in un'organizzazione. Ad esempio, è possibile visualizzare la posizione in cui gli utenti archiviano e collaborano ai documenti e la quantità di dati caricati nelle app o nei servizi esterni a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e08e7-p101">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using. For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="e08e7-115">Per generare un report di individuazione delle app, è necessario caricare manualmente i file di registro del traffico Web dai firewall e dai proxy, quindi l'analisi dei file di Office 365 cloud app viene analizzata e analizzata per il report.</span><span class="sxs-lookup"><span data-stu-id="e08e7-115">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e08e7-p102">Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore globale, un amministratore della sicurezza o un lettore di sicurezza. Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e08e7-p102">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="e08e7-118">Creare un report con l'individuazione delle app</span><span class="sxs-lookup"><span data-stu-id="e08e7-118">Create a report with app discovery</span></span>

<span data-ttu-id="e08e7-119">Per creare un report di individuazione delle app, identificare l'origine dati del fornitore per i file di registro che si desidera analizzare, selezionare i file di registro e quindi richiedere il report.</span><span class="sxs-lookup"><span data-stu-id="e08e7-119">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e08e7-120">Utilizzare i file di registro del traffico Web che includono i periodi di traffico di picco per ottenere la migliore rappresentazione di utilizzo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e08e7-120">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="e08e7-121">Raccogliere i [log del traffico Web e le origini dati per Office 365 cloud app Security](web-traffic-logs-and-data-sources-for-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="e08e7-121">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="e08e7-122">Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.</span><span class="sxs-lookup"><span data-stu-id="e08e7-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> 
       
3. <span data-ttu-id="e08e7-123">Scegliere **Scopri** \> **Crea nuovo report**.</span><span class="sxs-lookup"><span data-stu-id="e08e7-123">Choose **Discover** \> **Create new report**.</span></span> <br><span data-ttu-id="e08e7-124">![Nel portale di Office 365 CAS, scegliere Scopri](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span><span class="sxs-lookup"><span data-stu-id="e08e7-124">![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span></span><br>
  
4. <span data-ttu-id="e08e7-125">Specificare un nome e una descrizione per il report e quindi selezionare l'origine dati per i log del traffico Web nell'elenco **origine dati** .</span><span class="sxs-lookup"><span data-stu-id="e08e7-125">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> <br><span data-ttu-id="e08e7-126">![In O365 CA, scegliere Scopri \> Crea nuovo rapporto](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span><span class="sxs-lookup"><span data-stu-id="e08e7-126">![In O365 CAS, choose Discover \> Create new report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span></span><br><span data-ttu-id="e08e7-p103">Se un'origine dati che si desidera utilizzare non è presente nell'elenco, è possibile richiederne l'aggiunta. Selezionare **altro** per **origine dati**e quindi digitare il nome dell'origine dati che si sta tentando di caricare. È possibile esaminare il registro e sapere se viene aggiunto il supporto per l'origine dati che lo ha generato.</span><span class="sxs-lookup"><span data-stu-id="e08e7-p103">If a data source that you'd like to use is not listed, you can request that it be added. Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload. We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
5. <span data-ttu-id="e08e7-p104">Passare al percorso dei file di registro raccolti e selezionare i file. È necessario che i file di registro siano stati generati dall'origine dati scelta per il report.</span><span class="sxs-lookup"><span data-stu-id="e08e7-p104">Browse to the location of the log files you collected and select the files. The log files must have been generated by the data source that you chose for the report.</span></span>
    
6. <span data-ttu-id="e08e7-132">Fare clic su **Crea** per avviare il processo di creazione del report.</span><span class="sxs-lookup"><span data-stu-id="e08e7-132">Click **Create** to start the report creation process.</span></span> 
    
7. <span data-ttu-id="e08e7-p105">Per visualizzare lo stato del report, fare clic su **Gestisci rapporti snapshot**. Quando un report è pronto, verrà visualizzata l'opzione **Visualizza rapporto** .</span><span class="sxs-lookup"><span data-stu-id="e08e7-p105">To see the status of the report, click **Manage snapshot reports**. When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="e08e7-135">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e08e7-135">Next steps</span></span>

- [<span data-ttu-id="e08e7-136">Esaminare e intervenire sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="e08e7-136">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="e08e7-137">Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e08e7-137">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="e08e7-138">Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="e08e7-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

