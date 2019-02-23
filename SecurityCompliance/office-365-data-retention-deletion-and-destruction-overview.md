---
title: Conservazione, eliminazione e distruzione dei dati in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Una panoramica dei criteri di Microsoft per Office 365 relativamente alla conservazione, all'eliminazione e alla distruzione dei dati.
ms.openlocfilehash: 6aa272ece723aa83e15581062fd2348c508b04d5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219956"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Conservazione, eliminazione e distruzione dei dati in Office 365

Microsoft dispone di un criterio di gestione dei dati standard per Office 365 che specifica la durata di conservazione dei dati del cliente dopo essere stata eliminata. In genere, esistono due scenari in cui vengono eliminati i dati dei clienti:

- **Eliminazione attiva** : il tenant ha un abbonamento attivo e un utente elimina i dati o i dati forniti da un utente vengono eliminati dall'amministratore.
- **Eliminazione passiva** -termina la sottoscrizione tenant.

## <a name="data-retention"></a>Conservazione dei dati

Per ognuno di questi scenari di eliminazione, nella tabella seguente viene mostrato il periodo di conservazione dei dati massimo, per categoria e classificazione dei dati:

| Categoria di dati | Classificazione dei dati | Descrizione | Esempi | Periodo di conservazione |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| Dati cliente
 | Contenuto del cliente| Contenuto direttamente fornito/creato da amministratori e utenti <br><br> Questo include tutto il testo, audio, video, file di immagine e software creati e archiviati nei data center di Microsoft quando si utilizzano i servizi in Office 365 | Esempi delle applicazioni di Office 365 più comunemente utilizzate che consentono agli utenti di creare dati tra cui Word, Excel, PowerPoint, Outlook e OneNote <br><br> Il contenuto del cliente include anche i segreti di proprietà dei clienti/forniti (password, certificati, chiavi di crittografia, chiavi di archiviazione) | **Scenario di eliminazione attiva:** al massimo 30 giorni <br><br> **Scenario di eliminazione passiva:** al massimo 180 giorni |
| Dati cliente
 | Informazioni identificabili dall'utente finale (EUII) | Dati che identificano o possono essere utilizzati per identificare l'utente di un servizio Microsoft. EUII non contiene contenuto del cliente | Nome utente o nome visualizzato (dominio\nomeutente) <br><br> Nome dell'entità utente (nome @ dominio) <br><br>  Indirizzi IP specifici dell'utente | **Scenario di eliminazione attiva:** al massimo 180 giorni (solo un'azione di amministratore tenant) <br><br> **Scenario di eliminazione passiva:** al massimo 180 giorni |
| Dati personali <br> (dati non inclusi nei dati del cliente) | Identificatori pseudonimi dell'utente finale (EUPI) | Identificatore creato da Microsoft associato all'utente di un servizio Microsoft. Quando EUPI viene combinato con altre informazioni, ad esempio una tabella di mapping, identifica l'utente finale <br><br> EUPI non contiene informazioni caricate o create dal cliente | GUID utente, PUID o SID <br><br> ID di sessione | **Scenario di eliminazione attiva:** al massimo 30 giorni <br><br> **Scenario di eliminazione passiva:** al massimo 180 giorni |

## <a name="subscription-retention"></a>Conservazione della sottoscrizione

In qualsiasi momento, durante il periodo di un abbonamento attivo, un Sottoscrittore può accedere, estrarre o eliminare i dati dei clienti archiviati in Office 365. Se una sottoscrizione a pagamento termina o è terminata, Microsoft manterrà i dati dei clienti archiviati in Office 365 in un account con funzione limitata per 90 giorni per consentire al Sottoscrittore di estrarre i dati. Al termine del periodo di conservazione di 90 giorni, Microsoft disattiverà l'account ed eliminerà i dati del cliente. Non più di 180 giorni dopo la scadenza o la terminazione di un abbonamento a Office 365, Microsoft disattiverà l'account ed eliminerà tutti i dati dei clienti dall'account. Una volta trascorso il periodo di conservazione massimo per tutti i dati, i dati vengono resi commercialmente irrecuperabili.

Nel caso di una versione di valutazione gratuita, il tuo account passerà a uno stato di grazia per 30 giorni nella maggior parte dei paesi e delle aree geografiche. Durante questo periodo di prova, si ha la possibilità di acquistare Office 365. Se si decide di non acquistare Office 365, è possibile annullare la versione di valutazione o lasciare scadere il periodo di prova e le informazioni e i dati dell'account di valutazione verranno eliminati.

## <a name="expedited-deletion"></a>Eliminazione rapida
In qualsiasi momento, durante il periodo di qualsiasi sottoscrizione, un Sottoscrittore può contattare il supporto tecnico Microsoft e richiedere il deprovisioning degli abbonamenti celeri. In questo processo, tutti i dati degli utenti, inclusi i dati in SharePoint Online, Exchange Online che possono essere archiviati in cassette postali inattive, vengono eliminati tre giorni dopo che l'amministratore ha inserito il codice di blocco fornito da Microsoft. Per ulteriori informazioni sul deprovisioning rapido, vedere [Annulla Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).

## <a name="related-links"></a>Collegamenti correlati
- [Distruzione dei dati](office-365-data-destruction.md)
- [Capacità di immutabilità in Office 365](office-365-data-immutability.md)
- [Eliminazione dei dati di Exchange Online](office-365-exchange-online-data-deletion.md)
- [Eliminazione dei dati di SharePoint Online](office-365-sharepoint-online-data-deletion.md)
- [Eliminazione dei dati di Skype for Business](office-365-skype-data-deletion.md)