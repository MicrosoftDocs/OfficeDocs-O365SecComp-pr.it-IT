---
title: Confronto delle versioni di crittografia messaggi (OME) di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: In questo articolo vengono descritte le differenze tra le funzionalità recapitate con diverse versioni della crittografia dei messaggi di Office 365 e il modo in cui i due continuano a funzionare insieme.
ms.openlocfilehash: bb13208e2b630c8a6217b78b48a4cd3bb4b0de79
ms.sourcegitcommit: 895f67531f2b4afe46c7487ca5b44555ca791bae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836840"
---
# <a name="compare-versions-of-ome"></a>Confrontare le versioni di OME

Questo articolo consente di confrontare la crittografia dei messaggi di Office 365 (OME) legacy con le nuove funzionalità OME. Le nuove funzionalità sono una fusione e una versione più recente di OME e Information Rights Management (IRM). Sono delineate anche le caratteristiche uniche di distribuzione in GCC High. Si tratterà anche del modo in cui i due possono coesistere nell'organizzazione di Office 365.

||
|:-----|
|Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e professionisti IT. Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Confronto affiancato di caratteristiche e funzionalità

|                                   |Caratteristiche obsolete       |                   |Nuove funzionalità              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**Funzionalità**                     | **OME legacy**    | **IRM**           | **Nuove funzionalità OME** |
|*Invio di un messaggio crittografato*        |Tramite le regole del flusso di posta di Exchange|L'utente finale è stato avviato da Outlook desktop o Outlook sul Web. o tramite le regole del flusso di posta di Exchange|L'utente finale è stato avviato dal desktop di Outlook, Outlook per Mac o Outlook sul Web. tramite le regole del flusso di posta di Exchange (note anche come regole di trasporto) e la prevenzione della perdita di dati (DLP) di Office 365|
|*Modello Rights Management*       |   N/D      |Non inoltrare l'opzione e i modelli personalizzati|Non inoltrare l'opzione, l'opzione solo crittografia e i modelli personalizzati|
|*Tipo di destinatario*                   |Destinatari interni ed esterni|Solo destinatari interni         |Destinatari interni ed esterni|
|*Esperienza per il destinatario interno*|I destinatari ricevono un messaggio HTML che consente di scaricare e aprire in un Web browser o in un'app per dispositivi mobili|Utilizzo nativo in linea nei client Outlook|Utilizzo nativo in linea per i destinatari di Office 365. Tutti gli altri destinatari possono leggere il messaggio dal portale OME (non è necessario alcun download o app).|
|*Esperienza per il destinatario esterno*|I destinatari ricevono un messaggio HTML che consente di scaricare e aprire in un Web browser o in un'app per dispositivi mobili|N/D|Utilizzo nativo in linea per i destinatari di Office 365. Tutti gli altri destinatari possono leggere il messaggio dal portale OME (non è necessario alcun download o app).|
|*Autorizzazioni per gli allegati*           |Nessuna restrizione sugli allegati|Gli allegati sono protetti|Gli allegati sono protetti per l'opzione non inoltrare e i modelli personalizzati. Gli amministratori possono scegliere se gli allegati per l'opzione solo crittografia sono protetti o meno.|
|*Fornire il supporto per la chiave personale (BYOK)*|Nessuna                |Nessuna               |BYOK supportato          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vantaggi delle nuove funzionalità OME su OME legacy

Le nuove funzionalità offrono i vantaggi seguenti:

