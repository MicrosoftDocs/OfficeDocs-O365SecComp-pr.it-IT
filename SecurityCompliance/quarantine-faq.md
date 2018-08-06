---
title: Domande frequenti sulla quarantena
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
description: In questo argomento vengono riportate le domande frequenti e le risposte sulla quarantena in hosting.
ms.openlocfilehash: 6aebeadc5155cbdb8cbeeb73e29c8b8cb0d53767
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027083"
---
# <a name="quarantine-faq"></a>Domande frequenti sulla quarantena

In questo argomento vengono riportate le domande frequenti e le risposte sulla quarantena in hosting. Le risposte sono applicabili a clienti Microsoft Exchange Online e Exchange Online Protection.
  
 **D. come è possibile gestire i messaggi in quarantena malware in quarantena?**
  
È necessario utilizzare la sicurezza &amp; centro conformità per poter visualizzare e gestire i messaggi che sono stati messi in quarantena in quanto contengono malware. Per ulteriori informazioni, vedere [i messaggi di posta elettronica quarantena in Office 365](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
 **D. Come configurare il servizio per inviare messaggi di posta indesiderata in quarantena?**
  
R. Per impostazione predefinita, i messaggi sottoposti a filtro contenuto vengono inviati alla cartella Posta indesiderata dei destinatari. Tuttavia, gli amministratori possono configurare i criteri del filtro contenuto per inviare invece i messaggi di posta indesiderata in quarantena. Per ulteriori informazioni sulle azioni che possono essere intraprese sui messaggi a contenuto filtrato, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).
  
 **D. Il servizio consente ad amministratori e utenti finali di gestire i messaggi di posta indesiderata messi in quarantena?**
  
R. Gli amministratori possono cercare i e visualizzare i dettagli sui messaggi di posta elettronica in quarantena nell'interfaccia di amministrazione di Exchange (EAC). Dopo aver individuato il messaggio, è possibile rilasciarlo a specifici utenti e segnalarlo come falso positivo (non indesiderato) al team di analisi di posta indesiderata di Microsoft. Per ulteriori informazioni, vedere [Individuazione e rilascio dei messaggi in quarantena come amministratore](find-and-release-quarantined-messages-as-an-administrator.md).
  
Gli utenti finali possono gestire i propri messaggi messi in quarantena tramite gli strumenti indicati di seguito: 
  
- Interfaccia utente per la quarantena della posta indesiderata. Per ulteriori informazioni, vedere [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).
        
 **D. Come è possibile garantire l'accesso alla quarantena della posta indesiderata per gli utenti finali?**
  
A. per poter accedere alla quarantena di posta indesiderata utente finale, utenti finali devono avere un ID utente di Office 365 valido e una password. I clienti EOP protezione cassette postali locali devono essere creati tramite la sincronizzazione delle directory o l'interfaccia di amministrazione di Exchange agli utenti di posta elettronica valido. Per ulteriori informazioni sulla gestione degli utenti, gli amministratori di EOP possono vedere [gestione di utenti di posta in EOP](eop/manage-mail-users-in-eop.md). Per i clienti autonomo EOP, si consiglia di sincronizzazione della directory e abilitazione della Directory Based Edge Blocking; Per ulteriori informazioni, vedere [Utilizzo Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).
  
 **D. Un elemento diverso dalla posta indesiderata può essere inviato in quarantena?**
  
R. Possono essere inviati alla quarantena dell'amministratore anche i messaggi che corrispondono a una regola di trasporto, se questa è l'azione configurata. La quarantena dell'utente finale è riservata esclusivamente alla posta indesiderata.
  
 **Q. Per quanto tempo i messaggi vengono tenuti in quarantena?**
  
R. Per impostazione predefinita, i messaggi in quarantena della posta indesiderata rimangono lì per 15 giorni, mentre i messaggi in quarantena a cui corrispondano regole di trasporto rimangono per 7 giorni. Dopo questo periodo di tempo i messaggi sono eliminati e non recuperabili. Il periodo di conservazione per i messaggi in quarantena a cui corrispondono regole di trasporto non è configurabile. Tuttavia, il periodo di conservazione può essere ridotto con l'impostazione **Conserva posta indesiderata per (giorni)** nei criteri di filtro contenuto. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).
  
 **D. È possibile rilasciare o segnalare più di un messaggio in quarantena alla volta?**
  
R. la possibilità di rilascio o il report contemporaneamente più messaggi non è attualmente disponibile in EAC o quarantena della posta indesiderata utente finale. Tuttavia, gli amministratori possono creare uno script di Windows PowerShell remoto per eseguire questa operazione. Utilizzare il cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) per cercare i messaggi e il cmdlet [Versione-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) per il rilascio di essi. 
  
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


