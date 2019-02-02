---
title: Confronto tra le versioni di Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: Consente di descrivere le differenze nelle caratteristiche viene recapitate con diverse versioni di Office 365 Message Encryption anche il modo in cui i due continuano a lavorare contemporaneamente.
ms.openlocfilehash: a418d840c7e0eb50ae076bf2b03164bef9488058
ms.sourcegitcommit: 88f3982217c29b558e3f9e838bcb425da395dd5e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2019
ms.locfileid: "29708543"
---
# <a name="compare-versions-of-ome"></a>Confronto tra le versioni di OME

In questo articolo vengono confrontati legacy crittografia dei messaggi di Office 365 per le nuove funzionalità OME. Le nuove funzionalità sono una fusione e la versione più recente del OME e Information Rights Management (IRM). Verrà illustrato come i due possono coesistere nella propria organizzazione Office 365.

||
|:-----|
|In questo articolo fa parte di una serie di dimensioni maggiore di articoli su Office 365 Message Encryption. In questo articolo è destinato agli amministratori e ai professionisti IT. Se si è appena per informazioni su inviare né ricevere un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 messaggio crittografia dei](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Side-by-side confronto di caratteristiche e funzionalità

|                                   |Caratteristiche precedenti       |                   |Nuove funzionalità              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**Funzionalità**                     | **OME legacy**    | **IRM**           | **Nuove funzionalità OME** |
|*Inviare un messaggio crittografato*        |Tramite le regole di flusso della posta di Exchange|Per l'utente finale avviata dal desktop Outlook o Outlook sul Web. o tramite Exchange regole del flusso di posta|Per l'utente finale avviata dal desktop Outlook, Outlook per Mac o Outlook sul Web. tramite le regole di trasporto di Exchange e prevenzione della perdita di Office 365 dati (DLP)|
|*Modello di gestione dei diritti*       |   N/D      |Tale opzione non inoltrare e i modelli personalizzati|Tale opzione non inoltrare, opzione solo crittografa e modelli personalizzati|
|*Tipo di destinatario*                   |Destinatari interni ed esterni|Solo i destinatari interni         |Destinatari interni ed esterni|
|*Esperienza per destinatario interno*|I destinatari ricevono un messaggio HTML che si scarica e aprire un web browser o app per dispositivi mobili|Esperienza in linea nativo nei client Outlook|Esperienza in linea nativo per i destinatari di Office 365. Tutti gli altri destinatari possono leggere messaggi dal portale OME (download o app richiesta).|
|*Esperienza per destinatario esterno*|I destinatari ricevono un messaggio HTML che si scarica e aprire un web browser o app per dispositivi mobili|N/D|Esperienza in linea nativo per i destinatari di Office 365. Tutti gli altri destinatari possono leggere messaggi dal portale OME (download o app richiesta).|
|*Autorizzazioni degli allegati*           |Nessuna restrizione degli allegati|Gli allegati sono protetti|Gli allegati sono protetti per l'opzione non inoltrare e i modelli personalizzati. Gli amministratori possono scegliere se allegati per l'opzione solo crittografa sono protetti o non.|
|*Inserire il proprio supporto chiave (BYOK)*|Nessuno                |Nessuno               |BYOK supportati          |
||

## <a name="advantages-of-using-the-new-ome-capabilities-over-legacy-ome"></a>Vantaggi dell'utilizzo delle nuove funzionalità OME OME legacy

Le nuove funzionalità offrono i vantaggi seguenti:

- Possibilità di utilizzare crittografa solo (che consente la collaborazione protetta), non inoltrare, nonché le restrizioni personalizzate.
- Gli utenti possano inviare posta elettronica crittografata con le nuove funzionalità manualmente dal Desktop Outlook, Outlook per Mac e Microsoft Outlook nel client web.
- È possibile ottenere i destinatari di Office 365 da utilizzare un'esperienza in linea nel client di Outlook supportati. In alternativa, gli amministratori possono scegliere di visualizzare i destinatari di Office 365 un'esperienza personalizzata.
- Account all'esterno di Office 365, ad esempio gli account Gmail, Yahoo e Microsoft, sono federati con il portale OME che offre un'esperienza utente migliore per i destinatari. Tutte le altre identità utilizzare un sola volta passcode per accedere ai messaggi crittografati.
- Gli amministratori possono di personalizzazione e creare più modelli di personalizzazione.
- Gli amministratori possono revocare i messaggi di posta elettronica crittografati con le nuove funzionalità.
- Le nuove funzionalità di fornire report di utilizzo dettagliati tramite la sicurezza &amp; centro conformità.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coesistenza di OME legacy e le nuove funzionalità nello stesso tenant

È possibile utilizzare sia OME legacy e le nuove funzionalità nello stesso tenant. In qualità di amministratore tale scegliendo quale versione di OME da utilizzare quando si crea regole del flusso della posta.

- Per specificare la versione legacy di OME, utilizzare l'azione della regola flusso della posta Exchange "Applica alla versione precedente di OME".
- Per specificare le nuove funzionalità, utilizzare la Exchange posta flusso regola azione "applica Office 365 messaggio crittografia e diritti di protezione".

Gli utenti possono inoltre inviare posta elettronica crittografata con le nuove funzionalità manualmente dal Desktop Outlook, Outlook per Mac e Microsoft Outlook nel client web.

## <a name="migrating-from-legacy-ome-to-the-new-capabilities"></a>Migrazione da OME legacy per le nuove funzionalità

Anche se entrambe le versioni di OME possono coesistere, è consigliabile modificare le regole di flusso della posta precedenti che utilizzano l'azione della regola di "Si applicano alla versione precedente di OME" per utilizzare le nuove funzionalità specificando l'azione della regola flusso della posta "Applica crittografia messaggi Office 365 e i diritti di protezione". Per ulteriori informazioni, vedere [definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="getting-started-with-ome"></a>Guida introduttiva a OME

In genere, le nuove funzionalità OME vengono automaticamente abilitate per l'organizzazione Office 365. Se si è pronti per iniziare a utilizzare le nuove funzionalità OME all'interno dell'organizzazione, vedere [impostare le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md).

La versione legacy di OME è abilitata per l'organizzazione Office 365 automaticamente se è stata abilitata la protezione delle informazioni di Azure. In passato, OME legacy sono state eseguite anche se non è stata attivata la protezione delle informazioni di Azure. Questo non è più il caso.

Per iniziare a utilizzare OME legacy, se è stata abilitata la protezione delle informazioni di Azure, è sufficiente è configurare regole del flusso di posta elettronica che utilizzano l'azione della regola "Applica alla versione precedente di OME". Per ulteriori informazioni, vedere [definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).