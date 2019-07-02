---
title: Analisi delle minacce e risposta alle minacce in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Scoprire in che modo le funzionalità di intelligence in Office 365 Advanced Threat Protection consentono di ricercare le minacce per la propria organizzazione, di rispondere a malware, phishing e altri attacchi che Office 365 ha rilevato per conto dell'utente e di cercare una minaccia indicatori.
ms.openlocfilehash: c8b0815368e80151f8ee55161b9bcbaa98065228
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852810"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="c3153-103">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="c3153-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="c3153-104">Le funzionalità di ricerca e risposta alle minacce in [office 365 Advanced Threat Protection](office-365-atp.md) aiutano gli analisti e gli amministratori della sicurezza a proteggere gli utenti di Office 365 dell'organizzazione per:</span><span class="sxs-lookup"><span data-stu-id="c3153-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="c3153-105">Semplificare l'identificazione, il monitoraggio e la comprensione degli attacchi</span><span class="sxs-lookup"><span data-stu-id="c3153-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="c3153-106">Assistenza per l'indirizzamento rapido delle minacce in Exchange Online, SharePoint Online, OneDrive for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3153-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="c3153-107">Fornire informazioni e approfondimenti utili per prevenire gli attacchi alla propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="c3153-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="c3153-108">Indagine automatizzata e risposta per minacce critiche basate sulla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c3153-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="c3153-109">**Office 365 Advanced Threat Protection and Threat Investigation and Response (precedentemente noto come office 365 Threat Intelligence) sono ora office 365 Advanced Threat Protection Plan 2**, oltre a ulteriori funzionalità di protezione dalle minacce incluse in alcuni abbonamenti, ad esempio [microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 a5 e così via. Se l'organizzazione dispone di un abbonamento che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="c3153-109">**Office 365 Advanced Threat Protection and Threat Investigation and Response (previously known as Office 365 Threat Intelligence) are now Office 365 Advanced Threat Protection Plan 2**, along with additional threat protection capabilities included in in certain subscriptions, such as [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="c3153-110">Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span><span class="sxs-lookup"><span data-stu-id="c3153-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="c3153-111">Cosa cambia?</span><span class="sxs-lookup"><span data-stu-id="c3153-111">What's changing?</span></span>

<span data-ttu-id="c3153-112">In precedenza, Office 365 Threat Intelligence è stato incluso in abbonamenti, ad esempio Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c3153-112">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 E5.</span></span> <span data-ttu-id="c3153-113">Questo è il caso, poiché le funzionalità di ricerca e di risposta delle minacce fanno ora parte di Office 365 Advanced Threat Protection Plan 2 (e questo è incluso in Office 365 E5).</span><span class="sxs-lookup"><span data-stu-id="c3153-113">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 E5).</span></span> 

<span data-ttu-id="c3153-114">Inoltre, Office 365 Threat Intelligence era precedentemente disponibile per l'acquisto come componente aggiuntivo per i clienti di Office 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="c3153-114">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="c3153-115">A questo punto, queste funzionalità sono incluse in Office 365 Advanced Threat Protection Plan 2 (insieme a tutte le funzionalità di Office 365 Advanced Threat Protection Plan 1).</span><span class="sxs-lookup"><span data-stu-id="c3153-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="c3153-116">Per ulteriori informazioni, vedere [piani e prezzi per la protezione avanzata dalle minacce di Office 365](https://products.office.com/exchange/advance-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="c3153-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="c3153-117">Ecco cosa significa tutto questo:</span><span class="sxs-lookup"><span data-stu-id="c3153-117">Here's what all this means:</span></span>

- <span data-ttu-id="c3153-118">**Se l'organizzazione dispone già di Office 365 E5**, si dispone già di Advanced Threat Protection piano 2, che include le funzionalità di analisi e di risposta alle minacce.</span><span class="sxs-lookup"><span data-stu-id="c3153-118">**If your organization already has Office 365 E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="c3153-119">**Se l'organizzazione aveva precedentemente office 365 Threat Intelligence (ma non office 365 Advanced Threat Protection) come componente aggiuntivo** di un altro abbonamento a Office 365, sarà ora disponibile Office 365 Advanced Threat Protection Plan 2 e include analisi delle minacce e funzionalità di risposta.</span><span class="sxs-lookup"><span data-stu-id="c3153-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="c3153-120">**Se l'organizzazione aveva precedentemente office 365 Advanced Threat Protection (ma non office 365 Threat Intelligence) come componente aggiuntivo** di un altro abbonamento a Office 365, sarà ora disponibile Office 365 Advanced Threat Protection Plan 1.</span><span class="sxs-lookup"><span data-stu-id="c3153-120">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="c3153-121">Questo include Office 365 Advanced Threat Protection Plan 1 (ma non le funzionalità di ricerca e di risposta alle minacce).</span><span class="sxs-lookup"><span data-stu-id="c3153-121">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="c3153-122">Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="c3153-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="c3153-123">Iniziare a utilizzare le funzionalità di analisi e risposta alle minacce</span><span class="sxs-lookup"><span data-stu-id="c3153-123">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="c3153-124">Utilizzare le risorse seguenti per ulteriori informazioni sulle funzionalità di ricerca e risposta alle minacce in Office 365 e su come utilizzarlo per rendere più sicure le persone nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3153-124">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="c3153-125">[Introduzione all'analisi e alla risposta alle minacce](get-started-with-ti.md) (include informazioni sui ruoli necessari)</span><span class="sxs-lookup"><span data-stu-id="c3153-125">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="c3153-126">Informazioni sui tracker di minacce: nuove e degne di nota</span><span class="sxs-lookup"><span data-stu-id="c3153-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="c3153-127">Risparmiare tempo e fatica con le funzionalità di analisi e risposta automatizzate (AIR)</span><span class="sxs-lookup"><span data-stu-id="c3153-127">Save time and effort with Automated Investigation and Response (AIR) capabilities</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="c3153-128">Utilizzo di Esplora minacce (o rilevamenti in tempo reale) per identificare e analizzare contenuti dannosi in messaggi di posta elettronica e file</span><span class="sxs-lookup"><span data-stu-id="c3153-128">Use Threat Explorer (or real-time detections) to identify and investigate malicious content in email and files</span></span>](threat-explorer.md)
    
- [<span data-ttu-id="c3153-129">Identificare e analizzare i messaggi di posta elettronica dannosi recapitati</span><span class="sxs-lookup"><span data-stu-id="c3153-129">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="c3153-130">Usare simulatore di attacco per simulare gli attacchi e aumentare la consapevolezza degli utenti</span><span class="sxs-lookup"><span data-stu-id="c3153-130">Use Attack Simulator to simulate attacks and increase user awareness</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="c3153-131">Integrazione delle funzionalità di ricerca e risposta alle minacce con Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c3153-131">Integrate Threat Investigation and Response capabilities with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="c3153-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c3153-132">Related topics</span></span>

[<span data-ttu-id="c3153-133">Visualizzazioni di Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="c3153-133">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="c3153-134">Protezione dalle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="c3153-134">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="c3153-135">Protezione avanzata dalle minacce di Office 365</span><span class="sxs-lookup"><span data-stu-id="c3153-135">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="c3153-136">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="c3153-136">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
