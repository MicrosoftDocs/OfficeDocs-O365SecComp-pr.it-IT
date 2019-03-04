---
title: Come ridurre la posta indesiderata in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
description: Informazioni su vari modi per ridurre la posta indesiderata in Office 365.
ms.openlocfilehash: e1915bd51fcda8b587f3a7f248dc54fa18941c7d
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30340887"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Come ridurre la posta indesiderata in Office 365

 **Si riceve troppa posta indesiderata in Office 365? Ecco cosa fare.**
  
È consigliabile segnalare i messaggi falsi negativi [usando il componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) per aiutarci a migliorare i filtri. È anche possibile inoltrare il messaggio *come allegato* a junk@office365.microsoft.com o a phish@office365.microsoft.com (se si tratta di phishing).

> [!TIP]
> Se si ritiene che il messaggio è indesiderato e si trova nella cartella Posta indesiderata, questo non costituisce un problema. Se non si vuole visualizzarlo nella cassetta postale, è consigliabile modificare i criteri di filtro posta indesiderata per mettere in quarantena il messaggio. Per altre informazioni su come mettere in quarantena un messaggio, vedere [Mettere in quarantena i messaggi di posta elettronica in Office 365](quarantine-email-messages.md).

## <a name="fixing-allowed-spam"></a>Correzione della posta indesiderata consentita

Capita spesso che i clienti ricevano posta indesiderata nella Posta in arrivo a causa di configurazioni errate. Le configurazioni errate più comuni riguardano la configurazione dei domini in una regola di flusso di posta (nota anche come regola di trasporto) per ignorare i filtri oppure l'inserimento di domini nell'elenco di mittenti consentiti/attendibili. Questa configurazione non è valida perché questi messaggi non sono soggetti al filtro posta indesiderata e diversamente avrebbero potuto essere rilevati.  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>Soluzioni ad altre cause comuni della quantità elevata di posta indesiderata

Per proteggersi dalla ricezione di troppa posta indesiderata, Exchange Online Protection (EOP) chiede agli amministratori di completare alcune operazioni. Se non si è un amministratore del proprio tenant di Office 365 e si riceve troppa posta indesiderata, eseguire tali operazioni con l'amministratore. In caso contrario, è possibile passare alla sezione per gli utenti.
  
### <a name="for-admins"></a>Per gli amministratori

- **Impostare i record DNS in modo che puntino a Office 365** Affinché EOP fornisca la protezione ottimale, i record DNS di Mail Exchanger (MX) per tutti i domini devono puntare esclusivamente a Office 365. Vedere [Creare i record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
    
- **Attivare la regola della posta indesiderata in tutte le cassette postali** Per impostazione predefinita, l'operazione del filtro protezione da posta indesiderata è impostata su **Sposta messaggio nella cartella di posta indesiderata**. Se si tratta dell'azione del criterio di posta indesiderata corrente, allora in ogni cassetta postale [deve anche essere attivata la regola della posta indesiderata](https://support.office.com/it-IT/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Per verificarlo, è possibile eseguire il cmdlet Get-MailboxJunkEmailConfiguration su una o più cassette postali. Ad esempio, è possibile verificare tale condizione in tutte le cassette postali eseguendo: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    Visualizzando il risultato, la proprietà Enable deve essere impostata su True. Se è impostata su False, è possibile eseguire Set-MailboxJunkEmailConfiguration per impostarla su True.
    
- **Creare regole del flusso di posta nel server Exchange locale** Se si usa Exchange Online Protection, ma le cassette postali si trovano nel server Exchange locale, è necessario creare due regole del flusso di posta nel server Exchange locale. Vedere le [istruzioni relative solo a Exchange Online Protection](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).
    
- **Contrassegnare la posta elettronica inviata in massa come posta indesiderata** La posta elettronica inviata in massa è costituita da messaggi di posta elettronica per cui gli utenti hanno effettuato la registrazione, ma che potrebbero essere comunque indesiderati. Nell'intestazione del messaggio individuare la proprietà BCL (Bulk Confidence Level) nell'intestazione X-Microsoft-Antispam. Se il valore di BCL è inferiore alla soglia impostata nel filtro protezione da posta indesiderata, è consigliabile modificare la soglia invece di contrassegnare questi tipi di posta elettronica inviata in massa come posta indesiderata. Le tolleranze e le preferenze relative alla gestione della [posta elettronica inviata in massa](https://docs.microsoft.com/it-IT/office365/SecurityCompliance/bulk-complaint-level-values) variano da utente a utente. È possibile creare regole o criteri diversi in base alle preferenze degli utenti. 
    
- **Bloccare immediatamente un mittente** Se occorre bloccare immediatamente un mittente, è possibile applicare il blocco in base all'indirizzo di posta elettronica, al dominio o all'indirizzo IP. Vedere [Usare l'interfaccia di amministrazione di Exchange per creare una regola di flusso di posta che blocchi i messaggi inviati da un dominio](create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md#use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user). Tenere presente che una voce nell'elenco di indirizzi consentiti di un utente finale può impedire l'applicazione di un blocco impostato dall'amministratore.
    
- **Attivare il componente aggiuntivo Segnala messaggio per gli utenti** È consigliabile [attivare il componente aggiuntivo Segnala messaggio per gli utenti](enable-the-report-message-add-in.md). Un amministratore può anche visualizzare i commenti e suggerimenti inviati dagli utenti e utilizzare i modelli per modificare le impostazioni che potrebbero causare problemi.
    
### <a name="for-users"></a>Per gli utenti

- **Abilitare la regola della posta indesiderata e controllare l'elenco elementi attendibili** Verificare he la regola di azione della posta indesiderata sia attiva e che il mittente o il dominio del mittente non sia configurato per ignorare l'elenco di elementi attendibili personale. Il modo migliore per accedere a queste impostazioni è da [Blocca o consenti (impostazioni di posta indesiderata)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Qui, è anche possibile bloccare l'indirizzo di posta elettronica o il dominio del mittente.
    
- **Segnalare la posta indesiderata a Microsoft** Segnalare la posta indesiderata a Microsoft usando il [componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). È inoltre possibile inviare un messaggio all'indirizzo junk@office365.microsoft.com e allegare uno o più messaggi da segnalare.
    
    **Importante** Se non si inoltrano i messaggi come allegati, mancheranno le intestazioni e non potremo migliorare il filtro protezione da posta indesiderata di Office 365. 
    
- **Annullare l'iscrizione alla posta elettronica inviata in massa** Se il messaggio proviene da indirizzo alla quale ci si è iscritti (newsletter, prodotti e così via) e contiene un collegamento per annullare iscrizione di una fonte attendibile, è consigliabile semplicemente annullare l'iscrizione. Office 365 generalmente non gestisce questi messaggi come posta indesiderata. È anche possibile bloccare il mittente oppure rivolgersi all'amministratore per apportare una modifica affinché tutta la posta inviata in massa venga considerata posta indesiderata.
