---
title: Ricerca di tutte le cassette postali e dei siti utilizzando il Centro eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 56e2978f-71b6-4141-b769-ad856d31bbec
description: In Centro eDiscovery di Office 365, è possibile cercare tutte le cassette postali di Exchange Online, siti di SharePoint Online e OneDrive per i siti di Business in una ricerca eDiscovery singolo. Per trovare tutte le origini di contenuto nell'organizzazione, è necessario assegnare a un manager di eDiscovery autorizzazioni eDiscovery appropriato per ogni origine di contenuto.
ms.openlocfilehash: b3508d5929ca2b5b7a937eb2dccf677a2968cbbc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530641"
---
# <a name="search-all-mailboxes-and-sites-using-the-ediscovery-center"></a>Ricerca di tutte le cassette postali e dei siti utilizzando il Centro eDiscovery

In Centro eDiscovery di Office 365, è possibile cercare tutte le cassette postali di Exchange Online, siti di SharePoint Online e OneDrive per i siti di Business in una ricerca eDiscovery singolo. Per trovare tutte le origini di contenuto nell'organizzazione, è necessario assegnare a un manager di eDiscovery autorizzazioni eDiscovery appropriato per ogni origine di contenuto. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario assegnare le autorizzazioni opportune a un responsabile eDiscovery affinché quest'ultimo sia in grado di ricercare un'origine contenuto. Per ulteriori informazioni sull'assegnazione di autorizzazioni eDiscovery per i siti e le cassette postali, vedere i seguenti articoli: 
    
  - [Assegnare le autorizzazioni di eDiscovery di Exchange](https://go.microsoft.com/fwlink/p/?LinkId=526886)
    
  - [Assegnare le autorizzazioni di eDiscovery in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=526885)
    
  - [Assegnare le autorizzazioni eDiscovery ai siti OneDrive for Business](assign-permissions-to-onedrive-for-business-sites.md)
    
- È possibile cercare un massimo di 10.000 cassette postali e un numero illimitato di SharePoint Online e OneDrive per i siti in una query di ricerca di eDiscovery singolo. Tuttavia, se si specificano i siti specifici per la ricerca, il limite è 100 siti.
    
- Quando si visualizzano i risultati durante la ricerca di tutti i siti e le cassette postali, vedere la sezione [informazioni](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo) per una descrizione dei limiti. 
    
- Per ulteriori informazioni sulla creazione delle query di ricerca di eDiscovery Center, vedere [Create and query eseguire eDiscovery](https://go.microsoft.com/fwlink/p/?LinkID=404032).
    
## <a name="search-all-locations"></a>Ricerca di tutti i percorsi

1. Nel Centro eDiscovery, aprire il caso di eDiscovery per il quale si desidera eseguire la query di ricerca.
    
2. In **ricerca e l'esportazione**, fare clic su una query esistente o fare clic su **nuovo elemento** per creare una nuova query di ricerca. 
    
3. Nella pagina della query di ricerca, nella sezione **Origini** fare clic su **Modifica ambito della query**.
    
4. Nella pagina **Modifica ambito della query**, fare clic su **Cerca ovunque** e selezionare i percorsi dei contenuti da ricercare.
    
  - Selezionare **Exchange** per la ricerca di tutte le cassette postali. 
    
  - Selezionare **SharePoint** per cercare tutti SharePoint Online e OneDrive per i siti. 
    
  - Selezionare **Exchange** e **SharePoint** per cercare tutti i percorsi di contenuti nell'organizzazione. 
    
![Ricerca in tutte le cassette postali e i siti](media/e1f919ab-5596-43bb-a3c9-626cd41067b3.gif)
  
5. Fare clic su **OK** per salvare le modifiche. 
    
6. Completare o rivedere altre informazioni nella pagina della query di ricerca, come la query della parola chiave, l'intervallo di date o la definizione di tipi specifici dei contenuti da ricercare. Una volta pronti, eseguire la query facendo clic su **Cerca**. 
    
## <a name="more-information"></a>Ulteriori informazioni
<a name="moreinfo"> </a>

- I 500 siti e le 500 cassette postali principali con il maggior numero di risultati vengono elencati in **Origini** nella pagina **Query**. 
    
- Il numero complessivo di elementi rilevati in tutte le origini di contenuti e la relativa dimensione totale vengono visualizzati in **Origini** nella pagina **Query**. 
 
    
- È possibile visualizzare in anteprima i 200 risultati di ricerca più recenti delle cassette postali di Exchange o dei siti SharePoint nella pagina **Query**. 
    
    Nella seguente schermata è illustrato un esempio relativo ai risultati di ricerca visualizzati nella pagina **Query**, quando si eseguono ricerche in tutti i siti e in tutte le cassette postali. 
    
    ![Schermata dei risultati relativi alla ricerca di tutte le posizioni](media/4bf430f6-41ab-4bf6-afa9-33c3f6fd8b16.gif)
  

