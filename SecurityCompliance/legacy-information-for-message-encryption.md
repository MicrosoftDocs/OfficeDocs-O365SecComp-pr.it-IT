---
title: Informazioni di natura legacy per la crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
description: Se si ancora non sono stati spostati organizzazione Office 365 per le nuove funzionalità OME, ma sono già stati distribuiti OME, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia che si intende spostare le nuove funzionalità OME non appena è ragionevole per l'organizzazione. Per ulteriori informazioni, vedere Set up le nuove funzionalità di Office 365 Message Encryption basate sulla protezione delle informazioni di Azure. Se si desidera trovare ulteriori informazioni sul funzionamento innanzitutto le nuove funzionalità, vedere Office 365 Message Encryption. Il resto di questo articolo si riferisce al comportamento OME prima del rilascio delle nuove funzionalità OME.
ms.openlocfilehash: d5b21cbe0004ca7bda38085bd5d8ef5f2a22b04e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530886"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Informazioni di natura legacy per la crittografia dei messaggi di Office 365

Se si ancora non sono stati spostati organizzazione Office 365 per le nuove funzionalità OME, ma sono già stati distribuiti OME, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia che si intende spostare le nuove funzionalità OME non appena è ragionevole per l'organizzazione. Per ulteriori informazioni, vedere [impostare le nuove funzionalità di Office 365 Message Encryption basate sulla protezione delle informazioni di Azure](set-up-new-message-encryption-capabilities.md). Se si desidera trovare ulteriori informazioni sul funzionamento innanzitutto le nuove funzionalità, vedere [Office 365 Message Encryption](ome.md). Il resto di questo articolo si riferisce al comportamento OME prima del rilascio delle nuove funzionalità OME.
  
Con Office 365 Message Encryption, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra utenti interni ed esterni all'organizzazione. Office 365 della crittografia dei messaggi con Outlook.com, Yahoo, Gmail e altri servizi di posta elettronica. Crittografia dei messaggi posta elettronica è possibile essere certi che destinata unicamente i destinatari può visualizzare il contenuto del messaggio.
  
Ecco alcuni esempi:
  
- Un dipendente di banca invia carta di credito ai clienti
    
- Un rappresentante compagnia di assicurazione fornisce dettagli ai clienti
    
- Un broker di mutui richiede informazioni finanziarie di un cliente per offrire un prestito
    
- Un operatore sanitario invia informazioni mediche ai pazienti
    
- Un avvocato invia informazioni riservate a un cliente o a un altro avvocato
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Funzionamento di Office 365 Message Encryption senza le nuove funzionalità

Crittografia dei messaggi di Office 365 è un servizio online che si basa su Microsoft Azure Rights Management (Azure RMS). Con Azure RMS, gli amministratori possono definire regole per determinare le condizioni per la crittografia del flusso di posta elettronica. Ad esempio, una regola può richiedere la crittografia di tutti i messaggi indirizzati a un destinatario specifico.
  
Guardare questo breve video per vedere come funziona la crittografia dei messaggi di Office 365 senza le nuove funzionalità.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
Quando si riceve un messaggio di posta elettronica di Exchange Online che corrisponde a una regola di crittografia, il messaggio viene inviato con un allegato HTML. Il destinatario apre l'allegato HTML e segue le istruzioni per visualizzare il messaggio crittografato nel portale di Office 365 Message Encryption. Il destinatario è possibile scegliere di visualizzare il messaggio accesso con un account Microsoft o un ufficio o scuola associate a Office 365, o un passcode occasionale. Entrambe le opzioni in modo che solo il destinatario è possibile visualizzare il messaggio crittografato. Questo processo è molto diverso per le nuove funzionalità OME.
  
Nel seguente diagramma viene riepilogata la procedura di crittografia e decrittografia di un messaggio di posta elettronica.
  
![Diagramma del percorso di un messaggio di posta elettronica crittografato](media/O365-Office365MessageEncryption-Concept.png)
  
