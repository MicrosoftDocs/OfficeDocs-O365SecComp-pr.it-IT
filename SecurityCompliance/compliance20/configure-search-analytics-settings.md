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
# <a name="configure-search-and-analytics-settings"></a>Configurare le impostazioni di ricerca e analitica


## <a name="near-duplicates-and-email-threading"></a>Quasi duplicati e posta elettronica del threading

In questa sezione, è possibile impostare i parametri per il rilevamento duplicati, quasi duplicati e posta elettronica threading.

- Abilita/Disabilita: includa il rilevamento duplicato, quasi duplicati e posta elettronica threading come parte del flusso analitica se abilitato. Dal momento che si basano su tra loro, è necessario abilitare tutti gli elementi o disabilitare tutti gli utenti.

- Soglia: se il livello similarità di due documenti è superiore alla soglia, verranno messe nello stesso quasi duplicati set.

- Nascondere i duplicati per impostazione predefinita: se questa impostazione è attivata, sarà possibile applicare un filtro per nascondere documenti duplicati nella working set per impostazione predefinita. Il filtro è possibile rimuovere manualmente in working set se necessario.

- Numero minimo/massimo di parole: quasi duplicati e posta elettronica threading verrà eseguito solo su documenti che contengono almeno il numero minimo di parole e al massimo il numero massimo di parole. Per ulteriori informazioni, vedere [quasi duplicati](near-duplicates.md) e [posta elettronica threading](email-threading.md).

## <a name="themes"></a>Temi

In questa sezione, è possibile impostare i parametri per i temi.

- Abilita/Disabilita: includere temi clustering come parte del flusso analitica se abilitato.
- Modificare il numero massimo di temi in modo dinamico in modo dinamico: in alcuni casi, non vi sono documenti è insufficiente per produrre il numero di temi desiderato. Se questa impostazione è attivata, quindi anziché il tentativo di forzare il numero massimo desiderato dei temi, il sistema regola numero massimo di temi in modo dinamico.
- Numero massimo di temi: numero di temi desiderato
- Includere i numeri dei temi: se abilitato, includerà numeri durante la generazione di temi.  

## <a name="optical-character-recognition-ocr"></a>Riconoscimento ottico dei caratteri (OCR)

Quando questa impostazione è attivata, OCR verrà eseguito su immagini che vengono caricate in working set in modo che possano essere disponibili per le ricerche.

## <a name="ignore-text"></a>Ignora testo

Vi sono istanze in determinate testi è destinata a diminuire la qualità dei analitica, ad esempio lunghi dichiarazioni di non responsabilità che vengono aggiunti alcuni messaggi di posta elettronica indipendentemente dal contenuto del messaggio di posta elettronica. Se si conoscono tali casi, è possibile escludere il testo da analitica specificando il testo (è supportata RegEx) e i moduli che dovrebbe essere escluse testo.