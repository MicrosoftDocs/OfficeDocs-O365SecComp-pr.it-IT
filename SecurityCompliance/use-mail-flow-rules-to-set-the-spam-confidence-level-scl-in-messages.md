---
title: Usare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a impostare il SCL dei messaggi in Exchange Online Protection.
ms.openlocfilehash: e07b90ab1ab004c39ef36b2aa744ca87120c11fe
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692745"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="e6aa0-103">Usare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi</span><span class="sxs-lookup"><span data-stu-id="e6aa0-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="e6aa0-104">È possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che imposta il livello di probabilità di posta indesiderata (SCL) di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-104">You can create a mail flow rule (also known as a transport rule) that sets the spam confidence level (SCL) of an email message.</span></span> <span data-ttu-id="e6aa0-105">Il livello SCL è una misura del modo in cui un messaggio deve essere la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-105">The SCL is a measure of how likely a message is to be spam.</span></span> <span data-ttu-id="e6aa0-106">Per posta indesiderata si intendono quei messaggi di posta elettronica non richiesti (e in genere non desiderati).</span><span class="sxs-lookup"><span data-stu-id="e6aa0-106">Spam is unsolicited (and typically unwanted) email messages.</span></span> <span data-ttu-id="e6aa0-107">Il servizio esegue un'azione diversa su un messaggio in base alla classificazione SCL.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-107">The service takes different action on a message depending on its SCL rating.</span></span> <span data-ttu-id="e6aa0-108">Ad esempio, si potrebbe voler bypassare il filtro del contenuto di posta indesiderata per i messaggi inviati da persone all'interno dell'organizzazione perché è attendibile che un messaggio inviato internamente da un collega non sia posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-108">For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam.</span></span> <span data-ttu-id="e6aa0-109">L'utilizzo delle regole del flusso di posta per impostare il valore SCL di un messaggio garantisce un maggiore controllo della gestione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-109">Using mail flow rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="e6aa0-110">**Che cosa è necessario sapere prima di iniziare**</span><span class="sxs-lookup"><span data-stu-id="e6aa0-110">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="e6aa0-111">Tempo stimato per il completamento di questa procedura: 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-111">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="e6aa0-112">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="e6aa0-113">Per sapere quali autorizzazioni sono necessarie, vedere "regole del flusso di posta" in [autorizzazioni funzionalità in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) o [funzionalità Permissions in EOP](eop/feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e6aa0-113">To see what permissions you need, see the "Mail flow rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="e6aa0-114">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="e6aa0-115">Per creare una regola del flusso di posta che consente di impostare il livello SCL di un messaggio</span><span class="sxs-lookup"><span data-stu-id="e6aa0-115">To create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="e6aa0-116">Nell'interfaccia di amministrazione di Exchange (EAC), scegliere **regole**del **flusso** \> di posta.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-116">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="e6aa0-117">Fare \*\*\*\*![clic su nuova](media/ITPro-EAC-AddIcon.gif)icona Aggiungi e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-117">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="e6aa0-118">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-118">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="e6aa0-119">Scegliere **altre opzioni**e quindi in **applica questa regola se**, specificare una condizione che attiverà l'azione che verrà impostata per questa regola (ovvero impostare il valore SCL).</span><span class="sxs-lookup"><span data-stu-id="e6aa0-119">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="e6aa0-120">Ad esempio, è possibile impostare **il mittente** \> **come interno/esterno**e quindi nella finestra di dialogo **Seleziona percorso mittente** selezionare **all'interno dell'organizzazione**e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-120">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
    <span data-ttu-id="e6aa0-121">![Seleziona la località del mittente](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="e6aa0-121">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="e6aa0-122">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-122">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="e6aa0-123">Nella finestra di dialogo **specifica SCL** selezionare uno dei valori seguenti e quindi scegliere **OK**:</span><span class="sxs-lookup"><span data-stu-id="e6aa0-123">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="e6aa0-124">**Bypass del filtro posta** indesiderata-imposta il livello SCL su-1, il che significa che il filtro contenuto non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-124">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="e6aa0-125">**0-4** -quando si imposta il livello SCL su uno di questi valori, il messaggio viene passato al filtro contenuto per ulteriori elaborazioni.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-125">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="e6aa0-126">**5, 6** : quando si imposta il livello SCL su uno di questi valori, verrà applicata l'azione specificata per la **posta** indesiderata nei criteri di filtro del contenuto applicabili.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-126">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="e6aa0-127">Per impostazione predefinita, l'azione consiste nell'inviare il messaggio alla cartella posta inDesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-127">By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="e6aa0-128">**7-9** -quando si imposta il livello SCL su uno di questi valori, verrà applicata l'azione specificata per la posta indesiderata con **attendibilità elevata** nei criteri di filtro del contenuto applicabili.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-128">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="e6aa0-129">Per impostazione predefinita, l'azione consiste nell'inviare il messaggio alla cartella posta inDesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-129">By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="e6aa0-130">Per ulteriori informazioni sulla configurazione dei criteri di filtro del contenuto, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-130">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="e6aa0-131">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e6aa0-131">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="e6aa0-132">Specificare le proprietà aggiuntive per la regola e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-132">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e6aa0-133">Per ulteriori informazioni sulle proprietà aggiuntive che è possibile selezionare o specificare per questa regola, vedere [utilizzo dell'interfaccia di amministrazione di Exchange per creare regole del flusso di posta](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="e6aa0-133">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e6aa0-134">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="e6aa0-134">How do you know this worked?</span></span>

<span data-ttu-id="e6aa0-135">Per verificare la corretta esecuzione di questa procedura, inviare un messaggio di posta elettronica a un utente all'interno dell'organizzazione e verificare che l'azione eseguita sul messaggio sia come previsto.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-135">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="e6aa0-136">Se ad esempio si **imposta il livello di probabilità di posta indesiderata (SCL)** per **ignorare il filtro posta**indesiderata, il messaggio dovrà essere inviato alla cartella posta in arrivo del destinatario specificato.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-136">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="e6aa0-137">Tuttavia, se si **imposta il livello di probabilità di posta indesiderata (SCL)** su **9**e l'azione di **protezione da posta** indesiderata elevata per i criteri di filtro del contenuto applicabile è quella di spostare il messaggio nella cartella posta indesiderata, il messaggio deve essere inviato al valore specificato. cartella posta inDesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e6aa0-137">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  

