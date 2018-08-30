---
title: Utilizzare le regole di trasporto per configurare il filtro di posta elettronica in blocco
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: È possibile impostare filtri contenuti a livello aziendale per la posta elettronica da posta indesiderata e blocco tramite i criteri di filtro contenuto posta indesiderata predefiniti. Estrarre configurare i criteri di filtro da posta indesiderata e Set-HostedContentFilterPolicy su come impostare i criteri di filtro dei contenuti.
ms.openlocfilehash: 8fa4ba619b55ae12207f36b7625acfaa9838e696
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002479"
---
# <a name="use-transport-rules-to-configure-bulk-email-filtering"></a><span data-ttu-id="40397-104">Utilizzare le regole di trasporto per configurare il filtro di posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="40397-104">Use transport rules to configure bulk email filtering</span></span>

<span data-ttu-id="40397-p102">È possibile impostare filtri contenuti a livello aziendale per la posta elettronica da posta indesiderata e blocco tramite i criteri di filtro contenuto posta indesiderata predefiniti. Vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md) e [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) su come impostare i criteri di filtro dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="40397-p102">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="40397-p103">Se si desidera altre opzioni per filtrare i messaggi in blocco, è possibile creare regole di trasporto di Exchange per cercare i modelli di testo o frasi domande presenti in messaggi di posta elettronica in blocco. Qualsiasi messaggio che include le seguenti caratteristiche verrà contrassegnato come posta indesiderata. Utilizzo di queste regole consentono di ridurre la quantità di posta elettronica in blocco che riceve l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40397-p103">If you want to more options to filter bulk messages, you can create Exchange Transport rules to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40397-110">Prima di creare le regole di trasporto descritte in questo argomento, è consigliabile leggere innanzitutto [Qual è la differenza tra posta indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md) e [i valori di massa reclamo livello](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="40397-110">Before creating the Transport rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="40397-p104">Le procedure seguenti messaggio è contrassegnato come posta indesiderata per l'intera organizzazione. Tuttavia, è possibile aggiungere un'altra condizione per queste regole si applicano solo a destinatari specifici dell'organizzazione. In questo modo, il posta elettronica in blocco aggressivo possono applicare le impostazioni del filtro per alcuni utenti altamente mirate, mentre il resto degli utenti (gli utenti che per la maggior parte ricevono il posta elettronica in blocco che vengono iscritti) non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="40397-p104">The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
### <a name="create-an-exchange-transport-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="40397-114">Creare una regola Trasporto Exchange per filtrare i messaggi di posta elettronica in blocco in base agli schemi di testo</span><span class="sxs-lookup"><span data-stu-id="40397-114">Create an Exchange Transport rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="40397-115">Nell'interfaccia di amministrazione di Exchange accedere a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="40397-115">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="40397-116">Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif), quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="40397-116">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="40397-117">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="40397-117">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="40397-p105">Fare clic su **altre opzioni**. In **Applica questa regola se**, selezionare **l'oggetto o nel corpo** \> **oggetto o nel corpo corrisponde a questi modelli di testo**.</span><span class="sxs-lookup"><span data-stu-id="40397-p105">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="40397-120">Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti espressioni regolari che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine:</span><span class="sxs-lookup"><span data-stu-id="40397-120">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
  - <span data-ttu-id="40397-121">Se non è possibile visualizzare il contenuto di questo messaggio di posta elettronica\,</span><span class="sxs-lookup"><span data-stu-id="40397-121">If you are unable to view the content of this email\, please</span></span>
    
  - <span data-ttu-id="40397-122">\\>(safe )?unsubscribe( here)?\\</a\\></span><span class="sxs-lookup"><span data-stu-id="40397-122">\\>(safe )?unsubscribe( here)?\\</a\\></span></span>
    
  - <span data-ttu-id="40397-123">Se non si desidera ricevere ulteriori comunicazioni di questo tipo\,</span><span class="sxs-lookup"><span data-stu-id="40397-123">If you do not wish to receive further communications like this\, please</span></span>
    
  - <span data-ttu-id="40397-p106">\\<img height\="?1"? width\="?1"? src\=.?http\://</span><span class="sxs-lookup"><span data-stu-id="40397-p106">\\<img height\="?1"? width\="?1"? src\=.?http\://</span></span>
    
  - <span data-ttu-id="40397-127">Per non ricevere più questi\s+messaggi di posta elettronica\:http\://</span><span class="sxs-lookup"><span data-stu-id="40397-127">To stop receiving these\s+emails\:http\://</span></span>
    
  - <span data-ttu-id="40397-128">Per annullare la sottoscrizione a \w+ (e\-?letter|e?-?mail|newsletter)</span><span class="sxs-lookup"><span data-stu-id="40397-128">To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)</span></span>
    
  - <span data-ttu-id="40397-129">no longer (wish )?(to )?(be sent|receive) \w+ email</span><span class="sxs-lookup"><span data-stu-id="40397-129">no longer (wish )?(to )?(be sent|receive) \w+ email</span></span>
    
  - <span data-ttu-id="40397-130">Se non è possibile visualizzare il contenuto di questo messaggio di posta elettronica\, fare clic qui</span><span class="sxs-lookup"><span data-stu-id="40397-130">If you are unable to view the content of this email\, please click here</span></span>
    
  - <span data-ttu-id="40397-131">Per essere sicuri di ricevere (your daily deals|our e-?mails)\, aggiungere</span><span class="sxs-lookup"><span data-stu-id="40397-131">To ensure you receive (your daily deals|our e-?mails)\, add</span></span>
    
  - <span data-ttu-id="40397-132">Se non si desidera più ricevere questi messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="40397-132">If you no longer wish to receive these emails</span></span>
    
  - <span data-ttu-id="40397-133">per modificare le (subscription preferences|preferences or unsubscribe)</span><span class="sxs-lookup"><span data-stu-id="40397-133">to change your (subscription preferences|preferences or unsubscribe)</span></span>
    
  - <span data-ttu-id="40397-134">fare clic (here to|the) annullare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="40397-134">click (here to|the) unsubscribe</span></span>
    
    <span data-ttu-id="40397-135">**Note**:</span><span class="sxs-lookup"><span data-stu-id="40397-135">**Notes**:</span></span>
    
  - <span data-ttu-id="40397-p107">Tale elenco non è un set completo di espressioni regolari di messaggi di posta elettronica in blocco, informazioni possono essere aggiunti o rimossi in base alle esigenze. È tuttavia un punto di partenza ottimale.</span><span class="sxs-lookup"><span data-stu-id="40397-p107">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
  - <span data-ttu-id="40397-p108">Cercare parole o modelli di testo nell'oggetto o gli altri campi dell'intestazione nel messaggio viene generato *dopo che* il messaggio è stato decodificato dal trasferimento di contenuto MIME codifica del metodo utilizzato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. È possibile utilizzare le condizioni o eccezioni per cercare il raw (in genere Base64) codificato i valori dell'oggetto o gli altri campi dell'intestazione nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="40397-p108">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="40397-140">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="40397-140">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="40397-141">Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="40397-141">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
    <span data-ttu-id="40397-p109">L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="40397-p109">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40397-145">Se l'azione configurato il messaggio di quarantena anziché di inviarlo alla cartella posta indesiderata i destinatari, verrà inviato il messaggio in quarantena amministratore come corrispondenza di una regola di trasporto e non sarà disponibile nella quarantena della posta indesiderata utente finale o tramite notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="40397-145">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a transport rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
    <span data-ttu-id="40397-146">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="40397-146">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="40397-147">Salvare la regola.</span><span class="sxs-lookup"><span data-stu-id="40397-147">Save the rule.</span></span>
    
