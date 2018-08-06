---
title: Business intelligence di flusso di posta elettronica in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: "In genere si utilizza un connettore per instradare i messaggi dalla organizzazione Office 365 per locale ambiente di messaggistica. È inoltre possibile utilizzare un connettore per instradare i messaggi da Office 365 a un'organizzazione partner. Quando Office 365 non è in grado di distribuire questi messaggi attraverso il connettore, sta accodate in Office 365. "
ms.openlocfilehash: 495d73524afb3ab3a34fd2f1f5f4cd747481f9d8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027623"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="0a111-105">Business intelligence di flusso di posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="0a111-105">Mail flow intelligence in Office 365</span></span>
  
<span data-ttu-id="0a111-p102">In genere, si usa un connettore per instradare i messaggi dall'organizzazione di Office 365 all'ambiente di messaggistica locale. È anche possibile usare un connettore per instradare i messaggi da Office 365 a un'organizzazione partner. Quando Office 365 non è in grado di recapitare tali messaggi attraverso il connettore, questi ultimi vengono messi in coda in Office 365. Office 365 proverà a ripetere il recapito di ogni messaggio per 48 ore. Dopo 48 ore, il messaggio nella coda scade e viene inviato di nuovo al mittente originale tramite un rapporto di mancato recapito (detto anche NDR o notifica di mancato recapito).</span><span class="sxs-lookup"><span data-stu-id="0a111-p102">Typically, you use a connector to route messages from your Office 365 organization to your on-premises messaging environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>
  
<span data-ttu-id="0a111-p103">Office 365 genera un errore quando un messaggio non può essere recapitato utilizzando un connettore. In questo argomento sono descritti gli errori più comuni e le relative soluzioni. Nell'insieme, gli errori relativi alle code e alle notifiche dei messaggi non recapitabili inviati tramite il connettore sono noti come intelligence del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="0a111-p103">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as mailflow intelligence.</span></span>
  
 <span data-ttu-id="0a111-114">**Sommario**</span><span class="sxs-lookup"><span data-stu-id="0a111-114">**Contents**</span></span>
  
