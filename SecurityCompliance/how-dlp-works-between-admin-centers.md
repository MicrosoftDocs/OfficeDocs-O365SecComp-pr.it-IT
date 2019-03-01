---
title: Funzionamento di DLP tra il Centro sicurezza & compliance e l'interfaccia di amministrazione di Exchange
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Informazioni su come DLP nel centro sicurezza & Compliance funziona con le regole del flusso di posta e DLP (regole di trasporto) nell'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: c20cf5d4e7b83a726b104a57b89f2d8f765d7f16
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341487"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="7f3aa-103">Funzionamento di DLP tra il Centro sicurezza & compliance e l'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="7f3aa-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="7f3aa-104">In Office 365, è possibile creare un criterio di prevenzione della perdita di dati (DLP) in due diversi centri di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="7f3aa-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="7f3aa-p101">Nel **Centro sicurezza _AMP_ Compliance**, è possibile creare un singolo criterio DLP per proteggere il contenuto in SharePoint, OneDrive ed Exchange. Quando possibile, si consiglia di creare un criterio DLP. Per ulteriori informazioni, vedere [DLP in the Security _AMP_ Compliance Center](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7f3aa-p101">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="7f3aa-p102">Nell'interfaccia di **amministrazione di Exchange**, è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange. Questo criterio è in grado di utilizzare le regole del flusso di posta di Exchange (note anche come regole di trasporto), quindi dispone di più opzioni specifiche per la gestione della posta elettronica. Per ulteriori informazioni, vedere [DLP nell'](https://go.microsoft.com/fwlink/?linkid=852311)interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-p102">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email. For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="7f3aa-111">I criteri DLP creati in questi interfaccia di amministrazione sono affiancati-in questo argomento viene descritto come fare.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Pagine DLP in centro sicurezza e conformità e interfaccia di amministrazione di Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="7f3aa-113">Come DLP nel centro sicurezza e conformità di & funziona con le regole del flusso di posta e DLP nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="7f3aa-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="7f3aa-p103">Dopo aver creato un criterio DLP nel centro conformità & sicurezza, i criteri vengono distribuiti in tutti i percorsi inclusi nel criterio. Se il criterio è incluso in Exchange Online, i criteri vengono sincronizzati e applicati in modo esattamente analogo a quello di un criterio DLP creato nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-p103">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="7f3aa-p104">Se i criteri DLP sono stati creati nell'interfaccia di amministrazione di Exchange, tali criteri continueranno a funzionare fianco a fianco con qualsiasi criterio per la posta elettronica creato nel centro sicurezza & Compliance. Tuttavia, tenere presente che le regole create nell'interfaccia di amministrazione di Exchange hanno la precedenza. Tutte le regole del flusso di posta di Exchange vengono elaborate per prime e quindi vengono elaborate le regole DLP del Centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="7f3aa-119">Questo significa che:</span><span class="sxs-lookup"><span data-stu-id="7f3aa-119">This means that:</span></span>
  
- <span data-ttu-id="7f3aa-120">I messaggi bloccati dalle regole del flusso di posta di Exchange non vengono analizzati dalle regole DLP create nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="7f3aa-121">Se una regola del flusso di posta di Exchange modifica un messaggio in modo che corrisponda a un criterio DLP nel centro sicurezza & Compliance, ad esempio l'aggiunta di utenti esterni, le regole DLP lo rileveranno e implicheranno il criterio in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="7f3aa-122">Si noti inoltre che le regole del flusso di posta di Exchange che utilizzano l'azione "Interrompi l'elaborazione" non influiscono sull'elaborazione delle regole DLP nel centro sicurezza & Compliance: verranno comunque elaborate.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="7f3aa-123">Suggerimenti per i criteri nel centro conformità di sicurezza & e nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="7f3aa-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="7f3aa-p105">I suggerimenti per i criteri possono essere compatibili con i criteri DLP e le regole del flusso di posta creati nell'interfaccia di amministrazione di Exchange oppure con i criteri DLP creati nel centro sicurezza & Compliance, ma non in entrambi. Ciò è dovuto al fatto che questi criteri sono archiviati in posizioni diverse, ma i suggerimenti per i criteri possono essere disegnati solo da una singola posizione.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="7f3aa-p106">Se sono stati configurati suggerimenti per i criteri nell'interfaccia di amministrazione di Exchange, tutti i suggerimenti per i criteri configurati nel centro conformità sicurezza & non verranno visualizzati negli utenti di Outlook sul Web e in Outlook 2013 e versioni successive finché non si disattivano i suggerimenti nell'interfaccia di amministrazione di Exchange. Questo garantisce che le regole del flusso di posta di Exchange correnti continueranno a funzionare fino a quando non si sceglie di passare al centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-p106">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center. This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="7f3aa-128">Si noti che, mentre i suggerimenti per i criteri possono essere disegnati solo da una singola posizione, le notifiche di posta elettronica vengono sempre inviate, anche se si utilizzano i criteri DLP sia nel centro sicurezza & Compliance che nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="7f3aa-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

