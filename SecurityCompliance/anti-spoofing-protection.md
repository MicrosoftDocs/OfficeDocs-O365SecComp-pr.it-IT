---
title: "protezione anti-spoofing in Office 365" ms. Author: Krowley Author: kccross Manager: laurawi ms. Date: 12/06/2018 ms. audience: ITPro ms. Topic: article ms. Service: O365-seccomp localization_priority: Normal search. appverid:
- MET150 ms. AssetID: d24bb387-C65D-486E-93E7-06a4f1a436c0 ms. Collection:
    - M365-Security-Compliance Description: "in questo articolo viene descritto come Office 365 attenua gli attacchi di phishing che utilizzano domini di mittenti contraffatti, ovvero domini contraffatti. Questo risultato analizza i messaggi e blocca quelli che possono essere autenticati neithe utilizzando metodi di autenticazione della posta elettronica standard, né altre tecniche di reputazione mittente. Questa modifica viene implementata in modo da ridurre il numero di attacchi di phishing in cui sono esposte le organizzazioni di Office 365. "
---

# <a name="anti-spoofing-protection-in-office-365"></a>Protezione anti-spoofing in Office 365

In questo articolo viene descritto il modo in cui Office 365 attenua gli attacchi di phishing che utilizzano domini di mittenti contraffatti, ovvero domini contraffatti. Questo risultato analizza i messaggi e blocca quelli che non possono essere autenticati con i metodi di autenticazione della posta elettronica standard, né altre tecniche di reputazione mittente. Questa modifica viene implementata in modo da ridurre il numero di attacchi di phishing ai quali sono esposti i clienti.
  
In questo articolo viene descritto anche il motivo per cui è stata apportata la modifica, il modo in cui i clienti possono prepararsi per questa modifica, la modalità di visualizzazione dei messaggi che saranno coinvolti, la modalità di relazione sui messaggi, la modalità di attenuazione dei falsi positivi e il modo in cui i mittenti di Microsoft dovrebbero prepararsi per questo modificare.
  
La tecnologia antispoofing di Microsoft è stata inizialmente distribuita alle organizzazioni che avevano un abbonamento a Office 365 Enterprise E5 o avevano acquistato il componente aggiuntivo di Office 365 Advanced Threat Protection (ATP) per la sottoscrizione. A ottobre 2018 è stata estesa la protezione alle organizzazioni che dispongono anche di Exchange Online Protection (EOP). Inoltre, a causa del modo in cui tutti i filtri imparano l'uno dall'altro, possono essere coinvolti anche gli utenti di Outlook.com.
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Modalità di utilizzo dello spoofing negli attacchi di phishing

Quando si tratta di proteggere i propri utenti, Microsoft assume sul serio la minaccia del phishing. Una delle tecniche di uso frequente degli spammer e phisher è la falsificazione, ovvero quando il mittente viene falsificato e viene visualizzato un messaggio che proviene da un utente o da una posizione diversa dall'origine effettiva. Questa tecnica è spesso utilizzata nelle campagne di phishing progettate per ottenere le credenziali utente. La tecnologia anti-spoofing di Microsoft esamina in modo specifico la falsificazione del ' da: header ' che è quella visualizzata in un client di posta elettronica come Outlook. Quando Microsoft ha elevata fiducia che l'intestazione From: è contraffatta, identifica il messaggio come spoofing.
  
Lo spoofing dei messaggi ha due implicazioni negative per gli utenti della vita reale:
  
### <a name="1-spoofed-messages-deceive-users"></a>1. i messaggi falsificati ingannano gli utenti
  
In primo luogo, un messaggio contraffatto potrebbe ingannare un utente facendo clic su un collegamento e rinunciando alle proprie credenziali, scaricando malware o rispondendo a un messaggio con contenuti sensibili (il secondo dei quali è noto come compromesso per la posta elettronica aziendale). Ad esempio, di seguito è riportato un messaggio di phishing con un mittente contraffatto di msoutlook94@service.outlook.com:
  
