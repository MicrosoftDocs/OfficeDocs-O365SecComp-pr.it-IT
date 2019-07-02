---
title: Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Threat Investigation and Response
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Informazioni su come utilizzare le funzionalità di analisi e risposta alle minacce per individuare e studiare messaggi di posta elettronica dannosi.
ms.openlocfilehash: febcf6704b1ba9dc23bf4e698715fb4b929b998b
ms.sourcegitcommit: d3b2bffa8af5f19d97fe9771068c80705b890e85
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "35414806"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a>Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Advanced Threat Protection Plan 2)

[Office 365 Advanced Threat Protection](office-365-atp.md) consente di esaminare le attività che consentono agli utenti di eseguire operazioni per proteggere l'organizzazione. Ad esempio, se si fa parte del team di sicurezza dell'organizzazione, è possibile trovare e analizzare i messaggi di posta elettronica sospetti che sono stati recapitati agli utenti. A tale scopo, è possibile utilizzare [Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Prima di iniziare...

Verificare che vengano soddisfatti i seguenti requisiti:
  
- L'organizzazione dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) (piano 1 o piano 2) e le [licenze vengono assegnate agli utenti](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- La [registrazione di controllo di Office 365](turn-audit-log-search-on-or-off.md) è attivata per l'organizzazione. 
    
- L'organizzazione dispone di criteri definiti per la protezione da posta indesiderata, anti-malware, anti-phishing e così via. Vedere [protezione dalle minacce in Office 365](protect-against-threats.md).
    
- Si è un amministratore globale di Office 365 oppure è stato assegnato l'amministratore della sicurezza o il ruolo di ricerca ed eliminazione nel centro sicurezza &amp; e conformità. Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
    
## <a name="dealing-with-suspicious-emails"></a>Gestione di messaggi di posta elettronica sospetti

Gli utenti malintenzionati possono inviare messaggi ai propri clienti per cercare di phishing le proprie credenziali e accedere ai segreti aziendali. Per evitare questo, è consigliabile utilizzare i servizi di protezione dalle minacce in Office 365, tra cui [Exchange Online Protection](eop/exchange-online-protection-overview.md) e [Advanced Threat Protection](office-365-atp.md). Tuttavia, è possibile che un utente malintenzionato invii messaggi di posta elettronica agli utenti che contengono un URL e solo in seguito fare in modo che l'URL punti a contenuto dannoso (malware e così via). In alternativa, si potrebbe rendersi conto che un utente dell'organizzazione è stato compromesso e che l'utente è stato compromesso, un aggressore ha utilizzato quell'account per inviare messaggi di posta elettronica ad altri utenti della propria azienda. Durante la pulizia di entrambi gli scenari, potrebbe essere necessario rimuovere i messaggi di posta elettronica dalle cassette postali degli utenti. In situazioni come queste, è possibile sfruttare le [minacce Explorer (o rilevamenti in tempo reale)](threat-explorer.md) per individuare e rimuovere tali messaggi di posta elettronica.

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a>Dove si trovano i messaggi di posta elettronica reindirizzati dopo aver eseguito le operazioni

I rilevamenti in tempo reale di Esplora minacce sono stati aggiunti i campi azione di recapito e posizione di recapito nel luogo dello stato del recapito. Questo comporta un'immagine più completa della posizione dei messaggi di posta elettronica. Parte dell'obiettivo di questa modifica è facilitare la ricerca per gli addetti alle operazioni di sicurezza, ma il risultato finale è la conoscenza del percorso dei messaggi di posta elettronica problematici.

Lo stato di recapito è ora suddiviso in due colonne:

- **Azione** di recapito-qual è lo stato di questo messaggio di posta elettronica?
- **Percorso** di recapito-dove è stato instradato il messaggio di posta elettronica come risultato?

Azione di recapito è l'azione intrapresa su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le possibili azioni che un messaggio di posta elettronica può eseguire:

1. **** Recapitato: la posta elettronica è stata recapitata alla posta in arrivo o alla cartella di un utente e l'utente può accedervi direttamente.
2. **Junked** – la posta elettronica è stata inviata alla cartella posta indesiderata o alla cartella eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica nella cartella posta indesiderata o eliminata.
3. **Bloccato** : tutti i messaggi di posta elettronica in quarantena, che non sono riusciti o sono stati eliminati. Questo è completamente inaccessibile dall'utente.
4. **Sostituito** – qualsiasi messaggio di posta elettronica in cui gli allegati dannosi sono stati sostituiti dai file. txt che affermano che l'allegato è dannoso
 
Il percorso di recapito consente di visualizzare i risultati dei criteri e i rilevamenti eseguiti dopo il recapito. È collegato a un'azione di recapito. Questo campo è stato aggiunto per fornire informazioni dettagliate sull'azione intrapresa quando viene trovata una posta elettronica problematica. Di seguito sono riportati i possibili valori del percorso di recapito:

1. **Posta in arrivo o cartella** – la posta elettronica è in posta in arrivo o in una cartella (in base alle regole di posta elettronica).
2. **On-Prem o External** -la cassetta postale non esiste sul cloud ma è in locale.
3. **Cartella** posta indesiderata: l'indirizzo di posta elettronica nella cartella posta indesiderata di un utente.
4. **Cartella** posta eliminata: il messaggio nella cartella elementi eliminati di un utente.
5. **Quarantine** : l'indirizzo di posta elettronica in quarantena e non è incluso nella cassetta postale di un utente.
6. **Failed** : la posta elettronica non è riuscita a raggiungere la cassetta postale.
7. **Eliminato** : il messaggio di posta elettronica viene perso da qualche parte nel flusso.
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Individuare ed eliminare messaggi di posta elettronica sospetti recapitati

> [!TIP]
> Esplora minacce (a volte denominato Esplora) è un report potente che può servire a più scopi, ad esempio la ricerca e l'eliminazione dei messaggi, l'identificazione dell'indirizzo IP di un mittente di posta elettronica dannoso o l'avvio di un incidente per ulteriori indagini. La procedura seguente si concentra sull'utilizzo di Esplora risorse per individuare ed eliminare messaggi di posta elettronica dannosi dalle cassette postali dei destinatari.

Per visualizzare le modifiche apportate al precedente campo stato di recapito (ora operazione di recapito e posizione di recapito): 

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Nel riquadro di spostamento a sinistra, scegliere **gestione** \> **** minacce.
<!--Comment>
![Threat Explorer with Delivery Action and Delivery Location fields.](media/ThreatExFields.PNG)

    
3. In the View menu, choose **All email**.<br/>![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.<br/>![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only emails that ended up in users' inboxes.<br/>![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.<br/>![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.<br/>![You can view additional information about an item, including details and any attachments](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.<br/>![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
-->
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection piano 2](office-365-ti.md)
  
[Protezione dalle minacce in Office 365](protect-against-threats.md)
  
[Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
  

