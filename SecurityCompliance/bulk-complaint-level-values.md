---
title: Valori al livello reclamo massa
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
description: Blocco Mailer variano nei modelli di invio, la creazione di contenuto e alle pratiche di acquisizione di elenco. Alcuni lavoratori sono Mailer blocco buona che inviano intendeva i messaggi con il contenuto pertinente per i sottoscrittori. Questi messaggi generano reclami alcuni dei destinatari. Altri Mailer blocco inviare messaggi indesiderati strettamente essere simile a quella della posta indesiderata e generano reclami numero di destinatari. Per distinguere i tipi di Mailer di blocco, i messaggi provenienti da Mailer blocco sono assegnati un blocco reclamo livello (libreria di classi base). Libreria di classi base valutazioni compreso tra 1 e 9 in base al quale probabilità mailer blocco è per la generazione di reclami. Un mittente che presenta un livello di libreria di classi base 9 è probabile che venga generato reclami numero di destinatari, mentre una valutazione della libreria di classi base 3 è improbabile che per la generazione di reclami molti. Microsoft utilizza origini sia interne che terze parti per identificare posta inviata in blocco e determinare la libreria di classi base appropriato. Questa classificazione verrà reso disponibile nell'intestazione X-Microsoft-Antispam di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere anti-spam message headers.
ms.openlocfilehash: c4100b0d289398d9333369071c9886309f2abcb4
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003055"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="97b0e-112">Valori al livello reclamo massa</span><span class="sxs-lookup"><span data-stu-id="97b0e-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="97b0e-p102">Blocco Mailer variano nei modelli di invio, la creazione di contenuto e alle pratiche di acquisizione di elenco. Alcuni lavoratori sono Mailer blocco buona che inviano intendeva i messaggi con il contenuto pertinente per i sottoscrittori. Questi messaggi generano reclami alcuni dei destinatari. Altri Mailer blocco inviare messaggi indesiderati strettamente essere simile a quella della posta indesiderata e generano reclami numero di destinatari. Per distinguere i tipi di Mailer di blocco, i messaggi provenienti da Mailer blocco sono assegnati un blocco reclamo livello (libreria di classi base). Libreria di classi base valutazioni compreso tra 1 e 9 in base al quale probabilità mailer blocco è per la generazione di reclami. Un mittente che presenta un livello di libreria di classi base 9 è probabile che venga generato reclami numero di destinatari, mentre una valutazione della libreria di classi base 3 è improbabile che per la generazione di reclami molti. Microsoft utilizza origini sia interne che terze parti per identificare posta inviata in blocco e determinare la libreria di classi base appropriato. Questa classificazione verrà reso disponibile nell'intestazione **X-Microsoft-Antispam** di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere [anti-spam message headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="97b0e-p102">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices. Some are good bulk mailers that send wanted messages with relevant content to their subscribers. These messages generate few complaints from recipients. Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients. To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating. BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints. A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints. Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL. This rating is exposed in the **X-Microsoft-Antispam** header of every message. For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="97b0e-123">È possibile utilizzare i valori di libreria di classi base per impostare il livello di blocco filtro che l'organizzazione richiede seguendo i passaggi di [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md)desiderato.</span><span class="sxs-lookup"><span data-stu-id="97b0e-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="97b0e-p103">Numero di valori di libreria di classi base viene aggiunti e verrà inclusi qui in futuro. Nella tabella seguente vengono elencati e descritti i valori di libreria di classi base che sono attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="97b0e-p103">More BCL values are being added and will be included here in the future. The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="97b0e-126">**Libreria di classi base valore**</span><span class="sxs-lookup"><span data-stu-id="97b0e-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="97b0e-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="97b0e-127">**Description**</span></span> <br/> |
|<span data-ttu-id="97b0e-128">0</span><span class="sxs-lookup"><span data-stu-id="97b0e-128">0</span></span>  <br/> |<span data-ttu-id="97b0e-129">Il messaggio non è da un mittente in blocco.</span><span class="sxs-lookup"><span data-stu-id="97b0e-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="97b0e-130">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="97b0e-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="97b0e-131">Il messaggio è da un mittente di blocco che genera alcuni reclami.</span><span class="sxs-lookup"><span data-stu-id="97b0e-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="97b0e-132">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="97b0e-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="97b0e-133">Il messaggio proviene da un mittente di blocco che genera un numero misto di reclami.</span><span class="sxs-lookup"><span data-stu-id="97b0e-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="97b0e-134">8, 9</span><span class="sxs-lookup"><span data-stu-id="97b0e-134">8, 9</span></span>  <br/> |<span data-ttu-id="97b0e-135">Il messaggio proviene da un mittente di blocco che genera un numero elevato di reclami</span><span class="sxs-lookup"><span data-stu-id="97b0e-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

