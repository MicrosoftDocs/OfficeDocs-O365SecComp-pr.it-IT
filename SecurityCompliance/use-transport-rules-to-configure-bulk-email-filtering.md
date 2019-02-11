---
title: Utilizzare le regole di flusso di posta elettronica per configurare la posta elettronica in blocco il filtro in Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: Gli amministratori possono imparare a utilizzare le regole di flusso di posta in Exchange Online Protection per il filtro di posta elettronica in blocco.
ms.openlocfilehash: ce95872d3d80436dce4c62037caea9a5f735726d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "27382807"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="d1540-103">Utilizzare le regole di flusso di posta elettronica per configurare la posta elettronica in blocco il filtro in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d1540-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="d1540-p101">È possibile impostare filtri contenuti a livello aziendale per la posta elettronica da posta indesiderata e blocco tramite i criteri di filtro contenuto posta indesiderata predefiniti. Vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md) e [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) su come impostare i criteri di filtro dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="d1540-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="d1540-p102">Se si desidera altre opzioni per filtrare i messaggi in blocco, è possibile creare le regole di flusso di posta elettronica (noto anche come regole di trasporto) per cercare i modelli di testo o frasi domande presenti in messaggi di posta elettronica in blocco. Qualsiasi messaggio che include le seguenti caratteristiche verrà contrassegnato come posta indesiderata. Utilizzo di queste regole consentono di ridurre la quantità di posta elettronica in blocco che riceve l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1540-p102">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>
  
<span data-ttu-id="d1540-109">**Note**:</span><span class="sxs-lookup"><span data-stu-id="d1540-109">**Notes**:</span></span>

