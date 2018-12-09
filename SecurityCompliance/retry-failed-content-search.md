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
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="aca40-103">Riprovare la ricerca di contenuti per risolvere un errore di percorso contenuto</span><span class="sxs-lookup"><span data-stu-id="aca40-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="aca40-104">Quando si utilizza la ricerca del contenuto nel centro conformità protezione di Office 365 per cercare un numero molto elevato di cassette postali (ad esempio, la ricerca di cassette 100.000 postali o altri argomenti relativi a una singola ricerca contenuto), potrebbe essere visualizzato gli errori di ricerca che sono simili al seguente:</span><span class="sxs-lookup"><span data-stu-id="aca40-104">When you use Content Search in the Office 365 Security & Compliance Center to search a very large number of mailboxes (for example, searching 100,000 mailboxes or more in a single Content Search), you may get search errors that are similar to the following:</span></span>

```
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="aca40-p101">Questi errori (con codici di errore di CS008 009 e CS012-002) indicano che non è riuscito ricerca di contenuti cercare i percorsi di contenuti specifici; In questo esempio, non sono state ricercate due cassette postali. Questi errori vengono visualizzati nella pagina Stato dettagli comparsa di ricerca del contenuto.</span><span class="sxs-lookup"><span data-stu-id="aca40-p101">These errors (with error codes of CS008-009 and CS012-002) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched. These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="aca40-107">Causa di errori di percorso del contenuto</span><span class="sxs-lookup"><span data-stu-id="aca40-107">Cause of content location errors</span></span>

<span data-ttu-id="aca40-p102">Durante la ricerca di un numero elevato di cassette postali, la ricerca viene distribuita tra migliaia di server in un Data Center Microsoft. In qualsiasi momento, potrebbe essere server specifici in stato dopo il riavvio o il processo di failover di copie ridondanti. In entrambi i casi, la richiesta di ricerca del contenuto per recuperare i dati verranno timeout. Nell'esempio precedente, gli errori per le cassette postali che non sono stati il risultato di scadere ricerca.</span><span class="sxs-lookup"><span data-stu-id="aca40-p102">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter. At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies. In either of these cases, the Content Search's request to retrieve data will timeout. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="aca40-112">Risoluzione degli errori di percorso del contenuto</span><span class="sxs-lookup"><span data-stu-id="aca40-112">Resolving content location errors</span></span>

<span data-ttu-id="aca40-p103">Riavviare la ricerca spesso genererà errori simili in server diversi. Invece di riavvio di ricerca, fare clic sul pulsante **tentativi** viene visualizzato nella parte superiore della pagina dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="aca40-p103">Restarting the search will often result in similar errors on different servers. Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Fare clic sul pulsante Riprova per risolvere gli errori di percorso del contenuto](media/retrycontentsearch3.png)

<span data-ttu-id="aca40-p104">Il risultato è il nuovo tentativo in corso la ricerca solo per le cassette postali non riuscite. Quando si riprovare la ricerca, i risultati sono stati correttamente restituiti vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="aca40-p104">This will result in the retrying the search only for the mailboxes that failed. When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="aca40-118">Suggerimenti per evitare errori di percorso del contenuto</span><span class="sxs-lookup"><span data-stu-id="aca40-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="aca40-119">Ecco alcune delle cause degli errori di percorso contenuto aggiunta e alcuni suggerimenti che consentono di evitare di durante la ricerca di un numero elevato di cassette postali.</span><span class="sxs-lookup"><span data-stu-id="aca40-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="aca40-p105">La cassetta postale in corso la ricerca potrebbe essere non disponibile a causa di attività dell'utente. In questo caso, può limitare il servizio di ricerca in modo da impedire che la cassetta postale non sono più disponibili. Per evitare questo problema, provare a eseguire ricerche durante le ore di inattività.</span><span class="sxs-lookup"><span data-stu-id="aca40-p105">The mailbox being searched might be busy due to user activity. In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable. To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="aca40-p106">Query di ricerca potrebbe recupero troppo contenuto dalla cassetta postale. Se possibile, provare a restringere l'ambito della ricerca tramite parole chiave, data intervalli e le condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="aca40-p106">The search query might be retrieving too much content from the mailbox. If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="aca40-p107">Troppi parole chiave o frasi di parole chiave quando si crea una query di ricerca utilizzando l' [elenco di parole chiave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). Quando si esegue una query di ricerca che utilizza l'elenco di parole chiave, il servizio essenzialmente viene eseguita una ricerca distinto per ogni riga nell'elenco delle parole chiave in modo che possono essere generate le statistiche. Se si utilizza l'elenco di parole chiave nelle query di ricerca, ridurre al minimo il numero di righe nell'elenco delle parole chiave o suddividere le parole chiave numeri in elenchi di dimensioni ridotte e creare una ricerca diversa per ogni elenco di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="aca40-p107">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated. If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="aca40-128">Per contribuire alla riduzione problemi causati da elenchi di grandi dimensioni parole chiave, l'utente è ora solo per un massimo di 20 righe nell'elenco delle parole chiave di una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="aca40-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="aca40-p108">Troppi ricerche eseguite nella stessa cassetta postale contemporaneamente. Se possibile, provare a eseguire una ricerca in un momento in qualsiasi una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="aca40-p108">Too many searches are being performed on the same mailbox at the same time. If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="aca40-p109">Ricerca di un numero eccessivo di cassette postali in una singola ricerca. Consente di aumentare la probabilità di errori di percorso contenuto durante la ricerca di un numero molto elevato di cassette postali. Se possibile, provare a eseguire più ricerche in modo che ogni ricerca include un sottoinsieme delle cassette postali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aca40-p109">Searching too many mailboxes in a single search. The probability of content location errors increases when searching a very large number of mailboxes. If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="aca40-p110">Manutenzione necessaria in corso della cassetta postale. Se questo causa probabilmente non si verifica frequentemente, attendere un po' dopo l'errore di percorso contenuto e riprovare a eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="aca40-p110">Required maintenance is being performed on the mailbox. Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
