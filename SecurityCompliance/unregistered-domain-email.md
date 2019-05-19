---
title: Messaggio di posta elettronica di dominio non registrato
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Se si invia un volume elevato di posta elettronica di dominio non registrato, si rischia che la posta elettronica venga bloccata. Leggere questo articolo per ulteriori informazioni.
ms.openlocfilehash: 207b71ab7e144af9709e7485d61c936e07271a11
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156298"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="4a69f-104">Messaggio di posta elettronica di dominio non registrato: informazioni utili</span><span class="sxs-lookup"><span data-stu-id="4a69f-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="4a69f-105">Office 365 consente ai tenant di inoltrare alcuni messaggi tramite Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="4a69f-105">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="4a69f-106">Un esempio supportato potrebbe essere quello in cui gli utenti dispongono di una cassetta postale di Office 365 e un utente esterno invia loro la posta elettronica, ma l'inoltro della posta elettronica è configurato in modo che rientri nella cassetta postale esterna dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4a69f-106">One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox.</span></span> <span data-ttu-id="4a69f-107">Questo è il più comune negli ambienti scolastici in cui gli studenti desiderano sfruttare la propria interfaccia di posta elettronica personale, ma continuano a ricevere messaggi di posta elettronica correlati alla scuola.</span><span class="sxs-lookup"><span data-stu-id="4a69f-107">This is most common in education environments where students want to leverage their personal email interface but still get emails related to school.</span></span> <span data-ttu-id="4a69f-108">Un altro esempio è quando i clienti sono in uno scenario ibrido e dispongono di server locali che inviano messaggi di posta elettronica da EOP.</span><span class="sxs-lookup"><span data-stu-id="4a69f-108">Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="4a69f-109">Problemi relativi ai domini non registrati</span><span class="sxs-lookup"><span data-stu-id="4a69f-109">Problems with unregistered domains</span></span>

<span data-ttu-id="4a69f-110">Il problema è quando i server locali vengono compromessi e finiscono con l'inoltro di un volume elevato di posta indesiderata fuori EOP.</span><span class="sxs-lookup"><span data-stu-id="4a69f-110">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP.</span></span> <span data-ttu-id="4a69f-111">In quasi tutti i casi, i connettori giusti sono configurati, ma il messaggio di posta elettronica viene inviato dall'annullamento della registrazione, noto anche come Unprovisioned, Domains.</span><span class="sxs-lookup"><span data-stu-id="4a69f-111">In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains.</span></span> <span data-ttu-id="4a69f-112">Office 365 consente una quantità ragionevole di messaggi di posta elettronica provenienti da domini non registrati, ma un dominio accettato deve essere configurato nell'interfaccia di amministrazione per ogni dominio in cui si intende inviare.</span><span class="sxs-lookup"><span data-stu-id="4a69f-112">Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="4a69f-113">Una volta compromesso, ai tenant verrà impedito di inviare la posta in uscita per i domini non registrati.</span><span class="sxs-lookup"><span data-stu-id="4a69f-113">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains.</span></span> <span data-ttu-id="4a69f-114">Gli utenti riceveranno un rapporto di mancato recapito (NDR) che indica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4a69f-114">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="4a69f-115">550 servizio 5.7.750 non disponibile.</span><span class="sxs-lookup"><span data-stu-id="4a69f-115">550 5.7.750 Service unavailable.</span></span> <span data-ttu-id="4a69f-116">Client bloccato dall'invio di domini non registrati</span><span class="sxs-lookup"><span data-stu-id="4a69f-116">Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="4a69f-117">Sblocco del tenant per l'invio di nuovo</span><span class="sxs-lookup"><span data-stu-id="4a69f-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="4a69f-118">È necessario eseguire diverse operazioni se si viene bloccati per l'invio da domini non registrati:</span><span class="sxs-lookup"><span data-stu-id="4a69f-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="4a69f-119">Assicurarsi di registrare tutti i domini nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a69f-119">Make sure that you register all of your domains in Microsoft 365 admin center.</span></span> <span data-ttu-id="4a69f-120">Ulteriori informazioni sono disponibili [qui](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="4a69f-120">More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="4a69f-121">Cercare connettori inusuali.</span><span class="sxs-lookup"><span data-stu-id="4a69f-121">Look for unusual connectors.</span></span> <span data-ttu-id="4a69f-122">Gli attori maligni spesso creano nuovi connettori in ingresso nel tenant di Office 365 per inviare la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="4a69f-122">Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam.</span></span> <span data-ttu-id="4a69f-123">Ulteriori informazioni su come controllare i connettori sono disponibili [qui](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4a69f-123">More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="4a69f-124">Bloccare i server locali e assicurarsi che non vengano compromessi.</span><span class="sxs-lookup"><span data-stu-id="4a69f-124">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="4a69f-125">Vi sono numerosi fattori coinvolti in questo articolo, soprattutto se si tratta di server di terze parti.</span><span class="sxs-lookup"><span data-stu-id="4a69f-125">There are many factors involved here, especially if these are third-party servers.</span></span> <span data-ttu-id="4a69f-126">Indipendentemente da ciò, è necessario essere in grado di confermare che tutti i messaggi che lasciano i server siano legittimi.</span><span class="sxs-lookup"><span data-stu-id="4a69f-126">Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="4a69f-127">Dopo aver completato l'operazione, è necessario chiamare il supporto tecnico Microsoft e chiedere di ottenere il tenant sbloccato per inviare di nuovo i domini non registrati.</span><span class="sxs-lookup"><span data-stu-id="4a69f-127">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span>  <span data-ttu-id="4a69f-128">Fornire il codice di errore è utile, ma sarà necessario dimostrare che l'ambiente è protetto e che la posta indesiderata non verrà più inviata.</span><span class="sxs-lookup"><span data-stu-id="4a69f-128">Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again.</span></span> <span data-ttu-id="4a69f-129">Ulteriori informazioni sull'apertura di un caso di supporto sono disponibili [qui](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span><span class="sxs-lookup"><span data-stu-id="4a69f-129">More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="4a69f-130">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="4a69f-130">For more information</span></span>

[<span data-ttu-id="4a69f-131">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="4a69f-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="4a69f-132">Rapporti di mancato recapito della posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="4a69f-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="4a69f-133">Configurare l'inoltro della posta elettronica per una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="4a69f-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="4a69f-134">Come configurare un dispositivo multifunzionale o un'applicazione all'invio di posta elettronica tramite Office 365</span><span class="sxs-lookup"><span data-stu-id="4a69f-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="4a69f-135">[Gestire i domini accettati in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="4a69f-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
