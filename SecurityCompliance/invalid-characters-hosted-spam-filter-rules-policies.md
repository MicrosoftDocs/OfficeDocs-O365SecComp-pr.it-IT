---
title: Evitare di utilizzare caratteri non validi in regole del filtro posta indesiderata e il criterio di filtro posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Vengono fornite informazioni per gli amministratori che dispongono di caratteri non validi la configurazione di protezione da posta indesiderata e riscontrano problemi durante il tentativo di utilizzare la protezione &amp; centro conformità.
ms.openlocfilehash: ca409b4daa7bec01417adb7cbfdfa2a128929e81
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018735"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Evitare di utilizzare caratteri non validi in regole del filtro posta indesiderata e criterio di filtro della posta indesiderata 

In precedenza, gli amministratori di Office 365 impostato e configurato le regole di filtro posta indesiderata e il criterio di filtro posta indesiderata tramite l'interfaccia di amministrazione Exchange (EAC). È ora, utilizzare la sicurezza &amp; centro conformità per gestire la la configurazione di protezione da posta indesiderata. I caratteri seguenti sono supportati in EAC, ma non sono supportati per l'utilizzo della protezione &amp; centro conformità.  

**Caratteri non validi:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Se le regole di filtro posta indesiderata o i criteri di filtro posta indesiderata contiene uno dei caratteri non validi, potrebbero verificarsi uno o tutti questi problemi:
- Può risultare impossibile trovare il criterio o le regole per la protezione &amp; centro conformità.
- È possibile ricevere errori durante il tentativo di ottenere le regole o i criteri utilizzando Windows PowerShell.
- È possibile che le impostazioni o criteri di non eseguire o eseguire nel modo previsto.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>Rimuovere i caratteri non validi dal criterio di filtro posta indesiderata e regole

Dopo aver identificato i criteri e le regole contenenti caratteri non validi, è possibile modificare i nomi mediante i cmdlet di Windows PowerShell. 

1. [Connessione a Exchange Online tramite Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Per modificare il nome del criterio di filtro posta indesiderata, eseguire il cmdlet Set-HostedContentFilterPolicy come indicato di seguito:
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Per modificare il nome di una regola di filtro posta indesiderata, eseguire il cmdlet Set-HostedContentFilterRule come indicato di seguito:
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Ulteriori informazioni

[Gestione della protezione delle minacce &amp; centro conformità](threat-management.md)
  
[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
