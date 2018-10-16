---
title: Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/16/2018
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
ms.openlocfilehash: 295d92fc6a1cd26783b18304a2d119d2ea0d7f1f
ms.sourcegitcommit: b164d4af65709133e0b512a4327a70fae13a974d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "25577065"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="23c42-103">Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="23c42-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="23c42-p101">Se un utente in modo continuo invia messaggi di posta elettronica da Office 365 classificata come posta indesiderata, essi verranno bloccate di inviare messaggi più. L'utente verrà elencato nel servizio come mittente in uscita non valido e verrà visualizzato un mancato recapito rapporto di mancato recapito indicante:</span><span class="sxs-lookup"><span data-stu-id="23c42-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="23c42-p102">Non è stato recapitato il messaggio perché non sono state riconosciute come mittente valido. La causa più comune per l'oggetto è che l'indirizzo di posta elettronica sospetta l'invio di posta indesiderata e non ha non è più consentito inviare messaggi di fuori dell'organizzazione. Per assistenza, contattare l'amministratore di posta elettronica.  Server remoto ha restituito "550 5.1.8 accesso negato, mittente in uscita non valido"</span><span class="sxs-lookup"><span data-stu-id="23c42-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="23c42-p103">È possibile configurare le impostazioni di criteri di posta indesiderata in uscita in modo che si riceve una notifica quando un utente di Office 365 impedito l'invio di posta elettronica. Dopo aver risolto il problema con la cassetta postale dell'utente, è possibile rimuovere il blocco di tale mittente.</span><span class="sxs-lookup"><span data-stu-id="23c42-p103">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="23c42-112">Sbloccare un account di posta elettronica di Office 365</span><span class="sxs-lookup"><span data-stu-id="23c42-112">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="23c42-p104">Completare questa attività nel centro conformità (SCC) protezione di Office 365. Per ulteriori informazioni su controllo del codice sorgente, [passare alla sicurezza di Office 365 centro conformità](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="23c42-p104">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="23c42-115">Utilizzo di un ufficio o della scuola dell'account che disponga di privilegi di amministratore globale di Office 365, accedere a Centro connessioni di Office 365 sicurezza e conformità e nell'elenco a sinistra espandere **Threat Management**, scegliere **Rivedi**e quindi fare clic su **con restrizioni Gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="23c42-115">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="23c42-116">Per passare direttamente alla pagina **Utenti con restrizioni** (precedentemente nota come centro) la sicurezza &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="23c42-116">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="23c42-p105">In questa pagina sarà incluse nell'elenco di utenti che sono stati bloccati di inviare posta elettronica esterni all'organizzazione.  Trovare l'utente che si desidera rimuovere restrizioni e quindi fare clic su **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="23c42-p105">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="23c42-119">Fare clic su **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="23c42-119">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="23c42-p106">Non vi è un limite al numero di volte in cui è possibile sbloccare un account per l'amministrazione tenant. Se è stato superato il limite per un utente, viene visualizzato un messaggio di errore. È quindi necessario contattare il supporto per sbloccare l'utente.</span><span class="sxs-lookup"><span data-stu-id="23c42-p106">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="23c42-122">Elenchi di blocco di terze parti</span><span class="sxs-lookup"><span data-stu-id="23c42-122">Third-party block lists</span></span>

<span data-ttu-id="23c42-p107">Exchange Online Protection utilizza anche gli elenchi di blocco di terze parti per prendere decisioni nel filtro posta indesiderata. Gli utenti, siti, domini e gli indirizzi IP possono aggiunti da bloccare elenchi solo per la visualizzazione in un messaggio di posta indesiderata. Come amministratore di Office 365, è consigliabile ottenere questi oggetti rimossi i provider dell'elenco di terze parti se appartengono a un utente.</span><span class="sxs-lookup"><span data-stu-id="23c42-p107">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you.</span></span>

> [!NOTE]
> <span data-ttu-id="23c42-p108">Se qualcuno all'esterno di Office 365 non può inviare messaggi al proprio account di Office 365, potrebbe essere il proprio account nell'elenco Mittenti bloccati esterni. Gli utenti all'esterno di Office 365 è possono provare a rimuovere se stessi mediante il [portale self-service di rimozione](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span><span class="sxs-lookup"><span data-stu-id="23c42-p108">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="23c42-128">Per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="23c42-128">For more information</span></span>

[<span data-ttu-id="23c42-129">Rispondere a un account di posta elettronica compromesso</span><span class="sxs-lookup"><span data-stu-id="23c42-129">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="23c42-130">Configurare i criteri della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="23c42-130">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="23c42-131">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="23c42-131">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

