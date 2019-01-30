---
title: Utilizzando l'editor di comunicazioni
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
ms.openlocfilehash: 107f45510bcf70942c6f03bdfed0a9090f1d83c0
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607911"
---
# <a name="using-the-communications-editor"></a>Utilizzando l'Editor di comunicazioni
Quando si definisce il contenuto del contenuto del portale, legale attesa notifiche e promemoria correlate le misure correttive, è possibile utilizzare l'Editor Communications per formattare e personalizzare in modo dinamico del contenuto.

## <a name="rich-text-editor"></a>Editor testo RTF 

Editor Communications consente di personalizzare il testo utilizzando le opzioni editor. Ad esempio, gli utenti possono modificare tipi di carattere, creare gli elenchi puntati, evidenziare il contenuto e altro ancora. 

<<include screenshot>>

## <a name="merge-field-variables"></a>Unire le variabili di campi

È possibile utilizzare variabili di unione posta elettronica da Editor Communications per incorporare gli attributi personalizzati depositaria nel corpo del testo di comunicazione. Quando inviato per la depositaria, il campo unione verrà visualizzato il campo corrispondente. Ad esempio, quando si invia a depositaria John Smith, il campo unione [nome depositaria] verrebbe convertito con il nome corrispondente. 

È possibile utilizzare campi unione email selezionando le icone di **Campo unione** nella parte superiore del controllo editor testo RTF. I segnaposto verrà aggiunti base disattiva la posizione del puntatore degli utenti. 

### <a name="list-of-merge-field-variables"></a>Elenco di variabili di campi di stampa unione
| Nome del campo                  | Dettagli campo | 
| :------------------- | :-------------------: |
| Nome visualizzato  | Depositaria prima del nome e cognome | 
| Collegamento di conferma                 | Collegamento personalizzato per registrare il riconoscimento di ogni depositaria                 |
| Collegamento del portale     | Collegamento personalizzato per il portale di conformità del depositaria                 |
| Responsabile della emittente                   | Indirizzo di posta elettronica dell'emittente ufficiale specificato                   |
| Data di emissione                   | Data in cui l'avviso è stato emesso (UTC)              |