![Messaggio di phishing che rappresenta service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
Le precedenti non sono state effettivamente provenute da service.outlook.com, ma sono state falsificate dall'truffatore per farla sembrare così. Si sta tentando di ingannare un utente facendo clic sul collegamento all'interno del messaggio.
  
L'esempio seguente è spoofing contoso.com:
  
![Messaggio di phishing-compromesso di posta elettronica aziendale](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
Il messaggio sembra legittimo, ma in realtà è una parodia. Questo messaggio di phishing è un tipo di compromesso di posta elettronica aziendale che è una sottocategoria di phishing.
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. gli utenti confondono i messaggi reali per quelli falsi
  
In secondo luogo, i messaggi falsificati creano incertezza per gli utenti che conoscono i messaggi di phishing, ma non sono in grado di distinguere tra un messaggio reale e uno contraffatto. Ad esempio, di seguito è riportato un esempio di reimpostazione della password effettiva dall'indirizzo di posta elettronica dell'account di sicurezza Microsoft:
  
![Reimpostazione della password legittima di Microsoft](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
Il messaggio di cui sopra è venuto da Microsoft, ma allo stesso tempo, gli utenti vengono utilizzati per ottenere messaggi di phishing che possono ingannare un utente nel fare clic su un collegamento e rinunciare alle proprie credenziali, scaricare malware o rispondere a un messaggio con contenuti sensibili. Poiché è difficile distinguere tra la reimpostazione di una password reale e quella fasulla, molti utenti ignorano questi messaggi, li segnalano come posta indesiderata o inutilmente riferiscono i messaggi a Microsoft come tentativi di phishing non consentiti.
    
Per interrompere lo spoofing, l'industria del filtro della posta elettronica ha sviluppato protocolli di autenticazione della posta elettronica quali [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)e [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). DMARC impedisce lo spoofing che esamina il mittente di un messaggio-quello che l'utente vede nel proprio client di posta elettronica (negli esempi precedenti, si tratta di service.outlook.com, outlook.com e accountprotection.microsoft.com)-con il dominio che ha superato SPF o DKIM. Ovvero, il dominio visualizzato dall'utente è stato autenticato e pertanto non è falsificato. Per una discussione più completa, vedere la sezione "*capire perché l'autenticazione della posta elettronica non è sempre sufficiente per arrestare lo spoofing"* più avanti in questo documento. 
  
Tuttavia, il problema è che i record di autenticazione della posta elettronica sono facoltativi, non necessari. Di conseguenza, mentre i domini con criteri di autenticazione forti come microsoft.com e skype.com sono protetti dallo spoofing, i domini che pubblicano criteri di autenticazione più deboli o nessun criterio sono obiettivi per essere falsificati. Al 2018 marzo, solo il 9% dei domini delle aziende della Fortune 500 pubblica criteri di autenticazione di posta elettronica forti. Il restante 91% può essere falsificato da un truffatore e, a meno che il filtro della posta elettronica non lo rilevi utilizzando un altro criterio, può essere recapitato a un utente finale e ingannarlo:
  
![DMARC Policies de Fortune 500 companies](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
La percentuale di aziende di piccole e medie dimensioni che non rientrano nella fortuna 500 che pubblicano criteri di autenticazione di posta elettronica forti è più piccola e ancora più piccola per i domini esterni al Nord America e all'Europa occidentale.
  
Si tratta di un problema importante perché, mentre le aziende potrebbero non essere a conoscenza di come funziona l'autenticazione della posta elettronica, phisher capisce e approfitta della sua mancanza.
  
Per informazioni sulla configurazione di SPF, DKIM e DMARC, vedere la sezione "*Customers of Office 365"* più avanti in questo documento. 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>Interruzione dello spoofing con l'autenticazione implicita della posta elettronica

Dal momento che il phishing e la posta indesiderata sono un problema e, a causa dell'adozione limitata di criteri di autenticazione di tipo e-mail, Microsoft continua a investire in funzionalità per la protezione dei clienti. Di conseguenza, Microsoft procede con *l'autenticazione implicita della posta elettronica* : se un dominio non esegue l'autenticazione, Microsoft lo tratterà come se avesse pubblicato i record di autenticazione della posta elettronica e lo trattasse di conseguenza se non passa. 
  
Per ottenere questo risultato, Microsoft ha creato numerose estensioni alla regolare autenticazione della posta elettronica, tra cui la reputazione mittente, la cronologia mittente/destinatario, l'analisi comportamentale e altre tecniche avanzate. Un messaggio inviato da un dominio che non pubblica l'autenticazione della posta elettronica verrà contrassegnato come spoof, a meno che non contenga altri segnali per indicare che è legittimo.
  
In questo modo, gli utenti finali possono avere la certezza che un messaggio di posta elettronica inviato a loro non sia stato falsificato, i mittenti possono essere certi che nessuno impersona il proprio dominio e i clienti di Office 365 possono offrire una protezione ancora migliore, ad esempio la protezione della rappresentazione.
  
Per visualizzare l'annuncio generale di Microsoft, vedere [un mare di phishing parte 2-Enhanced anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>Identificare che un messaggio è classificato come falsificato

### <a name="composite-authentication"></a>Autenticazione composita

Anche se SPF, DKIM e DMARC sono tutti utili da soli, non comunicano sufficiente stato di autenticazione nel caso in cui un messaggio non disponga di record di autenticazione espliciti. Di conseguenza, Microsoft ha sviluppato un algoritmo che combina più segnali in un singolo valore denominato autenticazione composita o compauth in breve. I clienti di Office 365 dispongono di valori compauth contrassegnati nell'intestazione *Authentication-results* nelle intestazioni del messaggio. 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**Risultato CompAuth**|**Descrizione**|
|:-----|:-----|
|esito negativo|Messaggio non è stato eseguito l'autenticazione esplicita (invio esplicito dei record del dominio in DNS) o l'autenticazione implicita (il dominio di invio non ha pubblicato i record in DNS, quindi Office 365 ha interpolato il risultato come se avesse pubblicato i record).|
|passare|Il messaggio ha superato l'autenticazione esplicita (messaggio passato DMARC, o [migliore ipotesi passata DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) o l'autenticazione implicita con elevata sicurezza (il dominio di invio non pubblica i record di autenticazione della posta elettronica, ma Office 365 ha segnali di back-end forti per indicare che il messaggio è probabilmente legittimo).|
|softpass|Il messaggio ha superato l'autenticazione implicita con una confidenza bassa e media (il dominio di invio non pubblica l'autenticazione della posta elettronica, ma Office 365 ha segnali back-end per indicare che il messaggio è legittimo, ma la forza del segnale è più debole).|
|nessuno|Il messaggio non ha eseguito l'autenticazione (o ha eseguito l'autenticazione ma non è stato allineato), ma l'autenticazione composita non è stata applicata a causa della reputazione mittente o di altri fattori.|
   
|||
|:-----|:-----|
|**Motivo**|**Descrizione**|
|0XX|Messaggio l'autenticazione composita non riuscita.<br/>**000** indica che il messaggio ha avuto esito negativo DMARC con un'azione di rifiuto o quarantena.  <br/>**001** indica che il messaggio non ha eseguito l'autenticazione implicita della posta elettronica. Questo significa che il dominio di invio non ha pubblicato i record di autenticazione della posta elettronica o, in caso contrario, ha un criterio di errore più debole (non riuscito o neutro, criteri di DMARC di un criterio di p = None).<br/>**002** indica che l'organizzazione dispone di un criterio per la coppia mittente/dominio esplicitamente vietato dall'invio di messaggi di posta elettronica falsificati, questa impostazione viene impostata manualmente da un amministratore.  <br/>**010** indica che il messaggio ha avuto esito negativo DMARC con un'azione di rifiuto o quarantena e che il dominio di invio è uno dei domini accettati dell'organizzazione (questa è la parte del self-to-self o dell'intra-org, spoofing).  <br/>**011** indica che il messaggio non ha eseguito l'autenticazione implicita della posta elettronica e che il dominio di invio è uno dei domini accettati dell'organizzazione, ovvero parte di un self-to-self, o di un sistema di spoofing interno (org).|
|Tutti gli altri codici (1xx, 2xx, 3xx, 4xx, 5xx)|Corrisponde a vari codici interni per i motivi per cui un messaggio ha superato l'autenticazione implicita o non ha avuto l'autenticazione ma non è stata applicata alcuna azione.|
   
Esaminando le intestazioni di un messaggio, un amministratore o persino un utente finale può determinare in che modo Office 365 arriva alla conclusione che il mittente potrebbe essere contraffatto.
  
### <a name="differentiating-between-different-types-of-spoofing"></a>Differenziazione tra diversi tipi di spoofing

Microsoft distingue due tipi diversi di messaggi di spoofing:
  
 **Spoofing intra-org**
  
Conosciuto anche come spoofing self-to-self, questo si verifica quando il dominio nell'indirizzo from: è lo stesso del dominio destinatario (quando il dominio del destinatario è uno dei [domini accettati](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)dell'organizzazione). in alternativa, quando il dominio nell'indirizzo da: fa parte della stessa organizzazione.
  
Ad esempio, il mittente e il destinatario seguenti sono presenti nello stesso dominio (contoso.com). Gli spazi vengono inseriti nell'indirizzo di posta elettronica per impedire la raccolta di spambot in questa pagina):
  
From: sender @ contoso.com
  
A: Recipient @ contoso.com
  
Di seguito sono riportati i domini del mittente e del destinatario che si allineano al dominio dell'organizzazione (fabrikam.com):
  
From: sender @ foo.fabrikam.com
  
A: Recipient @ bar.fabrikam.com
  
