---
title: Skype Office 365 per l'eliminazione di dati Business
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
description: Una spiegazione dell'eliminazione di dati in Skype per le aziende.
ms.openlocfilehash: f3ddd0ad0797c465857919e8f7b28341492769ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531053"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Skype per l'eliminazione di dati Business in Office 365

Skype for Business fornisce le funzionalità di archiviazione dei messaggi istantanei peer-to-peer e con più partecipanti, nonché le attività di caricamento dei contenuti nelle riunioni. La capacità di archiviazione richiede Exchange ed è controllata dall'attributo di conservazione in locale della cassetta postale Exchange dell'utente, che archivia i contenuti di posta elettronica e Skype for Business.

Tutta l'archiviazione in Skype for Business viene considerata "archiviazione a livello dell'utente" perché consente di abilitare o disabilitare l'archiviazione per uno o più utenti o gruppi di utenti specifici, creando, configurando e applicando criteri di archiviazione a livello di utente per tali utenti. Nell'interfaccia di amministrazione di Skype for Business non è disponibile un controllo diretto sulle impostazioni di archiviazione.

I seguenti tipi di contenuto non vengono archiviati in Skype for Business: 
- File trasferiti peer-to-peer
- Audio/video per conferenze e messaggi immediati peer-to-peer
- Applicazioni condivise per conferenze e messaggi immediati peer-to-peer
- Annotazioni di conferenza 

## <a name="meeting-content-retention"></a>Conservazione del contenuto della riunione
I clienti che utilizzano Skype per le aziende possono caricare i dati in un Skype per le riunioni aziendali come allegati, ad esempio presentazioni di PowerPoint, file di OneNote e altri file. Il periodo di conservazione per il contenuto che è stato caricato in una riunione è il seguente:
- **Riunione singola** - il contenuto viene conservato per 15 giorni a partire da quando l'ultimo utente abbandona la riunione.
- **Riunione ricorrente** - il contenuto viene conservato per 15 giorni dopo l'ultimo utente abbandona la sessione ultima della riunione. Il timer di conservazione viene reimpostata se un utente accede a della stessa sessione riunione entro 15 giorni. Si supponga ad esempio Skype per le riunioni aziendali pianificato per l'esecuzione in ogni settimana per un anno e viene caricato un file alla riunione durante la prima istanza. Se almeno una persona viene aggiunto alla sessione di riunione ogni settimana, il file viene mantenuto in Skype per i server Online Business per l'intero anno oltre 15 giorni dopo l'ultimo utente abbandona la riunione precedente della serie.
- Contenuto delle **riunioni meet Now** - viene conservato per 8 ore dopo l'ora di fine della riunione.

> [!NOTE]
> Se un utente senza licenza o disattivato (ad esempio, se **msRTCSIP-userenabled** è impostato su *False*) e viene quindi nuovamente con contratto multilicenza o riabilitata, contenuto delle riunioni non viene mantenuto.

## <a name="meeting-expiration"></a>Scadenza della riunione
Gli utenti possono accedere a una riunione specifica dopo che è terminata in base ai seguenti periodi di scadenza:
- **Riunione singola** - riunione scade 14 giorni dopo l'ora di fine la riunione pianificata.
- **Riunione ricorrente con data di fine** - riunione scade 14 giorni dopo l'ora di fine pianificata dell'ultima occorrenza della riunione.
- **Riunione immediata riunione** - riunione scade dopo 8 ore.

## <a name="whiteboard-collaboration"></a>Collaborazione tramite Lavagna
Annotazioni apportate a lavagne verranno visualizzate da tutti i partecipanti. Quando si salva una lavagna, Lavagna e tutte le annotazioni verranno archiviate nel Skype per Business server e verrà mantenuto nel server in base ai criteri di scadenza del contenuto riunione impostata dall'amministratore.

## <a name="audio-test-service"></a>Servizio di prova audio
Un esempio short (circa 5 secondi) della voce è registrato durante la chiamata al servizio Test Audio. Nell'esempio di voice viene utilizzato dall'utente per verificare e/o verificare la qualità del suono del Skype per chiamata Business in base alla qualità della registrazione. Al termine, la chiamata al servizio Test Audio viene eliminato il codice di esempio vocale.

## <a name="persistent-group-chat"></a>Chat di gruppo permanenti
Gruppo di persistent Chat memorizza il contenuto delle conversazioni di group chat. Se attivata, l'amministratore può controllare il periodo di conservazione, il server in cui queste informazioni vengono archiviate, se viene archiviata cronologia Chat di gruppo per la conformità o altri scopi e gestire/modificare le proprietà di una chat room. Gli utenti con diversi ruoli dispongono diverse per i dati permanenti, come indicato di seguito:
- Gli amministratori possono eliminare contenuti meno recenti (ad esempio, il contenuto inserito prima di una determinata data) da una chat room per mantenere le dimensioni del database di crescita notevolmente. Oppure, rimuovere o sostituire i messaggi considerati non appropriati per una determinata chat (o considerate inadeguate).
- Gli utenti finali, compresi gli autori dei messaggi, è possono eliminare il contenuto da una chat room.
- Ai responsabili di chat possono disattivare le chat, ma non possono eliminare le chat. Solo gli amministratori possono eliminare una chat room dopo averlo creato.