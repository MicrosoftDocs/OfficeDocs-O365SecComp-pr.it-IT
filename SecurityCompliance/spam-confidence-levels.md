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
# <a name="spam-confidence-levels"></a>Livelli di sicurezza della protezione contro la posta indesiderata

Quando un messaggio di posta elettronica viene individuato dal filtro di protezione da posta indesiderata, viene assegnato un punteggio di posta indesiderata. Questo punteggio viene associato a un livello di probabilità di posta indesiderata (SCL, Spam Confidence Level) e contrasseganto nell'X-header. Il servizio agisce sui messaggi a seconda della valutazione SCL sul livello di probabilità di posta indesiderata. Nella tabella seguente viene mostrato come le diverse valutazioni SCL vengono interpretate dai filtri e come vengono intraprese le azioni sui messaggi in ingresso per ogni valutazione.
  
|**Valutazione SCL**|**Interpretazione del livello di sicurezza della protezione contro la posta indesiderata**|**Azione predefinita**|
|:-----|:-----|:-----|
|-1|Non posta indesiderata proveniente da un mittente sicuro, un destinatario sicuro o un indirizzo IP elencato sicuro (partner attendibile).|Recapito del messaggio nella Posta in arrivo del destinatario.|
|0, 1|Non posta indesiderata perché il messaggio è stato analizzato e determinato come pulito.|Recapito del messaggio nella Posta in arrivo del destinatario.|
|5, 6|Posta indesiderata|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|7, 8, 9|Alta probabilità di posta indesiderata|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
   
> [!TIP]
> Le valutazioni SCL di 2, 3, 4, 7 e 8 non vengono impostate dal servizio. Una valutazione SCL di 5 o 6 è considerata sospetta di posta indesiderata, che è meno sicura di essere posta indesiderata rispetto a una valutazione SCL pari a 9, considerata determinata posta indesiderata. Azioni diverse per la posta indesiderata e la posta indesiderata con elevata sicurezza possono essere configurate tramite criteri di filtro dei contenuti nell'interfaccia di amministrazione Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata. È inoltre possibile impostare la classificazione SCL per i messaggi che soddisfano condizioni specifiche utilizzando regole del flusso di posta (note anche come regole di trasporto), come descritto in [Use Mail Flow Rules to impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Se si utilizza una regola del flusso di posta per impostare SCL di 7, 8 o 9, il messaggio verrà considerato come posta indesiderata con elevata attendibilità. 
  
||
|:-----|
|![Piccola icona per LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuovo utente di Office 365?**         Sono disponibili esercitazioni video gratuite per **Office 365 admins and IT pros** grazie a LinkedIn Learning.|
   