- <span data-ttu-id="d1540-110">Prima di creazione di regole di flusso della posta descritte in questo argomento, è consigliabile leggere innanzitutto [Qual è la differenza tra posta indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md) e [i valori di massa reclamo livello](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="d1540-110">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span> 
  
- <span data-ttu-id="d1540-p103">Le procedure seguenti messaggio è contrassegnato come posta indesiderata per l'intera organizzazione. Tuttavia, è possibile aggiungere un'altra condizione per queste regole si applicano solo a destinatari specifici dell'organizzazione. In questo modo, il posta elettronica in blocco aggressivo possono applicare le impostazioni del filtro per alcuni utenti altamente mirate, mentre il resto degli utenti (gli utenti che per la maggior parte ricevono il posta elettronica in blocco che vengono iscritti) non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="d1540-p103">The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
### <a name="create-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="d1540-114">Creare una regola del flusso di posta elettronica per filtrare i messaggi di posta elettronica in blocco in base agli schemi di testo</span><span class="sxs-lookup"><span data-stu-id="d1540-114">Create mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="d1540-115">Nell'interfaccia di amministrazione di Exchange accedere a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="d1540-115">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="d1540-116">Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif), quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="d1540-116">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="d1540-117">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="d1540-117">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="d1540-p104">Fare clic su **altre opzioni**. In **Applica questa regola se**, selezionare **l'oggetto o nel corpo** \> **oggetto o nel corpo corrisponde a questi modelli di testo**.</span><span class="sxs-lookup"><span data-stu-id="d1540-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="d1540-120">Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti espressioni regolari che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine:</span><span class="sxs-lookup"><span data-stu-id="d1540-120">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - <span data-ttu-id="d1540-121">Se non è possibile visualizzare il contenuto di questo messaggio di posta elettronica\,</span><span class="sxs-lookup"><span data-stu-id="d1540-121">If you are unable to view the content of this email\, please</span></span>
    
   - <span data-ttu-id="d1540-122">\\>(safe )?unsubscribe( here)?\\</a\\></span><span class="sxs-lookup"><span data-stu-id="d1540-122">\\>(safe )?unsubscribe( here)?\\</a\\></span></span>
    
   - <span data-ttu-id="d1540-123">Se non si desidera ricevere ulteriori comunicazioni di questo tipo\,</span><span class="sxs-lookup"><span data-stu-id="d1540-123">If you do not wish to receive further communications like this\, please</span></span>
    
   - <span data-ttu-id="d1540-p105">\\<img height\="?1"? width\="?1"? src\=.?http\://</span><span class="sxs-lookup"><span data-stu-id="d1540-p105">\\<img height\="?1"? width\="?1"? src\=.?http\://</span></span>
    
   - <span data-ttu-id="d1540-127">Per non ricevere più questi\s+messaggi di posta elettronica\:http\://</span><span class="sxs-lookup"><span data-stu-id="d1540-127">To stop receiving these\s+emails\:http\://</span></span>
    
   - <span data-ttu-id="d1540-128">Per annullare la sottoscrizione a \w+ (e\-?letter|e?-?mail|newsletter)</span><span class="sxs-lookup"><span data-stu-id="d1540-128">To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)</span></span>
    
   - <span data-ttu-id="d1540-129">no longer (wish )?(to )?(be sent|receive) \w+ email</span><span class="sxs-lookup"><span data-stu-id="d1540-129">no longer (wish )?(to )?(be sent|receive) \w+ email</span></span>
    
   - <span data-ttu-id="d1540-130">Se non è possibile visualizzare il contenuto di questo messaggio di posta elettronica\, fare clic qui</span><span class="sxs-lookup"><span data-stu-id="d1540-130">If you are unable to view the content of this email\, please click here</span></span>
    
   - <span data-ttu-id="d1540-131">Per essere sicuri di ricevere (your daily deals|our e-?mails)\, aggiungere</span><span class="sxs-lookup"><span data-stu-id="d1540-131">To ensure you receive (your daily deals|our e-?mails)\, add</span></span>
    
   - <span data-ttu-id="d1540-132">Se non si desidera più ricevere questi messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d1540-132">If you no longer wish to receive these emails</span></span>
    
   - <span data-ttu-id="d1540-133">per modificare le (subscription preferences|preferences or unsubscribe)</span><span class="sxs-lookup"><span data-stu-id="d1540-133">to change your (subscription preferences|preferences or unsubscribe)</span></span>
    
   - <span data-ttu-id="d1540-134">fare clic (here to|the) annullare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="d1540-134">click (here to|the) unsubscribe</span></span>
    
   <span data-ttu-id="d1540-135">**Note**:</span><span class="sxs-lookup"><span data-stu-id="d1540-135">**Notes**:</span></span>

   - <span data-ttu-id="d1540-p106">Tale elenco non è un set completo di espressioni regolari di messaggi di posta elettronica in blocco, informazioni possono essere aggiunti o rimossi in base alle esigenze. È tuttavia un punto di partenza ottimale.</span><span class="sxs-lookup"><span data-stu-id="d1540-p106">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
   - <span data-ttu-id="d1540-p107">Cercare parole o modelli di testo nell'oggetto o gli altri campi dell'intestazione nel messaggio viene generato *dopo che* il messaggio è stato decodificato dal trasferimento di contenuto MIME codifica del metodo utilizzato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. È possibile utilizzare le condizioni o eccezioni per cercare il raw (in genere Base64) codificato i valori dell'oggetto o gli altri campi dell'intestazione nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d1540-p107">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="d1540-140">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="d1540-140">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="d1540-141">Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1540-141">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="d1540-p108">L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d1540-p108">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d1540-145">Se l'azione configurato il messaggio di quarantena anziché di inviarlo alla cartella posta indesiderata i destinatari, il messaggio verrà inviato per la quarantena amministratore come la corrispondenza di una regola di flusso di posta elettronica e non sarà disponibile nella quarantena della posta indesiderata utente finale o tramite per l'utente finale notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d1540-145">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="d1540-146">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d1540-146">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="d1540-147">Salvare la regola.</span><span class="sxs-lookup"><span data-stu-id="d1540-147">Save the rule.</span></span>
    
