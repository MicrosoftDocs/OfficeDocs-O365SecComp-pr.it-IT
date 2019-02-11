---
title: Secure Score di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/25/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: Come mai il livello di protezione dell'organizzazione effettivamente presente in Office 365? Punteggio sicura è qui Guida in linea. Punteggio sicura analizza la protezione dell'organizzazione in base alle normali attività e le impostazioni di sicurezza in Office 365 e assegna un punteggio.
ms.openlocfilehash: bc0379e40b09e63e5fded1b1a289d40c306def91
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559089"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="78e6a-105">Secure Score di Office 365</span><span class="sxs-lookup"><span data-stu-id="78e6a-105">Office 365 Secure Score</span></span>

<span data-ttu-id="78e6a-p102">**Riepilogo** Come mai il livello di protezione dell'organizzazione effettivamente presente in Office 365? Punteggio sicura è qui Guida in linea. Punteggio sicura analizza la protezione dell'organizzazione in base alle normali attività e le impostazioni di sicurezza in Office 365 e assegna un punteggio. In questo articolo per una panoramica di punteggio sicura e su come è possibile utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="78e6a-p102">**Summary** Ever wonder how secure your organization really is in Office 365? Secure Score is here to help. Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score. Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="78e6a-110">Come ottenere sicura punteggio</span><span class="sxs-lookup"><span data-stu-id="78e6a-110">How to get to Secure Score</span></span>

<span data-ttu-id="78e6a-111">Se l'organizzazione dispone di una sottoscrizione che include [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/)o Business Premium di Office 365 e si dispone delle [autorizzazioni necessarie](#required-permissions), è possibile visualizzare punteggio protette della propria organizzazione, visitare il sito [https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="78e6a-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="78e6a-112">In alternativa, è possibile visitare il centro conformità di & protezione ([https://protection.office.com](https://protection.office.com)), dove troverai un widget punteggio sicuro che offre il punteggio corrente.</span><span class="sxs-lookup"><span data-stu-id="78e6a-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![Secure widget punteggio](media/SecureScoreWidget-o365.png)

<span data-ttu-id="78e6a-114">Widget include un collegamento al dashboard punteggio sicura.</span><span class="sxs-lookup"><span data-stu-id="78e6a-114">The widget includes a link to your Secure Score dashboard.</span></span>

