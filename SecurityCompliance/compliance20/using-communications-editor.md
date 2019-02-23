---
title: Usare l'editor delle comunicazioni
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 967320aeb960258d77d90cca4e3b681849f9952e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215806"
---
# <a name="use-the-communications-editor"></a>Usare l'editor delle comunicazioni

Quando si definisce il contenuto del contenuto del portale, le notifiche di blocco legale e i promemoria e le escalation correlati, è possibile utilizzare l'editor comunicazioni per formattare e personalizzare dinamicamente il contenuto.

## <a name="rich-text-editor"></a>Editor di testo RTF 

L'editor comunicazioni consente all'utente di personalizzare il testo utilizzando le opzioni dell'editor. Ad esempio, gli utenti possono modificare i tipi di carattere, creare elenchi puntati, evidenziare il contenuto e altro ancora. 

## <a name="merge-field-variables"></a>Unire le variabili di campo

È possibile sfruttare le variabili di stampa unione dall'editor comunicazioni per incorporare gli attributi di un custode personalizzato nel testo del corpo di una comunicazione. Quando viene inviato al custode, il campo unione verrà popolato con il campo corrispondente. Quando, ad esempio, viene inviato al custode John Smith, il campo merge [nome custode] verrebbe convertito con il nome corrispondente. 

È possibile utilizzare i campi unione di posta elettronica selezionando le icone del **campo unione** nella parte superiore del controllo editor RTF. Il segnaposto verrà aggiunto in base alla posizione del cursore degli utenti. 

### <a name="list-of-merge-field-variables"></a>Elenco delle variabili di campo unione

| Nome del campo                  | Dettagli sul campo | 
| :------------------- | :------------------- |
| Nome visualizzato  | Nome e cognome del custode. | 
| Collegamento di conferma | Un collegamento personalizzato per registrare il riconoscimento di ogni custode.|                 |
| Collegamento portale     | Un collegamento personalizzato per il portale di conformità del custode.|                |
| Responsabile del rilascio                   | L'indirizzo di posta elettronica del responsabile del rilascio specificato.|                   |
| Data di emissione                   | La data in cui è stato emesso l'avviso (UTC).              |