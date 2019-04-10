---
title: Gestire i processi in Advanced eDiscovery (Preview)
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
ms.openlocfilehash: e5f7c6d0f0932041ef92591afcb59ad836cae0e4
ms.sourcegitcommit: 19d27ff836ee7fa1f8a4e761e04d928f13f4bfd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "31745288"
---
# <a name="manage-jobs-in-advanced-ediscovery-preview"></a>Gestire i processi in Advanced eDiscovery (Preview)

Di seguito è indicato un elenco dei processi (che in genere sono di lunga durata) che vengono registrati nella scheda **processi** di un caso in Advanced eDiscovery (Preview). Questi processi vengono attivati dalle azioni dell'utente durante l'utilizzo e la gestione dei casi.

| Tipo processo            | Descrizione     |
| :----------------- | :----------     |
|Aggiunta di dati a un working set | Un utente aggiunge i risultati di una ricerca a un working set.  Per ulteriori informazioni, vedere [Add Search results to a working set](add-data-to-working-set.md). |
|Aggiunta di dati a un altro working set | Un utente aggiunge documenti da un set di lavoro a un set di lavoro diverso nello stesso caso.|
|Aggiunta di dati non di Office 365 a un working set | Un utente carica i dati non di Office 365 in un working set. I dati vengono indicizzati anche durante questo processo. Ad esempio, i file provenienti da un server di file locale o da un computer client vengono caricati in un working set. Per ulteriori informazioni, vedere [caricare i dati non di Office 365 in un working set](load-non-office365-data.md).| 
|Aggiunta di dati corretti a un working set | I dati con errori di elaborazione vengono corretti e caricati di nuovo in un working set. Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati](error-remediation.md). | 
|Confronto tra set di carico | Un utente esamina le differenze tra set di carico diversi in un working set. Un set di carichi è un'istanza di aggiunta di dati a un working set. Ad esempio, se si aggiungono i risultati di due ricerche diverse allo stesso working set, ognuno di essi rappresenterà un set di carico. Per ulteriori informazioni, vedere [gestire i set di carico](manage-load-sets.md). |
|Conversione di documenti redatti in formato PDF|Dopo che un utente ha annotato un documento in un working set e redacts una parte di esso, può scegliere di convertire il documento redatto in un file PDF. Questo garantisce che la parte redatta non sarà visibile se il documento viene esportato per la presentazione. Per ulteriori informazioni, vedere [visualizzare i documenti in un working set](annotating-and-redacting-documents.md). |
|Stima dei risultati della ricerca | Dopo che un utente ha creato ed eseguito una nuova ricerca (o ha rieseguito una ricerca esistente), lo strumento di ricerca Cerca l'indice per gli elementi che corrispondono alla query di ricerca e prepara una stima che include il numero e la dimensione totale di tutti gli elementi in base alla ricerca e il numero di origini dati che bruciano Ched.  Per ulteriori informazioni, vedere [Collect Data for a case](collecting-data-for-ediscovery.md). | 
|Preparazione dei dati per l'esportazione | Un utente esporta i documenti da un set di lavoro. Al termine del processo di esportazione, è possibile scaricare i dati esportati in un computer locale. Per ulteriori informazioni, vedere [Export case data](exporting-data-ediscover20.md). | 
|Preparazione per la risoluzione degli errori |Quando un utente seleziona un file e crea una nuova correzione degli errori nella visualizzazione errori nella scheda **elaborazione** di un caso, il primo passaggio del processo consiste nel caricare il file che ha l'errore di elaborazione in una posizione di archiviazione di Azure nel cloud Microsoft. Questo processo tiene traccia dello stato di avanzamento della procedura di caricamento. Per ulteriori informazioni sul flusso di lavoro per la correzione degli errori, vedere correzione degli [errori durante l'elaborazione dei dati](error-remediation.md). | 
|Preparazione dell'anteprima di ricerca | Dopo che un utente ha creato ed eseguito una nuova ricerca (o ha rieseguito una ricerca esistente), lo strumento di ricerca prepara un sottoinsieme di elementi di esempio (che corrispondono alla query di ricerca) che è possibile visualizzare in anteprima. La visualizzazione in anteprima dei risultati della ricerca consente di determinare l'efficacia della ricerca.  Per ulteriori informazioni, vedere [Collect Data for a case](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Reindicizzazione dei dati del custode | Quando si aggiunge un custode a un caso, tutti gli elementi parzialmente indicizzati nelle origini dati selezionate del custode vengono reindicizzati da un processo denominato *Advanced*indicizzazione. Questo processo viene attivato anche quando si fa clic su **Aggiorna indice** nella visualizzazione indice nella scheda **elaborazione** di un caso. Per ulteriori informazioni, vedere [Advanced indicizzazione dei dati del custode](indexing-custodian-data.md).
|Esecuzione di analisi | Un utente analizza i dati in un working set eseguendo strumenti di analisi avanzata di eDiscovery, ad esempio in prossimità del rilevamento duplicato, dell'analisi del threading di posta elettronica e dell'analisi dei temi. Per ulteriori informazioni, vedere [analyze data in a working set](analyzing-data-in-working-set.md). | 
|Contrassegnare i documenti | Questo processo viene attivato quando un utente fa clic su **Avvia processo di tagging** nel **Pannello di tagging** quando si esaminano i documenti in un working set. Un utente può avviare questo processo dopo aver eseguito il tagging dei documenti in un working set e quindi selezionarli in blocco nel pannello Visualizza documento. Per ulteriori informazioni, vedere [tag Documents in a working set](tagging-documents.md). | 
|||
