---
title: Disattivare la posta indesiderata in Outlook sul web reporting
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
description: L'amministratore di Office 365, è possibile disattivare la possibilità per gli utenti per la posta elettronica report come posta indesiderata.
ms.openlocfilehash: 8ee5ff87408b80c443e4cf950ce49f624096becb
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272041"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Disattivare la posta indesiderata in Outlook sul web reporting

È possibile inviare posta indesiderata e phishing messaggi di posta non indesiderata a Microsoft per l'analisi tramite Outlook sulla posta indesiderata web reporting opzioni, come descritto in [posta indesiderata di Report e i tentativi di phishing in Outlook sul web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Se non si desidera utilizzare queste opzioni, gli amministratori possono essere disattivati mediante il cmdlet [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) . 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

- Tempo stimato per il completamento: 5 minuti
    
- È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Criteri cassetta postale di Outlook Web App" nell'argomento [autorizzazioni di Outlook Web App](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) . 
    
- Prima di eseguire i cmdlet necessari per disattivare la segnalazione della posta indesiderata, potrebbe essere utile esaminare le informazioni di riferimento negli argomenti [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) e [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) . 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Disattivare la posta indesiderato, phishing, posta indesiderata e non segnalazione a Microsoft
<a name="sectionSection1"> </a>

Innanzitutto, eseguire il seguente cmdlet per ottenere le directory virtuali per le quali si desidera disattivare la segnalazione:
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

Successivamente, eseguire il seguente cmdlet per disattivare la segnalazione della posta indesiderata e non in Microsoft:
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

Ad esempio, il seguente cmdlet consente di disattivare la segnalazione per la directory virtuale Contoso\owa:
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo
<a name="sectionSection2"> </a>

Eseguire Get-OWAMailboxPolicy per i valori dei parametri di controllo e quindi accedere a Outlook sul web e verificare che le opzioni per segnalare posta indesiderata, phishing, posta indesiderata e non si è disponibili. Sarà comunque possibile contrassegnare i messaggi di posta indesiderata, phishing, posta indesiderata e non, ma non sarà in grado di segnalarli. 
  

