---
title: Business intelligence di flusso di posta elettronica in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: "In genere si utilizza un connettore per instradare i messaggi dalla organizzazione Office 365 per locale ambiente di messaggistica. È inoltre possibile utilizzare un connettore per instradare i messaggi da Office 365 a un'organizzazione partner. Quando Office 365 non è in grado di distribuire questi messaggi attraverso il connettore, sta accodate in Office 365. "
ms.openlocfilehash: 495d73524afb3ab3a34fd2f1f5f4cd747481f9d8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027623"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Business intelligence di flusso di posta elettronica in Office 365
  
In genere, si usa un connettore per instradare i messaggi dall'organizzazione di Office 365 all'ambiente di messaggistica locale. È anche possibile usare un connettore per instradare i messaggi da Office 365 a un'organizzazione partner. Quando Office 365 non è in grado di recapitare tali messaggi attraverso il connettore, questi ultimi vengono messi in coda in Office 365. Office 365 proverà a ripetere il recapito di ogni messaggio per 48 ore. Dopo 48 ore, il messaggio nella coda scade e viene inviato di nuovo al mittente originale tramite un rapporto di mancato recapito (detto anche NDR o notifica di mancato recapito).
  
Office 365 genera un errore quando un messaggio non può essere recapitato utilizzando un connettore. In questo argomento sono descritti gli errori più comuni e le relative soluzioni. Nell'insieme, gli errori relativi alle code e alle notifiche dei messaggi non recapitabili inviati tramite il connettore sono noti come intelligence del flusso di posta.
  
 **Sommario**
  
