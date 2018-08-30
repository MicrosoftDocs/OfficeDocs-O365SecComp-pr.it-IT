---
title: Verificare la query di Ricerca contenuto per gli errori
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: Controllare le query con parole chiave per la ricerca del contenuto per gli errori e agli errori di digitazione, ad esempio caratteri non supportati e minuscoli operatori booleani, prima di eseguire la ricerca. Se viene trovato un errore, si verrà consiglia di effettuare una query modificata.
ms.openlocfilehash: 0d2119ceef4ce3777d3967a56357551e235e426c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530790"
---
# <a name="check-your-content-search-query-for-errors"></a>Verificare la query di Ricerca contenuto per gli errori

Quando si crea o modifica di una ricerca di contenuto, è necessario Office 365 controllare la query per i caratteri non supportati e operatori booleani che potrebbero non essere in maiuscolo. In che modo? Nella pagina query di ricerca del contenuto appena fare clic su **Controlla l'ortografia query** . 
  
![Fare clic su "Controlla l'ortografia query" per controllare la query di ricerca per i caratteri non supportati](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
Ecco un elenco dei caratteri non supportati che la ricerca. Caratteri non supportati sono spesso nascosto e vengono in genere causare un errore di ricerca o restituire risultati imprevisti.
  
- Non sono supportate **le virgolette inglesi** - Smart singola e virgolette doppie (denominate anche inglesi). Consente solo le virgolette semplici in una query di ricerca. 
    
- **Caratteri Non stampabili e controllo** - Non stampabili e caratteri di controllo non rappresentano un simbolo scritto, ad esempio un carattere alfanumerico. Esempi di non stampabile e caratteri di controllo includono caratteri che in formato testo o righe separate del testo. 
    
- **Contrassegni da destra a sinistra e da sinistra a destra** - si tratta di caratteri di controllo viene utilizzati per indicare l'orientamento del testo per le lingue da sinistra a destra (ad esempio inglese e italiano) e le relative lingue da destra a sinistra (ad esempio arabo ed ebraico).
    
- **Operatori booleani minuscola** - se si utilizza un operatore booleano, ad esempio **AND**, **o**e **non** in una query di ricerca devono essere maiuscola. Quando si verifica una query relativa agli errori di digitazione, la sintassi di query spesso indicherà che un operatore booleano viene utilizzato anche se minuscoli operatori possono eventualmente essere utilizzati; ad esempio `(WordA or WordB) and (WordC or WordD)`.
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>Cosa succede se una query con un carattere non supportato?

Se vengono trovati caratteri non supportati nella query, verrà visualizzato un messaggio di avviso che informa che caratteri non supportati che sono stati trovati e una proposta alternativa. Quindi è quindi possibile mantenere la query originale o sostituirla con la query modificata consigliata. Di seguito è riportato un esempio del messaggio di avviso visualizzata fare clic su **Controlla l'ortografia query** per la query di ricerca nella schermata precedente. Si noti che la query originale contiene le virgolette inglesi e operatori booleani minuscoli. 
  
![Verrà visualizzato un messaggio di avviso con una revisione consigliata per la query](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Come evitare caratteri non supportati nelle query di ricerca

Caratteri non supportati in genere vengono aggiunti a una query per copiare la query o la Web part della query da altre applicazioni (ad esempio Microsoft Word o Microsoft Excel) e copiarli nella finestra di parola chiave nella pagina query di ricerca di contenuto. Il modo migliore per evitare che caratteri non supportati è di tipo solo la query nella casella parole chiave. In alternativa, è possibile copiare una query da Word o Excel e incollarlo in un file in un editor di testo, ad esempio Microsoft Notepad. Quindi salvare il file di testo e selezionare nell'elenco a discesa **codifica** **ANSI** . Questo comando rimuoverà tutti i caratteri non supportati e formattazione. È quindi possibile copiare e incollare la query dal file di testo nella casella query parola chiave. 
