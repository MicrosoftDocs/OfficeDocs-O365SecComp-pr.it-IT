---
title: Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/01/2018
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
ms.collection:
- M365-security-compliance
description: "Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato. "
ms.openlocfilehash: 870e5eabca9e799dfca1e99846a5bfe845f65df4
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275936"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="5fee9-103">Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="5fee9-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="5fee9-p101">Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, verranno bloccati dall'invio di altri messaggi. L'utente verrà elencato nel servizio come mittente in uscita non valido e riceverà un rapporto di mancato reCapito (NDR) che dichiara:</span><span class="sxs-lookup"><span data-stu-id="5fee9-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="5fee9-p102">Non è stato possibile recapitare il messaggio perché non sono stati riconosciuti come mittenti validi. Il motivo più comune è che l'indirizzo di posta elettronica è sospettato di inviare posta indesiderata e non è più consentito l'invio di messaggi all'esterno dell'organizzazione. Contattare l'amministratore della posta elettronica per ricevere assistenza.  Il server remoto ha restituito ' 550 5.1.8 Access Denied, Bad Outbound sender '</span><span class="sxs-lookup"><span data-stu-id="5fee9-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="5fee9-110">Gli amministratori del tenant riceveranno anche un avviso che indica che l'utente è stato impedito di inviare altri messaggi in uscita.</span><span class="sxs-lookup"><span data-stu-id="5fee9-110">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5fee9-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5fee9-111">What do you need to know before you begin?</span></span>
<span data-ttu-id="5fee9-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="5fee9-112"></span></span>

<span data-ttu-id="5fee9-113">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="5fee9-113">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="5fee9-p103">Prima di poter eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate. Per sapere quali autorizzazioni sono necessarie, vedere "voce di protezione da posta indesiderata nell'argomento [autorizzazioni funzionalità in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5fee9-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="5fee9-p104">La procedura seguente può essere eseguita anche tramite Remote PowerShell. Utilizzare il cmdlet Get-BlockedSenderAddress per ottenere l'elenco di utenti con restrizioni e Remove-BlockedSenderAddress per rimuovere la restrizione. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="5fee9-p104">The following procedure can also be performed via remote PowerShell. Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="5fee9-119">Rimuovere le restrizioni relative a un account di posta elettronica di Office 365 bloccato</span><span class="sxs-lookup"><span data-stu-id="5fee9-119">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="5fee9-p105">Questa attività viene completata nel centro sicurezza & Compliance (SCC) di Office 365. Per ulteriori informazioni su SCC, [passare al centro conformità di Office 365 Security &](go-to-the-securitycompliance-center.md) . Per poter eseguire queste funzioni, è necessario essere nel gruppo di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per ulteriori informazioni sui gruppi di ruoli SCC, [accedere a autorizzazioni nel centro conformità di Office 365 Security &](permissions-in-the-security-and-compliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="5fee9-p105">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC. You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions. [Go to Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="5fee9-124">Utilizzando un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale di Office 365, accedere al centro sicurezza e conformità di Office 365 e, nell'elenco a sinistra, espandere **gestione minacce**, scegliere **Revisione**e quindi fare clic su **limitato. Gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="5fee9-124">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5fee9-125">Per passare direttamente alla pagina **utenti con restrizioni** (in precedenza nota come centro operazioni) nel centro sicurezza &amp; e conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="5fee9-125">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="5fee9-p106">Questa pagina contiene l'elenco di utenti bloccati dall'invio di posta all'esterno dell'organizzazione.  Individuare l'utente per il quale si desidera rimuovere le restrizioni e quindi fare clic su **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="5fee9-p106">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="5fee9-128">Fare clic su **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="5fee9-128">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5fee9-p107">Esiste un limite al numero di volte in cui un account può essere sbloccato dall'amministratore del tenant. Se il limite per un utente è stato superato, verrà visualizzato un messaggio di errore. Sarà quindi necessario contattare il supporto per sbloccare l'utente.</span><span class="sxs-lookup"><span data-stu-id="5fee9-p107">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span><br/><br/> <span data-ttu-id="5fee9-131">Potrebbe essere necessario fino a un'ora prima che l'utente venga sbloccato.</span><span class="sxs-lookup"><span data-stu-id="5fee9-131">It may take up to 1 hour before the user is unblocked.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="5fee9-132">Elenchi di blocco di terze parti</span><span class="sxs-lookup"><span data-stu-id="5fee9-132">Third-party block lists</span></span>

<span data-ttu-id="5fee9-p108">Exchange Online Protection utilizza anche elenchi di blocco di terze parti per contribuire a prendere decisioni nel filtraggio della posta indesiderata. Gli utenti, i siti Web, i domini e gli indirizzi IP possono essere aggiunti agli elenchi di blocco solo per la visualizzazione in un messaggio di posta indesiderata. Come amministratore di Office 365, è consigliabile provare a rimuovere questi oggetti dai provider di elenchi di terze parti se appartengono all'utente.</span><span class="sxs-lookup"><span data-stu-id="5fee9-p108">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you.</span></span>

> [!NOTE]
> <span data-ttu-id="5fee9-p109">Se un utente esterno a Office 365 non è in grado di inviare messaggi all'account di Office 365, è possibile che l'account sia presente nell'elenco Mittenti bloccati esterni. Gli utenti esterni a Office 365 possono provare a rimuoversi usando il portale di delisting [self-service](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span><span class="sxs-lookup"><span data-stu-id="5fee9-p109">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="5fee9-138">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="5fee9-138">For more information</span></span>

[<span data-ttu-id="5fee9-139">Risposta a un account di posta elettronica compromesso</span><span class="sxs-lookup"><span data-stu-id="5fee9-139">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="5fee9-140">Configurare i criteri della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="5fee9-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="5fee9-141">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="5fee9-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="5fee9-142">Autorizzazioni nel centro conformità & sicurezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="5fee9-142">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

  

