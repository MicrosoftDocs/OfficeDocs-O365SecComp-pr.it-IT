---
title: Riprovare la ricerca di contenuti per risolvere un errore di percorso contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Utilizzare il pulsante Riprova per risolvere ricerche di contenuto che presentano errori di percorso contenuto.
ms.openlocfilehash: 0fdc11593fec42e1f9f9b76fbbb408d9c16fd183
ms.sourcegitcommit: d5f841744b716fcf368c670009b61441f5a5eed2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2018
ms.locfileid: "27210189"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Riprovare la ricerca di contenuti per risolvere un errore di percorso contenuto

Quando si utilizza la ricerca del contenuto nel centro conformità protezione di Office 365 per cercare un numero molto elevato di cassette postali (ad esempio, la ricerca di cassette 100.000 postali o altri argomenti relativi a una singola ricerca contenuto), potrebbe essere visualizzato gli errori di ricerca che sono simili al seguente:

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Questi errori (con codici di errore di CS008 009 e CS012-002) indicano che non è riuscito ricerca di contenuti cercare i percorsi di contenuti specifici; In questo esempio, non sono state ricercate due cassette postali. Questi errori vengono visualizzati nella pagina Stato dettagli comparsa di ricerca del contenuto.

## <a name="cause-of-content-location-errors"></a>Causa di errori di percorso del contenuto

Durante la ricerca di un numero elevato di cassette postali, la ricerca viene distribuita tra migliaia di server in un Data Center Microsoft. In qualsiasi momento, potrebbe essere server specifici in stato dopo il riavvio o il processo di failover di copie ridondanti. In entrambi i casi, la richiesta di ricerca del contenuto per recuperare i dati verranno timeout. Nell'esempio precedente, gli errori per le cassette postali che non sono stati il risultato di scadere ricerca.

## <a name="resolving-content-location-errors"></a>Risoluzione degli errori di percorso del contenuto

Riavviare la ricerca spesso genererà errori simili in server diversi. Invece di riavvio di ricerca, fare clic sul pulsante **tentativi** viene visualizzato nella parte superiore della pagina dei risultati della ricerca.

![Fare clic sul pulsante Riprova per risolvere gli errori di percorso del contenuto](media/retrycontentsearch3.png)

Il risultato è il nuovo tentativo in corso la ricerca solo per le cassette postali non riuscite. Quando si riprovare la ricerca, i risultati sono stati correttamente restituiti vengono mantenuti.

## <a name="tips-to-avoid-content-location-errors"></a>Suggerimenti per evitare errori di percorso del contenuto

Ecco alcune delle cause degli errori di percorso contenuto aggiunta e alcuni suggerimenti che consentono di evitare di durante la ricerca di un numero elevato di cassette postali.

- La cassetta postale in corso la ricerca potrebbe essere non disponibile a causa di attività dell'utente. In questo caso, può limitare il servizio di ricerca in modo da impedire che la cassetta postale non sono più disponibili. Per evitare questo problema, provare a eseguire ricerche durante le ore di inattività.

- Query di ricerca potrebbe recupero troppo contenuto dalla cassetta postale. Se possibile, provare a restringere l'ambito della ricerca tramite parole chiave, data intervalli e le condizioni di ricerca.

- Troppi parole chiave o frasi di parole chiave quando si crea una query di ricerca utilizzando l' [elenco di parole chiave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). Quando si esegue una query di ricerca che utilizza l'elenco di parole chiave, il servizio essenzialmente viene eseguita una ricerca distinto per ogni riga nell'elenco delle parole chiave in modo che possono essere generate le statistiche. Se si utilizza l'elenco di parole chiave nelle query di ricerca, ridurre al minimo il numero di righe nell'elenco delle parole chiave o suddividere le parole chiave numeri in elenchi di dimensioni ridotte e creare una ricerca diversa per ogni elenco di parole chiave.

  > [!NOTE]
  > Per contribuire alla riduzione problemi causati da elenchi di grandi dimensioni parole chiave, l'utente è ora solo per un massimo di 20 righe nell'elenco delle parole chiave di una query di ricerca.

- Troppi ricerche eseguite nella stessa cassetta postale contemporaneamente. Se possibile, provare a eseguire una ricerca in un momento in qualsiasi una cassetta postale.

- Ricerca di un numero eccessivo di cassette postali in una singola ricerca. Consente di aumentare la probabilità di errori di percorso contenuto durante la ricerca di un numero molto elevato di cassette postali. Se possibile, provare a eseguire più ricerche in modo che ogni ricerca include un sottoinsieme delle cassette postali nell'organizzazione.

- Manutenzione necessaria in corso della cassetta postale. Se questo causa probabilmente non si verifica frequentemente, attendere un po' dopo l'errore di percorso contenuto e riprovare a eseguire la ricerca.
