---
title: Verificare la presenza di errori nella query di Ricerca contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: Prima di eseguire la ricerca, controllare la query di parole chiave per la ricerca di contenuto per errori e refusi, ad esempio caratteri non supportati e operatori booleani minuscoli. Se viene visualizzato un errore, verrà suggerita una query riveduta.
ms.openlocfilehash: 00612116f345e2a01471d5c83df77f4bc8db9ce5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243663"
---
# <a name="check-your-content-search-query-for-errors"></a>Verificare la presenza di errori nella query di Ricerca contenuto

Quando si crea o si modifica una ricerca di contenuto, è possibile che Office 365 verifichi la query per i caratteri non supportati e gli operatori booleani che potrebbero non essere capitalizzati. Come? Basta fare clic su **Controlla query per errori** di battitura nella pagina query di una ricerca contenuto. 
  
![Fare clic su "controlla query per errori di battitura" per controllare la query di ricerca per i caratteri non supportati](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
Di seguito è indicato un elenco dei caratteri non supportati che vengono verificati. I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o restituiscono risultati indesiderati.
  
- Virgolette **Smart** -le virgolette singole e doppie (chiamate anche virgolette) non sono supportate. In una query di ricerca è possibile utilizzare solo virgolette semplici. 
    
- **Caratteri non stampabili e di controllo** : i caratteri non stampabili e di controllo non rappresentano un simbolo scritto, ad esempio un carattere alfanumerico. Alcuni esempi di caratteri di controllo e non stampabili includono caratteri che formattano il testo o righe separate di testo. 
    
- **Segni da sinistra a destra e da destra a sinistra** , ovvero caratteri di controllo utilizzati per indicare la direzione del testo per le lingue da sinistra a destra, ad esempio l'inglese e lo spagnolo, e le lingue da destra a sinistra, ad esempio l'arabo e l'ebraico.
    
- **Operatori booleani minuscoli** : se si utilizza un operatore booleano, ad esempio **e**, **o**e **non** in una query di ricerca, è necessario che sia maiuscolo. Quando si controlla una query per errori di battitura, la sintassi della query indica spesso che è in uso un operatore booleano, anche se possono essere utilizzati operatori minuscoli; ad esempio, `(WordA or WordB) and (WordC or WordD)`.
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>Cosa succede se una query ha un carattere non supportato?

Se nella query sono presenti caratteri non supportati, viene visualizzato un messaggio di avviso che indica che i caratteri non supportati sono stati trovati e suggerisce un'alternativa. Successivamente, è possibile mantenere la query originale o sostituirla con la query riveduta consigliata. Di seguito è riportato un esempio del messaggio di avviso visualizzato dopo aver fatto clic su **Controlla query per errori** di recapito per la query di ricerca nella schermata precedente. Si noti che la query originale contiene le virgolette intelligenti e gli operatori booleani minuscoli. 
  
![Viene visualizzato un messaggio di avviso con una revisione consigliata per la query](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Come impedire i caratteri non supportati nelle query di ricerca

I caratteri non supportati vengono in genere aggiunti a una query quando si copia la query o parti della query da altre applicazioni, ad esempio Microsoft Word o Microsoft Excel, e vengono copiate nella casella parola chiave della pagina query di una ricerca di contenuto. Il modo migliore per evitare che i caratteri non supportati è solo digitare la query nella casella parola chiave. In alternativa, è possibile copiare una query da Word o Excel e incollarla nel file in un editor di testo normale, ad esempio il blocco note Microsoft. Salvare quindi il file di testo e selezionare **ANSI** nell'elenco a discesa **Encoding** . In questo modo, verranno rimossi tutti i caratteri di formattazione e non supportati. È quindi possibile copiare e incollare la query dal file di testo nella casella query parola chiave. 
