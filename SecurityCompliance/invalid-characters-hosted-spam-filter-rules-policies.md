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
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="751e0-103">Evitare di utilizzare caratteri non validi in regole del filtro posta indesiderata e criterio di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="751e0-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="751e0-p101">In precedenza, gli amministratori di Office 365 impostato e configurato le regole di filtro posta indesiderata e il criterio di filtro posta indesiderata tramite l'interfaccia di amministrazione Exchange (EAC). È ora, utilizzare la sicurezza &amp; centro conformità per gestire la la configurazione di protezione da posta indesiderata. I caratteri seguenti sono supportati in EAC, ma non sono supportati per l'utilizzo della protezione &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="751e0-p101">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange Admin Center (EAC). Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration. The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="751e0-107">**Caratteri non validi:**</span><span class="sxs-lookup"><span data-stu-id="751e0-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="751e0-108">Se le regole di filtro posta indesiderata o i criteri di filtro posta indesiderata contiene uno dei caratteri non validi, potrebbero verificarsi uno o tutti questi problemi:</span><span class="sxs-lookup"><span data-stu-id="751e0-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="751e0-109">Può risultare impossibile trovare il criterio o le regole per la protezione &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="751e0-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="751e0-110">È possibile ricevere errori durante il tentativo di ottenere le regole o i criteri utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="751e0-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="751e0-111">È possibile che le impostazioni o criteri di non eseguire o eseguire nel modo previsto.</span><span class="sxs-lookup"><span data-stu-id="751e0-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="751e0-112">Rimuovere i caratteri non validi dal criterio di filtro posta indesiderata e regole</span><span class="sxs-lookup"><span data-stu-id="751e0-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="751e0-113">Dopo aver identificato i criteri e le regole contenenti caratteri non validi, è possibile modificare i nomi mediante i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="751e0-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="751e0-114">[Connessione a Exchange Online tramite Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="751e0-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="751e0-115">Per modificare il nome del criterio di filtro posta indesiderata, eseguire il cmdlet Set-HostedContentFilterPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="751e0-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="751e0-116">Per modificare il nome di una regola di filtro posta indesiderata, eseguire il cmdlet Set-HostedContentFilterRule come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="751e0-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="751e0-117">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="751e0-117">For more information</span></span>

[<span data-ttu-id="751e0-118">Gestione della protezione delle minacce &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="751e0-118">Threat management in the Security &amp; Compliance Center</span></span>](threat-management.md)
  
[<span data-ttu-id="751e0-119">Set-HostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="751e0-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="751e0-120">Set-HostedContentFilterRule</span><span class="sxs-lookup"><span data-stu-id="751e0-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
