---
title: Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: L'azione predefinita per la protezione da posta indesiderata per i clienti di EOP è quella di spostare i messaggi di posta indesiderata nella cartella dei destinatari. Affinché questa azione funzioni con le cassette postali locali, è necessario configurare le regole di trasporto di Exchange sui server perimetrali o hub locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Queste regole di trasporto consentono di impostare il livello di probabilità di posta indesiderata utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare la posta indesiderata in ogni cassetta postale.
ms.openlocfilehash: f712e66934956bcf46215e4016501003ce9b1725
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222885"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti

> [!IMPORTANT]
> Questo argomento si applica solo ai clienti di Exchange Online Protection (EOP) che ospitano le cassette postali in locale in una distribuzione ibrida. I clienti di Exchange Online le cui cassette postali sono completamente ospitate in Office 365 non devono eseguire questi comandi. 
  
L'azione predefinita per la protezione da posta indesiderata per i clienti di EOP è quella di spostare i messaggi di posta indesiderata nella cartella dei destinatari. Affinché questa azione funzioni con le cassette postali locali, è necessario configurare le regole di trasporto di Exchange sui server perimetrali o hub locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Queste regole di trasporto consentono di impostare il livello di probabilità di posta indesiderata utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare la posta indesiderata in ogni cassetta postale. 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Per aggiungere regole di trasporto per garantire che la posta indesiderata venga spostata nella cartella posta inDesiderata utilizzando Windows PowerShell

1. Accedere a Exchange Management Shell per il server Exchange locale. Per informazioni su come aprire Exchange Management Shell nell'organizzazione di Exchange locale, vedere **Open the Shell**.
    
2. Per instradare i messaggi di posta indesiderata filtrata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkContentFilteredMail. 
    
3. Per instradare i messaggi di posta indesiderata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailBeforeReachingContentFilter. 
    
4. Eseguire il seguente comando per verificare che i messaggi provenienti da mittenti contenuti in un elenco di blocco nel criterio di filtro della posta indesiderata, ad esempio l'elenco dei **Mittenti bloccati** , vengano instradati alla cartella posta indesiderata: 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailInSenderBlockList. 
    
Se non si desidera utilizzare l'azione **Sposta messaggio all'interno della cartella posta** indesiderata, è possibile scegliere un'altra azione nei criteri di filtro del contenuto nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata. Per ulteriori informazioni su questi campi nell'intestazione del messaggio, vedere [intestazioni dei messaggi](anti-spam-message-headers.md)di protezione da posta indesiderata.
  
## <a name="see-also"></a>Vedere anche

[Cmdlet New-TransportRule](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

