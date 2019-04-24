---
title: Temi
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
ms.openlocfilehash: 7c9d1a52acef48d96816fefbb1c836032d262b93
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240978"
---
# <a name="themes"></a><span data-ttu-id="f04c1-102">Temi</span><span class="sxs-lookup"><span data-stu-id="f04c1-102">Themes</span></span>
<span data-ttu-id="f04c1-103">In che modo una persona scrive un documento?</span><span class="sxs-lookup"><span data-stu-id="f04c1-103">How does a person write a document?</span></span> <span data-ttu-id="f04c1-104">In genere iniziano con una o più idee che vogliono trasmettere nel documento e compongono l'utilizzo di parole che si allineano con le idee.</span><span class="sxs-lookup"><span data-stu-id="f04c1-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="f04c1-105">Più è prevalente un'idea, più le parole che sono correlate a quell'idea tendono ad essere.</span><span class="sxs-lookup"><span data-stu-id="f04c1-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="f04c1-106">In questo modo viene spiegato come gli utenti utilizzano i documenti. la cosa importante da leggere è la lettura di un documento e le idee che il documento sta cercando di trasmettere e quali idee vengono visualizzate e quali sono le relazioni tra le idee.</span><span class="sxs-lookup"><span data-stu-id="f04c1-106">This informs how people consume documents as well; the important thing to get from reading a document is the ideas that the document is trying to convey, and which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="f04c1-107">Questo può essere esteso a come una persona desidera utilizzare un insieme di documenti.</span><span class="sxs-lookup"><span data-stu-id="f04c1-107">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="f04c1-108">Desiderano vedere quali idee sono presenti nei set e quali documenti si riferiscono a queste idee.</span><span class="sxs-lookup"><span data-stu-id="f04c1-108">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="f04c1-109">Inoltre, se trovano un particolare documento di interesse, vogliono essere in grado di visualizzare i documenti che discutono di idee simili.</span><span class="sxs-lookup"><span data-stu-id="f04c1-109">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="f04c1-110">Il modulo themes cerca di simulare il modo in cui gli umani ragionano sui documenti, analizzando i "temi" descritti in un working set e assegnando loro i documenti.</span><span class="sxs-lookup"><span data-stu-id="f04c1-110">Themes module tries to mimic how humans reason about documents, by analyzing the "themes" that are discussed in a working set and assigning them to documents.</span></span> <span data-ttu-id="f04c1-111">I temi fanno un ulteriore passo e identifica per documento il "tema dominante"; vale a dire il tema più visualizzato.</span><span class="sxs-lookup"><span data-stu-id="f04c1-111">Themes goes one step further and identifies per document the "dominant theme"; i.e. the theme that appears the most.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="f04c1-112">Modalità di funzionamento dei temi</span><span class="sxs-lookup"><span data-stu-id="f04c1-112">How does Themes work?</span></span>
<span data-ttu-id="f04c1-113">Themes analizza i documenti con testo in un working set per analizzare i temi comuni che vengono visualizzati tra i documenti.</span><span class="sxs-lookup"><span data-stu-id="f04c1-113">Themes analyzes documents with text in a working set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="f04c1-114">Assegna quindi tali temi ai documenti in cui vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="f04c1-114">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="f04c1-115">Le etichette vengono inoltre contrassegnate con le parole utilizzate nei documenti rappresentativi del tema.</span><span class="sxs-lookup"><span data-stu-id="f04c1-115">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="f04c1-116">Poiché un documento può avere più di un argomento, in molti casi a un documento sono assegnati più temi.</span><span class="sxs-lookup"><span data-stu-id="f04c1-116">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="f04c1-117">Il tema più prominente in un documento è designato come tema dominante.</span><span class="sxs-lookup"><span data-stu-id="f04c1-117">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>