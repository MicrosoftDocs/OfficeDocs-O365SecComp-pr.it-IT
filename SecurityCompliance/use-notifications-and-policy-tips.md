---
title: Invio di notifiche di posta elettronica e la visualizzazione di suggerimenti sui criteri per i criteri DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 87496bc5-9601-4473-8021-cb05c71369c1
description: "Un suggerimento per il criterio è una notifica o un avviso che viene visualizzato quando un utente funzioni correttamente con il contenuto in conflitto con un criterio DLP. È possibile utilizzare le notifiche di posta elettronica e suggerimenti sui criteri per aumentare la consapevolezza e consentono di informare gli utenti sui criteri dell'organizzazione. È inoltre possibile fornire agli utenti l'opzione per ignorare il criterio, in modo che non è bloccati se dispongono di un'azienda valida necessario o se il criterio rilevamento di un falso positivo. "
ms.openlocfilehash: a24afe6dd1203af4dc1f0f21468e828751bc5f3b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531408"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a>Invio di notifiche di posta elettronica e la visualizzazione di suggerimenti sui criteri per i criteri DLP

È possibile utilizzare un criterio di criterio DLP perdita di dati per identificare, monitorare e proteggere le informazioni contenute in Office 365. Si desidera che gli utenti dell'organizzazione che lavorano con le relative informazioni riservate per garantire la conformità ai criteri DLP ma non si desidera bloccare la inutilmente Guida il loro lavoro. Si tratta in notifiche tramite posta elettronica e suggerimenti sui criteri consentono di.
  
