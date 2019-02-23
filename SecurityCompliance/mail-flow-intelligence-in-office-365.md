---
title: Business intelligence di flusso di posta elettronica in Office 365
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Gli amministratori possono ottenere informazioni sui codici di errore associati al recapito dei messaggi utilizzando i connettori di Office 365 (noto anche come Intelligence del flusso di posta).
ms.openlocfilehash: a679a3a50c2333a9f66509b69ec06ee96960bc83
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218716"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="c9ba2-103">Business intelligence di flusso di posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="c9ba2-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="c9ba2-p101">In genere, si utilizza un connettore per instradare i messaggi di posta elettronica dall'organizzazione di Office 365 all'ambiente di posta elettronica locale. È inoltre possibile utilizzare un connettore per instradare i messaggi da Office 365 a un'organizzazione partner. Quando Office 365 non è in grado di recapitare questi messaggi tramite il connettore, vengono accodati in Office 365. Office 365 continuerà a riprovare il recapito per ogni messaggio per 48 ore. Dopo 48 ore, il messaggio in coda scadrà e il messaggio verrà restituito al mittente originale in un rapporto di mancato recapito (noto anche come NDR o messaggio di rimbalzo).</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p101">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="c9ba2-p102">Office 365 genera un errore quando un messaggio non può essere recapitato utilizzando un connettore. Gli errori più comuni e le relative soluzioni sono descritti in questo argomento. Gli errori di Accodamento e di notifica per i messaggi non recapitabili inviati tramite connettori sono noti come _Intelligence del flusso di posta_.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p102">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="c9ba2-112">Codice errore: 450 4.4.312 Query DNS non riuscita</span><span class="sxs-lookup"><span data-stu-id="c9ba2-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="c9ba2-p103">In genere, questo errore indica che Office 365 ha tentato di connettersi allo smart host specificato nel connettore, ma la query DNS per individuare gli indirizzi IP dello smart host ha avuto esito negativo. Le possibili cause di questo errore sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p103">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed. The possible causes for this error are:</span></span>

