---
title: Livelli di sicurezza della protezione contro la posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Quando un messaggio di posta elettronica viene individuato dal filtro di protezione da posta indesiderata, viene assegnato un punteggio di posta indesiderata. Questo punteggio viene associato a un livello di probabilità di posta indesiderata (SCL, Spam Confidence Level) e contrasseganto nell'X-header. Il servizio agisce sui messaggi a seconda della valutazione SCL sul livello di probabilità di posta indesiderata. Nella tabella seguente viene mostrato come le diverse valutazioni SCL vengono interpretate dai filtri e come vengono intraprese le azioni sui messaggi in ingresso per ogni valutazione.
ms.openlocfilehash: e7e8e29a7c3d4a3f09d674f72a400d27746e9081
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341247"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="52974-106">Livelli di sicurezza della protezione contro la posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="52974-106">Spam confidence levels</span></span>

<span data-ttu-id="52974-p102">Quando un messaggio di posta elettronica viene individuato dal filtro di protezione da posta indesiderata, viene assegnato un punteggio di posta indesiderata. Questo punteggio viene associato a un livello di probabilità di posta indesiderata (SCL, Spam Confidence Level) e contrasseganto nell'X-header. Il servizio agisce sui messaggi a seconda della valutazione SCL sul livello di probabilità di posta indesiderata. Nella tabella seguente viene mostrato come le diverse valutazioni SCL vengono interpretate dai filtri e come vengono intraprese le azioni sui messaggi in ingresso per ogni valutazione.</span><span class="sxs-lookup"><span data-stu-id="52974-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="52974-111">**Valutazione SCL**</span><span class="sxs-lookup"><span data-stu-id="52974-111">**SCL Rating**</span></span>|<span data-ttu-id="52974-112">**Interpretazione del livello di sicurezza della protezione contro la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="52974-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="52974-113">**Azione predefinita**</span><span class="sxs-lookup"><span data-stu-id="52974-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="52974-114">-1</span><span class="sxs-lookup"><span data-stu-id="52974-114">-1</span></span>|<span data-ttu-id="52974-115">Non posta indesiderata proveniente da un mittente sicuro, un destinatario sicuro o un indirizzo IP elencato sicuro (partner attendibile).</span><span class="sxs-lookup"><span data-stu-id="52974-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="52974-116">Recapito del messaggio nella Posta in arrivo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="52974-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="52974-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="52974-117">0, 1</span></span>|<span data-ttu-id="52974-118">Non posta indesiderata perché il messaggio è stato analizzato e determinato come pulito.</span><span class="sxs-lookup"><span data-stu-id="52974-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="52974-119">Recapito del messaggio nella Posta in arrivo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="52974-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="52974-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="52974-120">5, 6</span></span>|<span data-ttu-id="52974-121">Posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="52974-121">Spam</span></span>|<span data-ttu-id="52974-122">Recapito del messaggio nella cartella Posta indesiderata del destinatario</span><span class="sxs-lookup"><span data-stu-id="52974-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="52974-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="52974-123">7, 8, 9</span></span>|<span data-ttu-id="52974-124">Alta probabilità di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="52974-124">High confidence spam</span></span>|<span data-ttu-id="52974-125">Recapito del messaggio nella cartella Posta indesiderata del destinatario</span><span class="sxs-lookup"><span data-stu-id="52974-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="52974-p103">Le valutazioni SCL di 2, 3, 4, 7 e 8 non vengono impostate dal servizio. Una valutazione SCL di 5 o 6 è considerata sospetta di posta indesiderata, che è meno sicura di essere posta indesiderata rispetto a una valutazione SCL pari a 9, considerata determinata posta indesiderata. Azioni diverse per la posta indesiderata e la posta indesiderata con elevata sicurezza possono essere configurate tramite criteri di filtro dei contenuti nell'interfaccia di amministrazione Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata. È inoltre possibile impostare la classificazione SCL per i messaggi che soddisfano condizioni specifiche utilizzando regole del flusso di posta (note anche come regole di trasporto), come descritto in [Use Mail Flow Rules to impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Se si utilizza una regola del flusso di posta per impostare SCL di 7, 8 o 9, il messaggio verrà considerato come posta indesiderata con elevata attendibilità.</span><span class="sxs-lookup"><span data-stu-id="52974-p103">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service. An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam. Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="52974-p104">![Piccola icona per LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuovo utente di Office 365?**         Sono disponibili esercitazioni video gratuite per **Office 365 admins and IT pros** grazie a LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="52974-p104">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

