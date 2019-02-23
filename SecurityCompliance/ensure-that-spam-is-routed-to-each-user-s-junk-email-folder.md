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
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="3bebf-105">Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti</span><span class="sxs-lookup"><span data-stu-id="3bebf-105">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bebf-p102">Questo argomento si applica solo ai clienti di Exchange Online Protection (EOP) che ospitano le cassette postali in locale in una distribuzione ibrida. I clienti di Exchange Online le cui cassette postali sono completamente ospitate in Office 365 non devono eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="3bebf-p102">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="3bebf-p103">L'azione predefinita per la protezione da posta indesiderata per i clienti di EOP è quella di spostare i messaggi di posta indesiderata nella cartella dei destinatari. Affinché questa azione funzioni con le cassette postali locali, è necessario configurare le regole di trasporto di Exchange sui server perimetrali o hub locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Queste regole di trasporto consentono di impostare il livello di probabilità di posta indesiderata utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare la posta indesiderata in ogni cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="3bebf-p103">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder. In order for this action to work with on-premises mailboxes, you must configure Exchange Transport rules on your on-premises Edge or Hub servers to detect spam headers added by EOP. These Transport rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="3bebf-111">Per aggiungere regole di trasporto per garantire che la posta indesiderata venga spostata nella cartella posta inDesiderata utilizzando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bebf-111">To add transport rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="3bebf-p104">Accedere a Exchange Management Shell per il server Exchange locale. Per informazioni su come aprire Exchange Management Shell nell'organizzazione di Exchange locale, vedere **Open the Shell**.</span><span class="sxs-lookup"><span data-stu-id="3bebf-p104">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="3bebf-114">Per instradare i messaggi di posta indesiderata filtrata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="3bebf-114">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="3bebf-115">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkContentFilteredMail.</span><span class="sxs-lookup"><span data-stu-id="3bebf-115">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="3bebf-116">Per instradare i messaggi di posta indesiderata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="3bebf-116">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="3bebf-117">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailBeforeReachingContentFilter.</span><span class="sxs-lookup"><span data-stu-id="3bebf-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="3bebf-118">Eseguire il seguente comando per verificare che i messaggi provenienti da mittenti contenuti in un elenco di blocco nel criterio di filtro della posta indesiderata, ad esempio l'elenco dei **Mittenti bloccati** , vengano instradati alla cartella posta indesiderata:</span><span class="sxs-lookup"><span data-stu-id="3bebf-118">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="3bebf-119">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailInSenderBlockList.</span><span class="sxs-lookup"><span data-stu-id="3bebf-119">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="3bebf-p105">Se non si desidera utilizzare l'azione **Sposta messaggio all'interno della cartella posta** indesiderata, è possibile scegliere un'altra azione nei criteri di filtro del contenuto nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata. Per ulteriori informazioni su questi campi nell'intestazione del messaggio, vedere [intestazioni dei messaggi](anti-spam-message-headers.md)di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="3bebf-p105">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3bebf-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bebf-123">See also</span></span>

[<span data-ttu-id="3bebf-124">Cmdlet New-TransportRule</span><span class="sxs-lookup"><span data-stu-id="3bebf-124">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