- <span data-ttu-id="c9ba2-115">Si è verificato un errore relativo al servizio di hosting DNS del proprio dominio (la terza parte che gestisce i server dei nomi autorevoli per il dominio).</span><span class="sxs-lookup"><span data-stu-id="c9ba2-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="c9ba2-116">Di recente, il dominio è scaduto e di conseguenza il record MX non può essere recuperato.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="c9ba2-117">Il record MX del dominio è stato recentemente modificato e i server DNS di Office 365 hanno ancora le informazioni DNS memorizzate in precedenza per il dominio.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="c9ba2-118">Come risolvere il codice di errore 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="c9ba2-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="c9ba2-119">Collaborare con il servizio di hosting DNS per identificare e risolvere il problema con il dominio.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="c9ba2-120">Se l'errore è dell'organizzazione partner (ad esempio, un provider di servizi cloud di terze parti), contattare il partner per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="c9ba2-121">Codice errore: 450 4.4.315 Timeout della connessione</span><span class="sxs-lookup"><span data-stu-id="c9ba2-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="c9ba2-p104">In genere, questo significa che Office 365 non è in grado di connettersi al server di posta elettronica di destinazione. I dettagli dell'errore spiegheranno il problema. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p104">Typically, this means Office 365 can't connect to the destination email server. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="c9ba2-125">Il server di posta elettronica locale è inattiva.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="c9ba2-126">Si è verificato un errore relativo alle impostazione dello smart host del connettore, quindi Office 365 prova a connettersi all'indirizzo IP sbagliato.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="c9ba2-127">Come risolvere il codice di errore 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="c9ba2-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="c9ba2-p105">Individuare lo scenario che si applica all'utente e apportare le correzioni necessarie. Ad esempio, se il flusso di posta funziona correttamente e non sono state modificate le impostazioni del connettore, è necessario controllare l'ambiente di posta elettronica locale per verificare se il server è inattivo o se sono state apportate modifiche all'infrastruttura di rete (ad esempio, sono stati modificati i provider di servizi Internet, quindi sono presenti diversi indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p105">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="c9ba2-130">Se l'errore è dell'organizzazione partner (ad esempio, un provider di servizi cloud di terze parti), contattare il partner per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="c9ba2-131">Codice errore: 450 4.4.316 Connessione rifiutata</span><span class="sxs-lookup"><span data-stu-id="c9ba2-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="c9ba2-p106">In genere, questo errore indica che Office 365 ha riscontrato un errore di connessione quando ha tentato di connettersi al server di posta elettronica di destinazione. Una probabile causa di questo errore è che il firewall sta bloccando le connessioni dagli indirizzi IP di Office 365. In alternativa, questo errore potrebbe essere dovuto alla progettazione se la migrazione del sistema di posta elettronica locale è stata completata in Office 365 e arrestare l'ambiente di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p106">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="c9ba2-135">Come risolvere il codice di errore 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="c9ba2-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="c9ba2-p107">Se si dispone di cassette postali nell'ambiente locale, è necessario modificare le impostazioni del firewall per consentire le connessioni dagli indirizzi IP di Office 365 sulla porta TCP 25 ai server di posta elettronica locali. Per un elenco degli indirizzi IP di Office 365, vedere [URL e intervalli di indirizzi IP di office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p107">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="c9ba2-p108">Se non devono essere recapitati più messaggi nell'ambiente locale, fare clic su **Correggi ora** nell'avviso affinché Office 365 possa rifiutare immediatamente i messaggi con destinatari non validi. Questo consente di ridurre il rischio di superare la quota dell'organizzazione per i destinatari non validi, che possono compromettere il recapito dei messaggi normali. In alternativa, è possibile utilizzare le istruzioni seguenti per risolvere manualmente il problema:</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p108">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="c9ba2-141">Nell'interfaccia di [amministrazione di Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disabilitare o eliminare il connettore che invia messaggi di posta elettronica da Office 365 all'ambiente di posta elettronica locale:</span><span class="sxs-lookup"><span data-stu-id="c9ba2-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="c9ba2-142">Nell'interfaccia di amministrazione di Exchange, andare a **connettori**del **flusso** \> di posta.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="c9ba2-143">Selezionare il connettore con il \*\*\*\* valore da **Office 365** e il valore **per** il **server di posta elettronica dell'organizzazione** ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ba2-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="c9ba2-144">Eliminare il connettore facendo clic su **Elimina** ![icona Rimuovi](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="c9ba2-144">Delete the connector by clicking **Delete** ![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="c9ba2-145">Disabilitare il connettore facendo clic su **modifica** ![icona](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) modifica e deselezionando **attiva**.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-145">Disable the connector by clicking **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="c9ba2-p109">Modificare il dominio accettato in Office 365 associato all'ambiente di posta elettronica locale dall' **inoltro interno** a autorevole. \*\*\*\* Per istruzioni, vedere [Manage Accepted Domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p109">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="c9ba2-p110">**Nota**: in genere, queste modifiche impiegano tra 30 minuti e un'ora per rendere effettive le operazioni. Dopo un'ora, verificare che l'errore non sia più stato ricevuto.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p110">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="c9ba2-150">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="c9ba2-151">Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="c9ba2-p111">In genere, questo errore indica che Office 365 è connesso al server di posta elettronica di destinazione, ma il server ha risposto con un errore immediato o non soddisfa i requisiti di connessione. I dettagli dell'errore spiegheranno il problema. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p111">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="c9ba2-155">Il server di posta elettronica di destinazione ha risposto con un messaggio di errore "servizio non disponibile", che indica che il server non è in grado di mantenere la comunicazione con Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="c9ba2-156">Il connettore è configurato per richiedere TLS, ma il server di posta elettronica di destinazione non supporta TLS.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="c9ba2-157">Come risolvere il codice di errore 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="c9ba2-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="c9ba2-158">Verificare le impostazioni e i certificati TLS nei server di posta elettronica locali e le impostazioni TLS sul connettore.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="c9ba2-159">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="c9ba2-160">Codice errore: 450 4.4.318 Connessione interrotta improvvisamente</span><span class="sxs-lookup"><span data-stu-id="c9ba2-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="c9ba2-p112">In genere, questo errore indica che Office 365 ha difficoltà a comunicare con l'ambiente di posta elettronica locale, in modo che la connessione sia stata eliminata. Le possibili cause di questo errore sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p112">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped. The possible causes for this error are:</span></span>

- <span data-ttu-id="c9ba2-163">Il firewall utilizza le regole di verifica del pacchetto SMTP e tali regole non funzionano correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="c9ba2-164">Il server di posta elettronica locale non funziona correttamente (ad esempio, il servizio si blocca, si arresta in modo anomalo o con risorse di sistema ridotte), causando il timeout del server e la chiusura della connessione a Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="c9ba2-165">Sono presenti errori di rete tra l'ambiente locale e Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="c9ba2-166">Come risolvere il codice di errore 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="c9ba2-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="c9ba2-167">Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="c9ba2-168">Se il problema è causato da problemi di rete tra l'ambiente locale e Office 365, contattare il team di rete per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="c9ba2-169">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="c9ba2-170">Codice errore: 450 4.7.320 Convalida del certificato non riuscita</span><span class="sxs-lookup"><span data-stu-id="c9ba2-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="c9ba2-p113">In genere, questo errore indica che Office 365 ha riscontrato un errore durante il tentativo di convalidare il certificato del server di posta elettronica di destinazione. I dettagli dell'errore spiegheranno l'errore. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p113">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server. The error details will explain the error. For example:</span></span>

- <span data-ttu-id="c9ba2-174">Certificato scaduto</span><span class="sxs-lookup"><span data-stu-id="c9ba2-174">Certificate expired</span></span>

- <span data-ttu-id="c9ba2-175">Mancata corrispondenza oggetto certificato</span><span class="sxs-lookup"><span data-stu-id="c9ba2-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="c9ba2-176">Certificato non più valido</span><span class="sxs-lookup"><span data-stu-id="c9ba2-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="c9ba2-177">Come risolvere il codice di errore 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="c9ba2-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="c9ba2-178">Consente di risolvere il certificato o le impostazioni sul connettore in modo che i messaggi in coda in Office 365 possano essere recapitati.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="c9ba2-179">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="c9ba2-180">Altri codici errore</span><span class="sxs-lookup"><span data-stu-id="c9ba2-180">Other error codes</span></span>

<span data-ttu-id="c9ba2-p114">Office 365 ha difficoltà a recapitare i messaggi al server di posta elettronica locale o partner. Utilizzare le informazioni sul **server di destinazione** nell'errore per esaminare il problema nell'ambiente o modificare il connettore se si verifica un errore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-p114">Office 365 is having difficulty delivering messages to your on-premises or partner email server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 

<span data-ttu-id="c9ba2-183">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
