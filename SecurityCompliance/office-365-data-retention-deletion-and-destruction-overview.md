---
title: Conservazione, eliminazione e distruzione dei dati in Office 365
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
description: Una panoramica dei criteri Microsoft per Office 365 relativa a conservazione, eliminazione e distruzione dei dati.
ms.openlocfilehash: 79a58381892cfcb773f6e83f129075d6f2037304
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622486"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Conservazione, eliminazione e distruzione dei dati in Office 365

Microsoft dispone di un criterio di gestione dei dati standard per Office 365 che specifica la durata di conservazione dei dati del cliente dopo l'eliminazione. In genere, esistono due scenari in cui vengono eliminati i dati dei clienti:

- **Eliminazione attiva:** Il tenant ha un abbonamento attivo e un utente elimina i dati, oppure Elimina i dati forniti da un utente.
- **Eliminazione passiva:** La sottoscrizione tenant termina.

## <a name="data-retention"></a>Conservazione dei dati

Per ognuno di questi scenari di eliminazione, nella tabella seguente viene mostrato il periodo di conservazione dei dati massimo, per categoria e classificazione dei dati:

| Categoria di dati | Classificazione dei dati | Descrizione | Esempi | Periodo di conservazione |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| Dati cliente
 | Contenuto del cliente| Contenuto direttamente fornito/creato da amministratori e utenti <br><br> Include tutto il testo, audio, video, file di immagine e software creati e archiviati nei data center di Microsoft quando si utilizzano i servizi in Office 365 | Esempi delle applicazioni di Office 365 più comunemente utilizzate che consentono agli utenti di creare dati includono Word, Excel, PowerPoint, Outlook e OneNote <br><br> Il contenuto del cliente include anche i segreti di proprietà dei clienti/forniti (password, certificati, chiavi di crittografia, chiavi di archiviazione) | **Scenario di eliminazione attiva:** al massimo 30 giorni <br><br> **Scenario di eliminazione passiva:** al massimo 180 giorni |
| Dati cliente
 | Informazioni identificabili dall'utente finale (EUII) | Dati che identificano o possono essere utilizzati per identificare l'utente di un servizio Microsoft. EUII non contiene contenuto del cliente | Nome utente o nome visualizzato (dominio\nomeutente) <br><br> Nome dell'entità utente (nome @ dominio) <br><br>  Indirizzi IP specifici dell'utente | **Scenario di eliminazione attiva:** al massimo 180 giorni (solo un'azione di amministratore tenant) <br><br> **Scenario di eliminazione passiva:** al massimo 180 giorni |
| Dati personali <br> (dati non inclusi nei dati del cliente) | Identificatori pseudonimi dell'utente finale (EUPI) | Identificatore creato da Microsoft associato all'utente di un servizio Microsoft. Se in combinazione con altre informazioni, ad esempio una tabella di mapping, EUPI identifica l'utente finale <br><br> EUPI non contiene informazioni caricate o create dal cliente | GUID utente, PUID o SID <br><br> ID di sessione | **Scenario di eliminazione attiva:** al massimo 30 giorni <br><br> **Scenario di eliminazione passiva:** al massimo 180 giorni |

## <a name="subscription-retention"></a>Conservazione della sottoscrizione

Nel termine di un abbonamento attivo, un Sottoscrittore può accedere, estrarre o eliminare i dati dei clienti archiviati in Office 365. Se una sottoscrizione a pagamento termina o è terminata, Microsoft conserva i dati dei clienti archiviati in Office 365 in un account con funzione limitata per 90 giorni per consentire al Sottoscrittore di estrarre i dati. Al termine del periodo di conservazione di 90 giorni, Microsoft disattiva l'account ed Elimina i dati del cliente. Non più di 180 giorni dopo la scadenza o la terminazione di un abbonamento a Office 365, Microsoft disattiva l'account ed Elimina tutti i dati dei clienti dall'account. Una volta trascorso il periodo di conservazione massimo per tutti i dati, i dati vengono resi commercialmente irrecuperabili.

Per una versione di valutazione gratuita, il tuo account si sposta in uno stato di grazia per 30 giorni nella maggior parte dei paesi e delle aree geografiche. Durante questo periodo di tolleranza è possibile acquistare Office 365. Se si decide di non acquistare Office 365, è possibile annullare la versione di valutazione o lasciare scadere il periodo di prova e le informazioni e i dati dell'account di valutazione vengono eliminati.

## <a name="expedited-deletion"></a>Eliminazione rapida

Per qualsiasi sottoscrizione, un Sottoscrittore può contattare il supporto tecnico Microsoft e richiedere il deprovisioning di sottoscrizione celere. In questo processo, tutti i dati degli utenti vengono eliminati tre giorni dopo l'immissione del codice di blocco fornito da Microsoft. Sono inclusi i dati in SharePoint Online e Exchange online in blocco o archiviati in cassette postali inattive.

Per ulteriori informazioni sul deprovisioning rapido, vedere [Annulla Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).

## <a name="related-links"></a>Collegamenti correlati
- [Distruzione dei dati](office-365-data-destruction.md)
- [Capacità di immutabilità in Office 365](office-365-data-immutability.md)
- [Eliminazione dei dati di Exchange Online](office-365-exchange-online-data-deletion.md)
- [Eliminazione dei dati di SharePoint Online](office-365-sharepoint-online-data-deletion.md)
- [Eliminazione dei dati di Skype for Business](office-365-skype-data-deletion.md)