### <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="d1540-148">Creare una regola del flusso di posta elettronica per filtrare i messaggi di posta elettronica in blocco in base alle frasi</span><span class="sxs-lookup"><span data-stu-id="d1540-148">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="d1540-149">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="d1540-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="d1540-150">Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif), quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="d1540-150">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="d1540-151">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="d1540-151">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="d1540-p109">Fare clic su **altre opzioni**. In **Applica questa regola se**, selezionare **l'oggetto o nel corpo** \> **oggetto o nel corpo include una di queste parole**.</span><span class="sxs-lookup"><span data-stu-id="d1540-p109">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="d1540-154">Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti frasi che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine:</span><span class="sxs-lookup"><span data-stu-id="d1540-154">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - <span data-ttu-id="d1540-155">per modificare le preferenze o annullare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="d1540-155">to change your preferences or unsubscribe</span></span>
    
   - <span data-ttu-id="d1540-156">Modificare le preferenze di posta elettronica o annullare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="d1540-156">Modify email preferences or unsubscribe</span></span>
    
   - <span data-ttu-id="d1540-157">Questo è un messaggio di posta elettronica promozionale</span><span class="sxs-lookup"><span data-stu-id="d1540-157">This is a promotional email</span></span>
    
   - <span data-ttu-id="d1540-158">Hai ricevuto questo messaggio di posta elettronica perché hai richiesto una sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="d1540-158">You are receiving this email because you requested a subscription</span></span>
    
   - <span data-ttu-id="d1540-159">fare clic qui per annullare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="d1540-159">click here to unsubscribe</span></span>
    
   - <span data-ttu-id="d1540-160">Hai ricevuto questo messaggio di posta elettronica perché hai effettuato la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="d1540-160">You have received this email because you are subscribed</span></span>
    
   - <span data-ttu-id="d1540-161">Se non si desidera più ricevere la nostra newsletter</span><span class="sxs-lookup"><span data-stu-id="d1540-161">If you no longer wish to receive our email newsletter</span></span>
    
   - <span data-ttu-id="d1540-162">per annullare la sottoscrizione a questa newsletter</span><span class="sxs-lookup"><span data-stu-id="d1540-162">to unsubscribe from this newsletter</span></span>
    
   - <span data-ttu-id="d1540-163">Se si verificano dei problemi nella visualizzazione di questo messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d1540-163">If you have trouble viewing this email</span></span>
    
   - <span data-ttu-id="d1540-164">Questo è un annuncio pubblicitario</span><span class="sxs-lookup"><span data-stu-id="d1540-164">This is an advertisement</span></span>
    
   - <span data-ttu-id="d1540-165">si desidera annullare la sottoscrizione o modificare</span><span class="sxs-lookup"><span data-stu-id="d1540-165">you would like to unsubscribe or change your</span></span>
    
   - <span data-ttu-id="d1540-166">visualizzare questo messaggio di posta elettronica come pagina Web</span><span class="sxs-lookup"><span data-stu-id="d1540-166">view this email as a webpage</span></span>
    
   - <span data-ttu-id="d1540-167">Hai ricevuto questo messaggio di posta elettronica perché hai effettuato la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="d1540-167">You are receiving this email because you are subscribed</span></span>
    
   <span data-ttu-id="d1540-p110">**Nota**: ancora una volta, l'elenco non è un set completo di frasi di messaggi di posta elettronica in blocco, informazioni possono essere aggiunti o rimossi in base alle esigenze. È tuttavia un punto di partenza ottimale.</span><span class="sxs-lookup"><span data-stu-id="d1540-p110">**Note**: Once again, this list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="d1540-170">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="d1540-170">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="d1540-171">Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1540-171">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="d1540-p111">L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d1540-p111">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d1540-175">Se l'azione configurato il messaggio di quarantena anziché di inviarlo alla cartella posta indesiderata i destinatari, il messaggio verrà inviato per la quarantena amministratore come la corrispondenza di una regola di flusso di posta elettronica e non sarà disponibile nella quarantena della posta indesiderata utente finale o tramite per l'utente finale notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d1540-175">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="d1540-176">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d1540-176">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="d1540-177">Salvare la regola.</span><span class="sxs-lookup"><span data-stu-id="d1540-177">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d1540-178">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="d1540-178">For more information</span></span>

[<span data-ttu-id="d1540-179">Differenza tra posta elettronica indesiderata e posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="d1540-179">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="d1540-180">Valori al livello reclamo massa</span><span class="sxs-lookup"><span data-stu-id="d1540-180">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="d1540-181">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="d1540-181">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="d1540-182">Opzioni di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="d1540-182">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
