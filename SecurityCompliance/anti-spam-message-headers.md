---
title: Intestazioni messaggi della protezione da posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
description: Quando Exchange Online Protection analizza un messaggio di posta elettronica in ingresso, inserisce l'intestazione **X-Forefront-Antispam-Report** nel messaggio.
ms.openlocfilehash: 39cac8e1406bd4f7505ae4bc626b8c7e78f88101
ms.sourcegitcommit: 75b985b2574f4be70cf352498ea300b3d99dd338
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2018
ms.locfileid: "26255891"
---
# <a name="anti-spam-message-headers"></a>Intestazioni messaggi della protezione da posta indesiderata

Quando Exchange Online Protection analizza un messaggio di posta elettronica in ingresso, inserisce l'intestazione **X-Forefront-Antispam-Report** nel messaggio. I campi di questa intestazione consentono agli amministratori di ottenere informazioni relative al messaggio e a come è stato elaborato. I campi nell'intestazione **X-Microsoft-Antispam** forniscono informazioni aggiuntive sulla posta inviata in massa e sul phishing. Oltre a queste due intestazioni, Exchange Online Protection inserisce anche i risultati dell'autenticazione della posta elettronica per ogni messaggio che elabora nell'intestazione **Authentication-results**.
  
> [!TIP]
> Per informazioni sulla visualizzazione dell'intestazione di un messaggio di posta elettronica in diversi client di posta elettronica, vedere [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583). È possibile copiare e incollare il contenuto dell'intestazione di un messaggio nello strumento [Analizzatore intestazione messaggio](https://testconnectivity.microsoft.com/?tabid=mha). Quando si seleziona un messaggio nella quarantena nell'interfaccia di amministrazione di Exchange, il collegamento **Visualizza intestazione messaggio** consente di copiare e incollare facilmente il testo dell'intestazione del messaggio nello strumento . Dopo l'accesso allo strumento Analizzatore intestazione messaggio, fare clic su **Analizza intestazioni** per recuperare le informazioni sull'intestazione.
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>Campi di intestazione del messaggio X-Forefront-Antispam-Report
<a name="sectionSection0"> </a>

Dopo aver effettuato l'accesso alle informazioni relative all'intestazione del messaggio, cercare **X-Forefront-Antispam-Report**, quindi cercare i campi seguenti. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.

|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|CIP: [indirizzo IP]|L'indirizzo IP. È possibile specificare l'indirizzo IP durante la creazione di un elenco di indirizzi IP consentiti o un elenco di indirizzi IP bloccati nel filtro di connessione. Per ulteriori informazioni, vedere [configurare il criterio di filtro di connessione](configure-the-connection-filter-policy.md).|
|CTRY|Il paese dal quale il messaggio è stato connesso al servizio. Questo è determinato dall'indirizzo IP di connessione, il quale potrebbe non essere uguale all'indirizzo IP di invio di origine.|
|LANG|LANG: la lingua in cui è scritto il messaggio, come specificato dal codice paese (ad esempio, ru_RU per la Russia).|
|SCL|Il valore del livello di probabilità di posta indesiderata (SCL) del messaggio. Per ulteriori informazioni sull'interpretazione di questi valori, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).  |
|PCL|Il valore del livello di confidenza di Phishing (PCL) del messaggio. Vedere [PCL](anti-spam-message-headers.md#PCL) per ulteriori informazioni sui valori PCL.  |
|SRV:BULK|Il messaggio è stato identificato come un messaggio di posta elettronica in blocco. Se l' **opzione avanzata di filtro della posta indesiderata Blocca tutti i messaggi di posta in blocco** è abilitata, il messaggio verrà contrassegnato come posta indesiderata. Se l'opzione è disabilitata, il messaggio verrà contrassegnato come posta indesiderata solo se il resto delle regole del filtro stabiliscono che è indesiderato.  |
|SFV:SFE|Il filtro è stato ignorato e il messaggio è stato lasciato passare perché è stato inviato da un indirizzo presente in un singolo elenco dei mittenti attendibili.|
|SFV:BLK|Il filtro è stato ignorato e il messaggio è stato bloccato perché è stato inviato da un indirizzo presente in un singolo elenco dei mittenti bloccati.  <br/> **Suggerimento**: per ulteriori informazioni su come gli utenti finali possono creare elenchi di mittenti attendibili e bloccati, vedere [Blocca o Consenti (impostazioni di posta indesiderata)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (Outlook sul web) e [Panoramica del filtro per la posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook).|
|IPV:CAL|Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.|
|IPV:NLI|L'indirizzo IP non è stato elencato in nessuno degli elenchi di reputazione IP.|
|SFV:SPM|Il messaggio è stato contrassegnato come posta indesiderata dal filtro contenuto.|
|SFV:SKS|Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alle regole di trasporto, che lo contrassegnano automaticamente come indesiderato e che ignorano tutte le regole del filtro aggiuntive.|
|SFV:SKA|Il messaggio ha ignorato il filtro ed è stato recapitato nella posta in arrivo perché è stata trovata una corrispondenza con un elenco Consenti nei criteri di filtro posta indesiderata, come l' **Elenco mittenti consentiti**.|
|SFV:SKB|Il messaggio è stato contrassegnato come posta indesiderata perché è stata trovata una corrispondenza con un elenco Blocca nei criteri di filtro posta indesiderata, come l' **Elenco mittenti bloccati**.|
|SFV:SKN|Il messaggio è stato contrassegnato come posta non indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alle regole di trasporto, che lo contrassegnano automaticamente come non indesiderato e che ignorano tutte le regole del filtro aggiuntive.|
|SFV:SKN|Come per SFV:SKN, il messaggio ha ignorato il filtro per un altro motivo, ad esempio perché si tratta di posta elettronica tra organizzazioni all'interno di un tenant.|
|SFV:SKQ|Il messaggio è stato rilasciato dalla quarantena ed è stato inviato al destinatario.|
|SFV:NSPM|Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.|
|H: [helostring]|La stringa HELO or EHLO del server di posta elettronica di connessione.|
|PTR: [ReverseDNS]|Il record PTR o record "Pointer" dell'indirizzo IP del mittente, noto anche come indirizzo DNS inverso.|
|SFTY|Il messaggio è stato identificato come phishing e inoltre essere contrassegnato con uno dei valori seguenti: <br/>• 9.1: il valore predefinito. Il messaggio contiene un URL di phishing, può contenere altri contenuti phishing o contrassegnato come phishing da un altro filtro di posta elettronica, ad esempio una versione locale di Exchange Server prima di inoltrare il messaggio a Office 365. <br/>• 9.11: anti-spoofing controlli non riusciti di messaggio dove il dominio di invio nella From: intestazione equivale, risulti allineato con o fa parte della stessa organizzazione al dominio di destinazione. <br/>• 9.21: non è stato messaggio anti-spoofing controlli e il dominio di invio nella From: intestazione non esegue l'autenticazione. Utilizzare in combinazione con CompAuth (vedere i risultati di autenticazione). <br/>• 9.22: simile a 9.21, ad eccezione del fatto che l'utente dispone di un mittente protetto è stato sottoposto a override. <br/>• 9.23: simile a 9.22, ad eccezione del fatto che l'organizzazione dispone di un mittente consentiti o un dominio a cui è stato sottoposto a override. <br/>• 9,24: identico 9.23, ad eccezione del fatto che l'utente dispone di una regola di flusso della posta di Exchange che è stato sottoposto a override.|
|X-CustomSpam: [ASFOption]|I messaggi corrispondono a una filtro della posta indesiderata opzione. Ad esempio, **X-CustomSpam: collegamenti a siti remoti dell'immagine** indica che l'opzione **collegamenti immagini a siti remoti** ASF corrispondente. Per testo X-header viene aggiunto per ogni opzione ASF specifici, vedere [Opzioni di filtro posta indesiderata](advanced-spam-filtering-asf-options.md).|
   
## <a name="x-microsoft-antispam-message-header-fields"></a>Campi di intestazione del messaggio X-Microsoft-Antispam
<a name="sectionSection1"> </a>

Nella tabella seguente vengono descritti i campi utili nell'intestazione del messaggio **X-Microsoft-Antispam**. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.
  
|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|BCL|Il Livello di reclamo in blocco (BCL) del messaggio. Per ulteriori informazioni, vedere [Valori al livello reclamo massa](bulk-complaint-level-values.md).  |
|PCL|Livello di probabilità di Phishing (PCL) del messaggio che indica se si tratta di un messaggio di phishing. Questo stato può essere restituito come uno dei valori numerici seguenti:<br/>• **0-3**: il contenuto del messaggio non è probabilmente phishing. <br/>• **4 a 8**: il contenuto del messaggio è probabilmente phishing. <br/>• **-9990**: (Exchange Online Protection solo) il contenuto del messaggio è probabilmente phishing.  <br/>  I valori vengono utilizzati per determinare quale azione accetta i client di posta elettronica nei messaggi. Ad esempio, Outlook utilizza il timbro PCL per bloccare il contenuto dei messaggi sospetti. Per ulteriori informazioni su phishing e la modalità di elaborazione dei messaggi di phishing in Outlook, vedere [attivare o disattivare i collegamenti nei messaggi di posta elettronica](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).|
   
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
|spf|Descrive i risultati del controllo SPF per il messaggio. Tra i possibili valori sono inclusi:  <br/>• **passa (indirizzo IP)**: indica la verifica SPF per il messaggio passato e include l'indirizzo IP del mittente. Il client è autorizzato a inviare o l'inoltro di posta elettronica per conto del dominio del mittente.<br/>• **esito negativo (indirizzo IP)**: indica la verifica SPF per il messaggio non è riuscita e include l'indirizzo IP del mittente. Questa operazione è definita a volte _non riuscito_.<br/>• **softfail (motivo)**: indica che il record SPF ha designato l'host come non consentiti per l'invio ma è in transizione. <br/>• **neutro**: indica che il record SPF è dichiarare esplicitamente che non implicitamente se l'indirizzo IP è autorizzato. <br/>• **Nessuno**: indica che il dominio non dispone di un record SPF o record SPF non restituisce un risultato. <br/>• **temperror**: indica un errore che può essere temporaneo di natura, ad esempio, un errore DNS. Tentativo in un secondo momento potrebbe avere esito positivo senza effettuare alcuna operazione di amministratore.<br/>• **permerror**: indica che si è verificato un errore permanente. Si verifica quando, ad esempio, il dominio è un record SPF formato non corretto.|
|SMTP.MailFrom|Contiene il dominio di origine da cui proviene il messaggio. Gli errori relativi a tale messaggio di posta elettronica verranno inviati al postmaster o all'entità responsabile del dominio. A volte viene chiamato indirizzo 5321.MailFrom o indirizzo reverse-path address sulla busta del messaggio.|
|dkim|Descrive i risultati del controllo DKIM per il messaggio. Tra i possibili valori sono inclusi:  <br/>• **passare**: indica il controllo DKIM per il messaggio passato. <br/>• **esito negativo (motivo)**: indica il controllo DKIM per il messaggio di errore e sui motivi per cui. Ad esempio, se il messaggio non è stato eseguito l'accesso o la firma non è stata verificata.<br/>• **Nessuno**: indica che il messaggio non è stato firmato. Ciò può o non potrebbe indicare che il dominio include un record DKIM o il record DKIM non restituisce un risultato, solo che questo messaggio non è stato firmato.|
|Header.d|Dominio identificato nella firma DKIM, se presente. Questo è il dominio sottoposto a query per la chiave pubblica.|
|dmarc|Descrive i risultati del controllo DMARC per il messaggio. Tra i possibili valori sono inclusi:  <br/>• **passare**: indica il controllo DMARC per il messaggio passato. <br/>• **esito negativo**: indica il controllo DMARC per il messaggio non è riuscito. <br/>• **bestguesspass**: indica che non esiste alcun record TXT DMARC per il dominio, ma se una esistevano viene passato il controllo DMARC per il messaggio. Ciò avviene perché il dominio dell'indirizzo 5321.MailFrom corrisponda al dominio dell'indirizzo 5322.From.<br/>• **Nessuno**: indica che non esiste alcun record TXT DKIM per il dominio di invio nel sistema DNS.|
|action|Indica l'azione eseguita dal filtro posta indesiderata in base ai risultati del controllo DMARC. Ad esempio:  <br/>• **permerror**: si è verificato un errore permanente durante la valutazione DMARC, ad esempio che si verifichi un TXT DMARC in formato non corretto registrare in DNS. Se si tenta di inviare nuovamente il messaggio non è probabile che terminano con un risultato diverso. In realtà, è necessario contattare il proprietario del dominio per risolvere il problema.<br/>• **temperror**: si è verificato un errore temporaneo durante la valutazione DMARC. È possibile richiedere che il mittente rinviare il messaggio in seguito per elaborare il messaggio di posta elettronica in modo corretto.<br/>• **oreject** o **o.reject**: sta per eseguire l'override Rifiuta. In questa utilizza case Office 365 questa azione quando viene ricevuto un messaggio che si verifica un errore di DMARC di controllo di un dominio a cui il record TXT DMARC dispone di un criterio di p = Rifiuta. Invece di eliminazione o rifiuto del messaggio, Office 365 messaggio viene contrassegnato come posta indesiderata. Per ulteriori informazioni su perché Office 365 è configurato in questo modo, vedere [i punti di manipolazione come Office 365 in ingresso di posta elettronica che si verifica un errore DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).<br/>• **pct.quarantine**: indica che una percentuale inferiore al 100% dei messaggi che non si passano DMARC devono essere recapitata comunque. Ciò significa che il messaggio non è riuscita DMARC e il criterio è stato impostato per mettere in quarantena, ma il campo pct non è impostato su 100% e il sistema in modo casuale determinato non si applica l'azione DMARC, in base a criteri del dominio specificato.<br/>• **pct.reject**: indica che una percentuale inferiore al 100% dei messaggi che non si passano DMARC devono essere recapitata comunque. Ciò significa che il messaggio non è riuscita DMARC e il criterio è stato impostato per rifiutare, ma il campo pct non è impostato su 100% e il sistema in modo casuale determinato non si applica l'azione DMARC, in base a criteri del dominio specificato.|
|Header.From|Il dominio dell'indirizzo di mittente nell'intestazione del messaggio di posta elettronica. Questo è detto anche indirizzo _5322.From_ .|
|compauth|Risultato dell'autenticazione composito. Utilizzato da Office 365 per combinare più tipi di autenticazione, ad esempio SPF, DKIM, DMARC o qualsiasi altra parte del messaggio per determinare se il messaggio viene autenticato. Viene utilizzato da: dominio come base di valutazione.|
|motivo|Il motivo per l'autenticazione composito passato o non è riuscita. Il valore per il motivo è costituito da tre cifre:<br/>• **000**: il messaggio di autenticazione non riuscita in modo esplicito. Ad esempio, il messaggio ricevuto fail DMARC con un'azione di quarantena o su Rifiuta.<br/>• **001**: il messaggio non è riuscita in modo implicito l'autenticazione e il dominio di invio non è stato pubblicare i criteri di autenticazione. Ad esempio, il criterio DMARC p = none.<br/>• **1xx**: il messaggio passato l'autenticazione. In secondo luogo due cifre sono codici interni utilizzati da Office 365.<br/>• **2xx**: l'autenticazione di passate reversibile. In secondo luogo due cifre sono codici interni utilizzati da Office 365.<br/>• **3xx**: il messaggio non è stato selezionato per l'autenticazione composito. <br/>• **4xx**: il messaggio ignorato autenticazione composito. In secondo luogo due cifre sono codici interni utilizzati da Office 365.|
