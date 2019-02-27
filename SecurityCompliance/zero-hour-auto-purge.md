---
title: 'Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware'
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare i messaggi con posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi di eseguire il rendering del contenuto dannoso innocuo. La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato.
ms.openlocfilehash: 84d9c1dc12c3caf0630d25a3980cdaea1830a4c0
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295639"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="47548-104">Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware</span><span class="sxs-lookup"><span data-stu-id="47548-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="47548-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="47548-105">Overview</span></span>

<span data-ttu-id="47548-p102">Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare messaggi con phishing, posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi viene eseguito il rendering del contenuto dannoso innocuo. La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato. la posta può essere zapped a causa di contenuto, URL o allegati di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="47548-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="47548-108">ZAP è disponibile con la protezione Exchange Online predefinita inclusa con qualsiasi sottoscrizione di Office 365 che contiene cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="47548-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="47548-109">L'opzione ZAP è attivata per impostazione predefinita, ma devono essere soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47548-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="47548-110">**Azione di posta** indesiderata è impostata per **spostare il messaggio nella cartella posta**indesiderata.</span><span class="sxs-lookup"><span data-stu-id="47548-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <br/><span data-ttu-id="47548-111">È inoltre possibile creare un nuovo criterio di filtro per la posta indesiderata che si applica solo a un gruppo di utenti se non si desidera che tutte le cassette postali vengano schermate da ZAP.</span><span class="sxs-lookup"><span data-stu-id="47548-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="47548-p103">Gli utenti hanno mantenuto le impostazioni predefinite della posta indesiderata e non sono state disattivate la protezione della posta indesiderata. Per informazioni dettagliate sulle opzioni utente in Outlook, vedere [modificare il livello di protezione del filtro della posta](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) indesiderata.</span><span class="sxs-lookup"><span data-stu-id="47548-p103">Users have kept their default junk mail settings, and have not turned off junk email protection. (See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-does-zap-work"></a><span data-ttu-id="47548-114">Come funziona ZAP?</span><span class="sxs-lookup"><span data-stu-id="47548-114">How does ZAP work?</span></span>

<span data-ttu-id="47548-p104">Office 365 aggiorna le firme di malware e del motore di protezione da posta indesiderata in tempo reale su base giornaliera. Tuttavia, gli utenti possono comunque ottenere messaggi dannosi recapitati alle cassette postali per una serie di motivi, incluso se il contenuto è armato dopo essere stato recapitato agli utenti. ZAP risolve questo monitoraggio continuamente gli aggiornamenti alle firme di posta indesiderata e malware di Office 365. ZAP è in grado di trovare e rimuovere i messaggi precedentemente recapitati che sono già presenti nelle cassette postali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="47548-p104">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures. ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span> 

- <span data-ttu-id="47548-119">Per la posta elettronica identificata come posta indesiderata, ZAP sposta i messaggi non letti nella cartella posta inDesiderata degli utenti.</span><span class="sxs-lookup"><span data-stu-id="47548-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span> 

- <span data-ttu-id="47548-120">Per la posta elettronica identificata come posta indesiderata, ZAP sposta i messaggi nella cartella posta inDesiderata degli utenti, indipendentemente dal fatto che il messaggio di posta elettronica sia stato letto.</span><span class="sxs-lookup"><span data-stu-id="47548-120">For mail that is identified as spam, ZAP moves messages to users' Junk mail folder, regardless of whether the email has been read.</span></span>

- <span data-ttu-id="47548-121">Per il malware appena rilevato, ZAP rimuove gli allegati dai messaggi di posta elettronica, indipendentemente dal fatto che il messaggio di posta elettronica sia stato letto.</span><span class="sxs-lookup"><span data-stu-id="47548-121">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span> 
  
<span data-ttu-id="47548-122">L'azione ZAP è senza problemi per l'utente della cassetta postale; non vengono notificati se viene spostato un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="47548-122">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span>
  
