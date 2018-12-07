---
title: Protezione anti-spoofing in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
description: In questo articolo viene descritto come Office 365 attenua contro gli attacchi di phishing che utilizzi contraffatto mittente domini, vale a dire che viene eseguito lo spoofing. Per ottenere questo risultato analisi dei messaggi e blocco quelle che possono essere autenticati neithe utilizzando i metodi di autenticazione standard di posta elettronica, né altri tecniche di reputazione mittente. Questa modifica viene viene implementata in modo da ridurre il numero di attacchi di phishing sono esposte per organizzazioni di Office 365.
ms.openlocfilehash: 95f4995b6447870700bc483f205ca3ff831045f5
ms.sourcegitcommit: 8c5a88433cff23c59b436260808cf3d91b06fdef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/07/2018
ms.locfileid: "27194717"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Protezione anti-spoofing in Office 365

In questo articolo viene descritto come Office 365 attenua contro gli attacchi di phishing che utilizzi contraffatto mittente domini, vale a dire che viene eseguito lo spoofing. Per ottenere questo risultato analisi dei messaggi e quelli che non possono essere autenticati utilizzando i metodi di autenticazione standard di posta elettronica, né altri tecniche di reputazione mittente di blocco. Questa modifica viene viene implementata in modo da ridurre il numero di attacchi di phishing clienti vengono presentati.
  
In questo articolo viene inoltre perché questa modifica è in corso la creazione, come i clienti possono preparare la modifica, come visualizzare i messaggi che saranno interessati, come segnalare i messaggi, come per ridurre i falsi positivi, nonché come mittenti a Microsoft necessario predisporre modificare.
  
Protezione anti-spoofing tecnologia Microsoft è stata inizialmente distribuita per le organizzazioni che hanno una sottoscrizione a Office 365 Enterprise E5 o hanno acquistato il componente aggiuntivo di Office 365 avanzate Threat Protection (degli strumenti di analisi) per la sottoscrizione. A partire da ottobre, 2018 è stata estesa la protezione per le organizzazioni che hanno anche Exchange Online Protection (EOP). Inoltre, a causa della modalità di che tutti i filtri informazioni tra loro, gli utenti Outlook.com anche interessati.
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Modalità lo spoofing di attacchi di phishing

Quando si tratta di protezione degli utenti, Microsoft prese in considerazione il rischio di phishing. Tra le tecniche che in genere utilizzano mittenti di posta indesiderata e autori spoofing, ovvero quando viene effettuato al mittente e viene visualizzato un messaggio sembrano provenire da una persona o in un punto qualsiasi diverso da origine effettivo. Questa tecnica viene spesso utilizzata nelle campagne di phishing progettate per ottenere le credenziali utente. Anti-spoofing tecnologia Microsoft esamina in modo specifico FALSO del ' da: intestazione ' che sia quello che viene visualizzato un client di posta elettronica come Outlook. Quando Microsoft con confidenza elevata che From: intestazione viene eseguito lo spoofing, identifica il messaggio come un spoofing.
  
Messaggi di spoofing influire negativamente sulle due negativi per gli utenti reali:
  
### <a name="1-spoofed-messages-deceive-users"></a>1. messaggi di spoofing inganno gli utenti
  
