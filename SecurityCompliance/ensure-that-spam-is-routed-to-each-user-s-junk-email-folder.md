---
title: Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a instradare la posta indesiderata alle cartelle di posta indesiderata degli utenti in Exchange Online Protection.
ms.openlocfilehash: 390ba26167521ccea7b69e7fac21924c0b9ec7de
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153213"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="8babe-103">Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti</span><span class="sxs-lookup"><span data-stu-id="8babe-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8babe-104">Questo argomento si applica solo ai clienti di Exchange Online Protection (EOP) che ospitano le cassette postali in locale in una distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="8babe-104">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment.</span></span> <span data-ttu-id="8babe-105">I clienti di Exchange Online le cui cassette postali sono completamente ospitate in Office 365 non devono eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="8babe-105">Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="8babe-106">L'azione di protezione da posta indesiderata predefinita per i clienti EOP consiste nello spostamento dei messaggi di posta indesiderata nella cartella Posta indesiderata dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="8babe-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="8babe-107">Affinché questa azione funzioni con le cassette postali locali, è necessario configurare le regole del flusso di posta di Exchange (note anche come regole di trasporto) sui server perimetrali o hub locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP.</span><span class="sxs-lookup"><span data-stu-id="8babe-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="8babe-108">Queste regole del flusso di posta consentono di impostare il livello di probabilità di protezione da posta indesiderata utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare lo spam nella cartella posta indesiderata di ogni cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="8babe-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="8babe-109">Per aggiungere regole del flusso di posta per garantire che la posta indesiderata venga spostata nella cartella posta indesiderata utilizzando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8babe-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="8babe-110">Accedere a Exchange Management Shell per il server Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="8babe-110">Access the Exchange Management Shell for your on-premises Exchange server.</span></span> <span data-ttu-id="8babe-111">Per sapere come aprire Exchange Management Shell nell'organizzazione Exchange locale, vedere **Open the Shell**.</span><span class="sxs-lookup"><span data-stu-id="8babe-111">To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="8babe-112">Per instradare i messaggi di posta indesiderata filtrata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="8babe-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="8babe-113">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkContentFilteredMail.</span><span class="sxs-lookup"><span data-stu-id="8babe-113">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="8babe-114">Per instradare i messaggi di posta indesiderata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="8babe-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="8babe-115">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailBeforeReachingContentFilter.</span><span class="sxs-lookup"><span data-stu-id="8babe-115">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="8babe-116">Eseguire il seguente comando per verificare che i messaggi provenienti da mittenti contenuti in un elenco di blocco nel criterio di filtro della posta indesiderata, ad esempio l'elenco dei **Mittenti bloccati** , vengano instradati alla cartella posta indesiderata:</span><span class="sxs-lookup"><span data-stu-id="8babe-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="8babe-117">Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailInSenderBlockList.</span><span class="sxs-lookup"><span data-stu-id="8babe-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="8babe-118">Se non si desidera utilizzare l'azione **Sposta messaggio all'interno della cartella posta** indesiderata, è possibile scegliere un'altra azione nei criteri di filtro del contenuto nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="8babe-118">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="8babe-119">Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8babe-119">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="8babe-120">Per ulteriori informazioni su questi campi nell'intestazione del messaggio, vedere [intestazioni dei messaggi](anti-spam-message-headers.md)di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8babe-120">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  

> [!TIP]
> <span data-ttu-id="8babe-121">Se non si desidera utilizzare l'azione **Sposta messaggio all'interno della cartella posta** indesiderata, è possibile scegliere un'altra azione nei criteri di filtro del contenuto nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="8babe-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="8babe-122">Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8babe-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="8babe-123">Per ulteriori informazioni su questi campi nell'intestazione del messaggio, vedere [intestazioni dei messaggi](anti-spam-message-headers.md)di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8babe-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
> 
## <a name="see-also"></a><span data-ttu-id="8babe-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8babe-124">See also</span></span>

[<span data-ttu-id="8babe-125">Cmdlet New-TransportRule</span><span class="sxs-lookup"><span data-stu-id="8babe-125">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

