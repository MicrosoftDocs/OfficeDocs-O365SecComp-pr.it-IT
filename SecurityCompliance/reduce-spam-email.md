---
title: Come ridurre la posta indesiderata in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
description: Informazioni su vari modi per ridurre la posta indesiderata in Office 365.
ms.openlocfilehash: fc7181333b9914673c9919d7132af99fec294773
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219926"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Come ridurre la posta indesiderata in Office 365

 **Si riceve troppa posta indesiderata in Office 365? Ecco cosa fare.**
  
Per risolvere molti problemi relativi alla posta indesiderata in Office 365, è possibile [visualizzare le intestazioni dei messaggi di posta elettronica](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) per determinare la causa del problema. L'intestazione da cercare è X-Forefront-Antispam-Report.

  La presenza della stringa SFV:NSPM indica che Exchange Online Protection (EOP) ha analizzato il messaggio e non lo ha considerato come posta indesiderata. Se si ritiene che lo sia, si tratta di un falso negativo. In tal caso è consigliabile [usare il componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) per consentirci di migliorare i filtri.

  Se questo valore non è presente nelle intestazioni, è possibile che il messaggio non è stato analizzato oppure che un problema di configurazione ha impedito che il messaggio venisse preso in considerazione. In tal caso, consultare le informazioni seguenti. 
  
È possibile ottenere maggiori informazioni sulle [intestazioni dei messaggi della protezione da posta indesiderata](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).

## <a name="solutions-to-common-causes-of-getting-too-much-spam"></a>Soluzioni alle cause comuni della quantità elevata di posta indesiderata

Per proteggersi dalla ricezione di troppa posta indesiderata, Exchange Online Protection (EOP) chiede agli amministratori di completare alcune operazioni. Se non si è un amministratore del proprio tenant di Office 365 e si riceve troppa posta indesiderata, eseguire tali operazioni con l'amministratore. In caso contrario, è possibile passare alla sezione per gli utenti.
  
### <a name="for-admins"></a>Per gli amministratori

- **Impostare i record DNS in modo che puntino a Office 365** Affinché EOP fornisca la protezione ottimale, i record DNS di Mail Exchanger (MX) per tutti i domini devono puntare esclusivamente a Office 365. Vedere [Creare i record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
    
- **Attivare la regola della posta indesiderata in tutte le cassette postali** Per impostazione predefinita, l'operazione del filtro protezione da posta indesiderata è impostata su **Sposta messaggio nella cartella di posta indesiderata**. Se si tratta dell'azione del criterio di posta indesiderata corrente, allora in ogni cassetta postale [deve anche essere attivata la regola della posta indesiderata](https://support.office.com/it-IT/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Per verificarlo, è possibile eseguire il cmdlet Get-MailboxJunkEmailConfiguration su una o più cassette postali. Ad esempio, è possibile verificare tale condizione in tutte le cassette postali eseguendo: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    Visualizzando il risultato, la proprietà Enable deve essere impostata su True. Se è impostata su False, è possibile eseguire Set-MailboxJunkEmailConfiguration per impostarla su True.
    
- **Verificare le regole del flusso di posta e gli elenchi elementi attendibili** Cercare l'intestazione del messaggio di un messaggio contrassegnato come posta indesiderata. Trovare la proprietà SCL nell'intestazione X-Forefront-Antispam-Report. Se il valore SCL è -1, significa che il messaggio era sicuro e ha superato il filtro protezione da posta indesiderata EOP. Analizzare le regole del flusso di posta, gli elenchi di elementi attendibili e l'elenco dei mittenti attendibili del destinatario. L'articolo [Individuare e risolvere i problemi di recapito della posta elettronica come amministratore di Office 365 per le aziende](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) potrebbe essere utile in quanto fornisce dettagli sul perché a un messaggio è stato assegnato un SCL pari a -1. 
    
- **Creare regole del flusso di posta nel server Exchange locale** Se si usa Exchange Online Protection, ma le cassette postali si trovano nel server Exchange locale, è necessario creare due regole del flusso di posta nel server Exchange locale. Vedere le [istruzioni relative solo a Exchange Online Protection](https://technet.microsoft.com/library/ms.exch.eac.EditAntispamPolicy_SpamAction%28EXCHG.150%29.aspx?v=15.20.548.14&amp;l=1&amp;s=BPOS_S_E15_0).
    
- **Contrassegnare la posta elettronica inviata in massa come posta indesiderata** La posta elettronica inviata in massa è costituita da messaggi di posta elettronica per cui gli utenti hanno effettuato la registrazione, ma che potrebbero essere comunque indesiderati. Nell'intestazione del messaggio individuare la proprietà BCL (Bulk Confidence Level) nell'intestazione X-Microsoft-Antispam. Se il valore di BCL è inferiore alla soglia impostata nel filtro protezione da posta indesiderata, è consigliabile modificare la soglia invece di contrassegnare questi tipi di posta elettronica inviata in massa come posta indesiderata. Le tolleranze e le preferenze relative alla gestione della [posta elettronica inviata in massa](https://docs.microsoft.com/it-IT/office365/SecurityCompliance/bulk-complaint-level-values) variano da utente a utente. È possibile creare regole o criteri diversi in base alle preferenze degli utenti. 
    
- **Bloccare immediatamente un mittente** Nel caso sia necessario bloccare immediatamente un mittente, è possibile bloccarlo tramite l'indirizzo di posta elettronica, il dominio o l'indirizzo IP. Vedere [Bloccare la posta indesiderata con il filtro protezione da posta indesiderata di Office 365 per evitare problemi di falsi negativi](block-email-spam-to-prevent-false-negatives.md). Una voce in un elenco di elementi attendibili dell'utente finale può sostituire un blocco impostato dall'amministratore.
    
- **Attivare il componente aggiuntivo Segnala messaggio per gli utenti** È consigliabile [attivare il componente aggiuntivo Segnala messaggio per gli utenti](enable-the-report-message-add-in.md). Un amministratore può anche visualizzare i commenti e suggerimenti inviati dagli utenti e utilizzare i modelli per modificare le impostazioni che potrebbero causare problemi.
    
### <a name="for-users"></a>Per gli utenti

- **Abilitare la regola della posta indesiderata e controllare l'elenco elementi attendibili** Verificare he la regola di azione della posta indesiderata sia attiva e che il mittente o il dominio del mittente non sia configurato per ignorare l'elenco di elementi attendibili personale. Il modo migliore per accedere a queste impostazioni è da [Blocca o consenti (impostazioni di posta indesiderata)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Qui, è anche possibile bloccare l'indirizzo di posta elettronica o il dominio del mittente.
    
- **Segnalare la posta indesiderata a Microsoft** Segnalare la posta indesiderata a Microsoft usando il [componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). È inoltre possibile inviare un messaggio all'indirizzo junk@office365.microsoft.com e allegare uno o più messaggi da segnalare.
    
    **Importante** Se non si inoltrano i messaggi come allegati, mancheranno le intestazioni e non potremo migliorare il filtro protezione da posta indesiderata di Office 365. 
    
- **Annullare l'iscrizione alla posta elettronica inviata in massa** Se il messaggio proviene da indirizzo alla quale ci si è iscritti (newsletter, prodotti e così via) e contiene un collegamento per annullare iscrizione di una fonte attendibile, è consigliabile semplicemente annullare l'iscrizione. Office 365 generalmente non gestisce questi messaggi come posta indesiderata. È anche possibile bloccare il mittente oppure rivolgersi all'amministratore per apportare una modifica affinché tutta la posta inviata in massa venga considerata posta indesiderata.
