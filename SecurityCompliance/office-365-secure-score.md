---
title: Office 365 Secure Score
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: Vi è mai chiesto come la sicurezza dell'organizzazione sia davvero in Office 365? Il Punteggio sicuro è qui per aiutarti. Secure Score analizza la sicurezza dell'organizzazione in base alle normali attività e alle impostazioni di sicurezza di Office 365 e assegna un punteggio.
ms.openlocfilehash: dd0dc87910853eba9f2ec3ec6752e857462b46e5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262464"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="3848f-105">Office 365 Secure Score</span><span class="sxs-lookup"><span data-stu-id="3848f-105">Office 365 Secure Score</span></span>

<span data-ttu-id="3848f-106">**Riepilogo** Vi è mai chiesto come la sicurezza dell'organizzazione sia davvero in Office 365?</span><span class="sxs-lookup"><span data-stu-id="3848f-106">**Summary** Ever wonder how secure your organization really is in Office 365?</span></span> <span data-ttu-id="3848f-107">Il Punteggio sicuro è qui per aiutarti.</span><span class="sxs-lookup"><span data-stu-id="3848f-107">Secure Score is here to help.</span></span> <span data-ttu-id="3848f-108">Secure Score analizza la sicurezza dell'organizzazione in base alle normali attività e alle impostazioni di sicurezza di Office 365 e assegna un punteggio.</span><span class="sxs-lookup"><span data-stu-id="3848f-108">Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score.</span></span> <span data-ttu-id="3848f-109">Leggere questo articolo per ottenere una panoramica del Punteggio sicuro e come utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="3848f-109">Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="3848f-110">Come ottenere il Punteggio sicuro</span><span class="sxs-lookup"><span data-stu-id="3848f-110">How to get to Secure Score</span></span>

