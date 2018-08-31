---
title: Impedire la posta elettronica vengono contrassegnati come posta indesiderata in Office 365 ed Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 74aaade0-efc0-46ac-b949-f2d1d59256fa
description: Suggerimenti per gli amministratori di Office 365 evitare una buona posta elettronica contrassegnato come posta indesiderata da viene messo in quarantena come falso positivo. Personalizzare dell'elenco indirizzi attendibili e altre opzioni per evitare una buona posta elettronica contrassegnato come posta indesiderata.
ms.openlocfilehash: 42b27d237592e95e6d175ab335959bc82269c0f7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530286"
---
# <a name="prevent-email-from-being-marked-as-spam-in-office-365-and-exchange-online-protection"></a>Impedire la posta elettronica vengono contrassegnati come posta indesiderata in Office 365 ed Exchange Online Protection

Gli amministratori di Exchange Online o Exchange Online Protection (EOP) con le credenziali di accesso appropriato possono utilizzare la procedura seguente per contribuire a garantire che un messaggio di posta elettronica in uscita tramite il servizio non è contrassegnato come posta indesiderata.
  
Può essere frustrante disporre di posta elettronica legittimo, buona messi in quarantena o bloccati come posta indesiderata e di destinazione in una cartella di quarantena. È possibile utilizzare un elenco dei mittenti attendibili o una regola di flusso di posta elettronica per ignorare il filtro posta indesiderata e impedire che venga contrassegnato come posta indesiderata i messaggi di posta elettronica valido. Quando un messaggio in modo non corretto è contrassegnato come posta indesiderata dal filtro posta indesiderata, viene definito un falso positivo. Il filtro posta indesiderata di Office 365 sono inoltre disponibili alcune opzioni che gli utenti finali possono personalizzare per poter prevenire falsi positivi.
  
Se si sta cercando assistenza posta negativa false, vale a dire un messaggio di posta indesiderata che ottiene quando non devono, consultare i suggerimenti di [posta elettronica di blocco della posta indesiderata con il filtro posta indesiderata di Office 365 per evitare problemi negativi false](block-email-spam-to-prevent-false-negatives.md).
  
## <a name="eop-only-customers-use-directory-synchronization"></a>I clienti EOP sola: utilizzare la sincronizzazione delle directory

EOP è una basata su cloud filtro della posta elettronica servizio che consente di proteggere l'organizzazione da posta indesiderata e malware. Se si dispongono delle cassette postali in Office 365, automaticamente protetti da EOP perché fa parte del servizio. 
  
Se si è un cliente solo EOP, vale a dire sottoscrivere il servizio EOP per l'utilizzo con il Server di Exchange locale, necessario sincronizzare le impostazioni utente con il servizio utilizzando la sincronizzazione delle directory. In questo modo assicura che i mittenti attendibili gli elenchi vengono rispettati da EOP. Per ulteriori informazioni, vedere "Utilizzare la sincronizzazione delle directory per gestire gli utenti di posta" in [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).
  
## <a name="prevent-false-positive-email-by-using-the-connection-filters-ip-allow-list"></a>Impedire falso positivo messaggio di posta elettronica utilizzando la connessione elenco indirizzi IP del filtro consentiti

Se si rileva che verrà sempre spostato posta elettronica del mittente per le cartelle di posta indesiderata nella propria organizzazione, è possibile aggiungere l'indirizzo IP del mittente del messaggio di posta elettronica per IP del filtro connessioni elenco Consenti. In genere, ciò impedisce false positive risposte per questo mittente per tutti i destinatari all'interno dell'organizzazione. L'eccezione si verifica quando un utente attivata l'opzione "Safe vengono elencati solo: posta in arrivo devono essere recapitata solo la posta proveniente da utenti o i domini inclusi nell'elenco Mittenti attendibili o destinatari attendibili" in Outlook e non aggiunge il mittente all'elenco Mittenti attendibili. Per informazioni su tale opzione viene sottoposto a override, vedere [risoluzione dei problemi: un messaggio a trovarsi nella cartella posta indesiderata anche se EOP ha contrassegnato il messaggio come non indesiderato](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam).
  
 **Per aggiungere un indirizzo IP per la connessione elenco indirizzi IP del filtro consentiti**
  
1. Ottenere l'intestazione di un messaggio inviato dal mittente che si desidera consentire. È possibile ottenere questo risultato dal proprio client di posta elettronica, ad esempio Outlook o Outlook sul Web, come descritto [nell'Analizzatore dell'intestazione di messaggio](https://go.microsoft.com/fwlink/p/?LinkId=306583).
    
