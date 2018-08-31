---
title: Il modo in cui Office 365 convalida l'indirizzo da per impedire il phishing
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
description: 'Per evitare di phishing, Office 365 e Outlook.com ora richiesta la conformità con RFC per da: indirizzi.'
ms.openlocfilehash: 562e08aa54cb6544beccb6f0e8760735f67b834b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530240"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="58f4f-103">Il modo in cui Office 365 convalida l'indirizzo da per impedire il phishing</span><span class="sxs-lookup"><span data-stu-id="58f4f-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="58f4f-p101">Office 365 e account di posta elettronica Outlook.com ricevono un numero sempre più elevato di attacchi di phishing. Una tecnica autori utilizzano consiste nell'inviare i messaggi che contengono valori per il mittente: indirizzo che non è conforme a [RFC 5322](https://tools.ietf.org/html/rfc5322). From: indirizzo è denominato anche indirizzo 5322.From. Per evitare questo tipo di phishing, Office 365 e Outlook.com richiedono i messaggi ricevuti dal servizio per includere un conforme a RFC da: risolvere come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p101">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks. One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322). The From: address is also called the 5322.From address. To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58f4f-p102">Le informazioni contenute in questo articolo è necessario disporre di una conoscenza di base del formato generale di indirizzi di posta elettronica. Per ulteriori informazioni, vedere [RFC 5322](https://tools.ietf.org/html/rfc5322) (particolarmente sezioni 3.2.3, 3.4 e 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), nonché [3696 RFC](https://tools.ietf.org/html/rfc3696). In questo articolo viene illustrato l'applicazione dei criteri per l'indirizzo 5322.From. In questo articolo non relative all'indirizzo 5321.MailFrom.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p102">The information in this article requires you to have a basic understanding of the general format of email addresses. For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696). This article is about policy enforcement for the 5322.From address. This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="58f4f-p103">Purtroppo sono ancora presenti alcuni server di posta elettronica legacy su Internet che continuano a inviare "legittimi" messaggi di posta elettronica con un parametro mancante o non corretto da: indirizzo. Se si regolarmente ricezione della posta elettronica di organizzazioni che utilizzano questi sistemi legacy, incoraggiare tali organizzazioni per aggiornare i server di posta elettronica per essere conforme agli standard di protezione moderno.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p103">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address. If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="58f4f-114">Microsoft consente di avviare l'applicazione dei criteri descritti in questo articolo in 9 novembre 2017 distribuzione.</span><span class="sxs-lookup"><span data-stu-id="58f4f-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="58f4f-115">Come Office 365 prevede l'utilizzo di un oggetto valido da: indirizzo per impedire attacchi di phishing</span><span class="sxs-lookup"><span data-stu-id="58f4f-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="58f4f-p104">Office 365 apporta modifiche al modo in cui prevede l'utilizzo di From: indirizzo in i messaggi ricevuti in modo da impedire attacchi di phishing. In questo articolo:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p104">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks. In this article:</span></span>
  
