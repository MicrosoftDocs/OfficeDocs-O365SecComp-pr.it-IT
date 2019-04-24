---
title: Funzionamento della prevenzione della perdita dei dati tra il Centro sicurezza e conformità e l'interfaccia di amministrazione di Exchange
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Informazioni su come DLP nel centro sicurezza & Compliance funziona con le regole del flusso di posta e DLP (regole di trasporto) nell'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: 66dceb447e02eb01810997c23644c76f68795844
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254930"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="0186f-103">Funzionamento della prevenzione della perdita dei dati tra il Centro sicurezza e conformità e l'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="0186f-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="0186f-104">In Office 365, è possibile creare un criterio di prevenzione della perdita di dati (DLP) in due diversi centri di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="0186f-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="0186f-105">Nel **Centro sicurezza _AMP_ Compliance**, è possibile creare un singolo criterio DLP per proteggere il contenuto in SharePoint, OneDrive ed Exchange.</span><span class="sxs-lookup"><span data-stu-id="0186f-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange.</span></span> <span data-ttu-id="0186f-106">Quando possibile, si consiglia di creare un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="0186f-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="0186f-107">Per ulteriori informazioni, vedere [DLP in the Security _AMP_ Compliance Center](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0186f-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="0186f-108">Nell'interfaccia di **amministrazione di Exchange**, è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange.</span><span class="sxs-lookup"><span data-stu-id="0186f-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="0186f-109">Questo criterio è in grado di utilizzare le regole del flusso di posta di Exchange (note anche come regole di trasporto), quindi dispone di più opzioni specifiche per la gestione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0186f-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="0186f-110">Per ulteriori informazioni, vedere [DLP nell'](https://go.microsoft.com/fwlink/?linkid=852311)interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0186f-110">For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="0186f-111">I criteri DLP creati in questi interfaccia di amministrazione sono affiancati-in questo argomento viene descritto come fare.</span><span class="sxs-lookup"><span data-stu-id="0186f-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Pagine DLP in centro sicurezza e conformità e interfaccia di amministrazione di Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="0186f-113">Come DLP nel centro sicurezza e conformità di & funziona con le regole del flusso di posta e DLP nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="0186f-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="0186f-114">Dopo aver creato un criterio DLP nel centro conformità & sicurezza, i criteri vengono distribuiti in tutti i percorsi inclusi nel criterio.</span><span class="sxs-lookup"><span data-stu-id="0186f-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="0186f-115">Se il criterio è incluso in Exchange Online, i criteri vengono sincronizzati e applicati in modo esattamente analogo a quello di un criterio DLP creato nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0186f-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="0186f-116">Se i criteri DLP sono stati creati nell'interfaccia di amministrazione di Exchange, tali criteri continueranno a funzionare fianco a fianco con qualsiasi criterio per la posta elettronica creato nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="0186f-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="0186f-117">Tuttavia, tenere presente che le regole create nell'interfaccia di amministrazione di Exchange hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="0186f-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="0186f-118">Tutte le regole del flusso di posta di Exchange vengono elaborate per prime e quindi vengono elaborate le regole DLP del Centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="0186f-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="0186f-119">Questo significa che:</span><span class="sxs-lookup"><span data-stu-id="0186f-119">This means that:</span></span>
  
- <span data-ttu-id="0186f-120">I messaggi bloccati dalle regole del flusso di posta di Exchange non vengono analizzati dalle regole DLP create nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="0186f-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="0186f-121">Se una regola del flusso di posta di Exchange modifica un messaggio in modo che corrisponda a un criterio DLP nel centro sicurezza & Compliance, ad esempio l'aggiunta di utenti esterni, le regole DLP lo rileveranno e implicheranno il criterio in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0186f-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="0186f-122">Si noti inoltre che le regole del flusso di posta di Exchange che utilizzano l'azione "Interrompi l'elaborazione" non influiscono sull'elaborazione delle regole DLP nel centro sicurezza & Compliance: verranno comunque elaborate.</span><span class="sxs-lookup"><span data-stu-id="0186f-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="0186f-123">Suggerimenti per i criteri nel centro conformità di sicurezza & e nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="0186f-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="0186f-124">I suggerimenti per i criteri possono essere compatibili con i criteri DLP e le regole del flusso di posta creati nell'interfaccia di amministrazione di Exchange oppure con i criteri DLP creati nel centro sicurezza & Compliance, ma non in entrambi.</span><span class="sxs-lookup"><span data-stu-id="0186f-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="0186f-125">Ciò è dovuto al fatto che questi criteri sono archiviati in posizioni diverse, ma i suggerimenti per i criteri possono essere disegnati solo da una singola posizione.</span><span class="sxs-lookup"><span data-stu-id="0186f-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="0186f-126">Se sono stati configurati suggerimenti per i criteri nell'interfaccia di amministrazione di Exchange, tutti i suggerimenti per i criteri configurati nel centro conformità sicurezza & non verranno visualizzati negli utenti di Outlook sul Web e in Outlook 2013 e versioni successive finché non si disattivano i suggerimenti nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0186f-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="0186f-127">Questo garantisce che le regole del flusso di posta di Exchange correnti continueranno a funzionare fino a quando non si sceglie di passare al centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="0186f-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="0186f-128">Si noti che, mentre i suggerimenti per i criteri possono essere disegnati solo da una singola posizione, le notifiche di posta elettronica vengono sempre inviate, anche se si utilizzano i criteri DLP sia nel centro sicurezza & Compliance che nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0186f-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

