---
title: Utilizzo dei depositari in Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lo strumento di gestione dei depositari in Advanced eDiscovery consente di gestire il flusso di lavoro attorno all'identificazione, alla conservazione e alla raccolta dei dati associati alle persone di interesse in un caso legale.
ms.openlocfilehash: 6e365f0b7f80a0a5caa050b2e0b08c94dbed4746
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151598"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a>Utilizzo dei depositari in Advanced eDiscovery

Quando un'organizzazione risponde a un'indagine legale, il flusso di lavoro relativo all'identificazione, alla conservazione e alla raccolta di contenuti potenzialmente rilevanti si basa sulle persone dell'organizzazione che sono depositarie dei dati rilevanti. In eDiscovery, questi individui sono denominati *depositari dei dati* (o solo *depositari*) e sono definiti come "persone che hanno il controllo amministrativo di un documento o di un file elettronico". Ad esempio, il custode di un messaggio di posta elettronica potrebbe essere il proprietario della cassetta postale che contiene il messaggio pertinente.  

Quando viene avviata un'indagine, il team di eDiscovery deve identificare rapidamente tutti i depositari rilevanti e le origini dati correlate al caso. Nel corso del tempo, l'elenco dei depositari e delle relative origini dati può aumentare o decreasse. Di conseguenza, le organizzazioni devono mantenere un processo controllato attorno all'identificazione, alla conservazione e alla raccolta di contenuto affidatario per tutto il ciclo di vita di un caso.

In un caso avanzato di eDiscovery, i team legali possono aggiungere individui all'interno della propria organizzazione come depositari e identificare e preservare automaticamente le origini dati di tipo affidatario, ad esempio le cassette postali di Exchange, gli account OneDrive e i siti di SharePoint e teams. Utilizzando lo strumento di gestione del custode incorporato in Advanced eDiscovery, le organizzazioni possono proteggere le informazioni archiviate elettronicamente dall'eliminazione involontaria (o intenzionale). In questo modo è possibile eliminare il processo che richiede tempo e l'errore di dover eseguire manualmente i processi di archiviazione legale. 

Per ulteriori informazioni sull'utilizzo dei depositari, vedere gli argomenti seguenti: 

- [Aggiungere responsabili a un caso](add-custodians-to-case.md)

- [Gestire i depositari in un caso](manage-new-custodians.md)

- [Visualizzare l'attività dei responsabili](view-custodian-activity.md)

## <a name="advanced-ediscovery-permissions"></a>Autorizzazioni avanzate di eDiscovery

In Advanced eDiscovery, è possibile utilizzare il gruppo di ruoli di eDiscovery Manager incorporato per assegnare le autorizzazioni necessarie agli investigatori legali in modo che possano gestire il flusso di lavoro end-to-end in Advanced eDiscovery. In alternativa, è possibile creare gruppi di ruoli personalizzati con un sottoinsieme dei ruoli necessari per eseguire determinate azioni in un caso in Advanced eDiscovery. Per ulteriori informazioni sui ruoli correlati a eDiscovery, vedere [assign eDiscovery Permissions in the Security _AMP_ Compliance Center](../assign-ediscovery-permissions.md).