<span data-ttu-id="3848f-111">Se l'organizzazione dispone di un abbonamento che include [office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 business](https://docs.microsoft.com/microsoft-365/business/)o Office 365 Business Premium ed è necessario disporre delle [autorizzazioni necessarie](#required-permissions), è possibile visualizzare il Punteggio sicuro dell'organizzazione visitando [https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="3848f-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="3848f-112">In alternativa, è possibile visitare il Centro sicurezza & Compliance[https://protection.office.com](https://protection.office.com)(), in cui si trova un widget Punteggio sicuro che fornisce il punteggio corrente.</span><span class="sxs-lookup"><span data-stu-id="3848f-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![Widget Punteggio sicuro](media/SecureScoreWidget-o365.png)

<span data-ttu-id="3848f-114">Il widget include un collegamento al dashboard di Punteggio sicuro.</span><span class="sxs-lookup"><span data-stu-id="3848f-114">The widget includes a link to your Secure Score dashboard.</span></span>

![Dashboard di Secure Score](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="3848f-116">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="3848f-116">How it works</span></span>

<span data-ttu-id="3848f-117">Il Punteggio sicuro determina quali servizi di Office 365 si sta utilizzando (ad esempio, OneDrive, SharePoint e Exchange), quindi confronta le impostazioni e le attività con una linea di base stabilita da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3848f-117">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft.</span></span> <span data-ttu-id="3848f-118">Si otterrà un punteggio basato sul modo in cui l'organizzazione è allineata con le procedure consigliate per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3848f-118">You'll get a score based on how well aligned your organization is with security best practices.</span></span> <span data-ttu-id="3848f-119">Sono inoltre disponibili suggerimenti sui passaggi che è possibile eseguire per migliorare il punteggio dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3848f-119">You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![Coda delle azioni nello strumento Office 365 Secure Score](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="3848f-121">Il Punteggio sicuro calcola il punteggio in base ai servizi acquistati.</span><span class="sxs-lookup"><span data-stu-id="3848f-121">Secure Score calculates your score based on the services you purchased.</span></span> <span data-ttu-id="3848f-122">Ad esempio, se è stato acquistato solo un piano di Exchange Online, non verranno segnate le caratteristiche di sicurezza di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3848f-122">For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features.</span></span> <span data-ttu-id="3848f-123">Il denominatore del punteggio è la somma di tutte le linee di base per i controlli che si applicano ai prodotti acquistati.</span><span class="sxs-lookup"><span data-stu-id="3848f-123">The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased.</span></span> <span data-ttu-id="3848f-124">Il numeratore è la somma di tutti i controlli per cui sono state completate o parzialmente completate le azioni da eseguire per il controllo.</span><span class="sxs-lookup"><span data-stu-id="3848f-124">The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="3848f-125">Espandi un'azione per conoscere i passaggi da eseguire, le minacce che ti aiuteranno a proteggere e il numero di punti che il tuo punteggio aumenterà dopo aver seguito il suggerimento.</span><span class="sxs-lookup"><span data-stu-id="3848f-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![Azione espansa nello strumento Office 365 Secure Score](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="3848f-127">Per visualizzare l'impatto delle azioni sulla sicurezza dell'organizzazione, selezionare la scheda **analizzaTore Punteggio** e esaminare la cronologia.</span><span class="sxs-lookup"><span data-stu-id="3848f-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![Scheda analizzatore Punteggio dello strumento Office 365 Secure Score](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="3848f-129">Al di sotto del grafico, verrà visualizzato un elenco di punteggi e azioni per categoria.</span><span class="sxs-lookup"><span data-stu-id="3848f-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![Grafico nella scheda analizzatore punteggio che mostra un punto dati selezionato](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="3848f-131">Le azioni contrassegnate come **[non segnate]** sono quelle che è possibile eseguire per l'organizzazione, ma poiché non sono connesse al Punteggio sicuro, non vengono segnate.</span><span class="sxs-lookup"><span data-stu-id="3848f-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="3848f-132">Nella pagina **analizzaTore partitura** fare clic su un punto dati per un giorno specifico, quindi scorrere verso il basso per visualizzare le azioni completate e incomplete per quel giorno per scoprire cosa è cambiato.</span><span class="sxs-lookup"><span data-stu-id="3848f-132">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed.</span></span> <span data-ttu-id="3848f-133">Il Punteggio viene calcolato una volta al giorno (circa 1:00 AM PST).</span><span class="sxs-lookup"><span data-stu-id="3848f-133">The score is calculated once per day (around 1:00 AM PST).</span></span> <span data-ttu-id="3848f-134">Se si apportano modifiche a un'azione misurata, il punteggio verrà aggiornato automaticamente il giorno successivo.</span><span class="sxs-lookup"><span data-stu-id="3848f-134">If you make a change to a measured action, the score will automatically update the next day.</span></span> <span data-ttu-id="3848f-135">Le modifiche apportate alla partitura richiedono fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="3848f-135">It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="3848f-136">Il Punteggio sicuro non esprime una misura assoluta della probabilità di essere violati.</span><span class="sxs-lookup"><span data-stu-id="3848f-136">Secure Score does not express an absolute measure of how likely you are to get breached.</span></span> <span data-ttu-id="3848f-137">Esprime la misura in cui sono state adottate caratteristiche che possono compensare il rischio di essere violate.</span><span class="sxs-lookup"><span data-stu-id="3848f-137">It expresses the extent to which you have adopted features that can offset the risk of being breached.</span></span> <span data-ttu-id="3848f-138">Nessun servizio può garantire che l'utente non verrà violato e che il Punteggio sicuro non debba essere interpretato come garanzia in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="3848f-138">No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="3848f-139">Come aiuta il Punteggio sicuro</span><span class="sxs-lookup"><span data-stu-id="3848f-139">How Secure Score helps</span></span>

<span data-ttu-id="3848f-140">Con il Punteggio sicuro, è possibile migliorare la posizione di sicurezza dell'organizzazione utilizzando le funzionalità di sicurezza predefinite di Office 365 (molte delle quali sono già state acquistate ma potrebbero non essere a conoscenza di).</span><span class="sxs-lookup"><span data-stu-id="3848f-140">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of).</span></span> <span data-ttu-id="3848f-141">Per saperne di più su queste funzionalità, è possibile garantire la tranquillità che si sta prendendo la procedura giusta per proteggere l'organizzazione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="3848f-141">Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="3848f-142">Ma non basta prendere la parola.</span><span class="sxs-lookup"><span data-stu-id="3848f-142">But don't just take our word for it.</span></span> <span data-ttu-id="3848f-143">I clienti che utilizzano il Punteggio sicuro hanno visto il loro punteggio aumentare cinque volte di più rispetto ai clienti che non lo utilizzano.</span><span class="sxs-lookup"><span data-stu-id="3848f-143">Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it.</span></span> <span data-ttu-id="3848f-144">L'aumento del punteggio corrisponde alle caratteristiche di sicurezza utilizzate nelle rispettive organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3848f-144">(The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="3848f-145">Il Punteggio sicuro non esprime una misura assoluta della probabilità di essere violati.</span><span class="sxs-lookup"><span data-stu-id="3848f-145">Secure Score does not express an absolute measure of how likely you are to get breached.</span></span> <span data-ttu-id="3848f-146">Esprime la misura in cui sono stati adottati controlli che possono compensare il rischio di essere violati.</span><span class="sxs-lookup"><span data-stu-id="3848f-146">It expresses the extent to which you have adopted controls which can offset the risk of being breached.</span></span> <span data-ttu-id="3848f-147">Nessun servizio può garantire che l'utente non verrà violato e che il Punteggio sicuro non debba essere interpretato come garanzia in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="3848f-147">No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="3848f-148">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="3848f-148">Required permissions</span></span>

<span data-ttu-id="3848f-149">Per visualizzare e utilizzare il dashboard di Punteggio sicuro, è necessario essere assegnati a uno dei ruoli seguenti in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles):</span><span class="sxs-lookup"><span data-stu-id="3848f-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles):</span></span>
- <span data-ttu-id="3848f-150">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="3848f-150">Global Administrator</span></span>
- <span data-ttu-id="3848f-151">Amministratore fatturazione</span><span class="sxs-lookup"><span data-stu-id="3848f-151">Billing Administrator</span></span>
- <span data-ttu-id="3848f-152">Amministratore utente</span><span class="sxs-lookup"><span data-stu-id="3848f-152">User Administrator</span></span>
- <span data-ttu-id="3848f-153">Amministratore password</span><span class="sxs-lookup"><span data-stu-id="3848f-153">Password Administrator</span></span>
- <span data-ttu-id="3848f-154">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="3848f-154">Security Administrator</span></span>
- <span data-ttu-id="3848f-155">Lettore di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3848f-155">Security Reader</span></span>
- <span data-ttu-id="3848f-156">Amministratore di Exchange</span><span class="sxs-lookup"><span data-stu-id="3848f-156">Exchange Administrator</span></span>
- <span data-ttu-id="3848f-157">Amministratore di SharePoint</span><span class="sxs-lookup"><span data-stu-id="3848f-157">SharePoint Administrator</span></span>

 <span data-ttu-id="3848f-158">Gli utenti a cui non è assegnato un ruolo di amministratore non saranno in grado di accedere al Punteggio sicuro.</span><span class="sxs-lookup"><span data-stu-id="3848f-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3848f-159">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3848f-159">Related topics</span></span>

[<span data-ttu-id="3848f-160">Panoramica del dashboard di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3848f-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="3848f-161">Qual è l’abbonamento corrente?</span><span class="sxs-lookup"><span data-stu-id="3848f-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
