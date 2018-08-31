---
title: Rapporti di supervisione
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: Utilizzare rapporti di supervisione per visualizzare i messaggi di posta elettronica necessario esaminare la conformità e che devono eseguire.
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530398"
---
# <a name="supervision-reports"></a><span data-ttu-id="b53d6-103">Rapporti di supervisione</span><span class="sxs-lookup"><span data-stu-id="b53d6-103">Supervision reports</span></span>

<span data-ttu-id="b53d6-p101">Definiscono criteri di supervisione cui communications all'interno dell'organizzazione devono revisione per la conformità e che verranno eseguite le valutazioni. Utilizzare i rapporti di supervisione esaminare l'attività di verifica a livello di criteri e revisore. Per ogni criterio, è inoltre possibile visualizzare le statistiche live sullo stato corrente dell'attività di verifica. [Ulteriori informazioni sui criteri di supervisione](configure-supervision-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="b53d6-p101">Supervision policies define which communications in your organization need review for compliance, and who will perform those reviews. Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. [Learn more about supervision policies ](configure-supervision-policies.md) .</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b53d6-p102">Utilizzo dei criteri di supervisione richiede una sottoscrizione a Office 365 E5 per l'organizzazione. Se non sono dial plan e desidera provare supervisione, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="b53d6-p102">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b53d6-110">È possibile utilizzare i rapporti di supervisione:</span><span class="sxs-lookup"><span data-stu-id="b53d6-110">You can use the supervision reports to:</span></span>
  
- <span data-ttu-id="b53d6-111">Verificare che i criteri funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="b53d6-111">Verify that your policies are working as you intended.</span></span> 
    
- <span data-ttu-id="b53d6-112">Scoprire quanti messaggi di posta elettronica viene identificati per la revisione.</span><span class="sxs-lookup"><span data-stu-id="b53d6-112">Find out how many emails are being identified for review.</span></span>
    
- <span data-ttu-id="b53d6-p103">Scoprire quanti messaggi di posta elettronica non è conforme e quelli che stanno passando la revisione. Queste informazioni consentono di decidere se ottimizzare i criteri o modificare il numero di revisori.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p103">Find out how many emails aren't compliant and which ones are passing review. This information can help you decide whether to fine-tune your policies or change the number of reviewers.</span></span>
    
## <a name="view-the-supervision-report"></a><span data-ttu-id="b53d6-115">Visualizzare il report di supervisione</span><span class="sxs-lookup"><span data-stu-id="b53d6-115">View the Supervision report</span></span>

1. <span data-ttu-id="b53d6-116">Accedere al [protezione &amp; centro conformità](https://protection.office.com/) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365 con le autorizzazioni per visualizzare i report di supervisione..</span><span class="sxs-lookup"><span data-stu-id="b53d6-116">Sign into the [Security &amp; Compliance Center](https://protection.office.com/) using the credentials for an admin account in your Office 365 organization that has permissions to view supervision reports..</span></span> 
    
2. <span data-ttu-id="b53d6-p104">Accedere a **rapporti** \> **Dashboard**. Verrà visualizzato un report widget per la supervisione e altri report è possibile accedere al.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p104">Go to **Reports** \> **Dashboard**. You'll see a reporting widget for supervision and other reports you have access to.</span></span>
    
3. <span data-ttu-id="b53d6-119">Fare clic su widget **supervisione** per aprire la pagina report dettagliato.</span><span class="sxs-lookup"><span data-stu-id="b53d6-119">Click the **Supervision** widget to open the detailed report page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b53d6-p105">Se non si è in grado di accedere alla pagina di **report** , verificare che l'utente sia un membro del gruppo di ruoli revisione supervisione come illustrato in [rendere supervisione disponibili nell'organizzazione](configure-supervision-policies.md#SRavailable). L'inclusione nel consente di gruppo ruolo creare e gestire supervisione criteri ed eseguire il report.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p105">If you aren't able to access the **Reports** page, check that you're a member of the Supervisory Review role group, as described in [Make supervision available in your organization](configure-supervision-policies.md#SRavailable). Being included in this role group lets you create and manage supervision polices and run the report.</span></span> 
  
## <a name="how-to-use-the-report"></a><span data-ttu-id="b53d6-122">Come utilizzare i report</span><span class="sxs-lookup"><span data-stu-id="b53d6-122">How to use the report</span></span>

<span data-ttu-id="b53d6-p106">Quando un criterio di supervisione identifica un messaggio di posta elettronica per la revisione, il messaggio di posta elettronica viene recapitato nella cartella di supervisione del revisore in Outlook e Outlook web app. In questo report sono elencati il nome di ogni criterio e il numero delle comunicazioni in ogni fase del processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p106">When a supervision policy identifies an email for review, the email is delivered to the reviewer's Supervision folder in Outlook and Outlook web app. This report lists each policy's name and the number of communications at each stage in the review process.</span></span>
  
<span data-ttu-id="b53d6-125">Utilizzare il report per:</span><span class="sxs-lookup"><span data-stu-id="b53d6-125">Use the report to:</span></span>
  
- <span data-ttu-id="b53d6-126">Visualizzare i dati per tutti i criteri specifici o.</span><span class="sxs-lookup"><span data-stu-id="b53d6-126">View data for all or specific policies.</span></span>
    
- <span data-ttu-id="b53d6-127">Visualizzare i dati raggruppati per tipo di tag (ad esempio conforme, Questionable e così via), revisore o tipo di messaggio.</span><span class="sxs-lookup"><span data-stu-id="b53d6-127">View data grouped by tag type (such as Compliant, Questionable, etc.), reviewer, or message type.</span></span>
    
- <span data-ttu-id="b53d6-128">Esportare dati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="b53d6-128">Export data to a CSV file.</span></span>
    
- <span data-ttu-id="b53d6-129">Filtrare i dati in base a rivedere data dell'attività, tipo di tag, revisore, tipo di messaggio.</span><span class="sxs-lookup"><span data-stu-id="b53d6-129">Filter data based on review activity date, tag type, reviewer, message type.</span></span>
    
<span data-ttu-id="b53d6-130">Di seguito vengono illustrati i valori che potrebbe essere presente nella colonna **tipo di Tag** .</span><span class="sxs-lookup"><span data-stu-id="b53d6-130">Here's a breakdown of the values you might see in the **Tag type** column.</span></span> 
  
|<span data-ttu-id="b53d6-131">**Tipo di tag**</span><span class="sxs-lookup"><span data-stu-id="b53d6-131">**Tag type**</span></span>|<span data-ttu-id="b53d6-132">**Significato**</span><span class="sxs-lookup"><span data-stu-id="b53d6-132">**What it means**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b53d6-133">Non è stato rivisto</span><span class="sxs-lookup"><span data-stu-id="b53d6-133">Not Reviewed</span></span>  <br/> |<span data-ttu-id="b53d6-p107">Il numero di messaggi di posta elettronica non ancora riviste. Questi messaggi di posta elettronica sono in attesa di revisione nella cartella di supervisione del revisore di Outlook.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p107">The number of emails that have not been reviewed yet. These emails are awaiting review in the reviewer's supervision folder in Outlook.</span></span>  <br/> |
|<span data-ttu-id="b53d6-136">Compatible</span><span class="sxs-lookup"><span data-stu-id="b53d6-136">Compliant</span></span>  <br/> |<span data-ttu-id="b53d6-p108">Il numero di messaggi di posta elettronica esaminato e contrassegnato come compatibile. Non è necessaria alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p108">The number of emails reviewed and marked as compliant. No further action is needed.</span></span>  <br/> |
|<span data-ttu-id="b53d6-139">Ambigui</span><span class="sxs-lookup"><span data-stu-id="b53d6-139">Questionable</span></span>  <br/> |<span data-ttu-id="b53d6-p109">Il numero di messaggi di posta elettronica esaminato e contrassegnati ambigui. Questo funge da un contrassegno; altri revisori consentono di controllare se un messaggio di posta elettronica deve indagini per motivi di conformità.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p109">The number of emails reviewed and marked questionable. This acts as a flag; other reviewers can help check whether an email needs investigation for compliance.</span></span>  <br/> |
|<span data-ttu-id="b53d6-142">Non conforme (attivo)</span><span class="sxs-lookup"><span data-stu-id="b53d6-142">Non-Compliant (Active)</span></span>  <br/> |<span data-ttu-id="b53d6-143">Il numero di messaggi di posta elettronica non conforme che sono attualmente analisi dei revisori.</span><span class="sxs-lookup"><span data-stu-id="b53d6-143">The number of non-compliant emails that reviewers are currently investigating.</span></span>  <br/> |
|<span data-ttu-id="b53d6-144">Non è compatibile (risolti)</span><span class="sxs-lookup"><span data-stu-id="b53d6-144">Non-Compliant (Resolved)</span></span>  <br/> |<span data-ttu-id="b53d6-145">Il numero di messaggi di posta elettronica non compatibili con i revisori esaminate e risolti.</span><span class="sxs-lookup"><span data-stu-id="b53d6-145">The number of non-compliant emails that reviewers investigated and resolved.</span></span>  <br/> |
   
## <a name="more-details"></a><span data-ttu-id="b53d6-146">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b53d6-146">More details</span></span>

- <span data-ttu-id="b53d6-147">Criteri di supervisione devono innanzitutto effettuare il provisioning prima che verranno visualizzate nel report.</span><span class="sxs-lookup"><span data-stu-id="b53d6-147">Supervision policies must first be provisioned before they will appear in this report.</span></span>
    
- <span data-ttu-id="b53d6-p110">Se vengono eliminati i criteri, i dati cronologici viene ancora visualizzati. Tuttavia, viene indicati come "criterio inesistente" e la funzione di **esportazione** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p110">If policies are deleted, historical data is still shown. However, they're indicated as a "Non-existent policy", and the **Export** function isn't available.</span></span> 
    
- <span data-ttu-id="b53d6-p111">Se il report non è presente alcun dato per impostazione predefinita, potrebbe essere perché l'intervallo di date corrente non contiene dati da visualizzare. In questi casi, utilizzare il controllo di **filtri** per modificare l'intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="b53d6-p111">If the report doesn't show any data by default, it might be because the current date range doesn't have any data to show. In these cases, use the **Filters** control to change the date range.</span></span> 
    

