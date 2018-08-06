---
title: Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: "Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato. "
ms.openlocfilehash: ce52ddfd96b582911bb519c15bbfe90351946db8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026333"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="a9917-103">Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a9917-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="a9917-104">Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato. </span><span class="sxs-lookup"><span data-stu-id="a9917-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="a9917-105">
Quando a un mittente viene impedito di inviare messaggi di posta elettronica, tale mittente riceve un rapporto di mancato recapito (NDR o impossibilità a inviare il messaggio) che fornisce informazioni specifiche sulla procedura da seguire per sbloccarsi.</span><span class="sxs-lookup"><span data-stu-id="a9917-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="a9917-p101">Non solo ai domini di servizio, ma i siti Web specifici, possono essere bloccati singoli utenti e gli indirizzi IP possono inoltre essere bloccati. In alcuni casi, domini o siti Web possono essere aggiunti a un elenco di blocco il fatto che vengono visualizzati in un messaggio di posta indesiderata. Come amministratore di Office 365, è possibile provare a ottenere gli utenti, siti, domini e gli indirizzi IP rimossi dagli elenchi di blocco di terze parti. Utilizzare i collegamenti della tabella nella parte inferiore di questo argomento per contattare ogni terze parti e quindi seguire le istruzioni. Se qualcuno all'esterno di Office 365 non può inviare messaggi al proprio account di Office 365, il proprio account potrebbe avere è terminato nell'elenco Mittenti bloccati esterno. Gli utenti all'esterno di Office 365 possono provare a se stessi rimuovere dall'elenco dei mittenti bloccati tramite il [portale self-service di rimozione](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a9917-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="a9917-p102">È possibile configurare le impostazioni di posta indesiderata in uscita in modo da ricevere una notifica quando a un utente di Office 365 viene impedito di inviare messaggi di posta elettronica classificati come posta indesiderata. Dopo aver risolto il problema relativo alla cassetta postale dell'utente, è possibile rimuovere il blocco di tale mittente.</span><span class="sxs-lookup"><span data-stu-id="a9917-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="a9917-114">Sbloccare un account di posta elettronica di Office 365</span><span class="sxs-lookup"><span data-stu-id="a9917-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="a9917-p103">Completare questa attività nell'interfaccia di amministrazione di Exchange (EAC). Vedere [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) per informazioni dettagliate sui EAC.</span><span class="sxs-lookup"><span data-stu-id="a9917-p103">You complete this task in the Exchange admin center (EAC). Check out [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) for details about the EAC.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a9917-117">A meno che non si è all'interno di EAC per Exchange Online, non verrà visualizzato alcun centro notifiche.</span><span class="sxs-lookup"><span data-stu-id="a9917-117">You won't see the action center unless you're in the EAC for Exchange Online.</span></span> 
  
1. <span data-ttu-id="a9917-118">In EAC, accedere a **protezione** \> **Centro**.</span><span class="sxs-lookup"><span data-stu-id="a9917-118">In the EAC, navigate to **protection** \> **action center**.</span></span>
    
    ![Passare al centro notifiche nell'interfaccia di amministrazione di Exchange](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. <span data-ttu-id="a9917-120">Selezionare l'icona **Cerca** e immettere l'indirizzo SMTP dell'utente bloccato.</span><span class="sxs-lookup"><span data-stu-id="a9917-120">Select the **Search** icon, and then enter the SMTP address of the blocked user.</span></span> 
    
    ![Ricerca di un utente bloccato nel centro notifiche](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. <span data-ttu-id="a9917-122">Fare clic su **Sblocca account** nel riquadro Descrizione.</span><span class="sxs-lookup"><span data-stu-id="a9917-122">Click **Unblock Account** in the description pane.</span></span> 
    
    ![Sblocco di un utente nel centro notifiche](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. <span data-ttu-id="a9917-124">Fare clic su **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="a9917-124">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a9917-p104">Esiste un limite per il numero di volte in cui un account può essere sbloccato dall'amministratore del tenant. Se tale limite è stato superato per un utente, viene visualizzato un messaggio di errore. Contattare il supporto per sbloccare l'utente.</span><span class="sxs-lookup"><span data-stu-id="a9917-p104">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. Contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="a9917-127">Elenchi di blocco di terze parti</span><span class="sxs-lookup"><span data-stu-id="a9917-127">Third-party block lists</span></span>

|<span data-ttu-id="a9917-128">**Nome dell'elenco **</span><span class="sxs-lookup"><span data-stu-id="a9917-128">**List Name**</span></span>|<span data-ttu-id="a9917-129">**Portale per la rimozione dall'elenco**</span><span class="sxs-lookup"><span data-stu-id="a9917-129">**Delisting Portal**</span></span>|<span data-ttu-id="a9917-130">**Ulteriori informazioni**</span><span class="sxs-lookup"><span data-stu-id="a9917-130">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a9917-131">URIBL</span><span class="sxs-lookup"><span data-stu-id="a9917-131">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="a9917-132">Sito Web URIBL</span><span class="sxs-lookup"><span data-stu-id="a9917-132"> URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="a9917-133">SURBL</span><span class="sxs-lookup"><span data-stu-id="a9917-133">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="a9917-134">Presentazione di dati di reputazione di URI SURBL</span><span class="sxs-lookup"><span data-stu-id="a9917-134">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="a9917-135">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="a9917-135">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="a9917-136">Informazioni sui filtri di DNSBLHTTP://</span><span class="sxs-lookup"><span data-stu-id="a9917-136">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="a9917-137">invaluement</span><span class="sxs-lookup"><span data-stu-id="a9917-137">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="a9917-138">elenco di anti elenco di protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a9917-138">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="a9917-139">Phishtank</span><span class="sxs-lookup"><span data-stu-id="a9917-139">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="a9917-140">PhishTank domande frequenti</span><span class="sxs-lookup"><span data-stu-id="a9917-140">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="a9917-141">Exchange Online Protection utilizza anche gli elenchi di blocco di terze parti per il filtraggio della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="a9917-141">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="a9917-142">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="a9917-142">For more information</span></span>

[<span data-ttu-id="a9917-143">Configurare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="a9917-143">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="a9917-144">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="a9917-144">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="a9917-145">Accedere al portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365</span><span class="sxs-lookup"><span data-stu-id="a9917-145">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