<span data-ttu-id="47548-123">Gli elenchi Consenti, [le regole del flusso di posta](https://go.microsoft.com/fwlink/p/?LinkId=722755)e le regole degli utenti finali o i filtri aggiuntivi hanno la precedenza su Zap.</span><span class="sxs-lookup"><span data-stu-id="47548-123">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="47548-124">Per rivedere o configurare un criterio di filtro per la posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="47548-124">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="47548-125">Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365.</span><span class="sxs-lookup"><span data-stu-id="47548-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="47548-126">In **gestione minacce**scegliere **protezione da posta**indesiderata.</span><span class="sxs-lookup"><span data-stu-id="47548-126">Under **Threat management**, choose **Anti-spam**.</span></span>

3. <span data-ttu-id="47548-127">Esaminare le impostazioni standard.</span><span class="sxs-lookup"><span data-stu-id="47548-127">Review the standard settings.</span></span> 

4. <span data-ttu-id="47548-p105">Se si desidera personalizzare le impostazioni, selezionare la scheda **personalizzato** e abilitare **le impostazioni personalizzate**. Modificare le impostazioni e, se lo si desidera, fare clic su **+ Crea un criterio** per aggiungere un nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="47548-p105">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**. Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span> 
    
## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="47548-130">Per verificare se il messaggio è stato spostato da ZAP</span><span class="sxs-lookup"><span data-stu-id="47548-130">To see if ZAP moved your message</span></span>

<span data-ttu-id="47548-131">Se si vuole vedere se ZAP ha spostato il messaggio, è possibile utilizzare il [rapporto sullo stato di protezione di minacce](view-email-security-reports.md#threat-protection-status-report) (o [Esplora minacce](use-explorer-in-security-and-compliance.md)).</span><span class="sxs-lookup"><span data-stu-id="47548-131">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>
    
## <a name="to-disable-zap"></a><span data-ttu-id="47548-132">Per disabilitare ZAP</span><span class="sxs-lookup"><span data-stu-id="47548-132">To disable ZAP</span></span>
  
<span data-ttu-id="47548-133">Se si desidera disabilitare ZAP per il tenant di Office 365 o un gruppo di utenti, utilizzare il parametro **ZapEnabled** di [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet di EOP.</span><span class="sxs-lookup"><span data-stu-id="47548-133">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
<span data-ttu-id="47548-134">Nell'esempio seguente, ZAP è disabilitato per un criterio di filtro dei contenuti denominato "test".</span><span class="sxs-lookup"><span data-stu-id="47548-134">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="47548-135">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="47548-135">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="47548-136">Cosa succede se un messaggio legittimo viene spostato nella cartella posta indesiderata?</span><span class="sxs-lookup"><span data-stu-id="47548-136">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="47548-p106">È consigliabile seguire la procedura di creazione di report normale per i falsi positivi. L'unico motivo per il quale il messaggio verrebbe spostato dalla posta in arrivo alla cartella posta indesiderata sarebbe perché il servizio ha determinato che il messaggio era posta indesiderata o dannoso.</span><span class="sxs-lookup"><span data-stu-id="47548-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="47548-139">Che cosa fare se si utilizza la quarantena di Office 365 anziché la cartella posta indesiderata?</span><span class="sxs-lookup"><span data-stu-id="47548-139">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="47548-140">ZAP non sposta i messaggi in quarantena dalla posta in arrivo in questo momento.</span><span class="sxs-lookup"><span data-stu-id="47548-140">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="47548-141">Cosa succede se si dispone di una regola del flusso di posta personalizzata (blocco/Consenti regola)?</span><span class="sxs-lookup"><span data-stu-id="47548-141">What If I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="47548-p107">Le regole create dagli amministratori (regole del flusso di posta) o blocca e Consenti hanno la precedenza. Tali messaggi sono esclusi dai criteri di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="47548-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="47548-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="47548-144">Related Topics</span></span>

[<span data-ttu-id="47548-145">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="47548-145">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="47548-146">Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi</span><span class="sxs-lookup"><span data-stu-id="47548-146">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
  

