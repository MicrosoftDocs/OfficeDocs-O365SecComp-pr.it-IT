---
title: Business intelligence di flusso di posta elettronica in Office 365
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Gli amministratori possono venire a conoscenza i codici di errore che sono associati a recapito dei messaggi utilizzando i connettori in Office 365 (noto anche come intelligence del flusso di posta elettronica).
ms.openlocfilehash: 9f27dfd4c265eb62028d68c27764183202692ef4
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "28327088"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Business intelligence di flusso di posta elettronica in Office 365

Utilizzato in genere, un connettore per instradare i messaggi di posta elettronica dall'organizzazione Office 365 per l'ambiente di posta elettronica locale. È inoltre possibile utilizzare un connettore per instradare i messaggi da Office 365 a un'organizzazione partner. Quando Office 365 non è in grado di distribuire questi messaggi attraverso il connettore, sta accodate in Office 365. Office 365 continuerà a tentativi di recapito per ogni messaggio per 48 ore. Dopo 48 ore, scade dopo il messaggio in coda e il messaggio verrà restituito al mittente originale in un rapporto di mancato recapito (noto anche come un messaggio di rapporto di mancato recapito o di rimbalzo).

Office 365 genererà un errore quando un messaggio non possono essere inviato tramite un connettore. In questo argomento vengono descritti gli errori più comuni e le relative soluzioni. Collettivamente, gli errori di Accodamento messaggi e le notifiche per i messaggi non recapitati inviati tramite un connettore è noto come _Business intelligence di flusso di posta elettronica_.

## <a name="error-code-450-44312-dns-query-failed"></a>Codice errore: 450 4.4.312 Query DNS non riuscita

Questo errore indica in genere, che Office 365 ha tentato di connettersi a quest ' ultimo specificato nel connettore, ma la query DNS per individuare gli indirizzi IP dell'host smart non è riusciti. Le possibili cause di questo errore sono:

- Si è verificato un errore relativo al servizio di hosting DNS del proprio dominio (la terza parte che gestisce i server dei nomi autorevoli per il dominio).

- Di recente, il dominio è scaduto e di conseguenza il record MX non può essere recuperato.

- Il record MX del dominio è stato recentemente modificato e i server DNS di Office 365 hanno ancora le informazioni DNS memorizzate in precedenza per il dominio.

### <a name="how-do-i-fix-error-code-450-44312"></a>Come è possibile risolvere il codice di errore 450 4.4.312?

- Utilizzare il servizio di hosting DNS per individuare e risolvere il problema con il proprio dominio.

- Se l'errore è dall'organizzazione partner (ad esempio, un 3rd parti cloud provider di servizi), contattare il partner per risolvere il problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Codice errore: 450 4.4.315 Timeout della connessione

In genere, ciò significa che Office 365 non è possibile connettersi al server di posta elettronica di destinazione. I dettagli dell'errore verranno illustrato il problema. Per esempio:

- Il server di posta elettronica locale è inattivo.

- Si è verificato un errore relativo alle impostazione dello smart host del connettore, quindi Office 365 prova a connettersi all'indirizzo IP sbagliato.

### <a name="how-do-i-fix-error-code-450-44315"></a>Come è possibile risolvere il codice di errore 450 4.4.315?

- Scoprire di quali scenario si applica a un utente e apportare le correzioni necessarie. Ad esempio, se il flusso della posta è stata funzioni correttamente e non è stato modificato le impostazioni dei connettori, è necessario controllare l'ambiente di posta elettronica locale per verificare se il server è inattivo o se sono state apportate modifiche all'infrastruttura di rete (ad esempio, siano state modificate provider di servizi internet, in modo che ora è indirizzi IP diversi).

- Se l'errore è dall'organizzazione partner (ad esempio, un 3rd parti cloud provider di servizi), contattare il partner per risolvere il problema.

## <a name="error-code-450-44316-connection-refused"></a>Codice errore: 450 4.4.316 Connessione rifiutata

Questo errore indica in genere, che Office 365 si è verificato un errore di connessione quando si è tentato di connettersi al server di posta elettronica di destinazione. Una possibile causa di questo errore è che il firewall blocca le connessioni da indirizzi IP di Office 365. In alternativa, questo errore può essere per impostazione predefinita se completamente eseguita la migrazione locale del sistema di posta elettronica a Office 365 e arrestare l'ambiente di posta elettronica locale.

