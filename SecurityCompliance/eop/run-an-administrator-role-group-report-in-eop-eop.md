---
title: 'Eseguire il rapporto del gruppo di ruoli amministratore in EOP '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Quando un amministratore aggiunge membri o rimuove membri dai gruppi di ruoli amministratore, Microsoft Exchange Online Protection (EOP) registra ogni occorrenza.
ms.openlocfilehash: 49311faa4ee54fafa1c05a2314ed2f9d74cbe5a5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027203"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="58196-103">Eseguire il rapporto del gruppo di ruoli amministratore in EOP</span><span class="sxs-lookup"><span data-stu-id="58196-103">Run an administrator role group report in EOP</span></span> 

 <span data-ttu-id="58196-p101">Quando un amministratore aggiunge membri o rimuove membri dai gruppi di ruoli amministratore, Microsoft Exchange Online Protection (EOP) registra ogni occorrenza. Quando si esegue un rapporto del gruppo di ruoli amministratore nell'interfaccia di amministrazione di Exchange, le voci vengono visualizzate come risultati di ricerca e includono i gruppi di ruolo interessati, chi ha modificato l'appartenenza al gruppo di ruoli e quando e quali aggiornamenti dell'appartenenza sono stati effettuati. Utilizzare questo rapporto per monitorare le modifiche apportate alle autorizzazioni amministrative assegnate agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58196-p101">When an administrator adds members to or removes members from administrator role groups, Microsoft Exchange Online Protection (EOP) logs each occurrence. When you run an administrator role group report in the Exchange admin center, entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made. Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="58196-107">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="58196-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="58196-108">Tempo stimato per il completamento: 2 minuti</span><span class="sxs-lookup"><span data-stu-id="58196-108">Estimated time to complete: 2 minutes</span></span>
    
- <span data-ttu-id="58196-p102">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Rapporti" dell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="58196-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="58196-111">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="58196-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="58196-p103">Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="58196-p103">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="58196-115">Esecuzione del report del gruppo di ruoli amministratore tramite EAC</span><span class="sxs-lookup"><span data-stu-id="58196-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="58196-116">Eseguire il rapporto di un gruppo di ruoli amministratore per trovare le modifiche ai gruppi di ruoli di gestione nell'organizzazione in uno specifico intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="58196-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular timeframe.</span></span>
  
1. <span data-ttu-id="58196-117">Nell'interfaccia di amministrazione di Exchange selezionare **Gestione della conformità** \> **Controllo**, quindi fare clic su **Esegui il rapporto di un gruppo di ruoli amministratore**.</span><span class="sxs-lookup"><span data-stu-id="58196-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>
    
2. <span data-ttu-id="58196-p104">Scegliere **Data di inizio** e **Data di fine**. Per impostazione predefinita, il rapporto cerca le modifiche apportate ai gruppi di ruoli amministratore nelle ultime due settimane.</span><span class="sxs-lookup"><span data-stu-id="58196-p104">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>
    
3. <span data-ttu-id="58196-p105">Per visualizzare le modifiche per un gruppo di ruoli specifico, fare clic su **Seleziona gruppi di ruoli**. Selezionare il gruppo o i gruppi di ruoli nella finestra di dialogo successiva, quindi fare clic su **OK**. È inoltre possibile lasciare il campo vuoto per trovare tutti i gruppi di ruolo modificati.</span><span class="sxs-lookup"><span data-stu-id="58196-p105">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>
    
4. <span data-ttu-id="58196-123">Fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="58196-123">Click **Search**.</span></span>
    
<span data-ttu-id="58196-p106">Se utilizzando i criteri specificati vengono trovate delle modifiche, queste verranno visualizzate nel riquadro dei risultati. Fare clic su un gruppo di ruoli nei risultati della ricerca per visualizzare le modifiche nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="58196-p106">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="58196-126">Come verificare se l'operazione ha avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="58196-126">How do you know this worked?</span></span>