Per ulteriori informazioni, vedere [informazioni sul servizio per la crittografia messaggi Office 365 legacy prima della versione delle nuove funzionalità OME](legacy-information-for-message-encryption.md#LegacyServiceInfo).
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Definizione delle regole di flusso della posta per Office 365 Message Encryption che non utilizzano le nuove funzionalità OME

Per abilitare la crittografia dei messaggi di Office 365 senza le nuove funzionalità, gli amministratori di Exchange Online ed Exchange Online Protection definire regole del flusso di posta di Exchange. Queste regole determinano sotto il messaggio di posta elettronica le condizioni devono essere crittografati i messaggi, nonché alle condizioni per la rimozione di crittografia dei messaggi. Quando viene impostata un'azione di crittografia per una regola, i messaggi che soddisfano le condizioni regola vengono crittografati prima che sta inviati.
  
Regole del flusso di posta elettronica sono flessibili, consentendo di combinare le condizioni in modo che è possibile soddisfare i requisiti di protezione specifici in una sola regola. Ad esempio, è possibile creare una regola per crittografare tutti i messaggi che contengono le parole chiave specificate e vengono specificati i destinatari esterni. Crittografia dei messaggi di Office 365 crittografato anche le risposte dei destinatari di posta elettronica crittografati ed è possibile creare una regola che consente di decrittografare le risposte convenienza dell'utente per gli utenti di posta elettronica. In questo modo, gli utenti dell'organizzazione non sarà necessario effettuare l'accesso al portale di crittografia per visualizzare le risposte.
  
Per ulteriori informazioni su come creare regole del flusso di posta elettronica di Exchange, vedere [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Invio, risposta e visualizzazione di messaggi di posta elettronica crittografati

Con Office 365 Message Encryption, messaggi di posta elettronica vengono crittografati automaticamente, in base alle regole definite dall'amministratore. Un messaggio di posta elettronica che contiene un messaggio crittografato arriva nella cartella Posta in arrivo del destinatario con un file allegato HTML.
  
Destinatari seguono le istruzioni nel messaggio per aprire l'allegato ed eseguire l'autenticazione utilizzando un account Microsoft o un ufficio o scuola associate a Office 365. Se l'account non dispongono di destinatari, viene indirizzati per creare un database di Microsoft account che verrà consentire loro di accedere a visualizzare il messaggio crittografato. In alternativa, i destinatari possono scegliere per ottenere un passcode occasionale per visualizzare il messaggio. Dopo l'accesso o utilizzando un codice unico passaggio, destinatari possono visualizzare il messaggio crittografato e inviare una risposta crittografata.
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Personalizzare i messaggi crittografati con Office 365 Message Encryption

Amministratore di Exchange Online ed Exchange Online Protection, è possibile personalizzare i messaggi crittografati. Ad esempio, è possibile aggiungere marchio dell'azienda e il logo, specificare un'introduzione e aggiungere dichiarazione di non responsabilità nei messaggi crittografati e nel portale in cui visualizzare i messaggi crittografati i destinatari. Utilizzo dei cmdlet di Windows PowerShell, è possibile personalizzare gli aspetti seguenti dell'esperienza di visualizzazione per i destinatari dei messaggi di posta elettronica crittografati:
  
- Testo introduttivo del messaggio di posta elettronica contenente il messaggio crittografato
    
- Testo della dichiarazione di non responsabilità del messaggio di posta elettronica contenente il messaggio crittografato
    
- Testo portale che apparirà nel messaggio di visualizzazione del portale
    
- Logo che verrà visualizzato nel messaggio di posta elettronica e nel portale di visualizzazione
    
È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.
  
Nel seguente esempio viene illustrato un logo personalizzato per ContosoPharma nell'allegato di posta elettronica:
  
![Esempio di visualizzazione della pagina del messaggio crittografato](media/TA-OME-3attachment2.jpg)
  
 **Per personalizzare i messaggi di posta elettronica di crittografia e il portale di crittografia con marchio dell'organizzazione**
  
1. Connessione a Exchange Online tramite Remote PowerShell, come descritto in [connessione a Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated).
    
2. Utilizzare il cmdlet Set-OMEConfiguration come descritto di seguito: [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) oppure utilizzare la seguente tabella per istruzioni. 
    
   **Opzioni di personalizzazione della crittografia**

|**Per personalizzare questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi di Windows PowerShell**|
|:-----|:-----|
|Testo predefinito che accompagna i messaggi di posta elettronica crittografati  <br/> Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **Esempio:**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **Esempio:**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **Esempio:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Esempio:**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> formati di file supportati: .png, .jpg, .bmp o .tiff  <br/> Dimensione ottimale relativa al file del logo: inferiore a 40 KB  <br/> Dimensioni ottimali relative all'immagine del logo: 170x70 pixel  <br/> |
   
 **Per rimuovere le personalizzazioni del marchio da messaggi di posta elettronica di crittografia e il portale di crittografia**
  
1. Connessione a Exchange Online tramite Remote PowerShell, come descritto in [connessione a Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).
    
2. Utilizzare il cmdlet Set-OMEConfiguration come descritto di seguito: [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). Per rimuovere l'organizzazione del marchio personalizzazioni da DisclaimerText, EmailText, e i valori PortalText, impostare il valore su una stringa vuota `""`. Per tutte le immagini di valori, ad esempio Logo, impostare il valore di `"$null"`.
    
   **Opzioni di personalizzazione della crittografia**

|**Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi di Windows PowerShell**|
|:-----|:-----|
|Testo predefinito che accompagna i messaggi di posta elettronica crittografati  <br/> Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Esempio:**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Esempio:**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Esempio il ripristino sul valore predefinito:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Esempio il ripristino sul valore predefinito:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>Informazioni di servizio per la crittografia messaggi Office 365 legacy prima della versione delle nuove funzionalità OME
<a name="LegacyServiceInfo"> </a>

Nella tabella seguente vengono fornite informazioni tecniche per il servizio Office 365 Message Encryption prima del rilascio delle nuove funzionalità OME.
  
|**Dettagli servizio**|**Descrizione**|
|:-----|:-----|
|Requisiti dei dispositivi client  <br/> |I messaggi crittografati possono essere visualizzati su tutti i dispositivi client, purché l'allegato HTML possa essere aperto in un browser moderno che supporta Post per i moduli.  <br/> |
|Algoritmo di crittografia e conformità FIPS (Federal Information Processing Standards)  <br/> |Crittografia dei messaggi di Office 365 utilizza le chiavi di crittografia stesso come Windows Azure Information Rights Management (IRM) e crittografia modalità 2 (2K tasto per RSA) e 256 bit sono supportati per i sistemi SHA-1. Per ulteriori informazioni sulle modalità di crittografia IRM sottostante, vedere [Modalità di crittografia RMS di Active Directory](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).<br/> |
|Tipi di messaggi supportati  <br/> |Crittografia dei messaggi di Office 365 è supportata solo per gli elementi con un ID di classe messaggio di **IPM. Nota**. Per ulteriori informazioni, vedere [tipi di elementi e classi messaggio](https://msdn.microsoft.com/library/office/ff861573.aspx).<br/> |
|Limiti di dimensione dei messaggi  <br/> |Crittografia dei messaggi di Office 365 possono crittografare i messaggi di fino a 25 MB. Per ulteriori informazioni sui limiti della dimensione dei messaggi, vedere [Exchange Online Limits](http://technet.microsoft.com/library/exchange-online-limits.aspx).<br/> |
|Criteri di conservazione di posta elettronica Exchange Online  <br/> |Exchange Online non memorizza i messaggi crittografati.  <br/> |
|Supporto linguistico per la crittografia dei messaggi di Office 365  <br/> | Crittografia dei messaggi di Office 365 supporta le ingue di Office 365, come segue:  <br/>  Messaggi di posta elettronica in arrivo e i file HTML allegati vengono localizzati in base alle impostazioni della lingua del mittente.  <br/>  Il portale di visualizzazione viene localizzato in base alle impostazioni del browser del destinatario.  <br/>  Il corpo (contenuto) del messaggio crittografato non è localizzato.  <br/> |
|Informazioni sulla privacy per il Portale OME e l'app visualizzatore OME  <br/> |[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) fornisce informazioni dettagliate sulle azioni effettuate da Microsoft con le informazioni private fornite dagli utenti.  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>Domande frequenti su OME legacy
<a name="LegacyServiceInfo"> </a>

Domande sulla crittografia dei messaggi di Office 365? Ecco alcune risposte. Se non è possibile trovare le informazioni necessarie, controllare i forum di community di Office 365 community di [Office 365](http://community.office365.com/en-us/forums/default.aspx).
  
 **D. la mia utenti inviano messaggi di posta elettronica crittografati a destinatari esterni all'organizzazione. È tutto ciò che i destinatari esterni sono state necessarie per leggere e rispondere ai messaggi di posta elettronica vengono crittografati con la crittografia dei messaggi di Office 365?**
  
I destinatari esterni all'organizzazione che ricevono messaggi crittografati di Office 365 possono visualizzarli seguendo uno dei due metodi riportati:
  
- Eseguendo l'accesso con un account Microsoft o un ufficio o della scuola associate a Office 365.
    
- Utilizzando una sola volta passcode.
    
 **D. I messaggi criptati di Office 365 vengono memorizzati sul cloud o sui server Microsoft?**
  
No, i messaggi crittografati vengono mantenuti nel sistema di posta elettronica del destinatario e quando il destinatario apre il messaggio, viene inserito temporaneamente per la visualizzazione nel server di Office 365. I messaggi non vengono archiviati disponibili.
  
 **D. È possibile personalizzare i messaggi di posta elettronica crittografati con il proprio marchio?**
  
Sì. È possibile utilizzare i cmdlet di Windows PowerShell per personalizzare il testo personalizzato che viene visualizzato nella parte superiore dei messaggi di posta elettronica crittografati, il testo della Dichiarazione di non responsabilità e il logo che si desidera utilizzare per il messaggio di posta elettronica e il portale di crittografia. Per i dettagli, vedere [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
 **D. Il servizio richiede una licenza per ogni utente dell'organizzazione?**
  
È necessario disporre di una licenza per ogni utente dell'organizzazione che invia messaggi di posta elettronica crittografati.
  
 **D. I destinatari esterni hanno bisogno di sottoscrizioni?**
  
No, i destinatari esterni non necessitano di una sottoscrizione per leggere o rispondere ai messaggi crittografati. 
  
 **D: come è diverso da Rights Management Services (RMS) di Office 365 Message Encryption?**
  
RMS fornisce funzionalità di protezione dei diritti informazioni per i messaggi di posta elettronica interni dell'organizzazione fornendo modelli predefiniti, ad esempio: non inoltrare e materiale aziendale riservato. Office 365 Message Encryption supporta la posta elettronica la crittografia dei messaggi per i messaggi inviati a destinatari esterni, nonché i destinatari interni.
  
 **D: come è diverso da S/MIME di Office 365 Message Encryption?**
  
S/MIME rappresenta una tecnologia di crittografia sul lato client e necessita di una complessa gestione del certificato e di pubblicazione dell'infrastruttura. La crittografia dei messaggi di Office 365 utilizza le regole di trasporto e non dipende dalla pubblicazione del certificato.
  
 **D. È possibile leggere i messaggi crittografati su dispositivi mobili?**
  
Sì, è possibile visualizzare i messaggi su iOS e Android scaricando le applicazioni del Visualizzatore OME da [Google Riproduci archiviare](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409) e [archiviare App Apple](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409). Aprire l'allegato HTML in app Visualizzatore OME e quindi seguire le istruzioni per aprire il messaggio crittografato. Per altri dispositivi mobili, è possibile aprire l'allegato HTML, purché il client di posta supporta Post per i moduli.
  
 **D. I messaggi di risposta e i messaggi inoltrati vengono crittografati?**
  
Sì. I messaggi di risposta vengono crittografati per tutta la durata del thread.
  
 **D. La crittografia dei messaggi di Office 365 fornisce localizzazione?**
  
Il contenuto della posta elettronica in arrivo viene localizzata in base alle impostazioni di posta elettronica del mittente. Il portale di visualizzazione viene localizzato in base alle impostazioni del browser del destinatario. Tuttavia, il corpo (contenuto) del messaggio crittografato non viene localizzato.
  
 **D. Quale metodo di crittografia viene utilizzato per la crittografia dei messaggi di Office 365?**
  
La crittografia dei messaggi di Office 365 utilizza Rights Management Services (RMS) come infrastruttura di crittografia. Il metodo di crittografia utilizzato dipende da dove ottieni le chiavi RMS utilizzate per crittografare e decrittografare messaggi.
  
- Se si utilizza Microsoft Azure RMS per ottenere i tasti, viene utilizzato modalità crittografia 2. Modalità crittografia 2 è un'implementazione di crittografia AD RMS aggiornata e avanzata. Supporta RSA 2048 per la crittografia e firma e supporta SHA-256 per la firma.
    
- Se si utilizza Active Directory (AD) RMS per ottenere le chiavi, viene utilizzata la Modalità di crittografia 1 o la Modalità di crittografia 2. Il metodo utilizzato dipende dalla distribuzione Active directory (AD) RMS. La Modalità di crittografia 1 è l'implementazione di crittografia AD RMS originale. Questa supporta RSA 1024 per la crittografia e firma e SHA-1 per firma. Questa modalità continua ad essere supportata da tutte le versioni correnti di RMS.
    
Per ulteriori informazioni, vedere [Modalità di crittografia RMS di Active Directory](http://go.microsoft.com/fwlink/p/?LinkId=398616).
  
 **D. Perché alcuni messaggi crittografati risultano provenienti da Office365@messaging.microsoft.com?**
  
Quando una risposta crittografata viene inviata dal portale di crittografia oppure tramite l'app Visualizzatore Crittografia messaggi di Office 365, l'indirizzo del messaggio di posta elettronica da inviare è impostato su Office365@messaging.microsoft.com perché il messaggio crittografato viene inviato tramite un endpoint di Microsoft. In questo modo si evita che i messaggi crittografati vengano contrassegnati come posta indesiderata. Il nome visualizzato nel messaggio di posta elettronica e l'indirizzo all'interno del portale di crittografia non vengono modificati a causa di questa etichetta. Inoltre, tale etichetta si applica solo ai messaggi inviati tramite il portale, non tramite altri client di posta elettronica.
  
 **D: perché un sottoscrittore Exchange Hosted Encryption (EHE). Dove trovare ulteriori informazioni sull'aggiornamento alla crittografia dei messaggi Office 365?**
  
Sono stati aggiornati tutti i clienti EHE alla crittografia dei messaggi di Office 365. Per ulteriori informazioni, visitare il [Centro di aggiornamento di Exchange Hosted Encryption](http://go.microsoft.com/fwlink/p/?LinkID=511077).
  
 **D necessario aprire alcun URL, IP indirizzi o le porte firewall dell'organizzazione per supportare la crittografia dei messaggi di Office 365?**
  
Sì. È necessario aggiungere degli URL per Exchange Online per consentire all'elenco della tua organizzazione di abilitare l'autenticazione per i messaggi criptati di crittografia dei messaggi di Office 365. Per un elenco di URL di Exchange Online, vedi [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx).
  
 **D. A quanti destinatari posso inviare un messaggio crittografato tramite Office 365?**
  
Numero massimo di destinatari per messaggio crittografato è in base al numero di caratteri nel campo **a** del messaggio. Se combinato (dopo l'espansione della lista di distribuzione), gli indirizzi dei destinatari nel campo **a** non devono superare 11,980 caratteri. Poiché gli indirizzi di posta elettronica possono variare in caratteri, non esiste alcun numero massimo di destinatari standard per un singolo messaggio crittografato. 
  
 **D. È possibile revocare un messaggio inviato a un particolare destinatario?**
  
No. Dopo l'invio non sarà possibile revocare un messaggio a una determinata persona.
  
 **D. Posso visualizzare un report dei messaggi crittografati che sono stati ricevuti e letti?**
  
Non vi è un rapporto che mostra se è stato mai visualizzato un messaggio crittografato, ma non vi siano disponibili che è possibile utilizzare per determinare il numero di messaggi corrispondenti a una regola di trasporto specifica, ad esempio report di Office 365.
  
 **D. Come vengono utilizzate da Microsoft le informazioni fornite tramite il Portale OME e l'app visualizzatore OME?**
  
Per informazioni dettagliate sugli elementi Microsoft e non eseguire con le informazioni personali, l' [informativa sulla privacy di portale di crittografia di messaggistica di Office 365](protected-message-viewer-portal-privacy-statement.md) . 
  

