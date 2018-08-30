---
title: Flusso di posta in EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/13/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Come cliente di Exchange Online Protection (EOP), tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti li visualizzino. A prescindere che tutte le cassette postali siano ospitate nel cloud con Exchange Online o siano locali (il cosiddetto scenario autonomo), ad esempio per continuare a sfruttare l'infrastruttura esistente, sono disponibili diverse opzioni di routing dei messaggi che passeranno attraverso EOP per l'elaborazione prima di essere instradati alle cassette postali dei dipendenti.
ms.openlocfilehash: ff5284eafe01a3887fa69fde2b5bcd023ee391db
ms.sourcegitcommit: 285c58a371e6ab82c40fac3f24530cf3b09d0175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2018
ms.locfileid: "23002146"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="2c721-104">Flusso di posta in EOP</span><span class="sxs-lookup"><span data-stu-id="2c721-104">Mail flow in EOP</span></span>

<span data-ttu-id="2c721-p102">Come cliente di Exchange Online Protection (EOP), tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti li visualizzino. A prescindere che tutte le cassette postali siano ospitate nel cloud con Exchange Online o siano locali (il cosiddetto scenario autonomo), ad esempio per continuare a sfruttare l'infrastruttura esistente, sono disponibili diverse opzioni di routing dei messaggi che passeranno attraverso EOP per l'elaborazione prima di essere instradati alle cassette postali dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="2c721-p102">As an Exchange Online Protection (EOP) customer, all messages sent to your organization pass through EOP before your workers see them. Whether you host all of your mailboxes in the cloud with Exchange Online, or you host your mailboxes on premises (called a standalone scenario), perhaps to continue taking advantage of your existing infrastructure, you have options about how to route messages that will pass through EOP for processing before they are routed to your worker inboxes.</span></span>
  
<span data-ttu-id="2c721-p103">È possibile configurare il routing della posta personalizzato ai fini della conformità della messaggistica a un requisito aziendale. Ad esempio, è possibile far passare tutta la posta in uscita attraverso l'applicazione di filtro dei criteri di posta.</span><span class="sxs-lookup"><span data-stu-id="2c721-p103">You may want to configure custom mail routing to conform your messaging to a business requirement. For instance, you can pass all of your outbound mail through a policy-filtering appliance.</span></span> 
  
## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="2c721-109">Utilizzo dei messaggi e delle opzioni di accesso ai messaggi</span><span class="sxs-lookup"><span data-stu-id="2c721-109">Working with messages and message access options</span></span>

<span data-ttu-id="2c721-p104">EOP offre molta flessibilità per il routing dei messaggi. Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="2c721-p104">EOP offers a lot of flexibility in how your messages are routed. The following topics explain steps in the mail flow process.</span></span>
  
<span data-ttu-id="2c721-112">[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) Descrive la funzionalità blocco Edge basato su directory che consente all'utente di rifiutare messaggi per destinatari non validi nel perimetro della rete di servizi.</span><span class="sxs-lookup"><span data-stu-id="2c721-112">[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span> 
  
<span data-ttu-id="2c721-113">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descrive come gestire i domini associati al servizio EOP.</span><span class="sxs-lookup"><span data-stu-id="2c721-113">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span> 
  
<span data-ttu-id="2c721-p105">Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini. Per ulteriori informazioni sui sottodomini, vedere [Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c721-p105">If you add subdomains to your organization, your EOP service can help you manage these too. Learn more about subdomains at [Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx).</span></span>
  
<span data-ttu-id="2c721-p106">In [Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx) vengono descritti i connettori EOP e come è possibile utilizzarli per personalizzare il routing della posta. Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host.</span><span class="sxs-lookup"><span data-stu-id="2c721-p106">[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx) introduces connectors and shows how you can use them to customize mail routing. Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span> 
  
<span data-ttu-id="2c721-p107">Per garantire che la posta indesiderata sia instradata correttamente alla cartella posta indesiderata di ogni utente, è necessario eseguire due passaggi di configurazione. Questi sono descritti nelle [Assicurarsi che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Se non si desidera spostare messaggi nella cartella posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](../configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2c721-p107">To ensure that junk email is routed correctly to each user's junk-email folder, you must perform a couple configuration steps. These are detailed in [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](../configure-your-spam-filter-policies.md).</span></span>
  
## <a name="verify-mail-flow"></a><span data-ttu-id="2c721-122">Verificare il flusso di posta</span><span class="sxs-lookup"><span data-stu-id="2c721-122">Verify mail flow</span></span>

<span data-ttu-id="2c721-p108">Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="2c721-p108">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span> 
  
<span data-ttu-id="2c721-125">[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx) fornisce le istruzioni per la verifica della configurazione corretta del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="2c721-125">[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx) provides instructions for testing that your mail flow is set up correctly.</span></span> 
  

