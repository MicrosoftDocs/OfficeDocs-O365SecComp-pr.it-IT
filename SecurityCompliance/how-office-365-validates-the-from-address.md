---
title: Come Office 365 convalida l'indirizzo mittente per impedire il phishing
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Per evitare il phishing, Office 365 e Outlook.com ora richiedono la conformità RFC per gli indirizzi da:.
ms.openlocfilehash: e540e56a7a40d13a92719865fccefefa61de47c2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253934"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="0a62a-103">Come Office 365 convalida l'indirizzo mittente per impedire il phishing</span><span class="sxs-lookup"><span data-stu-id="0a62a-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="0a62a-104">Gli account di posta elettronica di Office 365 e Outlook.com ricevono un numero sempre più elevato di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="0a62a-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="0a62a-105">Una tecnica utilizzata da phisher consiste nell'inviare messaggi con valori per l'indirizzo from: non conformi a [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="0a62a-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="0a62a-106">L'indirizzo from: è denominato anche indirizzo 5322. from.</span><span class="sxs-lookup"><span data-stu-id="0a62a-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="0a62a-107">Per evitare questo tipo di phishing, Office 365 e Outlook.com richiedono messaggi ricevuti dal servizio per includere un indirizzo conforme a RFC da: Address, come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0a62a-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a62a-108">Le informazioni contenute in questo articolo richiedono una conoscenza di base del formato generale degli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0a62a-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="0a62a-109">Per ulteriori informazioni, vedere [rfc 5322](https://tools.ietf.org/html/rfc5322) (in particolare le sezioni 3.2.3, 3,4 e 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), così come [RFC 3696](https://tools.ietf.org/html/rfc3696).</span><span class="sxs-lookup"><span data-stu-id="0a62a-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="0a62a-110">Questo articolo riguarda l'applicazione dei criteri per l'indirizzo 5322. from.</span><span class="sxs-lookup"><span data-stu-id="0a62a-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="0a62a-111">Questo articolo non riguarda l'indirizzo 5321. MailFrom.</span><span class="sxs-lookup"><span data-stu-id="0a62a-111">This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="0a62a-112">Purtroppo, esistono ancora alcuni server di posta elettronica legacy su Internet che continuano a inviare messaggi di posta elettronica "legittimi" che dispongono di un indirizzo mancante o non valido:</span><span class="sxs-lookup"><span data-stu-id="0a62a-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="0a62a-113">Se si ricevono regolarmente messaggi di posta elettronica da organizzazioni che utilizzano questi sistemi legacy, incoraggiare tali organizzazioni a aggiornare i propri server di posta elettronica in modo che siano conformi agli standard di sicurezza moderni.</span><span class="sxs-lookup"><span data-stu-id="0a62a-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="0a62a-114">Microsoft inizierà a implementare l'applicazione dei criteri descritti in questo articolo il 9 novembre 2017.</span><span class="sxs-lookup"><span data-stu-id="0a62a-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="0a62a-115">In che modo Office 365 applica l'utilizzo di un indirizzo valido da: per impedire attacchi di phishing</span><span class="sxs-lookup"><span data-stu-id="0a62a-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="0a62a-116">Office 365 sta apportando modifiche al modo in cui applica l'utilizzo dell'indirizzo from: nei messaggi ricevuti per garantire una maggiore protezione dagli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="0a62a-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="0a62a-117">Contenuto dell'articolo:</span><span class="sxs-lookup"><span data-stu-id="0a62a-117">In this article:</span></span>
  