### <a name="how-do-i-fix-error-code-450-44316"></a>Come è possibile risolvere il codice di errore 450 4.4.316?

- Se si dispongono delle cassette postali locali nell'ambiente in uso, è necessario modificare le impostazioni del firewall per consentire le connessioni da indirizzi IP di Office 365 sulla porta TCP 25 per i server di posta elettronica locale. Per un elenco di indirizzi IP di Office 365, vedere [Office 365 URL e intervalli di indirizzi IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).

- Se non devono essere recapitati più messaggi nell'ambiente locale, fare clic su **Correggi ora** nell'avviso affinché Office 365 possa rifiutare immediatamente i messaggi con destinatari non validi. Questo consente di ridurre il rischio di superare la quota dell'organizzazione per i destinatari non validi, che possono compromettere il recapito dei messaggi normali. In alternativa, è possibile utilizzare le istruzioni seguenti per risolvere manualmente il problema:

  - Nell' [interfaccia di amministrazione di Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disattivare o eliminare il connettore che invia messaggio di posta elettronica da Office 365 all'ambiente di posta elettronica locale:

    1. In EAC, andare a **flusso di posta** \> **connettori**.

    2. Selezionare il connettore con il valore **di** **Office 365** e il valore **per** **il server di posta elettronica dell'organizzazione** ed effettuare una delle operazioni seguenti:

       - Fare clic su **Elimina** per eliminare il connettore ![sull'icona Rimuovi](media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Disabilitare il connettore, scegliendo **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) e deselezione **attivarlo**.

  - Modificare il dominio accettato in Office 365 di cui è associato l'ambiente di posta elettronica locale di **Inoltro interno** su **autorevole**. Per ulteriori informazioni, vedere [Manage domini accettati in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).

  **Nota**: hanno in genere, le modifiche tra 30 minuti e un'ora per rendere effettive. Dopo un'ora, verificare che non viene più visualizzato l'errore.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.

Questo errore indica in genere, Office 365 connessi al server di posta elettronica di destinazione, ma il server ha restituito un errore immediato o non soddisfa i requisiti di connessione. I dettagli dell'errore verranno illustrato il problema. Per esempio:

- Server di posta elettronica di destinazione ha restituito un errore "Servizio non disponibile", che indica il server è in grado di mantenere la comunicazione con Office 365.

- Il connettore è configurato per richiedere TLS, ma il server di posta elettronica di destinazione non supporta TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Come è possibile risolvere il codice di errore 450 4.4.317?

- Verificare le impostazioni di TLS e dei certificati sui server di posta elettronica locale e le impostazioni di TLS sul connettore.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Codice errore: 450 4.4.318 Connessione interrotta improvvisamente

Questo errore indica in genere, che Office 365 è problemi nelle comunicazioni con l'ambiente di posta elettronica locale, in modo che la connessione è stata interrotta. Le possibili cause di questo errore sono:

- Il firewall utilizza le regole di verifica del pacchetto SMTP e tali regole non funzionano correttamente.

- Il server di posta elettronica locale non lavorativi correttamente (ad esempio, servizio blocchi, arresti anomali o risorse di sistema), che ha causato il server non scada e chiudere la connessione a Office 365.

- Sono presenti errori di rete tra l'ambiente locale e Office 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Come è possibile risolvere il codice di errore 450 4.4.318?

- Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni.

- Se il problema è dovuto a problemi di rete tra l'ambiente locale e Office 365, rivolgersi al team di rete per risolvere il problema.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Codice errore: 450 4.7.320 Convalida del certificato non riuscita

Questo errore indica in genere, che Office 365 si è verificato un errore durante il tentativo di convalidare il certificato del server di posta elettronica di destinazione. I dettagli dell'errore verranno illustrato l'errore. Per esempio:

- Certificato scaduto

- Mancata corrispondenza oggetto certificato

- Certificato non più valido

### <a name="how-do-i-fix-error-code-450-47320"></a>Come è possibile risolvere il codice di errore 450 4.7.320?

- Correggere il certificato o le impostazioni del connettore in modo che i messaggi in Office 365 in coda da recuperare.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="other-error-codes"></a>Altri codici errore

Office 365 è difficoltà il recapito dei messaggi in locale o server di posta elettronica di partner. Utilizzare le informazioni sul **server di destinazione** nel messaggio di errore per esaminare il problema nell'ambiente in uso o modificare il connettore se si verifica un errore di configurazione. 

Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
