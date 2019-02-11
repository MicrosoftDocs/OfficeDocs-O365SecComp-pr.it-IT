---
title: Business intelligence di flusso di posta elettronica in Office 365
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Gli amministratori possono venire a conoscenza i codici di errore che sono associati a recapito dei messaggi utilizzando i connettori in Office 365 (noto anche come intelligence del flusso di posta elettronica).
ms.openlocfilehash: 9f27dfd4c265eb62028d68c27764183202692ef4
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "28327088"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="f2e9a-103">Business intelligence di flusso di posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="f2e9a-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="f2e9a-p101">Utilizzato in genere, un connettore per instradare i messaggi di posta elettronica dall'organizzazione Office 365 per l'ambiente di posta elettronica locale. È inoltre possibile utilizzare un connettore per instradare i messaggi da Office 365 a un'organizzazione partner. Quando Office 365 non è in grado di distribuire questi messaggi attraverso il connettore, sta accodate in Office 365. Office 365 continuerà a tentativi di recapito per ogni messaggio per 48 ore. Dopo 48 ore, scade dopo il messaggio in coda e il messaggio verrà restituito al mittente originale in un rapporto di mancato recapito (noto anche come un messaggio di rapporto di mancato recapito o di rimbalzo).</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p101">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="f2e9a-p102">Office 365 genererà un errore quando un messaggio non possono essere inviato tramite un connettore. In questo argomento vengono descritti gli errori più comuni e le relative soluzioni. Collettivamente, gli errori di Accodamento messaggi e le notifiche per i messaggi non recapitati inviati tramite un connettore è noto come _Business intelligence di flusso di posta elettronica_.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p102">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="f2e9a-112">Codice errore: 450 4.4.312 Query DNS non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2e9a-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="f2e9a-p103">Questo errore indica in genere, che Office 365 ha tentato di connettersi a quest ' ultimo specificato nel connettore, ma la query DNS per individuare gli indirizzi IP dell'host smart non è riusciti. Le possibili cause di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p103">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed. The possible causes for this error are:</span></span>

