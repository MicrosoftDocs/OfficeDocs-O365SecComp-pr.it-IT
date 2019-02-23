---
title: Creare query di ricerca
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8e7f3d798d3b6cfe25d57b941ed2be1d8d5e92b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216986"
---
# <a name="build-search-queries"></a>Creare query di ricerca

Per creare la query, è possibile utilizzare diverse parole chiave e condizioni per definire gli elementi da trovare.

## <a name="keyword-searches"></a>Ricerche di parole chiave

Digitare una query di ricerca nella casella **parole chiave** . È possibile specificare le parole chiave, le proprietà del messaggio, ad esempio le date inviate e ricevute, o le proprietà del documento, ad esempio i nomi di file o la data dell'Ultima modifica di un documento. È possibile utilizzare una query più complessa che utilizza un operatore booleano, ad esempio **e**, **o**, **non**e **vicino**. È inoltre possibile cercare informazioni riservate (ad esempio i numeri di previdenza sociale) nei documenti oppure cercare documenti che sono stati condivisi esternamente. Se si lascia vuota la casella parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificato verrà incluso nei risultati della ricerca.
    
In alternativa, è possibile fare clic sulla casella di controllo **Mostra elenco parole chiave** e digitare una parola chiave in ogni riga. Se si esegue questa operazione, le parole chiave in ogni riga sono connesse da un operatore logico ( **c:s**) simile alla funzionalità all'operatore **or** nella query di ricerca creata. 
    
Perché usare l'elenco delle parole chiave? È possibile ottenere statistiche che mostrano il numero di elementi che corrispondono a ogni parola chiave. In questo modo è possibile identificare rapidamente quali parole chiave sono le più (e meno) effettive. È inoltre possibile utilizzare una frase di parole chiave (racchiusa tra parentesi) in una riga. Per ulteriori informazioni sulle statistiche di ricerca, vedere [statistica](search-statistics.md)della ricerca.

## <a name="conditions"></a>Condizioni
    
È possibile aggiungere condizioni di ricerca per restringere una ricerca e restituire un insieme di risultati più raffinato. Ogni condizione aggiunge una clausola alla query di ricerca che viene creata e eseguita all'avvio della ricerca. Una condizione è connessa logicamente alla query con parole chiave, specificata nella casella parola chiave, da un operatore logico (**c:c**) simile alla funzionalità all'operatore **and** . Questo significa che gli elementi devono soddisfare sia la query di parole chiave che una o più condizioni da includere nei risultati. Questo è il modo in cui le condizioni aiutano a limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "condizioni di ricerca" in [query di parole chiave e condizioni di ricerca per la ricerca di contenuto](../keyword-queries-and-search-conditions.md#search-conditions).


