---
title: Isolamento dei Tenant Office 365 in ufficio grafico e approfondire
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: Informazioni di isolamento tenant nel grafico Office e in Delve.'
ms.openlocfilehash: bdc0f34d558f25ec139861c9a91261a72418f18a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530638"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Isolamento del tenant in Office Graph e Delve

## <a name="tenant-isolation-in-the-office-graph"></a>Isolamento dei tenant del grafico di Office
Attività di modelli di [Grafico di Office](https://dev.office.com/officegraph) in servizi di Office 365, inclusi Exchange Online, SharePoint Online Yammer, Skype per Business, Azure Active Directory e altre risorse e in servizi esterni, ad esempio altri servizi Microsoft o terze parti. Componenti di Office grafico vengono utilizzati in Office 365. Nel grafico Office rappresenta un insieme di contenuto e attività e le relazioni tra di esse che si verificano a un intero gruppo di Office. Utilizza tecniche di apprendimento sofisticato per connettere gli utenti per il contenuto pertinente, le conversazioni e persone attorno. Ad esempio, l'indice tenant in SharePoint Online ha indice grafico di Office che consente di gestire le query Delve, il motore di elaborazione Analitica in SharePoint Online viene utilizzato per archiviare i segnali e calcolare sui concetti ed Exchange Online viene calcolato ogni utente cache del destinatario come input per analitica tenant.

Nel grafico Office contiene informazioni su oggetti dell'organizzazione, ad esempio utenti e documenti, nonché le relazioni e le interazioni tra questi oggetti. Le relazioni e le interazioni sono rappresentate come *bordi*. Nel grafico di Office è segmentato in base al tenant in modo che i bordi è disponibile solo tra i *nodi* tenancy stesso. Un *nodo* è un'entità con un identificatore URI (Uniform Resource), tipo di nodo, elenco di controllo di accesso e un set di facet che contiene *i metadati* e bordi. Ogni nodo è associati dei metadati e bordi, organizzati in *facet* come il modello della Knowledge base comune. *Metadati* sono denominate proprietà archiviate in un nodo che può essere utilizzato per la ricerca, il filtro o l'analisi all'interno del grafico di office. Un *aspetto* è un insieme logico dei metadati e bordi in un nodo. Ogni facet descrive un aspetto di un nodo. 

Nel grafico di Office non trasferire tutti i dati in un singolo archivio; piuttosto, Archivia metadati e le relazioni sui dati presenti in un' posizione. Nel grafico di Office è costituito da alcuni archivi dati e i componenti di elaborazione:
- L'archivio grafico Tenant consente l'archiviazione di massa ottimizzata per analitica efficiente.
- La Cache di contenuto attivo fornisce accesso rapido casuale al nodo attivo e i bordi di esperienze utente unità.
- L'input router notifica componenti interni ed esterni delle modifiche apportate al grafico tenant.

Analitica all'interno di ogni carico di lavoro ricavare informazioni rilevanti per i livello di tenant calcoli e distribuirli nel grafico tenant. Motivi analitica tenant su tutte le attività di una tenancy per produrre approfondite sui modelli di comportamento. Exchange Online, ad esempio calcola la cache del destinatario per ogni utente con analitica motivo in modo efficiente tramite cassetta postale di ogni utente. Questi analitica per utente produrre una serie di *Bordi RecipientCache* su ogni persona che a sua volta vengono spostati al grafico tenant. In questo modo, l'oggetto come parte di più vicino possibile i dati di origine del processo di elaborazione analitica.

## <a name="tenant-isolation-in-delve"></a>Isolamento dei tenant di approfondire
Come accennato in precedenza, il grafico Office potenza esperienze che consentono agli utenti individuare e collaborare su attività corrente nella propria organizzazione e fornisce una piattaforma incentrato sull'entità per analitica a motivo su attività e contenuto tra carichi di lavoro e Oltre a Office 365. Approfondire è la prima di tale esperienza con tecnologia nel grafico di Office. Approfondire è un'esperienza web di Office 365 che replica del contenuto di Office 365 e Yammer Enterprise agli utenti di Office 365 tramite il grafico di Office. Utilizzare le funzionalità web vengono visualizzati dati come aree diverse, ognuno con un determinato argomento, ad esempio *tendenza intorno a me* o *modificato dall'utente*. Ogni area è costituita da più schede di documenti che consentono di visualizzare un'immagine dal documento e il testo del sunto. Nella scheda consente agli utenti di eseguire operazioni come aprire il documento o una pagina di Yammer per il documento. Non vi è una pagina per ogni utente di un tenant di Office 365 che consente di visualizzare i documenti più pertinenti per tale persona e le icone che possono richiamare Exchange Online o Skype for Business per interagire con questa persona. Poiché Delve è basato sull'API del grafico di Office, è associato l'isolamento di tale API basata sul tenant.