2. Cercare manualmente l'indirizzo IP del tag di CIP nell'intestazione X-Forefront-Antispam-Report o utilizzando la scheda **Messaggio analizzatore** di [Analizzatore connettività remota](https://testconnectivity.microsoft.com/?tabid=mha).
    
3. Aggiungere l'indirizzo IP l'indirizzo IP elenco Consenti seguendo i passaggi descritti in "Utilizzare EAC per modificare il criterio di filtro connessioni predefinito" in [configurare i criteri di filtro di connessione](https://go.microsoft.com/fwlink/?LinkId=534132).
    
## <a name="prevent-false-positive-email-by-configuring-spam-filter-policies"></a>Impedire falso positivo messaggio di posta elettronica mediante la configurazione di criteri di filtro da posta indesiderata

È possibile aggiungere domini o agli indirizzi di posta elettronica singolo all'elenco Consenti seguendo i passaggi di [configurazione dei criteri di filtro posta indesiderata](https://go.microsoft.com/fwlink/?LinkID=534136).
  
## <a name="review-your-advanced-spam-filter-policies"></a>Esaminare i criteri del filtro posta indesiderata

Se si dispone di limitazioni particolari impostare un criterio di filtro posta indesiderata, ad esempio, se un intero dominio bloccato, è consigliabile rivedere per verificare se si sta causando falsi positivi. Vedere [configurazione dei criteri di filtro posta indesiderata](https://go.microsoft.com/fwlink/?LinkId=534136)e disattivare ulteriori [Opzioni di filtro posta indesiderata](https://go.microsoft.com/fwlink/?LinkId=534137) che possono causare messaggi deve essere contrassegnato come posta indesiderata. 
  
## <a name="help-your-end-users-create-a-safe-sender-list-to-prevent-good-email-from-being-marked-as-spam"></a>Consente agli utenti finali di creare un elenco di mittenti attendibili per impedire che una buona posta elettronica vengono contrassegnati come posta indesiderata
<a name="BKMK_email-user-help-safelist"> </a>

Chiedere agli utenti di aggiungere indirizzi da mittenti attendibili all'elenco Mittenti attendibili di [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) o [Outlook sul Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). Per iniziare a Outlook sul Web, fare clic su **Impostazioni**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Opzioni** \> **Blocca o Consenti**. Nel diagramma seguente è illustrato un esempio di aggiunta di un elemento a un elenco dei mittenti attendibili.
  
![Aggiunta di un mittente protetto in Outlook Web App](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
EOP rispetta mittenti attendibili e destinatari ma non domini attendibili degli utenti. Si tratta indipendentemente dal fatto che il dominio viene aggiunto tramite Outlook sul Web oppure in Outlook e sincronizzati con sincronizzazione delle Directory.
  
## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>Risoluzione dei problemi: Un messaggio a trovarsi nella cartella posta indesiderata anche se EOP ha contrassegnato il messaggio come non indesiderato
<a name="TroubleshootingJunkEOPNonSpam"> </a>

Se gli utenti hanno l'opzione in Outlook abilitati per "Safe vengono elencati solo: posta in arrivo devono essere recapitata solo la posta proveniente da utenti o i domini inclusi nell'elenco Mittenti attendibili o destinatari attendibili", quindi tutta la posta elettronica verrà inoltrate alla cartella posta indesiderata per un mittente, a meno che il mittente è incluso il contrassegna elenco dei mittenti attendibili di pient. Questa operazione verrà eseguita indipendentemente dall'utente se EOP contrassegna un messaggio come posta non indesiderata o se è stata configurata una regola di EOP per contrassegnare un messaggio come posta non indesiderata.
  
È possibile disabilitare l'opzione solo elenchi indirizzi attendibili per gli utenti di Outlook seguendo le istruzioni riportate in [Outlook: impostazione dei criteri per disabilitare l'interfaccia utente di posta elettronica indesiderata e meccanismo di filtro](https://support.microsoft.com/en-us/kb/2180568).
  
Se si visualizza il messaggio di Outlook sul Web, ci sarà un suggerimento di sicurezza gialla che indica che il messaggio nella cartella posta indesiderata poiché il mittente non è presente nell'elenco Mittenti attendibili del destinatario.
  
Se si esamina l'intestazione del messaggio, è possibile che includa il timestamp skn (indirizzi IP consentiti o consentire ETR) o SFV:NSPM (non spam), ma il messaggio è ancora inserito nella cartella posta indesiderata dell'utente. Non è nell'intestazione del messaggio che indica che l'utente dispone "Solo elenchi indirizzi attendibili" abilitato. Infatti, l'opzione "Solo elenchi indirizzi attendibili" impostato dagli utenti in Outlook ha priorità sull'impostazione di EOP. 
  
 **Per verificare il motivo per cui un messaggio da un mittente sicuro è contrassegnato come non indesiderato nell'intestazione del messaggio, ma ancora terminazioni nella cartella posta indesiderata dell'utente**
  
1. Per informazioni su come connettersi a Exchange Online PowerShell, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). 
    
2. Eseguire il comando seguente per visualizzare le impostazioni di configurazione di posta indesiderata dell'utente:
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

    Se TrustedListsOnly è impostata su True, significa che questa impostazione è attivata. Se ContactsTrusted è impostata su True, significa che l'utente considera attendibili i contatti e mittenti attendibili. Il TrustedSendersAndDomains Elenca il contenuto dell'elenco Mittenti attendibili dell'utente.
    
## <a name="still-need-help"></a>Ulteriore assistenza?
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[![Ottenere assistenza dai forum della community di Office 365](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Amministratori: Accedere e creare una richiesta di assistenza](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Amministratori: Chiama il supporto](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  
## <a name="see-also"></a>Vedere anche
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[Panoramica del filtro posta indesiderata](https://support.office.com/article/5AE3EA8E-CF41-4FA0-B02A-3B96E21DE089)
  
[Blocca o Consenti (impostazioni di posta indesiderata)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](block-email-spam-to-prevent-false-negatives.md)

