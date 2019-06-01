---
title: Panoramica delle barriere informative
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare le barriere informative per garantire la conformità della comunicazione tramite Microsoft teams all'interno dell'organizzazione.
ms.openlocfilehash: e52a62ca0b80aed577be1978b81c8a01ac2371b9
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668308"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="8a27d-103">Barriere informative (anteprima)</span><span class="sxs-lookup"><span data-stu-id="8a27d-103">Information barriers (Preview)</span></span>

<span data-ttu-id="8a27d-104">I servizi cloud Microsoft includono potenti funzionalità di comunicazione e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="8a27d-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="8a27d-105">Tuttavia, si supponga di voler limitare le comunicazioni tra due gruppi per evitare che si verifichi un conflitto di interessi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a27d-105">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="8a27d-106">In alternativa, è possibile limitare le comunicazioni tra alcune persone all'interno dell'organizzazione per salvaguardare le informazioni interne.</span><span class="sxs-lookup"><span data-stu-id="8a27d-106">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="8a27d-107">Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni, quindi è possibile limitare le comunicazioni tra i gruppi di utenti specifici, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8a27d-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="8a27d-108">Con barriere informative, è possibile!</span><span class="sxs-lookup"><span data-stu-id="8a27d-108">With information barriers, you can!</span></span> 

<span data-ttu-id="8a27d-109">Le barriere informative sono ora in anteprima, a partire da Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8a27d-109">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="8a27d-110">Quando queste funzionalità sono disponibili per la propria organizzazione, un amministratore di conformità o di barriere informative può definire criteri che consentano o impediscano le comunicazioni tra i gruppi di utenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8a27d-110">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="8a27d-111">I criteri di barriera delle informazioni possono essere utilizzati per situazioni come queste:</span><span class="sxs-lookup"><span data-stu-id="8a27d-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="8a27d-112">Un trader diurno non può chiamare qualcuno del team di marketing</span><span class="sxs-lookup"><span data-stu-id="8a27d-112">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="8a27d-113">Il personale finanziario che lavora su informazioni aziendali riservate non è in grado di ricevere chiamate da determinati gruppi all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8a27d-113">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="8a27d-114">Un team interno con materiale segreto commerciale non può chiamare o chattare online con persone di alcuni gruppi all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a27d-114">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="8a27d-115">Un team di ricerca può solo chiamare o chattare online con un team di sviluppo del prodotto</span><span class="sxs-lookup"><span data-stu-id="8a27d-115">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="8a27d-116">Per tutti questi scenari di esempio e altro ancora, è possibile definire i criteri di barriera delle informazioni per impedire o consentire le comunicazioni in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8a27d-116">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="8a27d-117">Tali criteri possono impedire agli utenti di effettuare chiamate o chattare con coloro che non devono o consentire agli utenti di comunicare solo con gruppi specifici in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8a27d-117">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="8a27d-118">Con i criteri di protezione delle informazioni in vigore, quando gli utenti interessati da tali criteri tentano di comunicare con altri membri di Microsoft teams, vengono eseguiti i controlli per impedire (o consentire) la comunicazione (come definito dai criteri di barriera delle informazioni).</span><span class="sxs-lookup"><span data-stu-id="8a27d-118">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> 

> [!NOTE]
> <span data-ttu-id="8a27d-119">Gli ostacoli alle informazioni non si applicano alle comunicazioni di posta elettronica o alla condivisione di file tramite SharePoint Online o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="8a27d-119">Information barriers will not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span>

<span data-ttu-id="8a27d-120">I criteri di barriera delle informazioni si applicano ai tipi di attività di comunicazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a27d-120">Information barrier policies apply to the following kinds of communication activities:</span></span>

- <span data-ttu-id="8a27d-121">Ricerca di un utente</span><span class="sxs-lookup"><span data-stu-id="8a27d-121">Searching for user</span></span>
- <span data-ttu-id="8a27d-122">Aggiunta di un membro a un team</span><span class="sxs-lookup"><span data-stu-id="8a27d-122">Adding a member to a team</span></span>
- <span data-ttu-id="8a27d-123">Avvio di una sessione di chat con un utente</span><span class="sxs-lookup"><span data-stu-id="8a27d-123">Starting a chat session with someone</span></span>
- <span data-ttu-id="8a27d-124">Avvio di una chat di gruppo</span><span class="sxs-lookup"><span data-stu-id="8a27d-124">Starting a group chat</span></span> 
- <span data-ttu-id="8a27d-125">Invitare un utente a partecipare a una riunione</span><span class="sxs-lookup"><span data-stu-id="8a27d-125">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="8a27d-126">Condivisione di una schermata</span><span class="sxs-lookup"><span data-stu-id="8a27d-126">Sharing a screen</span></span> 
- <span data-ttu-id="8a27d-127">Effettuazione di una chiamata</span><span class="sxs-lookup"><span data-stu-id="8a27d-127">Placing a call</span></span>

