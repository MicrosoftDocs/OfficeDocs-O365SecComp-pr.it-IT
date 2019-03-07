---
title: Aggiungere tag ai documenti in un set di lavoro
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1183264f64a74e50f750ee13618f7532ffe04eb7
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455158"
---
# <a name="tag-documents-in-a-working-set"></a>Aggiungere tag ai documenti in un set di lavoro

L'organizzazione del contenuto in un working set è importante per completare diversi flussi di lavoro nel processo di eDiscovery. Ciò include:

-  Eliminazione del contenuto non necessario.

- Identificare il contenuto pertinente.
 
-  Identificare il contenuto che deve essere esaminato da un esperto o da un avvocato.

Quando esperti, avvocati o altri utenti esaminano il contenuto in un working set, le loro opinioni relative al contenuto possono essere acquisite utilizzando i tag. Ad esempio, se lo scopo è quello di eliminare contenuto non necessario, un utente può contrassegnare i documenti con un tag come "non rispondente". Dopo la revisione e il tag del contenuto, è possibile creare una ricerca di working set che escluda qualsiasi contenuto contrassegnato come "non reattivo", che elimini questo contenuto dai passaggi successivi del flusso di lavoro di eDiscovery. Il riquadro Tag può essere personalizzato per ogni caso, in modo che i tag possano supportare il flusso di lavoro di revisione previsto.

## <a name="tag-types"></a>Tipi di tag

Advanced eDiscovery (Preview) fornisce due tipi di Tag:

- **Tag a scelta singola** : limita gli utenti a selezionare un singolo tag all'interno di un gruppo. Questo può essere utile per garantire agli utenti di non selezionare tag in conflitto, ad esempio "reattivi" e "non rispondenti". 

- **Tag a scelta multipla** : consente agli utenti di selezionare più tag all'interno di un gruppo.

## <a name="tag-structure"></a>Struttura tag

Oltre ai tipi di tag, è possibile utilizzare la struttura dei tag nell'organizzazione nel pannello Tag per rendere più intuitivi i documenti di tagging. I tag vengono raggruppati in base alle sezioni. La ricerca di working set supporta la funzionalità di ricerca in base al tag e alla sezione Tag. Questo significa che è possibile creare una ricerca di working set per recuperare i documenti contrassegnati con un tag qualsiasi in una sezione.

![Sezioni dei tag nel pannello Tag](../media/Tagtypes.png)

I tag possono essere ulteriormente organizzati annidando questi all'interno di una sezione. Ad esempio, se si intende identificare e contrassegnare il contenuto con privilegi, è possibile utilizzare la nidificazione per specificare che un utente può contrassegnare un documento come "privilegiato" e selezionare il tipo di privilegio selezionando il tag nidificato appropriato.

![Tag annidati all'interno di una sezione Tag](../media/Nestingtags.png)

## <a name="applying-tags"></a>Applicazione di tag

Esistono diversi modi per applicare un tag al contenuto.

### <a name="tagging-a-single-document"></a>Tagging di un singolo documento

Quando si visualizza un documento in un working set, è possibile visualizzare i tag che possono essere utilizzati da una recensione facendo clic su **Pannello di codifica**.

![Fare clic su pannello Tag per visualizzare il pannello Tag](../media/Singledoctag.png)

Ciò consentirà di applicare i tag al documento visualizzato nel visualizzatore.

### <a name="bulk-tagging"></a>Tag di massa

Il tagging di massa può essere ottenuto selezionando più file nella griglia dei risultati e quindi utilizzando i tag del **riquadro di codifica** in modo analogo al tagging dei singoli documenti. Non è possibile eseguire un tagging in blocco selezionando due volte i tag; il primo clic applicherà il tag e la seconda selezione assicurerà che il tag sia deselezionato per tutti i file selezionati.

![Schermata di una descrizione del telefono cellulare generata automaticamente](../media/Bulktag.png)

> [!NOTE]
> Quando si esegue il tagging in blocco, nel riquadro di tagging viene visualizzato il numero di file contrassegnati per ogni tag nel pannello.

### <a name="tagging-in-other-review-panels"></a>Tagging in altri pannelli di Revisione

Quando si esaminano i documenti, è possibile utilizzare gli altri pannelli di revisione per esaminare altre caratteristiche dei documenti nella griglia dei risultati. Questo include la revisione di altri documenti correlati, i thread di posta elettronica, la presenza di duplicati e duplicati hash. Ad esempio, quando si esaminano i documenti correlati (tramite il riquadro Revisione **famiglia documenti** ), è possibile ridurre in modo significativo il tempo di revisione tramite la codifica in blocco dei documenti correlati. Ad esempio, se un messaggio di posta elettronica dispone di più allegati e si desidera garantire che l'intera famiglia sia contrassegnata in modo coerente.

Ad esempio, ecco come visualizzare il pannello di **codifica** quando si utilizza il pannello Revisione **famiglia documenti** :

1. Se si apre il pannello di controllo per un documento selezionato, ad esempio l'elenco di contenuto correlato nel pannello Revisione **famiglia** documenti, fare clic su **documenti di codice** nella parte superiore del riquadro Revisione corrente.

   Il pannello di codifica viene visualizzato come finestra popup.

2. Scegliere uno o più tag per applicare il documento selezionato. 

3. Per contrassegnare tutti i documenti, selezionare tutti i documenti nel riquadro **famiglia** documenti, fare clic su **documenti di codice**e quindi scegliere i tag da applicare all'intera famiglia di documenti.

![Schermata di una descrizione di social media post generata automaticamente](../media/Relatedtag.png)
