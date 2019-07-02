---
title: Panoramica di Office 365 eDiscovery e delle funzionalità di ricerca
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
description: Panoramica della caratteristica eDiscovery e di altre funzionalità di ricerca di Office 365 per l'utilizzo e la trasparenza di controllo.
ms.openlocfilehash: 985a7fad9d321005439ea592b6fef8744a88220f
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622456"
---
# <a name="ediscovery-and-search-features"></a>Funzionalità di ricerca e di eDiscovery 

## <a name="ediscovery"></a>eDiscovery

La caratteristica eDiscovery fornisce un'unica posizione per gli amministratori, i responsabili della conformità e altri utenti autorizzati a eseguire un'indagine completa sull'attività degli utenti di Office 365. Gli addetti alla sicurezza con le autorizzazioni appropriate eseguono ricerche e conservazioni sul contenuto. I risultati della ricerca sono gli stessi risultati ottenuti da una ricerca di contenuto, ad eccezione dei casi di eDiscovery creati per qualsiasi esenzione applicata. I risultati delle ricerche di eDiscovery sono crittografati per la sicurezza ed è possibile analizzare i dati esportati con [eDiscovery avanzato](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4).

## <a name="content-search"></a>Ricerca contenuto

La [ricerca di contenuti](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) è uno strumento di ricerca di eDiscovery che offre funzionalità di ridimensionamento e prestazioni migliorate rispetto agli strumenti di ricerca di eDiscovery precedenti. Si utilizza la ricerca contenuto per cercare le cassette postali, le cartelle pubbliche, i siti di SharePoint Online e le posizioni di OneDrive for business. La ricerca contenuto supporta ricerche di grandi dimensioni. Non esistono limiti al numero di cassette postali e siti in cui è possibile eseguire la ricerca. Non sono previsti limiti al numero di ricerche eseguite contemporaneamente. Dopo aver eseguito una ricerca, il numero di origini di contenuto e il numero stimato di risultati della ricerca vengono visualizzati nel riquadro dei dettagli della pagina di ricerca. È possibile visualizzare in anteprima i risultati o esportarli in un computer locale. Se l'organizzazione dispone di un abbonamento a Office 365 Enterprise E5, è possibile [preparare i risultati](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare) per l'analisi utilizzando le potenti funzionalità di analisi di [Office 365 Advanced eDiscovery](http://go.microsoft.com/fwlink/p/?LinkID=620116).

## <a name="audit-log-search"></a>Ricerca nel log di controllo

Oltre a tenere traccia delle modifiche apportate all'organizzazione di Office 365, è possibile visualizzare i report di controllo ed esportare i registri di controllo. Una volta abilitata la funzionalità di controllo per un tenant di Office 365, le attività utente e amministrative vengono registrate nei registri eventi e rese disponibili per la ricerca. Ad esempio, è possibile utilizzare la registrazione di controllo delle cassette postali per controllare le azioni eseguite su una cassetta postale da parte di utenti diversi dal proprietario della cassetta postale. I responsabili della conformità possono utilizzare le funzionalità di ricerca e filtro per specifiche attività utente. Ad esempio, per identificare gli utenti che hanno visualizzato o scaricato un documento specifico, se gli amministratori hanno eseguito attività di gestione degli utenti o per visualizzare le modifiche apportate alla configurazione del tenant negli ultimi 90 giorni. I risultati della ricerca contengono preziose informazioni forensi su specifiche attività svolte da un utente o da un amministratore. Per una descrizione dell'utente e delle attività amministrative registrate in Office 365, vedere [attività controllate in office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents) .

Gli eventi provenienti da SharePoint Online e OneDrive for business vengono visualizzati nel registro entro 30 minuti dall'occorrenza. Gli eventi provenienti da Exchange Online vengono visualizzati nei registri di controllo entro 24 ore dalla ricorrenza. Gli eventi di accesso da Azure AD sono disponibili entro pochi minuti dall'occorrenza e altri eventi di directory di Azure AD sono disponibili entro 24 ore dall'evento. È possibile esportare le aperture nei risultati della ricerca dei log di controllo per ulteriori analisi. Vengono esportate al massimo 50.000 voci dalla ricerca del registro di controllo singolo. Per esportare più voci che questo limite, ridurre l'intervallo di date o eseguire più ricerche nei registri di controllo.

Nella tabella seguente vengono illustrate alcune delle informazioni visualizzate nei report attività. Per ulteriori informazioni sulle proprietà raccolte da ogni carico di lavoro di Office 365, vedere le [proprietà dettagliate nel log di controllo di office 365](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3) .

| Proprietà | Descrizione |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| Data | Data e ora dell'evento |
| Utente | Utente che ha eseguito l'azione |
| ClientIP | Indirizzo IPv4 o IPv6 del dispositivo utilizzato quando è stata registrata l'attività. |
| CreationTime | Data e ora in formato UTC (Coordinated Universal Time) quando l'utente ha eseguito l'attività. |
| EventSource | Indica che si è verificato un evento. I valori possibili sono SharePoint e ObjectModel. |
| ID | ID della voce del report. L'ID identifica in modo univoco la voce del report. |
| Operazione | Nome dell'utente o dell'attività, che corrisponde al valore selezionato nei risultati di visualizzazione per l'attività dell'utente. |
| IDOrganizzazione | GUID per il servizio Office 365 dell'organizzazione in cui si è verificato l'evento. |
| UserAgent | Informazioni sul browser dell'utente, fornite dal browser. |
| UserId | Utente che ha eseguito l'azione, specificata nella proprietà Operation, che ha provocato la registrazione del record. |
| UserType | Tipo di utente che ha eseguito l'operazione. I valori riportati di seguito indicano il tipo di utente. |
|  | 0 indica un utente normale. |
|  | 2 indica un amministratore dell'organizzazione di Office 365. |
|  | 3 indica un amministratore di Microsoft Datacenter o un account di sistema datacenter. |
| Carico di lavoro | Servizio Office 365 in cui si è verificata l'attività. I valori possibili per questa proprietà sono: |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive for Business |
|  | Report di Azure Active Directory |

Per la procedura dettagliata per la ricerca nei registri di controllo di Office 365, vedere [Searching Audit Logs in the office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="search-unified-audit-log"></a>Log di controllo unificato di ricerca

Utilizzare la funzionalità di ricerca del registro di controllo per eseguire una ricerca nel log di controllo unificato. Office 365 offre inoltre la possibilità di eseguire ricerche in questo registro tramite Remote PowerShell. Il [cmdlet Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps) in Exchange Online PowerShell viene utilizzato per eseguire ricerche nel log di controllo unificato degli eventi relativi alle operazioni degli utenti da Exchange Online, SharePoint Online, OneDrive for business e Azure ad. 

È possibile cercare tutti gli eventi in un intervallo di date specificato oppure è possibile filtrare i risultati in base a criteri specifici, ad esempio un'azione specifica, l'utente che ha eseguito l'azione o l'oggetto di destinazione. Gli amministratori possono utilizzare fino a tre sessioni di PowerShell di Exchange Online contemporaneamente per dividere le ricerche di un intervallo di date di grandi dimensioni.