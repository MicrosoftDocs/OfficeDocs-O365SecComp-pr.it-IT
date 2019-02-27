---
title: Risoluzione dei problemi della posta elettronica inviati a Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: In questo articolo vengono fornite informazioni per la risoluzione dei problemi per i mittenti che riscontrano problemi durante il tentativo di inviare messaggi di posta elettronica alle cassette postali in Office 365 e procedure consigliate per la posta in blocco ai clienti di Office 365
ms.openlocfilehash: cfb3901b930b63ef8a33391c673a32a73eaa1b07
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276296"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="237b5-103">Risoluzione dei problemi della posta elettronica inviati a Office 365</span><span class="sxs-lookup"><span data-stu-id="237b5-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="237b5-104">In questo articolo vengono fornite informazioni per la risoluzione dei problemi per i mittenti che riscontrano problemi durante il tentativo di inviare messaggi di posta elettronica alle cassette postali in Office 365 e procedure consigliate per la posta in blocco ai clienti di Office 365</span><span class="sxs-lookup"><span data-stu-id="237b5-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="237b5-105">Risoluzione dei problemi comuni relativi al recapito della posta elettronica a Office 365</span><span class="sxs-lookup"><span data-stu-id="237b5-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="237b5-106">Scegliere uno dei problemi comunemente riscontrati.</span><span class="sxs-lookup"><span data-stu-id="237b5-106">Choose from one of these commonly encountered issues.</span></span>
  