Per prima cosa, un messaggio di spoofing può indurre un utente a facendo clic su un collegamento e che le credenziali, download malware o la risposta a un messaggio con contenuto riservato (quest'ultima dei quali è noto come violazione della posta elettronica aziendale). Ad esempio, le operazioni seguenti è un messaggio di phishing con un mittente spoofing di msoutlook94@service.outlook.com:
  
![Messaggi di phishing service.outlook.com di rappresentazione](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
Il precedente non effettivamente proviene dal service.outlook.com, ma in realtà è stata spoofing da specificati per migliorare l'aspetto di quello. Sta tentando di indurre un utente a fare clic sul collegamento all'interno del messaggio.
  
Nell'esempio successivo è lo spoofing contoso.com:
  
![Messaggio di phishing - violazione della posta elettronica aziendale](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
Il messaggio cercato legittimo, ma è in effetti un spoofing. Questo messaggio di phishing è un tipo di violazione della posta elettronica aziendale che corrisponde a una sottocategoria di phishing.
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. utenti confondere messaggi reali per quelle falsi
  
I messaggi in secondo luogo, spoofing creare incertezze per gli utenti che conoscono sui messaggi di phishing ma non può distinguere tra un messaggio reale e uno falsificati. Ad esempio, di seguito è un esempio di un effettivo la reimpostazione della password dall'indirizzo di posta elettronica di Microsoft Security account:
  
![Reimpostazione della password legittimi Microsoft](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
Il messaggio è stato provengono da Microsoft, ma al contempo, gli utenti vengono utilizzati per il recupero di messaggi di phishing può indurre un utente a fare clic su un collegamento e che le credenziali, download malware o la risposta a un messaggio con contenuto riservato. Poiché è difficile stabilire la differenza tra una reimpostazione della password reali e un falso, molti utenti ignorano questi messaggi, segnalarli come posta indesiderata o inutilmente restituiscono i messaggi a Microsoft come persa tentativi di phishing.
    
Per arrestare lo spoofing, il filtro settore della posta elettronica ha sviluppato i protocolli di autenticazione di posta elettronica, ad esempio [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)e [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). DMARC impedisce lo spoofing analisi mittente del messaggio - quello che viene visualizzato nel proprio client di posta elettronica (negli esempi precedenti, si tratta service.outlook.com, outlook.com e accountprotection.microsoft.com) - con il dominio che passa SPF o DKIM. Vale a dire il dominio che viene visualizzato è stato autenticato e pertanto è non spoofing. Per un esame approfondito, vedere la sezione "*informazioni sui motivi per cui l'autenticazione di posta elettronica non è sempre sufficienti per arrestare lo spoofing"* più avanti in questo documento. 
  
Tuttavia, il problema è che l'autenticazione di posta elettronica record sono facoltativi, non è necessario. Di conseguenza, mentre i domini con i criteri di autenticazione avanzata like microsoft.com e skype.com sono protetti da attacchi di spoofing, domini pubblicare in tutti i criteri di autenticazione più vulnerabili o nessun criterio, sono obiettivi di spoofing. A partire da marzo 2018, solo 9% dei domini di società in Fortune 500 pubblicare criteri di autenticazione tramite posta elettronica sicuro. Le restanti 91% potrebbe spoofing da parte di un specificati e a meno che non viene rilevato dal filtro per la posta utilizzando un altro criterio, può essere recapitato a un utente finale e inganno li:
  
![Criteri di gruppo Fortune 500 DMARC](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
La percentuale di piccole e medie dimensioni società che non sono in Fortune 500 che pubblica i criteri di autenticazione tramite posta elettronica sicuro è più piccolo e più piccolo ancora per i domini che si trovano all'esterno dell'Europa occidentale e Nord America.
  
Si tratta di un grosso problema quanto mentre le organizzazioni potrebbero non essere consapevoli di funzionamento dell'autenticazione di posta elettronica, autori comprendere e sfruttare la mancanza di esso.
  
Per informazioni sull'impostazione SPF, DKIM e DMARC, vedere la sezione "*ai clienti di Office 365"* più avanti in questo documento. 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>Arresto spoofing con l'autenticazione di posta elettronica implicita

Poiché i tentativi di phishing e spear sono verificato un problema a causa dell'adozione limitato di criteri di autenticazione tramite posta elettronica sicuro, Microsoft continua a investire in funzionalità che consentono di proteggere i propri clienti. Di conseguenza, Microsoft sta spostando anticipo con *l'autenticazione di posta elettronica implicita* - se non autenticazione un dominio, Microsoft verrà considerato come se fosse pubblicato posta authentication record e considerarlo conseguenza se non passa. 
  
Per ottenere questo risultato, Microsoft ha creato numerose estensioni per l'autenticazione di posta elettronica regolare inclusi reputazione del mittente, cronologia mittente/destinatario, analisi comportamento e altre tecniche avanzate. Messaggio inviato da un dominio non pubblica l'autenticazione di posta elettronica verrà contrassegnato come spoofing a meno che non contiene altre segnali indicare che sia valido.
  
In questo modo, possono avere gli utenti finali probabilità che un messaggio di posta elettronica inviato a tali non è stato spoofing, mittenti possono essere certi che nessuno è una rappresentazione del proprio dominio e ai clienti di Office 365 possono offrire anche della protezione, ad esempio protezione rappresentazione.
  
Per verificare l'annuncio generale di Microsoft, vedere [A mare di Rilevatore attività parte 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>Identificazione di un messaggio è classificato come spoofing

### <a name="composite-authentication"></a>Autenticazione composito

Sebbene SPF, DKIM e DMARC siano tutti utili per sé, non comunicano sufficiente lo stato di autenticazione nel caso in cui un messaggio non contiene alcun record autenticazione esplicite. Di conseguenza, Microsoft ha sviluppato un algoritmo che combina più segnali in un singolo valore denominato autenticazione composito o compauth in breve. I clienti in Office 365 hanno valori compauth con indicatore data e all'intestazione *Dei risultati di autenticazione* nelle intestazioni dei messaggi. 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**Risultati CompAuth**|**Descrizione**|
|:-----|:-----|
|esito negativo|Messaggio non è riuscita autenticazione esplicite (dominio di invio pubblicati i record in modo esplicito in DNS) o autenticazione implicita (l'invio di dominio è stato non pubblica i record DNS, in modo che Office 365 interpolati il risultato come se fosse pubblicato record).|
|passare|Messaggio passato autenticazione esplicite (messaggio passato DMARC o [Migliore suppone passato DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) o autenticazione implicita con confidenza elevata (l'invio di dominio non pubblica i record di autenticazione di posta elettronica, ma Office 365 ha segnali di back-end sicuro indicare il messaggio è probabilmente legittimi).|
|softpass|Messaggio passato autenticazione implicita con confidenza medio-basso (invio dominio non pubblica l'autenticazione di posta elettronica, ma Office 365 ha segnali back-end per indicare il messaggio è valido, ma la potenza del segnale è più vulnerabile).|
|nessuno|Messaggio non è autenticato o l'autenticazione, ma non l'allineamento, ma composito autenticazione non è stato applicato a causa di reputazione mittente o altri fattori.|
   
|||
|:-----|:-----|
|**Motivo**|**Descrizione**|
|0XX|Messaggio di autenticazione composito non riuscita.<br/>**000** indica che non è stato DMARC con un'azione di quarantena o rifiuta il messaggio.                    -001 indica che il messaggio non è riuscita l'autenticazione di posta elettronica implicita. Ciò significa che il dominio di invio non dispone di record di autenticazione di posta elettronica pubblicati o in caso affermativo, aveva un criterio di errori più vulnerabile (fail soft SPF o indipendente dalla DMARC, il criterio di p = none).<br/>**002** indica che l'organizzazione dispone di un criterio per la coppia di mittente o il dominio in modo esplicito è consentito l'invio di posta elettronica falsificato, questa impostazione viene impostata manualmente dall'amministratore.  <br/>**010** indica che non è stato DMARC con un'azione di quarantena o rifiuta il messaggio e il dominio di invio è uno dei domini dell'organizzazione accettati (fanno parte della self a sé o intra-org, lo spoofing).  <br/>**011** indica che il messaggio non è riuscita l'autenticazione di posta elettronica implicita e il dominio di invio è uno dei domini accettati dell'organizzazione (fanno parte della self a sé o intra-org, lo spoofing).|
|Tutti gli altri codici (1xx, 2xx, 3xx, 4xx, 5xx)|Corrisponde a diversi codici interni per il motivo per cui un messaggio passato autenticazione implicita oppure non dispone di alcun tipo di autenticazione, ma è stata applicata alcuna azione.|
   
Esaminando le intestazioni del messaggio, un amministratore o persino un utente finale può determinare come Office 365 arriva alla conclusione che il mittente può essere eseguito lo spoofing.
  
### <a name="differentiating-between-different-types-of-spoofing"></a>Per distinguere tra diversi tipi di spoofing

Microsoft viene fatta distinzione tra due diversi tipi di spoofing messaggi:
  
 **Spoofing dell'organizzazione tra organizzazioni**
  
Nota anche come lo spoofing self a sé, questo problema si verifica quando il dominio da: indirizzo è uguale o risulti allineato con il dominio del destinatario (quando il dominio del destinatario è uno dei [Domini accettati](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)dell'organizzazione). In alternativa, se il dominio da: indirizzo fa parte della stessa organizzazione.
  
Ad esempio, le operazioni seguenti ha mittente e destinatario dello stesso dominio (contoso.com). Vengono inseriti spazi nell'indirizzo di posta elettronica per impedire la raccolta spambot in questa pagina):
  
Da: mittente @ contoso.com
  
A: destinatario @ contoso.com
  
Le operazioni seguenti con i domini di mittente e destinatario allineamento con il dominio dell'organizzazione (fabrikam.com):
  
Da: mittente @ foo.fabrikam.com
  
A: destinatario @ bar.fabrikam.com
  
Domini di mittente e destinatario seguenti sono diversi (microsoft.com e bing.com), ma appartengono alla stessa organizzazione (vale a dire, entrambi sono parte di domini accettati dell'organizzazione):
  
Da: mittente @ microsoft.com
  
A: destinatario @ bing.com
  
Messaggi che non superano lo spoofing tra organizzazione contengono i valori seguenti nelle intestazioni:
  
X-Forefront-Antispam-Report:... CAT:SPM/HSPM/PHSH;... SFTY:9.11
  
Il gatto è la categoria del messaggio e in genere è contrassegnato come SPM (spam), ma occasionalmente potrebbero essere HSPM (spam confidenza elevata) o per attività di PHISHING (anti-phishing) seconda gli altri tipi di modelli di generato nel messaggio.
  
Il SFTY è il livello di sicurezza del messaggio, la prima cifra (9) indica che il messaggio è phishing e secondo insieme di cifre dopo il punto (11) che significa che è lo spoofing dell'organizzazione tra organizzazioni.
  
Non esiste alcun codice motivo specifico per l'autenticazione composito per intra-org lo spoofing, che verrà identificati più avanti in 2018 (timeline non ancora definito).
  
 **Spoofing di altri domini**
  
Questo problema si verifica quando il dominio di invio nella From: l'indirizzo è un dominio esterno all'organizzazione di destinazione. Messaggi di autenticazione composito esito negativo a causa di altri domini spoofing possono includere i seguenti valori nelle intestazioni:
  
Risultati di autenticazione:... compauth = fail motivo = 000/001
  
X-Forefront-Antispam-Report:... CAT:SPOOF;... SFTY:9.22
  
In entrambi i casi, il suggerimento sicurezza rosso seguente viene indicato nel messaggio o equivalente personalizzato per la lingua della cassetta postale del destinatario:
  
![Suggerimento sicurezza rosso - rilevamento truffe di false](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
È solo esaminando From: indirizzi e sapere che cos'è la posta elettronica del destinatario o dal controllo intestazioni del messaggio di posta elettronica, che è possibile distinguere tra organizzazione e tra domini spoofing.
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Come i clienti di Office 365 possono prepararsi per la protezione anti-spoofing nuova

### <a name="information-for-administrators"></a>Informazioni per gli amministratori

Amministratore di un'organizzazione in Office 365, esistono fondamentali è necessario tenere conto delle informazioni.
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Informazioni sui motivi per cui l'autenticazione di posta elettronica non è sempre sufficienti per arrestare lo spoofing

La nuova protezione anti-spoofing si basa sull'autenticazione di posta elettronica (SPF, DKIM e DMARC) non contrassegnare un messaggio come lo spoofing. Un esempio comune è quando un dominio di invio pubblicati i record SPF. Se nessun record SPF o queste sono state impostate in modo non corretto, di un messaggio verrà contrassegnato come spoofing a meno che non dispone di Microsoft Business intelligence di back-end che informa che il messaggio è valido.
  
Ad esempio, prima di anti-spoofing da distribuire, un messaggio può essere simili seguenti con nessun record SPF, nessun record DKIM e nessun record DMARC: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
Dopo lo spoofing anti, se si dispone di Office 365 Enterprise E5, EOP o degli strumenti di analisi, viene indicato il valore compauth:
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

Se example.com fissi questo dall'impostazione di un record SPF ma non un record DKIM, passare autenticazione composito in quanto il dominio che passato SPF allineato al dominio in From: indirizzo: 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

In alternativa, se è configurato un record DKIM, ma non un record SPF, autenticazione composito inoltre passare perché il dominio della firma DKIM passare allineato al dominio in From: indirizzo: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

Un specificati possono inoltre impostare SPF e DKIM e firmare il messaggio con i propri dominio, tuttavia, specificare un dominio diverso da: indirizzo. SPF né DKIM richiede il dominio per allineare il dominio nel From: indirizzo, in modo che a meno che non example.com pubblicati i record DMARC, questo non verrà contrassegnato come un spoofing utilizzando DMARC: 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

Nel client di posta elettronica (Outlook, Outlook sul web o qualsiasi altro client di posta elettronica), solo da: dominio viene visualizzato, non al dominio in SPF o DKIM e che può indurre l'utente a ritenere example.com cui proviene il messaggio, ma effettivamente proviene da maliciousDomain.com .
  
![Messaggio autenticato ma da: dominio non esegue l'allineamento con quali passati SPF o DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
Per questo motivo, è necessario Office 365 al dominio in From: indirizzo risulti allineato con il dominio della firma SPF o DKIM e se non, contiene alcuni altri segnali interni che indica che il messaggio è valido. In caso contrario, il messaggio sarà fail compauth. 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

In questo modo, lo spoofing anti Office 365 protegge contro domini senza autenticazione e contro domini che ha configurato l'autenticazione ma mancata corrispondenza rispetto al dominio in From: indirizzo come in quello che l'utente visualizza e ritiene che sia il mittente del messaggio. Ciò è valido sia dei domini esterni all'organizzazione, nonché domini all'interno dell'organizzazione.
  
Se si riceve un messaggio che non è riuscita composito autenticazione e viene contrassegnato come spoofing, anche se il messaggio passato SPF e DKIM, è pertanto perché il dominio che passato SPF e DKIM non vengono allineati con il dominio nella From: indirizzo.
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>Informazioni sulle modifiche in modo spoofing messaggi di posta elettronica vengono considerati

Attualmente, per tutte le organizzazioni di Office 365 - degli strumenti di analisi e non-degli strumenti di analisi - i messaggi che non superano i DMARC con un criterio di rifiuto o quarantena sono contrassegnati come posta indesiderata e in genere richiedere l'azione posta indesiderata con confidenza elevata, in alcuni casi l'azione posta indesiderata regolare (a seconda se altre posta indesiderata le regole prima identificano come posta indesiderata). Rilevamenti di spoofing intra org eseguire l'azione posta indesiderata regolari. Questo problema non è necessario abilitare né può essere disattivata.
  
Tuttavia, per i messaggi di spoofing tra domini, prima di questa modifica verrebbero tramite controlli regolari posta indesiderata, per attività di phishing e malware e se altre parti del filtro li identificato come sospetti, sarebbe contrassegnarli come posta indesiderata, per attività di phishing o malware rispettivamente. Con la nuova protezione spoofing tra domini, tutti i messaggi che non possono essere autenticati, per impostazione predefinita, eseguirà l'azione definito in Anti-phishing \> criteri anti-spoofing. Se non definita, verrà spostato in una cartella posta indesiderata degli utenti. In alcuni casi, i messaggi sospetti più disporrà inoltre la punta di sicurezza rosso aggiunta al messaggio.
  
Ciò potrebbe causare alcuni messaggi che sono state precedentemente contrassegnati come posta indesiderata ancora Guida contrassegnati come posta indesiderata ma avranno anche un suggerimento sicurezza rosso; in altri casi, i messaggi che sono state precedentemente contrassegnati come posta non indesiderata avvierà venga contrassegnato come posta indesiderata (CAT:SPOOF) con un suggerimento sicurezza rosso aggiunto. In altri casi ancora, i clienti che sono stati spostato tutti posta indesiderata e per attività di phishing in quarantena ora visualizzati entrata nella cartella posta indesiderata (questo problema può essere modificato, vedere [Modifica delle impostazioni di protezione anti-spoofing](#changing-your-anti-spoofing-settings)).
  
Sono disponibili diversi modi diversi che un messaggio può essere eseguito lo spoofing (vedere [differenziazione tra diversi tipi di spoofing](#differentiating-between-different-types-of-spoofing) più indietro in questo articolo), ma a partire da marzo 2018 il modo in cui che Office 365 considera questi messaggi non è ancora unificato. Nella tabella seguente è riportato un riepilogo rapido, con protezione spoofing domini viene di nuovo comportamento: 
  
|**Tipo di spoofing**|**Categoria**|**Suggerimento sicurezza aggiunto?**|**Si applica a**|
|:-----|:-----|:-----|:-----|
|Fail DMARC (quarantena o rifiuto)  <br/> |HSPM (predefinito), potrebbe anche essere SPM o PHSH  <br/> |No (non ancora)  <br/> |Tutti i clienti di Office 365, Outlook.com  <br/> |
|Self-self  <br/> |SPM  <br/> |Sì  <br/> |Tutte le organizzazioni di Office 365, Outlook.com  <br/> |
|Altri domini  <br/> |SPOOFING  <br/> |Sì  <br/> |Clienti di Office 365 avanzate Threat Protection ed E5  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a>Modifica delle impostazioni di protezione anti-spoofing

Per creare o aggiornare le impostazioni di protezione anti-spoofing (domini), accedere a protezione Anti-phishing \> Anti-spoofing impostazioni in gestione rischio \> scheda Criteri di sicurezza &amp; centro conformità. Se non si sono mai stata creata tutte le impostazioni di protezione anti-phishing, è necessario creare uno:
  
![Antiphishing - creare un nuovo criterio](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
Se è già stato creato uno, è possibile selezionare per modificarla:
  
![Antiphishing - Modifica criterio esistente](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
Selezionare il criterio appena creato, eseguire le procedure descritte come descritto in [ulteriori informazioni sulla Business Intelligence di spoofing.](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)
  
![Abilitare o disabilitare antispoofing](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![Attivare o disattivare i suggerimenti di sicurezza antispoofing](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
Per creare un nuovo criterio tramite PowerShell: 
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

È quindi possibile modificare i parametri dei criteri anti-phishing tramite PowerShell, dopo la documentazione [all'Insieme AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). È possibile specificare il $name come parametro:
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

Più avanti in 2018, anziché la necessità di creare un criterio predefinito, ne verrà creato automaticamente l'ambito a tutti i destinatari dell'organizzazione in modo che non è necessario specificare manualmente (nelle figure che sono soggetti a modifiche prima dell'implementazione finale).
  
![Criterio predefinito per Antiphishing](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
A differenza di un criterio che si crea, è possibile eliminare il criterio predefinito, modificare la priorità o scegliere quali utenti, domini o gruppi come ambito per.
  
![Dettagli relativi al criterio predefinito antiphishing](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
Per impostare i motivi di sicurezza predefinito tramite PowerShell:
  
```
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

È consigliabile disabilitare la protezione anti-spoofing solo se si dispone di un altro server di posta elettronica o server davanti a Office 365 (vedere legittimi scenari per disabilitare lo spoofing anti per ulteriori informazioni). 
  
```
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> Al primo hop del percorso di posta elettronica è Office 365, se si desidera ottenere i messaggi di posta elettronica legittimi troppi contrassegnati come spoofing, deve innanzitutto impostare i mittenti che possono inviare posta elettronica falsificato al dominio (vedere la sezione "gestione dei mittenti legittimi che inviano u * messaggio di posta elettronica nauthenticated"* ). Se si desidera ottenere comunque troppi falsi positivi (ad esempio, legittimo i messaggi contrassegnati come spoofing), non è consigliabile disabilitare completamente la protezione anti-spoofing. In realtà, è consigliabile scegliendo base invece di protezione elevata.                    È preferibile utilizzare tramite falsi positivi rispetto alla esporre un'organizzazione per la posta elettronica falsificato che potrebbe finire imporre costi significativamente superiori a lungo termine.

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>Gestione dei mittenti legittimi l'invio di posta elettronica non autenticato

Office 365 si tiene traccia della che invia messaggio di posta elettronica non autenticato nell'organizzazione. Se il servizio ritiene che il mittente non è valido, verrà contrassegnato come un errore *compauth* . Verrà essere classificata come SPOOFING anche se tutto dipende i criteri anti-spoofing che è stato applicato al messaggio. 
  
Tuttavia, come amministratore, è possibile specificare i mittenti sono consentiti inviare la posta elettronica falsificato, ignorare la decisione di Office 365.
  
**Metodo 1 - se l'organizzazione possiede il dominio, impostato l'autenticazione di posta elettronica**
  
Questo metodo può essere utilizzato per risolvere lo spoofing interne all'organizzazione e tra domini spoofing nei casi in cui proprietario o interagire con più tenant. Consente inoltre di risolvere lo spoofing tra domini in cui inviano a altri clienti in Office 365, nonché le terze parti che sono ospitate in altri provider.
  
Per ulteriori informazioni, vedere [i clienti di Office 365](#customers-of-office-365). 
 
**Metodo 2 - intelligence spoofing utilizzare per configurare consentiti mittenti di posta elettronica non autenticato**
  
È inoltre possibile utilizzare [Intelligence spoofing](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) per consentire i mittenti per trasmettere i messaggi non autenticati nell'organizzazione. 
  
Per i domini esterni, l'utente spoofing è il dominio nell'indirizzo del mittente, mentre l'infrastruttura di invio è l'indirizzo IP invio (suddivisa /24 intervalli CIDR), o nel dominio dell'organizzazione del record PTR (nella cattura di schermata seguente, l'indirizzo IP del mittente può da cui il record PTR è outbound.mail.protection.outlook.com 131.107.18.4 e viene visualizzato come outlook.com per l'infrastruttura di invio).
  
Per consentire a questo mittente di inviare la posta elettronica non autenticato, modificare **No** , **Yes**.
  
![Impostazione di antispoofing mittenti consentiti](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
È inoltre possibile utilizzare PowerShell per consentire mittente specifico lo spoofing del dominio: 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Guida mittenti spoofing tramite Powershell](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
Nella figura precedente, le interruzioni di riga aggiuntive sono state aggiunte per effettuare questa cattura di schermata basse, ma in realtà tutti i valori verrebbero visualizzate in un'unica riga.
  
Modificare il file e individuare la riga corrispondente a outlook.com e bing.com e modificare la voce AllowedToSpoof da No a Sì:
  
![Consenti spoofing impostazione su Sì tramite Powershell](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
Salvare il file e quindi eseguire: 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

In questo modo ora bing.com per l'invio della posta elettronica non autenticata da \*. outlook.com.

**Metodo 3: creare una voce Consenti per la coppia mittente/destinatario**
  
È anche possibile scegliere di ignorare tutti i filtri per un determinato mittente. Per ulteriori informazioni, vedere [procedura aggiungere in modo sicuro un mittente all'elenco Consenti in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).
  
Se si utilizza questo metodo, non verrà eseguita la posta indesiderata e alcuni dei filtri per attività di phishing, ma non il filtro di malware.
  
**Metodo 4 - contattare il mittente e chiedere di impostare l'autenticazione di posta elettronica**
  
A causa del problema di posta indesiderata e phishing, è consigliabile tutti i mittenti, impostare l'autenticazione di posta elettronica. Se si conosce un amministratore del dominio di invio, contattare li e richiedere che vengono impostati i record di autenticazione di posta elettronica in modo che non è necessario aggiungere le sostituzioni. Per ulteriori informazioni, vedere [gli amministratori dei domini che vengono non i clienti di Office 365](#administrators-of-domains-that-are-not-office-365-customers)"più avanti in questo articolo. 
  
Sebbene possa risultare difficile in innanzitutto ottenere l'invio di domini per l'autenticazione, nel tempo, come più filtri di posta elettronica avviare junking o il rifiuto anche loro posta elettronica, determinerà amministratori di configurare i record DNS appropriati per garantire il recapito migliore.
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>Visualizzazione di rapporti di quanti messaggi sono stati contrassegnati come spoofing

Dopo aver abilitato i criteri anti-spoofing, è possibile utilizzare Intelligence minaccia per i numeri di risolvere il numero di messaggi contrassegnato come per attività di phishing. A tale scopo, che influiscono sulla sicurezza &amp; centro conformità (SCC) in Threat Management \> Explorer, impostare la visualizzazione per attività di phishing e gruppo dal dominio mittente o della protezione:
  
![Visualizzare il numero di messaggi contrassegnato come per attività di phishing](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
Interagire con i diversi tipi di report per visualizzare il numero sono stato contrassegnato come phishing, inclusi i messaggi contrassegnati come SPOOFING. Per ulteriori informazioni, vedere [Introduzione a Business Intelligence di Office 365 rischio](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441).
  
Non è ancora possibile dividere fuori che i messaggi contrassegnati a causa di spoofing e altri tipi di phishing (anti-phishing generale, dominio o utente rappresentazione e così via). Tuttavia, più avanti in 2018, sarà possibile eseguire questa operazione tramite la sicurezza &amp; centro conformità. Dopo l'installazione, è possibile utilizzare questo report come punto di partenza per identificare i domini di invio che potrebbero essere legittimi vengono contrassegnati come spoofing a causa di errore di autenticazione.
  
Nella schermata seguente è una proposta di come i dati avrà un aspetto, ma possono cambiare quando rilasciato:
  
![La visualizzazione dei report di phishing dal tipo di rilevamento](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
Per non di strumenti di analisi e di clienti E5, questi rapporti saranno disponibili più avanti in 2018 in rapporti di rischio protezione stato indica, ma verranno posticipati di almeno 24 ore. In questa pagina verrà aggiornata come sono integrate in sicurezza &amp; centro conformità.
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>Prevedere il numero di messaggi verrà contrassegnato come spoofing

Più avanti in 2018, una volta Office 365 consente di aggiornare le impostazioni per consentono di disattivare l'applicazione della protezione anti-spoofing o su con l'applicazione di base o avanzata, si verrà assegnato al ruolo la possibilità di visualizzare in che modo cambieranno disposizione del messaggio in varie impostazioni. Vale a dire, se lo spoofing anti è disattivato, sarà in grado di visualizzare il numero di messaggi verrà rilevato come spoofing se si attiva a Basic. In alternativa, se si tratta di base, sarà possibile visualizzare il numero di messaggi più verrà rilevato come spoofing se si attiva su un valore elevato.
  
Questa funzionalità è attualmente in fase di sviluppo. Quando si definiscono ulteriori dettagli, in questa pagina verrà aggiornata con schermate del centro conformità e sicurezza e con esempi di PowerShell.
  
!["Se" report per l'abilitazione antispoofing](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![Esperienza possibile per consentire a un mittente spoofing](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>Informazioni sulle modalità di posta indesiderata, phishing e phishing avanzate vengono combinati i rilevamenti di

Le organizzazioni che utilizzano Exchange Online, con o senza degli strumenti di analisi, è possono specificare le azioni da eseguire quando il servizio consente di identificare i messaggi come malware, posta indesiderata, posta indesiderata confidenza elevata, phishing e blocco. Con i criteri di Anti-phishing ATP per i clienti degli strumenti di analisi, i criteri di Anti-phishing per i clienti EOP e il fatto che un messaggio potrebbe raggiunto più tipi di rilevamento (ad esempio malware, phishing e rappresentazione dell'utente), potrebbe essere alcuni confusione in merito agli che criterio verrà applicato. 
  
In generale, il criterio applicato a un messaggio viene identificato nell'intestazione X-Forefront-Antispam-Report nella proprietà CAT (categoria). 
  
|**Priorità**|**Criterio**|**Categoria**|**Dove gestite?**|**Si applica a**|
|:-----|:-----|:-----|:-----|:-----|
|1   <br/> |Malware  <br/> |MALW  <br/> |[Criteri antimalware](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|2   <br/> |Phishing  <br/> |PHSH  <br/> |[Criterio di filtro contenuto ospitato](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|3   <br/> |Alta probabilità di posta indesiderata  <br/> |HSPM  <br/> |[Criterio di filtro contenuto ospitato](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|4   <br/> |Lo spoofing  <br/> |SPOOFING  <br/> |[Criteri di anti-phishing](https://go.microsoft.com/fwlink/?linkid=864553), [Business intelligence di spoofing](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) <br/> |Tutte le organizzazioni  <br/> |
|5   <br/> |Posta indesiderata  <br/> |SPM  <br/> |[Criterio di filtro contenuto ospitato](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|6   <br/> |Blocco  <br/> |BLOCCO  <br/> |[Criterio di filtro contenuto ospitato](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|7   <br/> |Rappresentazione di dominio  <br/> |DIMP  <br/> |[Criteri di anti-phishing](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |Organizzazioni con degli strumenti di analisi solo  <br/> |
|8   <br/> |Rappresentazione dell'utente  <br/> |UIMP  <br/> |[Criteri di anti-phishing](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |Organizzazioni con degli strumenti di analisi solo <br/> |
   
Se si dispone di più criteri Anti-phishing diversi, verrà applicato quello la priorità più alta. Ad esempio, se che si dispone di due criteri:
  
|**Criterio**|**Priorità**|**Rappresentazione dell'utente o il dominio**|**Protezione anti-spoofing**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1   <br/> |On  <br/> |Off  <br/> |
|B  <br/> |2   <br/> |Off  <br/> |Attivato  <br/> |
   
Se è disponibile in un messaggio e viene identificato come rappresentazione di spoofing e utente e ambito è lo stesso insieme di utenti al criterio A e B criteri, quindi il messaggio viene considerato come un spoofing, ma non viene applicata alcuna azione dopo anti-spoofing è disattivato , e lo SPOOFING esegue una priorità superiore (4) di rappresentazione utente (8).
  
Per rendere altri tipi di phishing criterio applicato, sarà necessario modificare le impostazioni di utenti diversi criteri vengono applicati a.
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>Scenari legittimi per disabilitare lo spoofing anti

Lo spoofing anti meglio protezione degli utenti da attacchi di phishing e pertanto disattivazione protezione anti-spoofing è sconsigliata. Per disabilitarlo, è possibile risolvere alcuni falsi positivi a breve termine, ma verranno presentate rischi più a lungo termine. Il costo per la configurazione dell'autenticazione sul lato mittente o con modifiche nei criteri anti-phishing sono in genere occasionali eventi o richiedono operazioni di manutenzione solo minimo, periodica. Il costo per ripristinare da un attacco di phishing in cui sono stato esposto dati o delle risorse sono state compromesse è tuttavia molto superiore.
  
Per questo motivo, è consigliabile utilizzare tramite lo spoofing anti falsi positivi rispetto alla disattiva la protezione anti-spoofing.
  
Esiste tuttavia uno scenario legittimo dove lo spoofing anti deve essere disabilitato e che è quando sono disponibili ulteriori il filtro della posta prodotti Office 365 e il routing dei messaggi non è il primo hop nel percorso di posta elettronica:
  
![Il record MX cliente non si riferisce a Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
L'altro server può essere un server di posta locali di Exchange, un filtro di dispositivi, ad esempio Ironport, di posta o servizio ospitato dal cloud diversa.
  
Se il record MX del dominio del destinatario non si riferisce a Office 365, non è necessario disabilitare lo spoofing anti perché Office 365 ricerca record MX del dominio di destinazione e viene eliminato lo spoofing anti punta a un altro servizio. Se non si conosce se il dominio con un altro server in primo piano, è possibile utilizzare un sito Web come MX della casella degli strumenti di cercare il record MX. Potrebbe indicare qualcosa di simile alla seguente:
  
![Record MX indica dominio non si riferisce a Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
In questo dominio dispone di un record MX che non si riferisce a Office 365, in modo che non si applicano applicazione della protezione anti-spoofing Office 365.
  
Tuttavia, se il record MX del dominio del destinatario *è* sceglie Office 365, anche se non esiste un altro servizio davanti a Office 365, è possibile disattivare lo spoofing anti. L'esempio più comune è tramite l'utilizzo di un destinatario riscrittura degli indirizzi: 
  
![Diagramma del routing per la riscrittura degli indirizzi dei destinatari](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
Record MX del dominio contoso.com punta al server locale, mentre i record MX del .net @office365.contoso dominio fa riferimento a Office 365 perché contiene \*. protection.outlook.com, o \*. eo.outlook.com il record MX:
  
![Punti di record MX a Office 365, pertanto probabilmente destinatario riscrivere](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
Assicurarsi di differenziare i record MX del dominio del destinatario non si riferisce a Office 365 e quando è stato sottoposto a un destinatario riscrittura degli indirizzi. È importante stabilire la differenza tra questi due casi.
  
Se si è certi se il dominio di destinazione ha subito un destinatario riscrittura degli indirizzi, in alcuni casi è possibile sapere esaminando le intestazioni del messaggio.
  
a) per prima cosa, esaminare le intestazioni del messaggio per il dominio del destinatario nell'intestazione dei risultati di autenticazione: 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

Il dominio del destinatario si trova nel testo in grassetto rosso in precedenza, in questo caso office365.contoso.net. Può essere diverso che il destinatario nel campo a: intestazione:
  
A: Esempio destinatario \<destinatario @ contoso.com\>
  
Eseguire una ricerca di record MX del dominio del destinatario effettivo. Se contiene \*. protection.outlook.com, mail.messaging.microsoft.com, \*. eo.outlook.com o frontbridge.com, significa che la MX punta a Office 365.
  
Se non contiene tali valori, ciò significa che la MX non punta a Office 365. Uno strumento che è possibile utilizzare per verificare questa impostazione è MX della casella degli strumenti.
  
In questo esempio specifico seguenti che informa che tale contoso.com, il dominio simile al destinatario poiché era a: intestazione, ha record record MX punta a un server in % di beni:
  
![Record MX punta al server % nel beni](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
Tuttavia, il destinatario effettivo è office365.contoso.net cui il record MX punta a Office 365:
  
![MX punta a Office 365, è necessario riscrittura degli indirizzi dei destinatari](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
Pertanto, questo messaggio di stato sottoposto probabile che un destinatario riscrittura degli indirizzi.
  
b) in secondo luogo, assicurarsi di distinguere tra casi di utilizzo comuni di riscrittura del destinatario. Se si intende riscrivere il dominio del destinatario per \*. onmicrosoft.com, in realtà riscrivere venga \*. mail.onmicrosoft.com.
  
Dopo aver identificato il dominio del destinatario finale instradata controllati da un altro server e record MX del dominio del destinatario effettivamente punta a Office 365 (come pubblicato in propri record DNS), è possibile procedere con per disabilitare lo spoofing anti.
  
Si tenga presente che non si desidera disabilitare lo spoofing anti se hop prima del dominio nel percorso di routing è Office 365, solo quando è controllato da uno o più servizi.
  
### <a name="how-to-disable-anti-spoofing"></a>Come disabilitare lo spoofing anti

Se si dispone già di un criterio di protezione Anti-phishing creato, impostare il parametro EnableAntispoofEnforcement su $false: 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

Se non si conosce il nome del criterio (o i criteri) per disattivare, è possibile visualizzare tali: 
  
```
Get-AntiphishPolicy | fl Name
```

Se non si dispone di tutti i criteri anti-phishing esistenti, è possibile creare uno e quindi disattivarlo (anche se non si dispone di un criterio, lo spoofing anti è ancora applicato, più avanti in 2018, verrà creato automaticamente un criterio predefinito e che può quindi disabilitare anziché creare una) . È necessario eseguire questa operazione nei passaggi più: 
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the antiphishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false 

```

Disattivazione di anti-spoofing è disponibile solo tramite cmdlet (più avanti in T2 2018 sarà disponibile in sicurezza &amp; centro conformità). Se non si ha accesso a PowerShell, creare un ticket di supporto.
  
Si tenga presente che deve essere applicata solo ai domini che subiscono indiretti routing quando inviati a Office 365. La parte relativa a disabilitare lo spoofing anti a causa di alcuni falsi positivi, sarà maggiore del tempo per il funzionamento attraverso tali.
  
### <a name="information-for-individual-users"></a>Informazioni per i singoli utenti

Modalità di interazione con la punta di protezione anti-spoofing limitati singoli utenti. Tuttavia, sono disponibili diverse operazioni da eseguire per risolvere gli scenari comuni.
  
### <a name="common-scenario-1---mailbox-forwarding"></a>Scenario comune #1 - inoltro delle cassette postali

Se si utilizza un altro servizio di posta elettronica e inoltra la posta elettronica a Office 365 o Outlook.com, la posta elettronica può essere contrassegnata come lo spoofing e ricevere un suggerimento sicurezza rosso. Office 365 e Outlook.com pianificare risolvere questo problema automaticamente quando il server di inoltro è uno dei Outlook.com, Office 365, Gmail o qualsiasi altro servizio che utilizza il [protocollo dell'arco](https://arc-spec.org). Tuttavia, fino a quando non viene distribuita tale correzione, gli utenti devono utilizzare la funzionalità di account connessi per importare i messaggi direttamente, anziché utilizzare l'opzione di inoltro.
  
Per configurare account connessi in Office 365, selezionare l'icona ingranaggio in alto a destra dell'interfaccia web di Office 365 \> posta \> posta \> account \> account connessi.
  
![Opzione account Office 365 - connessi](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
In Outlook.com, il processo è sull'icona dell'ingranaggio \> opzioni \> posta \> account \> account connessi.
  
### <a name="common-scenario-2---discussion-lists"></a>Gli elenchi di discussioni scenario comune #2:

Gli elenchi di discussioni sono noti per problemi di anti-spoofing dipende dal modo in cui inoltrare il messaggio e modificarne il contenuto sono ancora stati mantenere l'originale dal: indirizzo.
  
Si supponga, ad esempio, l'indirizzo di posta elettronica utente @ contoso.com, ed è di osservazione uccelli e partecipare il birdwatchers elenco discussione @ example.com. Quando si invia un messaggio all'elenco di discussione, è possibile inviare in questo modo:
  
**Da:** Luca Dellamore \<utente @ contoso.com\> 
  
**A:** Elenco di discussione di birdwatcher \<birdwatchers @ example.com\> 
  
**Soggetto:** Visualizzazione grande di jays blu nella parte superiore di MT. Rainier questa settimana 
  
Tutti gli utenti desidera estrarre la visualizzazione questa settimana da MT. Rainier?
  
Quando l'elenco di posta elettronica riceve il messaggio, si formattare il messaggio, modificarne il contenuto e riesecuzione per il resto dei membri nell'elenco di discussione che è costituita da partecipanti da molti ricevitori di posta elettronica diverso.
  
**Da:** Luca Dellamore \<utente @ contoso.com\> 
  
**A:** Elenco di discussione di birdwatcher \<birdwatchers @ example.com\> 
  
**Soggetto:** [BIRDWATCHERS] Visualizzazione grande di jays blu nella parte superiore di MT. Rainier questa settimana 
  
Tutti gli utenti desidera estrarre la visualizzazione questa settimana da MT. Rainier?
  
---
  
Questo messaggio è stato inviato all'elenco di discussione Birdwatchers. È possibile annullare la sottoscrizione in qualsiasi momento.
  
In precedenza, il messaggio rieseguito ha lo stesso da: indirizzo (utente @ contoso.com), ma il messaggio originale è stato modificato aggiungendo un tag alla riga dell'oggetto e il piè di pagina nella parte inferiore del messaggio. Questo tipo di modifica del messaggio comune in liste di distribuzione e potrebbe dar falsi positivi.
  
Se un utente all'interno dell'organizzazione sia un amministratore della lista di distribuzione, sarà possibile configurarlo per superare lo spoofing anti controlli.
  
- Controllare le domande frequenti relative al DMARC.org: [è possibile utilizzare una lista di distribuzione e desidera interoperare con DMARC, è possibile procedere?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)
    
- Leggere le istruzioni riportate in questo post di blog: [un suggerimento per gli operatori lista di distribuzione per l'interoperabilità con DMARC per evitare errori](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)
    
- È consigliabile installare gli aggiornamenti sul server lista di distribuzione per il supporto dell'arco, vedere[https://arc-spec.org](https://arc-spec.org/)
    
Se non si dispone delle proprietà della lista di distribuzione:
  
- È possibile richiedere il gestore della lista di distribuzione per implementare una delle opzioni indicate sopra (devono disporre anche di impostare per il dominio che all'elenco di indirizzi è l'inoltro dall'autenticazione di posta elettronica)
    
- È possibile creare regole delle cassette postali nei client di posta elettronica per spostare messaggi di posta in arrivo. È possibile richiedere agli amministratori dell'organizzazione per impostare le regole di autorizzazione o sostituzioni come descritto nella sezione gestione dei mittenti legittimi l'invio di posta elettronica non autenticato
    
- È possibile creare un ticket di supporto con Office 365 per creare una sostituzione per la lista di considerarlo legittimi
    
### <a name="other-scenarios"></a>Altri scenari

1. Se nessuno degli scenari comuni precedenti è il caso, segnalare il messaggio come falso positivo a Microsoft. Per ulteriori informazioni, vedere la sezione [come posso segnalare i messaggi di posta indesiderata o posta non indesiderata torna a Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) più avanti in questo articolo. 
    
2. È anche possibile rivolgersi all'amministratore di posta elettronica che può generare come un ticket del supporto Microsoft. Il team di progettazione Microsoft esaminerà perché il messaggio è stato contrassegnato come un spoofing.
    
3. Inoltre, se si esegue il mittente è e ha la certezza che non sono intenzionalmente spoofing, potrebbe rispondere al mittente che indica che si inviano i messaggi da un server di posta elettronica che non esegue l'autenticazione. In alcuni casi di conseguenza, contattare il proprio amministratore IT che configurerà i record di autenticazione necessari posta elettronica del mittente originale.
  
Quando sufficiente mittenti rispondano ai proprietari dei domini devono configurare record di autenticazione di posta elettronica, li spurs in esecuzione di azioni. Mentre Microsoft può essere utilizzato anche con i proprietari dei domini per pubblicare i record necessari, è utile ancora più quando gli utenti singoli richiedono.
    
4. Facoltativamente, aggiungere il mittente all'elenco Mittenti attendibili. Tuttavia, tenere presente che se un specificati esegue lo spoofing tale account, si verrà consegnato alla cassetta postale. Pertanto, questa opzione deve essere utilizzata solo in casi particolari.
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Come necessario preparare i mittenti a Microsoft per la protezione anti-spoofing

Se non è un amministratore che attualmente invia messaggi a Microsoft, Office 365 o Outlook.com, è necessario assicurarsi che la posta elettronica viene autenticata correttamente in caso contrario può essere contrassegnato come posta indesiderata o per attività di phishing. 
  
### <a name="customers-of-office-365"></a>Clienti di Office 365

In caso di un cliente di Office 365 e si utilizza Office 365 per inviare la posta elettronica in uscita:
  
- Per i domini, [configurare SPF in Office 365 per evitare attacchi di spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
    
- Per i domini principali, [Utilizzare la per convalidare la posta elettronica inviata dal dominio personalizzato in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
    
- [È consigliabile configurare record DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) per il dominio per determinare chi sono i mittenti legittimi 
    
Microsoft non fornisce linee guida per informazioni dettagliate per ogni SPF, DKIM e DMARC. Tuttavia, non esiste una quantità elevata di informazioni pubblicate in linea. Esistono inoltre 3rd società di terze parti dedicato a che consente all'organizzazione di impostare i record di autenticazione di posta elettronica.
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Amministratori dei domini che non sono clienti di Office 365

Se l'utente è un amministratore di dominio ma non è un cliente di Office 365:
  
- È consigliabile impostare SPF per pubblicare gli indirizzi IP di invio del dominio e inoltre impostare DKIM (se disponibile) per firmare digitalmente i messaggi. È consigliabile inoltre la configurazione di record DMARC.
    
- Se si dispone di mittenti in blocco la trasmissione di posta elettronica per conto dell'utente, dovrebbe funzionare con cui inviare la posta elettronica in modo tale che il dominio di invio nella From: indirizzi (se appartiene a un utente) viene allineato con il dominio che passa SPF o DMARC.
    
- Se si dispone in locale server di posta o inviare da un provider di Software come servizio o da un servizio di hosting cloud come Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services o allo stesso modo, è necessario verificare che vengono aggiunti a un record SPF.
    
- Se si è un dominio di piccole dimensioni ospitato da un provider di servizi Internet, è necessario impostare il record SPF in base alle istruzioni che viene fornito dal provider di servizi Internet. La maggior parte dei provider di servizi Internet forniscono questi tipi di istruzioni e sono disponibili nelle pagine di supporto della società.
    
- Anche se non sono di posta elettronica authentication record prima di pubblicare e funzionamento correttamente, è comunque necessario pubblicare record di autenticazione di posta elettronica da inviare a Microsoft. In questo modo, si sono nella lotta dal phishing e ridurre la possibilità che si o organizzazioni che si invia a, consentirà di ottenere phished.
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>Che cosa accade se non si conosce che invia messaggio di posta elettronica come dominio?

Molti domini non si pubblicano i record SPF perché non si conosce presenti tutti i mittenti. Questa impostazione è corretta, è necessario sapere chi tutte siano. In realtà, deve iniziare la pubblicazione di un record SPF per quelle che si conoscono, in particolare il traffico aziendale in cui si trova e pubblicare un criterio SPF neutro,? tutti:
  
example.com TXT IN "v = spf1 include:spf.example.com? tutti"
  
Il neutro SPF questo significa che qualsiasi messaggio di posta elettronica provenienti dall'infrastruttura aziendale passa l'autenticazione di posta elettronica affatto altri destinatari di posta elettronica. Messaggio di posta elettronica provenienti da mittenti su che non si conosce esegue il fallback al neutral, che è simile al non pubblicazione Nessun record SPF affatto.
  
Quando si invia a Office 365, posta elettronica provenienti dal traffico aziendale viene considerato come utenti autenticati, ma il messaggio di posta elettronica provenienti da origini su che non si conosce ancora può essere contrassegnata come spoofing (a seconda se Office 365 in modo implicito possibile autenticare viene). Tuttavia, si è ancora un miglioramento di tutta la posta elettronica vengono contrassegnato come spoofing da Office 365.
  
Dopo aver ricevuto avviato con un record SPF con un criterio di fallback di? tutti, è possibile includere gradualmente più invio dell'infrastruttura e quindi pubblicare un criterio più. 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>Se si è il proprietario della lista di distribuzione?

Vedere la sezione [scenario comune 2 - discussione sono elencati](#common-scenario-2---discussion-lists). 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>Se si è un provider dell'infrastruttura, ad esempio un Provider di servizi Internet (ISP), Provider di servizio di posta elettronica (ESP) o che ospita servizio cloud?

Se si esegue l'hosting posta elettronica del dominio e Invia messaggio di posta elettronica o fornire l'infrastruttura di hosting che può inviare posta elettronica, è consigliabile eseguire le operazioni seguenti:
  
- Verificare che i clienti dispongono della documentazione che descrive gli elementi da pubblicare i record SPF
    
- Prendere in considerazione per la firma DKIM firme nella posta elettronica in uscita anche se il cliente non viene impostato in modo esplicito backup (accesso con un dominio predefinito). È possibile anche double sign-messaggio di posta elettronica con le firme DKIM (una sola volta con dominio del cliente se è stata configurata e una seconda volta con firma DKIM aziendale)
    
Distribuzione di Microsoft non è garantita anche se si esegue l'autenticazione che hanno origine dalla piattaforma di posta elettronica, ma almeno assicura che Microsoft non indesiderato la posta elettronica perché non è autenticato. Per ulteriori dettagli sulla come Outlook.com filtri posta elettronica, vedere la [pagina Outlook.com Postmaster](https://postmaster.live.com/pm/postmaster.aspx).
  
Per ulteriori informazioni sulle procedure consigliate per i provider di servizi, vedere [M3AAWG Mobile messaggistica procedure consigliate per provider di servizi](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
  
## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="why-is-microsoft-making-this-change"></a>Perché è Microsoft questa modifica?

Causa di attacchi l'impatto di phishing e perché l'autenticazione di posta elettronica è stato attorno per oltre 15 anni, Microsoft ritiene che il rischio di continua a Consenti posta non autenticato sia superiore a rischio di perdita di posta elettronica legittimi.
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>Questa modifica determinerà posta elettronica legittimi deve essere contrassegnato come posta indesiderata?

Inizialmente, ci sarà alcuni messaggi contrassegnati come posta indesiderata. Tuttavia, nel tempo, modificheranno i mittenti e quindi la quantità di messaggi erroneamente contrassegnati come spoofing sarà trascurabile per la maggior parte dei percorsi di posta elettronica.
  
Microsoft ha adottato prima questa caratteristica diverse settimane prima della distribuzione per il resto dei propri clienti. Mentre si è verificato interruzione inizialmente, rifiutata gradualmente.
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>Microsoft avrà un questa caratteristica per i clienti Outlook.com e non avanzate rischio di protezione di Office 365?

Protezione anti-spoofing tecnologia Microsoft è stata inizialmente distribuita per le organizzazioni che hanno una sottoscrizione a Office 365 Enterprise E5 o hanno acquistato il componente aggiuntivo di Office 365 avanzate Threat Protection (degli strumenti di analisi) per la sottoscrizione. A partire da ottobre, 2018 è stata estesa la protezione per le organizzazioni che hanno anche Exchange Online Protection (EOP). In futuro, si può rilasciare per Outlook.com. Tuttavia, in questo caso, potrebbero esserci alcune funzionalità che non vengono applicate ad esempio i report e ha la precedenza personalizzato.
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Come posso segnalare i messaggi di posta indesiderata o posta non indesiderata torna a Microsoft?

È possibile utilizzare il [componente aggiuntivo di report per Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), o se non è installato, [Invia la posta indesiderata, posta non indesiderata e i messaggi di phishing phishing a Microsoft per l'analisi](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>Perché un amministratore di dominio che non sa presenti tutti i mittenti!

Vedere [gli amministratori dei domini che vengono non i clienti di Office 365](#administrators-of-domains-that-are-not-office-365-customers).
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>Cosa succede se disattiva la protezione anti-spoofing per l'organizzazione, anche se Office 365 è il filtro principale?

Non è consigliabile ciò perché è verrà reso disponibile per i messaggi di posta indesiderata e phishing più senza risposta. Spoofing di phishing non tutte le e verrà perse effettua lo spoofing non tutti. Tuttavia, i rischi è maggiore di un cliente che consente lo spoofing anti.
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Abilitazione della protezione anti-spoofing significa che saranno protetti dal phishing tutti?

Purtroppo no, perché verranno adattarsi per utilizzare altre tecniche, ad esempio autori danneggiata account o la configurazione di account dei servizi libero. Tuttavia, protezione anti-phishing funzioni molto meglio per rilevare questi altri tipi di metodi di phishing perché la protezione di Office 365 sono livelli progettate lavoro contemporaneamente e si basano su tra loro.
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>Altri ricevitori di posta elettronica di grandi dimensioni non bloccano non autenticati di posta elettronica?

Quasi tutti i ricevitori di posta elettronica di grandi dimensioni implementano tradizionale SPF DKIM e DMARC. Alcuni ricevitori di dispongono di altri controlli che sono più restrittivi rispetto solo gli standard, ma pochi passare come non autenticati di Office 365 per bloccare di posta elettronica e gestirle come un spoofing. Tuttavia, la maggior parte del settore sta diventando più rigida relative al tipo specifico di posta elettronica, soprattutto a causa del problema di phishing.
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>È comunque necessario l'opzione Advanced Spam Filtering abilitato per "SPF rigido Fail" se abilitare lo spoofing anti?

No, questa opzione non è più necessaria perché la caratteristica anti-spoofing considera non solo errore rigido SPF, ma una più ampia gamma di criteri. Se si dispone di spoofing anti abilitato e l'opzione esito negativo rigido SPF abilitata, è probabilmente verranno visualizzati più falsi positivi. È consigliabile disabilitare questa funzionalità, così come verrebbero non fornire quasi alcun catch aggiuntive per la posta indesiderata o per attività di phishing e invece generare principalmente falsi positivi.
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>il mittente riscrittura combinazione (SRS) consente di risolvere posta elettronica inoltrati?

SRS solo parzialmente consente di risolvere il problema di posta elettronica inoltrati. Per riscrivere il SMTP MAIL FROM, SRS può verificare che i passaggi di messaggi inoltrati SPF nella destinazione successivo. Tuttavia, poiché anti-spoofing si basa su From: indirizzo in combinazione con il MAIL FROM o la firma DKIM dominio (o altri segnali), non è sufficiente impedire che venga contrassegnato come in caso di spoofing posta elettronica inoltrati.
  

