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
description: Scoprire in che modo le funzionalità di intelligence in Office 365 Advanced Threat Protection consentono di ricercare le minacce per la propria organizzazione, di rispondere a malware, phishing e altri attacchi che Office 365 ha rilevato per conto dell'utente e di cercare una minaccia indicatori.
ms.openlocfilehash: 54dbe4cc39456189bca2af71294d181adce6f50b
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "30639033"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="b2175-103">Indagine e risposta alle minacce di Office 365</span><span class="sxs-lookup"><span data-stu-id="b2175-103">Office 365 Threat Investigation and Response</span></span>

<span data-ttu-id="b2175-104">Le funzionalità di ricerca e risposta alle minacce in Office 365 Advanced Threat Protection aiutano gli analisti e gli amministratori della sicurezza a proteggere gli utenti di Office 365 dell'organizzazione per:</span><span class="sxs-lookup"><span data-stu-id="b2175-104">Threat investigation and response capabilities in Office 365 Advanced Threat Protection help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="b2175-105">Semplificare l'identificazione, il monitoraggio e la comprensione degli attacchi</span><span class="sxs-lookup"><span data-stu-id="b2175-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="b2175-106">Assistenza per l'indirizzamento rapido delle minacce in Exchange Online, SharePoint Online, OneDrive for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2175-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="b2175-107">Fornire informazioni e approfondimenti utili per prevenire gli attacchi alla propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="b2175-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="b2175-108">Indagine automatizzata e risposta per minacce critiche basate sulla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b2175-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b2175-109">**Office 365 Advanced Threat Protection and Threat Investigation and Responses (precedentemente noto come Office 365 Threat Intelligence) fanno ora parte di office 365 Advanced Threat Protection Plan 2**, incluso in alcuni abbonamenti, ad esempio [ Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education a5 e così via. Se l'organizzazione dispone di un abbonamento che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="b2175-109">**Office 365 Advanced Threat Protection and Threat Investigation and Responses (previously known as Office 365 Threat Intelligence) are now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="b2175-110">Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span><span class="sxs-lookup"><span data-stu-id="b2175-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="b2175-111">Cosa cambia?</span><span class="sxs-lookup"><span data-stu-id="b2175-111">What's changing?</span></span>

<span data-ttu-id="b2175-112">Precedentemente, le funzionalità di analisi delle minacce e delle risposte di Office 365 sono state incluse in sottoscrizioni, ad esempio Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="b2175-112">Formerly, Office 365 Threat investigation and responses capabilities were included in subscriptions, such as Office 365 Enterprise E5.</span></span> <span data-ttu-id="b2175-113">Questo è ancora il caso e ora queste funzionalità fanno parte di Office 365 Advanced Threat Protection piano 2 (e questo è incluso in Office 365 Enterprise E5).</span><span class="sxs-lookup"><span data-stu-id="b2175-113">This is still the case, and now these features are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="b2175-114">Inoltre, le funzionalità di analisi e di risposta alle minacce di Office 365 erano già disponibili per l'acquisto come componente aggiuntivo per i clienti di Office 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="b2175-114">In addition, Office 365 Threat investigation and response capabilities were formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="b2175-115">A questo punto, queste funzionalità sono incluse in Office 365 Advanced Threat Protection Plan 2 (che include anche Office 365 Advanced Threat Protection Plan 1).</span><span class="sxs-lookup"><span data-stu-id="b2175-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (which also includes Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="b2175-116">Per ulteriori informazioni, vedere [piani e prezzi per la protezione avanzata dalle minacce di Office 365](https://products.office.com/exchange/advance-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="b2175-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="b2175-117">Ecco cosa significa tutto questo:</span><span class="sxs-lookup"><span data-stu-id="b2175-117">Here's what all this means:</span></span>

- <span data-ttu-id="b2175-118">**Se l'organizzazione dispone già di Office 365 Enterprise E5**, si dispone già di Advanced Threat Protection piano 2, che include le funzionalità di analisi e di risposta alle minacce.</span><span class="sxs-lookup"><span data-stu-id="b2175-118">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes Threat investigation and response capabilities.</span></span>

- <span data-ttu-id="b2175-119">**Se l'organizzazione aveva precedentemente office 365 Threat Intelligence (ma non office 365 Advanced Threat Protection) come componente aggiuntivo** di un altro abbonamento a Office 365, sarà necessario disporre di Office 365 Advanced Threat Protection Plan 2.</span><span class="sxs-lookup"><span data-stu-id="b2175-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="b2175-120">Questo include Office 365 Advanced Threat Protection Plan 1 e le funzionalità di ricerca e di risposta alle minacce.</span><span class="sxs-lookup"><span data-stu-id="b2175-120">This includes Office 365 Advanced Threat Protection Plan 1 and Threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="b2175-121">**Se l'organizzazione aveva precedentemente office 365 Advanced Threat Protection (ma non office 365 Threat Intelligence) come componente aggiuntivo** di un altro abbonamento a Office 365, sarà necessario disporre di Office 365 Advanced Threat Protection Plan 1.</span><span class="sxs-lookup"><span data-stu-id="b2175-121">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="b2175-122">Questo include Office 365 Advanced Threat Protection (ma non le funzionalità di analisi e risposta alle minacce).</span><span class="sxs-lookup"><span data-stu-id="b2175-122">This includes Office 365 Advanced Threat Protection (but not Threat investigation and response capabilities).</span></span>

<span data-ttu-id="b2175-123">Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="b2175-123">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="b2175-124">Iniziare a utilizzare le funzionalità di analisi e risposta alle minacce</span><span class="sxs-lookup"><span data-stu-id="b2175-124">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="b2175-125">Utilizzare le risorse seguenti per ulteriori informazioni sulle funzionalità di ricerca e risposta alle minacce in Office 365 e su come utilizzarlo per rendere più sicure le persone nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2175-125">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="b2175-126">[Introduzione all'analisi e alla risposta alle minacce](get-started-with-ti.md) (include informazioni sui ruoli necessari)</span><span class="sxs-lookup"><span data-stu-id="b2175-126">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="b2175-127">Informazioni sui tracker di minacce: nuove e degne di nota</span><span class="sxs-lookup"><span data-stu-id="b2175-127">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="b2175-128">Ricerca e analisi di messaggi di posta elettronica dannosi recapitati</span><span class="sxs-lookup"><span data-stu-id="b2175-128">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="b2175-129">Usare simulatore di attacco</span><span class="sxs-lookup"><span data-stu-id="b2175-129">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="b2175-130">Integrazione di analisi e risposta alle minacce con Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b2175-130">Integrate Threat Investigation and Response with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="b2175-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b2175-131">Related topics</span></span>

[<span data-ttu-id="b2175-132">Protezione dalle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="b2175-132">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="b2175-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b2175-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="b2175-134">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b2175-134">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