- <span data-ttu-id="f2e9a-115">Si è verificato un errore relativo al servizio di hosting DNS del proprio dominio (la terza parte che gestisce i server dei nomi autorevoli per il dominio).</span><span class="sxs-lookup"><span data-stu-id="f2e9a-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="f2e9a-116">Di recente, il dominio è scaduto e di conseguenza il record MX non può essere recuperato.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="f2e9a-117">Il record MX del dominio è stato recentemente modificato e i server DNS di Office 365 hanno ancora le informazioni DNS memorizzate in precedenza per il dominio.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="f2e9a-118">Come è possibile risolvere il codice di errore 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="f2e9a-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="f2e9a-119">Utilizzare il servizio di hosting DNS per individuare e risolvere il problema con il proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="f2e9a-120">Se l'errore è dall'organizzazione partner (ad esempio, un 3rd parti cloud provider di servizi), contattare il partner per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="f2e9a-121">Codice errore: 450 4.4.315 Timeout della connessione</span><span class="sxs-lookup"><span data-stu-id="f2e9a-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="f2e9a-p104">In genere, ciò significa che Office 365 non è possibile connettersi al server di posta elettronica di destinazione. I dettagli dell'errore verranno illustrato il problema. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p104">Typically, this means Office 365 can't connect to the destination email server. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="f2e9a-125">Il server di posta elettronica locale è inattivo.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="f2e9a-126">Si è verificato un errore relativo alle impostazione dello smart host del connettore, quindi Office 365 prova a connettersi all'indirizzo IP sbagliato.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="f2e9a-127">Come è possibile risolvere il codice di errore 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="f2e9a-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="f2e9a-p105">Scoprire di quali scenario si applica a un utente e apportare le correzioni necessarie. Ad esempio, se il flusso della posta è stata funzioni correttamente e non è stato modificato le impostazioni dei connettori, è necessario controllare l'ambiente di posta elettronica locale per verificare se il server è inattivo o se sono state apportate modifiche all'infrastruttura di rete (ad esempio, siano state modificate provider di servizi internet, in modo che ora è indirizzi IP diversi).</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p105">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="f2e9a-130">Se l'errore è dall'organizzazione partner (ad esempio, un 3rd parti cloud provider di servizi), contattare il partner per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="f2e9a-131">Codice errore: 450 4.4.316 Connessione rifiutata</span><span class="sxs-lookup"><span data-stu-id="f2e9a-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="f2e9a-p106">Questo errore indica in genere, che Office 365 si è verificato un errore di connessione quando si è tentato di connettersi al server di posta elettronica di destinazione. Una possibile causa di questo errore è che il firewall blocca le connessioni da indirizzi IP di Office 365. In alternativa, questo errore può essere per impostazione predefinita se completamente eseguita la migrazione locale del sistema di posta elettronica a Office 365 e arrestare l'ambiente di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p106">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="f2e9a-135">Come è possibile risolvere il codice di errore 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="f2e9a-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="f2e9a-p107">Se si dispongono delle cassette postali locali nell'ambiente in uso, è necessario modificare le impostazioni del firewall per consentire le connessioni da indirizzi IP di Office 365 sulla porta TCP 25 per i server di posta elettronica locale. Per un elenco di indirizzi IP di Office 365, vedere [Office 365 URL e intervalli di indirizzi IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p107">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="f2e9a-p108">Se non devono essere recapitati più messaggi nell'ambiente locale, fare clic su **Correggi ora** nell'avviso affinché Office 365 possa rifiutare immediatamente i messaggi con destinatari non validi. Questo consente di ridurre il rischio di superare la quota dell'organizzazione per i destinatari non validi, che possono compromettere il recapito dei messaggi normali. In alternativa, è possibile utilizzare le istruzioni seguenti per risolvere manualmente il problema:</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p108">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="f2e9a-141">Nell' [interfaccia di amministrazione di Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disattivare o eliminare il connettore che invia messaggio di posta elettronica da Office 365 all'ambiente di posta elettronica locale:</span><span class="sxs-lookup"><span data-stu-id="f2e9a-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="f2e9a-142">In EAC, andare a **flusso di posta** \> **connettori**.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="f2e9a-143">Selezionare il connettore con il valore **di** **Office 365** e il valore **per** **il server di posta elettronica dell'organizzazione** ed effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2e9a-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="f2e9a-144">Fare clic su **Elimina** per eliminare il connettore ![sull'icona Rimuovi](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="f2e9a-144">Delete the connector by clicking **Delete** ![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="f2e9a-145">Disabilitare il connettore, scegliendo **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) e deselezione **attivarlo**.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-145">Disable the connector by clicking **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="f2e9a-p109">Modificare il dominio accettato in Office 365 di cui è associato l'ambiente di posta elettronica locale di **Inoltro interno** su **autorevole**. Per ulteriori informazioni, vedere [Manage domini accettati in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p109">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="f2e9a-p110">**Nota**: hanno in genere, le modifiche tra 30 minuti e un'ora per rendere effettive. Dopo un'ora, verificare che non viene più visualizzato l'errore.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p110">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="f2e9a-150">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="f2e9a-151">Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="f2e9a-p111">Questo errore indica in genere, Office 365 connessi al server di posta elettronica di destinazione, ma il server ha restituito un errore immediato o non soddisfa i requisiti di connessione. I dettagli dell'errore verranno illustrato il problema. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p111">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="f2e9a-155">Server di posta elettronica di destinazione ha restituito un errore "Servizio non disponibile", che indica il server è in grado di mantenere la comunicazione con Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="f2e9a-156">Il connettore è configurato per richiedere TLS, ma il server di posta elettronica di destinazione non supporta TLS.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="f2e9a-157">Come è possibile risolvere il codice di errore 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="f2e9a-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="f2e9a-158">Verificare le impostazioni di TLS e dei certificati sui server di posta elettronica locale e le impostazioni di TLS sul connettore.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="f2e9a-159">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="f2e9a-160">Codice errore: 450 4.4.318 Connessione interrotta improvvisamente</span><span class="sxs-lookup"><span data-stu-id="f2e9a-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="f2e9a-p112">Questo errore indica in genere, che Office 365 è problemi nelle comunicazioni con l'ambiente di posta elettronica locale, in modo che la connessione è stata interrotta. Le possibili cause di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p112">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped. The possible causes for this error are:</span></span>

- <span data-ttu-id="f2e9a-163">Il firewall utilizza le regole di verifica del pacchetto SMTP e tali regole non funzionano correttamente.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="f2e9a-164">Il server di posta elettronica locale non lavorativi correttamente (ad esempio, servizio blocchi, arresti anomali o risorse di sistema), che ha causato il server non scada e chiudere la connessione a Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="f2e9a-165">Sono presenti errori di rete tra l'ambiente locale e Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="f2e9a-166">Come è possibile risolvere il codice di errore 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="f2e9a-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="f2e9a-167">Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="f2e9a-168">Se il problema è dovuto a problemi di rete tra l'ambiente locale e Office 365, rivolgersi al team di rete per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="f2e9a-169">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="f2e9a-170">Codice errore: 450 4.7.320 Convalida del certificato non riuscita</span><span class="sxs-lookup"><span data-stu-id="f2e9a-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="f2e9a-p113">Questo errore indica in genere, che Office 365 si è verificato un errore durante il tentativo di convalidare il certificato del server di posta elettronica di destinazione. I dettagli dell'errore verranno illustrato l'errore. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p113">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server. The error details will explain the error. For example:</span></span>

- <span data-ttu-id="f2e9a-174">Certificato scaduto</span><span class="sxs-lookup"><span data-stu-id="f2e9a-174">Certificate expired</span></span>

- <span data-ttu-id="f2e9a-175">Mancata corrispondenza oggetto certificato</span><span class="sxs-lookup"><span data-stu-id="f2e9a-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="f2e9a-176">Certificato non più valido</span><span class="sxs-lookup"><span data-stu-id="f2e9a-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="f2e9a-177">Come è possibile risolvere il codice di errore 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="f2e9a-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="f2e9a-178">Correggere il certificato o le impostazioni del connettore in modo che i messaggi in Office 365 in coda da recuperare.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="f2e9a-179">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="f2e9a-180">Altri codici errore</span><span class="sxs-lookup"><span data-stu-id="f2e9a-180">Other error codes</span></span>

<span data-ttu-id="f2e9a-p114">Office 365 è difficoltà il recapito dei messaggi in locale o server di posta elettronica di partner. Utilizzare le informazioni sul **server di destinazione** nel messaggio di errore per esaminare il problema nell'ambiente in uso o modificare il connettore se si verifica un errore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-p114">Office 365 is having difficulty delivering messages to your on-premises or partner email server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 

<span data-ttu-id="f2e9a-183">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="f2e9a-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