- [Codice errore: 450 4.4.312 Query DNS non riuscita](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [Codice errore: 450 4.4.315 Timeout della connessione](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [Codice errore: 450 4.4.316 Connessione rifiutata](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [Codice errore: 450 4.4.318 Connessione interrotta improvvisamente](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [Codice errore: 450 4.7.320 Convalida del certificato non riuscita](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a>Codice errore: 450 4.4.312 Query DNS non riuscita
<a name="ErrorCode44312"> </a>

In genere questo errore indica che Office 365 ha tentato di connettersi allo smart host specificato nel connettore, ma la query DNS di ricerca degli indirizzi IP dello smart host ha avuto esito negativo. Alcune possibili cause di questo errore:
  
- Si è verificato un errore relativo al servizio di hosting DNS del proprio dominio (la terza parte che gestisce i server dei nomi autorevoli per il dominio).
    
- Di recente, il dominio è scaduto e di conseguenza il record MX non può essere recuperato.
    
- Il record MX del dominio è stato recentemente modificato e i server DNS di Office 365 hanno ancora le informazioni DNS memorizzate in precedenza per il dominio.
    
È necessario risolvere il problema del DNS insieme agli addetti del servizio di hosting DNS.
  
Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
  
## <a name="error-code-450-44315-connection-timed-out"></a>Codice errore: 450 4.4.315 Timeout della connessione
<a name="ErrorCode44315"> </a>

In genere, ciò indica che Office 365 non è riuscito a connettersi al server di messaggistica di destinazione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:
  
- Il server di messaggistica locale è inattivo.
    
- Si è verificato un errore relativo alle impostazione dello smart host del connettore, quindi Office 365 prova a connettersi all'indirizzo IP sbagliato.
    
Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni. Ad esempio, se il flusso di posta non presenta problemi e non sono state modificate le impostazioni del connettore, è necessario controllare l'ambiente di messaggistica locale al fine di verificare se il server è inattivo oppure se sono state apportate modifiche all'infrastruttura di rete (ad esempio, sono stati modificati i provider dei servizi Internet e di conseguenza si hanno indirizzi IP diversi).
  
Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
  
## <a name="error-code-450-44316-connection-refused"></a>Codice errore: 450 4.4.316 Connessione rifiutata
<a name="ErrorCode44316"> </a>

In genere, questo errore indica che Office 365 ha riscontrato un errore di connessione quando ha provato a connettersi al server di messaggistica di destinazione. Una delle probabili cause di questo errore è la presenza di un firewall che blocca le connessioni dagli indirizzi IP di Office 365. In alternativa, questo errore potrebbe dipendere dalla progettazione se il sistema di messaggistica locale è stato migrato completamente in Office 365 ed è stato arrestato l'ambiente di messaggistica locale.
  
- Se si dispone di più cassette postali nell'ambiente locale, è necessario modificare le impostazioni del firewall per consentire connessioni dagli indirizzi IP di Office 365 sulla porta TCP 25 ai server di messaggistica locali. Per visualizzare un elenco degli indirizzi IP di Office 365, vedere [URL e intervalli di indirizzi IP per Office 365](https://go.microsoft.com/fwlink/p/?linkid=228887).
    
- Se non devono essere recapitati più messaggi nell'ambiente locale, fare clic su **Correggi ora** nell'avviso affinché Office 365 possa rifiutare immediatamente i messaggi con destinatari non validi. Questo consente di ridurre il rischio di superare la quota dell'organizzazione per i destinatari non validi, che possono compromettere il recapito dei messaggi normali. In alternativa, è possibile utilizzare le istruzioni seguenti per risolvere manualmente il problema: 
    
  - Disabilitare o eliminare il connettore da Office 365 nell'ambiente locale: interfaccia di amministrazione di Office 365 \> **Interfacce di amministrazione** \> **Exchange** \> **Flusso di posta** \> **Connettori** \> selezionare il connettore con il valore **From** come **Office 365** e il valore **To** come **Server di posta elettronica dell'organizzazione**. Eliminare il connettore facendo clic su **Elimina**![Icona Elimina](media/ITPro-EAC-DeleteIcon.png) oppure disabilitare il connettore facendo clic su **Modifica**![Icona Modifica](media/ITPro-EAC-EditIcon.png) e deselezionando **Abilita**.
    
  - Modificare il dominio accettato in Office 365 che è associato all'ambiente di messaggistica locale da **Inoltro interno** ad **Autorevole**. Per istruzioni, vedere [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).
    
    **Nota**: hanno in genere, le modifiche tra 30 minuti e un'ora per rendere effettive. Dopo un'ora, verificare che non viene più visualizzato l'errore.
    
Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.
<a name="ErrorCode44317"> </a>

In genere, questo errore indica che Office 365 ha stabilito la connessione al server di messaggistica di destinazione, ma il server ha risposto con un errore immediato oppure non ha soddisfatto i requisiti di connessione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:
  
- Il server di messaggistica di destinazione ha generato l'errore "Servizio non disponibile", che indica che il server non riesce a mantenere la comunicazione con Office 365.
    
- Il connettore viene configurato in modo che necessiti di TLS, ma il server di messaggistica di destinazione non supporta TLS.
    
Verificare le impostazioni di TLS e dei certificati nei server di messaggistica locale e le impostazioni TLS sul connettore.
  
Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Codice errore: 450 4.4.318 Connessione interrotta improvvisamente
<a name="ErrorCode44318"> </a>

In genere, questo errore indica che Office 365 non riesce a comunicare con l'ambiente di messaggistica locale dell'utente, quindi la connessione viene interrotta. Alcune possibili cause di questo errore:
  
- Il firewall utilizza le regole di verifica del pacchetto SMTP e tali regole non funzionano correttamente.
    
- Il server di messaggistica locale non funziona correttamente (ad esempio, il servizio si blocca, si arresta in modo anomalo oppure rallenta le risorse del sistema) e causa il timeout del server e l'interruzione della connessione a Office 365.
    
- Sono presenti errori di rete tra l'ambiente locale e Office 365. Se il problema persiste, rivolgersi al team di rete per risolvere il problema.
    
Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni.
  
Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
  
## <a name="error-code-450-47320-certificate-validation-failed"></a>Codice errore: 450 4.7.320 Convalida del certificato non riuscita
<a name="ErrorCode47320"> </a>

In genere, questo errore indica che Office 365 ha riscontrato un errore quando ha provato a convalidare il certificato del server di messaggistica di destinazione. Nei dettagli dell'errore è riportata una sua spiegazione. Ad esempio:
  
- Certificato scaduto
    
- Mancata corrispondenza oggetto certificato
    
- Certificato non più valido
    
Correggere il certificato o il connettore in modo che i messaggi nella coda di Office 365 possano essere recapitati.
  
Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
  
## <a name="other-error-codes"></a>Altri codici errore
<a name="sectionSection6"> </a>

Office 365 non riesce a recapitare i messaggi al server di messaggistica partner o locale. Utilizzare le informazioni **Server di destinazione** nell'errore per esaminare l'errore nel proprio ambiente o per modificare il connettore in presenza di un errore di configurazione. 
  
Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
  

