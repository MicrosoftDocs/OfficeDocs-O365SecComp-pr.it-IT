---
title: Utilizzare le regole di flusso di posta elettronica per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
description: È possibile creare una regola di trasporto che imposta il livello di probabilità di posta indesiderata (SCL) di un messaggio di posta elettronica. Il valore SCL è una misura di probabilmente come un messaggio di posta indesiderata. Posta indesiderata è messaggi di posta elettronica indesiderati (e in genere indesiderato). Deve agire diversi per un messaggio in base al relativo la posta indesiderata. Ad esempio, è possibile ignorare la posta indesiderata filtro del contenuto per i messaggi inviati da persone all'interno dell'organizzazione in quanto si considera attendibile che un messaggio inviato internamente da un collega non è la posta indesiderata. Utilizza le regole di trasporto per impostare il valore SCL di un messaggio offre maggiore controllo nella gestione della posta indesiderata.
ms.openlocfilehash: ad89230dac9de668488b40090d70d2b697a86edd
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026733"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="3220b-108">Utilizzare le regole di flusso di posta elettronica per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi</span><span class="sxs-lookup"><span data-stu-id="3220b-108">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="3220b-p102">È possibile creare una regola di trasporto che imposta il livello di probabilità di posta indesiderata (SCL) di un messaggio di posta elettronica. Il valore SCL è una misura di probabilmente come un messaggio di posta indesiderata. Posta indesiderata è messaggi di posta elettronica indesiderati (e in genere indesiderato). Deve agire diversi per un messaggio in base al relativo la posta indesiderata. Ad esempio, è possibile ignorare la posta indesiderata filtro del contenuto per i messaggi inviati da persone all'interno dell'organizzazione in quanto si considera attendibile che un messaggio inviato internamente da un collega non è la posta indesiderata. Utilizza le regole di trasporto per impostare il valore SCL di un messaggio offre maggiore controllo nella gestione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="3220b-p102">You can create a transport rule that sets the spam confidence level (SCL) of an email message. The SCL is a measure of how likely a message is to be spam. Spam is unsolicited (and typically unwanted) email messages. The service takes different action on a message depending on its SCL rating. For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam. Using transport rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="3220b-115">**Che cosa è necessario sapere prima di iniziare**</span><span class="sxs-lookup"><span data-stu-id="3220b-115">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="3220b-116">Tempo stimato per eseguire questa procedura: 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="3220b-116">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="3220b-p103">È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Regole di trasporto" in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) o [autorizzazioni funzionalità in EOP](eop/feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="3220b-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="3220b-119">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="3220b-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-transport-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="3220b-120">Per creare una regola di trasporto che imposta il valore SCL del messaggio</span><span class="sxs-lookup"><span data-stu-id="3220b-120">To create a transport rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="3220b-121">Nell'interfaccia di amministrazione di Exchange (EAC), scegliere **flusso di posta** \> **regole**.</span><span class="sxs-lookup"><span data-stu-id="3220b-121">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="3220b-122">Scegliere **New**![Aggiungi icona](media/ITPro-EAC-AddIcon.png), quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="3220b-122">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.png), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="3220b-123">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="3220b-123">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="3220b-124">Scegliere **altre opzioni**e quindi in **Applica questa regola se**, specificare una condizione che determinerà l'azione che verrà impostato per questa regola (che consiste nell'impostare il valore SCL).</span><span class="sxs-lookup"><span data-stu-id="3220b-124">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="3220b-125">Ad esempio, è possibile impostare **il mittente** \> **è interno/esterno**e quindi nella finestra di dialogo **Selezionare mittente percorso** selezionare **all'interno dell'organizzazione**e scegliere **ok**.</span><span class="sxs-lookup"><span data-stu-id="3220b-125">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span></br>
    <span data-ttu-id="3220b-126">![Seleziona la località del mittente](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="3220b-126">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="3220b-127">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="3220b-127">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="3220b-128">Nella finestra di dialogo **specificare SCL** selezionare uno dei valori seguenti e scegliere **ok**:</span><span class="sxs-lookup"><span data-stu-id="3220b-128">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="3220b-129">**Filtro posta indesiderata bypass** - questo imposta il valore SCL su -1, vale a dire che il filtro del contenuto non vengano eseguite.</span><span class="sxs-lookup"><span data-stu-id="3220b-129">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="3220b-130">**0-4** - quando si imposta il valore SCL su uno dei valori seguenti, il messaggio verrà passato lungo per il filtro contenuto per un'ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3220b-130">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="3220b-p104">**5, 6** - quando si imposta il valore SCL su uno dei valori seguenti, l'azione specificata per la **posta indesiderata** i criteri di filtro dei contenuti applicabile verranno applicate. Per impostazione predefinita, l'azione consiste nell'inviare il messaggio nella cartella posta indesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3220b-p104">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="3220b-p105">**7-9** - quando si imposta il valore SCL su uno dei valori seguenti, l'azione specificata per la **posta indesiderata confidenza elevata** i criteri di filtro dei contenuti applicabile verranno applicate. Per impostazione predefinita, l'azione consiste nell'inviare il messaggio nella cartella posta indesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3220b-p105">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="3220b-p106">Per ulteriori informazioni sulla configurazione dei criteri di filtro del contenuto, vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md). Per ulteriori informazioni sui valori SCL del servizio, vedere [Spam confidence levels](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3220b-p106">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="3220b-137">Specificare ulteriori proprietà per la regola e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3220b-137">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3220b-138">Per ulteriori informazioni sulle proprietà aggiuntive, è possibile selezionare o specificare per questa regola, vedere [utilizzare EAC per creare una regola di trasporto](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC).</span><span class="sxs-lookup"><span data-stu-id="3220b-138">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3220b-139">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="3220b-139">How do you know this worked?</span></span>

<span data-ttu-id="3220b-p107">Per verificare il corretto funzionamento di questa procedura, inviare un messaggio di posta elettronica a una persona interna all'organizzazione e verificare che l'azione eseguita quando il messaggio come previsto. Ad esempio, se si **Imposta il livello di probabilità di posta indesiderata (SCL)** per **il filtro posta indesiderata di Bypass**, quindi il messaggio deve essere inviato alla posta in arrivo del destinatario specificato. Tuttavia, se si **Imposta il livello di probabilità di posta indesiderata (SCL)** a **9**e l'azione **posta indesiderata confidenza elevata** per i criteri di filtro dei contenuti applicabile consiste nello spostare il messaggio nella cartella posta indesiderata, quindi il messaggio deve essere inviato all'oggetto specificato cartella posta indesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3220b-p107">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected. For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox. However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  

