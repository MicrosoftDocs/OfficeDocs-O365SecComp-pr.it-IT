---
title: Rilevamento dei documenti simili
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
ms.openlocfilehash: 40270fa1e3a6f7cdf0dd2a83650aa36a935d9a6d
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213126"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="d4177-102">Rilevamento dei documenti simili</span><span class="sxs-lookup"><span data-stu-id="d4177-102">Near duplicate detection</span></span>

<span data-ttu-id="d4177-p101">Si conSideri un insieme di documenti da rivedere in cui un sottoinsieme si basa sullo stesso modello e ha per lo più lo stesso linguaggio standard, con poche differenze qua e là. Se un revisore è in grado di identificare questo sottoinsieme, esaminare uno di essi accuratamente ed esaminare le differenze per il resto, non avrebbero perso le informazioni univoche tenendo solo una frazione di tempo che li avrebbe necessari per leggere tutti i documenti da coprire. Nei pressi dei gruppi di rilevamento duplicati, i documenti simili insieme consentono di rendere più efficiente il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="d4177-p101">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there. If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="d4177-106">Funzionamento.</span><span class="sxs-lookup"><span data-stu-id="d4177-106">How does it work?</span></span>

<span data-ttu-id="d4177-p102">Quando viene eseguito il rilevamento duplicato, il sistema analizza tutti i documenti con testo. Viene quindi confrontato ogni documento uno rispetto all'altro per determinare se la loro somiglianza è maggiore rispetto alla soglia impostata. In questo caso, i documenti vengono raggruppati. Una volta che tutti i documenti sono stati confrontati e raggruppati, un documento di ogni gruppo viene contrassegnato come "pivot"; durante la revisione dei documenti, è possibile esaminare prima un pivot ed esaminare gli altri documenti nello stesso set di duplicati vicino, concentrandosi sulla differenza tra il pivot e il documento in esame.</span><span class="sxs-lookup"><span data-stu-id="d4177-p102">When near duplicate detection is run, the system parses every document with text. Then, it compares every document against each other to determine whether their similarity is greater than the set threshold. If it is, the documents are grouped together. Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>