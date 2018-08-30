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
# <a name="bulk-complaint-level-values"></a>Valori al livello reclamo massa

Blocco Mailer variano nei modelli di invio, la creazione di contenuto e alle pratiche di acquisizione di elenco. Alcuni lavoratori sono Mailer blocco buona che inviano intendeva i messaggi con il contenuto pertinente per i sottoscrittori. Questi messaggi generano reclami alcuni dei destinatari. Altri Mailer blocco inviare messaggi indesiderati strettamente essere simile a quella della posta indesiderata e generano reclami numero di destinatari. Per distinguere i tipi di Mailer di blocco, i messaggi provenienti da Mailer blocco sono assegnati un blocco reclamo livello (libreria di classi base). Libreria di classi base valutazioni compreso tra 1 e 9 in base al quale probabilità mailer blocco è per la generazione di reclami. Un mittente che presenta un livello di libreria di classi base 9 è probabile che venga generato reclami numero di destinatari, mentre una valutazione della libreria di classi base 3 è improbabile che per la generazione di reclami molti. Microsoft utilizza origini sia interne che terze parti per identificare posta inviata in blocco e determinare la libreria di classi base appropriato. Questa classificazione verrà reso disponibile nell'intestazione **X-Microsoft-Antispam** di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere [anti-spam message headers](anti-spam-message-headers.md). 
  
È possibile utilizzare i valori di libreria di classi base per impostare il livello di blocco filtro che l'organizzazione richiede seguendo i passaggi di [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md)desiderato.
  
Numero di valori di libreria di classi base viene aggiunti e verrà inclusi qui in futuro. Nella tabella seguente vengono elencati e descritti i valori di libreria di classi base che sono attualmente in uso.
  
|||
|:-----|:-----|
|**Libreria di classi base valore** <br/> |**Descrizione** <br/> |
|0  <br/> |Il messaggio non è da un mittente in blocco.  <br/> |
|1, 2, 3  <br/> |Il messaggio è da un mittente di blocco che genera alcuni reclami.  <br/> |
|4, 5, 6, 7  <br/> |Il messaggio proviene da un mittente di blocco che genera un numero misto di reclami.  <br/> |
|8, 9  <br/> |Il messaggio proviene da un mittente di blocco che genera un numero elevato di reclami  <br/> |
   

