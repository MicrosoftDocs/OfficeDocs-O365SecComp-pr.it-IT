---
title: Risolvere i problemi di recapito della posta elettronica per il codice di errore 5.7.7 XX in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/11/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Informazioni su come risolvere i problemi di posta elettronica per il codice di errore 5.7.7 XX in Exchange Online (tenant bloccato dall'invio di messaggi di posta elettronica).
ms.openlocfilehash: dbdfdeb351125442018e520d72f953e116d8e1a8
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "34865510"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a><span data-ttu-id="023a5-103">Risolvere i problemi di recapito della posta elettronica per il codice di errore 5.7.7 XX in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="023a5-103">Fix email delivery issues for error code 5.7.7xx in Exchange Online</span></span>

<span data-ttu-id="023a5-104">In questo argomento vengono descritte le operazioni che è possibile eseguire se viene visualizzato il codice di stato 550 5.7.7 XX in un rapporto di mancato recapito (noto anche come NDR, messaggio di rimbalzo, notifica sullo stato del recapito o DSN).</span><span class="sxs-lookup"><span data-stu-id="023a5-104">This topic describes what you can do if you see status code 550 5.7.7xx in a non-delivery report (also known as an NDR, bounce message, delivery status notification, or DSN).</span></span> <span data-ttu-id="023a5-105">Questa notifica automatica viene visualizzata quando il tenant è limitato dall'invio di messaggi di posta elettronica in un modo o nell'altro.</span><span class="sxs-lookup"><span data-stu-id="023a5-105">You'll see this automated notification when your tenant is restricted from sending email in one way or another.</span></span> <span data-ttu-id="023a5-106">Questi codici di errore vengono in genere disponibili come 705 o 750.</span><span class="sxs-lookup"><span data-stu-id="023a5-106">These error codes will usually come in as 705 or 750.</span></span>

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a><span data-ttu-id="023a5-107">5.7.705: tenant ha superato la restrizione di soglia: informazioni utili</span><span class="sxs-lookup"><span data-stu-id="023a5-107">5.7.705: Tenant has exceeded threshold restriction: What you need to know</span></span>

<span data-ttu-id="023a5-108">I mittenti interni possono vedere questo rapporto di mancato recapito quando si tenta di inviare messaggi di posta elettronica se il tenant è stato compromesso.</span><span class="sxs-lookup"><span data-stu-id="023a5-108">Internal senders could see this NDR whenever you try to send mail if your tenant was compromised.</span></span> <span data-ttu-id="023a5-109">Questo solitamente occus quando la maggior parte del traffico proveniente dal tenant è stata rilevata come sospetta e ha portato al divieto di inviare l'abilità per il tenant.</span><span class="sxs-lookup"><span data-stu-id="023a5-109">This usually occus when the majority of traffic from your tenant has been detected as suspicious and has resulted in a ban on sending ability for the tenant.</span></span> <span data-ttu-id="023a5-110">Questo può verificarsi anche se gli utenti inviano una grande quantità di posta in blocco da Office 365.</span><span class="sxs-lookup"><span data-stu-id="023a5-110">This can also occur if your users send an large amount of bulk mail from Office 365.</span></span> <span data-ttu-id="023a5-111">Come indicato nella descrizione del servizio, i clienti di Exchange Online che hanno la necessità di inviare messaggi di posta elettronica commerciali legittimi (ad esempio, i bollettini dei clienti) devono utilizzare provider di terze parti specializzati in tali servizi.</span><span class="sxs-lookup"><span data-stu-id="023a5-111">As stated in the service description, Exchange Online customers who need to send legitimate bulk commercial email (for example, customer newsletters) should use third-party providers that specialize in these services.</span></span>

<span data-ttu-id="023a5-112">Una volta che gli utenti collettivamente, come tenant, inviano una certa quantità di posta sospette tramite il servizio, a tutti gli utenti può essere impedito di inviare posta finché il problema non viene risolto.</span><span class="sxs-lookup"><span data-stu-id="023a5-112">Once your users collectively, as a tenant, send a certain amount of suspicious mail through the service, all users can be prevented from sending any mail until the problem is fixed.</span></span> <span data-ttu-id="023a5-113">Gli utenti riceveranno un rapporto di mancato recapito (NDR) che indica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="023a5-113">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="023a5-114">550 5.7.705 accesso negato, il tenant ha superato la soglia</span><span class="sxs-lookup"><span data-stu-id="023a5-114">550 5.7.705 Access denied, tenant has exceeded threshold</span></span>

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a><span data-ttu-id="023a5-115">5.7.750: limitazione della posta elettronica del dominio non registrato: informazioni utili</span><span class="sxs-lookup"><span data-stu-id="023a5-115">5.7.750: Unregistered Domain Email restriction: What you need to know</span></span>

<span data-ttu-id="023a5-116">Office 365 consente ai tenant di inoltrare alcuni messaggi tramite Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="023a5-116">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="023a5-117">Un esempio supportato potrebbe essere quello in cui gli utenti dispongono di una cassetta postale di Office 365 e un utente esterno invia loro la posta elettronica, ma l'inoltro della posta elettronica è configurato in modo che rientri nella cassetta postale esterna dell'utente.</span><span class="sxs-lookup"><span data-stu-id="023a5-117">One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox.</span></span> <span data-ttu-id="023a5-118">Questo è il più comune negli ambienti scolastici in cui gli studenti desiderano sfruttare la propria interfaccia di posta elettronica personale, ma continuano a ricevere messaggi di posta elettronica correlati alla scuola.</span><span class="sxs-lookup"><span data-stu-id="023a5-118">This is most common in education environments where students want to leverage their personal email interface but still get emails related to school.</span></span> <span data-ttu-id="023a5-119">Un altro esempio è quando i clienti sono in uno scenario ibrido e dispongono di server locali che inviano messaggi di posta elettronica da EOP.</span><span class="sxs-lookup"><span data-stu-id="023a5-119">Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

### <a name="problems-with-unregistered-domains"></a><span data-ttu-id="023a5-120">Problemi relativi ai domini non registrati</span><span class="sxs-lookup"><span data-stu-id="023a5-120">Problems with unregistered domains</span></span>

<span data-ttu-id="023a5-121">Il problema è quando i server locali vengono compromessi e finiscono con l'inoltro di un volume elevato di posta indesiderata fuori EOP.</span><span class="sxs-lookup"><span data-stu-id="023a5-121">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP.</span></span> <span data-ttu-id="023a5-122">In quasi tutti i casi, i connettori giusti sono configurati, ma il messaggio di posta elettronica viene inviato dall'annullamento della registrazione, noto anche come Unprovisioned, Domains.</span><span class="sxs-lookup"><span data-stu-id="023a5-122">In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains.</span></span> <span data-ttu-id="023a5-123">Office 365 consente una quantità ragionevole di messaggi di posta elettronica provenienti da domini non registrati, ma un dominio accettato deve essere configurato nell'interfaccia di amministrazione per ogni dominio in cui si intende inviare.</span><span class="sxs-lookup"><span data-stu-id="023a5-123">Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="023a5-124">Una volta compromesso, ai tenant verrà impedito di inviare la posta in uscita per i domini non registrati.</span><span class="sxs-lookup"><span data-stu-id="023a5-124">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains.</span></span> <span data-ttu-id="023a5-125">Gli utenti riceveranno un rapporto di mancato recapito (NDR) che indica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="023a5-125">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="023a5-126">550 servizio 5.7.750 non disponibile.</span><span class="sxs-lookup"><span data-stu-id="023a5-126">550 5.7.750 Service unavailable.</span></span> <span data-ttu-id="023a5-127">Client bloccato dall'invio di domini non registrati</span><span class="sxs-lookup"><span data-stu-id="023a5-127">Client blocked from sending from unregistered domains</span></span>

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="023a5-128">Come sbloccare tenant per inviare di nuovo</span><span class="sxs-lookup"><span data-stu-id="023a5-128">How to unblocking tenant in order to send again</span></span>

<span data-ttu-id="023a5-129">Se il tenant viene bloccato per l'invio di messaggi di posta elettronica, è necessario eseguire diverse operazioni:</span><span class="sxs-lookup"><span data-stu-id="023a5-129">There are several things you need to do if your tenant get blocked for sending email:</span></span>

1. <span data-ttu-id="023a5-130">Assicurarsi di registrare tutti i domini nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="023a5-130">Make sure that you register all of your domains in Microsoft 365 admin center.</span></span> <span data-ttu-id="023a5-131">Ulteriori informazioni sono disponibili [qui](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="023a5-131">More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="023a5-132">Cercare connettori inusuali.</span><span class="sxs-lookup"><span data-stu-id="023a5-132">Look for unusual connectors.</span></span> <span data-ttu-id="023a5-133">Gli attori maligni spesso creano nuovi connettori in ingresso nel tenant di Office 365 per inviare la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="023a5-133">Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam.</span></span> <span data-ttu-id="023a5-134">Ulteriori informazioni su come controllare i connettori sono disponibili [qui](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="023a5-134">More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="023a5-135">Bloccare i server locali e assicurarsi che non vengano compromessi.</span><span class="sxs-lookup"><span data-stu-id="023a5-135">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="023a5-136">Vi sono numerosi fattori coinvolti in questo articolo, soprattutto se si tratta di server di terze parti.</span><span class="sxs-lookup"><span data-stu-id="023a5-136">There are many factors involved here, especially if these are third-party servers.</span></span> <span data-ttu-id="023a5-137">Indipendentemente da ciò, è necessario essere in grado di confermare che tutti i messaggi che lasciano i server siano legittimi.</span><span class="sxs-lookup"><span data-stu-id="023a5-137">Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="023a5-138">Dopo aver completato l'operazione, è necessario chiamare il supporto tecnico Microsoft e chiedere di ottenere il tenant sbloccato per inviare di nuovo i domini non registrati.</span><span class="sxs-lookup"><span data-stu-id="023a5-138">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span>  <span data-ttu-id="023a5-139">Fornire il codice di errore è utile, ma sarà necessario dimostrare che l'ambiente è protetto e che la posta indesiderata non verrà più inviata.</span><span class="sxs-lookup"><span data-stu-id="023a5-139">Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again.</span></span> <span data-ttu-id="023a5-140">Ulteriori informazioni sull'apertura di un caso di supporto sono disponibili [qui](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span><span class="sxs-lookup"><span data-stu-id="023a5-140">More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="023a5-141">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="023a5-141">For more information</span></span>

[<span data-ttu-id="023a5-142">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="023a5-142">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="023a5-143">Rapporti di mancato recapito della posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="023a5-143">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="023a5-144">Configurare l'inoltro della posta elettronica per una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="023a5-144">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="023a5-145">Come configurare un dispositivo multifunzionale o un'applicazione all'invio di posta elettronica tramite Office 365</span><span class="sxs-lookup"><span data-stu-id="023a5-145">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="023a5-146">[Gestire i domini accettati in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="023a5-146">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>