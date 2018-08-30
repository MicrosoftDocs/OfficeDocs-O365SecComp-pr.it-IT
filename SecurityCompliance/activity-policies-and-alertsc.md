---
title: Criteri di attività e gli avvisi in Office 365 Cloud App Security
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
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: Definire i criteri di attività con Office 365 Cloud App protezione per impostare gli avvisi per attivare indicanti l'attività specifiche eseguite avvenire troppo spesso. Tramite l'impostazione dei criteri per attivare gli avvisi, possono essere informati e monitorare le attività specifiche.
ms.openlocfilehash: a239e2bf453a01bf852a702a66cb2f09c02b8c96
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272371"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="7a46c-104">Criteri di attività e gli avvisi in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7a46c-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

<span data-ttu-id="7a46c-105">Gestione di sicurezza avanzata di Office 365 è sicurezza App Cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a46c-105">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="7a46c-106">Valutazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="7a46c-106">****Evaluation** \>**</span></span>|<span data-ttu-id="7a46c-107">Pianificazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="7a46c-107">****Planning** \>**</span></span>|<span data-ttu-id="7a46c-108">Distribuzione * *\>**</span><span class="sxs-lookup"><span data-stu-id="7a46c-108">****Deployment** \>**</span></span>|<span data-ttu-id="7a46c-109">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="7a46c-109">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="7a46c-110">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="7a46c-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="7a46c-111">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="7a46c-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="7a46c-112">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="7a46c-112">You are here!</span></span>  <br/> [<span data-ttu-id="7a46c-113">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7a46c-113">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="7a46c-114">Avviare utilizzando</span><span class="sxs-lookup"><span data-stu-id="7a46c-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="7a46c-p102">Con Office 365 Cloud App protezione, i criteri di gestione avanzata cloud attivano gli avvisi per attività specifiche eseguite o avvenire troppo spesso. Si supponga, ad esempio, un utente tenta di accedere a Office 365 e si verifica un errore volte 70 in un minuto. Si supponga che consente di scaricare 7.000 file un altro utente o sembra essere effettuato l'accesso dal Canada, quando l'utente deve per essere in un'altra posizione. O peggiori, si supponga che di un utente account è stata danneggiata e un utente malintenzionato utilizza tale account per l'accesso applicazioni basate su cloud dell'organizzazione e i dati riservati.</span><span class="sxs-lookup"><span data-stu-id="7a46c-p102">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently. For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute. Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location. Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="7a46c-p103">Se si è un [amministratore globale o amministratore di protezione](permissions-in-the-security-and-compliance-center.md), gli avvisi attività notificare è quando questi eventi si verificano. È quindi possibile eseguire azioni specifiche, ad esempio la sospensione di un account utente fino a quando non è possibile provare a utilizzare Dov'.</span><span class="sxs-lookup"><span data-stu-id="7a46c-p103">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur. You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a46c-p104">Criteri di protezione di applicazione Cloud di Office 365 sono diversi dai [avviso criteri in Office 365 Security &amp; centro conformità](alert-policies.md). L'attività criteri descritti in questo articolo vengono definiti nel portale di Office 365 Cloud App protezione e consentono di migliorare la gestione ambiente basato su cloud dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7a46c-p104">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md). The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="7a46c-123">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="7a46c-123">Before you begin</span></span>

<span data-ttu-id="7a46c-124">Verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7a46c-124">Make sure that:</span></span>
  
- <span data-ttu-id="7a46c-125">L'organizzazione dispone di [Protezione di Office 365 Cloud App](office-365-cas-overview.md)e il servizio è [attivata](turn-on-office-365-cas.md).</span><span class="sxs-lookup"><span data-stu-id="7a46c-125">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="7a46c-126">[Registrazione di controllo](turn-audit-log-search-on-or-off.md) è attivata per l'ambiente Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a46c-126">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="7a46c-127">Si è un amministratore globale o un amministratore di protezione per Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a46c-127">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="7a46c-128">Creare un nuovo criterio di attività</span><span class="sxs-lookup"><span data-stu-id="7a46c-128">Create a new activity policy</span></span>

