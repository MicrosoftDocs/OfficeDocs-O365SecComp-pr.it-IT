---
title: Valori di livello di reclamo in blocco
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dell'elenco. Alcuni sono buoni mailer che inviano messaggi desiderati con contenuto pertinente ai propri abbonati. Questi messaggi generano alcuni reclami dai destinatari. Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari. Per distinguere questi tipi di messaggi di posta elettronica in blocco, viene assegnato un punteggio di livello di reclamo in blocco da parte di un messaggio di posta elettronica in blocco. Le valutazioni BCL variano da 1 a 9 a seconda di quanto è probabile che il mailer di posta in blocco debba generare reclami. Un mittente che ha un punteggio di BCL 9 può generare molti reclami dai destinatari, mentre non è probabile che un punteggio di BCL 3 generi molti reclami. Microsoft utilizza origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata. Questa valutazione è esposta nell'intestazione X-Microsoft-antispam di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere intestazioni dei messaggi di protezione da posta indesiderata.
ms.openlocfilehash: 490823f045e2e3fcf6b537d9717ab12abc323da6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152128"
---
# <a name="bulk-complaint-level-values"></a>Valori di livello di reclamo in blocco

I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dell'elenco. Alcuni sono buoni mailer che inviano messaggi desiderati con contenuto pertinente ai propri abbonati. Questi messaggi generano alcuni reclami dai destinatari. Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari. Per distinguere questi tipi di messaggi di posta elettronica in blocco, viene assegnato un punteggio di livello di reclamo in blocco da parte di un messaggio di posta elettronica in blocco. Le valutazioni BCL variano da 1 a 9 a seconda di quanto è probabile che il mailer di posta in blocco debba generare reclami. Un mittente che ha un punteggio di BCL 9 può generare molti reclami dai destinatari, mentre non è probabile che un punteggio di BCL 3 generi molti reclami. Microsoft utilizza origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata. Questa valutazione è esposta nell'intestazione **X-Microsoft-antispam** di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere [intestazioni dei messaggi](anti-spam-message-headers.md)di protezione da posta indesiderata. 
  
È possibile utilizzare i valori BCL per impostare il livello di filtro di massa desiderato per l'organizzazione, attenendosi alla procedura descritta in [Configure Your Spam Filter Policies](configure-your-spam-filter-policies.md).
  
Sono stati aggiunti altri valori BCL che verranno inclusi in futuro. Nella tabella seguente sono elencati e descritti i valori BCL attualmente in uso.
  
|||
|:-----|:-----|
|**Valore BCL** <br/> |**Descrizione** <br/> |
|0  <br/> |Il messaggio non viene da un mittente in blocco.  <br/> |
|1, 2, 3  <br/> |Il messaggio è proveniente da un mittente in blocco che genera alcuni reclami.  <br/> |
|4, 5, 6, 7  <br/> |Il messaggio è proveniente da un mittente in blocco che genera un numero misto di denunce.  <br/> |
|8, 9  <br/> |Il messaggio è proveniente da un mittente in blocco che genera un numero elevato di denunce  <br/> |
   

