---
title: Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
description: L'azione di protezione da posta indesiderata predefinita per i clienti EOP consiste nello spostare messaggi di posta indesiderata nella cartella posta indesiderata per i destinatari. Affinché questa azione per l'utilizzo con cassette postali locali, è necessario configurare le regole di trasporto di Exchange sui server locali Hub o Edge per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Queste regole di trasporto impostare il livello di probabilità di posta indesiderata (SCL) viene utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare la posta indesiderata nella cartella posta indesiderata di ciascuna cassetta postale.
ms.openlocfilehash: 290a3cc6aed07cd4d91df65350fd49c9226a0d64
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026633"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti

> [!IMPORTANT]
> In questo argomento si applica solo ai clienti di Exchange Online Protection (EOP) che ospitano le cassette postali locali in una distribuzione ibrida. Utenti di Exchange Online le cui cassette postali sono completamente ospitato in Office 365 sono necessario eseguire questi comandi. 
  
L'azione di protezione da posta indesiderata predefinita per i clienti EOP consiste nello spostare messaggi di posta indesiderata nella cartella posta indesiderata per i destinatari. Affinché questa azione per l'utilizzo con cassette postali locali, è necessario configurare le regole di trasporto di Exchange sui server locali Hub o Edge per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Queste regole di trasporto impostare il livello di probabilità di posta indesiderata (SCL) viene utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare la posta indesiderata nella cartella posta indesiderata di ciascuna cassetta postale. 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Per aggiungere transport rules per garantire la posta indesiderata viene spostato nella cartella posta indesiderata tramite Windows PowerShell

1. Accedere a Exchange Management Shell per il server di Exchange locale. Per informazioni su come aprire Exchange Management Shell nell'organizzazione Exchange locale, vedere **aprire Shell**.
    
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
    
4. Eseguire il comando seguente per verificare che i messaggi da mittenti in un elenco di blocco nel criterio di filtro posta indesiderata, ad esempio l'elenco **Blocca mittente** , vengono instradati alla cartella posta indesiderata: 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailInSenderBlockList. 
    
Se non si desidera utilizzare l'azione **spostare il messaggio nella cartella posta indesiderata** , è possibile scegliere un'altra azione in Criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md). Per ulteriori informazioni su questi campi nell'intestazione del messaggio, vedere [anti-spam message headers](anti-spam-message-headers.md).
  
## <a name="see-also"></a>Vedere anche

[Cmdlet New-TransportRule](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

