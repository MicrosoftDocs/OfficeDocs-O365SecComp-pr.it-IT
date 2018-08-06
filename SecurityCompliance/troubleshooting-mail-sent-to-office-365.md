---
title: Risoluzione dei problemi di posta elettronica inviati a Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
description: In questo articolo vengono fornite informazioni sulla risoluzione dei problemi per i mittenti che hanno riscontrato problemi durante il tentativo di invio della posta elettronica in arrivo in Office 365 e procedure consigliate per la posta in blocco per i clienti di Office 365.
ms.openlocfilehash: 29c30787f493c69eb7d42b8025b25c86acddfff9
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026413"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="daa20-103">Risoluzione dei problemi di posta elettronica inviati a Office 365</span><span class="sxs-lookup"><span data-stu-id="daa20-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="daa20-104">In questo articolo vengono fornite informazioni sulla risoluzione dei problemi per i mittenti che hanno riscontrato problemi durante il tentativo di invio della posta elettronica in arrivo in Office 365 e procedure consigliate per la posta in blocco per i clienti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="daa20-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="daa20-105">Risoluzione dei problemi comuni di recapito della posta a Office 365</span><span class="sxs-lookup"><span data-stu-id="daa20-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="daa20-106">Scegliere uno di questi problemi comuni.</span><span class="sxs-lookup"><span data-stu-id="daa20-106">Choose from one of these commonly encountered issues.</span></span>
  