- [<span data-ttu-id="0a62a-118">Tutti i messaggi devono includere un indirizzo valido da:</span><span class="sxs-lookup"><span data-stu-id="0a62a-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="0a62a-119">Formato dell'indirizzo from: se non si include un nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="0a62a-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="0a62a-120">Formato dell'indirizzo from: se si include un nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="0a62a-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="0a62a-121">Esempi aggiuntivi di indirizzi validi e non validi:</span><span class="sxs-lookup"><span data-stu-id="0a62a-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="0a62a-122">Sopprimere le risposte automatiche al dominio personalizzato senza interrompere il criterio da:</span><span class="sxs-lookup"><span data-stu-id="0a62a-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="0a62a-123">Override di Office 365 da: criteri di applicazione degli indirizzi</span><span class="sxs-lookup"><span data-stu-id="0a62a-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="0a62a-124">Altri modi per prevenire e proteggere i reati informatici in Office 365</span><span class="sxs-lookup"><span data-stu-id="0a62a-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="0a62a-125">L'invio per conto di un altro utente non è influenzato da questa modifica, per ulteriori informazioni, leggere il Blog di Terry zinco "[cosa si intende quando si fa riferimento al ' mittente ' di un messaggio di posta elettronica?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="0a62a-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="0a62a-126">Tutti i messaggi devono includere un indirizzo valido da:</span><span class="sxs-lookup"><span data-stu-id="0a62a-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="0a62a-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="0a62a-127"></span></span>

<span data-ttu-id="0a62a-128">Alcuni messaggi automatici non includono un indirizzo da: quando vengono inviati.</span><span class="sxs-lookup"><span data-stu-id="0a62a-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="0a62a-129">In passato, quando Office 365 o Outlook.com ha ricevuto un messaggio senza un indirizzo from:, il servizio ha aggiunto il seguente indirizzo predefinito da: Address al messaggio per renderlo risultato finale:</span><span class="sxs-lookup"><span data-stu-id="0a62a-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="0a62a-130">A partire dal 9 novembre 2017, Office 365 distribuirà le modifiche apportate ai propri datacenter e ai server di posta che applicano una nuova regola in cui i messaggi senza un indirizzo da: non verranno più accettati da Office 365 o Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0a62a-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="0a62a-131">Al contrario, tutti i messaggi ricevuti da Office 365 devono già contenere un indirizzo valido da:.</span><span class="sxs-lookup"><span data-stu-id="0a62a-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="0a62a-132">In caso contrario, il messaggio verrà inviato alla cartella posta inDesiderata o agli elementi eliminati in Outlook.com e Office 365.</span><span class="sxs-lookup"><span data-stu-id="0a62a-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="0a62a-133">Panoramica della sintassi: formato valido per l'indirizzo da: per Office 365</span><span class="sxs-lookup"><span data-stu-id="0a62a-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="0a62a-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="0a62a-134"></span></span>

<span data-ttu-id="0a62a-135">Il formato per il valore dell'indirizzo from: è definito in dettaglio tra diverse RFC.</span><span class="sxs-lookup"><span data-stu-id="0a62a-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="0a62a-136">Sono presenti molte varianti sull'indirizzamento e su ciò che può essere considerato valido o non valido.</span><span class="sxs-lookup"><span data-stu-id="0a62a-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="0a62a-137">Per semplificare le operazioni, Microsoft consiglia di utilizzare il formato e le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a62a-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="0a62a-138">Dove:</span><span class="sxs-lookup"><span data-stu-id="0a62a-138">Where:</span></span>
  
- <span data-ttu-id="0a62a-139">Optional  *DisplayName* è una frase che descrive il proprietario dell'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0a62a-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="0a62a-140">Ad esempio, questo potrebbe essere un nome più facile da usare per descrivere il mittente rispetto al nome della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0a62a-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="0a62a-141">L'utilizzo di un nome visualizzato è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0a62a-141">Using a display name is optional.</span></span> <span data-ttu-id="0a62a-142">Tuttavia, se si sceglie di utilizzare un nome visualizzato, Microsoft consiglia di racchiuderlo sempre tra virgolette, come mostrato nella figura.</span><span class="sxs-lookup"><span data-stu-id="0a62a-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="0a62a-143">Necessari  *EmailAddress* è costituito da:</span><span class="sxs-lookup"><span data-stu-id="0a62a-143">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="0a62a-144">Dove:</span><span class="sxs-lookup"><span data-stu-id="0a62a-144">Where:</span></span>
    
  - <span data-ttu-id="0a62a-145">Necessari  *local-part* è una stringa che identifica la cassetta postale associata all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="0a62a-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="0a62a-146">Questo è univoco all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="0a62a-146">This is unique within the domain.</span></span> <span data-ttu-id="0a62a-147">Spesso, il nome utente o il GUID del proprietario della cassetta postale viene utilizzato come valore per la parte locale.</span><span class="sxs-lookup"><span data-stu-id="0a62a-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="0a62a-148">Necessari  *Domain* è il nome di dominio completo (FQDN) del server di posta che ospita la cassetta postale identificata dalla parte locale dell'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0a62a-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="0a62a-149">Formato dell'indirizzo from: se non si include un nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="0a62a-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="0a62a-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="0a62a-150"></span></span>

<span data-ttu-id="0a62a-151">Un indirizzo in formato appropriato che non include un nome visualizzato include solo un singolo indirizzo di posta elettronica con o senza parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="0a62a-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="0a62a-152">Microsoft consiglia di non separare le parentesi angolari con gli spazi.</span><span class="sxs-lookup"><span data-stu-id="0a62a-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="0a62a-153">Inoltre, non includere nulla dopo l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0a62a-153">In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="0a62a-154">Gli esempi seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="0a62a-154">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="0a62a-155">L'esempio che segue è valido ma non consigliato perché contiene spazi tra le parentesi angolari e l'indirizzo di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="0a62a-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="0a62a-156">L'esempio che segue non è valido perché contiene testo dopo l'indirizzo di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="0a62a-156">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="0a62a-157">Formato dell'indirizzo from: se si include un nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="0a62a-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="0a62a-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="0a62a-158"></span></span>

<span data-ttu-id="0a62a-159">Per gli indirizzi da: che includono un valore per il nome visualizzato, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a62a-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="0a62a-160">Se l'indirizzo del mittente include un nome visualizzato e il nome visualizzato include una virgola, il nome visualizzato deve essere racchiuso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="0a62a-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="0a62a-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0a62a-161">For example:</span></span>
    
    <span data-ttu-id="0a62a-162">L'esempio seguente è valido:</span><span class="sxs-lookup"><span data-stu-id="0a62a-162">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="0a62a-163">L'esempio seguente non è valido:</span><span class="sxs-lookup"><span data-stu-id="0a62a-163">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="0a62a-164">Non è necessario racchiudere il nome visualizzato tra virgolette se il nome visualizzato include una virgola non è valido in base a RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="0a62a-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="0a62a-165">Come procedura consigliata, inserire i contrassegni di virgolette attorno al nome visualizzato indipendentemente dal fatto che esista o meno una virgola all'interno del nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="0a62a-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="0a62a-166">Se l'indirizzo del mittente include un nome visualizzato, l'indirizzo di posta elettronica deve essere racchiuso tra parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="0a62a-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="0a62a-167">Come procedura consigliata, Microsoft consiglia di inserire uno spazio tra il nome visualizzato e l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0a62a-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="0a62a-168">Esempi aggiuntivi di indirizzi validi e non validi:</span><span class="sxs-lookup"><span data-stu-id="0a62a-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="0a62a-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0a62a-169"></span></span>

- <span data-ttu-id="0a62a-170">Valido</span><span class="sxs-lookup"><span data-stu-id="0a62a-170">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="0a62a-171">Non valido.</span><span class="sxs-lookup"><span data-stu-id="0a62a-171">Invalid.</span></span> <span data-ttu-id="0a62a-172">L'indirizzo di posta elettronica non è racchiuso tra parentesi uncinate:</span><span class="sxs-lookup"><span data-stu-id="0a62a-172">The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="0a62a-173">Valido, ma non consigliato.</span><span class="sxs-lookup"><span data-stu-id="0a62a-173">Valid, but not recommended.</span></span> <span data-ttu-id="0a62a-174">Il nome visualizzato non è incluso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="0a62a-174">The display name is not in quotes.</span></span> <span data-ttu-id="0a62a-175">Come procedura consigliata, inserire sempre le virgolette attorno al nome visualizzato:</span><span class="sxs-lookup"><span data-stu-id="0a62a-175">As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="0a62a-176">Non valido.</span><span class="sxs-lookup"><span data-stu-id="0a62a-176">Invalid.</span></span> <span data-ttu-id="0a62a-177">Tutto è racchiuso tra virgolette, non solo il nome visualizzato:</span><span class="sxs-lookup"><span data-stu-id="0a62a-177">Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="0a62a-178">Non valido.</span><span class="sxs-lookup"><span data-stu-id="0a62a-178">Invalid.</span></span> <span data-ttu-id="0a62a-179">Non ci sono parentesi angolari attorno all'indirizzo di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="0a62a-179">There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="0a62a-180">Non valido.</span><span class="sxs-lookup"><span data-stu-id="0a62a-180">Invalid.</span></span> <span data-ttu-id="0a62a-181">Non c'è spazio tra il nome visualizzato e la parentesi uncinata sinistra:</span><span class="sxs-lookup"><span data-stu-id="0a62a-181">There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="0a62a-182">Non valido.</span><span class="sxs-lookup"><span data-stu-id="0a62a-182">Invalid.</span></span> <span data-ttu-id="0a62a-183">Non vi sono spazi tra le virgolette di chiusura attorno al nome visualizzato e la parentesi angolare sinistra.</span><span class="sxs-lookup"><span data-stu-id="0a62a-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="0a62a-184">Sopprimere le risposte automatiche al dominio personalizzato senza interrompere il criterio da:</span><span class="sxs-lookup"><span data-stu-id="0a62a-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="0a62a-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="0a62a-185"></span></span>

<span data-ttu-id="0a62a-186">Con il nuovo da: applicazione dei criteri, non è più possibile utilizzare da: \< \> per sopprimere le risposte automatiche.</span><span class="sxs-lookup"><span data-stu-id="0a62a-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="0a62a-187">Al contrario, è necessario configurare un record MX null per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0a62a-187">Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="0a62a-188">Il record MX (Mail Exchanger) è un record di risorse in DNS che identifica il server di posta elettronica che riceve la posta per il dominio.</span><span class="sxs-lookup"><span data-stu-id="0a62a-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="0a62a-189">Le risposte automatiche (e tutte le risposte) sono naturalmente soppressi perché non esiste alcun indirizzo pubblicato a cui il server che risponde può inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="0a62a-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="0a62a-190">Quando si configura un record MX null per il dominio personalizzato:</span><span class="sxs-lookup"><span data-stu-id="0a62a-190">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="0a62a-191">Scegliere un dominio da cui inviare i messaggi che non accettano (ricevono) la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0a62a-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="0a62a-192">Ad esempio, se il dominio principale è contoso.com, è possibile scegliere noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0a62a-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="0a62a-193">Configurare il record MX null per il dominio.</span><span class="sxs-lookup"><span data-stu-id="0a62a-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="0a62a-194">Un record MX null è costituito da un singolo punto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0a62a-194">A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="0a62a-195">Per ulteriori informazioni sulla pubblicazione di un MX null, vedere [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="0a62a-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="0a62a-196">Override di Office 365 da: criteri di applicazione degli indirizzi</span><span class="sxs-lookup"><span data-stu-id="0a62a-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="0a62a-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="0a62a-197"></span></span>

<span data-ttu-id="0a62a-198">Una volta che il nuovo criterio è stato completato, è possibile ignorare questo criterio solo per la posta in ingresso ricevuta da Office 365 utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a62a-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="0a62a-199">Elenchi di indirizzi IP consentiti</span><span class="sxs-lookup"><span data-stu-id="0a62a-199">IP allow lists</span></span>
    
- <span data-ttu-id="0a62a-200">Regole del flusso di posta di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0a62a-200">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="0a62a-201">Microsoft consiglia vivamente di eseguire l'override dell'applicazione del criterio from:.</span><span class="sxs-lookup"><span data-stu-id="0a62a-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="0a62a-202">L'override di questo criterio può aumentare il rischio di esposizione da parte dell'organizzazione alla posta indesiderata, al phishing e ad altri reati informatici.</span><span class="sxs-lookup"><span data-stu-id="0a62a-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="0a62a-203">Non è possibile eseguire l'override di questo criterio per la posta in uscita inviata in Office 365.</span><span class="sxs-lookup"><span data-stu-id="0a62a-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="0a62a-204">Inoltre, Outlook.com non consentirà sostituzioni di alcun tipo, anche tramite supporto.</span><span class="sxs-lookup"><span data-stu-id="0a62a-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="0a62a-205">Altri modi per prevenire e proteggere i reati informatici in Office 365</span><span class="sxs-lookup"><span data-stu-id="0a62a-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="0a62a-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="0a62a-206"></span></span>

<span data-ttu-id="0a62a-207">Per ulteriori informazioni su come rafforzare la propria organizzazione contro i reati informatici, quali phishing, spamming, violazioni dei dati e altre minacce, vedere [procedure consigliate per la sicurezza per Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span><span class="sxs-lookup"><span data-stu-id="0a62a-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0a62a-208">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0a62a-208">Related Topics</span></span>

[<span data-ttu-id="0a62a-209">Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP</span><span class="sxs-lookup"><span data-stu-id="0a62a-209">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

