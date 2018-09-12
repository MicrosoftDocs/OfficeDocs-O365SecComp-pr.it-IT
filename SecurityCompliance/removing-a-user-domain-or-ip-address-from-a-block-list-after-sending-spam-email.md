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
ms.openlocfilehash: 8dcd6c8f55d867e1c2e249ec71a3a5c6b78ac76a
ms.sourcegitcommit: d89c24258123a3ffde574a391d59afd3aea8470d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "23955438"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="107d5-103">Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="107d5-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="107d5-p101">Se un utente in modo continuo invia messaggi di posta elettronica da Office 365 classificata come posta indesiderata, essi verranno bloccate di inviare messaggi più. L'utente verrà elencato nel servizio come mittente in uscita non valido e verrà visualizzato un rapporto di mancato recapito (NDR o non è riuscito a Invia messaggio di posta elettronica) che fornisce informazioni specifiche sulle operazioni che devono eseguire per sbloccare se stessi.</span><span class="sxs-lookup"><span data-stu-id="107d5-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>

<span data-ttu-id="107d5-p102">È possibile configurare le impostazioni di criteri di posta indesiderata in uscita in modo che si riceve una notifica quando un utente di Office 365 impedito l'invio di posta elettronica. Dopo aver risolto il problema con la cassetta postale dell'utente, è possibile rimuovere il blocco di tale mittente.</span><span class="sxs-lookup"><span data-stu-id="107d5-p102">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="107d5-108">Sbloccare un account di posta elettronica di Office 365</span><span class="sxs-lookup"><span data-stu-id="107d5-108">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="107d5-p103">Completare questa attività nel centro conformità (SCC) protezione di Office 365. Per ulteriori informazioni su controllo del codice sorgente, [passare alla sicurezza di Office 365 centro conformità](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="107d5-p103">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="107d5-111">Utilizzo di un ufficio o della scuola dell'account che disponga di privilegi di amministratore globale di Office 365, accedere a Centro connessioni di Office 365 sicurezza e conformità e nell'elenco a sinistra espandere **Threat Management**, scegliere **Rivedi**e quindi fare clic su **con restrizioni Gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="107d5-111">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="107d5-112">Per passare direttamente alla pagina **Utenti con restrizioni** per la protezione &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="107d5-112">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="107d5-p104">In questa pagina sarà incluse nell'elenco di utenti che sono stati bloccati di inviare posta elettronica esterni all'organizzazione.  Trovare l'utente che si desidera rimuovere restrizioni e quindi fare clic su **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="107d5-p104">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="107d5-115">Fare clic su **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="107d5-115">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="107d5-p105">Non vi è un limite al numero di volte in cui è possibile sbloccare un account per l'amministrazione tenant. Se è stato superato il limite per un utente, viene visualizzato un messaggio di errore. È quindi necessario contattare il supporto per sbloccare l'utente.</span><span class="sxs-lookup"><span data-stu-id="107d5-p105">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="107d5-118">Elenchi di blocco di terze parti</span><span class="sxs-lookup"><span data-stu-id="107d5-118">Third-party block lists</span></span>

<span data-ttu-id="107d5-p106">Exchange Online Protection utilizza anche gli elenchi di blocco di terze parti per prendere decisioni nel filtro posta indesiderata. Gli utenti, siti, domini e gli indirizzi IP possono aggiunti da bloccare elenchi solo per la visualizzazione in un messaggio di posta indesiderata. Come amministratore di Office 365, è consigliabile ottenere questi oggetti rimossi i provider dell'elenco di terze parti se appartengono a un utente. Utilizzare i collegamenti nel sotto la tabella per contattare ogni terze parti e quindi seguire le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="107d5-p106">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you. Use the links in the below table to contact each third party and then follow their instructions.</span></span>

|<span data-ttu-id="107d5-123">\*\*Nome dell'elenco \*\*</span><span class="sxs-lookup"><span data-stu-id="107d5-123">**List Name**</span></span>|<span data-ttu-id="107d5-124">**Portale per la rimozione dall'elenco**</span><span class="sxs-lookup"><span data-stu-id="107d5-124">**Delisting Portal**</span></span>|<span data-ttu-id="107d5-125">**Ulteriori informazioni**</span><span class="sxs-lookup"><span data-stu-id="107d5-125">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="107d5-126">URIBL</span><span class="sxs-lookup"><span data-stu-id="107d5-126">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="107d5-127">Sito Web URIBL</span><span class="sxs-lookup"><span data-stu-id="107d5-127">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="107d5-128">SURBL</span><span class="sxs-lookup"><span data-stu-id="107d5-128">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="107d5-129">Presentazione di dati di reputazione di URI SURBL</span><span class="sxs-lookup"><span data-stu-id="107d5-129">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="107d5-130">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="107d5-130">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="107d5-131">Informazioni sui filtri di DNSBLHTTP://</span><span class="sxs-lookup"><span data-stu-id="107d5-131">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="107d5-132">invaluement</span><span class="sxs-lookup"><span data-stu-id="107d5-132">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="107d5-133">elenco di anti elenco di protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="107d5-133">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="107d5-134">Phishtank</span><span class="sxs-lookup"><span data-stu-id="107d5-134">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="107d5-135">PhishTank domande frequenti</span><span class="sxs-lookup"><span data-stu-id="107d5-135">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |

> [!NOTE]
> <span data-ttu-id="107d5-p107">Se qualcuno all'esterno di Office 365 non può inviare messaggi al proprio account di Office 365, potrebbe essere il proprio account nell'elenco Mittenti bloccati esterni. Gli utenti all'esterno di Office 365 è possono provare a rimuovere se stessi mediante il [portale self-service di rimozione](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span><span class="sxs-lookup"><span data-stu-id="107d5-p107">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="107d5-138">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="107d5-138">For more information</span></span>

[<span data-ttu-id="107d5-139">Rispondere a un account di posta elettronica compromesso</span><span class="sxs-lookup"><span data-stu-id="107d5-139">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="107d5-140">Configurazione del criterio delle posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="107d5-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="107d5-141">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="107d5-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

