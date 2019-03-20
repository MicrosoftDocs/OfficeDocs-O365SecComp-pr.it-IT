---
title: Disattivare la segnalazione della posta indesiderata in Outlook sul Web
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: In qualità di amministratore di Office 365, è possibile disattivare la possibilità per gli utenti di segnalare la posta elettronica come indesiderata.
ms.openlocfilehash: f3e8a8cf837e7923d3c7241852ab2acd375492b8
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692555"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Disattivare la segnalazione della posta indesiderata in Outlook sul Web

È possibile inviare messaggi di posta indesiderata, di phishing e non a Microsoft per l'analisi utilizzando le opzioni di segnalazione della posta indesiderata di Outlook sul Web (in precedenza note come Outlook Web App), come descritto in [report posta indesiderata e truffe di phishing in Outlook sul Web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Se non si desidera utilizzare queste opzioni, gli amministratori possono disattivarli tramite il cmdlet [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) . 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Informazioni preliminari
<a name="sectionSection0"> </a>

- Tempo stimato per il completamento: 5 minuti
    
- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "criteri cassetta postale di Outlook sul Web" nell'argomento [autorizzazioni di Outlook sul Web](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) . 

- Per connettersi a PowerShell di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Disattiva la segnalazione di posta indesiderata, phishing e non di posta indesiderata a Microsoft
<a name="sectionSection1"> </a>

Prima di tutto, eseguire il seguente comando per ottenere i nomi dei criteri cassetta postale di Outlook sul Web disponibili:
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

Successivamente, utilizzare la seguente sintassi per abilitare o disabilitare la creazione di messaggi di posta indesiderata e non per la gestione delle cianfrusaglie a Microsoft in Outlook sul Web:
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

In questo esempio viene disattivata la creazione di report nel criterio cassetta postale di Outlook Web App predefinito:
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) e [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo
<a name="sectionSection2"> </a>

Eseguire **Get-OwaMailboxPolicy** per controllare i valori dei parametri e quindi aprire Outlook sul Web per un utente in cui è stato applicato il criterio cassetta postale di Outlook sul Web e verificare che le opzioni per segnalare la posta indesiderata, il phishing e non la posta indesiderata non siano disponibili. È comunque possibile contrassegnare i messaggi come posta indesiderata, phishing e non indesiderata, ma non sarà possibile segnalarli. 
