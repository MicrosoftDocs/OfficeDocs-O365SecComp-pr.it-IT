---
title: Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: "Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato. "
ms.openlocfilehash: ff5bb010f45b0c89e08239f0e37885bd7ae5c7cd
ms.sourcegitcommit: 234a22c61859133ed5e7988a9551a569781518a4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23875788"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="892d5-103">Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="892d5-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="892d5-104">Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato. </span><span class="sxs-lookup"><span data-stu-id="892d5-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="892d5-105">
Quando a un mittente viene impedito di inviare messaggi di posta elettronica, tale mittente riceve un rapporto di mancato recapito (NDR o impossibilità a inviare il messaggio) che fornisce informazioni specifiche sulla procedura da seguire per sbloccarsi.</span><span class="sxs-lookup"><span data-stu-id="892d5-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="892d5-p101">Non solo ai domini di servizio, ma i siti Web specifici, possono essere bloccati singoli utenti e gli indirizzi IP possono inoltre essere bloccati. In alcuni casi, domini o siti Web possono essere aggiunti a un elenco di blocco il fatto che vengono visualizzati in un messaggio di posta indesiderata. Come amministratore di Office 365, è possibile provare a ottenere gli utenti, siti, domini e gli indirizzi IP rimossi dagli elenchi di blocco di terze parti. Utilizzare i collegamenti della tabella nella parte inferiore di questo argomento per contattare ogni terze parti e quindi seguire le istruzioni. Se qualcuno all'esterno di Office 365 non può inviare messaggi al proprio account di Office 365, il proprio account potrebbe avere è terminato nell'elenco Mittenti bloccati esterno. Gli utenti all'esterno di Office 365 possono provare a se stessi rimuovere dall'elenco dei mittenti bloccati tramite il [portale self-service di rimozione](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="892d5-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="892d5-p102">È possibile configurare le impostazioni di posta indesiderata in uscita in modo da ricevere una notifica quando a un utente di Office 365 viene impedito di inviare messaggi di posta elettronica classificati come posta indesiderata. Dopo aver risolto il problema relativo alla cassetta postale dell'utente, è possibile rimuovere il blocco di tale mittente.</span><span class="sxs-lookup"><span data-stu-id="892d5-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="892d5-114">Sbloccare un account di posta elettronica di Office 365</span><span class="sxs-lookup"><span data-stu-id="892d5-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="892d5-p103">Completare questa attività nel centro conformità (SCC) protezione di Office 365. Per ulteriori informazioni su controllo del codice sorgente, [passare alla sicurezza di Office 365 centro conformità](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="892d5-p103">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="892d5-117">Utilizzo di un ufficio o della scuola dell'account che disponga di privilegi di amministratore globale di Office 365, accedere a Centro connessioni di Office 365 sicurezza e conformità e nell'elenco a sinistra espandere **Threat Management**, scegliere **Rivedi**e quindi fare clic su **con restrizioni Gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="892d5-117">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="892d5-118">Per passare direttamente alla pagina **Utenti con restrizioni** per la protezione &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="892d5-118">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="892d5-p104">In questa pagina sarà incluse nell'elenco di utenti che sono stati bloccati di inviare posta elettronica esterni all'organizzazione.  Trovare l'utente che si desidera rimuovere restrizioni e quindi fare clic su **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="892d5-p104">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="892d5-121">Fare clic su **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="892d5-121">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="892d5-p105">Non vi è un limite al numero di volte in cui è possibile sbloccare un account per l'amministrazione tenant. Se è stato superato il limite per un utente, viene visualizzato un messaggio di errore. È quindi necessario contattare il supporto per sbloccare l'utente.</span><span class="sxs-lookup"><span data-stu-id="892d5-p105">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="892d5-124">Elenchi di blocco di terze parti</span><span class="sxs-lookup"><span data-stu-id="892d5-124">Third-party block lists</span></span>

|<span data-ttu-id="892d5-125">\*\*Nome dell'elenco \*\*</span><span class="sxs-lookup"><span data-stu-id="892d5-125">**List Name**</span></span>|<span data-ttu-id="892d5-126">**Portale per la rimozione dall'elenco**</span><span class="sxs-lookup"><span data-stu-id="892d5-126">**Delisting Portal**</span></span>|<span data-ttu-id="892d5-127">**Ulteriori informazioni**</span><span class="sxs-lookup"><span data-stu-id="892d5-127">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="892d5-128">URIBL</span><span class="sxs-lookup"><span data-stu-id="892d5-128">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="892d5-129">Sito Web URIBL</span><span class="sxs-lookup"><span data-stu-id="892d5-129">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="892d5-130">SURBL</span><span class="sxs-lookup"><span data-stu-id="892d5-130">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="892d5-131">Presentazione di dati di reputazione di URI SURBL</span><span class="sxs-lookup"><span data-stu-id="892d5-131">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="892d5-132">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="892d5-132">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="892d5-133">Informazioni sui filtri di DNSBLHTTP://</span><span class="sxs-lookup"><span data-stu-id="892d5-133">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="892d5-134">invaluement</span><span class="sxs-lookup"><span data-stu-id="892d5-134">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="892d5-135">elenco di anti elenco di protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="892d5-135">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="892d5-136">Phishtank</span><span class="sxs-lookup"><span data-stu-id="892d5-136">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="892d5-137">PhishTank domande frequenti</span><span class="sxs-lookup"><span data-stu-id="892d5-137">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="892d5-138">Exchange Online Protection utilizza anche gli elenchi di blocco di terze parti per il filtraggio della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="892d5-138">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="892d5-139">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="892d5-139">For more information</span></span>

[<span data-ttu-id="892d5-140">Configurazione del criterio delle posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="892d5-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="892d5-141">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="892d5-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="892d5-142">Accedere al portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365</span><span class="sxs-lookup"><span data-stu-id="892d5-142">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