- [<span data-ttu-id="0a111-115">Codice errore: 450 4.4.312 Query DNS non riuscita</span><span class="sxs-lookup"><span data-stu-id="0a111-115">Error code: 450 4.4.312 DNS query failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [<span data-ttu-id="0a111-116">Codice errore: 450 4.4.315 Timeout della connessione</span><span class="sxs-lookup"><span data-stu-id="0a111-116">Error code: 450 4.4.315 Connection timed out</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [<span data-ttu-id="0a111-117">Codice errore: 450 4.4.316 Connessione rifiutata</span><span class="sxs-lookup"><span data-stu-id="0a111-117">Error code: 450 4.4.316 Connection refused</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [<span data-ttu-id="0a111-118">Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.</span><span class="sxs-lookup"><span data-stu-id="0a111-118">Error code: 450 4.4.317 Cannot connect to remote server</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [<span data-ttu-id="0a111-119">Codice errore: 450 4.4.318 Connessione interrotta improvvisamente</span><span class="sxs-lookup"><span data-stu-id="0a111-119">Error code: 450 4.4.318 Connection was closed abruptly</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [<span data-ttu-id="0a111-120">Codice errore: 450 4.7.320 Convalida del certificato non riuscita</span><span class="sxs-lookup"><span data-stu-id="0a111-120">Error code: 450 4.7.320 Certificate validation failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="0a111-121">Codice errore: 450 4.4.312 Query DNS non riuscita</span><span class="sxs-lookup"><span data-stu-id="0a111-121">Error code: 450 4.4.312 DNS query failed</span></span>
<span data-ttu-id="0a111-122"><a name="ErrorCode44312"> </a></span><span class="sxs-lookup"><span data-stu-id="0a111-122"></span></span>

<span data-ttu-id="0a111-p104">In genere questo errore indica che Office 365 ha tentato di connettersi allo smart host specificato nel connettore, ma la query DNS di ricerca degli indirizzi IP dello smart host ha avuto esito negativo. Alcune possibili cause di questo errore:</span><span class="sxs-lookup"><span data-stu-id="0a111-p104">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host IP addresses failed. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="0a111-125">Si è verificato un errore relativo al servizio di hosting DNS del proprio dominio (la terza parte che gestisce i server dei nomi autorevoli per il dominio).</span><span class="sxs-lookup"><span data-stu-id="0a111-125">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>
    
- <span data-ttu-id="0a111-126">Di recente, il dominio è scaduto e di conseguenza il record MX non può essere recuperato.</span><span class="sxs-lookup"><span data-stu-id="0a111-126">Your domain has recently expired, so the MX record can't be retrieved.</span></span>
    
- <span data-ttu-id="0a111-127">Il record MX del dominio è stato recentemente modificato e i server DNS di Office 365 hanno ancora le informazioni DNS memorizzate in precedenza per il dominio.</span><span class="sxs-lookup"><span data-stu-id="0a111-127">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>
    
<span data-ttu-id="0a111-128">È necessario risolvere il problema del DNS insieme agli addetti del servizio di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="0a111-128">You need to fix the DNS issue by working with your DNS hosting service.</span></span>
  
<span data-ttu-id="0a111-129">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="0a111-129">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="0a111-130">Codice errore: 450 4.4.315 Timeout della connessione</span><span class="sxs-lookup"><span data-stu-id="0a111-130">Error code: 450 4.4.315 Connection timed out</span></span>
<span data-ttu-id="0a111-131"><a name="ErrorCode44315"> </a></span><span class="sxs-lookup"><span data-stu-id="0a111-131"></span></span>

<span data-ttu-id="0a111-p105">In genere, ciò indica che Office 365 non è riuscito a connettersi al server di messaggistica di destinazione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0a111-p105">Typically, this means Office 365 can't connect to the destination messaging server. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="0a111-135">Il server di messaggistica locale è inattivo.</span><span class="sxs-lookup"><span data-stu-id="0a111-135">Your on-premises messaging server is down.</span></span>
    
- <span data-ttu-id="0a111-136">Si è verificato un errore relativo alle impostazione dello smart host del connettore, quindi Office 365 prova a connettersi all'indirizzo IP sbagliato.</span><span class="sxs-lookup"><span data-stu-id="0a111-136">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>
    
<span data-ttu-id="0a111-p106">Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni. Ad esempio, se il flusso di posta non presenta problemi e non sono state modificate le impostazioni del connettore, è necessario controllare l'ambiente di messaggistica locale al fine di verificare se il server è inattivo oppure se sono state apportate modifiche all'infrastruttura di rete (ad esempio, sono stati modificati i provider dei servizi Internet e di conseguenza si hanno indirizzi IP diversi).</span><span class="sxs-lookup"><span data-stu-id="0a111-p106">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises messaging environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed Internet service providers, so you now have different IP addresses).</span></span>
  
<span data-ttu-id="0a111-139">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="0a111-139">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="0a111-140">Codice errore: 450 4.4.316 Connessione rifiutata</span><span class="sxs-lookup"><span data-stu-id="0a111-140">Error code: 450 4.4.316 Connection refused</span></span>
<span data-ttu-id="0a111-141"><a name="ErrorCode44316"> </a></span><span class="sxs-lookup"><span data-stu-id="0a111-141"></span></span>

<span data-ttu-id="0a111-p107">In genere, questo errore indica che Office 365 ha riscontrato un errore di connessione quando ha provato a connettersi al server di messaggistica di destinazione. Una delle probabili cause di questo errore è la presenza di un firewall che blocca le connessioni dagli indirizzi IP di Office 365. In alternativa, questo errore potrebbe dipendere dalla progettazione se il sistema di messaggistica locale è stato migrato completamente in Office 365 ed è stato arrestato l'ambiente di messaggistica locale.</span><span class="sxs-lookup"><span data-stu-id="0a111-p107">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination messaging server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises messaging system to Office 365 and shut down your on-premises messaging environment..</span></span>
  
- <span data-ttu-id="0a111-p108">Se si dispone di più cassette postali nell'ambiente locale, è necessario modificare le impostazioni del firewall per consentire connessioni dagli indirizzi IP di Office 365 sulla porta TCP 25 ai server di messaggistica locali. Per visualizzare un elenco degli indirizzi IP di Office 365, vedere [URL e intervalli di indirizzi IP per Office 365](https://go.microsoft.com/fwlink/p/?linkid=228887).</span><span class="sxs-lookup"><span data-stu-id="0a111-p108">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises messaging servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=228887).</span></span>
    
- <span data-ttu-id="0a111-p109">Se non devono essere recapitati più messaggi nell'ambiente locale, fare clic su **Correggi ora** nell'avviso affinché Office 365 possa rifiutare immediatamente i messaggi con destinatari non validi. Questo consente di ridurre il rischio di superare la quota dell'organizzazione per i destinatari non validi, che possono compromettere il recapito dei messaggi normali. In alternativa, è possibile utilizzare le istruzioni seguenti per risolvere manualmente il problema:</span><span class="sxs-lookup"><span data-stu-id="0a111-p109">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span> 
    
  - <span data-ttu-id="0a111-p110">Disabilitare o eliminare il connettore da Office 365 nell'ambiente locale: interfaccia di amministrazione di Office 365 \> **Interfacce di amministrazione** \> **Exchange** \> **Flusso di posta** \> **Connettori** \> selezionare il connettore con il valore **From** come **Office 365** e il valore **To** come **Server di posta elettronica dell'organizzazione**. Eliminare il connettore facendo clic su **Elimina**![Icona Elimina](media/ITPro-EAC-DeleteIcon.png) oppure disabilitare il connettore facendo clic su **Modifica**![Icona Modifica](media/ITPro-EAC-EditIcon.png) e deselezionando **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="0a111-p110">Disable or delete the connector from Office 365 to your on-premises environment: Office 365 admin center \> **Admin centers** \> **Exchange** \> **Mail flow** \> **Connectors** \> select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server**. Delete the connector by clicking **Delete**![Delete icon](media/ITPro-EAC-DeleteIcon.png), or disable the connector by clicking **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png) and unchecking **Turn it on**.</span></span>
    
  - <span data-ttu-id="0a111-p111">Modificare il dominio accettato in Office 365 che è associato all'ambiente di messaggistica locale da **Inoltro interno** ad **Autorevole**. Per istruzioni, vedere [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).</span><span class="sxs-lookup"><span data-stu-id="0a111-p111">Change the accepted domain in Office 365 that's associated with your on-premises messaging environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).</span></span>
    
    <span data-ttu-id="0a111-p112">**Nota**: hanno in genere, le modifiche tra 30 minuti e un'ora per rendere effettive. Dopo un'ora, verificare che non viene più visualizzato l'errore.</span><span class="sxs-lookup"><span data-stu-id="0a111-p112">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>
    
<span data-ttu-id="0a111-156">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="0a111-156">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="0a111-157">Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.</span><span class="sxs-lookup"><span data-stu-id="0a111-157">Error code: 450 4.4.317 Cannot connect to remote server</span></span>
<span data-ttu-id="0a111-158"><a name="ErrorCode44317"> </a></span><span class="sxs-lookup"><span data-stu-id="0a111-158"></span></span>

<span data-ttu-id="0a111-p113">In genere, questo errore indica che Office 365 ha stabilito la connessione al server di messaggistica di destinazione, ma il server ha risposto con un errore immediato oppure non ha soddisfatto i requisiti di connessione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0a111-p113">Typically, this error means Office 365 connected to the destination messaging server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="0a111-162">Il server di messaggistica di destinazione ha generato l'errore "Servizio non disponibile", che indica che il server non riesce a mantenere la comunicazione con Office 365.</span><span class="sxs-lookup"><span data-stu-id="0a111-162">The destination messaging server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>
    
- <span data-ttu-id="0a111-163">Il connettore viene configurato in modo che necessiti di TLS, ma il server di messaggistica di destinazione non supporta TLS.</span><span class="sxs-lookup"><span data-stu-id="0a111-163">The connector is configured to require TLS, but the destination messaging server doesn't support TLS.</span></span>
    
<span data-ttu-id="0a111-164">Verificare le impostazioni di TLS e dei certificati nei server di messaggistica locale e le impostazioni TLS sul connettore.</span><span class="sxs-lookup"><span data-stu-id="0a111-164">Verify the TLS settings and certificates on your on-premises messaging servers, and the TLS settings on the connector.</span></span>
  
<span data-ttu-id="0a111-165">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="0a111-165">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="0a111-166">Codice errore: 450 4.4.318 Connessione interrotta improvvisamente</span><span class="sxs-lookup"><span data-stu-id="0a111-166">Error code: 450 4.4.318 Connection was closed abruptly</span></span>
<span data-ttu-id="0a111-167"><a name="ErrorCode44318"> </a></span><span class="sxs-lookup"><span data-stu-id="0a111-167"></span></span>

<span data-ttu-id="0a111-p114">In genere, questo errore indica che Office 365 non riesce a comunicare con l'ambiente di messaggistica locale dell'utente, quindi la connessione viene interrotta. Alcune possibili cause di questo errore:</span><span class="sxs-lookup"><span data-stu-id="0a111-p114">Typically, this error means Office 365 is having difficulty communicating with your on-premises messaging environment, so the connection was dropped. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="0a111-170">Il firewall utilizza le regole di verifica del pacchetto SMTP e tali regole non funzionano correttamente.</span><span class="sxs-lookup"><span data-stu-id="0a111-170">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>
    
- <span data-ttu-id="0a111-171">Il server di messaggistica locale non funziona correttamente (ad esempio, il servizio si blocca, si arresta in modo anomalo oppure rallenta le risorse del sistema) e causa il timeout del server e l'interruzione della connessione a Office 365.</span><span class="sxs-lookup"><span data-stu-id="0a111-171">Your on-premises messaging server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>
    
- <span data-ttu-id="0a111-p115">Sono presenti errori di rete tra l'ambiente locale e Office 365. Se il problema persiste, rivolgersi al team di rete per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="0a111-p115">There are network issues between your on-premises environment and Office 365. If the problem persists, contact your network team to troubleshoot the issue.</span></span>
    
<span data-ttu-id="0a111-174">Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni.</span><span class="sxs-lookup"><span data-stu-id="0a111-174">Find out which scenario applies to you, and make the necessary corrections.</span></span>
  
<span data-ttu-id="0a111-175">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="0a111-175">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="0a111-176">Codice errore: 450 4.7.320 Convalida del certificato non riuscita</span><span class="sxs-lookup"><span data-stu-id="0a111-176">Error code: 450 4.7.320 Certificate validation failed</span></span>
<span data-ttu-id="0a111-177"><a name="ErrorCode47320"> </a></span><span class="sxs-lookup"><span data-stu-id="0a111-177"></span></span>

<span data-ttu-id="0a111-p116">In genere, questo errore indica che Office 365 ha riscontrato un errore quando ha provato a convalidare il certificato del server di messaggistica di destinazione. Nei dettagli dell'errore è riportata una sua spiegazione. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0a111-p116">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination messaging server. The error details will explain the error. For example:</span></span>
  
- <span data-ttu-id="0a111-181">Certificato scaduto</span><span class="sxs-lookup"><span data-stu-id="0a111-181">Certificate expired</span></span>
    
- <span data-ttu-id="0a111-182">Mancata corrispondenza oggetto certificato</span><span class="sxs-lookup"><span data-stu-id="0a111-182">Certificate subject mismatch</span></span>
    
- <span data-ttu-id="0a111-183">Certificato non più valido</span><span class="sxs-lookup"><span data-stu-id="0a111-183">Certificate is no longer valid</span></span>
    
<span data-ttu-id="0a111-184">Correggere il certificato o il connettore in modo che i messaggi nella coda di Office 365 possano essere recapitati.</span><span class="sxs-lookup"><span data-stu-id="0a111-184">Please fix the certificate or the connector so that queued messages in Office 365can be delivered.</span></span>
  
<span data-ttu-id="0a111-185">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="0a111-185">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="other-error-codes"></a><span data-ttu-id="0a111-186">Altri codici errore</span><span class="sxs-lookup"><span data-stu-id="0a111-186">Other error codes</span></span>
<span data-ttu-id="0a111-187"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="0a111-187"></span></span>

<span data-ttu-id="0a111-p117">Office 365 non riesce a recapitare i messaggi al server di messaggistica partner o locale. Utilizzare le informazioni **Server di destinazione** nell'errore per esaminare l'errore nel proprio ambiente o per modificare il connettore in presenza di un errore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0a111-p117">Office 365 is having difficulty delivering messages to your on-premises or partner messaging server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 
  
<span data-ttu-id="0a111-190">Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="0a111-190">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  

