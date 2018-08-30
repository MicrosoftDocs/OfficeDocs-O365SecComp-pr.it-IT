---
title: Funzionamento di DLP tra la sicurezza &amp; centro conformità e l'interfaccia di amministrazione di Exchange
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Informazioni su come DLP nella protezione &amp; centro conformità può essere utilizzato con le regole di trasporto e DLP nell'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531077"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="9ea2d-103">Funzionamento di DLP tra la sicurezza &amp; centro conformità e l'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="9ea2d-103">How DLP works between the Security &amp; Compliance Center and Exchange Admin Center</span></span>

<span data-ttu-id="9ea2d-104">In Office 365, è possibile creare un criterio di criterio DLP perdita di dati in due diversi admin Center:</span><span class="sxs-lookup"><span data-stu-id="9ea2d-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="9ea2d-p101">Nella **protezione &amp; centro conformità**, è possibile creare un singolo criterio DLP per proteggere il contenuto di SharePoint, OneDrive ed Exchange. Se possibile, è consigliabile creare un criterio DLP. Per ulteriori informazioni, vedere [DLP nella protezione &amp; centro conformità](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9ea2d-p101">In the **Security &amp; Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security &amp; Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="9ea2d-p102">Nell' **Interfaccia di amministrazione di Exchange**, è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange. Questo criterio è possibile utilizzare le regole di trasporto di Exchange, quindi presenta altre opzioni specifiche per la gestione di posta elettronica. Per ulteriori informazioni, vedere [DLP nell'interfaccia di amministrazione di Exchange](https://go.microsoft.com/fwlink/?linkid=852311).</span><span class="sxs-lookup"><span data-stu-id="9ea2d-p102">In the **Exchange Admin Center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange transport rules, so it has more options specific to handling email. For more information, see [DLP in the Exchange Admin Center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="9ea2d-111">Criteri DLP creati in queste admin Center utilizzare affiancato - questo argomento viene illustrato come.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Pagine DLP in sicurezza e centro conformità e l'interfaccia di amministrazione di Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a><span data-ttu-id="9ea2d-113">Come DLP nella protezione &amp; centro conformità può essere utilizzato con le regole di trasporto e DLP nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="9ea2d-113">How DLP in the Security &amp; Compliance Center works with DLP and transport rules in the Exchange Admin Center</span></span>

<span data-ttu-id="9ea2d-p103">Dopo aver creato un criterio DLP per la protezione &amp; centro conformità, il criterio viene distribuito a tutti i percorsi inclusi nel criterio. Se il criterio include Exchange Online, i criteri sono sincronizzati e applicate in esattamente a un criterio DLP creato nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-p103">After you create a DLP policy in the Security &amp; Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="9ea2d-p104">Se sono state create criteri DLP nell'interfaccia di amministrazione di Exchange, i criteri continuerà a funzionare Affianca tutti i criteri per la posta elettronica creati in sicurezza &amp; centro conformità. Tuttavia, tenere presente che le regole create nell'interfaccia di amministrazione di Exchange hanno la precedenza. Tutte le regole di trasporto di Exchange vengono elaborate prima e quindi il DLP le regole di protezione del &amp; vengono elaborate centro conformità.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security &amp; Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange transport rules are processed first, and then the DLP rules from the Security &amp; Compliance Center are processed.</span></span>
  
<span data-ttu-id="9ea2d-119">Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="9ea2d-119">This means that:</span></span>
  
- <span data-ttu-id="9ea2d-120">I messaggi che vengono bloccati dalle regole di trasporto di Exchange non ottenere analizzati dalle regole DLP create in sicurezza &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-120">Messages that are blocked by Exchange transport rules won't get scanned by DLP rules created in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="9ea2d-121">Se una regola di trasporto di Exchange consente di modificare un messaggio in modo che ne determina la corrispondenza di un criterio DLP per la protezione &amp; centro conformità, ad esempio l'aggiunta di utenti esterni - quindi regole DLP rileva questo e applicare i criteri in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-121">If an Exchange transport rule modifies a message in a way that causes it to match a DLP policy in the Security &amp; Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="9ea2d-122">Anche le regole di nota che le regole di trasporto di Exchange che utilizzano l'azione "arrestare l'elaborazione" non influisce sull'esecuzione di DLP nella protezione &amp; centro conformità - verranno comunque elaborate.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-122">Also note that Exchange transport rules that use the "stop processing" action don't affect the processing of DLP rules in the Security &amp; Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="9ea2d-123">Criteri di suggerimenti per la sicurezza &amp; centro conformità e l'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="9ea2d-123">Policy tips in the Security &amp; Compliance Center vs. the Exchange Admin Center</span></span>

<span data-ttu-id="9ea2d-p105">Suggerimenti per i criteri possono lavorare con i criteri DLP e create nell'interfaccia di amministrazione di Exchange o con i criteri DLP creati in sicurezza le regole di flusso di posta &amp; centro conformità, ma non entrambi. Ciò avviene perché questi criteri vengono archiviati in percorsi diversi, ma solo da un'unica posizione possa disegnare suggerimenti sui criteri.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="9ea2d-p106">Se è stato configurato suggerimenti sui criteri nell'interfaccia di amministrazione di Exchange, eventuali suggerimenti sui criteri che consentono di configurare la protezione &amp; centro conformità non viene visualizzato agli utenti in Outlook sul web e Outlook 2013 e versioni successive fino a quando non si disattiva i suggerimenti nell'interfaccia di amministrazione di Exchange. In questo modo che le regole di trasporto di Exchange corrente continuerà a funzionare fino a quando non è possibile passare a sicurezza &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-p106">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="9ea2d-128">Si noti che le notifiche di posta elettronica mentre suggerimenti sui criteri possa disegnare solo da un'unica posizione, sempre inviato, anche se si utilizza criteri DLP in entrambi i Security &amp; centro conformità e l'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="9ea2d-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  

