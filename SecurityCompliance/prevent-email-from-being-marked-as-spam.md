---
title: Come evitare che i messaggi effettivi vengano contrassegnatati come indesiderati in Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: Informazioni su come evitare che i messaggi effettivi vengano contrassegnati come posta indesiderata in Office 365.
ms.openlocfilehash: 4da27aea157d3d816f8ce9a9631dd608dd5cd164
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614430"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>Come evitare che i messaggi effettivi vengano contrassegnatati come indesiderati in Office 365

 **I messaggi effettivi vengono contrassegnata come posta indesiderata in Office 365? Ecco cosa fare.**
  
Exchange Online Protection (EOP) tenta di filtrare la posta indesiderata, impedendo agli utenti di visualizzare nella Posta in arrivo contenuti non desiderati. Tuttavia, in alcuni casi, Exchange Online Protection filtra anche elementi che si desidera visualizzare.
  
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>Determinare il motivo per cui il messaggio è stato contrassegnato come posta indesiderata

Per risolvere molti problemi relativi alla posta indesiderata in Office 365, è possibile [visualizzare le intestazioni dei messaggi di posta elettronica](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) per determinare la causa del problema. L'intestazione da cercare è X-Forefront-Antispam-Report. Per altre informazioni sulle intestazioni dei messaggi della protezione da posta indesiderata, è possibile consultare [questo articolo](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).
  
Nell'intestazione cercare le intestazioni e i valori seguenti.
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:SPM**: indica che il messaggio è stato contrassegnato come posta indesiderata a causa dei filtri posta indesiderata EOP. 

- **SFV:BLK**: indica che il messaggio è stato contrassegnato come posta indesiderata perché l'indirizzo del mittente è incluso nell'elenco mittenti bloccati del destinatario. 
    
- **SFV:SKS**: indica che il messaggio è stato contrassegnato come posta indesiderata anteriormente al filtro del contenuto. Ad esempio una regola di trasporto ha segnato il messaggio come posta indesiderata. Eseguire una traccia dei messaggi per scoprire se è stata generata una regola di trasporto che ha impostato un elevato livello di probabilità di posta indesiderata (SCL). 
    
- **SFV:SKB**: indica che il messaggio è stato contrassegnato come posta indesiderata perché è stata trovata una corrispondenza con un elenco Blocca nei criteri di filtro posta indesiderata. 
    
- **SFV:BULK**: indica che il valore Livello di reclamo in blocco (BCL, Bulk Complaint Level) nell'intestazione x-Microsoft-Antispam è oltre la soglia impostata per il filtro dei contenuti. La posta elettronica in blocco è composta da messaggi di posta elettronica a cui gli utenti potrebbero essersi iscritti, ma che considerano comunque non desiderabili. Nell'intestazione del messaggio, individuare la proprietà BCL (Bulk Confidence Level) nell'intestazione X-Microsoft-Antispam. Se il valore BCL è inferiore alla soglia impostata nel filtro protezione da posta indesiderata, è consigliabile modificare la soglia invece di contrassegnare questi tipi di posta elettronica in blocco come posta indesiderata. Utenti diversi hanno diverse tolleranze e preferenze su come gestire la [posta elettronica in blocco](https://docs.microsoft.com/it-IT/office365/SecurityCompliance/bulk-complaint-level-values). È possibile creare regole o criteri diversi in base alle diverse preferenze degli utenti.
    
- **CAT:SPOOF** o **CAT:PHISH**: indica che il messaggio sembra essere falsificato, il che significa che la fonte del messaggio non può essere convalidata e potrebbe essere sospetta. Se è valido, il mittente dovrà assicurarsi di avere la corretta configurazione SPF e DKIM. Controllare l'intestazione Risultati di autenticazione per ulteriori informazioni. Sebbene possa essere difficile far sì che tutti i mittenti utilizzino i metodi di autenticazione email appropriati, ignorare questi controlli può essere estremamente pericoloso ed è la principale causa di compromissioni. 
    
### <a name="x-customspam"></a>x-customspam

- La presenza di questa intestazione indica che il messaggio è stato contrassegnato come posta indesiderata perché una delle [opzioni avanzate della posta indesiderata è abilitata](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) nel filtro della posta indesiderata. Se queste funzionalità non sono necessarie, è consigliabile usare le impostazioni predefinite. 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>Soluzioni per altri motivi di posta indesiderata in eccesso

Per funzionare correttamente, Exchange Online Protection (EOP) chiede agli amministratori di completare alcune operazioni. Se non si è un amministratore del proprio tenant di Office 365 e si riceve troppa posta indesiderata, eseguire tali operazioni con l'amministratore. In caso contrario, è possibile passare alla sezione per gli utenti.
  
### <a name="for-admins"></a>Per gli amministratori

- **Selezionare i record DNS di Office 365**. Per consentire a EOP di fornire protezione, i record DNS di Mail Exchanger (MX) per tutti i domini devono essere indirizzati a Office 365 e solo a Office 365. Se MX non punta a Office 365, EOP non può fornire filtri antispam per gli utenti. Se si desidera utilizzare un altro servizio o appliance per fornire filtri antispam al proprio dominio, prendere in considerazione la possibilità di disabilitare la protezione antispam in EOP. È possibile farlo creando una regola di trasporto che imposta il valore SCL su -1. Se in seguito si decide di utilizzare EOP, assicurarsi di rimuovere questa regola di trasporto. 
    
- **Disabilitare il filtro SmartScreen in Outlook**: se gli utenti utilizzano il client desktop Outlook, dovrebbero disabilitare la funzionalità di filtro SmartScreen, che è stata sospesa. Se abilitato, può causare falsi positivi. Questo non dovrebbe essere necessario se si esegue un client Outlook desktop aggiornato. 
    
- **Attivare il componente aggiuntivo Segnala messaggio per gli utenti**: è consigliabile [attivare il componente aggiuntivo Segnala messaggio per gli utenti](enable-the-report-message-add-in.md). Un amministratore può anche visualizzare i commenti e suggerimenti inviati dagli utenti e utilizzare i modelli per modificare le impostazioni che potrebbero causare problemi.
    
- **Consentire immediatamente un mittente**: nel caso in cui è necessario consentire immediatamente un mittente, è consigliabile che **consentire SOLO l'indirizzo IP di un mittente specifico**. In alternativa, è possibile consentire un mittente e assicurarsi che il mittente superi un controllo di autenticazione, ad esempio SPF o DKIM, creando una regola di trasporto che cerchi **sia** il dominio del mittente sia un'intestazione di risultati di autenticazione con esito positivo. 
    
### <a name="for-users"></a>Per gli utenti

- **Segnalare la posta indesiderata a Microsoft** Segnalare la posta indesiderata a Microsoft usando il [componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Inoltre, è possibile inviare un messaggio all'indirizzo junk@office365.microsoft.com e allegare uno o più messaggi da segnalare.
    
    **Importante** Se non si inoltrano i messaggi come allegati, mancheranno le intestazioni e non potremo migliorare il filtro protezione da posta indesiderata di Office 365. 
    
- **Aggiungere un mittente ai contatti autorizzati, ma con moderazione**: in alternativa, è possibile [bloccare o consentire (impostazioni di posta indesiderata)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Se si esegue questa operazione, si deve tenere presente che nella Posta in arrivo potrebbero essere consentiti tentativi di phishing mirati.
