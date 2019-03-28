---
title: Intestazioni messaggi della protezione da posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Quando Exchange Online Protection analizza un messaggio di posta elettronica in ingresso, inserisce l'intestazione **X-Forefront-Antispam-Report** nel messaggio.
ms.openlocfilehash: 92614b8cb6e1571c3d5438206f9dcd106579669a
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2019
ms.locfileid: "30936746"
---
# <a name="anti-spam-message-headers"></a>Intestazioni messaggi della protezione da posta indesiderata

Quando Exchange Online Protection analizza un messaggio di posta elettronica in ingresso, inserisce l'intestazione **X-Forefront-Antispam-Report** nel messaggio. I campi di questa intestazione consentono agli amministratori di ottenere informazioni relative al messaggio e a come è stato elaborato. I campi nell'intestazione **X-Microsoft-Antispam** forniscono informazioni aggiuntive sulla posta inviata in massa e sul phishing. Oltre a queste due intestazioni, Exchange Online Protection inserisce anche i risultati dell'autenticazione della posta elettronica per ogni messaggio che elabora nell'intestazione **Authentication-results**.
  
> [!TIP]
> Per informazioni sulla visualizzazione dell'intestazione di un messaggio di posta elettronica in diversi client di posta elettronica, vedere [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583). È possibile copiare e incollare il contenuto dell'intestazione di un messaggio nello strumento [Analizzatore intestazione messaggio](https://testconnectivity.microsoft.com/?tabid=mha). Quando si seleziona un messaggio nella quarantena nell'interfaccia di amministrazione di Exchange, il collegamento **Visualizza intestazione messaggio** consente di copiare e incollare facilmente il testo dell'intestazione del messaggio nello strumento . Dopo l'accesso allo strumento Analizzatore intestazione messaggio, fare clic su **Analizza intestazioni** per recuperare le informazioni sull'intestazione.
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>Campi di intestazione del messaggio X-Forefront-Antispam-Report

Dopo aver effettuato l'accesso alle informazioni relative all'intestazione del messaggio, cercare **X-Forefront-Antispam-Report**, quindi cercare i campi seguenti. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.

|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|CIP: [indirizzo IP]|L'indirizzo IP che si connette. È possibile specificare l'indirizzo IP quando si crea un elenco di indirizzi IP consentiti o un elenco di indirizzi IP bloccati nel filtro di connessione. Per ulteriori informazioni, vedere [Configurazione dei criteri di filtro delle connessioni](configure-the-connection-filter-policy.md).|
|CTRY|Il paese dal quale il messaggio è stato connesso al servizio. Questo è determinato dall'indirizzo IP di connessione, il quale potrebbe non essere uguale all'indirizzo IP di invio di origine.|
|LANG|LANG:   la lingua in cui è scritto il messaggio, come specificato dal codice paese (ad esempio, ru_RU per la Russia).|
|SCL|Il valore del livello di probabilità di posta indesiderata (SCL) del messaggio. Per ulteriori informazioni sull'interpretazione di questi valori, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).  |
|PCL|Il valore del livello di confidenza di Phishing (PCL) del messaggio.|
|SRV:BULK|Il messaggio è stato identificato come un messaggio di posta elettronica in blocco. Se l'**opzione avanzata di filtro della posta indesiderata Blocca tutti i messaggi di posta in blocco** è abilitata, il messaggio verrà contrassegnato come posta indesiderata. Se l'opzione è disabilitata, il messaggio verrà contrassegnato come posta indesiderata solo se il resto delle regole del filtro stabiliscono che è indesiderato.|
|SFV:SFE|Il filtro è stato ignorato e il messaggio è stato lasciato passare perché è stato inviato da un indirizzo presente in un singolo elenco dei mittenti attendibili.|
|SFV:BLK|Il filtro è stato ignorato e il messaggio è stato bloccato perché è stato inviato da un indirizzo presente in un singolo elenco dei mittenti bloccati.  <br/> **Suggerimento**: per ulteriori informazioni su come gli utenti finali possono creare elenchi di mittenti attendibili e bloccati, vedere [blocco o Consenti (impostazioni di posta indesiderata)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (Outlook sul Web) e [Panoramica del filtro per la posta](https://go.microsoft.com/fwlink/p/?LinkId=270065) indesiderata (Outlook).|
|IPV:CAL|Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.|
|IPV:NLI|L'indirizzo IP non è stato elencato in nessuno degli elenchi di reputazione IP.|
|SFV:SPM|Il messaggio è stato contrassegnato come posta indesiderata dal filtro contenuto.|
|SFV:SKS|Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro contenuto. Sono inclusi i messaggi in cui il messaggio corrisponde a una regola del flusso di posta (nota anche come regola di trasporto) per contrassegnare automaticamente la posta indesiderata e ignorare tutti i filtri aggiuntivi.|
|SFV:SKA|Il messaggio ha ignorato il filtro ed è stato recapitato nella posta in arrivo perché è stata trovata una corrispondenza con un elenco Consenti nei criteri di filtro posta indesiderata, come l'**Elenco mittenti consentiti**.|
|SFV:SKB|Il messaggio è stato contrassegnato come posta indesiderata perché è stata trovata una corrispondenza con un elenco Blocca nei criteri di filtro posta indesiderata, come l'**Elenco mittenti bloccati**.|
|SFV:SKN|Il messaggio è stato contrassegnato come posta non indesiderata prima di essere elaborato dal filtro contenuto. Sono inclusi i messaggi in cui il messaggio corrisponde a una regola del flusso di posta per contrassegnarlo automaticamente come non indesiderato e ignorare tutti i filtri aggiuntivi.|
|SFV:SKN|Come per SFV:SKN, il messaggio ha ignorato il filtro per un altro motivo, ad esempio perché si tratta di posta elettronica tra organizzazioni all'interno di un tenant.|
|SFV:SKQ|Il messaggio è stato rilasciato dalla quarantena ed è stato inviato al destinatario.|
|SFV:NSPM|Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.|
|H: [helostring]|La stringa HELO or EHLO del server di posta elettronica di connessione.|
|PTR: [ReverseDNS]|Il record PTR o record "Pointer" dell'indirizzo IP del mittente, noto anche come indirizzo DNS inverso.|
|SFTY|Il messaggio è stato identificato come phishing e viene contrassegnato anche con uno dei valori seguenti: <br/>• 9,1: valore predefinito. Il messaggio contiene un URL di phishing, può contenere altro contenuto di phishing o potrebbe essere stato contrassegnato come phishing da un altro filtro di posta elettronica, ad esempio una versione locale di Exchange Server, prima di inoltrare il messaggio a Office 365. <br/>• 9,11: messaggi che non hanno avuto esito negativo per la falsificazione dei controlli in cui il dominio di invio nell'intestazione From è uguale a, o è allineato a, o fa parte della stessa organizzazione del dominio di ricezione. Ciò indica che al messaggio verrà aggiunto un suggerimento per la sicurezza dello spoofing intra-org. <br/>• 9,19: i messaggi di dominio non riusciti vengono verificati in cui il dominio di invio sta tentando di rappresentare un dominio di proprietà del destinatario oppure un dominio personalizzato protetto dal criterio anti-phishing. In questo modo viene aggiunto un suggerimento per la sicurezza della rappresentazione al messaggio, se abilitato tramite il criterio anti-phishing. <br/>• 9,20: messaggio la rappresentazione utente non riuscita verifica la posizione in cui l'utente che esegue l'invio sta tentando di rappresentare un utente all'interno dell'organizzazione dei ricevitori o un utente personalizzato protetto dal criterio di anti-phishing. In questo modo viene aggiunto un suggerimento per la sicurezza della rappresentazione al messaggio, se abilitato tramite il criterio anti-phishing. <br/>• 9,21: i controlli anti-spoofing non riusciti del messaggio e il dominio di invio nell'intestazione From: non vengono autenticati e provenienti da un dominio esterno. Utilizzato in combinazione con CompAuth (vedere Authentication-results). <br/>• 9,22: uguale a 9,21, tranne per il fatto che l'utente dispone di un mittente sicuro sottoposto a override. <br/>• 9,23: uguale a 9,22, tranne per il fatto che l'organizzazione ha un mittente o un dominio consentito che è stato sottoposto a override. <br/>• 9,24: uguale a 9,23, tranne per il fatto che l'utente dispone di una regola del flusso di posta di Exchange sottoposta a override.|
|X-CustomSpam: [ASFOption]|Il messaggio ha trovato un'opzione di filtro per la posta indesiderata avanzata. Ad esempio, **X-CustomSpam: I collegamenti immagini a siti remoti** indicano che l'opzione ASF dei **collegamenti immagini a siti remoti** ha trovato una corrispondenza. Per scoprire quale testo X-header viene aggiunto per ogni specifica opzione ASF, vedere [Advanced Spam Filtering Options](advanced-spam-filtering-asf-options.md).|
   
## <a name="x-microsoft-antispam-message-header-fields"></a>Campi di intestazione del messaggio X-Microsoft-Antispam 

Nella tabella seguente vengono descritti i campi utili nell'intestazione del messaggio **X-Microsoft-Antispam**. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.
  
|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|BCL|Il Livello di reclamo in blocco (BCL) del messaggio. Per ulteriori informazioni, vedere [Valori al livello reclamo massa](bulk-complaint-level-values.md).  |
|PCL|Il Livello di probabilità di phishing (PCL) del messaggio, che indica se si tratta di un messaggio di phishing. Lo stato restituito può avere i seguenti valori numerici: <br/>• **0-3**: il contenuto del messaggio non è probabile che sia phishing. <br/>• **4-8**: è probabile che il contenuto del messaggio sia phishing. <br/>• **-9990**: (solo Exchange Online Protection) è probabile che il contenuto del messaggio sia phishing.  <br/>  I valori vengono utilizzati per determinare quale azione viene eseguita dal client di posta elettronica sui messaggi. Ad esempio, Outlook utilizza il timbro PCL per bloccare il contenuto dei messaggi sospetti. Per ulteriori informazioni sul phishing e su come Outlook elabora i messaggi di phishing, vedere [Attivare o disattivare i collegamenti nei messaggi di posta elettronica](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).|
   
## <a name="authentication-results-message-header"></a>Intestazione del messaggio Authentication-results

I risultati dei controlli su SPF, DKIM e DMARC vengono registrati (o contrassegnati) da Office 365 nell'intestazione del messaggio **Authentication-results** quando i server di posta ricevono un messaggio di posta elettronica.
  
### <a name="check-stamp-syntax-and-examples"></a>Esempi e sintassi del contrassegno di controllo

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

Nella tabella seguente vengono descritti i campi e i valori possibili per il controllo di autenticazione di ogni messaggio di posta elettronica.
  
|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|spf|Descrive i risultati del controllo SPF per il messaggio. Tra i possibili valori sono inclusi:<br/>• **Pass (indirizzo IP)**: indica che il controllo SPF per il messaggio è stato superato e include l'indirizzo IP del mittente. Il client è autorizzato a inviare o inoltrare la posta elettronica per conto del dominio del mittente. <br/>• **Fail (indirizzo IP)**: indica che il controllo SPF per il messaggio non è stato superato e include l'indirizzo IP del mittente. A volte viene chiamato _errore non riuscito_. <br/>• **SoftFail (motivo)**: indica che il record SPF ha designato l'host come non autorizzato all'invio ma che è in fase di transizione. <br/>• **Neutral**: indica che il record SPF ha dichiarato in modo esplicito che non sta asserendo se l'indirizzo IP è autorizzato. <br/>• **None**: indica che il dominio non dispone di un record SPF o che il record SPF non restituisce un risultato. <br/>• **TempError**: indica che si è verificato un errore che potrebbe essere temporaneo, ad esempio un errore DNS. Riprovare in un secondo momento potrebbe avere un esito positivo senza alcun intervento dell'amministratore. <br/>• **PermError**: indica che si è verificato un errore permanente. Ciò accade quando, ad esempio, il dominio presenta un record SPF con formato non valido.|
|SMTP. Mailfrom|Contiene il dominio di origine da cui proviene il messaggio. Gli errori relativi a tale messaggio di posta elettronica verranno inviati al postmaster o all'entità responsabile del dominio. A volte viene chiamato indirizzo 5321.MailFrom o indirizzo reverse-path address sulla busta del messaggio.|
|dkim|Descrive i risultati del controllo DKIM per il messaggio. Tra i possibili valori sono inclusi:<br/>• **pass**: indica che il controllo DKIM per il messaggio è stato superato. <br/>• **Fail (Reason)**: indica che il controllo DKIM per il messaggio non è riuscito e perché. Ad esempio, se il messaggio non è stato firmato o se la firma non è stata verificata. <br/>• **None**: indica che il messaggio non è stato firmato. Ciò potrebbe indicare o meno che il dominio dispone di un record DKIM o che il record DKIM non restituisce un risultato, solo che il messaggio non è stato firmato.|
|header. d|Dominio identificato nella firma DKIM, se presente. Questo è il dominio sottoposto a query per la chiave pubblica.|
|dmarc|Descrive i risultati del controllo DMARC per il messaggio. Tra i possibili valori sono inclusi:<br/>• **pass**: indica che il controllo DMARC per il messaggio è stato superato. <br/>• **Fail**: indica che il controllo DMARC per il messaggio non è riuscito. <br/>• **bestguesspass**: indica che non esiste alcun record TXT DMARC per il dominio, ma, se ne esiste uno, il controllo di DMARC del messaggio verrebbe superato. Questo è il motivo per cui il dominio nell'indirizzo 5321.MailFrom corrisponde al dominio nell'indirizzo 5322.From. <br/>• **None**: indica che non esiste alcun record TXT DKIM per il dominio di invio in DNS.|
|action|Indica l'azione eseguita dal filtro posta indesiderata in base ai risultati del controllo DMARC. Ad esempio:<br/>• **PermError**: si è verificato un errore permanente durante la valutazione di DMARC, ad esempio un record TXT DMARC formato erroneamente in DNS. Tentando di inviare di nuovo questo messaggio, probabilmente si otterrebbe un risultato diverso. Al contrario, potrebbe essere necessario contattare il proprietario del dominio per risolvere il problema. <br/>• **TempError**: si è verificato un errore temporaneo durante la valutazione di DMARC. Potrebbe essere possibile richiedere che il mittente invii il messaggio in un secondo momento per elaborare il messaggio correttamente. <br/>• **oreject** o o **. Reject**: è l'acronimo di rifiuto di sostituzione. In questo caso, Office 365 usa questa azione quando riceve un messaggio che non supera il controllo DMARC da un dominio il cui record TXT DMARC ha un criterio di p=reject. Anziché eliminare o rifiutare il messaggio, Office 365 lo contrassegna come posta indesiderata. Per ulteriori informazioni sul motivo per cui Office 365 è configurato in questo modo, vedere [Come viene gestita la posta elettronica in ingresso che non supera il controllo DMARC in Office 365](use-dmarc-to-validate-email.md#inbounddmarcfail). <br/>• **PCT. Quarantine**: indica che una percentuale inferiore al 100% dei messaggi che non superano DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su quarantine, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato. <br/>• **PCT. Reject**: indica che una percentuale inferiore al 100% dei messaggi che non superano DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su reject, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato.|
|header. from|Il dominio dell'indirizzo mittente nell'intestazione del messaggio di posta elettronica. A volte viene chiamato indirizzo _5322. from_ .|
|compauth|Risultato dell'autenticazione composita. Utilizzato da Office 365 per combinare più tipi di autenticazione, ad esempio SPF, DKIM, DMARC o qualsiasi altra parte del messaggio, per determinare se il messaggio è stato autenticato o meno. Utilizza il dominio from: come base di valutazione.|
|motivo|Il motivo per cui l'autenticazione composita è passata o non è riuscita. Il valore del motivo è costituito da tre cifre: <br/>• **000**: errore esplicito dell'autenticazione del messaggio. Ad esempio, il messaggio ricevuto DMARC ha esito negativo con un'azione di quarantena o rifiuto. <br/>• **001**: l'autenticazione del messaggio non è stata eseguita in modo implicito e il dominio di invio non ha pubblicato i criteri di autenticazione. Ad esempio, un criterio di DMARC di p = None. <br/>• **1xx**: il messaggio ha superato l'autenticazione. Le seconde due cifre sono codici interni utilizzati da Office 365. <br/>• **2xx**: l'autenticazione del messaggio in modalità Soft-passed. Le seconde due cifre sono codici interni utilizzati da Office 365. <br/>• **3xx**: il messaggio non è stato controllato per l'autenticazione composita. <br/>• **4xx**: l'autenticazione composita ignorata del messaggio. Le seconde due cifre sono codici interni utilizzati da Office 365.|
