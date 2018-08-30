---
title: Migrazioni delle cassette postali di Office 365
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
description: Un breve riepilogo dei cmdlet utilizzati per le migrazioni delle cassette postali di Office 365.
ms.openlocfilehash: 86896d956072b5c11e3b3292363bb32312ff1187
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531054"
---
# <a name="office-365-mailbox-migrations"></a>Migrazioni delle cassette postali di Office 365
Per una distribuzione ibrida basata su Exchange, i clienti è possono scegliere di spostare cassette postali di Exchange locale a un'organizzazione di [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) o spostare le cassette postali di Exchange Online in un'organizzazione di [Exchange in locale](https://docs.microsoft.com/Exchange/exchange-server) . Batch di migrazione vengono utilizzati durante lo spostamento delle cassette postali tra organizzazioni Exchange Online e locale. I clienti possono esaminare le statistiche e altre informazioni sulle migrazioni delle cassette postali utilizzando i cmdlet seguenti:

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - fornisce le statistiche predefinite per una cassetta postale utente, che include lo stato, la dimensione della cassetta postale, archiviare dimensione della cassetta postale e percentuale di completamento.
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) - offre un elenco riepilogativo di oggetti cassetta postale e gli attributi dell'organizzazione.
- [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) - viene fornito un elenco di oggetti abilitati alla posta elettronica esistenti, ad esempio le cassette postali, utenti di posta elettronica, contatti e gruppi di distribuzione.
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) - fornisce un stato dettagliato di una migrazione delle cassette postali in corso.
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - vengono fornite informazioni sulla cassetta postale migrazione e spostamento di utenti.
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - fornisce informazioni sullo stato del batch di migrazione corrente.
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - fornisce informazioni dettagliate sullo stato di migrazione di un utente specifico.
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) - vengono fornite informazioni sulle cassette postali, ad esempio dimensioni, il numero di messaggi e ora dell'ultimo accesso.

Per ulteriori informazioni su altri cmdlet, vedere [cmdlet di migrazione e spostamento in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).
