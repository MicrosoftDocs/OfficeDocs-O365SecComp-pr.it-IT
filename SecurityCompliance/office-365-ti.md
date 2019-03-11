---
title: Indagine e risposta alle minacce di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/09/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Scoprire in che modo le funzionalità di intelligence di minacce in Advanced Threat Protection consentono di ricercare le minacce per la propria organizzazione, di rispondere a malware, phishing e altri attacchi rilevati da Office 365 per conto dell'utente e di cercare indicatori di minaccia.
ms.openlocfilehash: 1d076ed6ca48b8423ad92d5ea71bd87167b8519a
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524000"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="29668-103">Indagine e risposta alle minacce di Office 365</span><span class="sxs-lookup"><span data-stu-id="29668-103">Office 365 Threat Investigation and Response</span></span>

<span data-ttu-id="29668-104">Le funzionalità di ricerca e risposta alle minacce in Office 365 Advanced Threat Protection aiutano gli analisti e gli amministratori della sicurezza a proteggere gli utenti di Office 365 dell'organizzazione per:</span><span class="sxs-lookup"><span data-stu-id="29668-104">Threat investigation and response capabilities in Office 365 Advanced Threat Protection help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="29668-105">Semplificare l'identificazione, il monitoraggio e la comprensione degli attacchi</span><span class="sxs-lookup"><span data-stu-id="29668-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="29668-106">Assistenza per l'indirizzamento rapido delle minacce in Exchange Online, SharePoint Online, One Drive for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29668-106">Helping to quickly address threats in Exchange Online, SharePoint Online, One Drive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="29668-107">Fornire informazioni e approfondimenti utili per prevenire gli attacchi alla propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="29668-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="29668-108">Indagine automatizzata e risposta per minacce critiche basate sulla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="29668-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="29668-109">**Office 365 Threat Investigation and Responses (precedentemente noto come office 365 Threat Intelligence) fa ora parte di office 365 Advanced Threat Protection Plan 2**, incluso in alcuni abbonamenti, ad esempio [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education a5 e così via. Se l'organizzazione dispone di un abbonamento che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="29668-109">**Office 365 THreat Investigation and Responses (previously known as Office 365 Threat Intelligence) is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="29668-110">Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span><span class="sxs-lookup"><span data-stu-id="29668-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="29668-111">Cosa cambia?</span><span class="sxs-lookup"><span data-stu-id="29668-111">What's changing?</span></span>

<span data-ttu-id="29668-112">Precedentemente, le funzionalità di analisi delle minacce e delle risposte di Office 365 sono state incluse in sottoscrizioni, ad esempio Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="29668-112">Formerly, Office 365 Threat investigation and responses capabilities were included in subscriptions, such as Office 365 Enterprise E5.</span></span> <span data-ttu-id="29668-113">Questo è ancora il caso e ora queste funzionalità fanno parte di Office 365 Advanced Threat Protection piano 2 (e questo è incluso in Office 365 Enterprise E5).</span><span class="sxs-lookup"><span data-stu-id="29668-113">This is still the case, and now these features are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="29668-114">Inoltre, Office 365 Threat Investigation and Response capbailities sono stati precedentemente disponibili per l'acquisto come componente aggiuntivo per i clienti di Office 365 for business.</span><span class="sxs-lookup"><span data-stu-id="29668-114">In addition, Office 365 Threat investigation and response capbailities were formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="29668-115">A questo punto, queste funzionalità sono incluse in Office 365 Advanced Threat Protection Plan 2 (che include anche Office 365 Advanced Threat Protection Plan 1).</span><span class="sxs-lookup"><span data-stu-id="29668-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (which also includes Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="29668-116">Per ulteriori informazioni, vedere [piani e prezzi per la protezione avanzata dalle minacce di Office 365](https://products.office.com/exchange/advance-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="29668-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="29668-117">Ecco cosa significa tutto questo:</span><span class="sxs-lookup"><span data-stu-id="29668-117">Here's what all this means:</span></span>

- <span data-ttu-id="29668-118">**Se l'organizzazione dispone già di Office 365 Enterprise E5**, si dispone già di Advanced Threat Protection piano 2, che include le funzionalità di analisi e di risposta alle minacce.</span><span class="sxs-lookup"><span data-stu-id="29668-118">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes Threat investigation and response capabilities.</span></span>

- <span data-ttu-id="29668-119">**Se l'organizzazione aveva precedentemente office 365 Threat Intelligence (ma non office 365 Advanced Threat Protection) come componente aggiuntivo** di un altro abbonamento a Office 365, sarà necessario disporre di Office 365 Advanced Threat Protection Plan 2.</span><span class="sxs-lookup"><span data-stu-id="29668-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="29668-120">Questo include il piano 1 avanzato di protezione dalle minacce e le funzionalità di analisi e risposta alle minacce.</span><span class="sxs-lookup"><span data-stu-id="29668-120">This includes Advanced Threat Protection Plan 1 and Threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="29668-121">**Se l'organizzazione aveva precedentemente office 365 Advanced Threat Protection (ma non office 365 Threat Intelligence) come componente aggiuntivo** di un altro abbonamento a Office 365, sarà necessario disporre di Office 365 Advanced Threat Protection Plan 1.</span><span class="sxs-lookup"><span data-stu-id="29668-121">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="29668-122">Questo include la protezione avanzata dalle minacce (ma non le funzionalità di investigaiton e di risposta).</span><span class="sxs-lookup"><span data-stu-id="29668-122">This includes Advanced Threat Protection (but not Threat investigaiton and response capabilities).</span></span>

<span data-ttu-id="29668-123">Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="29668-123">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigaiton-and-response-capabilities"></a><span data-ttu-id="29668-124">Introduzione alle funzionalità di investigaiton e di risposta alle minacce</span><span class="sxs-lookup"><span data-stu-id="29668-124">Get started with threat investigaiton and response capabilities</span></span>

<span data-ttu-id="29668-125">Utilizzare le risorse seguenti per ulteriori informazioni sulle funzionalità di ricerca e risposta alle minacce in Office 365 e su come utilizzarlo per rendere più sicure le persone nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29668-125">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="29668-126">[Introduzione all'analisi e alla risposta alle minacce](get-started-with-ti.md) (include informazioni sui ruoli necessari)</span><span class="sxs-lookup"><span data-stu-id="29668-126">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="29668-127">Informazioni sui tracker di minacce: nuove e degne di nota</span><span class="sxs-lookup"><span data-stu-id="29668-127">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="29668-128">Ricerca e analisi di messaggi di posta elettronica dannosi recapitati</span><span class="sxs-lookup"><span data-stu-id="29668-128">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="29668-129">Usare simulatore di attacco</span><span class="sxs-lookup"><span data-stu-id="29668-129">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="29668-130">Integrazione di analisi e risposta alle minacce con Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="29668-130">Integrate Threat Investigation and Response with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="29668-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="29668-131">Related topics</span></span>

[<span data-ttu-id="29668-132">Protezione dalle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="29668-132">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="29668-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="29668-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="29668-134">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="29668-134">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 