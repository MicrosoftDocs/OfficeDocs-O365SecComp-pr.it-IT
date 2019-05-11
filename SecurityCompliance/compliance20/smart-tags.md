---
title: Configurare gli smart tag per il rilevamento dei privilegi avvocato-client in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 721426f23aec862bcefbd13b8e61415dac3aeb27
ms.sourcegitcommit: aa8ea45d5854f8906714e0a407937585ec7993ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2019
ms.locfileid: "33951701"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a>Configurare gli smart tag per la revisione con supporto ML in Advanced eDiscovery

Le funzionalità di apprendimento automatico in Advanced eDiscovery devono contribuire a rendere più efficienti i processi decisionali sui documenti. Smart tag è un modo per portare le funzionalità di apprendimento automatico in cui vengono registrate le decisioni: Tag e gruppi di tag. Quando si crea un gruppo di smart tag, le decisioni del modello ML mappate al gruppo verranno mostrate in linea con i tag del gruppo in modo da visualizzare le informazioni in linea, in cui sono contestualemente più sensate.

## <a name="how-to-set-up-a-smart-tag-group"></a>Come configurare un gruppo di smart tag

1. In un set di revisione, andare a **Manage Review set** -> **gestire i tag**.

2. Fare clic sul menu a discesa accanto a **Aggiungi tag gruppo** e selezionare **Aggiungi smart tag Group**.

3. Selezionare il modello che si desidera mappare a questo gruppo. Verrà creata una sezione Tag e N tag figlio, dove N è il numero di output possibili del modello. Ad esempio, il modello di rilevamento dei privilegi avvocato-client ha due possibili output-privilegiati e non privilegiati; Se si seleziona questo modello, verranno creati due tag figlio nel set di revisione, ognuno corrispondente a uno dei possibili output.

4. Rinominare il gruppo di tag e i tag come si può vedere in forma.

## <a name="how-to-use-a-smart-tag-group"></a>Come usare un gruppo di smart tag

Quando si esamina un documento, i risultati del modello verranno esposti accanto al valore del tag appropriato. Ad esempio, se si dispone di un gruppo di smart tag per il rilevamento dei privilegi avvocato-client e si esamina un documento che il modello ha deciso è potenzialmente privilegiato, verrà visualizzato il motivo accanto al tag appropriato. È importante tenere presente che il tag non viene applicato automaticamente. per tutti gli effetti, i tag all'interno di un gruppo di smart tag agiscono esattamente come i tag normali, tranne per il fatto che espongono i risultati del modello accanto a essi, se necessario.