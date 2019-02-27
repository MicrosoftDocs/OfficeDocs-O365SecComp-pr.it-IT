---
title: Valori di livello di reclamo in blocco
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
ms.collection:
- M365-security-compliance
description: I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dell'elenco. Alcuni sono buoni mailer che inviano messaggi desiderati con contenuto pertinente ai propri abbonati. Questi messaggi generano alcuni reclami dai destinatari. Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari. Per distinguere questi tipi di messaggi di posta elettronica in blocco, viene assegnato un punteggio di livello di reclamo in blocco da parte di un messaggio di posta elettronica in blocco. Le valutazioni BCL variano da 1 a 9 a seconda di quanto è probabile che il mailer di posta in blocco debba generare reclami. Un mittente che ha un punteggio di BCL 9 può generare molti reclami dai destinatari, mentre non è probabile che un punteggio di BCL 3 generi molti reclami. Microsoft utilizza origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata. Questa valutazione è esposta nell'intestazione X-Microsoft-antispam di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere intestazioni dei messaggi di protezione da posta indesiderata.
ms.openlocfilehash: a948e90ba436dcfdb78df856e090983e6015bb0a
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276016"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="b3467-112">Valori di livello di reclamo in blocco</span><span class="sxs-lookup"><span data-stu-id="b3467-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="b3467-p102">I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dell'elenco. Alcuni sono buoni mailer che inviano messaggi desiderati con contenuto pertinente ai propri abbonati. Questi messaggi generano alcuni reclami dai destinatari. Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari. Per distinguere questi tipi di messaggi di posta elettronica in blocco, viene assegnato un punteggio di livello di reclamo in blocco da parte di un messaggio di posta elettronica in blocco. Le valutazioni BCL variano da 1 a 9 a seconda di quanto è probabile che il mailer di posta in blocco debba generare reclami. Un mittente che ha un punteggio di BCL 9 può generare molti reclami dai destinatari, mentre non è probabile che un punteggio di BCL 3 generi molti reclami. Microsoft utilizza origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata. Questa valutazione è esposta nell'intestazione **X-Microsoft-antispam** di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere [intestazioni dei messaggi](anti-spam-message-headers.md)di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="b3467-p102">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices. Some are good bulk mailers that send wanted messages with relevant content to their subscribers. These messages generate few complaints from recipients. Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients. To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating. BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints. A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints. Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL. This rating is exposed in the **X-Microsoft-Antispam** header of every message. For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="b3467-123">È possibile utilizzare i valori BCL per impostare il livello di filtro di massa desiderato per l'organizzazione, attenendosi alla procedura descritta in [Configure Your Spam Filter Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b3467-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="b3467-p103">Sono stati aggiunti altri valori BCL che verranno inclusi in futuro. Nella tabella seguente sono elencati e descritti i valori BCL attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="b3467-p103">More BCL values are being added and will be included here in the future. The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b3467-126">**Valore BCL**</span><span class="sxs-lookup"><span data-stu-id="b3467-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="b3467-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b3467-127">**Description**</span></span> <br/> |
|<span data-ttu-id="b3467-128">0</span><span class="sxs-lookup"><span data-stu-id="b3467-128">0</span></span>  <br/> |<span data-ttu-id="b3467-129">Il messaggio non viene da un mittente in blocco.</span><span class="sxs-lookup"><span data-stu-id="b3467-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="b3467-130">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="b3467-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="b3467-131">Il messaggio è proveniente da un mittente in blocco che genera alcuni reclami.</span><span class="sxs-lookup"><span data-stu-id="b3467-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="b3467-132">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="b3467-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="b3467-133">Il messaggio è proveniente da un mittente in blocco che genera un numero misto di denunce.</span><span class="sxs-lookup"><span data-stu-id="b3467-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="b3467-134">8, 9</span><span class="sxs-lookup"><span data-stu-id="b3467-134">8, 9</span></span>  <br/> |<span data-ttu-id="b3467-135">Il messaggio è proveniente da un mittente in blocco che genera un numero elevato di denunce</span><span class="sxs-lookup"><span data-stu-id="b3467-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

