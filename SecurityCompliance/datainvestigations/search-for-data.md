---
title: Ricerca di dati in un'indagine
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 5f52f26c4443addd0e108794e1d3635a9b8efb98
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030230"
---
# <a name="search-for-data-in-an-investigation"></a>Ricerca di dati in un'indagine

Nella scheda **ricerca** in un'analisi dei dati è possibile cercare i dati riservati, confidenziali o sensibili nei percorsi di contenuto di Office 365 utilizzando parole chiave e condizioni. 

Dopo aver eseguito una ricerca, è possibile visualizzare le statistiche sugli elementi restituiti dalla ricerca, ad esempio i percorsi di contenuto con la maggior parte degli elementi corrispondenti alla query di ricerca. È inoltre possibile visualizzare in anteprima un sottoinsieme dei risultati. Dopo aver identificato il set di documenti che si desidera approfondire, è possibile aggiungere i risultati della ricerca a un set di prove per elaborarli e analizzarli ulteriormente.

## <a name="create-a-search"></a>Create a search

1. In un'indagine fare clic sulla scheda **ricerche** e quindi fare clic su **nuova ricerca**. 

    Verrà visualizzata una procedura guidata che guiderà l'utente nel processo di creazione di una ricerca.

2. Immettere un nome di ricerca e una descrizione facoltativa per la ricerca.

3. Definire i criteri di ricerca. È possibile aggiungere condizioni per la ricerca utilizzando le schede delle condizioni predefinite o utilizzando i nomi delle proprietà di ricerca nella query di parole chiave. Per ulteriori informazioni, vedere [creazione di query di ricerca](build-search-queries.md).

