---
title: Utilizzare le regole del flusso di posta per configurare il filtro della posta elettronica in blocco in Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: Gli amministratori possono scoprire come utilizzare le regole del flusso di posta in Exchange Online Protection per il filtro della posta elettronica in blocco.
ms.openlocfilehash: d308439b5c26569f85eb62ddee6f01786d2998b9
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123917"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="23a8d-103">Utilizzare le regole del flusso di posta per configurare il filtro della posta elettronica in blocco in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="23a8d-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="23a8d-p101">È possibile impostare filtri di contenuto a livello aziendale per la posta indesiderata e i messaggi in blocco utilizzando i criteri di filtro contenuto spam predefiniti. Vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md) indesiderata e [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) su come impostare i criteri di filtro dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="23a8d-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="23a8d-p102">Se si desiderano ulteriori opzioni per filtrare i messaggi in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nei messaggi di posta elettronica in blocco. Tutti i messaggi che contengono queste caratteristiche verranno contrassegnati come posta indesiderata. L'utilizzo di queste regole può contribuire a ridurre la quantità di messaggi di posta elettronica indesiderata ricevuti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23a8d-p102">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23a8d-109">Prima di creare le regole del flusso di posta documentate questo argomento, si consiglia di leggere innanzitutto [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md) e [valori a livello](bulk-complaint-level-values.md)di reclamo in blocco.</span><span class="sxs-lookup"><span data-stu-id="23a8d-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br><span data-ttu-id="23a8d-p103">Le procedure seguenti contrassegnano un messaggio come posta indesiderata per l'intera organizzazione. Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole solo a destinatari specifici dell'organizzazione. In questo modo, le impostazioni di filtro della posta elettronica in blocco aggressive possono essere applicate a pochi utenti fortemente mirati, mentre gli altri utenti (che per lo più ricevono la posta elettronica di massa a cui hanno effettuato l'iscrizione) non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="23a8d-p103"> The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="23a8d-113">Creare una regola del flusso di posta per filtrare i messaggi di posta elettronica in blocco in base ai modelli di testo</span><span class="sxs-lookup"><span data-stu-id="23a8d-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="23a8d-114">Nell'interfaccia di amministrazione di Exchange accedere a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="23a8d-115">Fare \*\*\*\* ![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-115">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="23a8d-116">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="23a8d-116">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="23a8d-p104">Fare clic su **altre opzioni**. In **applica la regola se**, selezionare **l'** \> oggetto o il corpo o l'oggetto corpo **corrisponde a questi modelli di testo**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="23a8d-119">Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti espressioni regolari che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine:</span><span class="sxs-lookup"><span data-stu-id="23a8d-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   <span data-ttu-id="23a8d-p105">L'elenco di cui sopra non è un insieme esaustivo di espressioni regolari presenti nei messaggi di posta elettronica in blocco; Altre informazioni possono essere aggiunte o rimosse in base alle esigenze. Tuttavia, è un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="23a8d-p105">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span><br><span data-ttu-id="23a8d-p106">La ricerca di parole o di modelli di testo nell'oggetto o in altri campi di intestazione del messaggio si verifica *dopo* la decodifica del messaggio dal metodo MIME Content Transfer Encoding utilizzato per la trasmissione del messaggio binario tra i server SMTP in testo ASCII. Non è possibile utilizzare le condizioni o le eccezioni per cercare i valori non elaborati (in genere, Base64) codificati dell'oggetto o di altri campi di intestazione nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="23a8d-p106">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="23a8d-124">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="23a8d-125">Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="23a8d-p107">L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="23a8d-p107">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="23a8d-129">Se l'azione configurata è quella di mettere in quarantena il messaggio anziché inviarlo alla cartella posta inDesiderata dei destinatari, il messaggio verrà inviato alla quarantena dell'amministratore come corrispondenza della regola del flusso di posta e non sarà disponibile nella quarantena della posta indesiderata dell'utente finale o tramite l'utente finale. notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="23a8d-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="23a8d-130">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="23a8d-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="23a8d-131">Salvare la regola.</span><span class="sxs-lookup"><span data-stu-id="23a8d-131">Save the rule.</span></span>
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="23a8d-132">Creare una regola del flusso di posta per filtrare i messaggi di posta elettronica in blocco in base alle frasi</span><span class="sxs-lookup"><span data-stu-id="23a8d-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="23a8d-133">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="23a8d-134">Fare \*\*\*\* ![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-134">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="23a8d-135">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="23a8d-135">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="23a8d-p108">Fare clic su **altre opzioni**. In **applica la regola se**, selezionare **l'** \> oggetto o il corpo del soggetto o **del corpo include una o più delle seguenti parole**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-p108">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="23a8d-138">Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti frasi che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine:</span><span class="sxs-lookup"><span data-stu-id="23a8d-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   <span data-ttu-id="23a8d-p109">Questo elenco non è un insieme esaustivo di frasi trovate nei messaggi di posta elettronica in blocco; Altre informazioni possono essere aggiunte o rimosse in base alle esigenze. Tuttavia, è un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="23a8d-p109">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="23a8d-141">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="23a8d-142">Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="23a8d-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="23a8d-p110">L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="23a8d-p110">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="23a8d-146">Se l'azione configurata è quella di mettere in quarantena il messaggio anziché inviarlo alla cartella posta inDesiderata dei destinatari, il messaggio verrà inviato alla quarantena dell'amministratore come corrispondenza della regola del flusso di posta e non sarà disponibile nella quarantena della posta indesiderata dell'utente finale o tramite l'utente finale. notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="23a8d-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="23a8d-147">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="23a8d-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="23a8d-148">Salvare la regola.</span><span class="sxs-lookup"><span data-stu-id="23a8d-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="23a8d-149">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="23a8d-149">For more information</span></span>

[<span data-ttu-id="23a8d-150">Differenza tra posta elettronica indesiderata e posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="23a8d-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="23a8d-151">Valori di livello di reclamo in blocco</span><span class="sxs-lookup"><span data-stu-id="23a8d-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="23a8d-152">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="23a8d-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="23a8d-153">Opzioni di filtro della posta indesiderata avanzate</span><span class="sxs-lookup"><span data-stu-id="23a8d-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
