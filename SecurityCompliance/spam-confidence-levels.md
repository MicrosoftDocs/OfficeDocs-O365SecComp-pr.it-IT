---
title: Livelli di sicurezza della protezione contro la posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
description: Quando un messaggio di posta elettronica viene individuato dal filtro di protezione da posta indesiderata, viene assegnato un punteggio di posta indesiderata. Questo punteggio viene associato a un livello di probabilità di posta indesiderata (SCL, Spam Confidence Level) e contrasseganto nell'X-header. Il servizio agisce sui messaggi a seconda della valutazione SCL sul livello di probabilità di posta indesiderata. Nella tabella seguente viene mostrato come le diverse valutazioni SCL vengono interpretate dai filtri e come vengono intraprese le azioni sui messaggi in ingresso per ogni valutazione.
ms.openlocfilehash: cd33f440828761ab8cb496d9eff07288d974514c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026283"
---
# <a name="spam-confidence-levels"></a>Livelli di sicurezza della protezione contro la posta indesiderata

Quando un messaggio di posta elettronica viene individuato dal filtro di protezione da posta indesiderata, viene assegnato un punteggio di posta indesiderata. Questo punteggio viene associato a un livello di probabilità di posta indesiderata (SCL, Spam Confidence Level) e contrasseganto nell'X-header. Il servizio agisce sui messaggi a seconda della valutazione SCL sul livello di probabilità di posta indesiderata. Nella tabella seguente viene mostrato come le diverse valutazioni SCL vengono interpretate dai filtri e come vengono intraprese le azioni sui messaggi in ingresso per ogni valutazione.
  
|**Valutazione SCL**|**Interpretazione del livello di sicurezza della protezione contro la posta indesiderata**|**Azione predefinita**|
|:-----|:-----|:-----|
|-1  <br/> |I messaggi di posta non indesiderata provengono da mittenti o destinatari attendibili o da un elenco di indirizzi IP attendibili (partner attendibili)  <br/> |Recapito del messaggio nella Posta in arrivo del destinatario.  <br/> |
|0, 1  <br/> |I messaggi di posta non sono indesiderati perché sono stati analizzati ed è stato stabilito che sono puliti  <br/> |Recapito del messaggio nella Posta in arrivo del destinatario.  <br/> |
|5, 6  <br/> | Posta indesiderata  <br/> |Recapito del messaggio nella cartella Posta indesiderata del destinatario  <br/> |
|7, 8, 9  <br/> |Alta probabilità di posta indesiderata  <br/> |Recapito del messaggio nella cartella Posta indesiderata del destinatario  <br/> |
   
> [!TIP]
> Il servizio non utilizza le valutazioni SCL 2, 3, 4, 7 e 8. Una valutazione SCL di 5 o 6 viene considerata presumibilmente di posta indesiderata, il quale è sicuramente meno rispetto ad una valutazione di 9, che è considerata sicuramente di posta indesiderata. È possibile configurare azioni differenti per la posta indesiderata e per probabilità alta di posta indesiderata tramite i criteri di filtro del contenuto nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md). È anche possibile impostare il livello di probabilità di posta indesiderata per i messaggi che soddisfano specifiche condizioni tramite le regole di trasporto, come descritto in [Utilizzare le regole di flusso di posta elettronica per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Se si utilizza una regola di trasporto per impostare il livello di probabilità di posta indesiderata su 7, 8 o 9, il messaggio verrà considerato come posta con elevata probabilità di essere posta indesiderata. 
  
||
|:-----|
|![Piccola icona per LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuovo utente di Office 365?**         Sono disponibili esercitazioni video gratuite per **Office 365 admins and IT pros** grazie a LinkedIn Learning. |
   

