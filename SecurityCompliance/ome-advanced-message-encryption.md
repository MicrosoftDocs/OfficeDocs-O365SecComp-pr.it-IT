---
title: Crittografia avanzata dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: La crittografia avanzata dei messaggi in Office 365 consente alle organizzazioni di soddisfare gli obblighi di conformità abilitando gli amministratori a scadere e revocare l'accesso tramite un portale Web di Office 365 ai messaggi di posta elettronica crittografati.
ms.openlocfilehash: a775803a8d2678441f319c0145e96e7d19c26f7e
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506723"
---
# <a name="office-365-advanced-message-encryption"></a>Crittografia avanzata dei messaggi di Office 365

La crittografia avanzata dei messaggi di Office 365 è disponibile nella parte superiore della crittografia messaggi di Office 365 in alcuni abbonamenti. La crittografia avanzata dei messaggi è inclusa in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 e Office 365 Education a5. Se nell'organizzazione è presente un abbonamento a Office 365 che non include la crittografia avanzata dei messaggi di Office 365, è possibile acquistare la crittografia avanzata del messaggio come componente aggiuntivo con la conformità E5 della SKU per la conformità avanzata.

Questo articolo fa parte di una serie più ampia di articoli sulla [crittografia dei messaggi di Office 365](ome.md).

La crittografia avanzata dei messaggi in Office 365 consente ai clienti di soddisfare gli obblighi di conformità che richiedono controlli più flessibili su destinatari esterni e l'accesso ai messaggi di posta elettronica crittografati. Con la crittografia avanzata dei messaggi in Office 365, è possibile controllare i messaggi di posta elettronica riservati condivisi all'esterno dell'organizzazione con criteri automatici. Questi criteri possono essere configurati per identificare tipi di informazioni riservate, ad esempio i dati personali, finanziari o di integrità, oppure è possibile utilizzare parole chiave per migliorare la protezione. Dopo aver configurato i criteri, è necessario associare criteri a modelli di posta elettronica personalizzati e quindi aggiungere una data di scadenza per il controllo aggiuntivo per i messaggi di posta elettronica che soddisfano i criteri. Gli amministratori possono inoltre controllare ulteriori messaggi di posta elettronica crittografati accessibili esternamente tramite un portale web sicuro, revocando l'accesso alla posta in qualsiasi momento.

È possibile impostare solo una scadenza e revocare i messaggi di posta elettronica inviati a destinatari esterni.

Grazie alla crittografia avanzata dei messaggi di Office 365, ogni volta che si applica il marchio personalizzato, Office 365 applica il wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello. Inoltre, la scadenza può essere utilizzata solo se viene utilizzato il marchio personalizzato. È possibile revocare solo i messaggi ricevuti tramite il portale.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Iniziare a usare la crittografia avanzata dei messaggi di Office 365

Negli argomenti seguenti viene descritto come configurare e utilizzare la crittografia avanzata dei messaggi.

L'organizzazione deve disporre di un abbonamento che include la crittografia avanzata dei messaggi di Office 365. Per informazioni dettagliate sulle sottoscrizioni supportate, vedere [Message Policy and Compliance Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Configurare le nuove funzionalità di crittografia dei messaggi di Office 365 se non sono già state configurate per sfruttare le funzionalità avanzate di crittografia dei messaggi, che forniscono una protezione aggiunta oltre ai messaggi crittografati condivisi esternamente. Se non è stata configurata la crittografia dei messaggi di Office 365, vedere [configurare le nuove funzionalità di crittografia dei messaggi di office 365](set-up-new-message-encryption-capabilities.md).

[Impostare una data di scadenza per la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365](ome-advanced-expiration.md). Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione con criteri automatici che migliorano la protezione, in scadenza l'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati

[Revocare la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365](revoke-ome-encrypted-mail.md). Controllare i messaggi di posta elettronica sensibili condivisi all'esterno dell'organizzazione e migliorare la protezione revocando l'accesso tramite un portale web sicuro ai messaggi di posta elettronica crittografati.  