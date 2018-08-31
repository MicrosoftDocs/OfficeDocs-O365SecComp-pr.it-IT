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
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Il modo in cui Office 365 convalida l'indirizzo da per impedire il phishing

Office 365 e account di posta elettronica Outlook.com ricevono un numero sempre più elevato di attacchi di phishing. Una tecnica autori utilizzano consiste nell'inviare i messaggi che contengono valori per il mittente: indirizzo che non è conforme a [RFC 5322](https://tools.ietf.org/html/rfc5322). From: indirizzo è denominato anche indirizzo 5322.From. Per evitare questo tipo di phishing, Office 365 e Outlook.com richiedono i messaggi ricevuti dal servizio per includere un conforme a RFC da: risolvere come descritto in questo articolo.
  
> [!NOTE]
> Le informazioni contenute in questo articolo è necessario disporre di una conoscenza di base del formato generale di indirizzi di posta elettronica. Per ulteriori informazioni, vedere [RFC 5322](https://tools.ietf.org/html/rfc5322) (particolarmente sezioni 3.2.3, 3.4 e 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), nonché [3696 RFC](https://tools.ietf.org/html/rfc3696). In questo articolo viene illustrato l'applicazione dei criteri per l'indirizzo 5322.From. In questo articolo non relative all'indirizzo 5321.MailFrom. 
  
Purtroppo sono ancora presenti alcuni server di posta elettronica legacy su Internet che continuano a inviare "legittimi" messaggi di posta elettronica con un parametro mancante o non corretto da: indirizzo. Se si regolarmente ricezione della posta elettronica di organizzazioni che utilizzano questi sistemi legacy, incoraggiare tali organizzazioni per aggiornare i server di posta elettronica per essere conforme agli standard di protezione moderno.
  
Microsoft consente di avviare l'applicazione dei criteri descritti in questo articolo in 9 novembre 2017 distribuzione.
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Come Office 365 prevede l'utilizzo di un oggetto valido da: indirizzo per impedire attacchi di phishing

Office 365 apporta modifiche al modo in cui prevede l'utilizzo di From: indirizzo in i messaggi ricevuti in modo da impedire attacchi di phishing. In questo articolo:
  
- [Tutti i messaggi devono includere un valido da: indirizzo](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [Tutti i messaggi devono includere un valido da: indirizzo](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [Formato di From: risolvere se non si include un nome visualizzato](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [Formato di From: risolvere se si include un nome visualizzato](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [Ulteriori esempi di valido e non validi dalla: indirizzi](how-office-365-validates-the-from-address.md#Examples)
    
- [Eliminare le risposte automatiche per il dominio personalizzato senza interrompere From: criteri](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Eseguire l'override di Office 365 da: risolvere i criteri di applicazione](how-office-365-validates-the-from-address.md#Override)
    
- [Altri modi per impedire e proteggendo cybercrimes in Office 365](how-office-365-validates-the-from-address.md#OtherProtection)
    
Invia per conto di un altro utente non ha questa modifica, per ulteriori informazioni, leggere blog di Terry Zink "[cosa si intende quando si fa riferimento al mittente di un messaggio di posta elettronica?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".
  
### <a name="all-messages-must-include-a-valid-from-address"></a>Tutti i messaggi devono includere un valido da: indirizzo
<a name="MustIncludeFromAddress"> </a>

Alcuni messaggi automatici non includono un mittente: indirizzo quando vengono inviati. In passato, in Office 365 o Outlook.com ha ricevuto un messaggio senza un mittente: indirizzo, il servizio aggiunto predefinito riportato di seguito da: indirizzo per il messaggio per rendere risultato finale:
  
```
From: <>
```

Avviare il 9 novembre 2017 Office 365 verrà essere distribuzione modifiche per i server di datacenter e posta elettronica che determinerà una nuova regola di cui messaggi senza un mittente: indirizzo non più essere accettata da Office 365 o Outlook.com. In realtà, tutti i messaggi ricevuti da Office 365 devono già contenere valido da: indirizzo. In caso contrario, verrà inviato il messaggio alle cartelle di posta indesiderata o posta eliminata Outlook.com e Office 365. 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>Panoramica della sintassi: formato valido per il mittente: indirizzo per Office 365
<a name="SyntaxOverviewFromAddress"> </a>

Il formato del valore di From: indirizzo definito in modo dettagliato tra le diverse. Esistono molti le varianti di indirizzamento e ciò che può essere considerato valido o non validi. Per mantenere semplice, si consiglia di utilizzare le definizioni e il formato seguente:
  
```
From: "displayname " <emailaddress >
```

Dove:
  
- (Facoltativo)  *DisplayName* è una frase che descrive il proprietario dell'indirizzo di posta elettronica. Ad esempio, può essere un nome descrittivo per descrivere il mittente rispetto al nome della cassetta postale. Utilizzo di un nome visualizzato è facoltativo. Tuttavia, se si sceglie di utilizzare un nome visualizzato, è consigliabile che è sempre racchiuderlo tra virgolette come indicato. 
    
- (Obbligatorio)  *EmailAddress* è costituito da: 
    
  ```
  local-part @domain
  ```

    Dove:
    
  - (Obbligatorio)  *la parte locale* è una stringa che identifica la cassetta postale associata all'indirizzo. È univoco all'interno del dominio. Spesso, nome utente o il GUID del proprietario della cassetta postale viene utilizzato come valore per la parte locale. 
    
  - (Obbligatorio)  *dominio* è il nome di dominio completo (FQDN) del server di posta che ospita la cassetta postale identificata dalla parte locale dell'indirizzo di posta elettronica. 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>Formato di From: risolvere se non si include un nome visualizzato
<a name="FormatNoDisplayName"> </a>

A formattata correttamente rispetto a: indirizzo che non include un nome visualizzato include solo un indirizzo di posta elettronica singolo con o senza uncinate. Si consiglia di non separare le parentesi angolari con spazi. Inoltre, non includere lasciare dopo l'indirizzo di posta elettronica.
  
Negli esempi seguenti sono validi:
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

Nell'esempio seguente è valido, ma non consigliata perché contiene spazi tra le parentesi angolari e l'indirizzo di posta elettronica:
  
```
From: < sender@contoso.com >
```

Nell'esempio seguente non è valido perché contiene testo dopo l'indirizzo di posta elettronica:
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>Formato di From: risolvere se si include un nome visualizzato
<a name="FormatDisplayName"> </a>

Per da: gli indirizzi che includono un valore per il nome visualizzato, applicano le regole seguenti:
  
- Se l'indirizzo del mittente include un nome visualizzato e il nome visualizzato include una virgola, quindi il nome visualizzato deve essere racchiuso tra virgolette. Per esempio:
    
    Nell'esempio seguente è valido:
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    Nell'esempio seguente non è valido:
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    Non è valido in base alla RFC 5322 non che racchiudono il nome visualizzato tra virgolette se il nome visualizzato include una virgola.
    
    È consigliabile mettere virgolette racchiudere il nome visualizzato indipendentemente dall'utente se non esiste o è una virgola tra il nome visualizzato.
    
- Se l'indirizzo del mittente include un nome visualizzato, l'indirizzo di posta elettronica deve essere racchiusi tra parentesi angolari.
    
    Come procedura consigliata, si consiglia si inserisce uno spazio tra il nome visualizzato e l'indirizzo di posta elettronica.
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>Ulteriori esempi di valido e non validi dalla: indirizzi
<a name="Examples"> </a>

- Valido:
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- Non valido. L'indirizzo di posta elettronica non racchiusi tra parentesi angolari:
    
  ```
  From: Office 365 sender@contoso.com
  ```

- Valido, ma non consigliato. Il nome visualizzato non è racchiuso tra virgolette. Come procedura consigliata, posizionare sempre il nome visualizzato tra virgolette:
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- Non valido. Tutto il contenuto è racchiuso tra virgolette, non solo il nome visualizzato:
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- Non valido. Non esistono angolari intorno l'indirizzo di posta elettronica:
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- Non valido. Non è disponibile spazio tra il nome visualizzato e parentesi uncinata aperta:
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- Non valido. Non è disponibile spazio tra parentesi uncinata e quotation mark chiusura intorno il nome visualizzato.
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>Eliminare le risposte automatiche per il dominio personalizzato senza interrompere From: criteri
<a name="SuppressAutoReply"> </a>

Con la nuova da: applicazione dei criteri, non è più utilizzabili da: \< \> eliminare le risposte automatiche. In realtà, è necessario configurare un record MX null per il dominio personalizzato.
  
Il record mail exchanger (MX) è un record di risorse nel sistema DNS che identifica il server di posta elettronica che riceve la posta per il dominio. Le risposte automatiche (e tutte le risposte) naturalmente vengono eliminate dal momento che nessun indirizzo pubblicato a cui il server di risposta può inviare messaggi.
  
Quando si imposta un record MX null per il dominio personalizzato:
  
- Scegliere un dominio da cui si desidera inviare i messaggi che non accetta (ricezione) posta elettronica. Ad esempio, se il dominio primario è contoso.com, è possibile scegliere noreply.contoso.com.
    
- Consente di impostare il record MX null per il dominio. Un record MX null costituito da un punto, ad esempio:
    
  ```
  noreply.contoso.com IN MX .
  ```

Per ulteriori informazioni sulla pubblicazione di un MX null, vedere [RFC 7505](https://tools.ietf.org/html/rfc7505).
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Eseguire l'override di Office 365 da: risolvere i criteri di applicazione
<a name="Override"> </a>

Una volta (in inglese) completamente il nuovo criterio, è possibile ignorare solo questo criterio per la posta in ingresso che proveniente da Office 365 utilizzando uno dei metodi seguenti: 
  
- Elenchi di indirizzi IP consentiti
    
- Regole del flusso di posta elettronica Exchange Online
    
Si consiglia di base viene sottoposto a override l'applicazione di From: criterio. Eseguire l'override di questo criterio possono aumentare rischio dell'organizzazione di esposizione alla posta indesiderata e phishing altri cybercrimes.
  
Non è possibile ignorare questo criterio per la posta in uscita inviati in Office 365. Inoltre, Outlook.com non consente le sostituzioni di alcun tipo, anche tramite il supporto. 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Altri modi per impedire e proteggendo cybercrimes in Office 365
<a name="OtherProtection"> </a>

Per ulteriori informazioni su come è possibile aumentare il livello dell'organizzazione con cybercrimes come phishing, questi comportamenti, le violazioni di dati e altri rischi, vedere [le procedure consigliate per Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).
  
## <a name="related-topics"></a>Argomenti correlati

[Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

