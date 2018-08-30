---
title: Preparazione di Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Introduzione all'utilizzo della protezione App Cloud di Office 365
ms.openlocfilehash: 906570c6607c70b63fa9d2059d56b50f7807124a
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23229988"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a><span data-ttu-id="6947d-103">Preparazione di Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6947d-103">Get ready for Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="6947d-104">Valutazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="6947d-104">****Evaluation** \>**</span></span>|<span data-ttu-id="6947d-105">Pianificazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="6947d-105">****Planning** \>**</span></span>|<span data-ttu-id="6947d-106">Distribuzione * *\>**</span><span class="sxs-lookup"><span data-stu-id="6947d-106">****Deployment** \>**</span></span>|<span data-ttu-id="6947d-107">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="6947d-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="6947d-108">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="6947d-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |<span data-ttu-id="6947d-109">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="6947d-109">You are here!</span></span>  <br/> [<span data-ttu-id="6947d-110">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6947d-110">Next step</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="6947d-111">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="6947d-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="6947d-112">Avviare utilizzando</span><span class="sxs-lookup"><span data-stu-id="6947d-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="6947d-p101">Durante la preparazione per attivare e implementare la protezione di Office 365 Cloud App (precedentemente noto come gestire la sicurezza avanzata) per l'organizzazione, esistono alcuni aspetti da prendere in considerazione. Utilizzare questo articolo come guida per pianificare la protezione di Office 365 Cloud App.</span><span class="sxs-lookup"><span data-stu-id="6947d-p101">As you prepare to turn on and implement Office 365 Cloud App Security (formerly known as Advanced Security Management) for your organization, there are a few things to take into account. Use this article as a guide to plan for Office 365 Cloud App Security.</span></span>
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a><span data-ttu-id="6947d-115">Passaggio 1: Identificare e proteggere gli account di amministratore globali e sicurezza</span><span class="sxs-lookup"><span data-stu-id="6947d-115">Step 1: Identify and protect your global and security administrator accounts</span></span>

<span data-ttu-id="6947d-p102">Gli amministratori globali, sicurezza e lettori sicurezza potranno accedere al portale di protezione di applicazioni di Office 365 Cloud per visualizzare i criteri, analizzare gli avvisi e utilizzare i rapporti. Gli amministratori globali e sicurezza può definire i criteri ed eseguire altre azioni per proteggere l'organizzazione. (Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).) Esaminare gli account utente dell'organizzazione che dispongono di autorizzazioni elevate costituisce una precauzione.</span><span class="sxs-lookup"><span data-stu-id="6947d-p102">Global administrators, security administrators, and security readers can access the Office 365 Cloud App Security portal to view policies, review alerts, and use reports. Global administrators and security administrators can define policies and take other actions to protect your organization. (For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).) Review your organization's user accounts that have elevated permissions as a precaution.</span></span> 
  
 <span data-ttu-id="6947d-119">**[Account amministratore globale Protect Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**.</span><span class="sxs-lookup"><span data-stu-id="6947d-119">**[Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**.</span></span> 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a><span data-ttu-id="6947d-120">Passaggio 2: Attivare la registrazione di controllo per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6947d-120">Step 2: Turn on audit logging for your organization</span></span>

<span data-ttu-id="6947d-p103">Perché Office 365 Cloud App sicurezza per il funzionamento corretto, la registrazione di controllo deve essere attivata. Questo viene in genere eseguito da un amministratore di Exchange Online o un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="6947d-p103">In order for Office 365 Cloud App Security to work correct, audit logging must be turned on. This is typically done by an Exchange Online administrator or a global administrator.</span></span>
  
 <span data-ttu-id="6947d-123">**[Attivare Office 365 ricerca dei registri di controllo attivato o disattivato](turn-audit-log-search-on-or-off.md)**.</span><span class="sxs-lookup"><span data-stu-id="6947d-123">**[Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md)**.</span></span> 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="6947d-124">Passaggio 3: Accedere al portale di Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6947d-124">Step 3: Go to the Office 365 Cloud App Security portal</span></span>

1. <span data-ttu-id="6947d-p104">Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. (Si passa alla sicurezza &amp; centro conformità.)</span><span class="sxs-lookup"><span data-stu-id="6947d-p104">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="6947d-127">Accedere agli **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="6947d-127">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="6947d-128">Scegliere **Vai alla protezione di Office 365 Cloud App** per accedere al portale di Office 365 Cloud App sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6947d-128">Choose **Go to Office 365 Cloud App Security** to go to the Office 365 Cloud App Security portal.</span></span> 
    
    ![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    <span data-ttu-id="6947d-130">Quando si passa al portale di Office 365 Cloud App sicurezza, la prima pagina che viene visualizzato è la pagina criteri, che è simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="6947d-130">When you go to the Office 365 Cloud App Security portal, the first page you see is the Policies page, which resembles the following image:</span></span>
    
    ![Quando si passa al portale di protezione di applicazioni di Office 365 Cloud, si inizia con la pagina criteri](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a><span data-ttu-id="6947d-132">Passaggio 4: Definire i criteri e impostare avvisi &amp; azioni</span><span class="sxs-lookup"><span data-stu-id="6947d-132">Step 4: Define policies and set up alerts &amp; actions</span></span>

<span data-ttu-id="6947d-p105">Gli amministratori globali e sicurezza definire i criteri di sicurezza di Office 365 Cloud App. Durante il processo di definizione dei criteri, gli avvisi e le azioni vengono impostate anche. Un avviso è una notifica in base ai criteri viene visualizzato in una visualizzazione o inviata tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6947d-p105">Global administrators and security administrators define policies in Office 365 Cloud App Security. During the process of defining policies, alerts and actions are also set. An alert is a criteria-based notification that appears in a view or is sent via email.</span></span> 
  
<span data-ttu-id="6947d-p106">Esistono due tipi di avvisi di protezione di applicazioni di Office 365 Cloud: avvisi di rilevamento anomalia rilevare attività sospette e avvisi, attività che vengono definiti per le attività che possono essere atipiche per l'organizzazione. Avvisi avvisare gli amministratori globali e sicurezza in caso di un'attività nell'ambiente Office 365 è insolito che l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6947d-p106">There are two types of alerts in Office 365 Cloud App Security: anomaly detection alerts that detect suspicious activity, and activity alerts, which are defined for activities that might be atypical for your organization. Alerts notify global administrators and security administrators when there's an activity in your Office 365 environment that's unusual for your organization.</span></span>
  
<span data-ttu-id="6947d-138">Le risorse seguenti per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="6947d-138">See the following resources to learn more:</span></span>
  
- [<span data-ttu-id="6947d-139">Criteri di attività e gli avvisi in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6947d-139">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="6947d-140">Criteri di rilevamento delle anomalie in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6947d-140">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="6947d-141">Leggere ed eseguire l'azione avvisi di protezione di Office 365 Cloud App</span><span class="sxs-lookup"><span data-stu-id="6947d-141">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="step-5-learn-about-your-organizations-cloud-usage"></a><span data-ttu-id="6947d-142">Passaggio 5: Informazioni sull'utilizzo del cloud dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6947d-142">Step 5: Learn about your organization's cloud usage</span></span>

<span data-ttu-id="6947d-p107">Come amministratore globale, amministratore della sicurezza o lettore di protezione, informazioni sull'utilizzo del cloud dell'organizzazione tramite reports e un dashboard di individuazione Cloud (denominato anche produttività App Discovery). Questo dashboard vengono visualizzate informazioni su utenti, App, il traffico web e livelli di rischio.</span><span class="sxs-lookup"><span data-stu-id="6947d-p107">As a global administrator, security administrator, or security reader, you can learn about your organization's cloud usage through reports and a Cloud Discovery dashboard (also called Productivity App Discovery). This dashboard shows information about users, apps, web traffic, and risk levels.</span></span>
  
![Nel portale di accesso client di Office 365, selezionare individuazione \> dashboard individuazione Cloud](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="6947d-146">Per passare al dashboard di individuazione applicazioni di produttività, nel portale Office 365 Cloud App sicurezza scegliere **individuazione** \> **individuazione Cloud dashboard**.</span><span class="sxs-lookup"><span data-stu-id="6947d-146">To go to the Productivity App Discovery dashboard, in the Office 365 Cloud App Security portal, choose **Discover** \> **Cloud Discovery dashboard**.</span></span>
  
![Nel portale di accesso client di Office 365, selezionare individuazione](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
<span data-ttu-id="6947d-p108">Per popolare relazioni con le informazioni che necessarie, caricare i file di registro da firewall dell'organizzazione e i proxy. Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="6947d-p108">To populate reports with the information you need, upload your log files from your organization's firewalls and proxies. To learn more, see the following resources:</span></span>
  
- [<span data-ttu-id="6947d-150">Creare i rapporti di individuazione applicazioni in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6947d-150">Create app discovery reports in Office 365 Cloud App Security</span></span>](create-app-discovery-reports-in-ocas.md)
    
- [<span data-ttu-id="6947d-151">Esaminare i risultati di App Discovery in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6947d-151">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-6-manage-apps-that-your-organization-is-using-to-access-office-365"></a><span data-ttu-id="6947d-152">Passaggio 6: Gestire le app nell'organizzazione vengono utilizzati per accedere a Office 365</span><span class="sxs-lookup"><span data-stu-id="6947d-152">Step 6: Manage apps that your organization is using to access Office 365</span></span>

<span data-ttu-id="6947d-p109">Un amministratore globale o un amministratore di sicurezza, è possibile gestire le applicazioni, ad esempio App personalizzate o applicazioni di terze parti, che gli utenti dell'organizzazione vengono utilizzato nei dispositivi con Office 365. Ad esempio, si supponga che un utente ha scaricato un'app personalizzata che si desidera utilizzare con Office 365. È possibile esaminare le applicazioni utilizzano persone, escludere applicazioni non attendibili o contrassegnare le applicazioni come approvati alle proprie esigenze di verifica. [Gestire le autorizzazioni di app con Office 365 Cloud App sicurezza](manage-app-permissions-in-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="6947d-p109">As a global administrator or security administrator, you can manage apps, such as custom apps or third-party apps, that people in your organization are using on their devices with Office 365. For example, suppose that someone has downloaded a custom app they want to use with Office 365. You can review the apps people are using, ban untrusted apps, or mark apps as approved for your tracking purposes. [Manage app permissions using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).</span></span>
  
## <a name="step-7-use-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="6947d-157">Passaggio 7: Utilizzare il server SIEM con Office 365 Cloud App protezione</span><span class="sxs-lookup"><span data-stu-id="6947d-157">Step 7: Use your SIEM server with Office 365 Cloud App Security</span></span>

<span data-ttu-id="6947d-p110">L'organizzazione utilizza un server di gestione (SIEM) eventi e informazioni di protezione? Office 365 Cloud App protezione a questo punto è possibile integrare con il server SIEM per abilitare il monitoraggio centralizzato degli avvisi. Integrazione con un servizio SIEM consente di migliorare la protezione delle applicazioni cloud durante la gestione del flusso di lavoro di sicurezza normale, automazione delle procedure di sicurezza e la correlazione tra basata su cloud e locali degli eventi. L'agente SIEM viene eseguito sul server, utilizza gli avvisi di protezione di applicazioni di Office 365 Cloud e crea un flusso di tali avvisi nel server di SIEM. Vedere [SIEM dell'integrazione con Office 365 Cloud App protezione](integrate-your-siem-server-with-office-365-cas.md).</span><span class="sxs-lookup"><span data-stu-id="6947d-p110">Is your organization using a security information and event management (SIEM) server? Office 365 Cloud App Security can now integrate with your SIEM server to enable centralized monitoring of alerts. Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events. The SIEM agent runs on your server, pulls alerts from Office 365 Cloud App Security, and streams those alerts into your SIEM server. See [SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="6947d-163">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6947d-163">Next steps</span></span>

- [<span data-ttu-id="6947d-164">Attivare Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6947d-164">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
- <span data-ttu-id="6947d-165">Provare la [Guida del laboratorio di testing](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) per un'esperienza pratica dove è possibile effettuare una dimostrazione delle funzionalità avanzate di protezione di applicazioni di Office 365 Cloud e creare un modello di prova.</span><span class="sxs-lookup"><span data-stu-id="6947d-165">Try our [Test Lab Guide](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) for a hands-on experience where you can demonstrate the powerful features of Office 365 Cloud App Security and create a proof of concept.</span></span> 
    

