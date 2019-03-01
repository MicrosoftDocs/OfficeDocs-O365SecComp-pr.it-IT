---
title: Configurazione di criteri di protezione da posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Il filtro posta inDesiderata viene automaticamente abilitato a livello aziendale tramite i criteri di protezione da posta indesiderata predefiniti (filtro connessioni, filtro posta indesiderata e posta indesiderata in uscita) In qualità di amministratore, è possibile visualizzare e modificare, ma non eliminare, i criteri di protezione da posta indesiderata predefiniti in modo che siano adatti per soddisfare al meglio le esigenze dell'organizzazione. Per una maggiore granularità, è anche possibile creare criteri personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione. Per impostazione predefinita, i criteri personalizzati hanno la precedenza sui criteri predefiniti, ma è possibile modificare la priorità dei criteri.
ms.openlocfilehash: 3e972a150b70f1081cb4c3b5e3672a3acba34785
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30340967"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="9dc0e-106">Configurazione di criteri di protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="9dc0e-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="9dc0e-p102">Il filtro posta inDesiderata viene automaticamente abilitato a livello aziendale tramite i criteri di protezione da posta indesiderata predefiniti (filtro connessioni, filtro posta indesiderata e posta indesiderata in uscita) In qualità di amministratore, è possibile visualizzare e modificare, ma non eliminare, i criteri di protezione da posta indesiderata predefiniti in modo che siano adatti per soddisfare al meglio le esigenze dell'organizzazione. Per una maggiore granularità, è anche possibile creare criteri personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione. Per impostazione predefinita, i criteri personalizzati hanno la precedenza sui criteri predefiniti, ma è possibile modificare la priorità dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9dc0e-p102">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam). As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization. For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization. By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="9dc0e-111">Per ulteriori informazioni sulla configurazione dei criteri di protezione da posta indesiderata, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9dc0e-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="9dc0e-112">Configurare i criteri di filtro delle connessioni</span><span class="sxs-lookup"><span data-stu-id="9dc0e-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="9dc0e-113">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="9dc0e-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="9dc0e-p103">Per i clienti autonomi di EOP: per impostazione predefinita, i filtri di contenuto EOP inviano messaggi di posta indesiderata alla cartella posta inDesiderata di ogni destinatario. Tuttavia, per assicurarsi che il **messaggio di spostamento all'azione della cartella posta** indesiderata funzionerà con le cassette postali locali, è necessario configurare due regole del flusso di posta di Exchange (note anche come regole di trasporto) sui server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere Verificare che la posta indesiderata [venga instradata alla cartella posta indesiderata di ogni utente](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="9dc0e-p103">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="9dc0e-117">Configurare i criteri della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="9dc0e-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

