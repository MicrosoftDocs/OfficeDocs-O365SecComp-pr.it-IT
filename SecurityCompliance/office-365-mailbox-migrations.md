---
title: Migrazioni delle cassette postali di Office 365
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
description: Un breve riepilogo dei cmdlet utilizzati per le migrazioni delle cassette postali di Office 365.
ms.openlocfilehash: 8e0f23a3efbbcf6f84364c09e667678972120e18
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219146"
---
# <a name="office-365-mailbox-migrations"></a>Migrazioni delle cassette postali di Office 365
Con una distribuzione ibrida basata su Exchange, i clienti possono scegliere di spostare le cassette postali di Exchange locali in un'organizzazione di [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) o di spostare le cassette postali di Exchange online in un'organizzazione di [Exchange locale](https://docs.microsoft.com/Exchange/exchange-server) . Quando si spostano le cassette postali tra organizzazioni locali e di Exchange Online, vengono utilizzati i batch di migrazione. I clienti possono esaminare le statistiche e altre informazioni sulle migrazioni delle cassette postali utilizzando i seguenti cmdlet:

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -fornisce statistiche predefinite per una cassetta postale utente, che include lo stato, la dimensione della cassetta postale, la dimensione della cassetta postale di archiviazione e la percentuale di completamento.
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -fornisce un elenco riepilogativo degli oggetti e degli attributi delle cassette postali nell'organizzazione.
- [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) -fornisce un elenco di oggetti esistenti abilitati alla posta elettronica, quali cassette postali, utenti di posta elettronica, contatti e gruppi di distribuzione.
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -fornisce uno stato dettagliato di una migrazione delle cassette postali in uscita.
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -fornisce informazioni sullo spostamento delle cassette postali e sugli utenti di migrazione.
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -fornisce informazioni sullo stato del batch di migrazione corrente.
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -fornisce informazioni dettagliate sullo stato della migrazione per un utente specifico.
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -vengono fornite informazioni sulle cassette postali, ad esempio le dimensioni, il numero di messaggi e l'ora dell'ultimo accesso.

Per ulteriori informazioni sui cmdlet aggiuntivi, vedere [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).
