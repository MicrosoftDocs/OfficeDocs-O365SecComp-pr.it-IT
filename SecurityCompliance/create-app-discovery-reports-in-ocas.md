---
title: Creare i report dell’individuazione di app con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Creare report con Office 365 Cloud App sicurezza che consentono di comprendere come vengono utilizzati gli utenti dell'organizzazione Office 365 e altre applicazioni.
ms.openlocfilehash: f801c70e839a62b5bbb5423ff5e7c513dd1f09b4
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706300"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="dd60e-103">Creare i report dell’individuazione di app con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dd60e-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

<span data-ttu-id="dd60e-104">Gestione di sicurezza avanzata di Office 365 è sicurezza App Cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd60e-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="dd60e-105">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="dd60e-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="dd60e-106">Pianificazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="dd60e-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="dd60e-107">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="dd60e-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="dd60e-108">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="dd60e-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="dd60e-109">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="dd60e-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="dd60e-110">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="dd60e-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="dd60e-111">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="dd60e-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="dd60e-112">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="dd60e-112">You are here!</span></span>  <br/> [<span data-ttu-id="dd60e-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="dd60e-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="dd60e-p101">Protezione di Office 365 Cloud App consente agli amministratori globali, gli amministratori della protezione e lettori sicurezza approfondire servizi cloud utilizzano utenti dell'organizzazione. Ad esempio, è possibile visualizzare gli utenti archiviazione che collaborano sui documenti e la quantità di dati è in fase di caricamento per le applicazioni o servizi che si trovano all'esterno di Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd60e-p101">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using. For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="dd60e-116">Per generare un report di individuazione applicazioni, è caricare manualmente i file di registro del traffico web dai firewall e i proxy e quindi protezione di Office 365 Cloud App analizza e consente di analizzare i file per il report.</span><span class="sxs-lookup"><span data-stu-id="dd60e-116">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd60e-p102">È necessario essere un amministratore globale, l'amministratore della sicurezza o lettore di protezione per eseguire le attività descritte in questo articolo. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="dd60e-p102">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="dd60e-119">Creare un rapporto con individuazione app</span><span class="sxs-lookup"><span data-stu-id="dd60e-119">Create a report with app discovery</span></span>

<span data-ttu-id="dd60e-120">Per creare un report di individuazione applicazioni, si identifica l'origine dati di un fornitore per i file di registro che si desidera avere analizzata, selezionare i file di registro e quindi richiede il report.</span><span class="sxs-lookup"><span data-stu-id="dd60e-120">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd60e-121">Utilizzare i file di log del traffico web che includono i periodi di picco traffico per ottenere la migliore rappresentazione dei dati di utilizzo nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd60e-121">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="dd60e-122">Raccogliere i [registri di traffico web e le origini dati per la protezione di Office 365 Cloud App](web-traffic-logs-and-data-sources-for-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="dd60e-122">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="dd60e-123">Accedere a [https://security.microsoft.com](https://security.microsoft.com) e accedere utilizzando l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="dd60e-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in using your work or school account.</span></span> 
    
3. <span data-ttu-id="dd60e-124">In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="dd60e-124">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
4. <span data-ttu-id="dd60e-125">Scegliere **Vai a Office 365 Cloud App protezione**.</span><span class="sxs-lookup"><span data-stu-id="dd60e-125">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
5. <span data-ttu-id="dd60e-126">Scegliere **individuazione** \> **Crea un nuovo report**.</span><span class="sxs-lookup"><span data-stu-id="dd60e-126">Choose **Discover** \> **Create new report**.</span></span>
    
    ![Nel portale di accesso client di Office 365, selezionare individuazione](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
6. <span data-ttu-id="dd60e-128">Specificare un nome e una descrizione per il report e quindi selezionare l'origine dati per i registri di traffico web nell'elenco **origine dati** .</span><span class="sxs-lookup"><span data-stu-id="dd60e-128">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> 
    
    ![In accesso client di Office 365, selezionare individuazione \> creare nuovi report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)
  
    > [!NOTE]
    > <span data-ttu-id="dd60e-p103">Se un'origine dati che si desidera utilizzare non è elencata, è possibile richiedere che da aggiungere. Selezionare **altri** per **origine dati**e quindi digitare il nome dell'origine dati che si sta tentando di caricare. Si verrà esaminare il registro e consentono di conoscere se viene aggiunto il supporto per l'origine dati che lo ha generato.</span><span class="sxs-lookup"><span data-stu-id="dd60e-p103">If a data source that you'd like to use is not listed, you can request that it be added. Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload. We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
7. <span data-ttu-id="dd60e-p104">Passare al percorso dei file di registro che raccolti e selezionare i file. I file di registro devono essere stati generati dall'origine dati che si è scelto per il report.</span><span class="sxs-lookup"><span data-stu-id="dd60e-p104">Browse to the location of the log files you collected and select the files. The log files must have been generated by the data source that you chose for the report.</span></span>
    
8. <span data-ttu-id="dd60e-135">Fare clic su **Crea** per avviare il processo di creazione di report.</span><span class="sxs-lookup"><span data-stu-id="dd60e-135">Click **Create** to start the report creation process.</span></span> 
    
9. <span data-ttu-id="dd60e-p105">Per visualizzare lo stato del report, fare clic su **Gestisci snapshot rapporti**. Quando un report è pronto, verrà visualizzato l'opzione **Visualizza report** .</span><span class="sxs-lookup"><span data-stu-id="dd60e-p105">To see the status of the report, click **Manage snapshot reports**. When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="dd60e-138">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="dd60e-138">Next steps</span></span>

- [<span data-ttu-id="dd60e-139">Leggere ed eseguire l'azione gli avvisi</span><span class="sxs-lookup"><span data-stu-id="dd60e-139">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="dd60e-140">Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dd60e-140">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="dd60e-141">Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="dd60e-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

