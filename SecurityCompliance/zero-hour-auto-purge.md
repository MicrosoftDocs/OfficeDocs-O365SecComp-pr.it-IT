---
title: 'Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware'
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: Eliminazione automatica zero ore (ZAP) è una funzionalità di protezione posta elettronica in grado di rilevare i messaggi con la posta indesiderata o malware che sono già stati consegnati alla posta in arrivo degli utenti e quindi viene eseguito il rendering del contenuto dannoso dannosa. Come ZAP esegue questa operazione dipende dal tipo di contenuto dannoso rilevato.
ms.openlocfilehash: 1cf14051e91801a74a0d739c69900bb3f825b318
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180846"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="8724d-104">Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware</span><span class="sxs-lookup"><span data-stu-id="8724d-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="8724d-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8724d-105">Overview</span></span>

<span data-ttu-id="8724d-p102">Eliminazione automatica zero ore (ZAP) è una funzionalità di protezione posta elettronica in grado di rilevare i messaggi con per attività di phishing, posta indesiderata o malware che sono già stati consegnati alla posta in arrivo degli utenti e quindi viene eseguito il rendering del contenuto dannoso dannosa. Come ZAP esegue questa operazione dipende dal tipo di contenuto dannoso viene rilevato. posta può essere zapped a causa del contenuto della posta, gli URL o gli allegati.</span><span class="sxs-lookup"><span data-stu-id="8724d-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="8724d-108">ZAP è disponibile con l'impostazione predefinita, Exchange Online Protection incluso in qualsiasi sottoscrizione a Office 365 che contiene le cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8724d-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="8724d-109">ZAP è attivata per impostazione predefinita, ma devono essere soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8724d-109">ZAP is turned on by default, but the folowing conditions must be met:</span></span>
  