<span data-ttu-id="58196-p107">Se è stato eseguito correttamente un report dei gruppi di ruoli di amministratore, i gruppi di ruoli modificati entro l'intervallo di date vengono visualizzati nel riquadro dei risultati della ricerca. Se non è presente alcun risultato, non è stata eseguita alcuna modifica entro l'intervallo di date specificato. Se è prevista la presenza di risultati, modificare l'intervallo di date, quindi eseguire di nuovo il report.</span><span class="sxs-lookup"><span data-stu-id="58196-p107">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>
  
## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="58196-130">Monitorare le modifiche apportate all'appartenenza ai gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="58196-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="58196-p108">Quando si aggiungono o si rimuovono i membri di un gruppo di ruoli, nei risultati di ricerca visualizzati nel riquadro dei dettagli viene indicato che l'appartenenza al gruppo di ruoli è stata aggiornata e vengono elencati i membri correnti. I risultati non dichiarano in modo esplicito quale utente è stato aggiunto o rimosso.</span><span class="sxs-lookup"><span data-stu-id="58196-p108">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>
  
<span data-ttu-id="58196-p109">Per determinare se un utente è stato aggiunto o rimosso, è necessario confrontare due voci separate del rapporto. Ad esempio, osservare le voci di registro seguenti per il gruppo di ruoli **HelpDesk**:</span><span class="sxs-lookup"><span data-stu-id="58196-p109">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span> 
  
 <span data-ttu-id="58196-135">**27.01.13 16:43:00**</span><span class="sxs-lookup"><span data-stu-id="58196-135">**1/27/2013 4:43 PM**</span></span>
  
 <span data-ttu-id="58196-136">**Amministratore**</span><span class="sxs-lookup"><span data-stu-id="58196-136">**Administrator**</span></span>
  
 <span data-ttu-id="58196-137">**Membri aggiornati: Administrator;annb,florencef;pilarp**</span><span class="sxs-lookup"><span data-stu-id="58196-137">**Updated members: Administrator;annb,florencef;pilarp**</span></span>
  
 <span data-ttu-id="58196-138">**06.02.13 10:09:00**</span><span class="sxs-lookup"><span data-stu-id="58196-138">**2/06/2013 10:09 AM**</span></span>
  
 <span data-ttu-id="58196-139">**Amministratore**</span><span class="sxs-lookup"><span data-stu-id="58196-139">**Administrator**</span></span>
  
 <span data-ttu-id="58196-140">**Membri aggiornati: Administrator;annb;florencef;pilarp;tonip**</span><span class="sxs-lookup"><span data-stu-id="58196-140">**Updated members: Administrator;annb;florencef;pilarp;tonip**</span></span>
  
 <span data-ttu-id="58196-141">**19.02.13 14.12**</span><span class="sxs-lookup"><span data-stu-id="58196-141">**2/19/2013 2:12 PM**</span></span>
  
 <span data-ttu-id="58196-142">**Amministratore**</span><span class="sxs-lookup"><span data-stu-id="58196-142">**Administrator**</span></span>
  
 <span data-ttu-id="58196-143">**Membri aggiornati: Administrator;annb;florencef;tonip**</span><span class="sxs-lookup"><span data-stu-id="58196-143">**Updated members: Administrator;annb;florencef;tonip**</span></span>
  
<span data-ttu-id="58196-144">In questo esempio, l'account utente Amministratore ha apportato le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="58196-144">In this example, the Administrator user account made the following changes:</span></span>
  
- <span data-ttu-id="58196-145">Il 06.02.13 è stato aggiunto l'utente michaela.</span><span class="sxs-lookup"><span data-stu-id="58196-145">On 2/06/2013, it added the user tonip.</span></span>
    
- <span data-ttu-id="58196-146">Il 19.02.13 è stato rimosso l'utente adrianag.</span><span class="sxs-lookup"><span data-stu-id="58196-146">On 2/19/2013, it removed the user pilarp.</span></span>
    

