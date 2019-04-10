---
title: Gestire i processi in indagini sui dati
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
ms.openlocfilehash: 28577d45c44eabcffcff2d98bc89a664f3fba6f5
ms.sourcegitcommit: 19d27ff836ee7fa1f8a4e761e04d928f13f4bfd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "31745298"
---
# <a name="manage-jobs-in-data-investigations-preview"></a>Gestire i processi in indagini sui dati (anteprima)

Di seguito viene indicato un elenco dei processi (che in genere sono elaborati in modo prolungato) che vengono registrati nella scheda **processi** di un'indagine in indagini sui dati (Preview). Tali processi vengono attivati dalle azioni dell'utente durante l'utilizzo e la gestione delle indagini.

| Tipo processo            | Descrizione     |
| :----------------- | :----------     |
|Aggiunta di dati a un set di prove | Un utente aggiunge i risultati di una ricerca a un set di evidenze.  Per ulteriori informazioni, vedere [Search for data in an Investigation](search-for-data.md). |
|Aggiunta di dati a un altro set di prove | Un utente aggiunge i documenti da un set di prove a un set di prove diverso nello stesso caso.|
|Aggiunta di dati non di Office 365 a un set di prove | Un utente carica i dati non di Office 365 in un set di prove. I dati vengono indicizzati anche durante questo processo. Ad esempio, i file provenienti da un server di file locale o da un computer client vengono caricati in un set di prove. Per ulteriori informazioni, vedere [caricare i dati non di Office 365 in evidence](load-non-office365-data.md).| 
|Aggiunta di dati rimediati a un set di prove | I dati con errori di elaborazione vengono corretti e caricati di nuovo in un set di prove. Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati per un'indagine](error-remediation.md). | 
|Confronto tra set di carico | Un utente esamina le differenze tra set di carico diversi in un set di evidenze. Un set di carichi è un'istanza di aggiunta di dati a un set di evidenze. Ad esempio, se si aggiungono i risultati di due ricerche diverse allo stesso set di prove, ognuna rappresenta un set di carico. Per ulteriori informazioni, vedere [gestire i set di carico](manage-load-sets.md). |
|Conversione di documenti redatti in formato PDF|Dopo che un utente ha annotato un documento in un set di evidenze e redacts una parte di esso, può scegliere di convertire il documento redatto in un file PDF. Questo garantisce che la parte redatta non sarà visibile Whenf il documento viene esportato per la presentazione. Per ulteriori informazioni, vedere [Review data in evidence](review-data-in-evidence.md). |
|Stima dei risultati della ricerca | Dopo che un utente ha creato ed eseguito una nuova ricerca (o ha rieseguito una ricerca esistente), lo strumento di ricerca Cerca l'indice per gli elementi che corrispondono alla query di ricerca e prepara una stima che include il numero e la dimensione totale di tutti gli elementi per la ricerca e il numero di origini dati Sea rched.  Per ulteriori informazioni, vedere [Search for data in an Investigation](search-for-data.md). | 
|Preparazione dei dati per l'esportazione | Un utente esporta i documenti da un set di evidenze. Al termine del processo di esportazione, è possibile scaricare i dati esportati in un computer locale. Per ulteriori informazioni, vedere [esportare i dati da un'indagine](export-data.md). | 
|Preparazione per la risoluzione degli errori |Quando un utente seleziona un file e crea una nuova correzione degli errori nella visualizzazione errori nella scheda **elaborazione** di un'indagine, il primo passaggio del processo consiste nel caricare il file che ha l'errore di elaborazione in una posizione di archiviazione di Azure nel cloud Microsoft. Questo processo tiene traccia dello stato di avanzamento della procedura di caricamento. Per ulteriori informazioni sul flusso di lavoro per la correzione degli errori, vedere correzione degli [errori durante l'elaborazione dei dati per un'indagine](error-remediation.md).| 
|Preparazione dell'anteprima di ricerca | Dopo che un utente ha creato ed eseguito una nuova ricerca (o ha rieseguito una ricerca esistente), lo strumento di ricerca prepara un sottoinsieme di elementi di esempio (che corrispondono alla query di ricerca) che è possibile visualizzare in anteprima. La visualizzazione in anteprima dei risultati della ricerca può essere utile per determinare l'efficacia della ricerca.  Per ulteriori informazioni, vedere [Search for data in an Investigation](search-for-data.md). | 
|Reindicizzazione dei dati di persone di interesse | Quando si aggiunge una persona interessata a un'indagine, tutti gli elementi parzialmente indicizzati nelle origini dati selezionate della persona interessata vengono reindicizzati da un processo denominato *Advanced*indicizzazione. Questo processo viene attivato anche quando si fa clic su **Aggiorna indice** nella visualizzazione indice nella scheda **elaborazione** di un'indagine. Per ulteriori informazioni, vedere [Advanced indicizzazione dei dati per un'indagine](index-data-people-of-interest.md).
|Esecuzione di analisi | Un utente analizza i dati in un set di evidenze mediante l'esecuzione di strumenti di analisi quali il rilevamento duplicati, l'analisi del threading di posta elettronica e l'analisi dei temi. Per ulteriori informazioni, vedere [Run Analytics to investigate Faster](run-analytics-to-investigate-faster.md). | 
|Contrassegnare i documenti | Questo processo viene attivato quando un utente fa clic su **Avvia processo di tagging** nel **Pannello di tagging** quando si esaminano i documenti in un set di evidenze. Un utente può avviare questo processo dopo aver eseguito il tag dei documenti in un set di prove e quindi selezionarli in blocco nel pannello Visualizza documento. Per ulteriori informazioni, vedere [tag Documents in evidence](tag-documents.md). | 
|||
