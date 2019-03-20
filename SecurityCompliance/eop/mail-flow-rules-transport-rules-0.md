---
title: Regole del flusso di posta (regole di trasporto in Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/29/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: È possibile utilizzare le regole del flusso di posta (regole di trasporto) per identificare ed eseguire azioni sui messaggi che passano attraverso l'organizzazione di Office 365.
ms.openlocfilehash: 379886788a4fa411d70830c702dd8850e8118b32
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693255"
---
# <a name="mail-flow-rules-transport-rules-in-exchange-online-protection"></a>Regole del flusso di posta (regole di trasporto in Exchange Online Protection

È possibile utilizzare le regole del flusso di posta (note anche come regole di trasporto) per identificare ed eseguire azioni sui messaggi che passano attraverso l'organizzazione di Office 365. Le regole del flusso di posta sono simili alle regole della posta in arrivo che sono disponibili in Outlook e Outlook sul Web. La differenza principale è che le regole del flusso di posta eseguono azioni sui messaggi quando sono in transito e non dopo che il messaggio viene recapitato alla cassetta postale. Le regole del flusso di posta includono un insieme più ricco di condizioni, eccezioni e azioni, che forniscono la flessibilità necessaria per implementare molti tipi di criteri di messaggistica.
  
In questo articolo sono illustrati i componenti delle regole del flusso di posta e il loro funzionamento.
  
Per i passaggi per creare, copiare e gestire le regole del flusso di posta, vedere **Manage Mail Flow Rules**. Per ciascuna regola è possibile applicare, verificare o testare e inviare una notifica al mittente. Per ulteriori informazioni sulle opzioni di verifica, vedere **Testare una regola del flusso di posta elettronica** e **Suggerimenti per i criteri**.
  
Per i report di riepilogo e dettagli sui messaggi che corrispondono alle regole del flusso di posta, vedere **Use Mail Protection Reports in Office 365 to view data about malware, spam, and Rule detections**.
  
Per implementare determinati criteri di messaggistica usando le regole del flusso di posta, vedere gli argomenti seguenti:
  
- [Utilizzare le regole del flusso di posta per esaminare gli allegati ai messaggi in Office 365](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)
    
- [Configurare la crittografia in Office 365 Enterprise](https://support.office.com/article/e86fc991-0161-4f01-9c1c-d25e87733d06)
    
- [Intestazioni, piè di pagina, firme o dichiarazioni di non responsabilità nei messaggi per tutta l'organizzazione in Office 365](http://technet.microsoft.com/library/29ac61c2-77f1-4071-b14e-8cc64e3e76ba.aspx)
    
- [Usare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)
    
- [Creare elenchi di mittenti attendibili o bloccati per l'intera organizzazione in Office 365](../create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md)
    
- [Riduzione dei pericoli di malware tramite blocco dei file allegati in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)
    
- [Definire le regole per crittografare o decrittografare i messaggi di posta elettronica](https://go.microsoft.com/fwlink/p/?Linkid=402846)
    
Nel video seguente viene fornita una dimostrazione dell'impostazione delle regole del flusso di posta in Exchange Online Protection.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]
  
## <a name="mail-flow-rule-components"></a>Componenti delle regole del flusso di posta

Una regola del flusso di posta è composta da condizioni, eccezioni, azioni e proprietà:
  
- **Condizioni** Identificare i messaggi ai quali applicare le azioni. Alcune condizioni esaminano i campi d'intestazione dei messaggi (ad esempio, i campi A, Da, o Cc). Altre condizioni esaminano le proprietà del messaggio (ad esempio, l'oggetto, il corpo, gli allegati, la dimensione o la classificazione). Per la maggior parte delle condizioni l'utente deve specificare un operatore di confronto (ad esempio, uguale a, diverso da o contiene) e un valore da utilizzare per la corrispondenza. Se non sono presenti condizioni o eccezioni, la regola viene applicata a tutti i messaggi. 
    
    Per ulteriori informazioni sulle condizioni delle regole del flusso di posta in Exchange Online Protection, vedere [Mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online.](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).
    
- **Eccezioni** In modo facoltativo, identificare i messaggi sui quali non vanno applicate le azioni. Nelle eccezioni sono presenti gli stessi identificatori dei messaggi disponibili nelle condizioni. Le eccezioni sostituiscono le condizioni e impediscono l'esecuzione delle azioni della regola su un messaggio, anche nel caso in cui il messaggio soddisfi tutte le condizioni configurate. 
    
- **Azioni** Specificare cosa fare con i messaggi che soddisfano tutte le condizioni della regola e non corrispondono ad alcuna eccezione. Sono disponibili molte azioni, ad esempio il rifiuto, l'eliminazione o il reindirizzamento dei messaggi, l'aggiunta di altri destinatari, l'aggiunta di prefissi all'oggetto del messaggio o l'inserimento di dichiarazioni di non responsabilità nel corpo del messaggio. 
    
    Per ulteriori informazioni sulle azioni delle regole del flusso di posta disponibili in Exchange Online Protection, vedere [Mail Flow Rule Actions in Exchange Online Protection](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx).
    
- **Proprietà** Specificare altre impostazioni delle regole che sono diverse da condizioni, eccezioni o azioni. Ad esempio, quando è necessario applicare la regola oppure se applicare o verificare la regola, il periodo in cui la regola è attiva. 
    
     Per ulteriori informazioni, vedere la sezione in questo argomento [Proprietà delle regole del flusso di posta](mail-flow-rules-transport-rules-0.md#Properties). 
    
### <a name="multiple-conditions-exceptions-and-actions"></a>Più condizioni, eccezioni e azioni

Nella tabella seguente è illustrato come in una regola vengono gestite più condizioni, valori della condizione, eccezioni e azioni.
  
|**Componente**|**Logica**|**Comments**|
|:-----|:-----|:-----|
|Più condizioni  <br/> |E  <br/> |Un messaggio deve corrispondere a tutte le condizioni della regola. Se occorre una condizione di corrispondenza o un'altra, è possibile utilizzare regole distinte per ogni condizione. Ad esempio, per aggiungere la stessa dichiarazione di non responsabilità nei messaggi con allegati e nei messaggi con testo specifico, è possibile creare una regola per ogni condizione. Nell'interfaccia di amministrazione di Exchange, è possibile copiare facilmente una regola.  <br/> |
|Una condizione con più valori  <br/> |O  <br/> |Le stesse condizioni consentono di specificare più valori. Il messaggio deve corrispondere a uno qualsiasi (non tutti) dei valori specificati. Ad esempio, se in un messaggio di posta elettronica l'oggetto è Informazioni sul prezzo delle azioni e la condizione **L'oggetto include una o più parole seguenti** è configurata per la corrispondenza alle parole Contoso o azioni, la condizione è soddisfatta perché l'oggetto contiene almeno uno dei valori specificati.  <br/> |
|Più eccezioni  <br/> |OPPURE  <br/> |Se un messaggio corrisponde a una qualsiasi delle eccezioni, le azioni non vengono applicate al messaggio. Quest'ultimo non deve necessariamente corrispondere a tutte le eccezioni.  <br/> |
|Più azioni  <br/> |E  <br/> |I messaggi che corrispondono alle condizioni di una regola prendono tutte le azioni che sono specificate dalla regola. Ad esempio, se vengono selezionate le azioni **Anteponi all'oggetto del messaggio** e **Aggiungi destinatari alla casella Ccn**, verranno applicate entrambe al messaggio.<br/> Tenere presente che alcune azioni come **Elimina il messaggio senza inviare alcuna notifica** impediscono l'applicazione a un messaggio delle regole successive. Altre azioni quali **Inoltra il messaggio** non consentono azioni aggiuntive.<br/> È inoltre possibile impostare un'azione su una regola in modo che quando quella regola viene applicata, le regole successive non vengono applicate al messaggio.  <br/> |
   
### <a name="mail-flow-rule-properties"></a>Proprietà regola flusso di posta
<a name="Properties"> </a>

Nella tabella seguente vengono descritte le proprietà della regola che sono disponibili nelle regole di flusso della posta.
  
|**Nome proprietà nell'interfaccia di amministrazione di Exchange**|**Nome del parametro in PowerShell**|**Descrizione**|
|:-----|:-----|:-----|
|**Priorità** <br/> | _Priority_ <br/> |Indica in che ordine le regole vengono applicate ai messaggi. La priorità predefinita si basa sul momento di creazione della regola; le regole meno recenti hanno una priorità superiore rispetto a quelle più nuove, mentre le regole con priorità superiore vengono elaborate prima delle regole con priorità inferiore.  <br/> La priorità della regola vengono modificate nell'interfaccia di amministrazione di Exchange spostando la regola verso l'alto o verso il basso nell'elenco delle regole. In PowerShell, impostare il numero di priorità (0 è la priorità più alta).  <br/> Ad esempio, in caso di una regola per rifiutare i messaggi che includono un numero di carta di credito e un'altra che richiede l'approvazione, è possibile far applicare per prima la regola per il rifiuto e interrompere l'applicazione delle altre regole.  |
|**Modalità** <br/> | _Mode_ <br/> |È possibile specificare se la regola deve elaborare i messaggi immediatamente oppure se le regole devono essere testate senza coinvolgere il recapito del messaggio (con o senza suggerimenti sui criteri DLP).  <br/> I suggerimenti per i criteri presentano una breve nota in Outlook o Outlook sul Web che fornisce informazioni sulle possibili violazioni dei criteri alla persona che sta creando il messaggio. Per ulteriori informazioni, vedere **Suggerimenti per i criteri**.  <br/> Per ulteriori informazioni sulle modalità, vedere **Testare una regola del flusso di posta elettronica**.  <br/> |
|**Attiva la regola in data** <br/> **Disattiva la regola in data** <br/> | _ActivationDate_ <br/>  _ExpiryDate_ <br/> | Specifica l'intervallo di date in cui la data è attiva.  <br/> |
|Casella di controllo **On** selezionata o deselezionata  <br/> |Nuove regole: parametro  _Enabled_ nel cmdlet **New-TransportRule**.  <br/> Regole esistenti: Utilizzare il cmdlet **Enable-TransportRule** o **Disable-TransportRule**.  <br/> Il valore viene visualizzato nella proprietà **State** della regola.  <br/> |È possibile creare una regola disabilitata e abilitarla successivamente, quando l'utente è pronto per sottoporla a test. In alternativa, è possibile disabilitare una regola senza eliminarla per preservare le impostazioni.  <br/> |
|**Rimanda il messaggio se l'elaborazione della regola non può essere completata** <br/> | _RuleErrorAction_ <br/> |È possibile specificare in che modo bisogna gestire il messaggio, se l'elaborazione della regola non può essere completata. Per impostazione predefinita, la regola sarà ignorata, ma è possibile scegliere di inviare di nuovo il messaggio per l'elaborazione.  <br/> |
|**Trova l'indirizzo del mittente nella parte seguente del messaggio** <br/> | _SenderAddressLocation_ <br/> |Se la regola usa condizioni o eccezioni che esaminano l'indirizzo e-mail del mittente, è possibile cercare il valore nell'intestazione del messaggio, nella busta del messaggio o in entrambi i punti.  <br/> |
|**Arrestare l'elaborazione di più regole** <br/> | _SenderAddressLocation_ <br/> |Si tratta di un'azione per la regola, ma ha l'aspetto di una proprietà nell'interfaccia di amministrazione di Exchange. È possibile scegliere di interrompere l'applicazione di ulteriori regole a un messaggio dopo che una regola elabora un messaggio.  <br/> |
|**Commenti** <br/> | _Comments_ <br/> |È possibile immettere commenti descrittivi sulla regola.  <br/> |
   
## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Modalità di applicazione delle regole del flusso di posta ai messaggi

Tutti i messaggi che transitano nell'organizzazione vengono valutati rispetto alle regole di trasporto abilitate per l'organizzazione. Le regole vengono elaborate nell'ordine elencato nella pagina **regole** del **flusso** \> di posta in EAC o in base al valore del parametro _Priority_ corrispondente in PowerShell. 
  
Ogni regola offre inoltre l'opzione di arrestare l'elaborazione di più regole in caso di corrispondenza della regola. Questa impostazione è importante per i messaggi che corrispondono alle condizioni di più regole del flusso di posta. Quale regola si desidera applicare al messaggio? Tutte? Solo una?
  
### <a name="differences-in-processing-based-on-message-type"></a>Differenze di elaborazione in base al tipo di messaggio

Esistono diversi tipi di messaggi che passano attraverso un'organizzazione. Nella seguente tabella sono riportati i tipi di messaggio che possono essere elaborati dalle regole del flusso di posta.
  
****

|**Tipo di messaggio**|**È possibile applicare una regola?**|
|:-----|:-----|
|**Messaggi normali** Messaggi che contengono un unico corpo in formato RTF, HTML o in testo normale oppure un corpo costituito da più parti o un insieme alternativo di corpi del messaggio.  <br/> |Sì  <br/> |
|* * Office 365 crittografia dei messaggi * * messaggi crittografati tramite la crittografia dei messaggi di Office 365 in Office 365. Per ulteriori informazioni, vedere [Crittografia dei messaggi di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=392525).  <br/> |Le regole possono sempre accedere alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni.  <br/> Affinché una regola possa esaminare o modificare i contenuti di un messaggio crittografato, è necessario verificare che la crittografia di trasporto sia abilitata (Obbligatoria o Facoltativa; l'impostazione predefinita è Facoltativa). Per ulteriori informazioni, vedere [Abilitazione o disabilitaZione](https://go.microsoft.com/fwlink/p/?linkid=848060)della decrittografia di trasporto.  <br/> È inoltre possibile creare una regola che consente di decrittografare automaticamente i messaggi crittografati. Per ulteriori informazioni, vedere [definire le regole per crittografare o decrittografare i messaggi di posta elettronica](https://go.microsoft.com/fwlink/p/?Linkid=402846).  <br/> |
|**Messaggi crittografati (S/MIME)** <br/> |Le regole possono accedere solo alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni.  <br/> Le regole con le condizioni che richiedono l'analisi del contenuto del messaggio oppure le azioni che modificano i contenuti del messaggio non possono essere elaborate.  <br/> |
|**Messaggi protetti da RMS** Messaggi in cui è stato applicato un criterio Active Directory Rights Management Services (AD RMS) o Azure Rights Management (RMS).  <br/> |Le regole possono sempre accedere alle intestazioni delle buste ed elaborare i messaggi in base alle condizioni che esaminano quelle intestazioni.  <br/> Affinché una regola possa esaminare o modificare i contenuti di un messaggio protetto da RMS, è necessario verificare che la crittografia di trasporto sia abilitata (Obbligatoria o Facoltativa; l'impostazione predefinita è Facoltativa). Per ulteriori informazioni, vedere [Abilitazione o disabilitaZione](https://go.microsoft.com/fwlink/p/?linkid=848060)della decrittografia di trasporto.  <br/> |
|**Messaggi con firma in chiaro** Messaggi firmati ma non crittografati.  <br/> |Sì  <br/> |
|**Messaggi di messaggistica unificata** Messaggi creati o elaborati dal servizio di messaggistica unificata, ad esempio messaggi di segreteria telefonica, fax, notifiche di chiamata senza risposta e messaggi creati o inoltrati utilizzando Microsoft Outlook Voice Access.  <br/> |Sì  <br/> |
|**Messaggi anonimi** Messaggi inviati da mittenti anonimi.  <br/> |Sì  <br/> |
|**Rapporto di lettura** Rapporti generati in risposta alle richieste di conferma di lettura dei mittenti. I rapporti di lettura utilizzano la classe messaggio  `IPM.Note*.MdnRead` o  `IPM.Note*.MdnNotRead`.  <br/> |Sì  <br/> |
   
## <a name="what-else-should-i-know"></a>Informazioni aggiuntive

- La **versione** o il valore della proprietà **RuleVersion** per una regola non è importante in Exchange Online Protection. 
    
- Dopo aver creato o modificato una regola del flusso di posta, possono essere necessari fino a 30 minuti affinché la regola nuova o aggiornata venga applicata ai messaggi.
    
## <a name="for-more-information"></a>Ulteriori informazioni
  
[Utilizzare le regole del flusso di posta per esaminare gli allegati di messaggi in Exchange Online](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)
  
[Crittografia della posta elettronica in Office 365](https://support.office.com/article/c0d87cbe-6d65-4c03-88ad-5216ea5564e8)
  
[Limiti delle regole di journal, trasporto e Posta in arrivo ](https://go.microsoft.com/fwlink/p/?LinkId=324584)