![Barra dei messaggi che mostra il suggerimento per i criteri in Excel 2016](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
Un suggerimento per il criterio è una notifica o un avviso che viene visualizzato quando un utente funzioni correttamente con il contenuto in conflitto con un criterio DLP, ovvero del contenuto, ad esempio, ad esempio una cartella di lavoro di Excel in OneDrive per sito Business che contiene informazioni di identificazione personale (PII) ed è condiviso con un utente esterno.
  
È possibile utilizzare le notifiche di posta elettronica e suggerimenti sui criteri per aumentare la consapevolezza e consentono di informare gli utenti sui criteri dell'organizzazione. È inoltre possibile fornire agli utenti l'opzione per ignorare il criterio, in modo che non è bloccati se dispongono di un'azienda valida necessario o se il criterio rilevamento di un falso positivo.
  
In Office 365 Security &amp; centro conformità, quando si crea un criterio DLP, è possibile configurare per le comunicazioni e utente:
  
- Inviare una notifica tramite posta elettronica per le persone che si sceglie che descrive il problema.
    
- Visualizzare un suggerimento criterio per il contenuto in conflitto con il criterio DLP:
    
  - Per la posta elettronica in Outlook sul web e Outlook 2013 e versioni successive, durante il messaggio è vengono composti suggerimento sul criterio visualizzata nella parte superiore di un messaggio di sopra i destinatari.
    
  - Per i documenti di OneDrive per Business account o un sito di SharePoint Online, il suggerimento sul criterio è indicato da un'icona di avviso che viene visualizzata nell'elemento. Per visualizzare ulteriori informazioni, è possibile selezionare un elemento e quindi fare clic su **informazioni**![l'icona nel riquadro informazioni](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) nell'angolo superiore destro della pagina per aprire il riquadro dei dettagli. 
    
  - Per 2016 Excel, PowerPoint 2016 e i documenti di Word 2016 sono archiviati in un OneDrive for Business sito o un sito di SharePoint Online è incluso nei criteri DLP, viene visualizzata la descrizione dei criteri nella barra dei messaggi e la visualizzazione Backstage (dal menu **File** \> ** Info**).
    
## <a name="add-user-notifications-to-a-dlp-policy"></a>Aggiungere le notifiche di utente a un criterio DLP

Quando si crea un criterio DLP, le notifiche tramite posta elettronica e suggerimenti sui criteri fanno parte della sezione **notifiche utente** . 
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola. L'utente è ora in Office 365 protezione &amp; centro conformità.
    
3. In sicurezza &amp; centro conformità \> riquadro di spostamento sinistro \> **prevenzione della perdita di dati** \> **criteri** \> **+ Crea un criterio**.
    
    ![Creare un pulsante di criteri](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Scegliere il modello di criterio DLP che consente di proteggere i tipi di informazioni riservate che è necessario \> **successivo**.
    
    Per iniziare con un modello vuoto, scegliere **personalizzato** \> **criteri personalizzato** \> **successivo**.
    
5. Nome del criterio \> **successivo**.
    
6. Per scegliere i percorsi che si desidera che il criterio DLP per proteggere, effettuare una delle operazioni seguenti:
    
  - Scegliere **tutte le posizioni in Office 365** \> **successivo**.
    
  - Scegliere **Seleziona manualmente percorsi specifici** \> **successivo**.
    
    Per includere o escludere un intero percorso, ad esempio tutta la posta elettronica Exchange o tutti gli account OneDrive, cambiare lo **stato** di tale posizione attivato o disattivato. 
    
    Per includere solo specifici siti di SharePoint o gli account OneDrive, cambiare lo **stato** su e quindi fare clic sui collegamenti in **Includi** scegliere specifici siti o gli account. 
    
7. Scegliere **Impostazioni avanzate di utilizzo** \> **successivo**.
    
8. Scegliere **+ nuova regola**.
    
9. Nell'editor di regole, in **notifiche utente**accensione lo stato.
    
    ![Sezione notifiche utente dell'editor regole](media/47705927-c60b-4054-a072-ab914f33d15d.png)
  
## <a name="options-for-configuring-email-notifications"></a>Opzioni di configurazione delle notifiche di posta elettronica

Per ogni regola in un criterio DLP, è possibile:
  
- Inviare la notifica agli utenti selezionati. Questi utenti possono essere il proprietario del contenuto, l'autore dell'ultima modifica apportata al contenuto, il proprietario del sito in cui è archiviato il contenuto o un utente specifico.
    
- Personalizzare il testo incluso nella notifica tramite HTML o i token. Vedere la sezione seguente per ulteriori informazioni.
    
> [!NOTE]
>  Notifiche tramite posta elettronica possono essere inviati soltanto a singoli destinatari, ovvero non gruppi o le liste di distribuzione. > Nuovo contenuto solo attiverà una notifica tramite posta elettronica. Modifica del contenuto esistente attiverà suggerimenti sui criteri, ma non una notifica tramite posta elettronica. 
  
![Opzioni di notifica di posta elettronica](media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a>Notifica di posta elettronica predefinita

Le notifiche hanno una riga dell'oggetto che inizia con l'azione eseguita, ad esempio "Notifica", "Messaggio bloccato" per la posta elettronica o "Accesso bloccato" per i documenti. Se la notifica è su un documento, corpo del messaggio di notifica include un collegamento che consente di passare al sito in cui il documento della archiviato e verrà visualizzata la descrizione dei criteri per il documento in cui è possibile risolvere eventuali problemi (vedere la sezione sui suggerimenti sui criteri). Se la notifica è su un messaggio, la notifica include come allegato di un messaggio che corrisponde a un criterio DLP.
  
![Messaggio di notifica](media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
Per impostazione predefinita, le notifiche consentono di visualizzare testo simile a quanto segue per un elemento in un sito. Il testo di notifica è configurato separatamente per ogni regola affinché venga visualizzato in modo diverso a seconda della regola che viene soddisfatta.
  
| |
|**Se la regola del criterio DLP…**|**Quindi notifica predefinito di SharePoint o OneDrive per i documenti aziendali che informa che si...**|**Quindi notifica predefinito per i messaggi di Outlook che informa che si...**|
|:-----|:-----|:-----|
|Invia una notifica, ma non consente di sostituzione  <br/> |Questo elemento è in conflitto con un criterio dell'organizzazione.  <br/> |Il messaggio di posta elettronica messaggio è in conflitto con un criterio nell'organizzazione.  <br/> |
|Blocca l'accesso, invia una notifica e consente di ignorarla  <br/> |In questo articolo è in conflitto con un criterio nell'organizzazione. Se si non risolvere il conflitto, l'accesso al file potrebbe risultare bloccato.  <br/> |Il messaggio di posta elettronica messaggio è in conflitto con un criterio nell'organizzazione. Il messaggio non è stato recapitato a tutti i destinatari.  <br/> |
|Blocca l'accesso e invia una notifica  <br/> |Questo elemento è in conflitto con un criterio dell'organizzazione. L'accesso a questo elemento è limitato al proprietario, all'autore dell'ultima modifica e all'amministratore della raccolta siti principale.  <br/> |Il messaggio di posta elettronica messaggio è in conflitto con un criterio nell'organizzazione. Il messaggio non è stato recapitato a tutti i destinatari.  <br/> |
   
### <a name="custom-email-notification"></a>Notifica tramite posta elettronica personalizzato

È possibile creare una notifica tramite posta elettronica personalizzato invece di inviare la notifica di posta elettronica predefinito per i utenti finali o gli amministratori. La notifica di posta elettronica personalizzato supporta HTML e ha un limite di 5.000 caratteri. È possibile utilizzare HTML per includere le immagini, la formattazione e altri marchi nella notifica.
  
È inoltre possibile utilizzare i token seguenti per personalizzare la notifica di posta elettronica. Questi token sono variabili che sono state sostituite da informazioni specifiche nella notifica inviata.
  
| |
|**Token**|**Descrizione**|
|:-----|:-----|
|% % AppliedActions % %  <br/> |Le azioni applicate al contenuto.  <br/> |
|% % ContentURL % %  <br/> |L'URL del documento nel sito di SharePoint Online o OneDrive per sito aziendale.  <br/> |
|% % MatchedConditions % %  <br/> |Le condizioni che sono state trovate corrispondenze per il contenuto. Utilizzare questo token per fornire agli utenti dei possibili problemi di contenuto.  <br/> |
   
![Messaggio di notifica con cui vengono visualizzati i token](media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a>Opzioni di configurazione dei suggerimenti per i criteri

Per ogni regola in un criterio DLP, è possibile configurare suggerimenti per i criteri per:
  
- Notificano semplicemente la persona che il contenuto in conflitto con un criterio DLP, in modo che possono agire per risolvere il conflitto. È possibile utilizzare il testo predefinito (vedere la tabella riportata di seguito) o immettere il testo personalizzato sui criteri specifici dell'organizzazione.
    
- Consentire all'utente di ignorare il criterio DLP. In alternativa, è possibile:
    
  - Richiede all'utente di immettere una motivazione aziendale per eseguire l'override del criterio. I dati vengono registrati e sarà possibile visualizzare nei rapporti DLP nella sezione **report** della sicurezza &amp; centro conformità. 
    
  - Consentire all'utente di segnalare un falso positivo e di ignorare il criterio DLP. Anche questa informazione viene registrata per il report affinché sia possibile utilizzare falsi positivi per ottimizzare le regole.
    
![Opzioni di suggerimento dei criteri](media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
Ad esempio, potrebbe essere applicato a OneDrive per i siti dei criteri DLP che rileva informazioni personali (PII) e il criterio prevede tre regole:
  
1. Prima regola: Se vengono rilevate meno di cinque istanze di queste informazioni riservate in un documento e il documento è condiviso con utenti interni all'organizzazione, l'azione **Invia una notifica** mostra un suggerimento per i criteri. Non sono necessarie opzioni per ignorare i suggerimenti per i criteri perché la regola sta semplicemente informando l'utente senza bloccargli l'accesso. 
    
2. In secondo luogo della regola: se maggiore di cinque istanze di queste informazioni riservate vengono rilevate in un documento e il documento è condiviso con persone all'interno dell'organizzazione, l'azione di **bloccare l'accesso al contenuto** consente di limitare le autorizzazioni per il file e le ** Inviare una notifica** azione consente agli utenti di fornire una giustificazione aziendale per ignorare le azioni nell'elenco questa regola. Non si desidera il criterio DLP per bloccare queste operazioni aziendali dell'organizzazione richiede talvolta utenti interni di condividere dati PII. 
    
3. Terza regola: Se vengono rilevate più di cinque istanze di queste informazioni riservate in un documento e il documento è condiviso con utenti esterni all'organizzazione, l'azione **Blocca accesso al contenuto** limita le autorizzazioni per il file e l'azione **Invia una notifica** non consente agli utenti di ignorare le azioni in questa regola perché l'informazione è condivisa esternamente. In nessun caso gli utenti dell'organizzazione possono condividere dati PII all'esterno dell'organizzazione. 
    
Di seguito sono riportati alcuni punti per comprendere l'utilizzo di un suggerimento per i criteri per ignorare una regola:
  
- L'opzione per eseguire l'override è per ogni regola e viene eseguito l'override di tutte le azioni della regola (ad eccezione di inviare una notifica, non può essere ignorata).
    
- È possibile che il contenuto da soddisfare le diverse regole in un criterio DLP, ma verrà visualizzato solo il suggerimento per il criterio in base alla regola più restrittivo, priorità più alta. Ad esempio, un suggerimento per il criterio da una regola che blocca l'accesso al contenuto verrà visualizzato su un suggerimento sul criterio da una regola che si limita a inviare una notifica. In questo modo si impedisce persone da visualizzare in una serie di suggerimenti sui criteri.
    
- Se i suggerimenti per i criteri nella regola più restrittiva consentono all'utente di ignorare la regola, in questo modo vengono ignorate anche le altre regole per le quali è stata rilevata una corrispondenza del contenuto.
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a>Suggerimenti per i criteri nei siti OneDrive for Business e SharePoint Online

Quando una regola di un criterio DLP corrisponde a un documento in un OneDrive for Business sito o un sito di SharePoint Online e tale regola utilizza suggerimenti sui criteri, suggerimenti sui criteri di visualizzare le icone speciali per il documento:
  
1. Se la regola invia una notifica relativa al file, viene visualizzata l'icona di avviso.
    
2. Se la regola blocca l'accesso al documento, viene visualizzata l'icona di blocco.
    
![Icone suggerimento criterio nei documenti di un account OneDrive](media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
Eseguire un'azione in un documento, è possibile selezionare un elemento \> scegliere **informazioni**![l'icona nel riquadro informazioni](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) nell'angolo superiore destro della pagina per aprire il riquadro dei dettagli \> **suggerimento sul criterio di visualizzazione**.
  
Il suggerimento per i criteri elenca i problemi con il contenuto e, se i suggerimenti per i criteri sono configurati con queste opzioni, è possibile selezionare **Risolvi** e quindi **ignorare** il suggerimento per i criteri oppure **segnalare** un falso positivo. 
  
![Suggerimento per il criterio che mostra informazioni riquadro](media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![Suggerimento per i criteri con l'opzione per eseguire l'override](media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
I criteri DLP sono sincronizzati con i siti e il contenuto viene valutato periodicamente e in modo asincrono, quindi potrebbe esserci un breve ritardo tra il momento in cui viene creato il criterio DLP e il momento in cui si iniziano a visualizzare i suggerimenti per i criteri. Potrebbe verificarsi un ritardo simile da quando si risolve o si ignora un suggerimento per i criteri a quando scompare l'icona sul documento nel sito.
  
### <a name="default-text-for-policy-tips-on-sites"></a>Testo predefinito per i suggerimenti dei criteri nei siti

Per impostazione predefinita, i suggerimenti per i criteri consentono di visualizzare testo simile a quanto segue per un elemento in un sito. Il testo di notifica è configurato separatamente per ogni regola affinché venga visualizzato in modo diverso a seconda della regola che viene soddisfatta.
  
| |
|**Se la regola del criterio DLP…**|**Nel suggerimento per i criteri predefinito viene visualizzato…**|
|:-----|:-----|
|Invia una notifica, ma non consente di sostituzione  <br/> |Questo elemento è in conflitto con un criterio dell'organizzazione.  <br/> |
|Blocca l'accesso, invia una notifica e consente di ignorarla  <br/> |In questo articolo è in conflitto con un criterio nell'organizzazione. Se si non risolvere il conflitto, l'accesso al file potrebbe risultare bloccato.  <br/> |
|Blocca l'accesso e invia una notifica  <br/> |Questo elemento è in conflitto con un criterio dell'organizzazione. L'accesso a questo elemento è limitato al proprietario, all'autore dell'ultima modifica e all'amministratore della raccolta siti principale.  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a>Testo personalizzato per suggerimenti sui criteri nei siti

È possibile personalizzare il testo per suggerimenti sui criteri separatamente rispetto al notifica tramite posta elettronica. A differenza di testo personalizzato per le notifiche tramite posta elettronica (vedere sopra la sezione), il testo personalizzato per suggerimenti sui criteri non accetta HTML o i token. In realtà, il testo personalizzato per suggerimenti sui criteri è in testo normale solo con un massimo di 256 caratteri.
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a>Suggerimenti per il criterio in Outlook sul web e Outlook 2013 e versioni successive

Quando si compone di un nuovo messaggio di posta elettronica in Outlook sul web e Outlook 2013 e versioni successive, verrà visualizzato un suggerimento criterio se si aggiunge il contenuto che corrisponde a una regola di un criterio DLP e tale regola utilizza suggerimenti sui criteri. Il suggerimento per il criterio viene visualizzata nella parte superiore del messaggio, sopra i destinatari durante la quale vengono composti il messaggio.
  
![Suggerimento per il criterio nella parte superiore di un messaggio viene composto](media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
Criteri di suggerimenti per il lavoro se le informazioni riservate viene visualizzato nel corpo del messaggio, riga dell'oggetto o persino un allegato del messaggio come illustrato di seguito.
  
![Suggerimento sul criterio che mostra che un allegato in conflitto con un criterio DLP](media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
Se i suggerimenti sul criterio sono configurate per consentire l'override, è possibile scegliere **Mostra dettagli** \> **ignorare** \> immettere motivazione aziendale o un falso positivo \> **eseguire l'Override**.
  
![Suggerimento per il criterio nel messaggio espanso per visualizzare l'opzione di Override](media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![Finestra di dialogo suggerimento criteri in cui è possibile ignorare il suggerimento sul criterio](media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
Si noti che quando si aggiungono informazioni riservate a un messaggio di posta elettronica, potrebbe esserci latenza tra cui le informazioni riservate viene aggiunto e quando viene visualizzato il suggerimento sul criterio.
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a>Suggerimenti per il criterio nell'interfaccia di amministrazione di Exchange e la protezione di Office 365 &amp; centro conformità

Suggerimenti per i criteri possono lavorare con i criteri DLP e create nell'interfaccia di amministrazione di Exchange o con i criteri DLP creati in Office 365 Security le regole di flusso di posta &amp; centro conformità, ma non entrambi. Ciò avviene perché questi criteri vengono archiviati in percorsi diversi, ma solo da un'unica posizione possa disegnare suggerimenti sui criteri.
  
Se è stato configurato suggerimenti sui criteri nell'interfaccia di amministrazione di Exchange, eventuali suggerimenti sui criteri che consentono di configurare in Office 365 Security &amp; centro conformità non viene visualizzato agli utenti in Outlook sul web e Outlook 2013 e versioni successive fino a quando non si disattiva i suggerimenti nello scambio Interfaccia di amministrazione. In questo modo che le regole di trasporto di Exchange corrente continuerà a funzionare fino a quando non è possibile passare a Office 365 Security &amp; centro conformità.
  
Si noti che le notifiche di posta elettronica mentre suggerimenti sui criteri possa disegnare solo da un'unica posizione, sempre inviato, anche se si utilizza criteri DLP nel entrambi della protezione di Office 365 &amp; centro conformità e l'interfaccia di amministrazione di Exchange.
  
### <a name="default-text-for-policy-tips-in-email"></a>Testo predefinito per i suggerimenti sui criteri di posta elettronica

Per impostazione predefinita, suggerimenti sui criteri di visualizzazione del testo simile al seguente per la posta elettronica.
  
| |
|**Se la regola del criterio DLP…**|**Nel suggerimento per i criteri predefinito viene visualizzato…**|
|:-----|:-----|
|Invia una notifica, ma non consente di sostituzione  <br/> |Il messaggio di posta elettronica in conflitto con un criterio nell'organizzazione.  <br/> |
|Blocca l'accesso, invia una notifica e consente di ignorarla  <br/> |Il messaggio di posta elettronica in conflitto con un criterio nell'organizzazione.  <br/> |
|Blocca l'accesso e invia una notifica  <br/> |Il messaggio di posta elettronica in conflitto con un criterio nell'organizzazione.  <br/> |
   
## <a name="policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Suggerimenti per i criteri in Excel 2016, PowerPoint 2016 e Word 2016

Quando gli utenti lavorano con contenuti riservati nelle versioni desktop di Excel 2016, PowerPoint 2016 e Word 2016, i suggerimenti per i criteri possono informarli in tempo reale che il contenuto è in conflitto con un criterio DLP. Ciò richiede che:
  
- Il documento di Office è archiviato in un sito OneDrive for Business o SharePoint Online.
    
- Il sito è incluso in un criterio DLP configurato per utilizzare i suggerimenti sui criteri.
    
Queste applicazioni desktop di Office 2016 sincronizzare automaticamente i criteri DLP direttamente da Office 365 e quindi di analisi dei documenti per assicurarsi che non sono in conflitto con i criteri DLP e visualizzazione dei suggerimenti dei criteri in tempo reale.
  
A seconda della modalità di configurazione dei suggerimenti per i criteri nel criterio DLP, gli utenti possono scegliere se ignorare semplicemente il suggerimento per i criteri, ignorare il criterio con o senza una motivazione aziendale oppure segnalare un falso positivo.
  
I suggerimenti per i criteri vengono visualizzati nella barra dei messaggi.
  
![Barra dei messaggi che mostra il suggerimento per i criteri in Excel 2016](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
I suggerimenti per i criteri sono visibili anche nella visualizzazione Backstage (nella scheda **File**). 
  
![Backstage che mostra il suggerimento per i criteri in Excel 2016](media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
Se i suggerimenti per i criteri nel criterio DLP sono configurati con queste opzioni, è possibile selezionare **Risolvi** per **ignorare** un suggerimento per i criteri oppure **segnalare** un falso positivo. 
  
![Opzioni sul suggerimento per i criteri in Backstage in Excel 2016](media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
In ognuno di questi programmi desktop di Office 2016, gli utenti possono scegliere se disattivare i suggerimenti per i criteri. Se disattivati, i suggerimenti per i criteri che sono delle semplici notifiche non vengono visualizzati nella barra dei messaggi o nella visualizzazione Backstage (nella scheda **File**). Tuttavia, i suggerimenti per i criteri di blocco o sostituzione continuano a essere visualizzati e a ricevere notifiche di posta elettronica. Inoltre, la disattivazione dei suggerimenti per i criteri non esclude il documento da eventuali criteri DLP che vi sono stati applicati. 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Testo predefinito per i suggerimenti per i criteri in Excel 2016, PowerPoint 2016 e Word 2016

Per impostazione predefinita, i suggerimenti per i criteri mostrano un testo simile a quanto segue nella barra dei messaggi e nella visualizzazione Backstage di un documento aperto. Il testo di notifica è configurato separatamente per ogni regola affinché venga visualizzato in modo diverso a seconda della regola che viene soddisfatta.
  
| |
|**Se la regola del criterio DLP…**|**Nel suggerimento per i criteri predefinito viene visualizzato…**|
|:-----|:-----|
|Invia una notifica, ma non consente di sostituzione  <br/> |In questo file in conflitto con un criterio nell'organizzazione. Vai dal menu **File** per ulteriori informazioni.<br/> |
|Blocca l'accesso, invia una notifica e consente di ignorarla  <br/> |In questo file in conflitto con un criterio nell'organizzazione. Se si non risolvere il conflitto, l'accesso al file potrebbe risultare bloccato. Vai dal menu **File** per ulteriori informazioni.<br/> |
|Blocca l'accesso e invia una notifica  <br/> |In questo file in conflitto con un criterio nell'organizzazione. Se si non risolvere il conflitto, l'accesso al file potrebbe risultare bloccato. Vai dal menu **File** per ulteriori informazioni.<br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Suggerimenti per il testo personalizzato per i criteri in Excel 2016, 2016 PowerPoint e Word 2016

È possibile personalizzare il testo per suggerimenti sui criteri separatamente rispetto al notifica tramite posta elettronica. A differenza di testo personalizzato per le notifiche tramite posta elettronica (vedere sopra la sezione), il testo personalizzato per suggerimenti sui criteri non accetta HTML o i token. In realtà, il testo personalizzato per suggerimenti sui criteri è in testo normale solo con un massimo di 256 caratteri.
  
## <a name="more-information"></a>Ulteriori informazioni

- [Panoramica relativa ai criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md)
    
- [Creare un criterio DLP da un modello](create-a-dlp-policy-from-a-template.md)
    
- [Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà](protect-documents-that-have-fci-or-other-properties.md)
    
- [Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
    
- [Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)
    

