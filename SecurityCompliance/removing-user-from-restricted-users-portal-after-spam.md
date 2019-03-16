---
title: Rimozione di un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Se un utente invia continuamente messaggi di posta elettronica provenienti da Office 365 classificati come posta indesiderata, non invierà più messaggi.
ms.openlocfilehash: 61d52ad1f25dc3767ad51da5b3a217ace59303ce
ms.sourcegitcommit: 9918411c01e962d5c67d53dd30a8a9c28c547397
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "30654553"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="489a1-103">Rimozione di un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="489a1-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="489a1-104">Se un utente invia continuamente messaggi di posta elettronica provenienti da Office 365 classificati come posta indesiderata, non invierà più messaggi in uscita.</span><span class="sxs-lookup"><span data-stu-id="489a1-104">If a user continuously sends emails from Office 365 that are classified as spam, they will be restricted from sending any more messages outbound.</span></span> <span data-ttu-id="489a1-105">L'utente verrà elencato nel servizio come mittente in uscita non valido e riceverà un rapporto di mancato reCapito (NDR) che dichiara:</span><span class="sxs-lookup"><span data-stu-id="489a1-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="489a1-106">Non è stato possibile recapitare il messaggio perché non sono stati riconosciuti come mittenti validi.</span><span class="sxs-lookup"><span data-stu-id="489a1-106">Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="489a1-107">Il motivo più comune è che l'indirizzo di posta elettronica è sospettato di inviare posta indesiderata e non è più consentito l'invio di messaggi all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="489a1-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization.</span></span> <span data-ttu-id="489a1-108">Contattare l'amministratore della posta elettronica per ricevere assistenza.</span><span class="sxs-lookup"><span data-stu-id="489a1-108">Contact your email admin for assistance.</span></span> <span data-ttu-id="489a1-109">Il server remoto ha restituito ' 550 5.1.8 Access Denied, Bad Outbound sender '</span><span class="sxs-lookup"><span data-stu-id="489a1-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="489a1-110">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="489a1-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="489a1-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="489a1-111"></span></span>

<span data-ttu-id="489a1-112">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="489a1-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="489a1-113">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="489a1-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="489a1-114">Per sapere quali autorizzazioni sono necessarie, vedere "voce di protezione da posta indesiderata nell'argomento [autorizzazioni funzionalità in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="489a1-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="489a1-115">La seguente procedura può essere eseguita anche tramite PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="489a1-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="489a1-116">Utilizzare il cmdlet Get-BlockedSenderAddress per ottenere l'elenco di utenti con restrizioni e Remove-BlockedSenderAddress per rimuovere la restrizione.</span><span class="sxs-lookup"><span data-stu-id="489a1-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="489a1-117">Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="489a1-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="489a1-118">Rimuovere le restrizioni relative a un account di posta elettronica di Office 365 bloccato</span><span class="sxs-lookup"><span data-stu-id="489a1-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="489a1-119">Questa attività viene completata nel centro sicurezza & Compliance (SCC) di Office 365.</span><span class="sxs-lookup"><span data-stu-id="489a1-119">You complete this task in the Office 365 Security & Compliance Center (SCC).</span></span> <span data-ttu-id="489a1-120">Per ulteriori informazioni su SCC, [passare al centro conformità di Office 365 Security &](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="489a1-120">[Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="489a1-121">Per poter eseguire queste funzioni, è necessario essere nel gruppo di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="489a1-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="489a1-122">Per ulteriori informazioni sui gruppi di ruoli SCC, [accedere a autorizzazioni nel centro conformità di Office 365 Security &](permissions-in-the-security-and-compliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="489a1-122">[Go to Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="489a1-123">Utilizzando un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale di Office 365, accedere al centro sicurezza e conformità di Office 365 e, nell'elenco a sinistra, espandere **gestione minacce**, scegliere **Revisione**e quindi fare clic su **limitato. Gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="489a1-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="489a1-124">Per passare direttamente alla pagina **utenti con restrizioni** (in precedenza nota come centro operazioni) nel centro sicurezza &amp; e conformità, utilizzare questo URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="489a1-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="489a1-125">Questa pagina contiene l'elenco di utenti bloccati dall'invio di posta all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="489a1-125">This page will contain the list of users that have been blocked from sending mail to outside of your organization.</span></span>  <span data-ttu-id="489a1-126">Individuare l'utente per il quale si desidera rimuovere le restrizioni e quindi fare clic su **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="489a1-126">Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="489a1-127">Un fly-out entrerà nei dettagli relativi all'account di cui è riservata l'invio.</span><span class="sxs-lookup"><span data-stu-id="489a1-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="489a1-128">È consigliabile eseguire le procedure consigliate per assicurarsi di prendere le azioni appropriate nel caso in cui l'account sia effettivamente compromesso.</span><span class="sxs-lookup"><span data-stu-id="489a1-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="489a1-129">Fare clic su **Avanti** al termine.</span><span class="sxs-lookup"><span data-stu-id="489a1-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="489a1-130">Nella schermata successiva sono disponibili suggerimenti che consentono di evitare futuri compromessi.</span><span class="sxs-lookup"><span data-stu-id="489a1-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="489a1-131">L'abilitazione dell'autenticazione a più fattori (AMF) e la modifica delle password sono una buona difesa.</span><span class="sxs-lookup"><span data-stu-id="489a1-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="489a1-132">Fare clic su **Sblocca utente** al termine.</span><span class="sxs-lookup"><span data-stu-id="489a1-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="489a1-133">Fare clic su **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="489a1-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="489a1-134">Potrebbero essere necessari fino a 30 minuti prima che vengano rimosse le restrizioni.</span><span class="sxs-lookup"><span data-stu-id="489a1-134">It may take up to 30 minutes before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="489a1-135">Verificare che gli amministratori siano avvisati quando questo accade</span><span class="sxs-lookup"><span data-stu-id="489a1-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="489a1-136">Gli amministratori del tenant riceveranno anche un avviso che indica che l'utente è stato impedito di inviare altri messaggi in uscita.</span><span class="sxs-lookup"><span data-stu-id="489a1-136">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span> <span data-ttu-id="489a1-137">Si tratta di un avviso predefinito fornito per tutti i tenant ed è elencato nella pagina Criteri di avviso di SCC, intitolata "utente con restrizioni dall'invio di messaggi di posta elettronica".</span><span class="sxs-lookup"><span data-stu-id="489a1-137">It is a default alert that is provided for all tenants and is listed in the SCC Alert policies page, titled "User restricted from sending email".</span></span> <span data-ttu-id="489a1-138">Andare a [criteri di avviso nel centro conformità di Office 365 Security &](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies) per ulteriori informazioni sull'avviso.</span><span class="sxs-lookup"><span data-stu-id="489a1-138">Go to [Alert policies in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies) for more information on the alert.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="489a1-139">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="489a1-139">For more information</span></span>

[<span data-ttu-id="489a1-140">Risposta a un account di posta elettronica compromesso</span><span class="sxs-lookup"><span data-stu-id="489a1-140">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="489a1-141">Informazioni sull'utente con restrizioni dall'invio di messaggi di avviso tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="489a1-141">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[<span data-ttu-id="489a1-142">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="489a1-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="489a1-143">Autorizzazioni nel centro conformità & sicurezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="489a1-143">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
