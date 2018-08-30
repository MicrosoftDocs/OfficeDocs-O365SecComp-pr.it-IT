---
title: Eliminazione dei dati in linea di Exchange di Office 365
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
description: Modalità di software e hardware eliminazioni dati vengono gestite in Exchange Online.
ms.openlocfilehash: 3a17b09e9c21ae309e00bcb0ddc0b51b93478bc1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530651"
---
# <a name="exchange-online-data-deletion-in-office-365"></a>Eliminazione di dati in linea di Exchange in Office 365
In Exchange Online, esistono due tipi di eliminazioni: soft eliminazioni ed eliminazioni disco rigido. Ciò vale per le cassette postali e gli elementi all'interno di una cassetta postale.

## <a name="soft-deleted-and-hard-deleted-mailboxes"></a>Cassette postali eliminate e disco rigido eliminati
Una cassetta postale utente eliminate è una cassetta postale è stata eliminata utilizzando l'interfaccia di amministrazione di Office 365 o il cmdlet Remove-Mailbox ed è stato ancora nel Cestino Azure Active Directory per meno di 30 giorni. Una cassetta postale può diventare eliminate in uno dei modi seguenti:
- La cassetta postale utente associata account utente viene eliminato Azure Active Directory (l'oggetto utente è fuori ambito o nel contenitore recycle bin).
- Account utente di Azure Active Directory associato della cassetta postale utente è stata eliminata, ma la cassetta postale di Exchange Online è in una conservazione per controversia legale o eDiscovery attesa.
- La cassetta postale utente associata account utente è stato eliminato negli ultimi 30 giorni, Azure Active Directory ovvero il periodo di conservazione massimo Exchange Online manterrà la cassetta postale in uno stato eliminato prima che sia in modo permanente eliminati definitivamente.

Una cassetta postale eliminata definitivamente utente è una cassetta postale eliminata in uno dei modi seguenti:
- La cassetta postale utente è stato eliminato per più di 30 giorni e l'utente di Azure Active Directory associato è stata eliminata definitivamente. Tutto il contenuto delle cassette postali, ad esempio messaggi di posta elettronica, contatti e i file vengono eliminati definitivamente.
- L'account utente associato alla cassetta postale utente è stata eliminata da Azure Active Directory. La cassetta postale utente è ora eliminate in Exchange Online e rimane nello stato di eliminazione reversibile per 30 giorni. Se nel periodo di 30 giorni un nuovo utente di Azure Active Directory è sincronizzato dall'account destinatario originale con lo stesso **ExchangeGuid** o **ArchiveGuid**e che viene concesso in licenza nuovo account di Exchange Online, ciò consentirà di eliminazione del disco rigido la cassetta postale utente originale. Tutto il contenuto delle cassette postali, ad esempio messaggi di posta elettronica, contatti e i file vengono eliminati definitivamente.
- Una cassetta postale eliminata viene eliminata tramite **PermanentlyDelete Remove-Mailbox**.

Gli scenari di eliminazione precedente si presuppongono che la cassetta postale utente non si trova in uno Stato esenzione come conservazione per controversia legale o esenzione di eDiscovery. Se non vi è alcun tipo di sospensione della cassetta postale, la cassetta postale non possono essere eliminata. Per tutti i tipi di destinatario utente di posta elettronica, tutte le impostazioni di [conservazione](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e?ui=en-US&rs=en-US&ad=US) vengono ignorate e non hanno effetto sul disco rigido eliminazioni o le eliminazioni reversibile.

## <a name="soft-deleted-and-hard-deleted-items"></a>Elementi eliminate e disco rigido eliminati
Quando un utente elimina un elemento della cassetta postale (ad esempio un messaggio di posta elettronica, un contatto, un appuntamento del calendario o un'attività), l'elemento viene spostato nella cartella elementi recuperabili e in una sottocartella denominata eliminazioni. Questa operazione viene definita un'eliminazione sfumata. Quanto tempo eliminati vengono mantenuti gli elementi nel eliminazioni cartella dipende il periodo di mantenimento impostato per la cassetta postale. Una cassetta postale di Exchange Online consente di mantenere gli elementi eliminati 14 giorni per impostazione predefinita, ma gli amministratori di Exchange Online è possono modificare questa impostazione per aumentare il periodo fino a un massimo di 30 giorni. (Per informazioni dettagliate sulla procedura aumentare il periodo di mantenimento elementi eliminati per una cassetta postale di Exchange Online, vedere [vengono conservati gli elementi eliminato in modo permanente il tempo di modifica per una cassetta postale di Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention).) Gli utenti possono recuperare o eliminare, gli elementi eliminati prima della scadenza del periodo di mantenimento per un elemento eliminato. A tale scopo, utilizzano la funzionalità Recupera elementi eliminati in Microsoft Outlook o Outlook sul web.

Se un utente elimina un elemento eliminato utilizzando la caratteristica Recupera elementi eliminati in Outlook o Outlook sul web, questo è noto come un'eliminazione disco rigido. In Exchange Online, ripristino di singoli elementi è attivato per impostazione predefinita quando si crea una nuova cassetta postale, in modo che un amministratore può comunque [Recupera](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/recover-deleted-messages) elementi eliminati rigido prima della scadenza del periodo di mantenimento elementi eliminati. Inoltre, se un messaggio viene modificato da un utente o un processo, copie dell'elemento originale inoltre vengono mantenute quando ripristino di singoli elementi è attivato.

## <a name="page-zeroing"></a>Azzeramento delle pagine
*Zeroing* è un meccanismo di protezione che scrive gli zero o un formato binario su dati eliminati in modo che i dati eliminati sono più difficili da recuperare. In Exchange Online, database delle cassette postali utilizzano *le pagine* come le unità di archiviazione e implementano un processo di sovrascrittura denominato *azzeramento delle pagine*. Azzeramento delle pagine è abilitata per impostazione predefinita e non può essere disattivata dai clienti o da Microsoft. Operazioni di azzeramento delle pagina vengono registrate nei file di registro delle transazioni in modo che tutte le copie di un determinato database pagina-azzeramento in modo analogo. Azzeramento una pagina di una copia attiva del database, la pagina ottenere azzerate su copie passive del database.

Azzeramento delle pagine scrive un motivo binario su disco rigido eliminati i record. Il motivo di azzeramento delle pagine è specifico per operazioni di motore ESE (Extensible Storage) (il nome del motore di database interno utilizzato dai server in Exchange Online) ed è diverso per le operazioni di runtime e operazioni di manutenzione in background del database. (Manutenzione in background del database è un processo che continuamente checksum e analisi ogni database. La funzione principale è alle pagine di database checksum, ma gestisce inoltre pulitura spazio e di azzeramento delle pagine che non sono state azzerate a causa di un arresto anomalo del sistema di archiviazione e registrate.)

La tabella seguente elenca le sequenze di riempimento che corrispondono a specifiche operazioni runtime.

| Operazione runtime di ESE   | Sequenza di riempimento |
|--------------------------|--------------|
| Sostituisce                  | R            |
| Elimina record/valore lungo | D            |
| Spazio pagina liberato         | H            |


La tabella che segue elenca le sequenze di riempimento che corrispondono alle specifiche operazioni che avvengono durante le operazioni di manutenzione in background di ESE.

| Operazioni di manutenzione in background del database ESE | Motivo riempimento |
|-----------------------------------------------|--------------|
| Elimina record                                 | D            |
| Elimina valore lungo                             | L            |
| Spazio pagina liberato della pagina parzialmente utilizzata       | Z            |
| Spazio pagina liberato della pagina inutilizzata               | U            |


### <a name="page-zeroing-process"></a>Processo di azzeramento pagina
Il processo di azzeramento delle pagine dipende lo scenario di eliminazione. Nella tabella seguente vengono illustrati gli scenari di eliminazione di database e quando si verificano funzione di azzeramento delle pagina.

| Scenario di eliminazione dal database | Processo di ESE e tempi di azzeramento dei dati del database |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Elemento scade al termine del periodo di mantenimento elementi eliminati. | Un thread asincrono scrive una sequenza binaria sui dati eliminati. Questa azione si verifica entro pochi millisecondi dall'eliminazione del record. Se il processo di archiviazione si arresta in modo anomalo mentre è ancora attiva la funzione di azzeramento asincrono (o se viene annullata la funzione di pulitura dell'archivio versioni a causa di un aumento delle dimensioni), l'azzeramento viene completato quando la manutenzione in background del database elabora quella sezione del database. |
| Scenario di visualizzazione: Scadenza di elementi di Outlook e Outlook nella vista della cartella web (ad esempio, visualizzazione conversazione) | L'azzeramento dei dati avviene quando la manutenzione in background del database elabora questa sezione del database. |
| Spostamento delle cassette postali ed eliminazione delle cassette postali Scenario: Cassetta postale di origine eliminata (scadenza della cassetta postale eliminata) | L'azzeramento dei dati avviene quando la manutenzione in background del database elabora questa sezione del database. |

### <a name="mailbox-data-types-without-page-zeroing"></a>Tipo di dati delle cassette postali senza azzeramento delle pagine
I seguenti tipi di dati delle cassette postali non hanno provisioning per l'azzeramento delle pagine:
- **Registri delle transazioni del database delle cassette postali** - quando eliminare i registri delle transazioni durante le normali operazioni, non esiste alcun processo su zero i blocchi del file System che archiviati i file di registro eliminati. È probabile che il file system rapidamente utilizzerà nuovamente che lo spazio disponibile per i registri appena creati, ma non è garantito che questa operazione verrà eseguita.
- **File di catalogo dell'indice di contenuto** - Exchange Online utilizza Search Foundation (noto anche come FAST) per la ricerca la funzionalità di indicizzazione. Il catalogo dell'indice di ricerca è costituito da diversi decine file archiviati nello stesso volume del file di database delle cassette postali. Quando un messaggio viene eliminata dal database delle cassette postali, il contenuto del catalogo di ricerca associato non viene eliminato immediatamente. Eliminazione del contenuto viene generato quando viene Search Foundation un'ombreggiatura o unione master di molti catalogo piccoli file in un unico file di dimensioni maggiore. Una volta completata l'unione master, vengono eliminati i file di catalogo più piccoli. Non esiste alcun processo su zero blocchi che archiviati i file di catalogo eliminato.

## <a name="continuous-replication"></a>Replica continua
Replica continua (noto anche come log shipping e riesecuzione) è la tecnologia di Exchange Online che consente di creare e gestisce le copie di ogni database delle cassette postali per fornire disponibilità elevata, la resilienza del sito e il ripristino di emergenza. Replica continua sfrutta il supporto per il ripristino di Exchange Server database arresto anomalo per fornire la tecnologia che consente di eseguire l'aggiornamento asincroni di uno o più copie di un database delle cassette postali. Ogni server cassette postali vengono registrati gli aggiornamenti di database eseguiti in un database attivo (ad esempio, attività di posta elettronica dell'utente) come record del Registro di un set sequenza dei file di registro delle transazioni 1 MB. Questa serie di file è definita il flusso di log. Nella replica continua, flusso di registri viene inoltre utilizzato per aggiornare in modo asincrono una o più copie di un database. Questa operazione viene eseguita per trasmettere i registri in un percorso contenente una copia passiva del database attivo e quindi la relativa riproduzione nella copia passiva del database. Se tutti i log dal database attivo sono duplicati per una copia passiva del database, quindi i due database sono equivalenti ed è tramite questo processo che qualsiasi fisico modifica apportata a un database attivo viene replicato tutte le copie passive del database.

Qualsiasi eliminazione di un database delle cassette postali, se un elemento della cassetta postale o un'intera cassetta postale e un disco rigido-delete, o un'eliminazione reversibile rappresenta una modifica fisica al database attivo. Azzeramento delle pagine anche comporta apportare modifiche fisiche al database attivo. Queste modifiche vengono scritti i file di registro un processo di replica continua e quando i file di registro sono duplicati per le copie passive del database, vengono apportate le modifiche fisiche stesse a tali database passivi.