### <a name="create-an-exchange-transport-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="40397-148">Creare una regola Trasporto Exchange per filtrare i messaggi di posta elettronica in blocco in base alle frasi</span><span class="sxs-lookup"><span data-stu-id="40397-148">Create an Exchange Transport rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="40397-149">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="40397-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="40397-150">Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif), quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="40397-150">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="40397-151">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="40397-151">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="40397-p110">Fare clic su **altre opzioni**. In **Applica questa regola se**, selezionare **l'oggetto o nel corpo** \> **oggetto o nel corpo include una di queste parole**.</span><span class="sxs-lookup"><span data-stu-id="40397-p110">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="40397-154">Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti frasi che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine:</span><span class="sxs-lookup"><span data-stu-id="40397-154">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
  - <span data-ttu-id="40397-155">per modificare le preferenze o annullare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="40397-155">to change your preferences or unsubscribe</span></span>
    
  - <span data-ttu-id="40397-156">Modificare le preferenze di posta elettronica o annullare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="40397-156">Modify email preferences or unsubscribe</span></span>
    
  - <span data-ttu-id="40397-157">Questo è un messaggio di posta elettronica promozionale</span><span class="sxs-lookup"><span data-stu-id="40397-157">This is a promotional email</span></span>
    
  - <span data-ttu-id="40397-158">Hai ricevuto questo messaggio di posta elettronica perché hai richiesto una sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="40397-158">You are receiving this email because you requested a subscription</span></span>
    
  - <span data-ttu-id="40397-159">fare clic qui per annullare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="40397-159">click here to unsubscribe</span></span>
    
  - <span data-ttu-id="40397-160">Hai ricevuto questo messaggio di posta elettronica perché hai effettuato la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="40397-160">You have received this email because you are subscribed</span></span>
    
  - <span data-ttu-id="40397-161">Se non si desidera più ricevere la nostra newsletter</span><span class="sxs-lookup"><span data-stu-id="40397-161">If you no longer wish to receive our email newsletter</span></span>
    
  - <span data-ttu-id="40397-162">per annullare la sottoscrizione a questa newsletter</span><span class="sxs-lookup"><span data-stu-id="40397-162">to unsubscribe from this newsletter</span></span>
    
  - <span data-ttu-id="40397-163">Se si verificano dei problemi nella visualizzazione di questo messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="40397-163">If you have trouble viewing this email</span></span>
    
  - <span data-ttu-id="40397-164">Questo è un annuncio pubblicitario</span><span class="sxs-lookup"><span data-stu-id="40397-164">This is an advertisement</span></span>
    
  - <span data-ttu-id="40397-165">si desidera annullare la sottoscrizione o modificare</span><span class="sxs-lookup"><span data-stu-id="40397-165">you would like to unsubscribe or change your</span></span>
    
  - <span data-ttu-id="40397-166">visualizzare questo messaggio di posta elettronica come pagina Web</span><span class="sxs-lookup"><span data-stu-id="40397-166">view this email as a webpage</span></span>
    
  - <span data-ttu-id="40397-167">Hai ricevuto questo messaggio di posta elettronica perché hai effettuato la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="40397-167">You are receiving this email because you are subscribed</span></span>
    
    <span data-ttu-id="40397-p111">**Nota**: ancora una volta, l'elenco non è un set completo di frasi di messaggi di posta elettronica in blocco, informazioni possono essere aggiunti o rimossi in base alle esigenze. È tuttavia un punto di partenza ottimale.</span><span class="sxs-lookup"><span data-stu-id="40397-p111">**Note**: Once again, this list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="40397-170">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="40397-170">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="40397-171">Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="40397-171">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
    <span data-ttu-id="40397-p112">L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="40397-p112">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40397-175">Se l'azione configurato il messaggio di quarantena anziché di inviarlo alla cartella posta indesiderata i destinatari, verrà inviato il messaggio in quarantena amministratore come corrispondenza di una regola di trasporto e non sarà disponibile nella quarantena della posta indesiderata utente finale o tramite notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="40397-175">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a transport rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
    <span data-ttu-id="40397-176">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="40397-176">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="40397-177">Salvare la regola.</span><span class="sxs-lookup"><span data-stu-id="40397-177">Save the rule.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="40397-178">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="40397-178">For more information</span></span>

[<span data-ttu-id="40397-179">Differenza tra posta elettronica indesiderata e posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="40397-179">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)
  
[<span data-ttu-id="40397-180">Valori al livello reclamo massa</span><span class="sxs-lookup"><span data-stu-id="40397-180">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)
  
[<span data-ttu-id="40397-181">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="40397-181">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="40397-182">Opzioni di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="40397-182">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
  