- [<span data-ttu-id="daa20-107">Invio di gestione dei IP e del dominio reputazione?</span><span class="sxs-lookup"><span data-stu-id="daa20-107">Are you managing your IP and domain's sending reputation?</span></span>](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [<span data-ttu-id="daa20-108">Sono posta invio da nuovi indirizzi IP?</span><span class="sxs-lookup"><span data-stu-id="daa20-108">Are you sending email from new IP addresses?</span></span>](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [<span data-ttu-id="daa20-109">Verificare che il DNS sia impostato correttamente</span><span class="sxs-lookup"><span data-stu-id="daa20-109">Confirm that your DNS is set up correctly</span></span>](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [<span data-ttu-id="daa20-110">Verificare che si non annuncia se stessi come un indirizzo IP non instradabile</span><span class="sxs-lookup"><span data-stu-id="daa20-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [<span data-ttu-id="daa20-111">È stato ricevuto un rapporto di mancato recapito (NDR) per l'invio di posta elettronica a un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="daa20-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [<span data-ttu-id="daa20-112">Posta elettronica sbarcata nella cartella posta indesiderata del destinatario in EOP</span><span class="sxs-lookup"><span data-stu-id="daa20-112">My email landed in the recipient's junk folder in EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [<span data-ttu-id="daa20-113">Il traffico dall'indirizzo IP è limitato da EOP</span><span class="sxs-lookup"><span data-stu-id="daa20-113">Traffic from my IP address is throttled by EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="daa20-114">Invio di gestione dei IP e del dominio reputazione?</span><span class="sxs-lookup"><span data-stu-id="daa20-114">Are you managing your IP and domain's sending reputation?</span></span>
<span data-ttu-id="daa20-115"><a name="ManageRep"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-115"></span></span>

<span data-ttu-id="daa20-p101">Tecnologie di filtraggio EOP sono progettate per fornire protezioni di protezione da posta indesiderate per Microsoft Office 365, nonché altri prodotti di Microsoft Exchange Server, Microsoft Office Outlook e Windows Live Mail. È inoltre possibile sfruttare SPF, DKIM e DMARC; posta elettronica le tecnologie di autenticazione che consentono di risolvere il problema di phishing e spoofing verificare che il dominio di invio della posta elettronica è autorizzato a tale scopo. Filtraggio EOP è influenzato da diversi fattori legati all'indirizzo IP del mittente, dominio, autenticazione, correttezza dell'elenco, percentuali di reclamo, contenuto e altro ancora. Una delle entità fattori determinano verso il basso reputazione del mittente e le capacità di fornire il messaggio di posta elettronica è tariffa reclamo posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="daa20-p101">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail. We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so. EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more. Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span> 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="daa20-120">Sono posta invio da nuovi indirizzi IP?</span><span class="sxs-lookup"><span data-stu-id="daa20-120">Are you sending email from new IP addresses?</span></span>
<span data-ttu-id="daa20-121"><a name="NewIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-121"></span></span>

<span data-ttu-id="daa20-p102">Indirizzi IP precedentemente non utilizzati per inviare posta elettronica in genere non dispongono di alcun reputazione costituita nel nostro sistemi. Di conseguenza, messaggi di posta elettronica dalla nuovo IP sono più probabile riscontrare problemi di recapito. Dopo che l'indirizzo IP è generato reputazione per non l'invio di posta indesiderata, EOP consente in genere per una migliore esperienza di recapito di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="daa20-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>
  
<span data-ttu-id="daa20-p103">Nuovo indirizzi IP che vengono aggiunte per i domini che vengono autenticati in record SPF esistenti in genere verificarsi il vantaggio di ereditarietà alcune della reputazione mittente del dominio. Se il dominio è una buona l'invio di reputazione IP nuovo potrebbe verificarsi un più rapido quanto tempo. Un nuovo PI prevedibili utilizzare il nome all'interno di un paio di settimane o prima a seconda di volume, correttezza dell'elenco e tariffe reclamo posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="daa20-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="daa20-128">Verificare che il DNS sia impostato correttamente</span><span class="sxs-lookup"><span data-stu-id="daa20-128">Confirm that your DNS is set up correctly</span></span>
<span data-ttu-id="daa20-129"><a name="ConfirmDNSsetup"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-129"></span></span>

<span data-ttu-id="daa20-130">Per istruzioni su come creare e gestire i record DNS, incluso il record MX necessario per il routing della posta, è necessario contattare il provider di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="daa20-130">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="daa20-131">Verificare che si non annuncia se stessi come un indirizzo IP non instradabile</span><span class="sxs-lookup"><span data-stu-id="daa20-131">Ensure that you do not advertise yourself as a non-routable IP</span></span>
<span data-ttu-id="daa20-132"><a name="NoReverseDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-132"></span></span>

<span data-ttu-id="daa20-p104">È non può accettare la posta elettronica da mittenti che ha esito negativo di una ricerca DNS inverso. In alcuni casi, i mittenti legittimi annunciano erroneamente come un indirizzo IP instradabile internet non quando si tenta di aprire una connessione a EOP. Indirizzi IP riservati per le reti private (non instradabili) includono:</span><span class="sxs-lookup"><span data-stu-id="daa20-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>
  
- <span data-ttu-id="daa20-136">192.168.0.0/16 (o 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="daa20-136">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
    
- <span data-ttu-id="daa20-137">10.0.0.0/8 (o 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="daa20-137">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
    
- <span data-ttu-id="daa20-138">172.16.0.0/11 (o 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="daa20-138">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="daa20-139">È stato ricevuto un rapporto di mancato recapito (NDR) per l'invio di posta elettronica a un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="daa20-139">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>
<span data-ttu-id="daa20-140"><a name="NDRInbound"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-140"></span></span>

<span data-ttu-id="daa20-p105">Alcuni problemi di recapito sono il risultato dell'indirizzo IP del mittente viene bloccato da Microsoft o dal momento che l'account utente viene identificato come mittente da escludere a causa di attività da posta indesiderata precedente. Se si ritiene che si è ricevuto il rapporto di mancato recapito in errore, eseguire le istruzioni nel messaggio di rapporto di mancato recapito per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="daa20-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span> 
  
<span data-ttu-id="daa20-143">Per ulteriori informazioni sull'errore è stato ricevuto, vedere l'elenco completo dei codici di errore SMTP [DSN e NDR in Exchange 2013 locale e Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span><span class="sxs-lookup"><span data-stu-id="daa20-143">For more information about the error you received, see the complete list of SMTP error codes in [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span></span>
  
 <span data-ttu-id="daa20-144">Ad esempio, se viene visualizzato il rapporto di mancato recapito seguente, significa che l'indirizzo IP del mittente è stato bloccato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="daa20-144">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span> 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
<span data-ttu-id="daa20-145">Per richiedere la rimozione dall'elenco, è possibile [utilizzare il portale delist per eliminare il proprio nome nell'elenco Mittenti bloccati di Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="daa20-145">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="daa20-146">Posta elettronica sbarcata nella cartella posta indesiderata del destinatario in EOP</span><span class="sxs-lookup"><span data-stu-id="daa20-146">My email landed in the recipient's junk folder in EOP</span></span>
<span data-ttu-id="daa20-147"><a name="JunkMailBox"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-147"></span></span>

<span data-ttu-id="daa20-p106">Se un messaggio è stato erroneamente identificato come posta indesiderata da EOP, è possibile utilizzare il destinatario a inviare questo messaggio falso positivo al Team di analisi della posta indesiderata Microsoft, che valutare e analizzare il messaggio. In base ai risultati dell'analisi, le regole di filtro dei contenuti da posta indesiderata a livello di servizio possono essere regolate per consentire il messaggio attraverso. Messaggio di posta elettronica consente di inviare messaggi a Microsoft che non devono essere classificate come posta indesiderata. In tal caso, assicurarsi di utilizzare i passaggi nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="daa20-p106">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through. You use email to submit messages to Microsoft that should not be classified as spam. When doing so, be sure to use the steps in the following procedure.</span></span>
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="daa20-152">Utilizzare la posta elettronica per inviare messaggi falsi positivi al Team di analisi della posta indesiderata di Microsoft</span><span class="sxs-lookup"><span data-stu-id="daa20-152">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="daa20-153">Salvare il messaggio che si desidera inviare come posta non indesiderata.</span><span class="sxs-lookup"><span data-stu-id="daa20-153">Save the message you want to submit as non-spam.</span></span>
    
2. <span data-ttu-id="daa20-154">Creare un nuovo messaggio vuoto e allegarvi il messaggio di posta non indesiderata.</span><span class="sxs-lookup"><span data-stu-id="daa20-154">Create a new, blank message and attach the non-spam message to it.</span></span>
    
    <span data-ttu-id="daa20-155">Se necessario, è possibile collegare più messaggi di posta non indesiderata.</span><span class="sxs-lookup"><span data-stu-id="daa20-155">You can attach multiple non-spam messages if needed.</span></span>
    
3. <span data-ttu-id="daa20-156">Copiare e incollare la riga dell'oggetto del messaggio originale nella riga dell'oggetto del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="daa20-156">Copy and paste the original message subject line into the new message subject line.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="daa20-157">Lasciare vuoto il corpo del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="daa20-157">Leave the body of the new message empty.</span></span> 
  
4. <span data-ttu-id="daa20-158">Inviare il nuovo messaggio a [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="daa20-158">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="daa20-159">Il traffico dall'indirizzo IP è limitato da EOP</span><span class="sxs-lookup"><span data-stu-id="daa20-159">Traffic from my IP address is throttled by EOP</span></span>
<span data-ttu-id="daa20-160"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-160"></span></span>

<span data-ttu-id="daa20-161">Se si riceve un rapporto di mancato recapito da EOP che indica che l'indirizzo IP viene limitato da EOP, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="daa20-161">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
<span data-ttu-id="daa20-p107">È stato ricevuto il rapporto di mancato recapito perché sono stata rilevata attività sospette dall'indirizzo IP e sono state temporaneamente limitata durante un'ulteriore di valutazione. Se il sospetto è deselezionato attraverso la valutazione, questa limitazione verrà revocata a breve.</span><span class="sxs-lookup"><span data-stu-id="daa20-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="daa20-164">Non è possibile ricevere posta elettronica da mittenti in Office 365</span><span class="sxs-lookup"><span data-stu-id="daa20-164">I can't receive email from senders in Office 365</span></span>
<span data-ttu-id="daa20-165"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-165"></span></span>

 <span data-ttu-id="daa20-p108">Per ricevere messaggi da utenti, verificare che la rete consente connessioni verso gli indirizzi IP utilizzato nel nostro datacenter EOP. Per ulteriori informazioni, vedere [gli indirizzi IP di Exchange Online Protection](eop/exchange-online-protection-ip-addresses.md). Per un record dell'indirizzo IP di tutti gli indirizzi che sono stati aggiunti, modificati o obsoleti lo scorso anno, vedere [Modifica delle notifiche per gli indirizzi IP di EOP](eop/change-notification-for-eop-ip-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="daa20-p108">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters. For more information, see [Exchange Online Protection IP addresses](eop/exchange-online-protection-ip-addresses.md). For a record of all IP addresses that have been added, changed, or deprecated in the past year, see [Change notification for EOP IP addresses](eop/change-notification-for-eop-ip-addresses.md).</span></span>
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="daa20-169">Procedure consigliate per l'invio tramite posta elettronica in blocco per gli utenti di Office 365</span><span class="sxs-lookup"><span data-stu-id="daa20-169">Best practices for bulk emailing to Office 365 users</span></span>
<span data-ttu-id="daa20-170"><a name="BulkMailer"> </a></span><span class="sxs-lookup"><span data-stu-id="daa20-170"></span></span>

<span data-ttu-id="daa20-171">Se si spesso condurre campagne di posta elettronica in blocco per gli utenti di Office 365 e per garantire che i messaggi di posta elettronica verranno aggiunti in modo sicuro e tempestivo, seguire i suggerimenti forniti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="daa20-171">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="daa20-172">Verificare che il mittente: nome riflette il mittente del messaggio</span><span class="sxs-lookup"><span data-stu-id="daa20-172">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="daa20-p109">L'oggetto deve essere un breve riepilogo delle quali il messaggio è dedicato e il corpo dei messaggi deve chiaramente e conciso indicano il ruolo l'offerta, servizi o prodotti su. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="daa20-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>
  
<span data-ttu-id="daa20-175">Correggere</span><span class="sxs-lookup"><span data-stu-id="daa20-175">Correct</span></span>
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
<span data-ttu-id="daa20-176">Non corretto</span><span class="sxs-lookup"><span data-stu-id="daa20-176">Incorrect</span></span>
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
<span data-ttu-id="daa20-177">Per i partecipanti a sapere chi è il più semplice apportate e meno difficoltà, le operazioni è necessario il recapito attraverso la maggior parte dei filtri posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="daa20-177">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="daa20-178">Sempre includono un'opzione unsubscribe in messaggi di posta elettronica campagna</span><span class="sxs-lookup"><span data-stu-id="daa20-178">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="daa20-p110">Messaggi di posta elettronica di marketing, soprattutto notiziari, deve sempre includere un modo per annullare la sottoscrizione da futuri messaggi di posta elettronica. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="daa20-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
<span data-ttu-id="daa20-p111">Alcuni mittenti includono questa opzione per richiedere i destinatari inviare un messaggio di posta elettronica a un determinato alias con "Unsubscribe" nell'oggetto. Questo non è preferibile utilizzare l'esempio di un solo clic. Se si sceglie di richiedono ai destinatari di inviare un messaggio di posta, assicurarsi che quando si fa clic sul collegamento, tutti i campi necessari siano prepopolati.</span><span class="sxs-lookup"><span data-stu-id="daa20-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="daa20-184">Utilizzare l'opzione doppia consenso esplicito per la registrazione del messaggio di posta elettronica o newsletter di marketing</span><span class="sxs-lookup"><span data-stu-id="daa20-184">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="daa20-p112">Se l'azienda richiede o incoraggia agli utenti di registrare le informazioni di contatto per accedere ai prodotti o servizi, è consigliabile questo best practice del settore. Alcune aziende rendono consigliata per accedere automaticamente agli utenti di marketing messaggi di posta elettronica o newsletter durante il processo di registrazione, ma si è considerato un'ambigui consigliata marketing nel mondo del filtro di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="daa20-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>
  
<span data-ttu-id="daa20-187">Durante il processo di registrazione, se il "Sì, inviare me notiziario" o "Sì, inviare me offerte speciali" casella di controllo è selezionata per impostazione predefinita, gli utenti che non prestare particolare attenzione potrebbero inavvertitamente iscrizione a posta elettronica marketing o newsletter che non vengano Se si desidera ricevere.</span><span class="sxs-lookup"><span data-stu-id="daa20-187">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>
  
 <span data-ttu-id="daa20-p113">È consigliabile l'opzione doppio di consenso esplicito in realtà, il che significa che la casella di controllo per i messaggi di marketing o newsletter sia selezionata per impostazione predefinita. Inoltre, dopo che il modulo di registrazione è stato inviato, all'utente con un URL che consente di verificare la propria decisione di ricevere messaggi di marketing viene inviato un messaggio di posta elettronica di verifica.</span><span class="sxs-lookup"><span data-stu-id="daa20-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span> 
  
 <span data-ttu-id="daa20-190">In questo modo si garantisce che solo gli utenti che desiderano ricevere posta marketing effettuati la registrazione per i messaggi di posta elettronica, successivamente deselezionando la società invio di un messaggio di posta elettronica ambigui marketing consigliate.</span><span class="sxs-lookup"><span data-stu-id="daa20-190">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span> 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="daa20-191">Verificare che il contenuto di messaggi di posta elettronica trasparente e riconducibili</span><span class="sxs-lookup"><span data-stu-id="daa20-191">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="daa20-p114">Altrettanto importante come il contenuto che contengono il modo in cui che vengono inviati i messaggi di posta elettronica. Durante la creazione di contenuto di posta elettronica, utilizzare le procedure consigliate seguenti per verificare che i messaggi di posta elettronica non verrà essere contrassegnati da servizi di filtro della posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="daa20-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>
  
- <span data-ttu-id="daa20-194">Quando il messaggio di posta elettronica richiede che i destinatari di aggiungere il mittente alla Rubrica, è necessario indicare che tale azione non è una garanzia di recapito.</span><span class="sxs-lookup"><span data-stu-id="daa20-194">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>
    
- <span data-ttu-id="daa20-p115">Devono essere inclusi nel corpo del messaggio i reindirizzamenti simile e coerenti e non più e variabili. Un reindirizzamento in questo contesto è tutto ciò che punta dal messaggio, ad esempio documenti e collegamenti. Se si dispone di una quantità elevata di tali campagne o annullare collegamenti o aggiornare i collegamenti di profilo, sono tutti i devono puntare allo stesso dominio. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="daa20-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>
    
    <span data-ttu-id="daa20-199">Correggere</span><span class="sxs-lookup"><span data-stu-id="daa20-199">Correct</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    <span data-ttu-id="daa20-200">Non corretto</span><span class="sxs-lookup"><span data-stu-id="daa20-200">Incorrect</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- <span data-ttu-id="daa20-201">Evitare di contenuto con immagini di grandi dimensioni e gli allegati o messaggi composti unicamente di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="daa20-201">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>
    
- <span data-ttu-id="daa20-202">Impostazioni relative alla privacy pubblica o P3P devono indicare la presenza di verifica pixel (bug web o beacon).</span><span class="sxs-lookup"><span data-stu-id="daa20-202">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="daa20-203">Rimuovere gli alias di posta elettronica non corretto dei database</span><span class="sxs-lookup"><span data-stu-id="daa20-203">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="daa20-p116">Un alias di posta elettronica del database che consente di creare un rimbalzo-back è necessario e inserisce i messaggi di posta elettronica in uscita a rischio per un ulteriore esame da servizi di filtro della posta elettronica. Verificare che il database di posta elettronica aggiornato.</span><span class="sxs-lookup"><span data-stu-id="daa20-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>
  

