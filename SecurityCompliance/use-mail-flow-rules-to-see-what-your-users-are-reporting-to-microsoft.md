---
title: Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: È possibile creare una regola del flusso di posta di Exchange per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzarli nei propri processi di sicurezza
ms.openlocfilehash: e93c90074ad2d143a964b928d8e868bee24acba2
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341167"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="e9dab-103">Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9dab-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="e9dab-p101">È possibile inviare messaggi falsi positivi e falsi negativi a Microsoft per l'analisi in diversi modi. Come amministratore, è possibile utilizzare le regole del flusso di posta per vedere cosa gli utenti riferiscono a Microsoft come posta indesiderata, non posta indesiderata e truffe di phishing. Per ulteriori informazioni, vedere [inviare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Al contrario, è possibile creare una regola del flusso di posta di Exchange (nota anche come regola di trasporto) per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzarli nei propri processi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e9dab-p101">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e9dab-108">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="e9dab-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="e9dab-109">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="e9dab-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="e9dab-p102">Prima di poter eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate. Per sapere quali autorizzazioni sono necessarie, vedere la voce "regole del flusso di posta" nell'argomento [criteri di messaggistica e autorizzazioni di conformità](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) e "criteri cassetta postale di Outlook sul Web" nell'argomento [autorizzazioni per client e dispositivi mobili](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) .</span><span class="sxs-lookup"><span data-stu-id="e9dab-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="e9dab-112">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="e9dab-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="e9dab-113">Utilizzare l'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta per visualizzare report manuali dell'utente su posta indesiderata, phishing e posta non indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e9dab-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="e9dab-114">Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="e9dab-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="e9dab-115">Fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="e9dab-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="e9dab-116">Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="e9dab-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="e9dab-117">In **Applica questa regola se**, selezionare **Il destinatario** e scegliere **l'indirizzo include una di queste parole**.</span><span class="sxs-lookup"><span data-stu-id="e9dab-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="e9dab-118">Nella casella **Specificare parole o frasi**, eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="e9dab-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="e9dab-p103">Digitare `abuse@messaging.microsoft.com` e quindi fare ![clic su](media/ITPro-EAC-AddIcon.gif)icona Aggiungi, quindi `junk@office365.microsoft.com` digitare e quindi ![fare clic](media/ITPro-EAC-AddIcon.gif)su icona Aggiungi. Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi falsi negativi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9dab-p103">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="e9dab-p104">Digitare `phish@office365.microsoft.com` e quindi fare ![clic su](media/ITPro-EAC-AddIcon.gif)icona Aggiungi. Questo indirizzo di posta elettronica viene utilizzato per inviare messaggi di phishing mancanti a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9dab-p104">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="e9dab-p105">Digitare `false_positive@messaging.microsoft.com` e quindi fare ![clic su](media/ITPro-EAC-AddIcon.gif)icona Aggiungi, quindi `not_junk@office365.microsoft.com` digitare e quindi ![fare clic](media/ITPro-EAC-AddIcon.gif)su icona Aggiungi. Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9dab-p105">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="e9dab-125">Fare clic su **ok**.</span><span class="sxs-lookup"><span data-stu-id="e9dab-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="e9dab-126">In **Eseguire le operazioni seguenti** selezionare **Invia il messaggio in Ccn a...**, quindi selezionare le cassette postali in cui si desidera ricevere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="e9dab-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="e9dab-p106">Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarlo. Vedere [procedure per le regole del flusso di posta](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="e9dab-p106">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="e9dab-p107">Fare clic sul pulsante **salva** per salvare la regola. Viene visualizzata nell'elenco delle regole.</span><span class="sxs-lookup"><span data-stu-id="e9dab-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="e9dab-132">Dopo aver creato e impostato la regola, eventuali messaggi inviati dall'organizzazione agli indirizzi di posta elettronica specificati verranno copiati alla cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="e9dab-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

