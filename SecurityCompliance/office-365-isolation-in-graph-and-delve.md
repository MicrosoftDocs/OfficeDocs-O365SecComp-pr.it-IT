---
title: Isolamento tenant di Office 365 nel grafico di Office e approfondire
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "Sintesi: una spiegazione dell'isolamento del tenant in Office Graph e in approfondire."
ms.openlocfilehash: 22bcf581c26ea4e334539a81861ff4dee68967ef
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004203"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Isolamento del tenant in Office Graph e Delve

## <a name="tenant-isolation-in-the-office-graph"></a>Isolamento del tenant in Office Graph
L'attività dei modelli di [Office Graph](https://dev.office.com/officegraph) nei servizi di Office 365, tra cui Exchange Online, SharePoint Online, Yammer, Skype for business, Azure Active Directory e altro ancora, e nei servizi esterni, ad esempio altri servizi Microsoft o servizi di terze parti. I componenti di Office Graph vengono utilizzati in Office 365. Il grafico di Office rappresenta un insieme di contenuto e attività e le relazioni tra di essi che si verificano nell'intera famiglia di prodotti Office. Utilizza sofisticate tecniche di apprendimento automatico per connettere le persone ai contenuti, alle conversazioni e alle persone rilevanti che li circondano. Ad esempio, l'indice tenant in SharePoint Online include un indice di Office Graph utilizzato per eseguire query approfondite, il motore di elaborazione dell'analisi in SharePoint Online viene utilizzato per archiviare i segnali e calcolare gli Insight e Exchange Online calcola i dati di ogni utente cache dei destinatari come input nell'analisi del tenant.

Il grafico di Office contiene informazioni sugli oggetti dell'organizzazione, ad esempio persone e documenti, nonché le relazioni e le interazioni tra questi oggetti. Le relazioni e le interazioni sono rappresentate come *spigoli*. Il grafico di Office è segmentato dal tenant in modo che i bordi possano esistere solo tra i *nodi* dello stesso contratto di locazione. Un *nodo* è un'entità con un URI (Uniform Resource Identifier), un tipo di nodo, un elenco di controllo di accesso e un set di facet che contengono *metadati* e spigoli. A ciascun nodo sono associati metadati e spigoli, disposti ** in facet come nel modello di conoscenza comune. I *metadati* sono proprietà denominate archiviate in un nodo che è possibile utilizzare per la ricerca, il filtro o l'analisi all'interno del grafico di Office. Un *facet* è una raccolta logica di metadati e spigoli su un nodo. Ogni facet descrive un aspetto di un nodo. 

In Office Graph non vengono portati tutti i dati in un unico repository. piuttosto, memorizza i metadati e le relazioni sui dati che vivono altrove. Il grafico di Office è costituito da diversi archivi dati e componenti di elaborazione:
- L'archivio grafico tenant fornisce archiviazione di massa ottimizzata per analisi efficienti.
- La cache del contenuto attivo fornisce un accesso casuale rapido ai nodi e ai bordi attivi per guidare le esperienze degli utenti.
- Il router di input notifica ai componenti interni ed esterni le modifiche apportate al grafico tenant.

L'analisi all'interno di ogni carico di lavoro deduce informazioni rilevanti per i calcoli a livello di tenant e li inserisce nel grafico tenant. I motivi di analisi tenant su tutte le attività in una locazione per produrre informazioni su modelli di comportamento. Ad esempio, Exchange Online calcola la cache dei destinatari per ogni utente con analisi che ragionano efficacemente sulla cassetta postale di ogni utente. Queste analisi per utente producono un insieme di *spigoli RecipientCache* su ogni persona, che a sua volta vengono spinte nel grafico tenant. In questo modo il processo di analisi viene mantenuto il più vicino possibile ai dati di origine.

## <a name="tenant-isolation-in-delve"></a>Isolamento del tenant nell'approfondimento
Come accennato in precedenza, Office Graph alimenta le esperienze che consentono agli utenti di individuare e collaborare alle attività correnti nell'organizzazione e fornisce una piattaforma di analisi incentrata su entità per il motivo del contenuto e dell'attività tra i carichi di lavoro e oltre Office 365. Approfondire è la prima esperienza di questo tipo fornita da Office Graph.
Approfondire è un'esperienza Web di Office 365 che consente di visualizzare il contenuto di Office 365 e Yammer Enterprise con gli utenti di Office 365 tramite Office Graph. L'esperienza Web consente di visualizzare i dati come schede diverse, ognuna con un determinato argomento, ad esempio i *trend attorno a me* o *modificati da me*. Ogni scheda è costituita da diverse schede documento che visualizzano testo di riepilogo e un'immagine del documento. La scheda consente agli utenti di eseguire operazioni come aprire il documento o una pagina di Yammer per il documento. Vi è una pagina per ogni persona in un tenant di Office 365 che Visualizza i documenti più rilevanti per questa persona e le icone che possono richiamare Exchange Online o Skype for business per interagire con quella persona. Poiché il servizio di approfondimento è basato sull'API di Office Graph, è associato all'isolamento basato sul tenant di tale API.