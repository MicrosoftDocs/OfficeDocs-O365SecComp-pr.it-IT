---
title: Domande frequenti sulla quarantena
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: In questo argomento vengono riportate le domande frequenti e le risposte sulla quarantena in hosting.
ms.openlocfilehash: 9f9b16a92b8ef8105a9439972ebed54111b227c6
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341177"
---
# <a name="quarantine-faq"></a>Domande frequenti sulla quarantena

In questo argomento vengono riportate le domande frequenti e le risposte sulla quarantena in hosting. Le risposte sono applicabili a clienti Microsoft Exchange Online e Exchange Online Protection.
  
 **D. come è la gestione dei messaggi in quarantena per i malware?**
  
È necessario utilizzare il Centro sicurezza &amp; e conformità per visualizzare e gestire i messaggi inviati alla quarantena perché contengono malware. Per ulteriori informazioni, vedere [messaggi di posta elettronica in quarantena in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
 **D. Come configurare il servizio per inviare messaggi di posta indesiderata in quarantena?**
  
R. Per impostazione predefinita, i messaggi sottoposti a filtro contenuto vengono inviati alla cartella Posta indesiderata dei destinatari. Tuttavia, gli amministratori possono configurare i criteri del filtro contenuto per inviare invece i messaggi di posta indesiderata in quarantena. Per ulteriori informazioni sulle azioni che possono essere intraprese sui messaggi a contenuto filtrato, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).
  
 **D. Il servizio consente ad amministratori e utenti finali di gestire i messaggi di posta indesiderata messi in quarantena?**
  
R. Gli amministratori possono cercare i e visualizzare i dettagli sui messaggi di posta elettronica in quarantena nell'interfaccia di amministrazione di Exchange (EAC). Dopo aver individuato il messaggio, è possibile rilasciarlo a specifici utenti e segnalarlo come falso positivo (non indesiderato) al team di analisi di posta indesiderata di Microsoft. Per ulteriori informazioni, vedere [Individuazione e rilascio dei messaggi in quarantena come amministratore](find-and-release-quarantined-messages-as-an-administrator.md).
  
Gli utenti finali possono gestire i propri messaggi messi in quarantena tramite gli strumenti indicati di seguito: 
  
- Interfaccia utente per la quarantena della posta indesiderata. Per ulteriori informazioni, vedere [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).
        
 **D. Come è possibile garantire l'accesso alla quarantena della posta indesiderata per gli utenti finali?**
  
A. per accedere alla quarantena della posta indesiderata dell'utente finale, gli utenti finali devono disporre di un ID utente e una password di Office 365 validi. I clienti di EOP che proteggono le cassette postali locali devono essere utenti di posta elettronica validi creati tramite la sincronizzazione della directory o EAC. Per ulteriori informazioni sulla gestione degli utenti, gli amministratori di EOP possono fare riferimento per [gestire gli utenti di posta elettronica in EOP](eop/manage-mail-users-in-eop.md). Per i clienti autonomi di EOP, si consiglia di utilizzare la sincronizzazione della directory e di abilitare il blocco Edge basato su directory. Per ulteriori informazioni, vedere [use directory based Edge Blocking to Reject messages sent to invalid recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).
  
 **D. Un elemento diverso dalla posta indesiderata può essere inviato in quarantena?**
  
A. i messaggi che corrispondono a una regola del flusso di posta (nota anche come regola di trasporto) possono anche essere inviati alla quarantena dell'amministratore, se questa è l'azione configurata. La quarantena dell'utente finale è solo per la posta indesiderata.
  
 **Q. Per quanto tempo i messaggi vengono tenuti in quarantena?**
  
A. per impostazione predefinita, i messaggi in quarantena della posta indesiderata vengono mantenuti in quarantena per 30 giorni, mentre i messaggi in quarantena che corrispondono a una regola del flusso di posta vengono mantenuti in quarantena per 7 giorni. Dopo questo periodo di tempo, i messaggi vengono eliminati e non possono essere recuperati. Il periodo di conservazione per i messaggi in quarantena che corrispondono a una regola del flusso di posta elettronica non è configurabile. Tuttavia, il periodo di conservazione per i messaggi in quarantena della posta indesiderata può essere ridotto tramite l'impostazione **Mantieni posta indesiderata per (giorni)** nei criteri di filtro del contenuto. Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata.
  
 **D. È possibile rilasciare o segnalare più di un messaggio in quarantena alla volta?**
  
A. la possibilità di rilasciare o segnalare più messaggi contemporaneamente non è attualmente disponibile nell'interfaccia di amministrazione di Exchange o nella quarantena della posta indesiderata dell'utente finale. Tuttavia, gli amministratori possono creare uno script di Windows PowerShell remoto per eseguire questa attività. Utilizzare il cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) per cercare i messaggi e il cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) per rilasciarli. 
  
 **D. Sono supportati i caratteri jolly nella ricerca dei messaggi in quarantena? Posso cercare i messaggi in quarantena in base a un dominio specifico?**
  
R. I caratteri jolly non sono supportati quando si specificano i criteri di ricerca nell'interfaccia di amministrazione di Exchange. Ad esempio, quando si cerca un mittente, è necessario specificare l'indirizzo di posta elettronica completo.
  
Utilizzando Windows PowerShell remoto, gli amministratori possono specificare il cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) per cercare i messaggi in quarantena per un dominio specifico (ad esempio contoso.com): 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

I risultati possono essere passati al cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx). Includere il parametro -ReleaseToAll per rilasciare il messaggio a tutti i destinatari. Una volta che il messaggio viene rilasciato, non può essere rilasciato nuovamente. 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