- <span data-ttu-id="8724d-110">**Azione posta indesiderata** è impostata su **spostare il messaggio nella cartella posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="8724d-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <br/><span data-ttu-id="8724d-111">È inoltre possibile creare un nuovo criterio di filtro posta indesiderata che si applica solo a un insieme di utenti se non si desidera che tutte le cassette postali per essere analizzata da ZAP.</span><span class="sxs-lookup"><span data-stu-id="8724d-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="8724d-p103">Gli utenti sono mantenuti valori predefiniti delle impostazioni della posta indesiderata e la protezione della posta elettronica indesiderata non sono disattivata. (Per informazioni dettagliate sulle opzioni utente in Outlook, vedere [modificare il livello di protezione di filtro per la posta indesiderata](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) ).</span><span class="sxs-lookup"><span data-stu-id="8724d-p103">Users have kept their default junk mail settings, and have not turned off junk email protection. (See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-does-zap-work"></a><span data-ttu-id="8724d-114">Funzionamento ZAP</span><span class="sxs-lookup"><span data-stu-id="8724d-114">How does ZAP work?</span></span>

<span data-ttu-id="8724d-p104">Aggiornamenti di Office 365 firme malware e motore di protezione da posta indesiderate in tempo reale a intervalli giornalieri. Gli utenti possono comunque dannoso messaggi vengano recapitati posta in arrivo per una serie di motivi, ad esempio se il contenuto è weaponized dopo il recapito agli utenti. ZAP evitare questo problema monitorando continuamente aggiornamenti per le firme di posta indesiderata e malware Office 365. ZAP possono individuare e rimuovere contenuti ai messaggi che sono già nella posta in arrivo degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8724d-p104">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures. ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span> 

- <span data-ttu-id="8724d-119">Per la posta identificata come posta indesiderata, ZAP Sposta i messaggi non letti nella cartella posta indesiderata degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8724d-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span> 

- <span data-ttu-id="8724d-120">Per la posta identificata come posta indesiderata, messaggi ZAP spostati nella cartella posta indesiderata degli utenti, indipendentemente dal fatto che il messaggio di posta elettronica è stato letto.</span><span class="sxs-lookup"><span data-stu-id="8724d-120">For mail that is identified as spam, ZAP moves messages to users' Junk mail folder, regardless of whether the email has been read.</span></span>

- <span data-ttu-id="8724d-121">Per appena rilevato malware, ZAP rimuove gli allegati di messaggi di posta elettronica, indipendentemente dal fatto che il messaggio di posta elettronica è stato letto.</span><span class="sxs-lookup"><span data-stu-id="8724d-121">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span> 
  
<span data-ttu-id="8724d-122">L'azione ZAP è semplice per l'utente della cassetta postale. essi non ricevere una notifica se un messaggio di posta elettronica viene spostato.</span><span class="sxs-lookup"><span data-stu-id="8724d-122">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span>
  
<span data-ttu-id="8724d-123">Consenti regole degli utenti finali, [regole del flusso di posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=722755)e gli elenchi o altri filtri hanno la precedenza su ZAP.</span><span class="sxs-lookup"><span data-stu-id="8724d-123">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="8724d-124">Per verificare o configurare un criterio di filtro posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="8724d-124">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="8724d-125">Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365.</span><span class="sxs-lookup"><span data-stu-id="8724d-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="8724d-126">In **gestione rischio**, scegliere la **protezione da posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="8724d-126">Under **Threat management**, choose **Anti-spam**.</span></span>

3. <span data-ttu-id="8724d-127">Esaminare le impostazioni standard.</span><span class="sxs-lookup"><span data-stu-id="8724d-127">Review the standard settings.</span></span> 

4. <span data-ttu-id="8724d-p105">Se si desidera personalizzare le impostazioni, fare clic sulla scheda **personalizzato** e attivare **le impostazioni personalizzate**. Modificare le impostazioni e se si desidera, sceglierne **+ Crea un criterio** per aggiungere un nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="8724d-p105">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**. Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span> 
    
## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="8724d-130">Per vedere se ZAP spostato il messaggio</span><span class="sxs-lookup"><span data-stu-id="8724d-130">To see if ZAP moved your message</span></span>

<span data-ttu-id="8724d-131">Se si desidera visualizzare se ZAP spostato il messaggio, è possibile utilizzare sia la [relazione sullo stato di protezione di rischio](view-email-security-reports.md#threat-protection-status-report-new) (o [Esplora rischio](use-explorer-in-security-and-compliance.md)).</span><span class="sxs-lookup"><span data-stu-id="8724d-131">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report-new) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>
    
## <a name="to-disable-zap"></a><span data-ttu-id="8724d-132">Per disabilitare ZAP</span><span class="sxs-lookup"><span data-stu-id="8724d-132">To disable ZAP</span></span>
  
<span data-ttu-id="8724d-133">Se si desidera disabilitare ZAP per il tenant di Office 365 o un insieme di utenti, utilizzare il parametro **ZapEnabled** del [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet EOP.</span><span class="sxs-lookup"><span data-stu-id="8724d-133">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
<span data-ttu-id="8724d-134">Nell'esempio seguente, ZAP è disabilitata per un criterio di filtro dei contenuti denominato "Test".</span><span class="sxs-lookup"><span data-stu-id="8724d-134">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="8724d-135">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="8724d-135">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="8724d-136">Cosa succede se un messaggio viene spostato nella cartella posta indesiderata?</span><span class="sxs-lookup"><span data-stu-id="8724d-136">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="8724d-p106">È consigliabile eseguire il normale processo di creazione di rapporti per falsi positivi. È l'unico motivo il messaggio verrà spostato dalla posta in arrivo nella cartella posta indesiderata in quanto il servizio ha rilevato che il messaggio era posta indesiderata o dannosi.</span><span class="sxs-lookup"><span data-stu-id="8724d-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="8724d-139">Se è possibile utilizzare alla quarantena di Office 365 anziché nella cartella posta indesiderata?</span><span class="sxs-lookup"><span data-stu-id="8724d-139">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="8724d-140">ZAP non vengono spostati i messaggi in quarantena dalla posta in arrivo in questa fase.</span><span class="sxs-lookup"><span data-stu-id="8724d-140">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="8724d-141">Se dispone di una regola di flusso di posta personalizzato (bloccare o consentire regola)?</span><span class="sxs-lookup"><span data-stu-id="8724d-141">What If I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="8724d-p107">Le regole create da admins (regole del flusso di posta elettronica) o Consenti e blocca regole hanno la precedenza. Tali messaggi vengono esclusi dai criteri di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8724d-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8724d-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8724d-144">Related Topics</span></span>

[<span data-ttu-id="8724d-145">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="8724d-145">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="8724d-146">Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi</span><span class="sxs-lookup"><span data-stu-id="8724d-146">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)
  

