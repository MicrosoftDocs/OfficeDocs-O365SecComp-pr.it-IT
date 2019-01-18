---
title: Regole del flusso di posta (regole di trasporto in Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/29/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: È possibile utilizzare le regole del flusso di posta (dette anche regole di trasporto) per identificare ed eseguire azioni sui messaggi che transitano nell'organizzazione di Office 365.
ms.openlocfilehash: b6bd5f0510c8a9e5f5cc4679dce669b6da50f5e8
ms.sourcegitcommit: b0b0b716718c22779c7c04775b8010d65cd6656b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723243"
---
# <a name="mail-flow-rules-transport-rules-in-exchange-online-protection"></a>Regole del flusso di posta (regole di trasporto in Exchange Online Protection

È possibile utilizzare le regole del flusso di posta (dette anche regole di trasporto) per identificare ed eseguire azioni sui messaggi che transitano nell'organizzazione di Office 365. Le regole del flusso di posta sono analoghe a quelle della posta in arrivo che sono disponibili in Outlook e Outlook sul Web. La differenza principale è che le regole del flusso di posta eseguono azioni sui messaggi quando sono in transito e non dopo che il messaggio viene recapitato alla cassetta postale. Le regole del flusso di posta includono un insieme più ricco di condizioni, eccezioni e azioni, che forniscono la flessibilità necessaria per implementare molti tipi di criteri di messaggistica.
  
In questo articolo sono illustrati i componenti delle regole del flusso di posta e il loro funzionamento.
  
Per istruzioni su come creare, copiano e gestire le regole di flusso di posta elettronica, vedere **Gestisci regole di flusso di posta elettronica**. Per ogni regola, è necessario l'opzione di applicazione, test, o test e notifica al mittente. Per ulteriori informazioni sulle opzioni di test, vedere **Test una regola del flusso di posta elettronica** e **Suggerimenti sui criteri**.
  
Per rapporti dettagliati e di riepilogo sui messaggi corrispondenti alle regole relative al flusso di posta, vedere **Use mail protection reports in Office 365 to view data about malware, spam, and rule detections**.
  
Per implementare determinati criteri di messaggistica usando le regole del flusso di posta, vedere gli argomenti seguenti:
  
- [Use mail flow rules to inspect message attachments in Office 365](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)
    
- [Configurare la crittografia in Office 365 Enterprise](https://support.office.com/article/e86fc991-0161-4f01-9c1c-d25e87733d06)
    
- [Organization-wide message disclaimers, signatures, footers, or headers in Office 365](http://technet.microsoft.com/library/29ac61c2-77f1-4071-b14e-8cc64e3e76ba.aspx)
    
- [Use mail flow rules to set the spam confidence level (SCL) in messages](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)
    
- [Create organization-wide safe sender or blocked sender lists in Office 365](../create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md)
    
- [Riduzione dei pericoli di malware tramite blocco dei file allegati in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)
    
- [Definire le regole per crittografare o decrittografare i messaggi di posta elettronica](https://go.microsoft.com/fwlink/p/?Linkid=402846)
    
Nel seguente video viene fornita una dimostrazione dell'impostazione delle regole del flusso di posta in Exchange Online Protection.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]
  
## <a name="mail-flow-rule-components"></a>Componenti delle regole del flusso di posta

Una regola del flusso di posta è composta da condizioni, eccezioni, azioni e proprietà:
  
- **Condizioni** Identificare i messaggi ai quali applicare le azioni. Alcune condizioni esaminano i campi d'intestazione dei messaggi (ad esempio, i campi A, Da, o Cc). Altre condizioni esaminano le proprietà del messaggio (ad esempio, l'oggetto, il corpo, gli allegati, la dimensione o la classificazione). Per la maggior parte delle condizioni l'utente deve specificare un operatore di confronto (ad esempio, uguale a, diverso da o contiene) e un valore da utilizzare per la corrispondenza. Se non sono presenti condizioni o eccezioni, la regola viene applicata a tutti i messaggi. 
    
    Per ulteriori informazioni sulle condizioni delle regole del flusso della posta in Exchange Online Protection, vedere [eccezioni (predicati) e condizioni delle regole del flusso di posta in Exchange Online.](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).
    
- **Eccezioni** In modo facoltativo, identificare i messaggi sui quali non vanno applicate le azioni. Nelle eccezioni sono presenti gli stessi identificatori dei messaggi disponibili nelle condizioni. Le eccezioni sostituiscono le condizioni e impediscono l'esecuzione delle azioni della regola su un messaggio, anche nel caso in cui il messaggio soddisfi tutte le condizioni configurate. 
    
- **Azioni** Specificare cosa fare con i messaggi che soddisfano tutte le condizioni della regola e non corrispondono ad alcuna eccezione. Sono disponibili molte azioni, ad esempio il rifiuto, l'eliminazione o il reindirizzamento dei messaggi, l'aggiunta di altri destinatari, l'aggiunta di prefissi all'oggetto del messaggio o l'inserimento di dichiarazioni di non responsabilità nel corpo del messaggio. 
    
    Per ulteriori informazioni sulla posta flusso le azioni delle regole disponibili in Exchange Online Protection, vedere [posta azioni delle regole del flusso di Exchange Online Protection](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx).
    
- **Proprietà** Specificare altre impostazioni delle regole che sono diverse da condizioni, eccezioni o azioni. Ad esempio, quando è necessario applicare la regola oppure se applicare o verificare la regola, il periodo in cui la regola è attiva. 
    
     Per ulteriori informazioni, vedere la sezione in questo argomento [Proprietà regola flusso di posta](mail-flow-rules-transport-rules-0.md#Properties). 
    
### <a name="multiple-conditions-exceptions-and-actions"></a>Più condizioni, eccezioni e azioni

Nella tabella seguente è illustrato come in una regola vengono gestite più condizioni, valori della condizione, eccezioni e azioni.
  
|**Componente**|**Logica**|**Commenti**|
|:-----|:-----|:-----|
|Più condizioni  <br/> |E  <br/> |Un messaggio deve corrispondere a tutte le condizioni della regola. Se occorre una condizione di corrispondenza o un'altra, è possibile utilizzare regole distinte per ogni condizione. Ad esempio, per aggiungere la stessa dichiarazione di non responsabilità nei messaggi con allegati e nei messaggi con testo specifico, è possibile creare una regola per ogni condizione. Nell'interfaccia di amministrazione di Exchange, è possibile copiare facilmente una regola.  <br/> |
|Una condizione con più valori  <br/> |OPPURE  <br/> |Le stesse condizioni consentono di specificare più valori. Il messaggio deve corrispondere a uno qualsiasi (non tutti) dei valori specificati. Ad esempio, se in un messaggio di posta elettronica l'oggetto è Informazioni sul prezzo delle azioni e la condizione **L'oggetto include una o più parole seguenti** è configurata per la corrispondenza alle parole Contoso o azioni, la condizione è soddisfatta perché l'oggetto contiene almeno uno dei valori specificati.  <br/> |
|Più eccezioni  <br/> |OPPURE  <br/> |Se un messaggio corrisponde a una qualsiasi delle eccezioni, le azioni non vengono applicate al messaggio. Quest'ultimo non deve necessariamente corrispondere a tutte le eccezioni.  <br/> |
|Più azioni  <br/> |E  <br/> |I messaggi che corrispondono alle condizioni di una regola prendono tutte le azioni che sono specificate dalla regola. Ad esempio, se vengono selezionate le azioni **Anteponi all'oggetto del messaggio** e **Aggiungi destinatari alla casella Ccn**, verranno applicate entrambe al messaggio.  <br/> Tenere presente che alcune azioni come **Elimina il messaggio senza inviare alcuna notifica** impediscono l'applicazione a un messaggio delle regole successive. Altre azioni quali **Inoltra il messaggio** non consentono azioni aggiuntive.  <br/> È inoltre possibile impostare un'azione su una regola in modo che quando quella regola viene applicata, le regole successive non vengono applicate al messaggio.  <br/> |
   
### <a name="mail-flow-rule-properties"></a>Proprietà regola flusso di posta
<a name="Properties"> </a>

Nella tabella seguente vengono descritte le proprietà della regola che sono disponibili nelle regole di flusso della posta.
  
|**Nome proprietà nell'interfaccia di amministrazione di Exchange**|**Nome parametro in PowerShell**|**Descrizione**|
|:-----|:-----|:-----|
|**Priorità** <br/> | _Priority_ <br/> |Indica in che ordine le regole vengono applicate ai messaggi. La priorità predefinita si basa sul momento di creazione della regola; le regole meno recenti hanno una priorità superiore rispetto a quelle più nuove, mentre le regole con priorità superiore vengono elaborate prima delle regole con priorità inferiore.    <br/> La priorità della regola vengono modificate nell'interfaccia di amministrazione di Exchange spostando la regola verso l'alto o verso il basso nell'elenco delle regole. In PowerShell, impostare il numero di priorità (0 è la priorità più alta).    <br/> Ad esempio, in caso di una regola per rifiutare i messaggi che includono un numero di carta di credito e un'altra che richiede l'approvazione, è possibile far applicare per prima la regola per il rifiuto e interrompere l'applicazione delle altre regole.  |
|**Modalità** <br/> | _Mode_ <br/> |È possibile specificare se la regola deve elaborare i messaggi immediatamente oppure se le regole devono essere testate senza coinvolgere il recapito del messaggio (con o senza suggerimenti sui criteri DLP).  <br/> I suggerimenti per i criteri presentano una breve nota in Outlook o Outlook sul Web nella quale sono riportate informazioni sulle possibili violazioni del criterio indirizzate alla persona che sta creando il messaggio. Per ulteriori informazioni, vedere **Policy Tips**.  <br/> Per ulteriori informazioni sulle modalità, vedere **Testare una regola del flusso di posta elettronica**.  <br/> |
|**Attiva la regola in data** <br/> **Disattiva la regola in data** <br/> | _ActivationDate_ <br/>  _ExpiryDate_ <br/> |Specifica l'intervallo di date in cui la data è attiva.  <br/> |
|Casella di controllo **On** selezionata o deselezionata  <br/> |Nuove regole: parametro  _Enabled_ nel cmdlet **New-TransportRule**.  <br/> Regole esistenti: Utilizzare il cmdlet **Enable-TransportRule** o **Disable-TransportRule**.  <br/> Il valore viene visualizzato nella proprietà **State** della regola.  <br/> |È possibile creare una regola disabilitata e abilitarla successivamente, quando l'utente è pronto per sottoporla a test. In alternativa, è possibile disabilitare una regola senza eliminarla per preservare le impostazioni.  <br/> |
|**Rimanda il messaggio se l'elaborazione della regola non può essere completata** <br/> | _RuleErrorAction_ <br/> |È possibile specificare in che modo bisogna gestire il messaggio, se l'elaborazione della regola non può essere completata. Per impostazione predefinita, la regola sarà ignorata, ma è possibile scegliere di inviare di nuovo il messaggio per l'elaborazione.  <br/> |
|**Trova l'indirizzo del mittente nella parte seguente del messaggio** <br/> | _SenderAddressLocation_ <br/> |Se la regola usa condizioni o eccezioni che esaminano l'indirizzo e-mail del mittente, è possibile cercare il valore nell'intestazione del messaggio, nella busta del messaggio o in entrambi i punti.  <br/> |
|**Arrestare l'elaborazione di più regole** <br/> | _SenderAddressLocation_ <br/> |Si tratta di un'azione per la regola, ma ha l'aspetto di una proprietà nell'interfaccia di amministrazione di Exchange. È possibile scegliere di interrompere l'applicazione di ulteriori regole a un messaggio dopo che una regola elabora un messaggio.  <br/> |
|**Commenti** <br/> | _Comments_ <br/> |È possibile immettere commenti descrittivi sulla regola.  <br/> |
   
## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Modalità di applicazione delle regole del flusso di posta ai messaggi

Tutti i messaggi che transitano nell'organizzazione vengono valutati rispetto alle regole di trasporto abilitate per l'organizzazione. Le regole vengono elaborate nell'ordine elencato nella pagina **Flusso di posta** \> **Regole** nell'interfaccia di amministrazione di Exchange oppure sul valore del parametro  _Priority_ corrispondente in PowerShell. 
  
Ogni regola offre inoltre l'opzione di arrestare l'elaborazione di più regole in caso di corrispondenza della regola. Questa impostazione è importante per i messaggi che corrispondono alle condizioni di più regole del flusso di posta. Quale regola si desidera applicare al messaggio? Tutte? Solo una?
  
### <a name="differences-in-processing-based-on-message-type"></a>Differenze di elaborazione in base al tipo di messaggio

Esistono diversi tipi di messaggi che passano attraverso un'organizzazione. Nella seguente tabella sono riportati i tipi di messaggio che possono essere elaborati dalle regole del flusso di posta.
  
****

|**Tipo di messaggio**|**È possibile applicare una regola?**|
|:-----|:-----|
|**Messaggi normali** Messaggi che contengono un unico corpo in formato RTF, HTML o in testo normale oppure un corpo costituito da più parti o un insieme alternativo di corpi del messaggio.  <br/> |Sì  <br/> |
|**Crittografia dei messaggi di Office 365 ** Messaggi crittografati da Crittografia dei messaggi di Office 365 in Office 365. Per ulteriori informazioni, vedere [Crittografia dei messaggi di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=392525).  <br/> |Le regole possono sempre accedere alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni.  <br/> Affinché una regola possa esaminare o modificare i contenuti di un messaggio crittografato, è necessario verificare che la crittografia di trasporto sia abilitata (Obbligatoria o Facoltativa; l'impostazione predefinita è Facoltativa). Per ulteriori informazioni, vedere [Abilitare o disabilitare la decrittografia di trasporto](https://go.microsoft.com/fwlink/p/?linkid=848060).  <br/> È inoltre possibile creare una regola che consente di decrittografare automaticamente i messaggi crittografati. Per ulteriori informazioni, vedere [Definire le regole per crittografare o decrittografare i messaggi di posta elettronica](https://go.microsoft.com/fwlink/p/?Linkid=402846).  <br/> |
|**Messaggi crittografati (S/MIME)** <br/> |Le regole possono accedere solo alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni.  <br/> Le regole con le condizioni che richiedono l'analisi del contenuto del messaggio oppure le azioni che modificano i contenuti del messaggio non possono essere elaborate.  <br/> |
|**Messaggi protetti da RMS** Messaggi su cui è stato applicato il criterio Active Directory Rights Management Services (AD RMS) o Azure Rights Management (RMS).  <br/> |Le regole possono sempre accedere alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni.  <br/> Affinché una regola possa esaminare o modificare i contenuti di un messaggio protetto da RMS, è necessario verificare che la crittografia di trasporto sia abilitata (Obbligatoria o Facoltativa; l'impostazione predefinita è Facoltativa). Per ulteriori informazioni, vedere [Abilitare o disabilitare la decrittografia di trasporto](https://go.microsoft.com/fwlink/p/?linkid=848060).  <br/> |
|**Messaggi con firma in chiaro** Messaggi firmati ma non crittografati.  <br/> |Sì  <br/> |
|**Messaggi di messaggistica unificata** Messaggi creati o elaborati dal servizio di messaggistica unificata, ad esempio messaggi di segreteria telefonica, fax, notifiche di chiamata senza risposta e messaggi creati o inoltrati utilizzando Microsoft Outlook Voice Access.  <br/> |Sì  <br/> |
|**Messaggi anonimi** Messaggi inviati da mittenti anonimi.  <br/> |Sì  <br/> |
|**Rapporto di lettura** Rapporti generati in risposta alle richieste di conferma di lettura dei mittenti. I rapporti di lettura utilizzano la classe messaggio  `IPM.Note*.MdnRead` o  `IPM.Note*.MdnNotRead`.  <br/> |Sì  <br/> |
   
## <a name="what-else-should-i-know"></a>Informazioni aggiuntive

- La **versione** o il valore della proprietà **RuleVersion** per la regola non è importante in Exchange Online Protection. 
    
- Dopo aver creato o modificato una regola del flusso di posta, possono essere necessari fino a 30 minuti affinché la regola nuova o aggiornata venga applicata ai messaggi.
    
## <a name="for-more-information"></a>Ulteriori informazioni

[Gestione delle regole di trasporto](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)
  
[Transport Rule Predicates](http://technet.microsoft.com/library/04edeaba-afd4-4207-b2cb-51bcc44e483c.aspx)
  
[Azioni delle regole di trasporto](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)
  
[Utilizzo delle regole di trasporto per esaminare messaggi con allegati](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)
  
[Crittografia della posta elettronica in Office 365](https://support.office.com/article/c0d87cbe-6d65-4c03-88ad-5216ea5564e8)
  
[Procedure di regola di trasporto](http://technet.microsoft.com/library/bc682071-eb68-4cd9-a306-e5de0e1e79cc.aspx)
  
[Limiti delle regole di trasporto e per Posta in arrivo](https://go.microsoft.com/fwlink/p/?LinkId=324584)
  