![Secure punteggio dashboard](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="78e6a-116">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="78e6a-116">How it works</span></span>

<span data-ttu-id="78e6a-p103">Punteggio sicura determina quali servizi di Office 365 in uso (ad esempio, OneDrive, SharePoint ed Exchange) quindi confronta le impostazioni e delle attività alla linea di base stabilita da Microsoft. Verrà visualizzato un punteggio in base alla modalità allineata in modo corretto nell'organizzazione è con suggerimenti per la protezione. Verranno inoltre presentati suggerimenti sulla procedura da eseguire per migliorare il punteggio dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78e6a-p103">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft. You'll get a score based on how well aligned your organization is with security best practices. You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![Coda di azioni nello strumento di Office 365 sicura punteggio](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="78e6a-p104">Punteggio sicura calcola il punteggio in base ai servizi che è stato acquistato. Se è stato acquistato solo un piano di Exchange Online, non sarà ad esempio, essere catalogato per la funzionalità di sicurezza di SharePoint Online. Denominatore del punteggio di è la somma di tutte le linee di base per i controlli che si applicano ai prodotti che è stato acquistato. Numeratore è la somma di tutti i controlli di cui è completata o completata parzialmente, le azioni per soddisfare tale controllo.</span><span class="sxs-lookup"><span data-stu-id="78e6a-p104">Secure Score calculates your score based on the services you purchased. For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features. The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased. The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="78e6a-125">Espandere un'azione per conoscere i passaggi da eseguire, le minacce che saranno utili protezione da e il numero di punti punteggio aumenterà dopo che è seguire i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="78e6a-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![Azione espansa nello strumento di Office 365 sicura punteggio](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="78e6a-127">Per visualizzare l'impatto delle proprie azioni in sicurezza della propria organizzazione, selezionare la scheda **Punteggio Analyzer** e rivedere la cronologia delle.</span><span class="sxs-lookup"><span data-stu-id="78e6a-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![Scheda Analyzer punteggio dello strumento di Office 365 sicura punteggio](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="78e6a-129">Sotto il grafico verrà visualizzato un elenco di punteggi e azioni in base alla categoria.</span><span class="sxs-lookup"><span data-stu-id="78e6a-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![Grafico della scheda Analyzer punteggio con un punto di dati selezionato](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="78e6a-131">Azioni che sono contrassegnate come **[Non catalogato]** sono quelle eseguibili per l'organizzazione, ma poiché non sono connessi al punteggio sicura, non sono catalogati.</span><span class="sxs-lookup"><span data-stu-id="78e6a-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="78e6a-p105">Nella pagina **Analizzatore di punteggio** , fare clic su un punto di dati per un giorno specifico, quindi scorrere verso il basso per vedere le azioni completate e da completare per quel giorno scoprire quali modificate. Il punteggio viene calcolato una volta al giorno (circa 1:00 AM PST). Se si apporta una modifica a un'azione misurata, il punteggio verrà aggiornati automaticamente il giorno successivo. Accetta un massimo di 48 ore essere presi in punteggio una modifica.</span><span class="sxs-lookup"><span data-stu-id="78e6a-p105">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed. The score is calculated once per day (around 1:00 AM PST). If you make a change to a measured action, the score will automatically update the next day. It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="78e6a-p106">Punteggio sicura non express una misura assoluta della probabilità che verranno ottenere superata. Consente di rappresentare l'estensione a cui si hanno adottato caratteristiche che consentono di compensare i rischi di viene superata. Nessun servizio può garantire che non essere superata e punteggio sicura non deve essere interpretato come una garanzia in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="78e6a-p106">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted features that can offset the risk of being breached. No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="78e6a-139">Come aiuta a proteggere punteggio</span><span class="sxs-lookup"><span data-stu-id="78e6a-139">How Secure Score helps</span></span>

<span data-ttu-id="78e6a-p107">Con punteggio sicura, è possibile migliorare condizioni di protezione dell'organizzazione utilizzando le funzionalità di protezione predefinite in Office 365 (molte delle quali già acquistato, ma potrebbe non essere presente). Informazioni approfondite su tali funzionalità consentono la massima di ricordare che verrà affidata la procedura appropriata per proteggere l'organizzazione da minacce.</span><span class="sxs-lookup"><span data-stu-id="78e6a-p107">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of). Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="78e6a-p108">Ma semplicemente provate per tale. Clienti che utilizzano sicura punteggio hanno registrato il punteggio di aumentare i clienti che non utilizzano lo stato coinvolge cinque volte. Il l'aumento della loro punteggio corrisponde con le funzionalità di sicurezza in uso nelle loro organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="78e6a-p108">But don't just take our word for it. Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it. (The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="78e6a-p109">Punteggio sicura non express una misura assoluta della probabilità che verranno ottenere superata. Consente di rappresentare l'estensione a cui si hanno adottato controlli che consentono di compensare il rischio che viene superata. Nessun servizio può garantire che non essere superata e sicura punteggio non deve essere interpretato come una garanzia in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="78e6a-p109">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted controls which can offset the risk of being breached. No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="78e6a-148">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="78e6a-148">Required permissions</span></span>

<span data-ttu-id="78e6a-149">Per visualizzare e utilizzare il dashboard di punteggio sicura, è necessario essere assegnato uno dei seguenti ruoli di Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="78e6a-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in Azure Active Directory:</span></span>
- <span data-ttu-id="78e6a-150">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="78e6a-150">Global Administrator</span></span>
- <span data-ttu-id="78e6a-151">Amministratore fatturazione</span><span class="sxs-lookup"><span data-stu-id="78e6a-151">Billing Administrator</span></span>
- <span data-ttu-id="78e6a-152">Amministratore utenti</span><span class="sxs-lookup"><span data-stu-id="78e6a-152">User Administrator</span></span>
- <span data-ttu-id="78e6a-153">Amministratore password</span><span class="sxs-lookup"><span data-stu-id="78e6a-153">Password Administrator</span></span>
- <span data-ttu-id="78e6a-154">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="78e6a-154">Security Administrator</span></span>
- <span data-ttu-id="78e6a-155">Lettore di sicurezza</span><span class="sxs-lookup"><span data-stu-id="78e6a-155">Security Reader</span></span>
- <span data-ttu-id="78e6a-156">Amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="78e6a-156">Exchange Administrator</span></span>
- <span data-ttu-id="78e6a-157">Amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="78e6a-157">SharePoint Administrator</span></span>

 <span data-ttu-id="78e6a-158">Gli utenti non assegnati a un ruolo di amministratore non saranno in grado di accedere punteggio sicura.</span><span class="sxs-lookup"><span data-stu-id="78e6a-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="78e6a-159">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="78e6a-159">Related topics</span></span>

[<span data-ttu-id="78e6a-160">Panoramica della sicurezza di dashboard</span><span class="sxs-lookup"><span data-stu-id="78e6a-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="78e6a-161">Qual è l’abbonamento corrente?</span><span class="sxs-lookup"><span data-stu-id="78e6a-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)