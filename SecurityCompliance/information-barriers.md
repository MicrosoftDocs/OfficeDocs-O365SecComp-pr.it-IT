---
title: Panoramica delle barriere informative
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare le barriere informative per garantire la conformità della comunicazione tramite Microsoft teams all'interno dell'organizzazione.
ms.openlocfilehash: a2c202d08f1de60f92f13b2ac4c2b9d3c7f900e8
ms.sourcegitcommit: eeb51470d8996e93fac28d7f12c6117e2aeb0cf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2019
ms.locfileid: "34935938"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="792a7-103">Barriere informative (anteprima)</span><span class="sxs-lookup"><span data-stu-id="792a7-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="792a7-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="792a7-104">Overview</span></span>

<span data-ttu-id="792a7-105">I servizi cloud Microsoft includono potenti funzionalità di comunicazione e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="792a7-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="792a7-106">Tuttavia, si supponga di voler limitare le comunicazioni tra due gruppi per evitare che si verifichi un conflitto di interessi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="792a7-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="792a7-107">In alternativa, è possibile limitare le comunicazioni tra alcune persone all'interno dell'organizzazione per salvaguardare le informazioni interne.</span><span class="sxs-lookup"><span data-stu-id="792a7-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="792a7-108">Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni, quindi è possibile limitare le comunicazioni tra i gruppi di utenti specifici, se necessario.</span><span class="sxs-lookup"><span data-stu-id="792a7-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="792a7-109">Con barriere informative, è possibile!</span><span class="sxs-lookup"><span data-stu-id="792a7-109">With information barriers, you can!</span></span> 

<span data-ttu-id="792a7-110">Le barriere informative sono ora in anteprima, a partire da Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="792a7-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="792a7-111">Quando queste funzionalità sono disponibili per la propria organizzazione, un amministratore di conformità o di barriere informative può definire criteri che consentano o impediscano le comunicazioni tra i gruppi di utenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="792a7-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="792a7-112">I criteri di barriera delle informazioni possono essere utilizzati per situazioni come queste:</span><span class="sxs-lookup"><span data-stu-id="792a7-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="792a7-113">Un trader diurno non può chiamare qualcuno del team di marketing</span><span class="sxs-lookup"><span data-stu-id="792a7-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="792a7-114">Il personale finanziario che lavora su informazioni aziendali riservate non è in grado di ricevere chiamate da determinati gruppi all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="792a7-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="792a7-115">Un team interno con materiale segreto commerciale non può chiamare o chattare online con persone di alcuni gruppi all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="792a7-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="792a7-116">Un team di ricerca può solo chiamare o chattare online con un team di sviluppo del prodotto</span><span class="sxs-lookup"><span data-stu-id="792a7-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="792a7-117">Per tutti questi scenari di esempio e altro ancora, è possibile definire i criteri di barriera delle informazioni per impedire o consentire le comunicazioni in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="792a7-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="792a7-118">Tali criteri possono impedire agli utenti di effettuare chiamate o chattare con coloro che non devono o consentire agli utenti di comunicare solo con gruppi specifici in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="792a7-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="792a7-119">Con i criteri di protezione delle informazioni in vigore, quando gli utenti interessati da tali criteri tentano di comunicare con altri membri di Microsoft teams, vengono eseguiti i controlli per impedire (o consentire) la comunicazione (come definito dai criteri di barriera delle informazioni).</span><span class="sxs-lookup"><span data-stu-id="792a7-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="792a7-120">Per ulteriori informazioni sull'esperienza utente con barriere informative, vedere barriere informative [in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="792a7-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="792a7-121">Gli ostacoli alle informazioni non si applicano alle comunicazioni di posta elettronica o alla condivisione di file tramite SharePoint Online o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="792a7-121">Information barriers will not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="792a7-122">Licenze e autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="792a7-122">Required licenses and permissions</span></span>

<span data-ttu-id="792a7-123">**Attualmente, la caratteristica barriera informativa è in anteprima privata**.</span><span class="sxs-lookup"><span data-stu-id="792a7-123">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="792a7-124">Quando queste funzionalità sono in genere disponibili, verranno incluse nelle sottoscrizioni, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="792a7-124">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="792a7-125">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="792a7-125">Microsoft 365 E5</span></span>
- <span data-ttu-id="792a7-126">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="792a7-126">Office 365 E5</span></span>
- <span data-ttu-id="792a7-127">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="792a7-127">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="792a7-128">Microsoft 365 E5 Information Protection and Compliance</span><span class="sxs-lookup"><span data-stu-id="792a7-128">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="792a7-129">Per ulteriori informazioni, vedere [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span><span class="sxs-lookup"><span data-stu-id="792a7-129">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="792a7-130">Per [definire o modificare criteri di barriera delle informazioni](information-barriers-policies.md), è necessario essere assegnati a uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="792a7-130">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="792a7-131">Microsoft 365 amministratore globale</span><span class="sxs-lookup"><span data-stu-id="792a7-131">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="792a7-132">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="792a7-132">Office 365 global administrator</span></span>
- <span data-ttu-id="792a7-133">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="792a7-133">Compliance administrator</span></span>
- <span data-ttu-id="792a7-134">Amministratore di barriere informative</span><span class="sxs-lookup"><span data-stu-id="792a7-134">Information barriers administrator</span></span>

<span data-ttu-id="792a7-135">È necessario avere familiarità con i cmdlet di PowerShell per definire, convalidare o modificare i criteri di barriera delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="792a7-135">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="792a7-136">Anche se vengono forniti diversi esempi di cmdlet di PowerShell nelle [informazioni su come](information-barriers-policies.md), è necessario conoscere ulteriori dettagli, ad esempio i parametri, per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="792a7-136">Although we provide several examples of PowerShell cmdlets in the [how-to information](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="792a7-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="792a7-137">Next steps</span></span>

- [<span data-ttu-id="792a7-138">Per ulteriori informazioni, vedere barriere informative in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="792a7-138">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="792a7-139">Visualizzare gli attributi che è possibile utilizzare per i criteri di barriera delle informazioni</span><span class="sxs-lookup"><span data-stu-id="792a7-139">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="792a7-140">Definire i criteri per le barriere informative</span><span class="sxs-lookup"><span data-stu-id="792a7-140">Define policies for information barriers</span></span>](information-barriers-policies.md) 

