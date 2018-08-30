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
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
description: L'azione di protezione da posta indesiderata predefinita per i clienti EOP consiste nello spostare messaggi di posta indesiderata nella cartella posta indesiderata per i destinatari. Affinché questa azione per l'utilizzo con cassette postali locali, è necessario configurare le regole di trasporto di Exchange sui server locali Hub o Edge per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Queste regole di trasporto impostare il livello di probabilità di posta indesiderata (SCL) viene utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare la posta indesiderata nella cartella posta indesiderata di ciascuna cassetta postale.
ms.openlocfilehash: 1b0a9e5ee39820baade714612ca0b0bdb7a81bb9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002855"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="6ee0d-105">Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti</span><span class="sxs-lookup"><span data-stu-id="6ee0d-105">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ee0d-p102">In questo argomento si applica solo ai clienti di Exchange Online Protection (EOP) che ospitano le cassette postali locali in una distribuzione ibrida. Utenti di Exchange Online le cui cassette postali sono completamente ospitato in Office 365 sono necessario eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="6ee0d-p102">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="6ee0d-p103">L'azione di protezione da posta indesiderata predefinita per i clienti EOP consiste nello spostare messaggi di posta indesiderata nella cartella posta indesiderata per i destinatari. Affinché questa azione per l'utilizzo con cassette postali locali, è necessario configurare le regole di trasporto di Exchange sui server locali Hub o Edge per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Queste regole di trasporto impostare il livello di probabilità di posta indesiderata (SCL) viene utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare la posta indesiderata nella cartella posta indesiderata di ciascuna cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="6ee0d-p103">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder. In order for this action to work with on-premises mailboxes, you must configure Exchange Transport rules on your on-premises Edge or Hub servers to detect spam headers added by EOP. These Transport rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="6ee0d-111">Per aggiungere transport rules per garantire la posta indesiderata viene spostato nella cartella posta indesiderata tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ee0d-111">To add transport rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="6ee0d-p104">Accedere a Exchange Management Shell per il server di Exchange locale. Per informazioni su come aprire Exchange Management Shell nell'organizzazione Exchange locale, vedere **aprire Shell**.</span><span class="sxs-lookup"><span data-stu-id="6ee0d-p104">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="6ee0d-114">Per instradare i messaggi di posta indesiderata filtrata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="6ee0d-114">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="6ee0d-115">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkContentFilteredMail.</span><span class="sxs-lookup"><span data-stu-id="6ee0d-115">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="6ee0d-116">Per instradare i messaggi di posta indesiderata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="6ee0d-116">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="6ee0d-117">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailBeforeReachingContentFilter.</span><span class="sxs-lookup"><span data-stu-id="6ee0d-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="6ee0d-118">Eseguire il comando seguente per verificare che i messaggi da mittenti in un elenco di blocco nel criterio di filtro posta indesiderata, ad esempio l'elenco **Blocca mittente** , vengono instradati alla cartella posta indesiderata:</span><span class="sxs-lookup"><span data-stu-id="6ee0d-118">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="6ee0d-119">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailInSenderBlockList.</span><span class="sxs-lookup"><span data-stu-id="6ee0d-119">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="6ee0d-p105">Se non si desidera utilizzare l'azione **spostare il messaggio nella cartella posta indesiderata** , è possibile scegliere un'altra azione in Criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md). Per ulteriori informazioni su questi campi nell'intestazione del messaggio, vedere [anti-spam message headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="6ee0d-p105">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6ee0d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ee0d-123">See also</span></span>

[<span data-ttu-id="6ee0d-124">Cmdlet New-TransportRule</span><span class="sxs-lookup"><span data-stu-id="6ee0d-124">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

