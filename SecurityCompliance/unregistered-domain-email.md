---
title: Messaggio di posta elettronica dominio non registrati
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Se si invia un volume elevato di posta elettronica dominio annullare la registrazione, si corre il rischio della posta elettronica Guida bloccato. In questo articolo per ulteriori informazioni.
ms.openlocfilehash: f2b60f492197bf0dadb702a1c3f184c2d7e56bf1
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998600"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="965a3-104">Annullare la registrazione dominio di posta elettronica: Che cosa è necessario sapere</span><span class="sxs-lookup"><span data-stu-id="965a3-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="965a3-p102">Office 365 consente di tenant inoltrare alcuni messaggi tramite Exchange Online Protection (EOP). Un esempio supportato è quando gli utenti dispongono di una cassetta postale di Office 365 e un utente esterno Invia messaggio di posta elettronica ma inoltro della posta è configurato in modo che torna alla cassetta postale esterno dell'utente. Si tratta più comune in ambienti education cui studenti desiderano sfruttare l'interfaccia di posta elettronica personale da dispongono comunque messaggi di posta elettronica relativi a scuola. Un altro esempio è quando i clienti sono in uno scenario ibrido e sono presenti server locali che inviano posta elettronica da EOP.</span><span class="sxs-lookup"><span data-stu-id="965a3-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premise servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="965a3-109">Problemi con i domini non registrati</span><span class="sxs-lookup"><span data-stu-id="965a3-109">Problems with unregistered domains</span></span>

<span data-ttu-id="965a3-p103">Il problema è quando i server locali vengano compromessi e finiscono con l'inoltro di un volume elevato di posta indesiderata da EOP. Nella maggior parte dei casi, vengono impostati i connettori destro ma posta venga inviata da domini di annullare la registrazione, noto anche come provisioning. Office 365 consente di posta elettronica proviene da domini non registrati ragionevole, ma deve essere configurato un dominio accettato nell'interfaccia di amministrazione per ogni dominio di che se si prevede di invio.</span><span class="sxs-lookup"><span data-stu-id="965a3-p103">The problem is when on-premise servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="965a3-p104">Una volta compromesso, tenant viene impedito l'invio dei messaggi in uscita per i domini di annullare la registrazione. Gli utenti riceveranno un mancato recapito rapporto di mancato recapito indicante:</span><span class="sxs-lookup"><span data-stu-id="965a3-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="965a3-p105">550 5.7.750 servizio non disponibile. Bloccata l'invio da domini annullare la registrazione client</span><span class="sxs-lookup"><span data-stu-id="965a3-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="965a3-117">Sblocco tenant per inviare nuovamente</span><span class="sxs-lookup"><span data-stu-id="965a3-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="965a3-118">Esistono diversi aspetti da eseguire se ottenere bloccato per l'invio da domini annullare la registrazione:</span><span class="sxs-lookup"><span data-stu-id="965a3-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="965a3-p106">Assicurarsi di registrare tutti i domini nell'interfaccia di amministrazione di Office 365. Sono disponibili ulteriori informazioni [di seguito](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="965a3-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="965a3-p107">Bloccare i server locali e verificare che non vengano compromesse. Esistono molti fattori coinvolti in questo caso, in particolare se si tratta di server di terze parti, ma è necessario assicurarsi che tutti i messaggi lasciano tale server sia valido.</span><span class="sxs-lookup"><span data-stu-id="965a3-p107">Lock down your on-premise servers and ensure that they are not compromised. There are many factors involved here, especially if these are third-party servers, but you will need to be able to make sure all mail leaving that server is legitimate.</span></span>

<span data-ttu-id="965a3-p108">Al termine, è necessario chiamare il supporto Microsoft e chiederà di ottenere il tenant sbloccato per inviare nuovamente da domini di annullare la registrazione.  Fornire il codice di errore è utile, ma è necessario verificare che l'ambiente è protetta e che la posta indesiderata non verrà inviata nuovamente. Sono disponibili ulteriori informazioni [di seguito](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span><span class="sxs-lookup"><span data-stu-id="965a3-p108">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="965a3-126">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="965a3-126">For more information</span></span>

[<span data-ttu-id="965a3-127">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="965a3-127">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="965a3-128">Rapporti di mancato recapito di posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="965a3-128">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="965a3-129">Configurazione dell'inoltro della posta elettronica per una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="965a3-129">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="965a3-130">Come configurare un dispositivo multifunzionale o un'applicazione all'invio di posta elettronica tramite Office 365</span><span class="sxs-lookup"><span data-stu-id="965a3-130">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="965a3-131">[Gestisci domini accettati in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="965a3-131">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
