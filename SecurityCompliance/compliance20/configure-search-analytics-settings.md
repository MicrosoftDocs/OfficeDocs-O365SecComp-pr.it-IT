---
title: Configurare le impostazioni di ricerca e analitica
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
ms.openlocfilehash: d9528a4bcfaa77f2e232b25d03eda46cce42ebb9
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607901"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="314d2-102">Configurare le impostazioni di ricerca e analitica</span><span class="sxs-lookup"><span data-stu-id="314d2-102">Configure search and analytics settings</span></span>


## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="314d2-103">Quasi duplicati e posta elettronica del threading</span><span class="sxs-lookup"><span data-stu-id="314d2-103">Near duplicates and email threading</span></span>

<span data-ttu-id="314d2-104">In questa sezione, è possibile impostare i parametri per il rilevamento duplicati, quasi duplicati e posta elettronica threading.</span><span class="sxs-lookup"><span data-stu-id="314d2-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="314d2-p101">Abilita/Disabilita: includa il rilevamento duplicato, quasi duplicati e posta elettronica threading come parte del flusso analitica se abilitato. Dal momento che si basano su tra loro, è necessario abilitare tutti gli elementi o disabilitare tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="314d2-p101">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled. Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="314d2-107">Soglia: se il livello similarità di due documenti è superiore alla soglia, verranno messe nello stesso quasi duplicati set.</span><span class="sxs-lookup"><span data-stu-id="314d2-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="314d2-p102">Nascondere i duplicati per impostazione predefinita: se questa impostazione è attivata, sarà possibile applicare un filtro per nascondere documenti duplicati nella working set per impostazione predefinita. Il filtro è possibile rimuovere manualmente in working set se necessario.</span><span class="sxs-lookup"><span data-stu-id="314d2-p102">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default. The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="314d2-p103">Numero minimo/massimo di parole: quasi duplicati e posta elettronica threading verrà eseguito solo su documenti che contengono almeno il numero minimo di parole e al massimo il numero massimo di parole. Per ulteriori informazioni, vedere [quasi duplicati](near-duplicates.md) e [posta elettronica threading](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="314d2-p103">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words. For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="314d2-112">Temi</span><span class="sxs-lookup"><span data-stu-id="314d2-112">Themes</span></span>

<span data-ttu-id="314d2-113">In questa sezione, è possibile impostare i parametri per i temi.</span><span class="sxs-lookup"><span data-stu-id="314d2-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="314d2-114">Abilita/Disabilita: includere temi clustering come parte del flusso analitica se abilitato.</span><span class="sxs-lookup"><span data-stu-id="314d2-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="314d2-p104">Modificare il numero massimo di temi in modo dinamico in modo dinamico: in alcuni casi, non vi sono documenti è insufficiente per produrre il numero di temi desiderato. Se questa impostazione è attivata, quindi anziché il tentativo di forzare il numero massimo desiderato dei temi, il sistema regola numero massimo di temi in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="314d2-p104">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes. If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="314d2-117">Numero massimo di temi: numero di temi desiderato</span><span class="sxs-lookup"><span data-stu-id="314d2-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="314d2-118">Includere i numeri dei temi: se abilitato, includerà numeri durante la generazione di temi.</span><span class="sxs-lookup"><span data-stu-id="314d2-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="314d2-119">Riconoscimento ottico dei caratteri (OCR)</span><span class="sxs-lookup"><span data-stu-id="314d2-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="314d2-120">Quando questa impostazione è attivata, OCR verrà eseguito su immagini che vengono caricate in working set in modo che possano essere disponibili per le ricerche.</span><span class="sxs-lookup"><span data-stu-id="314d2-120">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="314d2-121">Ignora testo</span><span class="sxs-lookup"><span data-stu-id="314d2-121">Ignore text</span></span>

<span data-ttu-id="314d2-p105">Vi sono istanze in determinate testi è destinata a diminuire la qualità dei analitica, ad esempio lunghi dichiarazioni di non responsabilità che vengono aggiunti alcuni messaggi di posta elettronica indipendentemente dal contenuto del messaggio di posta elettronica. Se si conoscono tali casi, è possibile escludere il testo da analitica specificando il testo (è supportata RegEx) e i moduli che dovrebbe essere escluse testo.</span><span class="sxs-lookup"><span data-stu-id="314d2-p105">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email. If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>