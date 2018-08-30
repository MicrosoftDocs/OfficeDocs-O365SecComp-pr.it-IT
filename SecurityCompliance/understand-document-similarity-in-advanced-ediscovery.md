---
title: Informazioni sulla similarità dei documenti di Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Vedere funzionamento documento similarità valore, il livello minimo di somiglianza per due file da prendere in considerazione quasi duplicati in Office 365 avanzate eDiscovery. '
ms.openlocfilehash: 39cd8c31204f0164f6b52c71fa707253cb22758a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530630"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a>Informazioni sulla similarità dei documenti di Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In eDiscovery avanzate, similarità documento è il livello minimo di somiglianza necessario per i due documenti devono essere considerati quasi duplicati.
  
> [!TIP]
> Per la maggior parte delle applicazioni di business, è consigliabile utilizzare un valore similarità di 60-75%. Per i materiali, il riconoscimento ottico caratteri (OCR) molto scarso di qualità inferiore similarità valori possono essere applicati. 
  
> [!NOTE]
> Dopo che è impostata e l'esecuzione di un determinato case, il valore similarità non può essere modificato. 
  
All'interno di un set di duplicati Near (ND), potrebbe essere documenti con un livello di somiglianza di sotto della soglia similarità. Per un documento a un set di ND, deve essere presente almeno un documento in ND impostare con un livello di somiglianza che superano la similarità. 
  
Si supponga ad esempio la similarità è impostata su 80%, documento F1 analogo al documento F2 a livello di 85% e documenti F2 utilizza il formato documento F3 a livello del 90%. 
  
Tuttavia, documento F1 potrebbe essere simile documento F3 a livello di solo il 70%, di sotto della soglia. Tuttavia, in questo esempio i documenti F1, F2 e F3 uno ND vengono visualizzati tutti impostati. Analogamente, utilizzando un valore similarità 80%, si può avere creato due set, EquiSet-1 e 2 EquiSet. EquiSet 1 contiene documenti E1 ed E2. Equiset 2 contiene documenti F1, F2 e F3. 
  
Come indicato di seguito sono illustrati i livelli di somiglianza:
  
![Somiglianza documento](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
Si presuppone che un altro documento, X1, viene inserito. Somiglianza tra X1 ed E3 è 87%. Analogamente, la somiglianza tra X1 e F1 è 92%. Di conseguenza, EquiSet -1, EquiSet -2 e X1 sono stati unificati nello un ND set.
  
![Somiglianza documento](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> Se i due documenti vengono assegnate a un gruppo ND, rimangono contemporaneamente nello stesso set di ND, anche se altri documenti vengono aggiunte all'insieme o se gli insiemi vengono uniti. 
  
Dopo l'unione di insiemi, è possibile modificare il documento Pivot quando vengono aggiunti nuovi documenti a un set di. 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Impostazione delle opzioni di analisi](set-analyze-options-in-advanced-ediscovery.md)
  
[Impostazione Ignora testo](set-ignore-text-in-advanced-ediscovery.md)
  
[Impostazioni avanzate di analisi di impostazione](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Visualizzazione dei risultati di analisi](view-analyze-results-in-advanced-ediscovery.md)

