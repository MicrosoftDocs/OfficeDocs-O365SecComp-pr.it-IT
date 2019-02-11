---
title: Creare query di ricerca
ms.author: markjjo
author: markjjo
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
ms.openlocfilehash: c337b49491fca11e0ba5bc13d22ac3e54038c400
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695072"
---
# <a name="build-search-queries"></a>Creare query di ricerca

Nella creazione delle query, è possibile utilizzare diverse parole chiave e le condizioni per definire gli elementi da trovare.

## <a name="keyword-searches"></a>Ricerche per parole chiave

Nella casella **parole chiave** , digitare una query di ricerca. È possibile specificare le parole chiave, messaggio proprietà come inviati e ricevuti, date o proprietà del documento, ad esempio i nomi di file o la data dell'ultima modifica di un documento. È possibile utilizzare una query più complesse che utilizzano un operatore booleano, ad esempio **AND**, **OR**, **non**e **NEAR**. È inoltre possibile cercare informazioni sensibili (ad esempio numeri di previdenza sociale) nei documenti o ricerca per i documenti condivisi esternamente. Se si lascia vuota la casella parole chiave, tutto il contenuto disponibile nei percorsi di contenuto specificati sarà incluse nei risultati della ricerca.
    
In alternativa, è possibile selezionare la casella di controllo **Mostra elenco di parole chiave** e il tipo di una parola chiave in ogni riga. In questo caso, le parole chiave in ogni riga sono connessi tramite un operatore logico ( **c:s**) che è simile all'operatore **OR** nella query di ricerca che viene creata. 
    
Perché utilizzare l'elenco delle parole chiave? È possibile ottenere le statistiche che mostra il numero di elementi corrispondenti a ogni parola chiave. Ciò consente di identificare rapidamente i quali le parole chiave sono il massimo (e almeno) efficaci. È inoltre possibile utilizzare una frase parola chiave (racchiusa tra parentesi) in una riga. Per ulteriori informazioni sulle statistiche di ricerca, vedere [informazioni statistiche di ricerca](search-statistics.md).

## <a name="conditions"></a>Condizioni
    
È possibile aggiungere le condizioni di ricerca per restringere la ricerca e restituire un set di risultati più dettagliato. Ogni condizione aggiunge una clausola di query di ricerca che viene creata ed eseguita quando si avvia la ricerca. Una condizione è connesso logicamente per le query con parole chiave (specificata nella casella parole chiave) da un operatore logico (**c:c**) funzionalità analogo all'operatore **AND** . Ciò significa che gli elementi presentano soddisfare le query con parole chiave sia una o più condizioni da includere nei risultati. Si tratta come condizioni consentono di limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "Criteri di ricerca" in [condizioni di ricerca per la ricerca del contenuto e query con parole chiave](../keyword-queries-and-search-conditions.md#search-conditions).


