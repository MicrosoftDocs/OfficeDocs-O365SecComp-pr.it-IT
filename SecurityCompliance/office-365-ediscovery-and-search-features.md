---
title: Office 365 eDiscovery e panoramica sulle funzionalità di ricerca
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
description: Panoramica della funzionalità eDiscovery e altre funzionalità di ricerca in Office 365 per l'utilizzo di controllo e la trasparenza.
ms.openlocfilehash: 2d5cc2533c195b51f685aebd8da4462518116905
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530832"
---
# <a name="ediscovery-and-search-features"></a>Funzionalità di ricerca e di eDiscovery 

## <a name="ediscovery"></a>eDiscovery
La funzionalità eDiscovery fornisce un'unica posizione per gli amministratori, responsabili della conformità, e altro autorizzato agli utenti di eseguire un'analisi completa in attività degli utenti di Office 365. Responsabili della sicurezza con le autorizzazioni appropriate possono eseguire ricerche e archiviazioni sul posto nel contenuto. I risultati della ricerca sono gli stessi risultati che viene visualizzato da una ricerca di contenuto, ad eccezione del fatto che viene creato un caso di eDiscovery per qualsiasi esenzioni che vengono applicate. I risultati delle ricerche di eDiscovery sono crittografati per la protezione e i dati esportati possono essere analizzati tramite [eDiscovery avanzate](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4).

## <a name="content-search"></a>Ricerca contenuto
[Ricerca del contenuto](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) è un nuovo strumento di ricerca di eDiscovery per la protezione e centro conformità che offre maggiore scalabilità e le prestazioni tramite gli strumenti di ricerca di eDiscovery precedente. È possibile utilizzare ricerca contenuto per la ricerca di cassette postali, le cartelle pubbliche, siti di SharePoint Online e OneDrive per i percorsi di Business. Ricerca del contenuto è stato appositamente progettato per le ricerche di grandi dimensioni. Non esistono limiti sul numero di cassette postali e i siti che è possibile eseguire la ricerca. Non vi sono inoltre alcun limite al numero di ricerche che è possibile eseguire contemporaneamente. Dopo aver eseguito la ricerca, il numero di origini di contenuto e il numero stimato di ricerca di risultati vengono visualizzati nel riquadro dei dettagli della pagina ricerca, dove è possibile visualizzare in anteprima i risultati o le Esporta in un computer locale. Se l'organizzazione dispone di una sottoscrizione a Office 365 Enterprise E5, è inoltre possibile [preparare i risultati](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare) dell'analisi dell'utilizzo delle funzionalità analitica potenti di [Office 365 avanzate eDiscovery](http://go.microsoft.com/fwlink/p/?LinkID=620116).

## <a name="audit-log-search"></a>Ricerca dei registri di controllo
Oltre a tenere traccia delle modifiche all'interno dell'organizzazione Office 365, i clienti possono inoltre visualizzare i report di controllo ed esportare i registri di controllo. Una volta per un tenant di Office 365 è abilitato il controllo, utente e all'attività amministrative per il tenant viene registrato nei registri eventi e apportate supportano la ricerca. Ad esempio, è possibile utilizzare la registrazione per tenere traccia delle azioni eseguite su una cassetta postale da utenti diversi dal proprietario della cassetta postale di controllo delle cassette postali. Inoltre, responsabili della conformità possono utilizzare le funzionalità di ricerca e filtro per verificare se un utente dispone di visualizzare o scaricare un documento specifico o se un amministratore ha eseguito le attività di gestione o apportate modifiche alla configurazione del tenant negli ultimi 90 giorni. Risultati della ricerca può contenere utili informazioni sulle attività specifiche che sono stati eseguiti da un utente o un amministratore. Per una descrizione dell'utente e le attività di amministrazione che vengono registrate in Office 365, vedere [attività di Audited in Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents) .

Gli eventi da SharePoint Online e OneDrive for Business vengono visualizzati nel Registro di 30 minuti di loro occorrenza. Eventi da Exchange Online vengono visualizzati nel log di controllo entro 24 ore di occorrenza. Sono disponibili gli eventi di account di accesso di Azure Active Directory all'interno di minuti di occorrenza e altri eventi di directory di Azure Active Directory sono disponibili all'interno di 24 ore di occorrenza. Gli eventi nei risultati della ricerca di log di controllo possono essere esportati anche per un'ulteriore analisi. (Un massimo di 50.000 voci può essere esportato da una ricerca dei registri di controllo singolo. Per esportare più voci che questo limite, ridurre l'intervallo di date, oppure eseguire ricerche del Registro di controllo più.)

Nella tabella seguente vengono illustrati alcuni delle informazioni visualizzate nei rapporti di attività. Vedere il [Registro di controllo proprietà dettagliate in Office 365](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3
) per ulteriori informazioni sulle proprietà vengono raccolti da ogni carico di lavoro di Office 365.

| Proprietà | Descrizione |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| Data | Data e ora dell'evento |
| Utente | Utente che ha eseguito l'azione |
| ClientIP | Indirizzo IPv4 o IPv6 del dispositivo utilizzato quando ha effettuato l'accesso all'attività. |
| CreationTime | Data e ora in ora UTC (Coordinated) quando l'utente ha eseguito l'attività. |
| EventSource | Identifica che si è verificato un evento. I valori possibili sono SharePoint e ObjectModel. |
| ID | ID della voce del report. L'ID identifica in modo univoco la voce del report. |
| Operazione | Nome dell'utente o l'attività che corrisponde al valore selezionato nei risultati della visualizzazione per questa attività dell'utente. |
| OrganizationId | GUID del servizio di Office 365 dell'organizzazione in cui si è verificato l'evento. |
| UserAgent | Informazioni sui browser dell'utente come fornito dal browser. |
| ID utente | Utente che ha eseguito l'azione (specificato nella proprietà Operation) che hanno generato il record registrato. |
| UserType | Tipo di utente che ha eseguito l'operazione. I valori seguenti indicano il tipo di utente. |
|  | 0 indica che un utente normale. |
|  | 2 indica un amministratore dell'organizzazione Office 365. |
|  | 3 indica un account sistema amministratore o Data Center del Data Center di Microsoft. |
| Carico di lavoro | Servizio Office 365 in cui si è verificato l'attività. I valori possibili per la proprietà sono: |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive for Business |
|  | Rapporti di Azure Active Directory |


Per informazioni dettagliate sulla ricerca di Office 365 registri di controllo, vedere [i registri di controllo ricerca nel centro conformità protezione di Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="search-unified-audit-log"></a>Ricerca unificata Log di controllo
La funzionalità di ricerca dei registri di controllo nel centro conformità protezione consente di eseguire ricerche nel Registro di controllo unificato. Office 365 offre la possibilità di eseguire ricerche questo registro utilizzando PowerShell remoto. In particolare, il [cmdlet Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps) in Exchange Online PowerShell può essere utilizzato per cercare il Registro di controllo unificato degli eventi relativi alle operazioni utente di Exchange Online, SharePoint Online, OneDrive for Business e Azure Active Directory. È possibile cercare tutti gli eventi in un intervallo di date specificato oppure è possibile filtrare i risultati in base a criteri specifici, ad esempio un'azione specifica, l'utente che ha eseguito l'azione o l'oggetto di destinazione. Gli amministratori possono utilizzare fino a 3 eseguiti contemporaneamente le sessioni di Exchange Online PowerShell per suddividere le ricerche di intervallo date di grandi dimensioni.