1. <span data-ttu-id="7a46c-129">Un amministratore globale o un amministratore di protezione, passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="7a46c-129">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="7a46c-130">In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="7a46c-130">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="7a46c-131">Scegliere **Vai a Office 365 Cloud App protezione**.</span><span class="sxs-lookup"><span data-stu-id="7a46c-131">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    <span data-ttu-id="7a46c-132">Verrà visualizzata la pagina Criteri di protezione di Office 365 Cloud App.</span><span class="sxs-lookup"><span data-stu-id="7a46c-132">This takes you to the Office 365 Cloud App Security Policies page.</span></span>
    
    ![Quando si passa al portale di protezione di applicazioni di Office 365 Cloud, si inizia con la pagina criteri](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
4. <span data-ttu-id="7a46c-134">Fare clic su **Crea un criterio**e quindi selezionare **il criterio di attività**.</span><span class="sxs-lookup"><span data-stu-id="7a46c-134">Click **Create policy**, and then select **Activity policy**.</span></span>
    
    ![Quando si crea un criterio di accesso client di Office 365, è possibile scegliere tra i criteri di attività e rilevamento anomalia.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
5. <span data-ttu-id="7a46c-p105">Nella pagina **Crea un criterio attività** consente di specificare il **nome del criterio** e la **Descrizione**. Per definire un criterio di base su un modello predefinito, scegliere uno nell'elenco **modello dei criteri** o creare i criteri senza utilizzare un modello.</span><span class="sxs-lookup"><span data-stu-id="7a46c-p105">On the **Create activity policy** page, specify the **Policy name** and **Description**. To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span> 
    
    ![È possibile creare criteri di attività con Office 365 Cloud App protezione.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
6. <span data-ttu-id="7a46c-p106">Selezionare un **livello di gravità criteri** (bassa, Media o alta) che misura come gravi è all'utente se questo criterio viene generato un avviso. Sarà quindi possibile filtrare gli avvisi quando è esame più avanti.</span><span class="sxs-lookup"><span data-stu-id="7a46c-p106">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert. This will help you filter alerts when you're reviewing them later.</span></span> 
    
7. <span data-ttu-id="7a46c-p107">Scegliere una **categoria** per questo criterio. Ciò consente di filtrare e ordinare gli avvisi che sono stati attivati o criteri di gruppo quando viene esaminata al loro di apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="7a46c-p107">Choose a **Category** for this policy. This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
8. <span data-ttu-id="7a46c-143">Scegliere **filtri attività** di configurazione di altre azioni o metriche che verranno generato un avviso in base a questo criterio.</span><span class="sxs-lookup"><span data-stu-id="7a46c-143">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
9. <span data-ttu-id="7a46c-144">In **attività corrispondenza con i parametri**, specificare se la violazione dei criteri viene attivata quando una singola attività genera una corrispondenza per i filtri, o se è necessario un numero specificato di attività ripetute prima di trigger avviso.</span><span class="sxs-lookup"><span data-stu-id="7a46c-144">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span>
    
    <span data-ttu-id="7a46c-145">Se si seleziona **Repeated attività**, specificare il numero di attività, l'intervallo di tempo, e indica se una violazione verrà inclusi nel conteggio di un utente all'interno di un'app specifica o per lo stesso utente con le app.</span><span class="sxs-lookup"><span data-stu-id="7a46c-145">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
10. <span data-ttu-id="7a46c-146">Facoltativamente, è possibile selezionare **avviso crea** per creare ulteriori avvisi per la ricezione di notifiche da questo criterio (tramite posta elettronica, SMS o entrambi).</span><span class="sxs-lookup"><span data-stu-id="7a46c-146">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7a46c-147">Assicurarsi che il provider di posta elettronica non Blocca messaggi di posta elettronica inviati da no-reply@cloudappsecurity.com.</span><span class="sxs-lookup"><span data-stu-id="7a46c-147">Make sure that your email provider doesn't block emails sent from no-reply@cloudappsecurity.com.</span></span> 
  
11. <span data-ttu-id="7a46c-148">Scegliere le **Azioni** da eseguire quando viene generato un avviso per sospendere l'utente o richiedere all'utente di effettuare nuovamente l'accesso alle app di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7a46c-148">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
12. <span data-ttu-id="7a46c-149">Scegliere **Crea** per completare la creazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="7a46c-149">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="7a46c-150">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7a46c-150">Next steps</span></span>
<span data-ttu-id="7a46c-151"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="7a46c-151"></span></span>

- [<span data-ttu-id="7a46c-152">Criteri di rilevamento anomalia</span><span class="sxs-lookup"><span data-stu-id="7a46c-152">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="7a46c-153">Integrare il server SIEM</span><span class="sxs-lookup"><span data-stu-id="7a46c-153">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="7a46c-154">Leggere ed eseguire l'azione gli avvisi</span><span class="sxs-lookup"><span data-stu-id="7a46c-154">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="7a46c-155">Gli indirizzi IP per semplificare la gestione di gruppo</span><span class="sxs-lookup"><span data-stu-id="7a46c-155">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    