- [<span data-ttu-id="237b5-107">Si sta gestendo la reputazione di invio di IP e domini?</span><span class="sxs-lookup"><span data-stu-id="237b5-107">Are you managing your IP and domain's sending reputation?</span></span>](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [<span data-ttu-id="237b5-108">Si sta inviando messaggi di posta elettronica da nuovi indirizzi IP?</span><span class="sxs-lookup"><span data-stu-id="237b5-108">Are you sending email from new IP addresses?</span></span>](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [<span data-ttu-id="237b5-109">Verificare che il DNS sia configurato correttamente</span><span class="sxs-lookup"><span data-stu-id="237b5-109">Confirm that your DNS is set up correctly</span></span>](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [<span data-ttu-id="237b5-110">Assicurarsi di non essere pubblicizzati come IP non instradabile</span><span class="sxs-lookup"><span data-stu-id="237b5-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [<span data-ttu-id="237b5-111">Si è ricevuto un rapporto di mancato recapito (NDR) quando si invia un messaggio di posta elettronica a un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="237b5-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [<span data-ttu-id="237b5-112">La posta elettronica è atterrata nella cartella di posta indesiderata del destinatario in EOP</span><span class="sxs-lookup"><span data-stu-id="237b5-112">My email landed in the recipient's junk folder in EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [<span data-ttu-id="237b5-113">Il traffico proveniente dall'indirizzo IP è limitato da EOP</span><span class="sxs-lookup"><span data-stu-id="237b5-113">Traffic from my IP address is throttled by EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="237b5-114">Si sta gestendo la reputazione di invio di IP e domini?</span><span class="sxs-lookup"><span data-stu-id="237b5-114">Are you managing your IP and domain's sending reputation?</span></span>
<span data-ttu-id="237b5-115"><a name="ManageRep"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-115"></span></span>

<span data-ttu-id="237b5-p101">Le tecnologie di filtro di EOP sono progettate per fornire protezione da posta indesiderata per Microsoft Office 365, nonché altri prodotti Microsoft come Exchange Server, Microsoft Office Outlook e Windows Live Mail. È inoltre possibile utilizzare SPF, DKIM e DMARC; tecnologie di autenticazione della posta elettronica che consentono di risolvere il problema dello spoofing e del phishing verificando che il dominio che invia il messaggio di posta elettronica sia autorizzato a farlo. Il filtro EOP è influenzato da una serie di fattori correlati all'IP di invio, al dominio, all'autenticazione, all'accuratezza degli elenchi, alle tariffe dei reclami, al contenuto e altro ancora. Tra questi, uno dei fattori principali per abbassare la reputazione del mittente e la possibilità di inviare messaggi di posta elettronica è la frequenza dei reclami per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="237b5-p101">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail. We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so. EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more. Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span> 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="237b5-120">Si sta inviando messaggi di posta elettronica da nuovi indirizzi IP?</span><span class="sxs-lookup"><span data-stu-id="237b5-120">Are you sending email from new IP addresses?</span></span>
<span data-ttu-id="237b5-121"><a name="NewIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-121"></span></span>

<span data-ttu-id="237b5-p102">Gli indirizzi IP non utilizzati in precedenza per inviare messaggi di posta elettronica in genere non dispongono di una reputazione integrata nei sistemi. Di conseguenza, è più probabile che i messaggi di posta elettronica provenienti da nuovi IP sperimentino problemi di recapito. Una volta che l'IP ha creato una reputazione per l'invio di posta indesiderata, EOP consentirà una migliore esperienza di recapito della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="237b5-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>
  
<span data-ttu-id="237b5-p103">I nuovi indirizzi IP aggiunti per i domini autenticati con i record SPF esistenti in genere avvertono l'ulteriore vantaggio di ereditare una parte della reputazione di invio del dominio. Se il dominio ha una buona reputazione di invio, è possibile che i nuovi IP possano riscontrare tempi di rampa più veloci. Un nuovo IP può pretendere di essere completamente rampante entro un paio di settimane o prima a seconda del volume, dell'accuratezza degli elenchi e delle tariffe di reclamo per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="237b5-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="237b5-128">Verificare che il DNS sia configurato correttamente</span><span class="sxs-lookup"><span data-stu-id="237b5-128">Confirm that your DNS is set up correctly</span></span>
<span data-ttu-id="237b5-129"><a name="ConfirmDNSsetup"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-129"></span></span>

<span data-ttu-id="237b5-130">Per istruzioni su come creare e gestire i record DNS, incluso il record MX necessario per il routing della posta, sarà necessario contattare il provider di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="237b5-130">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="237b5-131">Assicurarsi di non essere pubblicizzati come IP non instradabile</span><span class="sxs-lookup"><span data-stu-id="237b5-131">Ensure that you do not advertise yourself as a non-routable IP</span></span>
<span data-ttu-id="237b5-132"><a name="NoReverseDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-132"></span></span>

<span data-ttu-id="237b5-p104">Non è possibile accettare messaggi di posta elettronica provenienti da mittenti che non eseguono una ricerca DNS inversa. In alcuni casi, i mittenti legittimi si annunciano in modo errato come IP instradabile non Internet quando si tenta di aprire una connessione a EOP. Gli indirizzi IP riservati per la rete privata (non instradabile) includono:</span><span class="sxs-lookup"><span data-stu-id="237b5-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>
  
- <span data-ttu-id="237b5-136">192.168.0.0/16 (o 192.168.0.0-192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="237b5-136">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
    
- <span data-ttu-id="237b5-137">10.0.0.0/8 (o 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="237b5-137">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
    
- <span data-ttu-id="237b5-138">172.16.0.0/11 (o 172.16.0.0-172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="237b5-138">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="237b5-139">Si è ricevuto un rapporto di mancato recapito (NDR) quando si invia un messaggio di posta elettronica a un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="237b5-139">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>
<span data-ttu-id="237b5-140"><a name="NDRInbound"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-140"></span></span>

<span data-ttu-id="237b5-p105">Alcuni problemi di recapito sono il risultato dell'indirizzo IP del mittente che è stato bloccato da Microsoft o perché l'account utente è stato identificato come mittente vietato a causa di precedenti attività di posta indesiderata. Se si ritiene di aver ricevuto il rapporto di MANCAto reCAPITO in caso di errore, seguire le istruzioni riportate nel messaggio di MANCAto reCAPITO per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="237b5-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span> 
  
<span data-ttu-id="237b5-143">Per ulteriori informazioni sull'errore ricevuto, vedere l'elenco completo dei codici di errore SMTP nelle [DSN e nei rapporti di mancato recapito in Exchange 2013 e Office 365 locali](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span><span class="sxs-lookup"><span data-stu-id="237b5-143">For more information about the error you received, see the complete list of SMTP error codes in [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span></span>
  
 <span data-ttu-id="237b5-144">Ad esempio, se si riceve il rapporto di MANCAto reCAPITO seguente, indica che l'indirizzo IP di invio è stato bloccato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="237b5-144">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span> 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
<span data-ttu-id="237b5-145">Per richiedere la rimozione da questo elenco, è possibile [utilizzare il portale di delist per rimuovere se stessi dall'elenco Mittenti bloccati di Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="237b5-145">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="237b5-146">La posta elettronica è atterrata nella cartella di posta indesiderata del destinatario in EOP</span><span class="sxs-lookup"><span data-stu-id="237b5-146">My email landed in the recipient's junk folder in EOP</span></span>
<span data-ttu-id="237b5-147"><a name="JunkMailBox"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-147"></span></span>

<span data-ttu-id="237b5-p106">Se un messaggio è stato erroneamente identificato come posta indesiderata da EOP, è possibile collaborare con il destinatario per inviare questo messaggio falso positivo al team di analisi di posta inDesiderata di Microsoft, che valuterà e analizzerà il messaggio. A seconda dei risultati dell'analisi, è possibile modificare le regole di filtro del contenuto della posta indesiderata a livello di servizio per consentire il passaggio del messaggio. Si utilizza la posta elettronica per inviare messaggi a Microsoft che non devono essere classificati come posta indesiderata. Quando si esegue questa operazione, accertarsi di utilizzare i passaggi descritti nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="237b5-p106">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through. You use email to submit messages to Microsoft that should not be classified as spam. When doing so, be sure to use the steps in the following procedure.</span></span>
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="237b5-152">Per utilizzare la posta elettronica per inviare messaggi falsi positivi al team di analisi di posta inDesiderata di Microsoft</span><span class="sxs-lookup"><span data-stu-id="237b5-152">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="237b5-153">Salvare il messaggio che si desidera inviare come non di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="237b5-153">Save the message you want to submit as non-spam.</span></span>
    
2. <span data-ttu-id="237b5-154">Creare un nuovo messaggio vuoto e allegarvi il messaggio di posta non indesiderata.</span><span class="sxs-lookup"><span data-stu-id="237b5-154">Create a new, blank message and attach the non-spam message to it.</span></span>
    
    <span data-ttu-id="237b5-155">Se necessario, è possibile allegare più messaggi non di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="237b5-155">You can attach multiple non-spam messages if needed.</span></span>
    
3. <span data-ttu-id="237b5-156">Copiare e incollare la riga dell'oggetto del messaggio originale nella riga dell'oggetto del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="237b5-156">Copy and paste the original message subject line into the new message subject line.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="237b5-157">Lasciare vuoto il corpo del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="237b5-157">Leave the body of the new message empty.</span></span> 
  
4. <span data-ttu-id="237b5-158">Inviare il nuovo messaggio a [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="237b5-158">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="237b5-159">Il traffico proveniente dall'indirizzo IP è limitato da EOP</span><span class="sxs-lookup"><span data-stu-id="237b5-159">Traffic from my IP address is throttled by EOP</span></span>
<span data-ttu-id="237b5-160"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-160"></span></span>

<span data-ttu-id="237b5-161">Se si riceve un rapporto di MANCAto reCAPITO da EOP che indica che l'indirizzo IP è sottoposto a limitazione da EOP, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="237b5-161">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
<span data-ttu-id="237b5-p107">È stato ricevuto il rapporto di MANCAto reCAPITO perché l'attività sospetta è stata rilevata dall'indirizzo IP ed è stata temporaneamente limitata durante la valutazione. Se il sospetto è deselezionato tramite valutazione, questa restrizione verrà revocata a breve.</span><span class="sxs-lookup"><span data-stu-id="237b5-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="237b5-164">Non è possibile ricevere messaggi di posta elettronica da mittenti in Office 365</span><span class="sxs-lookup"><span data-stu-id="237b5-164">I can't receive email from senders in Office 365</span></span>
<span data-ttu-id="237b5-165"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-165"></span></span>

 <span data-ttu-id="237b5-p108">Per ricevere i messaggi dagli utenti, verificare che la rete consenta le connessioni dagli indirizzi IP utilizzati da EOP nei data center. Per ulteriori informazioni, vedere [indirizzi IP di Exchange Online Protection](eop/exchange-online-protection-ip-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="237b5-p108">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters. For more information, see [Exchange Online Protection IP addresses](eop/exchange-online-protection-ip-addresses.md).</span></span> 
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="237b5-168">Procedure consigliate per l'invio di posta elettronica in blocco agli utenti di Office 365</span><span class="sxs-lookup"><span data-stu-id="237b5-168">Best practices for bulk emailing to Office 365 users</span></span>
<span data-ttu-id="237b5-169"><a name="BulkMailer"> </a></span><span class="sxs-lookup"><span data-stu-id="237b5-169"></span></span>

<span data-ttu-id="237b5-170">Se si eseguono spesso campagne di posta elettronica in blocco per gli utenti di Office 365 e si vuole garantire la sicurezza e la tempestività dei messaggi, seguire le indicazioni riportate in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="237b5-170">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="237b5-171">Verificare che il nome: rispecchi chi sta inviando il messaggio</span><span class="sxs-lookup"><span data-stu-id="237b5-171">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="237b5-p109">L'oggetto dovrebbe essere un breve riepilogo del messaggio e il corpo del messaggio deve indicare in modo chiaro e conciso cosa significa l'offerta, il servizio o il prodotto. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="237b5-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>
  
<span data-ttu-id="237b5-174">Corretto</span><span class="sxs-lookup"><span data-stu-id="237b5-174">Correct</span></span>
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
<span data-ttu-id="237b5-175">Non corretto</span><span class="sxs-lookup"><span data-stu-id="237b5-175">Incorrect</span></span>
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
<span data-ttu-id="237b5-176">Più è facile per gli utenti sapere chi è e cosa si sta facendo, minore sarà la difficoltà con la maggior parte dei filtri per la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="237b5-176">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="237b5-177">Includi sempre un'opzione di annullamento della sottoscrizione nei messaggi di posta elettronica della campagna</span><span class="sxs-lookup"><span data-stu-id="237b5-177">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="237b5-p110">I messaggi di posta elettronica di marketing, in particolare le newsletter, dovrebbero includere sempre un modo di annullamento della sottoscrizione da messaggi di posta elettronica futuri. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="237b5-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
<span data-ttu-id="237b5-p111">Alcuni mittenti includono questa opzione richiedendo ai destinatari di inviare un messaggio di posta elettronica a un determinato alias con "Annulla sottoscrizione" nell'oggetto. Questo non è preferibile all'esempio di un clic sopra riportato. Se si sceglie di richiedere ai destinatari di inviare un messaggio di posta elettronica, verificare che quando si fa clic sul collegamento, tutti i campi richiesti siano precompilati.</span><span class="sxs-lookup"><span data-stu-id="237b5-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="237b5-183">Utilizzare l'opzione double opt-in per la registrazione della posta elettronica o della newsletter di marketing</span><span class="sxs-lookup"><span data-stu-id="237b5-183">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="237b5-p112">Questa procedura consigliata per il settore è consigliabile se la propria azienda richiede o incoraggia gli utenti a registrare le proprie informazioni di contatto per accedere al prodotto o ai servizi. Alcune aziende hanno la consuetudine di iscrivere automaticamente gli utenti per i messaggi di posta elettronica di marketing o di e-newsletter durante il processo di registrazione, ma questa è considerata una pratica di marketing discutibile nel mondo del filtraggio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="237b5-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>
  
<span data-ttu-id="237b5-186">Durante il processo di registrazione, se la casella di controllo "Sì, Inviami la tua newsletter" o "Sì, Inviami offerte speciali" è selezionata per impostazione predefinita, gli utenti che non prestano molta attenzione possono involontariamente iscriversi per la posta elettronica di marketing o le newsletter che non desidera ricevere.</span><span class="sxs-lookup"><span data-stu-id="237b5-186">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>
  
 <span data-ttu-id="237b5-p113">È consigliabile invece l'opzione double opt-in, il che significa che la casella di controllo per i messaggi di posta elettronica di marketing o le newsletter è deselezionata per impostazione predefinita. Inoltre, una volta che il modulo di registrazione è stato inviato, un messaggio di posta elettronica di verifica viene inviato all'utente con un URL che consente di confermare la decisione di ricevere messaggi di posta elettronica di marketing.</span><span class="sxs-lookup"><span data-stu-id="237b5-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span> 
  
 <span data-ttu-id="237b5-189">In questo modo si garantisce che solo gli utenti che desiderano ricevere la posta elettronica di marketing siano iscritti per la posta elettronica, successivamente deselezionando la società di invio di eventuali pratiche di marketing della posta elettronica discutibili.</span><span class="sxs-lookup"><span data-stu-id="237b5-189">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span> 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="237b5-190">Verificare che il contenuto del messaggio di posta elettronica sia trasparente e tracciabile</span><span class="sxs-lookup"><span data-stu-id="237b5-190">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="237b5-p114">Altrettanto importante del modo in cui vengono inviati i messaggi di posta elettronica è il contenuto che contengono. Quando si crea il contenuto della posta elettronica, utilizzare le procedure consigliate seguenti per garantire che i messaggi di posta elettronica non vengano contrassegnati tramite i servizi di filtraggio delle e-mail:</span><span class="sxs-lookup"><span data-stu-id="237b5-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>
  
- <span data-ttu-id="237b5-193">Quando il messaggio di posta elettronica richiede che i destinatari aggiungono il mittente alla Rubrica, è necessario indicare chiaramente che tale azione non è una garanzia di recapito.</span><span class="sxs-lookup"><span data-stu-id="237b5-193">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>
    
- <span data-ttu-id="237b5-p115">I reindirizzamenti inclusi nel corpo del messaggio devono essere simili e coerenti e non multipli e diversificati. Un reindirizzamento in questo contesto è qualsiasi elemento che punti al di fuori del messaggio, ad esempio collegamenti e documenti. Se si dispone di numerosi collegamenti pubblicitari o di annullamento della sottoscrizione oppure si aggiornano i collegamenti dei profili, tutti gli utenti devono puntare allo stesso dominio. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="237b5-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>
    
    <span data-ttu-id="237b5-198">Corretto</span><span class="sxs-lookup"><span data-stu-id="237b5-198">Correct</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    <span data-ttu-id="237b5-199">Non corretto</span><span class="sxs-lookup"><span data-stu-id="237b5-199">Incorrect</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- <span data-ttu-id="237b5-200">Evitare contenuti con immagini e allegati di grandi dimensioni o messaggi composti unicamente da un'immagine.</span><span class="sxs-lookup"><span data-stu-id="237b5-200">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>
    
- <span data-ttu-id="237b5-201">La privacy pubblica o le impostazioni di P3P devono indicare chiaramente la presenza di pixel di rilevamento (bug Web o beacon).</span><span class="sxs-lookup"><span data-stu-id="237b5-201">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="237b5-202">Rimuovere gli alias di posta elettronica non corretti dai database</span><span class="sxs-lookup"><span data-stu-id="237b5-202">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="237b5-p116">Qualsiasi alias di posta elettronica nel database che consente di creare un rimbalzo non è necessario e pone i messaggi di posta elettronica in uscita a rischio per un ulteriore controllo tramite i servizi di filtraggio della posta elettronica. Verificare che il database di posta elettronica sia aggiornato.</span><span class="sxs-lookup"><span data-stu-id="237b5-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>
  

