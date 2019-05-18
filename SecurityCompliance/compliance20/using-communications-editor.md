---
title: Usare l'editor delle comunicazioni
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 78865efc5c10ebcff9742f922f675b637bb9b2b0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151488"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="a4638-102">Usare l'editor delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="a4638-102">Use the communications editor</span></span>

<span data-ttu-id="a4638-103">Quando si definisce il contenuto del contenuto del portale, le notifiche di blocco legale e i promemoria e le escalation correlati, è possibile utilizzare l'editor comunicazioni per formattare e personalizzare dinamicamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="a4638-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="a4638-104">Editor di testo RTF</span><span class="sxs-lookup"><span data-stu-id="a4638-104">Rich text editor</span></span> 

<span data-ttu-id="a4638-105">L'editor comunicazioni consente all'utente di personalizzare il testo utilizzando le opzioni dell'editor.</span><span class="sxs-lookup"><span data-stu-id="a4638-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="a4638-106">Ad esempio, gli utenti possono modificare i tipi di carattere, creare elenchi puntati, evidenziare il contenuto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="a4638-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="a4638-107">Unire le variabili di campo</span><span class="sxs-lookup"><span data-stu-id="a4638-107">Merge field variables</span></span>

<span data-ttu-id="a4638-108">È possibile sfruttare le variabili di stampa unione dall'editor comunicazioni per incorporare gli attributi di un custode personalizzato nel testo del corpo di una comunicazione.</span><span class="sxs-lookup"><span data-stu-id="a4638-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="a4638-109">Quando viene inviato al custode, il campo unione verrà popolato con il campo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a4638-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="a4638-110">Quando, ad esempio, viene inviato al custode John Smith, il campo merge [nome custode] verrebbe convertito con il nome corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a4638-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="a4638-111">È possibile utilizzare i campi unione di posta elettronica selezionando le icone del **campo unione** nella parte superiore del controllo editor RTF.</span><span class="sxs-lookup"><span data-stu-id="a4638-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="a4638-112">Il segnaposto verrà aggiunto in base alla posizione del cursore degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a4638-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="a4638-113">Elenco delle variabili di campo unione</span><span class="sxs-lookup"><span data-stu-id="a4638-113">List of merge field variables</span></span>

| <span data-ttu-id="a4638-114">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="a4638-114">Field name</span></span>                  | <span data-ttu-id="a4638-115">Dettagli sul campo</span><span class="sxs-lookup"><span data-stu-id="a4638-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="a4638-116">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="a4638-116">Display Name</span></span>  | <span data-ttu-id="a4638-117">Nome e cognome del custode.</span><span class="sxs-lookup"><span data-stu-id="a4638-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="a4638-118">Collegamento di conferma</span><span class="sxs-lookup"><span data-stu-id="a4638-118">Acknowledgement Link</span></span> | <span data-ttu-id="a4638-119">Un collegamento personalizzato per registrare il riconoscimento di ogni custode.</span><span class="sxs-lookup"><span data-stu-id="a4638-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="a4638-120">Collegamento portale</span><span class="sxs-lookup"><span data-stu-id="a4638-120">Portal Link</span></span>     | <span data-ttu-id="a4638-121">Un collegamento personalizzato per il portale di conformità del custode.</span><span class="sxs-lookup"><span data-stu-id="a4638-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="a4638-122">Responsabile del rilascio</span><span class="sxs-lookup"><span data-stu-id="a4638-122">Issuing Officer</span></span>                   | <span data-ttu-id="a4638-123">L'indirizzo di posta elettronica del responsabile del rilascio specificato.</span><span class="sxs-lookup"><span data-stu-id="a4638-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="a4638-124">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="a4638-124">Issuing Date</span></span>                   | <span data-ttu-id="a4638-125">La data in cui è stato emesso l'avviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="a4638-125">The date that the notice was issued (UTC).</span></span>              |