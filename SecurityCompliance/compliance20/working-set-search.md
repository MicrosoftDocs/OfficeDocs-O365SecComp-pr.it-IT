---
title: Eseguire query sui dati in un set di lavoro
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
ms.openlocfilehash: 2523072181307cce510f0f318834329b2c70b376
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454988"
---
# <a name="query-the-data-in-a-working-set"></a><span data-ttu-id="da3cd-102">Eseguire query sui dati in un set di lavoro</span><span class="sxs-lookup"><span data-stu-id="da3cd-102">Query the data in a working set</span></span>

<span data-ttu-id="da3cd-103">Nella maggior parte dei casi, sarà utile essere in grado di approfondire gli elementi presenti in un working set e organizzarli per la revisione in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="da3cd-103">In most cases, it will be useful to be able to dig deeper into what is there in a working set and organize them to review more efficiently.</span></span> <span data-ttu-id="da3cd-104">Le query all'interno di un working set consentono di eseguire questa operazione consentendo di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri definiti dall'utente in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="da3cd-104">Queries within a working set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-working-set"></a><span data-ttu-id="da3cd-105">Creazione e esecuzione di una query all'interno di un working set</span><span class="sxs-lookup"><span data-stu-id="da3cd-105">Creating and running a query within a working set</span></span>

<span data-ttu-id="da3cd-106">Per creare ed eseguire una query all'interno del working set, fare clic su "nuova query" nel working set.</span><span class="sxs-lookup"><span data-stu-id="da3cd-106">In order to create and run a query within your working set, click on "New Query" in your working set.</span></span> <span data-ttu-id="da3cd-107">Dopo aver denominati la query e aver definito le condizioni, fare clic su "Salva" per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="da3cd-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="da3cd-108">Per eseguire una query salvata in precedenza, è sufficiente fare clic sulla query salvata.</span><span class="sxs-lookup"><span data-stu-id="da3cd-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="da3cd-109">Fare riferimento ai [campi dei metadati del documento](document-metadata-fields.md) per un elenco di metadati di cui è possibile eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="da3cd-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="da3cd-110">Creazione di una query</span><span class="sxs-lookup"><span data-stu-id="da3cd-110">Building your query</span></span>

<span data-ttu-id="da3cd-111">È possibile creare la query utilizzando una combinazione di schede di condizione e lingua di query nella scheda condizione parole chiave.</span><span class="sxs-lookup"><span data-stu-id="da3cd-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span>

### <a name="condition-card"></a><span data-ttu-id="da3cd-112">Scheda condizione</span><span class="sxs-lookup"><span data-stu-id="da3cd-112">Condition card</span></span>

<span data-ttu-id="da3cd-113">Ogni campo ricercabile di un working set ha una corrispondente scheda di condizione che è possibile utilizzare per creare la query.</span><span class="sxs-lookup"><span data-stu-id="da3cd-113">Every searchable field in a working set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="da3cd-114">Sono disponibili più tipi di schede di condizione:</span><span class="sxs-lookup"><span data-stu-id="da3cd-114">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="da3cd-115">FREETEXT: la scheda di stato FREETEXT viene utilizzata per i campi di testo, ad esempio subject.</span><span class="sxs-lookup"><span data-stu-id="da3cd-115">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="da3cd-116">È possibile elencare più termini di ricerca separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="da3cd-116">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="da3cd-117">Data: la scheda condizione data viene utilizzata per i campi data, ad esempio la data dell'Ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="da3cd-117">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="da3cd-118">Opzioni di ricerca: la scheda condizione opzioni di ricerca fornisce un elenco di valori possibili per il campo specifico del working set.</span><span class="sxs-lookup"><span data-stu-id="da3cd-118">Search options: search options condition card will provide a list of possible values for the particular field in your working set.</span></span> <span data-ttu-id="da3cd-119">Viene utilizzato per i campi come sender, in cui è presente un numero finito di valori possibili nel working set.</span><span class="sxs-lookup"><span data-stu-id="da3cd-119">This is used for fields such as sender, where there is a finite number of possible values in your working set.</span></span>
- <span data-ttu-id="da3cd-120">Keyword: la scheda condizione parola chiave è una specifica istanza della scheda di condizione di FREETEXT che è possibile utilizzare per cercare i termini oppure utilizzare la lingua di query simile a KQL.</span><span class="sxs-lookup"><span data-stu-id="da3cd-120">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="da3cd-121">Per ulteriori informazioni, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="da3cd-121">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="da3cd-122">Lingua query</span><span class="sxs-lookup"><span data-stu-id="da3cd-122">Query language</span></span>

<span data-ttu-id="da3cd-123">Oltre alle schede delle condizioni, è possibile utilizzare una lingua di query simile a KQL nella scheda Parole chiave per creare la query.</span><span class="sxs-lookup"><span data-stu-id="da3cd-123">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="da3cd-124">Il linguaggio di query supporta la sintassi di KQL standard, come e, o, non e vicino (n).</span><span class="sxs-lookup"><span data-stu-id="da3cd-124">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="da3cd-125">Supporta anche caratteri jolly con caratteri singoli (?) e caratteri jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="da3cd-125">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>