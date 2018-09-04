---
title: Protezione dalla posta indesiderata in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: Informazioni sulle impostazioni di protezione da posta indesiderate e i filtri che sono contenute informazioni utili che impedire la posta indesiderata in Exchange Online e Office 365. Ricevere troppo posta indesiderata in Office 365? È possibile personalizzare il filtro da posta indesiderata e le impostazioni di criteri di protezione da posta indesiderata.
ms.openlocfilehash: 5547904633a0be9ad57fa7431aeddf1267871662
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530833"
---
# <a name="office-365-email-anti-spam-protection"></a><span data-ttu-id="ce14d-105">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="ce14d-105">Office 365 email anti-spam protection</span></span>

<span data-ttu-id="ce14d-p102">Si desidera evitare troppo posta indesiderata in Office 365? È stata incorporata più filtri posta indesiderata nel servizio Office 365 o Exchange Online Protection (EOP) in modo che la posta elettronica è protetta dal momento in cui che viene visualizzato il primo messaggio. Per evitare la posta indesiderata in Office 365, è possibile modificare un'impostazione di protezione di gestione di un problema specifico all'interno dell'organizzazione, ad esempio si ricevono una quantità elevata di posta indesiderata da un mittente specifico, ad esempio, o in semplicemente fine regolare le impostazioni in modo che siano personalizzati per più adatte alle esigenze dell'organizzazione. A tale scopo, è possibile modificare le impostazioni di protezione da posta indesiderate in Office 365 Security &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="ce14d-p102">Are you concerned about too much spam in Office 365? We've built multiple spam filters into your Office 365 or Exchange Online Protection (EOP) service, so your email is protected from the moment you receive your first message. In order to help prevent spam in Office 365, you may want to change a protection setting to deal with a specific issue in your organization—say you're receiving a lot of spam from a particular sender, for example—or to simply fine tune your settings so that they're tailored to best meet the needs of your organization. To do this, you can change anti-spam settings in the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="ce14d-p103">In questo articolo è destinato agli amministratori di Office 365. Se non si è un amministratore, ma si è un utente di Office 365 e che desiderano apprendere le modalità di gestione con la posta indesiderata che viene visualizzato, questo non è l'articolo che si sta cercando. Al contrario, se si utilizza Outlook per PC o Outlook per Mac, Usa [Panoramica del filtro per la posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Se si utilizza Outlook sul web, iniziare con [informazioni sulla posta indesiderata e phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).</span><span class="sxs-lookup"><span data-stu-id="ce14d-p103">This article is intended for Office 365 administrators. If you're not an administrator, but you are an Office 365 user and you want to learn how to deal with spam you receive, this isn't the article you're looking for. Instead, if you use Outlook for PC or Outlook for Mac, start with [Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). If you use Outlook on the web, start with [Learn about junk email and phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).</span></span>
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a><span data-ttu-id="ce14d-114">Queste opzioni consentono di evitare la posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="ce14d-114">These options help you prevent spam in Office 365</span></span>

 <span data-ttu-id="ce14d-p104">**Filtro connessioni.** Quando si utilizzano il filtro connessioni, Office 365 controlla la reputazione del mittente prima di consentire un messaggio di ottenere tramite. È possibile creare un elenco Consenti o un elenco dei mittenti attendibili, per assicurarsi che ogni messaggio viene inviato da un indirizzo IP specifico o un intervallo di indirizzi IP. È inoltre possibile creare un elenco di indirizzi IP da utilizzare per bloccare i messaggi, viene chiamati un elenco di blocco. Per ulteriori informazioni, vedere [Configure Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). Se si è interessati sulla posta indesiderata in Office 365, utilizzare il filtro connessioni per evitare la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ce14d-p104">**Connection filtering.** When you use connection filtering, Office 365 checks the reputation of the sender before allowing a message to get through. You can create an allow list, or safe sender list, to make sure you receive every message sent to you from a specific IP address or IP address range. You can also create a list of IP addresses from which to block messages, called a block list. For more information, see [Configure the Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). If you're concerned about spam in Office 365, use connection filtering to help prevent spam.</span></span>
  
<span data-ttu-id="ce14d-p105">Per i clienti che dispongono di Office 365 Enterprise E5 o hanno acquistato licenze avanzate Threat Protection (degli strumenti di analisi), il filtro connessioni viene utilizzato per business intelligence di spoofing per creare elenchi di mittenti attendibili che sono lo spoofing del dominio Consenti e blocca. Per ulteriori informazioni, vedere [riferimento alle informazioni sulla business intelligence di spoofing](https://go.microsoft.com/fwlink/?LinkID=735009).</span><span class="sxs-lookup"><span data-stu-id="ce14d-p105">For customers who have Office 365 Enterprise E5 or have purchased Advanced Threat Protection (ATP) licenses, connection filtering is used by spoof intelligence to create allow and block lists of senders who are spoofing your domain. For more information, see [Learn more about spoof intelligence](https://go.microsoft.com/fwlink/?LinkID=735009).</span></span>
  
 <span data-ttu-id="ce14d-p106">**Filtro posta indesiderata.** Office 365 controlla delle caratteristiche del messaggio coerente con la posta indesiderata tramite il filtro posta indesiderata. È possibile modificare le azioni per eseguire sui messaggi identificati come posta indesiderata e scegliere se si desidera filtrare i messaggi scritti in determinate lingue o inviati da determinati paesi o aree. È inoltre possibile attivare avanzate per posta indesiderata opzioni di filtro se si desidera utilizzare un approccio aggressivo filtro posta indesiderata. Inoltre, è possibile configurare le notifiche di posta indesiderata dell'utente finale per informare gli utenti quando i messaggi destinati a loro sono stati messi in quarantena invece. (L'invio di messaggi in quarantena è una delle operazioni configurabile). Queste notifiche agli utenti finali possono rilasciare falsi positivi e segnalarli a Microsoft per l'analisi. Per ulteriori informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=617147). Per contribuire a evitare la posta indesiderata in Office 365, utilizzare la posta indesiderata, se si è preoccupati troppo posta indesiderata in Office 365, utilizzare il filtro connessioni per evitare la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ce14d-p106">**Spam filtering.** Office 365 checks for message characteristics consistent with spam by using spam filtering. You can change what actions to take on messages identified as spam, and choose whether to filter messages written in specific languages, or sent from specific countries or regions. You can also turn on advanced spam filtering options if you want to pursue an aggressive approach to spam filtering. Additionally, you can configure end-user spam notifications to inform users when messages intended for them were sent to the quarantine instead. (Sending messages to the quarantine is one of the configurable actions.) From these notifications, end users can release false positives and report them to Microsoft for analysis. For more information, see [Configure your spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147). In order to help prevent spam in Office 365, use spam filtering, if you're concerned about too much spam in Office 365, use connection filtering to help prevent spam.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce14d-p107">Per i clienti EOP autonomo: per impostazione predefinita, il filtro da posta indesiderata EOP invia messaggi di rilevamento posta indesiderata nella cartella posta indesiderata di ogni destinatario. Tuttavia, per assicurare che l'azione **Sposta il messaggio nella cartella posta indesiderata** funzionino con cassette postali locali, è necessario configurare due regole di trasporto di Exchange sui server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [verificare che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce14d-p107">For EOP standalone customers: By default, the EOP spam filters send spam-detected messages to each recipients' Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx).</span></span> 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a><span data-ttu-id="ce14d-134">Informazioni aggiuntive se vengono visualizzati troppo posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="ce14d-134">Extra information if you receive too much spam in Office 365</span></span>

<span data-ttu-id="ce14d-135">Nel seguente video viene fornita una panoramica della configurazione della posta indesiderata in EOP.</span><span class="sxs-lookup"><span data-stu-id="ce14d-135">The following video provides an overview of configuring spam filtering in EOP.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
<span data-ttu-id="ce14d-136">Per ulteriori informazioni, vedere l'argomento [Configure criteri di filtro della posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=617147) .</span><span class="sxs-lookup"><span data-stu-id="ce14d-136">For more details, see the [Configure spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147) topic.</span></span> 
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a><span data-ttu-id="ce14d-137">Controllare i messaggi in uscita per evitare la posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="ce14d-137">Check your outgoing messages to prevent spam in Office 365</span></span>

 <span data-ttu-id="ce14d-p108">**Un filtro in uscita.** Office 365 consente inoltre di verificare che gli utenti non inviino posta indesiderata. Ad esempio computer dell'utente può ottenere contenere malware che ne determina la inviare messaggi di posta indesiderata, in modo creiamo difesa contro che ha chiamato *un filtro in uscita* . Non è possibile disattivare il filtro in uscita, ma è possibile configurare le impostazioni descritte in [configurare i criteri di posta indesiderata in uscita](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). Se si è preoccupati troppo posta indesiderata in Office 365, utilizzare il filtro in uscita per evitare la posta indesiderata in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ce14d-p108">**Outbound filtering.** Office 365 also checks to make sure that your users don't send spam. For instance, a user's computer may get infected with malware that causes it to send spam messages, so we build protection against that called  *outbound filtering*  . You can't turn off outbound filtering, but you can configure the settings described in [Configure the outbound spam policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). If you're concerned about too much spam in Office 365, use outbound filtering to help prevent spam in Exchange Online.</span></span>
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a><span data-ttu-id="ce14d-143">Oltre a informazioni di base: ulteriori modi per evitare la posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="ce14d-143">Beyond the basics: More ways to prevent spam in Office 365</span></span>
<span data-ttu-id="ce14d-144"><a name="BeyondBasics"> </a></span><span class="sxs-lookup"><span data-stu-id="ce14d-144"></span></span>

 <span data-ttu-id="ce14d-p109">**Regole del flusso di posta.** Se si desidera andare oltre il filtro posta indesiderata integrato e creare regole personalizzate che si basano sui criteri aziendali, le *[regole del flusso di posta elettronica](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)* , denominati anche *le regole di trasporto* , sono un altro filtro che consentono di evitare la posta indesiderata in Office 365. Ad esempio, è possibile utilizzare le regole di flusso di posta elettronica per impostare il valore di (SCL) livello spam confidence per i messaggi che soddisfano le condizioni specifiche, come descritto in [utilizzare le regole di flusso di posta elettronica per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce14d-p109">**Mail flow rules.** If you want to go beyond built-in spam filtering and create custom rules that are based on your business policies,  *[mail flow rules](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*  , also called  *transport rules*  , are another filter that help you prevent spam in Office 365. For example, you can use mail flow rules to set the spam confidence level (SCL) value for messages that match specific conditions, as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx).</span></span> 
  
 <span data-ttu-id="ce14d-p110">**L'autenticazione di posta elettronica.** Le tecniche che utilizzano il sistema DNS (Domain Name) per aggiungere informazioni verificabili a messaggi di posta elettronica relative al mittente di un messaggio di posta elettronica vengono chiamate l'autenticazione di posta elettronica. Gli amministratori possono rendere più avanzate di Office 365 utilizzare questi metodi di autenticazione di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="ce14d-p110">**Email authentication.** Techniques that use the Domain Name System (DNS) to add verifiable information to email messages about the sender of an email message are called email authentication. More advanced Office 365 admins can make use of these email authentication methods:</span></span> 
  
- <span data-ttu-id="ce14d-p111">**Sender Policy Framework (SPF).** SPF consente di convalidare l'origine dei messaggi di posta elettronica per verificare l'indirizzo IP del mittente per il proprietario presunto del dominio di invio. Per una breve introduzione a SPF e per ottenere una configurazione rapidamente, vedere [impostare SPF in Office 365 per evitare attacchi di spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Per una più approfondita dei come Office 365 utilizza SPF o per le distribuzioni di risoluzione dei problemi o non standard, ad esempio le distribuzioni ibride, iniziare con [la modalità di Office 365 utilizza mittente Policy Framework (SPF) per impedire attacchi di spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce14d-p111">**Sender Policy Framework (SPF).** SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain. For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="ce14d-p112">**DomainKeys identificato posta (DKIM).** DKIM consente di collegare una firma digitale a messaggi di posta elettronica nell'intestazione del messaggio di posta elettronica da inviare. Sistemi di posta elettronica ricevano della posta elettronica dal dominio utilizzano la firma digitale per determinare se posta elettronica in arrivo che ricevono è valido. Per informazioni su DKIM e Office 365, vedere [Utilizzo DKIM per convalidare la posta elettronica inviata dal dominio in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce14d-p112">**DomainKeys Identified Mail (DKIM).** DKIM lets you attach a digital signature to email messages in the message header of emails you send. Email systems that receive email from your domain use this digital signature to determine if incoming email that they receive is legitimate. For information about DKIM and Office 365, see [Use DKIM to validate outbound email sent from your domain in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="ce14d-p113">**Autenticazione dei messaggi basati sul dominio, Reporting e conformità (DMARC).** Vengono fornite informazioni utili DMARC la ricezione di sistemi di posta elettronica determinano cosa fare con messaggi di errore verifiche SPF o DKIM e fornendo un altro livello di attendibilità per i partner di posta elettronica. Per informazioni sull'impostazione DMARC, vedere [Utilizzo DMARC per convalidare la posta elettronica in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce14d-p113">**Domain-based Message Authentication, Reporting, and Conformance (DMARC).** DMARC helps receiving mail systems determine what to do with messages that fail SPF or DKIM checks and provides another level of trust for your email partners. For information on setting up DMARC, see [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>
    
<span data-ttu-id="ce14d-162">Se si è interessati su posta indesiderata, phishing e spoofing in Office 365, utilizzare SPF, DKIM e DMARC insieme al fine di evitare la posta indesiderata e lo spoofing indesiderati.</span><span class="sxs-lookup"><span data-stu-id="ce14d-162">If you're concerned about spam, phishing, and spoofing in Office 365, use SPF, DKIM, and DMARC together to help prevent spam and unwanted spoofing.</span></span>
  
 <span data-ttu-id="ce14d-p114">**Impostazioni gestito per l'utente finale.** Si sta cercando informazioni su come gli utenti finali possono gestire le proprie impostazioni della posta indesiderata, vedere [Panoramica del filtro per la posta indesiderata](https://go.microsoft.com/fwlink/?LinkId=270065) (per gli utenti di Microsoft Outlook) o [fare riferimento alle informazioni sulla posta indesiderata e phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (per Outlook sugli utenti web). Se si sta utilizzando EOP per proteggere le cassette postali locali, assicurarsi di utilizzare la sincronizzazione delle directory per assicurarsi che queste impostazioni vengono sincronizzate con il servizio. Per ulteriori informazioni sull'impostazione di sincronizzazione della directory, vedere "Utilizzare la sincronizzazione delle directory per gestire gli utenti di posta" in [Gestione utenti di posta in EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce14d-p114">**End-user managed settings.** If you're looking for information about how end users can manage their own spam settings, check out [Overview of the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=270065) (for Microsoft Outlook users) or [Learn about Junk email and phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (for Outlook on the web users). If you're using EOP to protect on-premises mailboxes, be sure to use directory synchronization to ensure that these settings are synced to the service. For more information about setting up directory synchronization, see "Use directory synchronization to manage mail users" in [Manage mail users in EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="ce14d-167">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ce14d-167">For more information</span></span>
<span data-ttu-id="ce14d-168"><a name="BeyondBasics"> </a></span><span class="sxs-lookup"><span data-stu-id="ce14d-168"></span></span>

[<span data-ttu-id="ce14d-169">Blog: Perché di posta indesiderata e phishing visualizzato tramite Office 365?</span><span class="sxs-lookup"><span data-stu-id="ce14d-169">Blog: Why does spam and phishing get through Office 365?</span></span>](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[<span data-ttu-id="ce14d-170">Domande frequenti sulla protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ce14d-170">Anti-Spam Protection FAQ</span></span>](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="ce14d-171">Evitare che la posta elettronica venga erroneamente contrassegnata come posta indesiderata tramite un elenco di indirizzi attendibili o altre tecniche</span><span class="sxs-lookup"><span data-stu-id="ce14d-171">Prevent false positive email marked as spam with a safelist or other techniques</span></span>](prevent-email-from-being-marked-as-spam-0.md)
  
[<span data-ttu-id="ce14d-172">Come impostare il filtro consente di bloccare i messaggi di posta indesiderata antispam di Office 365</span><span class="sxs-lookup"><span data-stu-id="ce14d-172">How to set up Office 365 spam filtering to help block junk messages</span></span>](block-email-spam-to-prevent-false-negatives.md)
  
[<span data-ttu-id="ce14d-173">Che cos'è la differenza tra posta indesiderata e posta elettronica in blocco?</span><span class="sxs-lookup"><span data-stu-id="ce14d-173">What's the Difference Between Junk Email and Bulk Email?</span></span>](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="ce14d-174">Intestazioni messaggi della protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ce14d-174">Anti-spam message headers</span></span>](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="ce14d-175">Backscatter recapito ed EOP</span><span class="sxs-lookup"><span data-stu-id="ce14d-175">Backscatter Messages and EOP</span></span>](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)
  
## <a name="still-need-help"></a><span data-ttu-id="ce14d-176">Ulteriore assistenza?</span><span class="sxs-lookup"><span data-stu-id="ce14d-176">Still need help?</span></span>
<span data-ttu-id="ce14d-177"><a name="BeyondBasics"> </a></span><span class="sxs-lookup"><span data-stu-id="ce14d-177"></span></span>

<span data-ttu-id="ce14d-178">[![Ottenere assistenza dai forum della community di Office 365](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)</span><span class="sxs-lookup"><span data-stu-id="ce14d-178">[![Get help from the Office 365 community forums](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)</span></span>
  
<span data-ttu-id="ce14d-179">[![Amministratori: Accedere e creare una richiesta di assistenza](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)</span><span class="sxs-lookup"><span data-stu-id="ce14d-179">[![Admins: Sign in and create a service request](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)</span></span>
  
<span data-ttu-id="ce14d-180">[![Amministratori: Chiama il supporto](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span><span class="sxs-lookup"><span data-stu-id="ce14d-180">[![Admins: Call Support](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span></span>
  
