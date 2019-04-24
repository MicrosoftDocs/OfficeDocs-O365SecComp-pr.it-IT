---
title: Note sulla versione per Advanced eDiscovery (Preview)
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
description: In questo articolo sono contenute le note sulla versione per Advanced eDiscovery (Preview).
ms.openlocfilehash: 32a02c16fd30e740fcc6e1c99b46775b97590a28
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240941"
---
# <a name="release-notes-for-advanced-ediscovery-preview"></a>Note sulla versione per Advanced eDiscovery (Preview)

Il programma di anteprima pubblica per Advanced eDiscovery è il modo in cui ottenere un accesso precoce alle funzionalità e agli aggiornamenti imminenti. Per ottenere un accesso rapido alle funzionalità più recenti, è sufficiente creare e utilizzare un caso avanzato di eDiscovery (anteprima) nel centro conformità & sicurezza di Office 365. Per ulteriori informazioni, vedere [Create a New Case](create-new-ediscovery-case.md).

## <a name="known-issues"></a>Problemi noti

**Microsoft Forms**

- I dati corrispondenti a un modulo creato prima del 31 gennaio 2019 non saranno disponibili per la ricerca quando si utilizza lo strumento di ricerca in Advanced eDiscovery (Preview) per cercare le cassette postali del custode. I moduli creati dopo questa data saranno disponibili per la ricerca.

- Un modulo creato da un utente può comunque ricevere risposte anche dopo che l'utente che ha creato il modulo è stato eliminato. Tuttavia, i dati corrispondenti per tali risposte (che si sono verificati dopo l'eliminazione della cassetta postale di custode) non saranno disponibili per la ricerca quando si utilizza lo strumento di ricerca in Advanced eDiscovery (Preview) per cercare le cassette postali del custode.
 
**Microsoft Sway**

- Se un utente modifica un dominio subito prima dell'eliminazione dell'account utente per il proprietario del dominio, tali modifiche potrebbero non essere disponibili per la ricerca quando si utilizza lo strumento di ricerca in Advanced eDiscovery (Preview) per cercare le cassette postali del custode. L'ondeggiamento blocca le modifiche apportate a un ondeggiamento non appena riceve un segnale che l'account è stato eliminato. Tuttavia, c'è una piccola possibilità che un ondeggiamento può essere modificato prima che questo segnale venga ricevuto.

## <a name="issues-fixed-in-this-release"></a>Problemi risolti in questa versione

- DCR: gestione delle eccezioni per gli elementi non indicizzati e gli elementi orfani
- DCR: notifiche di blocco
- DCR: depositari in eDiscovery

## <a name="whats-new"></a>Novità

- **Riprogettata la struttura di spostamento nel centro sicurezza _AMP_ Compliance** – Advanced eDiscovery (Preview) ha un aspetto nuovo. Utilizzare Advanced eDiscovery (Preview) per gestire più del flusso di lavoro del caso.

- **Gestione dei casi** : supporto aggiuntivo per nuovi tipi di case. È inoltre possibile selezionare e salvare i casi recenti e preferiti. Tenere conto e monitorare le attività all'interno e tra i casi tramite i nuovi dashboard.

- **Gestione dei depositari** : aggiungere e rimuovere utenti come depositari dei dati all'interno di un caso.

- **Integrazione di Exchange, OneDrive e teams** : aggiungere automaticamente la cassetta postale corrente di un utente, l'account OneDrive for business e i siti di Microsoft Teams a un caso. 

- **Comunicazioni del custode** – inviare e gestire notifiche di blocco legale per conto dell'organizzazione.

- **Portale custode** – nuovo portale per i depositari per accedere alle notifiche di archiviazione attiva.

- **Deep** indicizzazione: rieseguire la ricerca per indicizzazione degli elementi parzialmente indicizzati su richiesta.

- Correzione degli errori: correzione o download di un **errore** di elaborazione; Questo include il supporto per la correzione di tipi di file di grandi dimensioni, file protetti da password e altro ancora. 

- **Miglioramenti alla ricerca** : creare una ricerca identificando i depositari e/o le posizioni.

- **Working sets** – gestire, monitorare e controllare insiemi statici di documenti.

- **Recensione** : utilizzare una visualizzazione nativa, di testo e quasi nativa per esaminare i documenti aggiunti al working set.

- **Redigere, tag e** annotazioni – testo di redigere, applicare i tag e creare annotazioni durante la revisione dei documenti.
  
- **Revisione con tecnologia di analisi**: utilizzare eDiscovery Analytics per individuare, cercare ed eliminare i risultati all'interno di un working set.

- **Jobs** – verifica lo stato dei processi con esecuzione prolungata.

- **Nuove attività di controllo** : monitorare e visualizzare nuove attività di controllo per Advanced eDiscovery.
