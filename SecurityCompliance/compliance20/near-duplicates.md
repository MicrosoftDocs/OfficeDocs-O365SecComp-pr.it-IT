---
title: Quasi duplicati
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
ms.openlocfilehash: a3f5945ee4ba0a1bc78ab6c8ccc9af934d392232
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607894"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="4e304-102">Quasi duplicati</span><span class="sxs-lookup"><span data-stu-id="4e304-102">Near duplicate detection</span></span>

<span data-ttu-id="4e304-p101">Si consideri un set di documenti per la revisione in cui un sottoinsieme basato sul modello stesso ed è principalmente standard medesime, con alcune differenze qui e non esiste. Se il revisore può identificare questo subset, esaminare attentamente ognuno di essi ed esaminare le differenze per il resto, sono potrebbe non essere andate perse eventuali informazioni univoche durante la disconnessione solo una frazione di tempo che avrebbe richiesto loro di leggere tutti i documenti in. Rilevamento duplicati prossimo gruppi di documenti in formato testo simili insieme che consentono di rendere più efficiente il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="4e304-p101">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there. If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="4e304-106">Funzionamento.</span><span class="sxs-lookup"><span data-stu-id="4e304-106">How does it work?</span></span>

<span data-ttu-id="4e304-p102">Quando viene eseguito quasi duplicati, il sistema analizza ogni documento con il testo. Quindi, confronto di ogni documento con l'altra per determinare se i similarità è maggiore della soglia set. Se si tratta, i documenti sono raggruppati. Dopo che tutti i documenti sono stati confrontati e raggruppati, un documento da ogni gruppo è contrassegnato come "pivot"; Nell'analisi dei documenti, è possibile esaminare un pivot prima e altri documenti nella stessa quasi duplicati set, concentrandosi sulle differenze tra il pivot e il documento in revisione.</span><span class="sxs-lookup"><span data-stu-id="4e304-p102">When near duplicate detection is run, the system parses every document with text. Then, it compares every document against each other to determine whether their similarity is greater than the set threshold. If it is, the documents are grouped together. Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>