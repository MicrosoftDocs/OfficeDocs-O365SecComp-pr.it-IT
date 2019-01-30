---
title: Statistiche ricerca
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c5b7caff3550d42d84408d6b4e966655b8341123
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607930"
---
# <a name="search-statistics"></a>Statistiche ricerca
È possibile verificare i risultati della ricerca, è possibile esaminare le statistiche intorno ai risultati per assicurarsi che siano allineate con le aspettative. Al termine di una ricerca, le statistiche generali vengono visualizzate nel riquadro a comparsa dettagli di ricerca:
- Numero e il volume degli elementi recuperato dalla ricerca
- Numero e il volume di parzialmente indicizzato/non indicizzate gli elementi che sono stati rilevati nei percorsi di ricerca
- Numero di cassette postali e i percorsi eseguita la ricerca. Per visualizzare le statistiche più dettagliate, fare clic su "Statistiche" dal menu mobile dettagli di ricerca.

## <a name="summary"></a>Riepilogo
Nella visualizzazione Riepilogo, è possibile visualizzare i risultati della ricerca suddivisi per tipo di posizione (ad esempio Exchange). Per ogni tipo di percorso, è possibile visualizzare:
- Numero di posizioni che aveva elementi corrispondenti alle condizioni di ricerca
- Numero di elementi da queste posizioni corrispondenti alle condizioni di ricerca
- Volume totale di elementi corrispondenti alle condizioni di ricerca.

## <a name="top-locations"></a>Percorsi principali
Nella visualizzazione percorsi principali sono mostrate le posizioni singole con più corrispondenze. Per ogni percorso, verrà visualizzato:
- Nome della posizione (ad esempio un URL di SharePoint)
- Tipo di percorso
- Numero di elementi corrispondenti alle condizioni di ricerca
- Volume totale di elementi corrispondenti alle condizioni di ricerca.

## <a name="queries"></a>Query
Se è stata utilizzata una parola chiave (c:s) o delle righe di parola chiave nella query, è possibile visualizzare la suddivisione della query nella visualizzazione di query per ogni tipo di percorso. Per ogni tipo di posizione, verrà visualizzato:
- Parte: questa colonna necessario impostare la parola "Principale" o "Parola chiave". "Principale" indica che la riga vengono presentate le statistiche su intera query, mentre "Parola chiave" indica uno dei componenti di query.
- Query: il componente di query effettivo della riga fa riferimento a. Se la parte è "Principale", sarà l'intera query; Se parte era "Parola chiave", verrà visualizzato tra i componenti di query.
  - Quando si esegue la ricerca di tutte le cassette postali contenutomodifica (se non viene specificata una qualsiasi parola chiave), l'effettiva query è ( gt _ dimensione = 0) in modo che vengano restituiti tutti gli elementi
  - Quando si cerca i siti di SharePoint Online e OneDrive, vengono aggiunti i due componenti seguenti:
    - NON IsExternalContent:1 - esclude qualsiasi contenuto da un'organizzazione di SharePoint locale
    - NON isOneNotePage: 1 - consente di escludere tutti i file di OneNote in quanto tali documenti sono duplicati di qualsiasi documento che corrisponda alla query di ricerca.
- Numero di posizioni che aveva elementi corrispondenti alle condizioni di ricerca
- Numero di elementi da queste posizioni corrispondenti alle condizioni di ricerca
- Totale volumne degli elementi corrispondenti alle condizioni di ricerca.

## <a name="refiners"></a>Criteri di affinamento
Cassette postali di Exchange, criteri di affinamento ricerca visualizzazione fornisce ulteriori suddivisioni ItemClass, mittente e destinatario. Per ogni valore di percorso e il criterio di affinamento ricerca, è possibile visualizzare il numero di documenti sono stato restituito nella ricerca.