- [<span data-ttu-id="58f4f-118">Tutti i messaggi devono includere un valido da: indirizzo</span><span class="sxs-lookup"><span data-stu-id="58f4f-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="58f4f-119">Tutti i messaggi devono includere un valido da: indirizzo</span><span class="sxs-lookup"><span data-stu-id="58f4f-119">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="58f4f-120">Formato di From: risolvere se non si include un nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="58f4f-120">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="58f4f-121">Formato di From: risolvere se si include un nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="58f4f-121">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="58f4f-122">Ulteriori esempi di valido e non validi dalla: indirizzi</span><span class="sxs-lookup"><span data-stu-id="58f4f-122">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="58f4f-123">Eliminare le risposte automatiche per il dominio personalizzato senza interrompere From: criteri</span><span class="sxs-lookup"><span data-stu-id="58f4f-123">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="58f4f-124">Eseguire l'override di Office 365 da: risolvere i criteri di applicazione</span><span class="sxs-lookup"><span data-stu-id="58f4f-124">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="58f4f-125">Altri modi per impedire e proteggendo cybercrimes in Office 365</span><span class="sxs-lookup"><span data-stu-id="58f4f-125">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="58f4f-126">Invia per conto di un altro utente non ha questa modifica, per ulteriori informazioni, leggere blog di Terry Zink "[cosa si intende quando si fa riferimento al mittente di un messaggio di posta elettronica?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="58f4f-126">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="58f4f-127">Tutti i messaggi devono includere un valido da: indirizzo</span><span class="sxs-lookup"><span data-stu-id="58f4f-127">All messages must include a valid From: address</span></span>
<span data-ttu-id="58f4f-128"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="58f4f-128"></span></span>

<span data-ttu-id="58f4f-p105">Alcuni messaggi automatici non includono un mittente: indirizzo quando vengono inviati. In passato, in Office 365 o Outlook.com ha ricevuto un messaggio senza un mittente: indirizzo, il servizio aggiunto predefinito riportato di seguito da: indirizzo per il messaggio per rendere risultato finale:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p105">Some automated messages don't include a From: address when they are sent. In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="58f4f-p106">Avviare il 9 novembre 2017 Office 365 verrà essere distribuzione modifiche per i server di datacenter e posta elettronica che determinerà una nuova regola di cui messaggi senza un mittente: indirizzo non più essere accettata da Office 365 o Outlook.com. In realtà, tutti i messaggi ricevuti da Office 365 devono già contenere valido da: indirizzo. In caso contrario, verrà inviato il messaggio alle cartelle di posta indesiderata o posta eliminata Outlook.com e Office 365.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p106">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com. Instead, all messages received by Office 365 must already contain a valid From: address. Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="58f4f-134">Panoramica della sintassi: formato valido per il mittente: indirizzo per Office 365</span><span class="sxs-lookup"><span data-stu-id="58f4f-134">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="58f4f-135"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="58f4f-135"></span></span>

<span data-ttu-id="58f4f-p107">Il formato del valore di From: indirizzo definito in modo dettagliato tra le diverse. Esistono molti le varianti di indirizzamento e ciò che può essere considerato valido o non validi. Per mantenere semplice, si consiglia di utilizzare le definizioni e il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p107">The format for the value of the From: address is defined in detail across several RFCs. There are many variations on addressing and what may be considered valid or invalid. To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="58f4f-139">Dove:</span><span class="sxs-lookup"><span data-stu-id="58f4f-139">Where:</span></span>
  
- <span data-ttu-id="58f4f-p108">(Facoltativo)  *DisplayName* è una frase che descrive il proprietario dell'indirizzo di posta elettronica. Ad esempio, può essere un nome descrittivo per descrivere il mittente rispetto al nome della cassetta postale. Utilizzo di un nome visualizzato è facoltativo. Tuttavia, se si sceglie di utilizzare un nome visualizzato, è consigliabile che è sempre racchiuderlo tra virgolette come indicato.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p108">(Optional)  *displayname*  is a phrase that describes the owner of the email address. For example, this might be a more user-friendly name to describe the sender than the name of the mailbox. Using a display name is optional. However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="58f4f-144">(Obbligatorio)  *EmailAddress* è costituito da:</span><span class="sxs-lookup"><span data-stu-id="58f4f-144">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="58f4f-145">Dove:</span><span class="sxs-lookup"><span data-stu-id="58f4f-145">Where:</span></span>
    
  - <span data-ttu-id="58f4f-p109">(Obbligatorio)  *la parte locale* è una stringa che identifica la cassetta postale associata all'indirizzo. È univoco all'interno del dominio. Spesso, nome utente o il GUID del proprietario della cassetta postale viene utilizzato come valore per la parte locale.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p109">(Required)  *local-part*  is a string that identifies the mailbox associated with the address. This is unique within the domain. Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="58f4f-149">(Obbligatorio)  *dominio* è il nome di dominio completo (FQDN) del server di posta che ospita la cassetta postale identificata dalla parte locale dell'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="58f4f-149">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="58f4f-150">Formato di From: risolvere se non si include un nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="58f4f-150">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="58f4f-151"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="58f4f-151"></span></span>

<span data-ttu-id="58f4f-p110">A formattata correttamente rispetto a: indirizzo che non include un nome visualizzato include solo un indirizzo di posta elettronica singolo con o senza uncinate. Si consiglia di non separare le parentesi angolari con spazi. Inoltre, non includere lasciare dopo l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p110">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets. Microsoft recommends that you do not separate the angle brackets with spaces. In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="58f4f-155">Negli esempi seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="58f4f-155">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="58f4f-156">Nell'esempio seguente è valido, ma non consigliata perché contiene spazi tra le parentesi angolari e l'indirizzo di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="58f4f-156">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="58f4f-157">Nell'esempio seguente non è valido perché contiene testo dopo l'indirizzo di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="58f4f-157">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="58f4f-158">Formato di From: risolvere se si include un nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="58f4f-158">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="58f4f-159"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="58f4f-159"></span></span>

<span data-ttu-id="58f4f-160">Per da: gli indirizzi che includono un valore per il nome visualizzato, applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="58f4f-160">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="58f4f-p111">Se l'indirizzo del mittente include un nome visualizzato e il nome visualizzato include una virgola, quindi il nome visualizzato deve essere racchiuso tra virgolette. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p111">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks. For example:</span></span>
    
    <span data-ttu-id="58f4f-163">Nell'esempio seguente è valido:</span><span class="sxs-lookup"><span data-stu-id="58f4f-163">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="58f4f-164">Nell'esempio seguente non è valido:</span><span class="sxs-lookup"><span data-stu-id="58f4f-164">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="58f4f-165">Non è valido in base alla RFC 5322 non che racchiudono il nome visualizzato tra virgolette se il nome visualizzato include una virgola.</span><span class="sxs-lookup"><span data-stu-id="58f4f-165">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="58f4f-166">È consigliabile mettere virgolette racchiudere il nome visualizzato indipendentemente dall'utente se non esiste o è una virgola tra il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="58f4f-166">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="58f4f-167">Se l'indirizzo del mittente include un nome visualizzato, l'indirizzo di posta elettronica deve essere racchiusi tra parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="58f4f-167">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="58f4f-168">Come procedura consigliata, si consiglia si inserisce uno spazio tra il nome visualizzato e l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="58f4f-168">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="58f4f-169">Ulteriori esempi di valido e non validi dalla: indirizzi</span><span class="sxs-lookup"><span data-stu-id="58f4f-169">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="58f4f-170"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="58f4f-170"></span></span>

- <span data-ttu-id="58f4f-171">Valido:</span><span class="sxs-lookup"><span data-stu-id="58f4f-171">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="58f4f-p112">Non valido. L'indirizzo di posta elettronica non racchiusi tra parentesi angolari:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p112">Invalid. The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="58f4f-p113">Valido, ma non consigliato. Il nome visualizzato non è racchiuso tra virgolette. Come procedura consigliata, posizionare sempre il nome visualizzato tra virgolette:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p113">Valid, but not recommended. The display name is not in quotes. As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="58f4f-p114">Non valido. Tutto il contenuto è racchiuso tra virgolette, non solo il nome visualizzato:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p114">Invalid. Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="58f4f-p115">Non valido. Non esistono angolari intorno l'indirizzo di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p115">Invalid. There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="58f4f-p116">Non valido. Non è disponibile spazio tra il nome visualizzato e parentesi uncinata aperta:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p116">Invalid. There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="58f4f-p117">Non valido. Non è disponibile spazio tra parentesi uncinata e quotation mark chiusura intorno il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p117">Invalid. There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="58f4f-185">Eliminare le risposte automatiche per il dominio personalizzato senza interrompere From: criteri</span><span class="sxs-lookup"><span data-stu-id="58f4f-185">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="58f4f-186"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="58f4f-186"></span></span>

<span data-ttu-id="58f4f-p118">Con la nuova da: applicazione dei criteri, non è più utilizzabili da: \< \> eliminare le risposte automatiche. In realtà, è necessario configurare un record MX null per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p118">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies. Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="58f4f-p119">Il record mail exchanger (MX) è un record di risorse nel sistema DNS che identifica il server di posta elettronica che riceve la posta per il dominio. Le risposte automatiche (e tutte le risposte) naturalmente vengono eliminate dal momento che nessun indirizzo pubblicato a cui il server di risposta può inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p119">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain. Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="58f4f-191">Quando si imposta un record MX null per il dominio personalizzato:</span><span class="sxs-lookup"><span data-stu-id="58f4f-191">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="58f4f-p120">Scegliere un dominio da cui si desidera inviare i messaggi che non accetta (ricezione) posta elettronica. Ad esempio, se il dominio primario è contoso.com, è possibile scegliere noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p120">Choose a domain from which to send messages that doesn't accept (receive) email. For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="58f4f-p121">Consente di impostare il record MX null per il dominio. Un record MX null costituito da un punto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="58f4f-p121">Set up the null MX record for your domain. A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="58f4f-196">Per ulteriori informazioni sulla pubblicazione di un MX null, vedere [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="58f4f-196">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="58f4f-197">Eseguire l'override di Office 365 da: risolvere i criteri di applicazione</span><span class="sxs-lookup"><span data-stu-id="58f4f-197">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="58f4f-198"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="58f4f-198"></span></span>

<span data-ttu-id="58f4f-199">Una volta (in inglese) completamente il nuovo criterio, è possibile ignorare solo questo criterio per la posta in ingresso che proveniente da Office 365 utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="58f4f-199">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="58f4f-200">Elenchi di indirizzi IP consentiti</span><span class="sxs-lookup"><span data-stu-id="58f4f-200">IP allow lists</span></span>
    
- <span data-ttu-id="58f4f-201">Regole del flusso di posta elettronica Exchange Online</span><span class="sxs-lookup"><span data-stu-id="58f4f-201">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="58f4f-p122">Si consiglia di base viene sottoposto a override l'applicazione di From: criterio. Eseguire l'override di questo criterio possono aumentare rischio dell'organizzazione di esposizione alla posta indesiderata e phishing altri cybercrimes.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p122">Microsoft strongly recommends against overriding the enforcement of the From: policy. Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="58f4f-p123">Non è possibile ignorare questo criterio per la posta in uscita inviati in Office 365. Inoltre, Outlook.com non consente le sostituzioni di alcun tipo, anche tramite il supporto.</span><span class="sxs-lookup"><span data-stu-id="58f4f-p123">You cannot override this policy for outbound mail you send in Office 365. In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="58f4f-206">Altri modi per impedire e proteggendo cybercrimes in Office 365</span><span class="sxs-lookup"><span data-stu-id="58f4f-206">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="58f4f-207"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="58f4f-207"></span></span>

<span data-ttu-id="58f4f-208">Per ulteriori informazioni su come è possibile aumentare il livello dell'organizzazione con cybercrimes come phishing, questi comportamenti, le violazioni di dati e altri rischi, vedere [le procedure consigliate per Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span><span class="sxs-lookup"><span data-stu-id="58f4f-208">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="58f4f-209">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="58f4f-209">Related Topics</span></span>

[<span data-ttu-id="58f4f-210">Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP</span><span class="sxs-lookup"><span data-stu-id="58f4f-210">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