<span data-ttu-id="8a27d-128">Se le persone coinvolte sono incluse in un criterio barriera informativo che impedisce l'attività, non saranno in grado di procedere.</span><span class="sxs-lookup"><span data-stu-id="8a27d-128">If the people involved are included in an information barrier policy that prevents the activity, they will not be able to proceed.</span></span> <span data-ttu-id="8a27d-129">Per ulteriori informazioni sull'esperienza utente con barriere informative, vedere barriere informative [in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="8a27d-129">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

<span data-ttu-id="8a27d-130">Attualmente, i criteri di barriera delle informazioni vengono definiti e gestiti in Office 365 utilizzando i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a27d-130">Currently, information barrier policies are defined and managed in Office 365 by using PowerShell cmdlets.</span></span> <span data-ttu-id="8a27d-131">Questo è in genere effettuato da un amministratore di conformità o da un amministratore globale e richiede familiarità con i cmdlet e i parametri di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a27d-131">This is typically done by a compliance administrator or a global administrator, and requires familiarity with PowerShell cmdlets (and parameters).</span></span> <span data-ttu-id="8a27d-132">Per ulteriori informazioni, vedere [PowerShell (per la definizione di barriere informative)](information-barriers-policies.md#powershell).</span><span class="sxs-lookup"><span data-stu-id="8a27d-132">To learn more, see [PowerShell (for defining information barriers)](information-barriers-policies.md#powershell).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="8a27d-133">Licenze e autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="8a27d-133">Required licenses and permissions</span></span>

<span data-ttu-id="8a27d-134">**Attualmente, la caratteristica barriera informativa è in anteprima privata**.</span><span class="sxs-lookup"><span data-stu-id="8a27d-134">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="8a27d-135">Quando queste funzionalità sono in genere disponibili, verranno incluse nelle sottoscrizioni, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8a27d-135">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="8a27d-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8a27d-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="8a27d-137">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="8a27d-137">Office 365 E5</span></span>
- <span data-ttu-id="8a27d-138">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="8a27d-138">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="8a27d-139">Microsoft 365 E5 Information Protection and Compliance</span><span class="sxs-lookup"><span data-stu-id="8a27d-139">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="8a27d-140">Per ulteriori informazioni, vedere [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span><span class="sxs-lookup"><span data-stu-id="8a27d-140">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="8a27d-141">Per [definire o modificare criteri di barriera delle informazioni](information-barriers-policies.md), è necessario essere assegnati a uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a27d-141">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="8a27d-142">Microsoft 365 amministratore globale</span><span class="sxs-lookup"><span data-stu-id="8a27d-142">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="8a27d-143">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="8a27d-143">Office 365 global administrator</span></span>
- <span data-ttu-id="8a27d-144">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="8a27d-144">Compliance administrator</span></span>
- <span data-ttu-id="8a27d-145">Amministratore di barriere informative</span><span class="sxs-lookup"><span data-stu-id="8a27d-145">Information barriers administrator</span></span>

<span data-ttu-id="8a27d-146">È necessario avere familiarità con i cmdlet di PowerShell per definire, convalidare o modificare i criteri di barriera delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="8a27d-146">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="8a27d-147">Anche se vengono forniti diversi esempi di cmdlet di PowerShell nelle [informazioni su come](information-barriers-policies.md), è necessario conoscere ulteriori dettagli, ad esempio i parametri, per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a27d-147">Although we provide several examples of PowerShell cmdlets in the [how-to information](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a27d-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8a27d-148">Next steps</span></span>

- [<span data-ttu-id="8a27d-149">Per ulteriori informazioni, vedere barriere informative in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a27d-149">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="8a27d-150">Visualizzare gli attributi che è possibile utilizzare per i criteri di barriera delle informazioni</span><span class="sxs-lookup"><span data-stu-id="8a27d-150">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="8a27d-151">Definire i criteri per le barriere informative</span><span class="sxs-lookup"><span data-stu-id="8a27d-151">Define policies for information barriers</span></span>](information-barriers-policies.md) 

