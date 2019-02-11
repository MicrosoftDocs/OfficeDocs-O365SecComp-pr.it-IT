---
title: Usare l'editor delle comunicazioni
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
ms.openlocfilehash: b148ff1a77cd9225a26f98e7612e9fb5b57331e3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706057"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="f7b1d-102">Usare l'editor delle comunicazioni</span><span class="sxs-lookup"><span data-stu-id="f7b1d-102">Use the communications editor</span></span>

<span data-ttu-id="f7b1d-103">Quando si definisce il contenuto del contenuto del portale, legale attesa notifiche e promemoria correlate le misure correttive, è possibile utilizzare l'Editor Communications per formattare e personalizzare in modo dinamico del contenuto.</span><span class="sxs-lookup"><span data-stu-id="f7b1d-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="f7b1d-104">Editor testo RTF</span><span class="sxs-lookup"><span data-stu-id="f7b1d-104">Rich text editor</span></span> 

<span data-ttu-id="f7b1d-p101">Editor Communications consente di personalizzare il testo utilizzando le opzioni editor. Ad esempio, gli utenti possono modificare tipi di carattere, creare gli elenchi puntati, evidenziare il contenuto e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="f7b1d-p101">The Communications Editor allows user to customize the text using the editor options. For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="f7b1d-107">Unire le variabili di campi</span><span class="sxs-lookup"><span data-stu-id="f7b1d-107">Merge field variables</span></span>

<span data-ttu-id="f7b1d-p102">È possibile utilizzare variabili di unione posta elettronica da Editor Communications per incorporare gli attributi personalizzati depositaria nel corpo del testo di comunicazione. Quando inviato per la depositaria, il campo unione verrà visualizzato il campo corrispondente. Ad esempio, quando si invia a depositaria John Smith, il campo unione [nome depositaria] verrebbe convertito con il nome corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f7b1d-p102">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text. When sent to the custodian, the merge field will be populated with the corresponding field. For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="f7b1d-p103">È possibile utilizzare campi unione email selezionando le icone di **campo unione** nella parte superiore del controllo editor testo RTF. I segnaposto verrà aggiunti base disattiva la posizione del puntatore degli utenti.</span><span class="sxs-lookup"><span data-stu-id="f7b1d-p103">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control. The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="f7b1d-113">Elenco di variabili di campi di stampa unione</span><span class="sxs-lookup"><span data-stu-id="f7b1d-113">List of merge field variables</span></span>

| <span data-ttu-id="f7b1d-114">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="f7b1d-114">Field name</span></span>                  | <span data-ttu-id="f7b1d-115">Dettagli campo</span><span class="sxs-lookup"><span data-stu-id="f7b1d-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="f7b1d-116">Nome visualizzato</span><span class="sxs-lookup"><span data-stu-id="f7b1d-116">Display Name</span></span>  | <span data-ttu-id="f7b1d-117">Il depositaria prima del nome e cognome.</span><span class="sxs-lookup"><span data-stu-id="f7b1d-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="f7b1d-118">Collegamento di conferma</span><span class="sxs-lookup"><span data-stu-id="f7b1d-118">Acknowledgement Link</span></span> | <span data-ttu-id="f7b1d-119">Un collegamento personalizzato per registrare il riconoscimento di ogni depositaria.</span><span class="sxs-lookup"><span data-stu-id="f7b1d-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="f7b1d-120">Collegamento del portale</span><span class="sxs-lookup"><span data-stu-id="f7b1d-120">Portal Link</span></span>     | <span data-ttu-id="f7b1d-121">Un collegamento personalizzato per il portale di conformità del depositaria.</span><span class="sxs-lookup"><span data-stu-id="f7b1d-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="f7b1d-122">Responsabile della emittente</span><span class="sxs-lookup"><span data-stu-id="f7b1d-122">Issuing Officer</span></span>                   | <span data-ttu-id="f7b1d-123">L'indirizzo di posta elettronica dell'emittente ufficiale specificato.</span><span class="sxs-lookup"><span data-stu-id="f7b1d-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="f7b1d-124">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="f7b1d-124">Issuing Date</span></span>                   | <span data-ttu-id="f7b1d-125">Data in cui l'avviso è stato emesso (Time).</span><span class="sxs-lookup"><span data-stu-id="f7b1d-125">The date that the notice was issued (UTC).</span></span>              |