---
title: Confronto delle versioni di crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Vengono illustrate le differenze tra le funzionalità fornite con diverse versioni della crittografia dei messaggi di Office 365 e il modo in cui i due continuano a funzionare insieme.
ms.openlocfilehash: 477fbe8f9d71bd92225a7ba5043576f164933b4e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216676"
---
# <a name="compare-versions-of-ome"></a>Confrontare le versioni di OME

In questo articolo viene confrontata la crittografia dei messaggi legacy di Office 365 con le nuove funzionalità OME. Le nuove funzionalità sono una fusione e una versione più recente sia di OME che di Information Rights Management (IRM). Si tratterà anche del modo in cui i due possono coesistere nell'organizzazione di Office 365.

||
|:-----|
|Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e professionisti IT. Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Confronto affiancato di caratteristiche e funzionalità

|                                   |Caratteristiche obsolete       |                   |Nuove funzionalità              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**Funzionalità**                     | **OME legacy**    | **IRM**           | **Nuove funzionalità OME** |
|*Invio di un messaggio crittografato*        |Tramite le regole del flusso di posta di Exchange|L'utente finale è stato avviato da Outlook desktop o Outlook sul Web. o tramite le regole del flusso di posta di Exchange|L'utente finale è stato avviato dal desktop di Outlook, Outlook per Mac o Outlook sul Web. tramite le regole di trasporto di Exchange e la prevenzione della perdita di dati (DLP) di Office 365|
|*Modello Rights Management*       |   N/D      |Non inoltrare l'opzione e i modelli personalizzati|Non inoltrare l'opzione, l'opzione solo crittografia e i modelli personalizzati|
|*Tipo di destinatario*                   |Destinatari interni ed esterni|Solo destinatari interni         |Destinatari interni ed esterni|
|*Esperienza per il destinatario interno*|I destinatari ricevono un messaggio HTML che consente di scaricare e aprire in un Web browser o in un'app per dispositivi mobili|Utilizzo nativo in linea nei client Outlook|Utilizzo nativo in linea per i destinatari di Office 365. Tutti gli altri destinatari possono leggere il messaggio dal portale OME (non è necessario alcun download o app).|
|*Esperienza per il destinatario esterno*|I destinatari ricevono un messaggio HTML che consente di scaricare e aprire in un Web browser o in un'app per dispositivi mobili|N/D|Utilizzo nativo in linea per i destinatari di Office 365. Tutti gli altri destinatari possono leggere il messaggio dal portale OME (non è necessario alcun download o app).|
|*Autorizzazioni per gli allegati*           |Nessuna restrizione sugli allegati|Gli allegati sono protetti|Gli allegati sono protetti per l'opzione non inoltrare e i modelli personalizzati. Gli amministratori possono scegliere se gli allegati per l'opzione solo crittografia sono protetti o meno.|
|*Fornire il supporto per la chiave personale (BYOK)*|Nessuna                |Nessuna               |BYOK supportato          |
||

## <a name="advantages-of-using-the-new-ome-capabilities-over-legacy-ome"></a>Vantaggi dell'utilizzo delle nuove funzionalità OME su OME legacy

Le nuove funzionalità offrono i vantaggi seguenti:

- Possibilità di utilizzare solo crittografia (che consente la collaborazione sicura), non inoltrare, nonché restrizioni personalizzate.
- I mittenti possono inviare messaggi di posta elettronica crittografati con le nuove funzionalità manualmente da Outlook desktop, Outlook per Mac e Outlook sul Web client.
- Gli utenti di Office 365 ricevono l'utilizzo di un'esperienza in linea nei client Outlook supportati. In alternativa, gli amministratori possono scegliere di mostrare ai destinatari di Office 365 un'esperienza di marca.
- Gli account esterni a Office 365, ad esempio Gmail, Yahoo e gli account Microsoft, sono federati con il portale OME, che offre un'esperienza utente migliore per questi destinatari. Tutte le altre identità utilizzano un codice Pass una tantum per accedere ai messaggi crittografati.
- Gli amministratori possono personalizzare la personalizzazione e creare modelli di branding multipli.
- Gli amministratori possono revocare i messaggi di posta elettronica crittografati con le nuove funzionalità.
- Le nuove funzionalità forniscono rapporti di utilizzo dettagliati tramite &amp; il Centro sicurezza e conformità.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coesistenza di OME legacy e nuove funzionalità nello stesso tenant

È possibile utilizzare sia legacy OME che le nuove funzionalità nello stesso tenant. In qualità di amministratore, è possibile scegliere la versione di OME che si desidera utilizzare quando si creano le regole del flusso di posta.

- Per specificare la versione legacy di OME, utilizzare l'azione della regola del flusso di posta di Exchange "Apply the previous version of OME".
- Per specificare le nuove funzionalità, utilizzare l'azione della regola del flusso di posta di Exchange "Apply Office 365 Message Encryption and Rights Protection".

Gli utenti possono anche inviare manualmente la posta crittografata con le nuove funzionalità dal desktop di Outlook, Outlook per Mac e Outlook sul Web client.

## <a name="migrating-from-legacy-ome-to-the-new-capabilities"></a>Migrazione da OME legacy alle nuove funzionalità

Anche se entrambe le versioni di OME possono coesistere, si consiglia di modificare le regole del flusso di posta precedenti che utilizzano l'azione della regola "applica la versione precedente di OME" per utilizzare le nuove funzionalità specificando l'azione della regola del flusso di posta elettronica "applicare la crittografia dei messaggi di Office 365 e protezione dei diritti ". Per istruzioni, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="getting-started-with-ome"></a>Guida introduttiva a OME

In genere, le nuove funzionalità OME sono abilitate automaticamente per l'organizzazione di Office 365. Se si è pronti per iniziare a utilizzare le nuove funzionalità OME all'interno dell'organizzazione, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md).

La versione legacy di OME è abilitata automaticamente per l'organizzazione di Office 365 se è stata abilitata Azure Information Protection. In passato, la funzionalità OME Legacy ha funzionato anche se la protezione delle informazioni di Azure non è stata abilitata. Questo non è più il caso.

Per iniziare a utilizzare OME legacy, se è stata abilitata Azure Information Protection, è sufficiente configurare le regole del flusso di posta che utilizzano l'azione della regola "applica la versione precedente di OME". Per istruzioni, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).