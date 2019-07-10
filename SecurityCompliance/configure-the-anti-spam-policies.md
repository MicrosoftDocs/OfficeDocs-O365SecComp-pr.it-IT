---
title: Configurazione di criteri di protezione da posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Il filtro posta indesiderata viene automaticamente abilitato a livello aziendale tramite i criteri di protezione da posta indesiderata predefiniti (filtro connessioni, filtro posta indesiderata e posta indesiderata in uscita) L'amministratore può visualizzare e modificare, ma non eliminare, i criteri di protezione da posta indesiderata predefiniti espressamente concepiti per soddisfare nel modo migliore le esigenze dell'organizzazione. Per una maggiore granularità, è anche possibile creare criteri personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione. Per impostazione predefinita, i criteri personalizzati hanno sempre la precedenza sui criteri predefiniti, ma non è possibile modificarne la priorità.
ms.openlocfilehash: f6690ddf0f50762aaa7b9ff61385c279f66716c8
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600112"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="e99e5-106">Configurare i criteri di protezione dalla posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="e99e5-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="e99e5-107">Il filtro posta indesiderata viene automaticamente abilitato a livello aziendale tramite i criteri di protezione da posta indesiderata predefiniti (filtro connessioni, filtro posta indesiderata e posta indesiderata in uscita)</span><span class="sxs-lookup"><span data-stu-id="e99e5-107">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam).</span></span> <span data-ttu-id="e99e5-108">L'amministratore può visualizzare e modificare, ma non eliminare, i criteri di protezione da posta indesiderata predefiniti espressamente concepiti per soddisfare nel modo migliore le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e99e5-108">As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization.</span></span> <span data-ttu-id="e99e5-109">Per una maggiore granularità, è anche possibile creare criteri personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e99e5-109">For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization.</span></span> <span data-ttu-id="e99e5-110">Per impostazione predefinita, i criteri personalizzati hanno sempre la precedenza sui criteri predefiniti, ma non è possibile modificarne la priorità.</span><span class="sxs-lookup"><span data-stu-id="e99e5-110">By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="e99e5-111">Per ulteriori informazioni sulla configurazione dei criteri di protezione da posta indesiderata, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="e99e5-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="e99e5-112">Configurare i criteri di filtro delle connessioni</span><span class="sxs-lookup"><span data-stu-id="e99e5-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="e99e5-113">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="e99e5-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="e99e5-114">Per i clienti EOP indipendenti: per impostazione predefinita, i filtri di contenuto EOP inviano messaggi rilevati dalla posta indesiderata alla cartella Posta indesiderata di ciascun destinatario.</span><span class="sxs-lookup"><span data-stu-id="e99e5-114">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder.</span></span> <span data-ttu-id="e99e5-115">Tuttavia, per assicurarsi che il **messaggio di spostamento all'azione della cartella posta** indesiderata funzionerà con le cassette postali locali, è necessario configurare due regole del flusso di posta di Exchange (note anche come regole di trasporto) sui server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP.</span><span class="sxs-lookup"><span data-stu-id="e99e5-115">However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="e99e5-116">Per ulteriori informazioni, vedere [Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="e99e5-116">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="e99e5-117">Configurare i criteri della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="e99e5-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

