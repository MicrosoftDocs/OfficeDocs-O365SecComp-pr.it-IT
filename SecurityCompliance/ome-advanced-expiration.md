---
title: Impostare una data di scadenza per la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Con le funzionalità di crittografia dei messaggi avanzate di Office 365 in cima a Office 365 Message Encryption (OME), è possibile estendere la sicurezza della posta elettronica impostando una data di scadenza nei messaggi di posta elettronica tramite un modello personalizzato.
ms.openlocfilehash: c1fb876724bed970095e950906500ff551d93cee
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506722"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Impostare una data di scadenza per la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365

La crittografia avanzata dei messaggi di Office 365 è disponibile nella parte superiore della crittografia messaggi di Office 365 in alcuni abbonamenti. La crittografia avanzata dei messaggi è inclusa in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 e Office 365 Education a5. Se nell'organizzazione è presente un abbonamento a Office 365 che non include la crittografia avanzata dei messaggi di Office 365, è possibile acquistare la crittografia avanzata del messaggio come componente aggiuntivo con la conformità E5 della SKU per la conformità avanzata.

È possibile utilizzare la scadenza dei messaggi nei messaggi di posta elettronica inviati dagli utenti ai destinatari esterni che utilizzano il portale OME per accedere ai messaggi di posta elettronica crittografati. È possibile forzare i destinatari a utilizzare il portale OME per visualizzare e rispondere ai messaggi di posta elettronica crittografati inviati dall'organizzazione utilizzando un modello personalizzato che specifichi una data di scadenza in Windows PowerShell.

In qualità di amministratore globale di O365, quando si applica il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione di Office 365, è anche possibile specificare una scadenza per questi messaggi di posta elettronica. Con la crittografia avanzata dei messaggi di Office 365, è possibile creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione. Se si utilizza un modello, è possibile controllare la durata di accesso dei destinatari alla posta inviata dagli utenti.

Quando un utente finale riceve la posta con un set di date di scadenza, l'utente Visualizza la data di scadenza nel messaggio di posta elettronica del wrapper. Se un utente tenta di aprire un messaggio di posta elettronica scaduto, viene visualizzato un messaggio di errore nel portale OME.

Solo i messaggi di posta elettronica ai destinatari esterni sono scaduti.

Grazie alla crittografia avanzata dei messaggi di Office 365, ogni volta che si applica il marchio personalizzato, Office 365 applica il wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello. Inoltre, la scadenza può essere utilizzata solo se viene utilizzato il marchio personalizzato.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Creare un modello di personalizzazione personalizzato per forzare la scadenza della posta tramite PowerShell

1. [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) utilizzando un account con autorizzazioni di amministratore globale nel tenant di Office 365.

2. Eseguire il cmdlet New-OMEConfiguration.

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

Dove:

- Identity è il nome del modello personalizzato.

- ExternalMailExpiryInDays identifica il numero di giorni in cui si desidera che i destinatari siano in grado di mantenere la posta prima della scadenza. È possibile utilizzare qualsiasi valore compreso tra 1 e 730 giorni.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365

- [Crittografia avanzata dei messaggi di Office 365](ome-advanced-message-encryption.md)

- [Revoca dei messaggi di posta elettronica crittografati da Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md)

- [Descrizione del servizio criteri di conformità e del messaggio](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)