I domini del mittente e del destinatario seguenti sono diversi (microsoft.com e bing.com), ma appartengono alla stessa organizzazione (entrambi fanno parte dei domini accettati dell'organizzazione):
  
From: sender @ microsoft.com
  
A: Recipient @ bing.com
  
I messaggi che non riescono a eseguire lo spoofing intra-org contengono i valori seguenti nelle intestazioni:
  
X-Forefront-antispam-report:... CAT: SPM/HSPM/PHSH;... SFTY: 9.11
  
Il gatto è la categoria del messaggio ed è normalmente contrassegnato come SPM (posta indesiderata), ma occasionalmente può essere HSPM (protezione da posta indesiderata elevata) o phishing (phishing) a seconda di quali altri tipi di modelli si verificano nel messaggio.
  
SFTY è il livello di sicurezza del messaggio, la prima cifra (9) indica che il messaggio è phishing e il secondo set di cifre dopo il punto (11) indica che si tratta di una spoofing tra organizzazioni.
  
Non esiste un codice motivo specifico per l'autenticazione composita per lo spoofing tra organizzazioni, che verrà stampato in un secondo momento in 2018 (Timeline non ancora definito).
  
 **Spoofing tra domini**
  
Questo problema si verifica quando il dominio di invio nell'indirizzo da: è un dominio esterno all'organizzazione di ricezione. I messaggi che non riescono ad eseguire l'autenticazione composita a causa dello spoofing tra domini contengono i seguenti valori nelle intestazioni:
  
Autenticazione-risultati:... compauth = Fail Reason = 000/001
  
X-Forefront-antispam-report:... CAT: SPOOFING;... SFTY: 9.22
  
In entrambi i casi, il seguente suggerimento per la sicurezza rossa viene contrassegnato nel messaggio oppure un equivalente personalizzato per la lingua della cassetta postale del destinatario:
  
![Punta di sicurezza rossa-rilevamento frodi](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
È solo guardando l'indirizzo da: e sapendo che cosa è la posta elettronica del destinatario, o ispezionando le intestazioni di posta elettronica, che è possibile distinguere tra lo spoofing tra organizzazioni intra-org e Cross-Domain.
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>In che modo i clienti di Office 365 possono prepararsi per la nuova protezione anti-spoofing

### <a name="information-for-administrators"></a>Informazioni per gli amministratori

In qualità di amministratore di un'organizzazione di Office 365, è necessario tenere presenti diverse informazioni importanti.
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Informazioni sul motivo per cui l'autenticazione della posta elettronica non è sempre sufficiente per arrestare lo spoofing

La nuova protezione anti-spoofing si basa sull'autenticazione della posta elettronica (SPF, DKIM e DMARC) per non contrassegnare un messaggio come spoofing. Un esempio comune è il momento in cui un dominio di invio non ha mai pubblicato i record SPF. Se non sono presenti record SPF o non sono stati configurati correttamente, un messaggio inviato verrà contrassegnato come falsificato, a meno che Microsoft non disponga di informazioni di back-end che dicono che il messaggio è legittimo.
  
Ad esempio, prima di eseguire la distribuzione di anti-spoofing, un messaggio potrebbe essere simile al seguente senza record SPF, nessun record di DKIM e nessun record di DMARC: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
Dopo aver eseguito l'anti-spoofing, se si dispone di Office 365 Enterprise E5, EOP o ATP, il valore compauth viene contrassegnato come indicato di seguito:
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

Se example.com ha risolto questo valore impostando un record SPF ma non un record DKIM, l'autenticazione composita verrebbe passata perché il dominio che ha superato SPF è stato allineato al dominio nell'indirizzo from: 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

In alternativa, se si configura un record di DKIM ma non un record SPF, l'autenticazione composita verrà passata anche perché il dominio nella firma di DKIM che è stato passato allineato al dominio nell'indirizzo from:: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

Tuttavia, un truffatore può anche configurare SPF e DKIM e firmare il messaggio con il proprio dominio, ma specificare un dominio diverso nell'indirizzo from:. Né SPF né DKIM richiede che il dominio sia allineato al dominio nell'indirizzo from:, quindi, a meno che example.com abbia pubblicato DMARC Records, questa operazione non verrebbe contrassegnata come spoof tramite DMARC: 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

Nel client di posta elettronica (Outlook, Outlook sul Web o in qualsiasi altro client di posta elettronica), viene visualizzato solo il dominio da:, non il dominio nell'SPF o DKIM, e questo può indurre l'utente a pensare che il messaggio provenisse da example.com, ma che in realtà provenisse da maliciousDomain.com .
  
![Messaggio autenticato ma da: il dominio non è allineato con quello che ha superato SPF o DKIM](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
Per questo motivo, Office 365 richiede che il dominio nell'indirizzo from: sia allineato al dominio nella firma SPF o DKIM e, in caso contrario, contenga alcuni altri segnali interni che indicano che il messaggio è legittimo. In caso contrario, il messaggio è un errore compauth. 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

Pertanto, Office 365 anti-spoofing protegge i domini senza autenticazione e contro i domini che configurano l'autenticazione ma non corrispondono al dominio nell'indirizzo from: come quello che l'utente vede e ritiene essere il mittente del messaggio. Questo è vero per entrambi i domini esterni all'organizzazione, nonché per i domini all'interno dell'organizzazione.
  
Pertanto, se si riceve un messaggio che non ha avuto esito positivo sull'autenticazione composita ed è contrassegnato come contraffatto, anche se il messaggio ha superato SPF e DKIM, è perché il dominio che ha superato SPF e DKIM non è allineato al dominio nell'indirizzo from:.
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>Informazioni sulle modifiche apportate alla modalità di trattamento dei messaggi falsificati

Attualmente, per tutte le organizzazioni di Office 365-ATP e non-ATP-messages che non riescono DMARC con un criterio di rifiuto o quarantena sono contrassegnati come posta indesiderata e di solito prendere l'azione di posta indesiderata ad alta sicurezza, o talvolta la normale azione di posta indesiderata (a seconda se altro spam le regole lo identificano come posta indesiderata. I rilevamenti di spoofing intra-org eseguono la normale azione di posta indesiderata. Non è necessario che questo comportamento sia abilitato o che sia disabilitato.
  
Tuttavia, per i messaggi di spoofing tra domini, prima di questa modifica passa attraverso la posta indesiderata, phishing e i controlli antimalware, e se le altre parti del filtro le identificano come sospette, le contrassegnerà rispettivamente come posta indesiderata, phishing o malware. Con la nuova protezione da spoofing tra domini, tutti i messaggi che non possono essere autenticati, per impostazione predefinita, eseguono l'azione definita nel criterio di anti \> -spoofing anti-phishing. Se uno non è definito, verrà spostato in una cartella posta inDesiderata degli utenti. In alcuni casi, i messaggi più sospetti avranno anche il suggerimento per la sicurezza rossa aggiunto al messaggio.
  
Questo può comportare che alcuni messaggi che in precedenza erano contrassegnati come posta indesiderata continuano a essere contrassegnati come posta indesiderata ma avranno ora anche un suggerimento per la sicurezza rossa; in altri casi, i messaggi che sono stati precedentemente contrassegnati come non di posta indesiderata inizieranno a essere contrassegnati come posta indesiderata (CAT: SPOOF) con un suggerimento per la sicurezza rosso aggiunto. In altri casi, i clienti che stavano spostando tutti i messaggi di posta indesiderata e phishing alla quarantena, potrebbero ora visualizzarli nella cartella posta inDesiderata (questo comportamento può essere modificato, vedere [modifica delle impostazioni di anti-spoofing](#changing-your-anti-spoofing-settings)).
  
Sono disponibili diversi modi in cui un messaggio può essere falsificato (vedere [differenziazione tra diversi tipi di spoofing](#differentiating-between-different-types-of-spoofing) precedenti in questo articolo) ma a marzo 2018 il modo in cui Office 365 tratta questi messaggi non è ancora stato unificato. La tabella seguente è un breve riepilogo, con una protezione dello spoofing tra domini che è un nuovo comportamento: 
  
|**Tipo di spoofing**|**Categoria**|**Suggerimento sulla sicurezza aggiunto?**|**Si applica a**|
|:-----|:-----|:-----|:-----|
|DMARC Fail (Quarantine o Reject)  <br/> |HSPM (impostazione predefinita), può anche essere SPM o PHSH  <br/> |No (non ancora)  <br/> |Tutti i clienti di Office 365, Outlook.com  <br/> |
|Self-to-self  <br/> |SPM  <br/> |Sì  <br/> |Tutte le organizzazioni di Office 365, Outlook.com  <br/> |
|Cross-Domain  <br/> |SPOOF  <br/> |Sì  <br/> |Clienti di Office 365 Advanced Threat Protection e E5  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a>Modifica delle impostazioni di protezione da spoofing

Per creare o aggiornare le impostazioni di anti-spoofing (Cross-Domain), passare alle impostazioni anti-spoofing \> anti-phishing nella scheda criteri di gestione \> dei pericoli nel centro sicurezza &amp; e conformità. Se non sono state create impostazioni anti-phishing, sarà necessario crearne una:
  
![Antiphishing: creare un nuovo criterio](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
Se ne è già stato creato uno, è possibile selezionarlo per modificarlo:
  
![Antiphishing-modifica criteri esistenti](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
Selezionare il criterio appena creato e procedere con i passaggi descritti in [Learn more about spoofing Intelligence.](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)
  
![Abilitazione o disabilitazione dell'antispoofing](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![Abilitare o disabilitare i suggerimenti per la sicurezza antispoofing](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
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

È possibile modificare i parametri dei criteri di anti-phishing tramite PowerShell, seguendo la documentazione in [set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). È possibile specificare il $name come parametro:
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

Più avanti in 2018, invece di dover creare un criterio predefinito, verrà creato un ambito per tutti i destinatari dell'organizzazione, in modo che non sia necessario specificarlo manualmente (gli screenshot riportati di seguito sono soggetti a modifiche prima dell'implementazione finale).
  
![Criterio predefinito per antiphishing](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
A differenza di un criterio creato, non è possibile eliminare il criterio predefinito, modificarne la priorità oppure scegliere gli utenti, i domini o i gruppi a cui si desidera applicare l'ambito.
  
![Dettagli dei criteri predefiniti antiphishing](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
Per configurare la protezione predefinita tramite PowerShell:
  
```
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

È consigliabile disabilitare la protezione anti-spoofing solo se si dispone di un altro server di posta o di server di fronte a Office 365 (vedere gli scenari legittimi per disabilitare l'anti-spoofing per ulteriori dettagli). 
  
```
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> Se il primo hop nel percorso di posta elettronica è Office 365 e si ricevono troppi messaggi di posta elettronica legittimi contrassegnati come spoof, è consigliabile configurare i mittenti autorizzati a inviare messaggi di posta elettronica falsificati al proprio dominio (vedere la sezione *"gestione dei mittenti legittimi che stanno inviando u posta elettronica di nauthenticated "* ). Se si ricevono ancora troppi falsi positivi (ad esempio, messaggi legittimi contrassegnati come spoof), non è consigliabile disabilitare completamente la protezione anti-spoofing. Si consiglia invece di scegliere Basic anziché High Protection.                    È preferibile utilizzare i falsi positivi piuttosto che esporre la propria organizzazione a messaggi di posta elettronica falsificati che potrebbero imporre costi significativamente più alti a lungo termine.

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>Gestione dei mittenti legittimi che inviano messaggi di posta elettronica non autenticati

Office 365 tiene conto di chi sta inviando messaggi di posta elettronica non autenticati alla propria organizzazione. Se il servizio pensa che il mittente non sia legittimo, lo contrassegnerà come un errore *compauth* . Questo verrà classificato come SPOOF, anche se dipende dal criterio di anti-spoofing applicato al messaggio. 
  
Tuttavia, come amministratore, è possibile specificare quali mittenti sono autorizzati a inviare messaggi di posta elettronica falsificati, ignorando la decisione di Office 365.
  
**Metodo 1: se l'organizzazione è proprietaria del dominio, configurare l'autenticazione della posta elettronica**
  
Questo metodo può essere utilizzato per risolvere lo spoofing tra organizzazioni e lo spoofing tra domini nei casi in cui si è proprietari o si interagisce con più tenant. Consente inoltre di risolvere lo spoofing tra domini in cui si inviano ad altri clienti all'interno di Office 365 e anche di terze parti ospitate in altri provider.
  
Per ulteriori informazioni, vedere [clienti di Office 365](#customers-of-office-365). 
 
**Metodo 2: utilizzare l'intelligence spoof per configurare i mittenti consentiti di posta elettronica non autenticata**
  
È inoltre possibile utilizzare l' [Intelligence spoof](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) per consentire ai mittenti di trasmettere messaggi non autenticati alla propria organizzazione. 
  
Per i domini esterni, l'utente falsificato è il dominio nell'indirizzo mittente, mentre l'infrastruttura di invio è l'indirizzo IP di invio (suddiviso in/24 intervalli CIDR) o il dominio dell'organizzazione del record PTR (nella schermata seguente, l'IP di invio potrebbe essere 131.107.18.4 il cui record PTR è outbound.mail.protection.outlook.com e questo verrebbe visualizzato come outlook.com per l'infrastruttura di invio.
  
Per consentire al mittente di inviare messaggi di posta elettronica non autenticati, modificare il **numero** di un **Sì**.
  
![Configurazione dei mittenti consentiti per l'antispoofing](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
È inoltre possibile utilizzare PowerShell per consentire a un mittente specifico di falsificare il dominio: 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Ottenere mittenti contraffatti tramite PowerShell](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
Nell'immagine precedente sono state aggiunte altre interruzioni di riga per adattare la schermatura, ma in realtà tutti i valori verrebbero visualizzati su una singola riga.
  
Modificare il file e cercare la riga corrispondente a outlook.com e bing.com e modificare la voce AllowedToSpoof da no a Yes:
  
![Impostazione di spoofing Consenti Sì tramite PowerShell](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
Salvare il file e quindi eseguire: 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

Ciò consentirà ora a bing.com di inviare messaggi di posta \*elettronica non autenticati da. Outlook.com.

**Metodo 3: creare una voce Consenti per la coppia mittente/destinatario**
  
È inoltre possibile scegliere di ignorare tutti i filtri di posta indesiderata per un mittente specifico. Per ulteriori informazioni, vedere [come aggiungere un mittente in modo sicuro a un elenco di indirizzi consentiti in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).
  
Se si utilizza questo metodo, si ignorerà la posta indesiderata e parte del filtro phishing, ma non il filtro antimalware.
  
**Metodo 4-contattare il mittente e chiedere loro di configurare l'autenticazione della posta elettronica**
  
A causa del problema di posta indesiderata e phishing, Microsoft consiglia a tutti i mittenti di configurare l'autenticazione della posta elettronica. Se si conosce un amministratore del dominio di invio, contattarlo e richiedere che configurano i record di autenticazione della posta elettronica in modo che non sia necessario aggiungere eventuali sostituzioni. Per ulteriori informazioni, vedere [amministratori dei domini che non sono clienti di Office 365](#administrators-of-domains-that-are-not-office-365-customers)"più avanti in questo articolo. 
  
Anche se in un primo momento può essere difficile ottenere l'invio di domini per l'autenticazione, nel corso del tempo, poiché sempre più filtri per la posta elettronica avviano la posta indesiderata o addirittura rifiutano il proprio indirizzo di posta elettronica, verranno configurati i record corretti per garantire un miglior recapito.
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>Visualizzazione di report su quanti messaggi sono stati contrassegnati come falsificati

Dopo aver abilitato il criterio di spoofing, è possibile utilizzare l'intelligence di minacce per ottenere i numeri relativi al numero di messaggi contrassegnati come phishing. A tale scopo, accedere al centro sicurezza &amp; e conformità in \> Esplora minacce, impostare la visualizzazione phishing e il dominio del mittente o di protezione:
  
![Visualizzazione del numero di messaggi contrassegnati come phishing](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
È possibile interagire con i diversi rapporti per vedere quanti sono stati contrassegnati come phishing, inclusi i messaggi contrassegnati come SPOOF. Per ulteriori informazioni, vedere [Introduzione a Office 365 Threat Intelligence](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441).
  
Non è ancora possibile dividere quali messaggi sono stati contrassegnati a causa dello spoofing o di altri tipi di phishing (generale, rappresentazione del dominio o dell'utente e così via). Tuttavia, più avanti in 2018, sarà possibile eseguire questa operazione tramite il Centro sicurezza &amp; e conformità. Dopo averlo fatto, è possibile utilizzare questo rapporto come punto di partenza per identificare i domini di invio che possono essere legittimi contrassegnati come spoof a causa di un'autenticazione non riuscita.
  
La schermata seguente è una proposta per la modalità di visualizzazione dei dati, ma può variare quando viene rilasciata:
  
![Visualizzazione di report di phishing per tipo di rilevamento](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
Per i clienti non ATP e E5, questi rapporti saranno disponibili in un secondo momento in 2018 sotto i rapporti di stato di protezione dalle minacce (TPS), ma saranno ritardati di almeno 24 ore. Questa pagina verrà aggiornata perché è integrata nel centro sicurezza &amp; e conformità.
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>PreDizione del numero di messaggi che verranno contrassegnati come spoof

Più avanti in 2018, una volta che Office 365 aggiorna le impostazioni in modo che l'applicazione di antispoofing venga disAttivata o attivata con l'applicazione di base o elevata, verrà data la possibilità di visualizzare la modalità di modifica della disposizione dei messaggi nelle varie impostazioni. In altre informazioni, se l'anti-spoofing è disattivato, sarà possibile visualizzare il numero di messaggi che verranno rilevati come spoof se si attiva la funzionalità di base. in alternativa, se si tratta di base, sarà possibile visualizzare il numero di messaggi che verranno rilevati come spoof se lo si attiva in alto.
  
Questa funzionalità è attualmente in fase di sviluppo. Man mano che vengono definiti ulteriori dettagli, questa pagina verrà aggiornata sia con schermate del Centro sicurezza e conformità, sia con esempi di PowerShell.
  
![Report "che cosa succede se" per abilitare l'antispoofing](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![Possibile UX per consentire a un mittente falsificato](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>Informazioni sul modo in cui vengono combinati posta indesiderata, phishing e rilevamento avanzato di phishing

Le organizzazioni che utilizzano Exchange Online, con o senza ATP, possono specificare le azioni da intraprendere quando il servizio identifica i messaggi come malware, posta indesiderata, posta indesiderata elevata, phishing e massa. Con i criteri di anti-phishing ATP per i clienti ATP e i criteri di anti-phishing per i clienti di EOP e il fatto che un messaggio possa colpire più tipi di rilevamento (ad esempio, malware, phishing e User-Impersonation), può verificarsi una certa confusione su quale si applica il criterio. 
  
In generale, il criterio applicato a un messaggio viene identificato nell'intestazione X-Forefront-antispam-report nella proprietà CAT (categoria). 
  
|**Priorità**|**Criterio**|**Categoria**|**Dove gestito?**|**Si applica a**|
|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |Malware  <br/> |MALW  <br/> |[Criteri antiMalware](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|2  <br/> |Phishing  <br/> |PHSH  <br/> |[Criteri di filtro contenuto ospitato](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|3  <br/> |Alta probabilità di posta indesiderata  <br/> |HSPM  <br/> |[Criteri di filtro contenuto ospitato](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|4  <br/> |Spoofing  <br/> |SPOOF  <br/> |[Criteri di anti-phishing](https://go.microsoft.com/fwlink/?linkid=864553), [spoofing Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) <br/> |Tutte le organizzazioni  <br/> |
|5  <br/> |Posta indesiderata  <br/> |SPM  <br/> |[Criteri di filtro contenuto ospitato](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|6   <br/> |Bulk  <br/> |BULK  <br/> |[Criteri di filtro contenuto ospitato](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |Tutte le organizzazioni  <br/> |
|7   <br/> |Rappresentazione del dominio  <br/> |DIMP  <br/> |[Criteri di anti-phishing](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |Organizzazioni con solo ATP  <br/> |
|8   <br/> |Rappresentazione utente  <br/> |UIMP  <br/> |[Criteri di anti-phishing](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |Organizzazioni con solo ATP <br/> |
   
Se si dispone di più criteri di anti-phishing, verrà applicato quello con la priorità più alta. Si supponga, ad esempio, di disporre di due criteri:
  
|**Criterio**|**Priorità**|**Rappresentazione utente/dominio**|**Anti-spoofing**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1  <br/> |On  <br/> |Off  <br/> |
|B  <br/> |2  <br/> |Off  <br/> |Attivato  <br/> |
   
Se un messaggio viene identificato come spoofing e rappresentazione utente e lo stesso insieme di utenti ha come ambito il criterio A e il criterio B, il messaggio viene considerato come spoof ma non viene applicata alcuna azione poiché l'anti-spoofing è disattivato e SPOOF viene eseguito con una priorità più alta (4) rispetto alla rappresentazione dell'utente (8).
  
Per applicare altri tipi di criteri di phishing, è necessario modificare le impostazioni a cui sono applicati i diversi criteri.
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>Scenari legittimi per disabilitare l'anti-spoofing

L'anti-spoofing protegge meglio i clienti dagli attacchi di phishing e quindi la disabilitazione della protezione antispoofing è fortemente scoraggiata. Disabilitarlo, è possibile risolvere alcuni falsi positivi a breve termine, ma a lungo termine si sarà esposti a più rischi. Il costo per la configurazione dell'autenticazione da parte del mittente o la modifica dei criteri di phishing, in genere sono eventi di una tantum o che richiedono solo una manutenzione periodica minima. Tuttavia, il costo per il ripristino da un attacco di phishing in cui i dati sono stati esposti o che le risorse sono state compromesse è molto più alto.
  
Per questo motivo, è preferibile utilizzare i falsi positivi antispoofing anziché disabilitare la protezione anti-spoofing.
  
Tuttavia, esiste uno scenario legittimo in cui è necessario disabilitare l'antispoofing, ovvero quando sono presenti ulteriori prodotti per il filtro della posta elettronica nel routing dei messaggi e Office 365 non è il primo hop nel percorso di posta elettronica:
  
![Il record MX del cliente non punta a Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
L'altro server può essere un server di posta elettronica locale di Exchange, un dispositivo di filtro della posta, ad esempio IronPort, o un altro servizio ospitato su cloud.
  
Se il record MX del dominio del destinatario non punta a Office 365, non è necessario disabilitare l'anti-spoofing perché Office 365 cerca il record MX del dominio di ricezione ed Elimina l'anti-spoofing se punta a un altro servizio. Se non si sa se il dominio è di fronte a un altro server, è possibile utilizzare un sito Web come la casella degli strumenti MX per cercare il record MX. Si potrebbe dire qualcosa di simile al seguente:
  
![Record MX indica che il dominio non punta a Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
Questo dominio ha un record MX che non punta a Office 365, quindi Office 365 non applica l'applicazione anti-spoofing.
  
Tuttavia, se il record MX del dominio del destinatario ** punta a Office 365, anche se esiste un altro servizio di fronte a Office 365, è necessario disabilitare l'anti-spoofing. L'esempio più comune è l'utilizzo di una riscrittura dei destinatari: 
  
![Diagramma di routing per la riscrittura dei destinatari](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
Il record MX del dominio contoso. com punta al server locale, mentre il dominio @office365. contoso. NET del record MX punta a Office 365 perché contiene \*. Protection.Outlook.com, o \*. eo.Outlook.com nel record MX:
  
![Il record MX punta a Office 365, quindi probabilmente riscriverà il destinatario](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
Assicurarsi di distinguere se il record MX di un dominio del destinatario non punta a Office 365 e quando ha subito una riscrittura del destinatario. È importante indicare la differenza tra questi due casi.
  
Se non si è certi che il dominio di ricezione abbia subito un destinatario-riscrittura, a volte si può dire guardando le intestazioni del messaggio.
  
a) per prima cosa, esaminare le intestazioni del messaggio per il dominio del destinatario nell'intestazione Authentication-Results: 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

Il dominio del destinatario si trova nel testo in grassetto rosso sopra, in questo caso office365.contoso.net. Questo può essere diverso dal destinatario nell'intestazione to::
  
A: esempio \<destinatario destinatario @ contoso.com\>
  
Eseguire una ricerca di record MX del dominio del destinatario effettivo. Se contiene \*. protection.outlook.com, mail.Messaging.Microsoft.com, \*. eo.Outlook.com o mail.Global.frontbridge.com, significa che la MX punta a Office 365.
  
Se non contiene tali valori, significa che l'MX non punta a Office 365. Uno strumento che è possibile utilizzare per verificare questa è la casella degli strumenti MX.
  
In questo esempio viene indicato che contoso.com, il dominio che assomiglia al destinatario, poiché è stato l'intestazione to:, ha un record MX punta a un server on-Prem:
  
![Il record MX punta al server on-Prem](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
Tuttavia, il destinatario effettivo è office365.contoso.net il cui record MX punta a Office 365:
  
![MX punta a Office 365, deve essere riscrittura del destinatario](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
Pertanto, è probabile che questo messaggio abbia subito un destinatario-riscrittura.
  
b) in secondo luogo, accertarsi di distinguere tra i casi di utilizzo comuni delle riscritture dei destinatari. Se si intende riscrivere il dominio del destinatario in \*. onmicrosoft.com, riscriverlo in \*. mail.onmicrosoft.com.
  
Dopo aver identificato il dominio del destinatario finale instradato dietro un altro server e il record MX del dominio del destinatario punta effettivamente a Office 365 (come pubblicato nei suoi record DNS), è possibile procedere per disabilitare l'anti-spoofing.
  
Tenere presente che non si desidera disabilitare la funzionalità di anti-spoofing se il primo hop del dominio nel percorso di routing è Office 365, solo quando si è dietro uno o più servizi.
  
### <a name="how-to-disable-anti-spoofing"></a>Come disabilitare l'anti-spoofing

Se è già stato creato un criterio anti-phishing, impostare il parametro EnableAntispoofEnforcement su $false: 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

Se non si conosce il nome del criterio (o dei criteri) da disabilitare, è possibile visualizzarli: 
  
```
Get-AntiphishPolicy | fl Name
```

Se non si dispone di criteri di anti-phishing esistenti, è possibile crearne uno e disabilitarlo (anche se non si dispone di un criterio, l'anti-spoofing è ancora applicato; più avanti in 2018, verrà creato un criterio predefinito e sarà quindi possibile disabilitarlo anziché crearne uno) . Sarà necessario eseguire questa operazione in più passaggi: 
  
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

La disAttivazione dell'antispoofing è disponibile solo tramite cmdlet (più avanti nel Q2 2018 sarà disponibile nel centro sicurezza &amp; e conformità). Se non si ha accesso a PowerShell, creare un ticket di supporto.
  
Tenere presente che questo dovrebbe essere applicato solo ai domini che subiscono instradamenti indiretti quando vengono inviati a Office 365. Resistere alla tentazione di disabilitare l'anti-spoofing a causa di alcuni falsi positivi, sarà meglio a lungo andare a lavorare attraverso di loro.
  
### <a name="information-for-individual-users"></a>Informazioni per singoli utenti

I singoli utenti sono limitati nel modo in cui possono interagire con il suggerimento per la sicurezza anti-spoofing. Tuttavia, esistono diverse operazioni che è possibile eseguire per risolvere gli scenari comuni.
  
### <a name="common-scenario-1---mailbox-forwarding"></a>Scenario comune #1-inoltro delle cassette postali

Se si utilizza un altro servizio di posta elettronica e si inoltra la posta elettronica a Office 365 o Outlook.com, è possibile che la posta elettronica sia contrassegnata come spoofing e riceva un suggerimento per la sicurezza rossa. Office 365 e Outlook.com pianificano l'indirizzamento automatico quando il mittente è uno di Outlook.com, Office 365, Gmail o qualsiasi altro servizio che utilizza il [protocollo Arc](https://arc-spec.org). Tuttavia, finché non viene distribuita la correzione, gli utenti devono utilizzare la funzionalità account connessi per importare i propri messaggi direttamente, anziché utilizzare l'opzione di inoltro.
  
Per impostare gli account connessi in Office 365, selezionare l'icona a inGranaggio nell'angolo in alto a destra degli account \> di \> posta \> elettronica \> dell'interfaccia Web di Office 365.
  
![Opzione account connessi a Office 365](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
In Outlook.com, il processo è \> l'icona dell'ingranaggio opzioni \> account di posta elettronica \> account \> connessi.
  
### <a name="common-scenario-2---discussion-lists"></a>Scenario comune #2-liste di discussione

Gli elenchi di discussione hanno problemi con l'anti-spoofing a causa del modo in cui inoltrare il messaggio e modificarne il contenuto conservano l'indirizzo originale da:.
  
Si supponga, ad esempio, che l'indirizzo di posta elettronica sia user @ contoso.com e che sia interessato a Bird watching e si unisca all'elenco di discussione birdwatching @ example.com. Quando si invia un messaggio all'elenco di discussioni, è possibile inviarlo in questo modo:
  
**Da:** Utente di \<John Doe @ contoso.com\> 
  
**Per:** Elenco \<delle discussioni del birdwatching birdwatching @ example.com\> 
  
**Oggetto:** Ottima visualizzazione di Blue Jays nella parte superiore del Mt. Rainier questa settimana 
  
Tutti gli utenti che desiderano visualizzare la visualizzazione di questa settimana da mt. Rainier?
  
Quando l'elenco di posta elettronica riceve il messaggio, formatta il messaggio, ne modifica il contenuto e lo rivisualizza negli altri membri dell'elenco di discussione, costituito da partecipanti provenienti da numerosi ricevitori di posta elettronica diversi.
  
**Da:** Utente di \<John Doe @ contoso.com\> 
  
**Per:** Elenco \<delle discussioni del birdwatching birdwatching @ example.com\> 
  
**Oggetto:** BIRDWATCHING Ottima visualizzazione di Blue Jays nella parte superiore del Mt. Rainier questa settimana 
  
Tutti gli utenti che desiderano visualizzare la visualizzazione di questa settimana da mt. Rainier?
  
---
  
Questo messaggio è stato inviato all'elenco di discussione degli amanti del birdwatching. È possibile annullare la sottoscrizione in qualsiasi momento.
  
In questo modo, il messaggio riprodotto ha lo stesso indirizzo: Address (user @ contoso.com), ma il messaggio originale è stato modificato aggiungendo un tag alla riga dell'oggetto e un piè di pagina nella parte inferiore del messaggio. Questo tipo di modifica dei messaggi è comune nelle liste di distribuzione e può generare falsi positivi.
  
Se l'utente o un utente dell'organizzazione è un amministratore della mailing list, potrebbe essere possibile configurarlo in modo che superi i controlli di anti-spoofing.
  
- Controllare le domande frequenti su DMARC.org: [gestisco una mailing list e desidero interoperare con DMARC, cosa devo fare?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)
    
- Leggere le istruzioni riportate in questo post di Blog: [un suggerimento per gli operatori di mailing list che interagiscono con DMARC per evitare errori](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)
    
- Prendere in considerazione l'installazione degli aggiornamenti nel server di mailing list per supportare ARC, vedere[https://arc-spec.org](https://arc-spec.org/)
    
Se non si dispone della proprietà della mailing list:
  
- È possibile richiedere al manutentore della mailing list di implementare una delle opzioni sopra riportate (devono essere configurate anche le impostazioni di autenticazione della posta elettronica per il dominio da cui viene inoltrata la mailing list)
    
- È possibile creare le regole delle cassette postali nel client di posta elettronica per spostare i messaggi nella cartella posta in arrivo. È inoltre possibile richiedere agli amministratori dell'organizzazione di configurare le regole di autorizzazione o le sostituzioni come descritto nella sezione Managing legittima Senders che stanno inviando messaggi di posta elettronica non autenticati
    
- È possibile creare un ticket di supporto con Office 365 per creare una sostituzione per la mailing list per trattarla come legittima
    
### <a name="other-scenarios"></a>Altri scenari

1. Se nessuno degli scenari comuni precedenti si applica alla situazione, riportare il messaggio come falso positivo a Microsoft. Per ulteriori informazioni, vedere la sezione [come è possibile segnalare messaggi di posta indesiderata o non di posta indesiderata a Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) più avanti in questo articolo. 
    
2. È inoltre possibile contattare l'amministratore di posta elettronica che può sollevarlo come ticket di supporto con Microsoft. Il team di ingegneri Microsoft analizzerà il motivo per cui il messaggio è stato contrassegnato come spoof.
    
3. Inoltre, se si conosce il mittente e si è sicuri che non vengano falsificati in modo malevolo, è possibile rispondere al mittente che indica che inviano messaggi da un server di posta che non esegue l'autenticazione. In questo modo, a volte, il mittente originale contatterà l'amministratore IT che consentirà di impostare i record di autenticazione della posta elettronica necessari.
  
Quando un numero sufficiente di mittenti risponde ai proprietari dei domini che dovrebbero impostare i record di autenticazione della posta elettronica, li sprona a intervenire. Anche se Microsoft è compatibile con i proprietari di dominio per pubblicare i record necessari, è utile anche quando i singoli utenti lo richiedono.
    
4. Facoltativamente, aggiungere il mittente all'elenco Mittenti attendibili. Tuttavia, tenere presente che se un truffatore falsifica quell'account, verrà recapitato alla cassetta postale. Pertanto, questa opzione deve essere utilizzata con parsimonia.
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Come i mittenti di Microsoft devono prepararsi per la protezione anti-spoofing

Se si è un amministratore che attualmente invia messaggi a Microsoft, Office 365 o Outlook.com, è necessario assicurarsi che la posta elettronica sia autenticata in modo appropriato altrimenti potrebbe essere contrassegnata come posta indesiderata o phishing. 
  
### <a name="customers-of-office-365"></a>Clienti di Office 365

Se si è un cliente di Office 365 e si usa Office 365 per inviare la posta elettronica in uscita:
  
- Per i domini, [impostare SPF in Office 365 per evitare lo spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
    
- Per i domini primari, [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
    
- [Valutare la possibilità di configurare i record di DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) per il dominio per determinare chi sono i mittenti legittimi 
    
Microsoft non fornisce linee guida dettagliate sull'implementazione per ognuno di SPF, DKIM e DMARC. Tuttavia, sono presenti numerose informazioni pubblicate online. Ci sono anche società terze parti dedicate per aiutare l'organizzazione a configurare i record di autenticazione della posta elettronica.
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Amministratori di domini che non sono clienti di Office 365

Se si è un amministratore di dominio, ma non si tratta di un cliente di Office 365:
  
- È necessario configurare SPF per pubblicare gli indirizzi IP di invio del dominio e configurare DKIM (se disponibile) per la firma digitale dei messaggi. È inoltre possibile prendere in considerazione la configurazione dei record di DMARC.
    
- Se si dispone di mittenti in blocco che trasmettono messaggi di posta elettronica per conto dell'utente, è necessario collaborare con essi per inviare messaggi di posta elettronica in modo tale che il dominio di invio nell'indirizzo from: (se appartiene all'utente) sia allineato al dominio che passa SPF o DMARC.
    
- Se si dispone di server di posta elettronica locali o si inviano da un provider di servizi come software o da un servizio di hosting cloud come Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services o similari, è necessario verificare che vengano aggiunti al record SPF.
    
- Se si è un dominio di piccole dimensioni ospitato da un ISP, è necessario configurare il record SPF in base alle istruzioni fornite dall'ISP. La maggior parte degli ISP fornisce questo tipo di istruzioni e può essere trovato nelle pagine di supporto della società.
    
- Anche se non è stato necessario pubblicare i record di autenticazione della posta elettronica prima e ha funzionato bene, è comunque necessario pubblicare i record di autenticazione della posta elettronica da inviare a Microsoft. In questo modo, si contribuisce alla lotta contro il phishing e si riduce la possibilità che l'utente o le organizzazioni a cui si inviano vengano phishing.
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>Che cosa succede se non si conosce chi invia messaggi di posta elettronica come dominio?

Molti domini non pubblicano i record SPF perché non sanno chi sono tutti i mittenti. Va bene, non è necessario sapere chi sono tutti. È consigliabile, invece, iniziare con la pubblicazione di un record SPF per quelli che si conoscono, soprattutto in cui si trova il traffico aziendale e pubblicare un criterio SPF neutro,? all:
  
example.com IN TXT "v = spf1 include: SPF. example. com? All"
  
Il criterio SPF neutro indica che qualsiasi messaggio di posta elettronica che fuoriesce dall'infrastruttura aziendale passerà l'autenticazione della posta elettronica a tutti gli altri ricevitori di posta elettronica. La posta elettronica proveniente da mittenti che non si conoscono ricadrà su neutro, che è quasi uguale alla pubblicazione di nessun record SPF.
  
Quando si invia un messaggio a Office 365, la posta elettronica proveniente dal traffico aziendale verrà contrassegnata come autenticata, ma il messaggio di posta elettronica proveniente da fonti non riconosciute potrebbe essere ancora contrassegnato come spoof (a seconda che Office 365 possa autenticarlo implicitamente). Tuttavia, questo è ancora un miglioramento da tutti i messaggi di posta elettronica contrassegnati come spoof da Office 365.
  
Dopo aver iniziato con un record SPF con un criterio di fallback di? All, è possibile includere gradualmente sempre più infrastruttura di invio e quindi pubblicare un criterio più rigoroso. 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>Che cosa succede se si è il proprietario di una mailing list?

Vedere la sezione [scenario comune #2-liste di discussione](#common-scenario-2---discussion-lists). 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>Che cosa succede se si è un provider di infrastruttura, ad esempio un provider di servizi Internet (ISP), un provider di servizi di posta elettronica o un servizio di hosting cloud?

Se si ospita il messaggio di posta elettronica di un dominio e si invia la posta elettronica o si fornisce un'infrastruttura di hosting in grado di inviare messaggi di posta elettronica, è consigliabile eseguire le operazioni seguenti:
  
- Verificare che i clienti dispongano di documentazione dettagliata su cosa pubblicare nei propri record SPF
    
- Valutare la possibilità di firmare le firme di DKIM nei messaggi di posta elettronica in uscita anche se il cliente non l'ha esplicitamente configurata (segno con un dominio predefinito). È anche possibile firmare due volte il messaggio di posta elettronica con le firme di DKIM (una volta con il dominio del cliente se sono state configurate e una seconda volta con la firma DKIM della società)
    
La reCapito a Microsoft non è garantita anche se si autentica la posta elettronica proveniente dalla piattaforma, ma almeno garantisce che Microsoft non inrifiuti la posta elettronica perché non è autenticata. Per ulteriori informazioni sul modo in cui Outlook.com filtra la posta elettronica, vedere la [pagina postmaster di Outlook.com](https://postmaster.live.com/pm/postmaster.aspx).
  
Per ulteriori informazioni sulle procedure consigliate dei provider di servizi, vedere procedure consigliate [per la messaggistica mobile di M3AAWG per i provider di servizi](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
  
## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="why-is-microsoft-making-this-change"></a>Perché Microsoft sta facendo questa modifica?

A causa dell'impatto degli attacchi di phishing e poiché l'autenticazione della posta elettronica è in circolazione da oltre 15 anni, Microsoft ritiene che il rischio di continuare a consentire la posta elettronica non autenticata sia superiore al rischio di perdere la posta elettronica legittima.
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>Se questa modifica causa la posta elettronica legittima per essere contrassegnata come posta indesiderata?

All'inizio, vi saranno alcuni messaggi contrassegnati come posta indesiderata. Tuttavia, nel corso del tempo, i mittenti verranno adattati e quindi la quantità di messaggi erroneamente falsificati come contraffatti sarà trascurabile per la maggior parte dei percorsi di posta elettronica.
  
Microsoft stesso ha adottato questa funzionalità alcune settimane prima di distribuirlo al resto dei suoi clienti. Anche se all'inizio si è verificato un problema di disgregazione, è diminuito gradualmente.
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>Microsoft offrirà questa funzionalità a Outlook.com e ai clienti non avanzati di protezione dalle minacce di Office 365?

La tecnologia antispoofing di Microsoft è stata inizialmente distribuita alle organizzazioni che avevano un abbonamento a Office 365 Enterprise E5 o avevano acquistato il componente aggiuntivo di Office 365 Advanced Threat Protection (ATP) per la sottoscrizione. A ottobre 2018 è stata estesa la protezione alle organizzazioni che dispongono anche di Exchange Online Protection (EOP). In futuro, è possibile rilasciarlo per Outlook.com. Tuttavia, in questo caso, potrebbero essere presenti alcune funzionalità non applicate, ad esempio la creazione di report e le sostituzioni personalizzate.
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Come si fa a segnalare messaggi di posta indesiderata o non di posta indesiderata a Microsoft?

È possibile utilizzare il [componente aggiuntivo per i messaggi di report per Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)oppure, se non è installato, [inviare messaggi di posta indesiderata, non di posta indesiderata e tentativi di phishing a Microsoft per l'analisi](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>Sono un amministratore di dominio che non sa chi sono tutti i mittenti.

Consultare gli [amministratori dei domini che non sono clienti di Office 365](#administrators-of-domains-that-are-not-office-365-customers).
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>Cosa succede se si disattiva la protezione anti-spoofing per la propria organizzazione, anche se Office 365 è il filtro principale?

Non è consigliabile perché si è esposti a messaggi di posta indesiderata e di phishing più mancanti. Non tutti i tentativi di phishing sono spoofing e non verranno perse tutte le spoofing. Tuttavia, il rischio sarà maggiore rispetto a un cliente che Abilita l'anti-spoofing.
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>L'abilitazione della protezione anti-spoofing significa che sarò protetto da tutti i tentativi di phishing?

Purtroppo no, perché phisher si adatterà a utilizzare altre tecniche come gli account compromessi o a configurare gli account dei servizi gratuiti. Tuttavia, la protezione anti-phishing funziona molto meglio per rilevare questi altri tipi di metodi di phishing, perché i livelli di protezione di Office 365 sono stati disegnati insieme e si creano uno sopra l'altro.
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>Gli altri ricevitori di posta elettronica di grandi dimensioni bloccano la posta elettronica non autenticata?

Quasi tutti i destinatari di posta elettronica di grandi dimensioni implementano i tradizionali SPF, DKIM e DMARC. Alcuni ricevitori dispongono di altri controlli che sono più severi rispetto a quelli standard, ma pochi sono disponibili fino a Office 365 per bloccare il messaggio di posta elettronica non autenticato e trattarli come una parodia. Tuttavia, la maggior parte del settore sta diventando sempre più rigorosa su questo tipo di messaggio di posta elettronica, in particolare a causa del problema del phishing.
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>Se si Abilita l'anti-spoofing, è ancora necessaria l'opzione di filtro per la posta inDesiderata avanzata abilitata per il "fail duro SPF"?

No, questa opzione non è più necessaria perché la funzionalità di anti-spoofing non considera solo l'esito negativo di SPF, ma un insieme di criteri molto più ampio. Se è abilitata la funzionalità di anti-spoofing e l'opzione di failover rigido SPF è abilitata, è probabile che vengano configurati più falsi positivi. Si consiglia di disabilitare questa funzionalità poiché non fornirà quasi nessun ulteriore catch per la posta indesiderata o phishing e invece genererà principalmente falsi positivi.
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>Lo schema di riscrittura del mittente (SRS) consente di risolvere i messaggi di posta elettronica inoltrati?

SRS risolve solo parzialmente il problema del messaggio di posta elettronica inoltrato. Riscrivendo la posta SMTP da, SRS può garantire che il messaggio inoltrato passi SPF alla prossima destinazione. Tuttavia, poiché l'antispoofing è basato sull'indirizzo da: in combinazione con il dominio di posta elettronica o DKIM (o altri segnali), non è sufficiente impedire che la posta elettronica inoltrata venga contrassegnata come contraffatta.
  

