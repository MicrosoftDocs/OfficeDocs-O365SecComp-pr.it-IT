---
title: Configurare gli utenti e i casi in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Informazioni su come configurare i ruoli utente, creare casi e assegnare gli utenti ai casi in Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: f393c59a9726baa6d7423eacb33543ae7adf5065
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212989"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="b406e-103">Configurare gli utenti e i casi in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b406e-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="b406e-104">In questo argomento viene descritto come configurare gli utenti e i casi per Office 365 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b406e-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b406e-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="b406e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="b406e-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b406e-107">Prerequisites</span></span>

<span data-ttu-id="b406e-108">Prima di configurare i casi e gli utenti in Advanced eDiscovery, è necessario quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b406e-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="b406e-p102">Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata. Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5.</span><span class="sxs-lookup"><span data-stu-id="b406e-p102">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="b406e-p103">È necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza &amp; e conformità di Office 365 per creare un caso di eDiscovery e aggiungere membri. Per aggiungersi al gruppo di ruoli eDiscovery Manager nel centro &amp; sicurezza e conformità, è necessario essere un amministratore globale dell'organizzazione di Office 365. Se non si è un amministratore globale, è necessario chiedere a un amministratore globale di aggiungerlo al gruppo di ruoli eDiscovery Manager. Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="b406e-p103">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it. To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization. If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group. For more information, see:</span></span>
    
  - [<span data-ttu-id="b406e-116">Autorizzazioni nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="b406e-116">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="b406e-117">Assegnare le autorizzazioni di eDiscovery nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="b406e-117">Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="b406e-118">Passaggio 1: assegnare autorizzazioni di eDiscovery agli utenti</span><span class="sxs-lookup"><span data-stu-id="b406e-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="b406e-p104">Il primo passaggio consiste nell'assegnare agli utenti le autorizzazioni dei requisiti nel &amp; Centro sicurezza e conformità in modo che possano essere aggiunte come membri di un caso di eDiscovery. Dopo che un utente è stato aggiunto come membro di un caso nel centro &amp; sicurezza e conformità, sarà possibile accedere al caso in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b406e-p104">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case. After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="b406e-121">Per assegnare a un utente le autorizzazioni necessarie in modo che possano essere aggiunte come membri di un caso di eDiscovery, vedere il passaggio 1 in [eDiscovery Cases in &amp; The Office 365 Security Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="b406e-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="b406e-122">Passaggio 2: creare un caso di eDiscovery e aggiungere membri</span><span class="sxs-lookup"><span data-stu-id="b406e-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="b406e-p105">Il passaggio successivo consiste nel creare un nuovo caso di eDiscovery nel centro &amp; conformità sicurezza e aggiungere membri. I membri del caso saranno quindi in grado di accedere al caso in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b406e-p105">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members. Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="b406e-125">Per creare un nuovo caso di eDiscovery, vedere il passaggio 2 in [eDiscovery Cases in the &amp; Office 365 Security Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="b406e-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="b406e-126">Per aggiungere membri a un caso di eDiscovery, vedere il passaggio 3 nei [casi di eDiscovery nel centro &amp; sicurezza e conformità di Office 365](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="b406e-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="b406e-127">Passaggio 3: andare a un caso in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b406e-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="b406e-p106">Dopo aver creato un caso di eDiscovery e aver aggiunto membri, l'utente (o qualsiasi membro del caso) può accedere al caso corrispondente in Advanced eDiscovery. Per accedere a un caso in Advanced eDiscovery, vedere il passaggio 8 in [eDiscovery Cases in the &amp; Office 365 Security Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="b406e-p106">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery. To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b406e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b406e-130">See also</span></span>

[<span data-ttu-id="b406e-131">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b406e-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b406e-132">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="b406e-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 