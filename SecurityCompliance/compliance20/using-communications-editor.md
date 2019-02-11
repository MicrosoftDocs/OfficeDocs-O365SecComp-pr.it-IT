---
title: Usare l'editor delle comunicazioni
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
ms.openlocfilehash: b148ff1a77cd9225a26f98e7612e9fb5b57331e3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706057"
---
# <a name="use-the-communications-editor"></a>Usare l'editor delle comunicazioni

Quando si definisce il contenuto del contenuto del portale, legale attesa notifiche e promemoria correlate le misure correttive, è possibile utilizzare l'Editor Communications per formattare e personalizzare in modo dinamico del contenuto.

## <a name="rich-text-editor"></a>Editor testo RTF 

Editor Communications consente di personalizzare il testo utilizzando le opzioni editor. Ad esempio, gli utenti possono modificare tipi di carattere, creare gli elenchi puntati, evidenziare il contenuto e altro ancora. 

## <a name="merge-field-variables"></a>Unire le variabili di campi

È possibile utilizzare variabili di unione posta elettronica da Editor Communications per incorporare gli attributi personalizzati depositaria nel corpo del testo di comunicazione. Quando inviato per la depositaria, il campo unione verrà visualizzato il campo corrispondente. Ad esempio, quando si invia a depositaria John Smith, il campo unione [nome depositaria] verrebbe convertito con il nome corrispondente. 

È possibile utilizzare campi unione email selezionando le icone di **campo unione** nella parte superiore del controllo editor testo RTF. I segnaposto verrà aggiunti base disattiva la posizione del puntatore degli utenti. 

### <a name="list-of-merge-field-variables"></a>Elenco di variabili di campi di stampa unione

| Nome del campo                  | Dettagli campo | 
| :------------------- | :------------------- |
| Nome visualizzato  | Il depositaria prima del nome e cognome. | 
| Collegamento di conferma | Un collegamento personalizzato per registrare il riconoscimento di ogni depositaria.|                 |
| Collegamento del portale     | Un collegamento personalizzato per il portale di conformità del depositaria.|                |
| Responsabile della emittente                   | L'indirizzo di posta elettronica dell'emittente ufficiale specificato.|                   |
| Data di emissione                   | Data in cui l'avviso è stato emesso (Time).              |