---
title: Isolamento dei Tenant Office 365 nella ricerca di Office 365
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
description: 'Riepilogo: Informazioni di isolamento tenant nella ricerca di Office 365.'
ms.openlocfilehash: cc73f3c157ffd20b3891a6b7c58e7d0b2adf4e55
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530198"
---
# <a name="tenant-isolation-in-office-365-search"></a>Ricerca dell’isolamento del tenant in Office 365
Ricerca di SharePoint Online utilizza un modello di separazione tenant che offre un buon livello l'efficienza delle strutture di dati condivise con protezione contro la perdita tra tenant informazioni. Con questo modello è impedire le funzionalità di ricerca da:
- Restituisce i risultati delle query contenenti documenti provenienti da altri tenant
- Esposizione di informazioni sufficienti nei risultati della query che un utente esperto può derivare informazioni su altri tenant
- Visualizzazione dello schema o le impostazioni da un altro tenant
- Combinazione di elaborazione delle informazioni tra tenant o memorizzare i risultati nel tenant errato analitica
- Mediante le voci di dizionario da un altro tenant

Per ogni tipo di dati relativi al tenant, viene utilizzato uno o più livelli di protezione nel codice per impedire la perdita accidentale dei dati. I dati più importanti contengono la maggior parte dei livelli di protezione per verificare che un solo difetto non provoca la perdita di informazioni effettivamente o percepite come.

## <a name="tenant-separation-for-the-search-index"></a>Separazione del tenant per l'indice di ricerca
L'indice di ricerca viene memorizzato su disco nel server che ospitano i componenti di indicizzazione e il tenant di condividere i file di indice. Documenti indicizzati del tenant sono visibili solo per le query per il tenant. Tre meccanismi indipendenti impedire la perdita di informazioni:
- Filtro dell'ID tenant
- Prefisso termini ID tenant
- Controlli ACL

Tutti e tre i meccanismi sarebbe costretto a esito negativo per la ricerca restituire i documenti per il tenant errato.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtro dell'ID tenant e termini ID Tenant aggiunta come prefisso
Prefissi ricerca ogni termine che viene indicizzato nell'indice full-text con l'ID tenant. Ad esempio, quando il termine "*foo*" è indicizzato per un tenant con ID "*123*", la voce di indice full-text è "*123foo.*"

Tutte le query viene convertita in modo da includere l'ID tenant utilizzando un processo noto come filtro dell'ID tenant. Ad esempio, la query "*foo*" viene convertita in "<*guid*>. *Foo* E *ID tenant*: <*guid*> ", dove <*guid*> rappresenta i tenant che esegue la query. Questa conversione di query viene eseguita all'interno di ciascun nodo indice ed elaborazione delle query e il contenuto non può influire. Poiché l'ID viene aggiunto a tutte le query, la frequenza di un termine in altri tenant non è desunta cercando migliore corrispondenza di classificazione in un tenant.

Prefisso termini ID tenant si verifica solo nell'indice full-text. Le ricerche già distribuito sul campo, ad esempio "*title: foo*", passare a un indice di ricerca sintetica cui termini non sono prefisso ID tenant. In realtà, le ricerche già distribuito sul campo includono il prefisso con il nome del campo. Ad esempio, la query "*title: foo*" viene convertita in "*fields.title:foo fields.tenantID AND*: <*guid*>." Poiché la frequenza di un termine non influire sulla classificazione dei risultati dell'indice di ricerca sintetica, non è necessario per la separazione dei tenant dal prefisso per termini. Per la ricerca già distribuito sul campo come "*titolo: foo*", separazione del contenuto tenant dipende dal filtro per la conversione di query ID tenant.

## <a name="document-access-control-list-checks"></a>Controlli elenco degli accessi di documenti
Ricerca controlla l'accesso ai documenti tramite ACL salvati nell'indice di ricerca. Sono indicizzato a tutti gli elementi con un set di termini in un campo ACL speciale. Il campo ACL contiene un termine per ogni gruppo o un utente che è possibile visualizzare il documento. Tutte le query è arricchita con un elenco di termini voce di elenco di controllo di accesso uno per ogni gruppo a cui appartiene l'utente autenticato.

Ad esempio, una query come "<*guid*>. *foo ID tenant AND*: <*guid*> "diventa:" <*guid*>. *foo ID tenant AND*: <*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*: <*ace2*> *OR docACL*: <*ace3*> *... *)"

Poiché utente e gli identificatori di gruppo e pertanto le voci sono univoche, in tal modo un ulteriore livello di sicurezza tra tenant per i documenti sono visibili solo per alcuni utenti. Lo stesso avviene per il speciale "tutti tranne agli utenti esterni" ACE che concede l'accesso agli utenti regolari nel tenant. Ma poiché le voci per "Tutti" sono identiche per tutti i tenant, la separazione dei tenant per i documenti pubblici dipende dal filtro dell'ID tenant. Nega che sono inoltre supportate le voci. Augmentation query aggiunge una clausola che consente di rimuovere un documento dal risultato quando viene rilevata una corrispondenza con negata.

Nella ricerca di Exchange Online, l'indice viene partizionata ID della cassetta postale per le cassette postali dell'utente singoli anziché tenant a ID sottoscrizione come SharePoint Online. Il meccanismo di partizionamento corrisponde a SharePoint Online, ma non esiste alcun ACL filtro.
