---
title: Messaggio di posta elettronica dominio non registrati
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Se si invia un volume elevato di posta elettronica dominio annullare la registrazione, si corre il rischio della posta elettronica Guida bloccato. In questo articolo per ulteriori informazioni.
ms.openlocfilehash: 30d7887be0429195380f2c4ae1a328904dffd69c
ms.sourcegitcommit: 6d72cdb882b93edf6dfddb5ff2e6d8a16e2fa0bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "25596729"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="1a416-104">Annullare la registrazione dominio di posta elettronica: Che cosa è necessario sapere</span><span class="sxs-lookup"><span data-stu-id="1a416-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="1a416-p102">Office 365 consente di tenant inoltrare alcuni messaggi tramite Exchange Online Protection (EOP). Un esempio supportato è quando gli utenti dispongono di una cassetta postale di Office 365 e un utente esterno Invia messaggio di posta elettronica ma inoltro della posta è configurato in modo che torna alla cassetta postale esterno dell'utente. Si tratta più comune in ambienti education cui studenti desiderano sfruttare l'interfaccia di posta elettronica personale da dispongono comunque messaggi di posta elettronica relativi a scuola. Un altro esempio è quando i clienti sono in uno scenario ibrido e sono presenti server locali che inviano posta elettronica da EOP.</span><span class="sxs-lookup"><span data-stu-id="1a416-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premise servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="1a416-109">Problemi con i domini non registrati</span><span class="sxs-lookup"><span data-stu-id="1a416-109">Problems with unregistered domains</span></span>

<span data-ttu-id="1a416-p103">Il problema è quando i server locali vengano compromessi e finiscono con l'inoltro di un volume elevato di posta indesiderata da EOP. Nella maggior parte dei casi, vengono impostati i connettori destro ma posta venga inviata da domini di annullare la registrazione, noto anche come provisioning. Office 365 consente di posta elettronica proviene da domini non registrati ragionevole, ma deve essere configurato un dominio accettato nell'interfaccia di amministrazione per ogni dominio di che se si prevede di invio.</span><span class="sxs-lookup"><span data-stu-id="1a416-p103">The problem is when on-premise servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="1a416-p104">Una volta compromesso, tenant viene impedito l'invio dei messaggi in uscita per i domini di annullare la registrazione. Gli utenti riceveranno un mancato recapito rapporto di mancato recapito indicante:</span><span class="sxs-lookup"><span data-stu-id="1a416-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="1a416-p105">550 5.7.750 servizio non disponibile. Bloccata l'invio da domini annullare la registrazione client</span><span class="sxs-lookup"><span data-stu-id="1a416-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="1a416-117">Sblocco tenant per inviare nuovamente</span><span class="sxs-lookup"><span data-stu-id="1a416-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="1a416-118">Esistono diversi aspetti da eseguire se ottenere bloccato per l'invio da domini annullare la registrazione:</span><span class="sxs-lookup"><span data-stu-id="1a416-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="1a416-p106">Assicurarsi di registrare tutti i domini nell'interfaccia di amministrazione di Office 365. Sono disponibili ulteriori informazioni [di seguito](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="1a416-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="1a416-p107">Cercare i connettori non comune. Gli operatori dannosi spesso creano nuovi connettori in ingresso nel tenant Office 365 per inviare posta indesiderata. Sono disponibili ulteriori informazioni sull'archiviazione dei connettori di [seguito](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1a416-p107">Look for unusual connectors. Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam. More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="1a416-124">Bloccare i server locali e verificare che non vengano compromesse.</span><span class="sxs-lookup"><span data-stu-id="1a416-124">Lock down your on-premise servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="1a416-p108">Esistono molti fattori coinvolti in questo caso, in particolare se si tratta di server di terze parti. In ogni caso, è necessario poter verificare che tutti i messaggi lasciano i server siano legittimi.</span><span class="sxs-lookup"><span data-stu-id="1a416-p108">There are many factors involved here, especially if these are third-party servers. Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="1a416-p109">Al termine, è necessario chiamare il supporto Microsoft e chiederà di ottenere il tenant sbloccato per inviare nuovamente da domini di annullare la registrazione.  Fornire il codice di errore è utile, ma è necessario verificare che l'ambiente è protetta e che la posta indesiderata non verrà inviata nuovamente. Sono disponibili ulteriori informazioni sull'apertura di un caso del supporto tecnico [di seguito](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span><span class="sxs-lookup"><span data-stu-id="1a416-p109">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="1a416-130">Per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="1a416-130">For more information</span></span>

[<span data-ttu-id="1a416-131">Office 365 email anti-spam protection</span><span class="sxs-lookup"><span data-stu-id="1a416-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="1a416-132">Rapporti di mancato recapito della posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="1a416-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="1a416-133">Configurare l'inoltro della posta elettronica per una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="1a416-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="1a416-134">Come configurare un dispositivo multifunzione o un'applicazione per l'invio di posta elettronica con Office 365</span><span class="sxs-lookup"><span data-stu-id="1a416-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="1a416-135">[Gestisci domini accettati in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="1a416-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
