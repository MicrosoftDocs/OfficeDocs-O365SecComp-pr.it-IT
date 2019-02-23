---
title: Eliminazione dei dati di Office 365 Skype for business
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Spiegazione dell'eliminazione dei dati in Skype for business.
ms.openlocfilehash: 77ead8b8c2251ce21f9a0c0db9e29d5d48829760
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221146"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Eliminazione dei dati di Skype for business in Office 365

Skype for Business fornisce le funzionalità di archiviazione dei messaggi istantanei peer-to-peer e con più partecipanti, nonché le attività di caricamento dei contenuti nelle riunioni. La capacità di archiviazione richiede Exchange ed è controllata dall'attributo di conservazione in locale della cassetta postale Exchange dell'utente, che archivia i contenuti di posta elettronica e Skype for Business.

Tutta l'archiviazione in Skype for Business viene considerata "archiviazione a livello dell'utente" perché consente di abilitare o disabilitare l'archiviazione per uno o più utenti o gruppi di utenti specifici, creando, configurando e applicando criteri di archiviazione a livello di utente per tali utenti. Nell'interfaccia di amministrazione di Skype for Business non è disponibile un controllo diretto sulle impostazioni di archiviazione.

I seguenti tipi di contenuto non vengono archiviati in Skype for business: 
- File trasferiti peer-to-peer
- Audio/video per conferenze e messaggi immediati peer-to-peer
- Applicazioni condivise per conferenze e messaggi immediati peer-to-peer
- Annotazioni di conferenza 

## <a name="meeting-content-retention"></a>Conservazione del contenuto della riunione
I clienti che utilizzano Skype for business possono caricare contenuti in una riunione di Skype for business come allegati, ad esempio presentazioni di PowerPoint, file OneNote e altri file. Il periodo di conservazione per il contenuto caricato in una riunione è il seguente:
- La riunione-contenuto **una tantum** viene conservata per 15 giorni a partire da quando l'ultima persona lascia la riunione.
- Il contenuto di **riunioni ricorrenti** viene conservato per 15 giorni dopo che l'ultima persona ha lasciato l'ultima sessione della riunione. Il timer di conservazione viene reimpostato se un utente si unisce alla stessa sessione di riunione entro 15 giorni. Si supponga, ad esempio, che venga pianificata una riunione di Skype for business su base settimanale per un anno e che un file venga caricato alla riunione durante la prima istanza. Se almeno una persona entra a far parte della sessione di riunione ogni settimana, il file viene conservato nei server Skype for business online per tutto l'anno più 15 giorni dopo che l'ultima persona ha lasciato l'ultima riunione della serie.
- **Meet Now meeting** -Content viene conservato per 8 ore dopo l'ora di fine della riunione.

> [!NOTE]
> Se un utente non è autorizzato o disabilitato (ad esempio, se **msRTCSIP-UserEnabled** è impostato su *false*) e viene quindi riconcesso in licenza o riabilitato, il contenuto della riunione non viene mantenuto.

## <a name="meeting-expiration"></a>Scadenza della riunione
Gli utenti possono accedere a una riunione specifica dopo che è terminata in base ai seguenti periodi di scadenza:
- La riunione di **una tantum** scade 14 giorni dopo l'ora di fine della riunione pianificata.
- **Riunione ricorrente con data di fine** -la riunione scade 14 giorni dopo l'ora di fine pianificata dell'ultima riunione.
- **Meet Now meeting** -meeting scade dopo 8 ore.

## <a name="whiteboard-collaboration"></a>Collaborazione lavagna
Le anNotazioni eseguite nelle lavagne verranno visualizzate da tutti i partecipanti. Quando si salva una lavagna, la lavagna e tutte le annotazioni verranno archiviate su un server Skype for business e verranno conservate sul server in base ai criteri di scadenza del contenuto delle riunioni impostati dall'amministratore.

## <a name="audio-test-service"></a>Servizio di test audio
Durante la chiamata del servizio di test audio viene registrato un campione breve (circa 5 secondi) della voce. Il campione vocale viene utilizzato dall'utente per verificare e/o verificare la qualità del suono della chiamata Skype for business in base alla qualità della registrazione. Quando viene terminata la chiamata al servizio di test audio, viene eliminato l'esempio di voce.

## <a name="persistent-group-chat"></a>Chat di gruppo persistente
Persistent Group Chat archivia il contenuto delle conversazioni di Group Chat. Se abilitato, l'amministratore può controllare il periodo di conservazione, il server in cui sono archiviate le informazioni, se la cronologia della chat di gruppo viene archiviata per la conformità o altri scopi e gestire/modificare le proprietà in una chat room. Gli utenti con ruoli diversi hanno accesso diverso ai dati permanenti, come indicato di seguito:
- Gli amministratori possono eliminare i contenuti meno recenti (ad esempio, il contenuto inserito prima di una determinata data) da qualsiasi chat room per evitare che le dimensioni del database crescano notevolmente. In alternativa, è possibile rimuovere o sostituire i messaggi considerati inappropriati per una determinata chat room (o considerati inadatti).
- Gli utenti finali, compresi gli autori dei messaggi, non possono eliminare il contenuto da una chat room.
- I responsabili della chat room possono disabilitare le sale ma non possono eliminare le sale. Solo gli amministratori possono eliminare una chat room dopo che è stata creata.