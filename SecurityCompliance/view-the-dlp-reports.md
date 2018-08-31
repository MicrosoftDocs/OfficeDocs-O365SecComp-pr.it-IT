---
title: Visualizzare i report di prevenzione della perdita di dati
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 41eb4324-c513-4fa5-91c8-8fbd8aaba83b
description: Con i rapporti DLP in Office 365, è possibile visualizzare rapidamente il numero di corrispondenze di criteri DLP, sostituzioni o falsi positivi; Se si sta avvicinando verso l'alto o verso il basso nel tempo, vedere filtrare il report in vari modi; e visualizzare dettagli aggiuntivi selezionando un punto sulla linea nel grafico.
ms.openlocfilehash: 379e66fc3f2611cf338739d030c2b1d48e7416d8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013910"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="0a52a-103">Visualizzare i report di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="0a52a-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="0a52a-p101">Dopo aver creato la perdita di dati politiche di prevenzione (DLP), è consigliabile verificare che si sta lavorando come è lo scopo e servizio di supporto per garantire la conformità. Con il DLP report in Office 365 Security &amp; centro conformità, è possibile visualizzare rapidamente:</span><span class="sxs-lookup"><span data-stu-id="0a52a-p101">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="0a52a-p102">**Corrispondenze criteri DLP** In questo rapporto viene visualizzato il numero di corrispondenze di criteri DLP nel tempo. È possibile filtrare il report per data, posizione, criteri o azione. È possibile utilizzare questo report per:</span><span class="sxs-lookup"><span data-stu-id="0a52a-p102">**DLP policy matches** This report shows the count of DLP policy matches over time. You can filter the report by date, location, policy, or action. You can use this report to:</span></span> 
    
  - <span data-ttu-id="0a52a-p103">Ottimizzare o filtrare i criteri DLP come eseguirli in modalità test. È possibile visualizzare la regola specifica corrispondenti al contenuto.</span><span class="sxs-lookup"><span data-stu-id="0a52a-p103">Tune or refine your DLP policies as you run them in test mode. You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="0a52a-111">Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.</span><span class="sxs-lookup"><span data-stu-id="0a52a-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="0a52a-112">Individuare i processi aziendali che violano i criteri DLP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0a52a-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="0a52a-113">Acquisire familiarità con un impatto aziendale di criteri DLP visualizzando le azioni vengono applicate al contenuto.</span><span class="sxs-lookup"><span data-stu-id="0a52a-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="0a52a-114">Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.</span><span class="sxs-lookup"><span data-stu-id="0a52a-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="0a52a-115">Visualizzare un elenco degli utenti principali e ripetere gli utenti che contribuiscono a risolte all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0a52a-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="0a52a-116">Visualizzare un elenco dei tipi principali di informazioni riservate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0a52a-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="0a52a-p104">**Risolte DLP** Questo report mostra inoltre corrispondenze di criteri nel tempo, come report genera una corrispondenza per i criteri. Tuttavia, il criterio corrisponde report mostra corrisponde a un livello di regola. Se, ad esempio, un messaggio di posta elettronica corrispondenti a tre regole diverse, il criterio corrisponde report mostra tre diverse voci. Al contrario, il rapporto risolte Mostra corrisponde a un livello di elemento; ad esempio, se un messaggio di posta elettronica corrispondenti a tre regole diverse, il rapporto risolte Mostra una singola voce di tale parte del contenuto.</span><span class="sxs-lookup"><span data-stu-id="0a52a-p104">**DLP incidents** This report also shows policy matches over time, like the policy matches report. However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items. By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="0a52a-p105">Poiché i conteggi dei report è aggregati in modo diverso, il rapporto di corrispondenze di criteri è migliore per l'identificazione di corrispondenze con regole specifiche e regolazione criteri DLP. Il rapporto risolte è migliore per identificare le parti specifiche del contenuto sono problematiche per i criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="0a52a-p105">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies. The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="0a52a-p106">**Sostituzioni e falsi positivi DLP** Se il criterio DLP consente agli utenti di ignorare lo o un falso positivo, questo rapporto viene visualizzato un numero di istanze di questo tipo nel tempo. È possibile filtrare il report per data, posizione o criteri. È possibile utilizzare questo report per:</span><span class="sxs-lookup"><span data-stu-id="0a52a-p106">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time. You can filter the report by date, location, or policy. You can use this report to:</span></span> 
    
  - <span data-ttu-id="0a52a-125">Ottimizzare o filtrare i criteri DLP visualizzando i criteri comportano un numero elevato di falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="0a52a-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="0a52a-126">Consente di visualizzare motivazioni inviate dagli utenti durante la risoluzione di un suggerimento criterio ignorando il criterio.</span><span class="sxs-lookup"><span data-stu-id="0a52a-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="0a52a-127">Scopri dove esegue l'override di conflitto di criteri DLP con i processi aziendali valido, poiché richiede un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="0a52a-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="0a52a-p107">Tutti i rapporti DLP possono visualizzare i dati del periodo di tempo quattro mesi più recente. I dati più recenti possono richiedere fino a 24 ore per visualizzati nei rapporti.</span><span class="sxs-lookup"><span data-stu-id="0a52a-p107">All DLP reports can show data from the most recent four-month time period. The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="0a52a-130">È possibile trovare questi rapporti in sicurezza &amp; centro conformità \> **report** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="0a52a-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Corrispondenze di criteri DLP report](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="0a52a-132">Consente di visualizzare la motivazione inviata da un utente per un override</span><span class="sxs-lookup"><span data-stu-id="0a52a-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="0a52a-133">Se il criterio DLP consente agli utenti di ignorare lo, è possibile utilizzare il falso positivo e sostituire report per visualizzare il testo inviato dagli utenti durante il suggerimento sul criterio.</span><span class="sxs-lookup"><span data-stu-id="0a52a-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Campo giustificazione nei dettagli dei falsi positivi DLP e report di sostituzione](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="0a52a-135">Eseguire l'azione su informazioni e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="0a52a-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="0a52a-136">È possibile report visualizzati sui concetti e i suggerimenti dove è possibile fare clic sull'icona di avviso rosso per visualizzare i dettagli sui possibili problemi ed eseguire azioni correttive possibili.</span><span class="sxs-lookup"><span data-stu-id="0a52a-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Fare clic su un'icona informativa per visualizzare informazioni dettagliate e le azioni da eseguire](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="0a52a-138">Trovare i cmdlet per i rapporti DLP</span><span class="sxs-lookup"><span data-stu-id="0a52a-138">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="0a52a-139">Utilizzare la maggior parte dei cmdlet per la sicurezza &amp; centro conformità, è necessario:</span><span class="sxs-lookup"><span data-stu-id="0a52a-139">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="0a52a-140">Connettersi a Office 365 Security &amp; centro conformità utilizzando PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="0a52a-140">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="0a52a-141">Utilizzare una qualsiasi delle domande [protezione di Office 365 &amp; cmdlet centro conformità](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="0a52a-141">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="0a52a-p108">Tuttavia, rapporti DLP necessario estrarre dati da tra Office 365, inclusi Exchange Online. Per questo motivo, i cmdlet per i rapporti DLP sono disponibili in Exchange Online Powershell, ovvero non in sicurezza &amp; Powershell centro conformità. Pertanto, per utilizzare i cmdlet per i rapporti DLP, è necessario:</span><span class="sxs-lookup"><span data-stu-id="0a52a-p108">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="0a52a-145">Connessione a Exchange Online tramite remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a52a-145">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="0a52a-146">Utilizzare uno di questi cmdlet per i rapporti DLP:</span><span class="sxs-lookup"><span data-stu-id="0a52a-146">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="0a52a-147">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="0a52a-147">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="0a52a-148">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="0a52a-148">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