- Possibilità di utilizzare solo crittografia (che consente la collaborazione sicura), non inoltrare e restrizioni personalizzate.
- I mittenti possono inviare messaggi di posta elettronica crittografati con le nuove funzionalità manualmente da Outlook desktop, Outlook per Mac e Outlook sul Web client.
- Gli utenti di Office 365 ricevono l'utilizzo di un'esperienza in linea nei client Outlook supportati. In alternativa, gli amministratori possono scegliere di mostrare ai destinatari di Office 365 un'esperienza di marca.
- Gli account esterni a Office 365, ad esempio Gmail, Yahoo e gli account Microsoft, sono federati con il portale OME, che offre un'esperienza utente migliore per questi destinatari. Tutte le altre identità utilizzano un codice Pass una tantum per accedere ai messaggi crittografati.
- Gli amministratori possono personalizzare la personalizzazione e creare modelli di branding multipli.
- Gli amministratori possono revocare i messaggi di posta elettronica crittografati con le nuove funzionalità.
- Le nuove funzionalità forniscono rapporti di utilizzo dettagliati tramite &amp; il Centro sicurezza e conformità.

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Caratteristiche esclusive della crittografia dei messaggi di Office 365 in una distribuzione ad alta GCC

Se si prevede di utilizzare la crittografia dei messaggi di Office 365 in un ambiente GCC High, esistono alcune caratteristiche uniche relative all'esperienza del destinatario.

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a>Messaggi di posta elettronica crittografati da GCC High a GCC High Recipients

I mittenti possono crittografare manualmente i messaggi di posta elettronica in Outlook per PC e Mac e Outlook sul Web, oppure le organizzazioni possono configurare un criterio per crittografare i messaggi di posta elettronica utilizzando le regole del flusso del messaggio di Exchange.

I destinatari all'interno di GCC High ricevono la stessa esperienza di lettura in linea in Outlook per PC e Mac e Outlook sul Web come tutti gli altri utenti di Office 365.

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a>Messaggi di posta elettronica crittografati da GCC High a destinatari non GCC alti

I mittenti all'interno di GCC High possono inviare messaggi di posta elettronica crittografati all'esterno del limite alto GCC.

Tutti i destinatari esterni a GCC High, compresi gli utenti di Office 365 commerciali, gli utenti di Outlook.com e altri utenti di altri provider di posta elettronica come Gmail e Yahoo, ricevono un messaggio di posta elettronica wrapper che reindirizza il destinatario al portale OME in cui il destinatario è in grado di leggere e Rispondi a un messaggio.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coesistenza di OME legacy e nuove funzionalità nello stesso tenant

È possibile utilizzare sia legacy OME che le nuove funzionalità nello stesso tenant. In qualità di amministratore, è possibile scegliere la versione di OME che si desidera utilizzare quando si creano le regole del flusso di posta.

- Per specificare la versione legacy di OME, utilizzare l'azione regola flusso di posta di Exchange **applicare la versione precedente di ome**.
- Per specificare le nuove funzionalità, utilizzare l'azione della regola del flusso di posta di Exchange **applicare la crittografia dei messaggi di Office 365 e Rights Protection**.

Gli utenti possono inviare manualmente messaggi di posta elettronica crittografati con le nuove funzionalità di Outlook desktop, Outlook per Mac e Outlook sul Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Eseguire la migrazione da OME legacy alle nuove funzionalità

Anche se entrambe le versioni di OME possono coesistere, è consigliabile modificare le regole del flusso di posta obsolete che utilizzano l'azione regola **applicano la versione precedente di ome** per utilizzare le nuove funzionalità. Update these rules to use the mail Flow Rule Action **Apply Office 365 Message Encryption and Rights Protection**. Per istruzioni, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Introduzione a OME

In genere, le nuove funzionalità OME sono abilitate automaticamente per l'organizzazione di Office 365. Per ulteriori informazioni sulle nuove funzionalità OME all'interno dell'organizzazione, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md).

La versione legacy di OME è abilitata automaticamente per l'organizzazione di Office 365 se è stata abilitata Azure Information Protection. In passato, la funzionalità OME Legacy ha funzionato anche se la protezione delle informazioni di Azure non è stata abilitata. Questo non è più il caso.

Per iniziare a utilizzare OME legacy, se è stata abilitata la protezione delle informazioni di Azure, è sufficiente configurare le regole del flusso di posta che utilizzano l'azione regola **applicano la versione precedente di ome**. Per istruzioni, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).