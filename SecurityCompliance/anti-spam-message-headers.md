---
title: Intestazioni messaggi della protezione da posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/9/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
description: Quando Exchange Online Protection analizza un messaggio di posta elettronica in ingresso, inserisce l'intestazione **X-Forefront-Antispam-Report** nel messaggio.
ms.openlocfilehash: 192a1d3e3331256819ddd68fbe0aa0c1fa16c9a7
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003145"
---
# <a name="anti-spam-message-headers"></a>Intestazioni messaggi della protezione da posta indesiderata

Quando Exchange Online Protection analizza un messaggio di posta elettronica in ingresso, inserisce l'intestazione **X-Forefront-Antispam-Report** nel messaggio. I campi di questa intestazione consentono agli amministratori di ottenere informazioni relative al messaggio e a come è stato elaborato. I campi nell'intestazione **X-Microsoft-Antispam** forniscono informazioni aggiuntive sulla posta inviata in massa e sul phishing. Oltre a queste due intestazioni, Exchange Online Protection inserisce anche i risultati dell'autenticazione della posta elettronica per ogni messaggio che elabora nell'intestazione **Authentication-results**. 
  
> [!TIP]
> Per informazioni sulla visualizzazione dell'intestazione di un messaggio di posta elettronica in diversi client di posta elettronica, vedere [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583). È possibile copiare e incollare il contenuto dell'intestazione di un messaggio nello strumento [Analizzatore intestazione messaggio](https://testconnectivity.microsoft.com/?tabid=mha). Quando si seleziona un messaggio nella quarantena nell'interfaccia di amministrazione di Exchange, il collegamento **Visualizza intestazione messaggio** consente di copiare e incollare facilmente il testo dell'intestazione del messaggio nello strumento . Dopo l'accesso allo strumento Analizzatore intestazione messaggio, fare clic su **Analizza intestazioni** per recuperare le informazioni sull'intestazione. 
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>Campi di intestazione del messaggio X-Forefront-Antispam-Report
<a name="sectionSection0"> </a>

Dopo aver effettuato l'accesso alle informazioni relative all'intestazione del messaggio, cercare **X-Forefront-Antispam-Report**, quindi cercare i campi seguenti. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica. 
  
|||
|:-----|:-----|
|**Campo di intestazione** <br/> |**Descrizione** <br/> |
|CIP: [indirizzo IP]  <br/> |L'indirizzo IP. È possibile specificare l'indirizzo IP durante la creazione di un elenco di indirizzi IP consentiti o un elenco di indirizzi IP bloccati nel filtro di connessione. Per ulteriori informazioni, vedere [configurare il criterio di filtro di connessione](configure-the-connection-filter-policy.md).<br/> |
|CTRY  <br/> |Il paese dal quale il messaggio è stato connesso al servizio. Questo è determinato dall'indirizzo IP di connessione, il quale potrebbe non essere uguale all'indirizzo IP di invio di origine.  <br/> |
|LANG  <br/> |LANG: la lingua in cui è scritto il messaggio, come specificato dal codice paese (ad esempio, ru_RU per la Russia).  <br/> |
|SCL  <br/> |Il valore del livello di probabilità di posta indesiderata (SCL) del messaggio. Per ulteriori informazioni sull'interpretazione di questi valori, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).  <br/> |
|PCL  <br/> |Il valore del livello di confidenza di Phishing (PCL) del messaggio. Vedere [PCL](anti-spam-message-headers.md#PCL) per ulteriori informazioni sui valori PCL.  <br/> |
|SRV:BULK  <br/> |Il messaggio è stato identificato come un messaggio di posta elettronica in blocco. Se l' **opzione avanzata di filtro della posta indesiderata Blocca tutti i messaggi di posta in blocco** è abilitata, il messaggio verrà contrassegnato come posta indesiderata. Se l'opzione è disabilitata, il messaggio verrà contrassegnato come posta indesiderata solo se il resto delle regole del filtro stabiliscono che è indesiderato.  <br/> |
|SFV:SFE  <br/> |Il filtro è stato ignorato e il messaggio è stato lasciato passare perché è stato inviato da un indirizzo presente in un singolo elenco dei mittenti attendibili.  <br/> |
|SFV:BLK  <br/> |Il filtro è stato ignorato e il messaggio è stato bloccato perché è stato inviato da un indirizzo presente in un singolo elenco dei mittenti bloccati.  <br/> **Suggerimento:** Per ulteriori informazioni su come gli utenti finali possono creare elenchi di mittenti attendibili e bloccati, vedere [Bloccati o consentiti (impostazioni della posta indesiderata)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (OWA) e [Panoramica del filtro della posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook).  <br/> |
|IPV:CAL  <br/> |Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.  <br/> |
|IPV:NLI  <br/> |L'indirizzo IP non è stato elencato in nessuno degli elenchi di reputazione IP.  <br/> |
|SFV:SPM  <br/> |Il messaggio è stato contrassegnato come posta indesiderata dal filtro contenuto.  <br/> |
|SFV:SKS  <br/> |Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alle regole di trasporto, che lo contrassegnano automaticamente come indesiderato e che ignorano tutte le regole del filtro aggiuntive.  <br/> |
|SFV:SKA  <br/> |Il messaggio ha ignorato il filtro ed è stato recapitato nella posta in arrivo perché è stata trovata una corrispondenza con un elenco Consenti nei criteri di filtro posta indesiderata, come l' **Elenco mittenti consentiti**.  <br/> |
|SFV:SKB  <br/> |Il messaggio è stato contrassegnato come posta indesiderata perché è stata trovata una corrispondenza con un elenco Blocca nei criteri di filtro posta indesiderata, come l' **Elenco mittenti bloccati**.  <br/> |
|SFV:SKN  <br/> |Il messaggio è stato contrassegnato come posta non indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alle regole di trasporto, che lo contrassegnano automaticamente come non indesiderato e che ignorano tutte le regole del filtro aggiuntive.  <br/> |
|SFV:SKN  <br/> |Come per SFV:SKN, il messaggio ha ignorato il filtro per un altro motivo, ad esempio perché si tratta di posta elettronica tra organizzazioni all'interno di un tenant.  <br/> |
|SFV:SKQ  <br/> |Il messaggio è stato rilasciato dalla quarantena ed è stato inviato al destinatario.  <br/> |
|SFV:NSPM  <br/> |Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.  <br/> |
|H: [helostring]  <br/> |La stringa HELO or EHLO del server di posta elettronica di connessione.  <br/> |
|PTR: [ReverseDNS]  <br/> |Il record PTR o record "Pointer" dell'indirizzo IP del mittente, noto anche come indirizzo DNS inverso.  <br/> |
|SFTY  <br/> | Il messaggio è stato identificato come phishing e inoltre essere contrassegnato con uno dei valori seguenti:  <br/>  9.1 - valore predefinito. Il messaggio contiene un URL di phishing, può contenere altri contenuti phishing o contrassegnato come phishing da un altro filtro di posta elettronica, ad esempio una versione locale di Exchange Server prima di inoltrare il messaggio a Office 365.  <br/>  9.11 - anti-spoofing controlli non riusciti messaggio dove il dominio di invio nella From: intestazione equivale, risulti allineato con o fa parte della stessa organizzazione al dominio di destinazione.  <br/>  Non è stato messaggio 9.21 - anti-spoofing controlli e il dominio di invio nella From: intestazione non esegue l'autenticazione. Utilizzare in combinazione con CompAuth (vedere i risultati di autenticazione).  <br/>  9.22 - simile a 9.21, ad eccezione del fatto che l'utente dispone di un mittente protetto è stato sottoposto a override.  <br/>  9.23 - simile a 9.22, ad eccezione del fatto che l'organizzazione dispone di un mittente consentiti o un dominio a cui è stato sottoposto a override.  <br/>  9,24 - stessi 9.23, ad eccezione del fatto che l'utente dispone di un flusso di posta di Exchange della regola che è stato sottoposto a override.  <br/> |
|X-CustomSpam: [ASFOption]  <br/> |I messaggi corrispondono a una filtro della posta indesiderata opzione. Ad esempio, **X-CustomSpam: collegamenti a siti remoti dell'immagine** indica che l'opzione **collegamenti immagini a siti remoti** ASF corrispondente. Per testo X-header viene aggiunto per ogni opzione ASF specifici, vedere [Opzioni di filtro posta indesiderata](advanced-spam-filtering-asf-options.md).<br/> |
   
## <a name="x-microsoft-antispam-message-header-fields"></a>Campi di intestazione del messaggio X-Microsoft-Antispam
<a name="sectionSection1"> </a>

Nella tabella seguente vengono descritti i campi utili nell'intestazione del messaggio **X-Microsoft-Antispam**. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica. 
  
|||
|:-----|:-----|
|**Campo di intestazione** <br/> |**Descrizione** <br/> |
|BCL  <br/> |Il Livello di reclamo in blocco (BCL) del messaggio. Per ulteriori informazioni, vedere [Valori al livello reclamo massa](bulk-complaint-level-values.md).  <br/> |
|PCL  <br/> | Il Livello di probabilità di phishing (PCL) del messaggio, che indica se si tratta di un messaggio di phishing.  <br/>  Lo stato restituito può avere i seguenti valori numerici:  <br/> **0-3** È probabile che il contenuto del messaggio non sia phishing.  <br/> **4-8** È probabile che il contenuto del messaggio sia phishing.  <br/> **-9990** (solo Exchange Online Protection) È probabile che il contenuto del messaggio sia phishing.  <br/>  I valori vengono utilizzati per determinare quale azione viene eseguita dal client di posta elettronica sui messaggi. Ad esempio, Microsoft Office Outlook utilizza l'indicatore PCL per bloccare il contenuto dei messaggi sospetti. Per ulteriori informazioni sul phishing e su come Outlook elabora i messaggi di phishing, vedere [Attivare o disattivare i collegamenti nei messaggi di posta elettronica](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).  <br/> |
   
## <a name="authentication-results-message-header"></a>Intestazione del messaggio Authentication-results
<a name="sectionSection2"> </a>

I risultati dei controlli su SPF, DKIM e DMARC vengono registrati (o contrassegnati) da Office 365 nell'intestazione del messaggio **Authentication-results** quando i server di posta ricevono un messaggio di posta elettronica. 
  
### <a name="check-stamp-syntax-and-examples"></a>Esempi e sintassi del contrassegno di controllo
<a name="referenceSPFstamp"> </a>

I seguenti esempi di sintassi mostrano una porzione del "contrassegno" che Office 365 applica all'intestazione di ogni messaggio di posta elettronica che viene sottoposto a una verifica dell'autenticazione della posta elettronica quando viene ricevuto dai server della posta. Il contrassegno viene aggiunto all'intestazione **Authentication-Results**. 
  
 **Sintassi: timbro segno di spunta SPF**
  
Per SPF, si applica la sintassi seguente.
  
```
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

 **Esempi: timbro segno di spunta SPF**
  
```
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com

```

 **Sintassi: timbro segno di spunta DKIM**
  
Per DKIM, si applica la sintassi seguente.
  
```
dkim=<pass|fail (reason)|none> header.d=<domain>
```

 **Esempi: timbro segno di spunta DKIM**
  
```
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

 **Sintassi: timbro segno di spunta DMARC**
  
Per DMARC, si applica la sintassi seguente.
  
```
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

 **Esempi: timbro segno di spunta DMARC**
  
```
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Campi di intestazione del messaggio Authentication-results utilizzati dall'autenticazione della posta elettronica di Office 365
<a name="referenceSPFstamp"> </a>

Nella tabella seguente vengono descritti i campi e i valori possibili per il controllo di autenticazione di ogni messaggio di posta elettronica.
  
|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|spf  <br/> | Descrive i risultati del controllo SPF per il messaggio. Tra i possibili valori sono inclusi:  <br/> **pass (indirizzo IP)** indica che il controllo SPF per il messaggio è stato superato e include l'indirizzo IP del mittente. Il client è autorizzato a inviare o inoltrare la posta elettronica per conto del dominio del mittente.  <br/> **fail (indirizzo IP)** indica che il controllo SPF per il messaggio non è stato superato e include l'indirizzo IP del mittente. Talvolta viene definito controllo non riuscito.  <br/> **softfail (motivo)** indica che il record SPF ha designato l'host come non autorizzato all'invio ma in transizione.  <br/> **neutral** indica che il record SPF ha dichiarato in modo esplicito che non afferma se l'indirizzo IP è autorizzato.  <br/> **none** indica che il dominio non dispone di un record SPF o che il record SPF non restituisce un risultato.  <br/> **temperror** indica che si è verificato un errore che potrebbe essere di natura temporanea, ad esempio, un errore DNS. Riprovare in un secondo momento potrebbe avere un esito positivo senza alcun intervento dell'amministratore.  <br/> **permerror** indica che si è verificato un errore permanente. Ciò accade quando, ad esempio, il dominio presenta un record SPF con formato non valido.  <br/> |
|SMTP.MailFrom  <br/> |Contiene il dominio di origine da cui proviene il messaggio. Gli errori relativi a tale messaggio di posta elettronica verranno inviati al postmaster o all'entità responsabile del dominio. A volte viene chiamato indirizzo 5321.MailFrom o indirizzo reverse-path address sulla busta del messaggio.  <br/> |
|dkim  <br/> | Descrive i risultati del controllo DKIM per il messaggio. Tra i possibili valori sono inclusi:  <br/> **pass** indica che il controllo DKIM per il messaggio è stato superato.  <br/> **fail (motivo)** indica che il controllo DKIM per il messaggio non è stato superato e include il motivo. Ad esempio, se il messaggio non è stato firmato o se la firma non è stata verificata.  <br/> **none** indica che il messaggio non è stato firmato. Ciò potrebbe indicare o meno che il dominio dispone di un record DKIM o che il record DKIM non restituisce un risultato, solo che il messaggio non è stato firmato.  <br/> |
|Header.d  <br/> |Dominio identificato nella firma DKIM, se presente. Questo è il dominio sottoposto a query per la chiave pubblica.  <br/> |
|dmarc  <br/> | Descrive i risultati del controllo DMARC per il messaggio. Tra i possibili valori sono inclusi:  <br/> **pass** indica che il controllo DMARC per il messaggio è stato superato.  <br/> **fail** indica che il controllo DMARC per il messaggio non è stato superato.  <br/> **bestguesspass** indica che non esistono record TXT DMARC per il dominio, ma se ne esistesse uno, il controllo DMARC per il messaggio sarebbe stato superato. Questo è il motivo per cui il dominio nell'indirizzo 5321.MailFrom corrisponde al dominio nell'indirizzo 5322.From.  <br/> **none** indica che non esistono record TXT DKIM per il dominio di invio in DNS.  <br/> |
|action  <br/> | Indica l'azione eseguita dal filtro posta indesiderata in base ai risultati del controllo DMARC. Ad esempio:  <br/> **permerror** Si è verificato un errore permanente durante la valutazione DMARC (ad esempio, è stato trovato un record TXT DMARC con formato non valido in DNS). Tentando di inviare di nuovo questo messaggio, probabilmente si otterrebbe un risultato diverso. Al contrario, potrebbe essere necessario contattare il proprietario del dominio per risolvere il problema.  <br/> **temperror** Si è verificato un errore temporaneo durante la valutazione DMARC. Potrebbe essere possibile richiedere che il mittente invii il messaggio in un secondo momento per elaborare il messaggio correttamente.  <br/> **oreject** o **o.reject** sta per override reject (rifiuto override). In questo caso, Office 365 usa questa azione quando riceve un messaggio che non supera il controllo DMARC da un dominio il cui record TXT DMARC ha un criterio di p=reject. Anziché eliminare o rifiutare il messaggio, Office 365 lo contrassegna come posta indesiderata. Per ulteriori informazioni sul motivo per cui Office 365 è configurato in questo modo, vedere [Modalità di gestione della posta elettronica in ingresso che non supera DMARC da parte di Office 365](use-dmarc-to-validate-email.md#inbounddmarcfail).  <br/> **pct.quarantine** Indica che una percentuale inferiore al 100% di messaggi che non superano il controllo DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su quarantine, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato.  <br/> **pct.reject** Indica che una percentuale inferiore al 100% di messaggi che non superano il controllo DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su reject, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato.  <br/> |
|Header.From  <br/> |Il dominio dell'indirizzo mittente nell'intestazione del messaggio di posta elettronica. A volte viene chiamato indirizzo 5322.From.  <br/> |
|compauth  <br/> |Risultato dell'autenticazione composito. Utilizzato da Office 365 per combinare più tipi di autenticazione, ad esempio SPF, DKIM, DMARC o qualsiasi altra parte del messaggio per determinare se il messaggio viene autenticato. Viene utilizzato da: dominio come base di valutazione.  <br/> |
|motivo  <br/> | Il motivo per l'autenticazione composito passato o non è riuscita. Il valore per il motivo è costituito da tre cifre:  <br/>  000 - il messaggio in modo esplicito autenticazione non riuscita. Ad esempio, il messaggio ricevuto fail DMARC con un'azione di quarantena o su Rifiuta.  <br/>  001 - il messaggio di autenticazione non riuscita in modo implicito e il dominio di invio non è stato pubblicare i criteri di autenticazione. Ad esempio, il criterio DMARC p = none.  <br/>  1xx - il messaggio passato l'autenticazione. In secondo luogo due cifre sono codici interni utilizzati da Office 365.  <br/>  2xx – l'autenticazione di passate reversibile. In secondo luogo due cifre sono codici interni utilizzati da Office 365.  <br/>  3xx - il messaggio non è stata selezionata per l'autenticazione composito.  <br/>  4xx - messaggio ignorato autenticazione composito. In secondo luogo due cifre sono codici interni utilizzati da Office 365.  <br/> |
  