4. Scegliere i percorsi di contenuto (origini dati) da cercare. È possibile ambire la ricerca selezionando i percorsi di contenuto di persone specifiche di interesse (se è stato aggiunto un oggetto all'inchiesta). Se sono state aggiunte persone di interesse per l'indagine, è possibile aggiungerle seguendo la procedura descritta in [Manage people of interest](manage-people-of-interest.md#add-people-of-interest).
 
    In alcuni casi, potrebbe essere necessario eseguire una ricerca in tutti i percorsi di contenuto dell'organizzazione. in alternativa, potrebbe essere necessario cercare percorsi che non sono di proprietà di una persona specifica. In questo scenario, è possibile scegliere di eseguire una ricerca nell'intera organizzazione o in tutte le posizioni per uno specifico servizio di Office 365, ad esempio Exchange, SharePoint, OneDrive of business o teams.

5. Salvare ed eseguire la ricerca.

Una volta creata la ricerca, viene visualizzata una pagina a comparsa con i dettagli relativi alla ricerca. Si noti che i pulsanti **statistiche** e **Anteprima** inizialmente sono inattivati perché la ricerca non è stata completata. È possibile tenere conto dello stato di avanzamento monitorando la colonna **stato** nella scheda **ricerche** .

## <a name="view-statistics-and-search-results"></a>Visualizzare le statistiche e i risultati della ricerca

Dopo aver creato e avviato una ricerca per l'analisi dei dati, lo strumento utilizza i criteri di ricerca (la query di ricerca e i percorsi di contenuto) definiti e cerca un indice nel servizio Live per gli elementi che soddisfano i criteri di ricerca. Sono disponibili tre componenti di una ricerca che vengono restituiti al termine della ricerca: 

- **Stima** -poiché la ricerca Cerca solo un indice (anziché le posizioni di contenuto effettive), i risultati di una ricerca sono una stima (in base alle informazioni rilevate nell'indice corrispondente ai risultati della ricerca). Un riepilogo della stima viene visualizzato nella pagina riquadro a comparsa di ricerca in **stato**. Si noti che lo stato del processo di stima per una ricerca viene visualizzato nella scheda **ricerche** nella colonna **stato stima** . Al termine della stima della ricerca, questo stato è impostato su **esito positivo**.

- **Statistica** -le statistiche forniscono informazioni più dettagliate sui risultati della ricerca. Sono incluse le attività seguenti:

    - Riepilogo: statistiche simili ai risultati delle stime di ricerca visualizzati nella pagina a comparsa.
    - Posizioni principali-statistiche sul numero di elementi che corrispondono alla query di ricerca in ogni percorso di contenuto in cui è stata eseguita la ricerca. 
    - Query: statistiche dettagliate sulla query di ricerca, incluso il numero di elementi che corrispondono a ogni condizione in una query di ricerca.

    Fare clic su **statistiche** nella pagina a comparsa per visualizzare queste statistiche. Tenere presente che questo pulsante è inattivo finché il valore dello **stato stima** nella scheda **ricerche** non è impostato su **esito positivo**. Per ulteriori informazioni sulle statistiche di ricerca, vedere [Search Statistics](search-statistics.md).

- **Anteprima** : quando la ricerca è stata completata, è possibile visualizzare gli elementi effettivi da un sottoinsieme di esempio dei risultati della ricerca restituiti dalla ricerca. È possibile visualizzare nella visualizzazione nativa del tipo di elemento, qualsiasi è anche possibile visualizzare i metadati relativi all'elemento. Questo è un ottimo metodo per determinare rapidamente se i risultati della ricerca sono quelli previsti o se è necessario modificare la ricerca e rieseguirla. Fare clic su **Anteprima** nella pagina a comparsa per visualizzare gli elementi dai risultati della ricerca. Tenere presente che questo pulsante è inattivo finché il valore dello **stato di anteprima** della scheda **ricerche** non è impostato su **esito positivo**.
 
> [!NOTE]
> I valori di stato per le colonne stato **stima** e **stato anteprima** nella scheda **ricerche** sono **inoltrati**, **in corso**e con **esito positivo**. Se si verifica un errore con la ricerca, viene visualizzato lo stato **failed** .

## <a name="add-search-results-to-evidence"></a>Aggiungere i risultati della ricerca all'evidenza

Quando si è soddisfatti dei risultati di una ricerca e si è pronti per analizzare e correggere i risultati della ricerca, è possibile aggiungerli a un set di evidenze nell'inchiesta. Quando si aggiungono elementi a un set di evidenze nella scheda **Evidence** , si verificano le due operazioni seguenti:

- Tutti gli elementi nei risultati della ricerca vengono copiati dall'origine dati nel servizio Live e copiati in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

- Tutti gli elementi, inclusi il contenuto e i metadati, vengono reindicizzati in modo che tutti i dati del set di evidenze siano completamente ricercabili durante l'indagine. La reindicizzazione dei risultati dei dati viene eseguita in ricerche accurate e molto veloci quando si esegue una ricerca nei dati del set di evidenze durante l'indagine.

Un vantaggio della copia dei dati attivi in un set di evidenze in Azure è che per gli incidenti critici o sensibili al tempo, è possibile contenere rapidamente i danni eliminando immediatamente il contenuto sospetto nell'origine dati originale nel servizio Live e quindi esaminando l'incidente analizzando la prova che è stata copiata nell'ambiente in quarantena del percorso di archiviazione di Azure. 

La copia dei dati originali nel set di evidenze facilita anche l'indagine fornendovi strumenti di analisi avanzati, come il rilevamento di temi, il rilevamento quasi duplicati e l'identificazione dei thread di posta elettronica.

Se necessario, è anche possibile aggiungere dati provenienti da origini dati non di Office 365 a un set di evidenze in modo che venga memorizzato insieme ai dati raccolti da Office 365.

Per aggiungere dati a un set evidenziato, selezionare una ricerca nella scheda **ricerche** e quindi fare clic su **Aggiungi risultati in evidenza** nella pagina a comparsa. Si noti che è possibile aggiungere dati a un set di evidenze esistente o creare un nuovo set di prove al volo.

### <a name="tracking-the-progress-of-adding-search-results-to-evidence"></a>Verifica dello stato di avanzamento dell'aggiunta dei risultati della ricerca all'evidenza

L'aggiunta di dati a un set di evidenze è un processo a esecuzione prolungata. Il processo include la raccolta degli elementi provenienti dall'origine dati originale da Office 365 (ad esempio, da cassette postali e siti), copiarli nel percorso di archiviazione di Azure ( ** questo processo di copia è denominato anche ingestione) e quindi reindicizzare gli elementi. È possibile tracciare lo stato di avanzamento nella scheda **processi** o nella scheda **ricerche** della colonna **Aggiunta dati in evidenza** . Dopo aver completato l'elaborazione delle evidenze, è possibile passare alla scheda **Evidence** , fare clic sul set di prove, quindi avviare l'analisi ricercando, rivedendo, contrassegnando ed esportando i dati rilevanti in base alle esigenze.