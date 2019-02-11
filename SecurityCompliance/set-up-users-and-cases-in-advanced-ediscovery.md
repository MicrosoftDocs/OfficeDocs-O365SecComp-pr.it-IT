---
title: Configurare gli utenti e i casi in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Informazioni su come configurare i ruoli utente, creare casi e assegnare gli utenti ai casi di eDiscovery avanzate di Office 365.  '
ms.openlocfilehash: 4c0043b7651cc82272492e19faf01041c6f67932
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559059"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2ce15-103">Configurare gli utenti e i casi in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2ce15-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="2ce15-104">In questo argomento viene descritto come configurare gli utenti e dei casi eDiscovery avanzate di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ce15-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ce15-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2ce15-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="2ce15-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2ce15-107">Prerequisites</span></span>

<span data-ttu-id="2ce15-108">Prima di impostare i casi e gli utenti di eDiscovery avanzate, è necessario:</span><span class="sxs-lookup"><span data-stu-id="2ce15-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="2ce15-p102">Per analizzare i dati dell'utente tramite eDiscovery avanzate, l'utente (depositaria dei dati) deve essere assegnato una licenza di Office 365 E5. In alternativa, gli utenti con una licenza di Office 365 E1 o E3 è possibile assegnare una licenza autonoma eDiscovery avanzate. Gli amministratori e responsabili della conformità assegnati ai casi e utilizzare eDiscovery avanzate per analizzare i dati non è necessario una licenza E5.</span><span class="sxs-lookup"><span data-stu-id="2ce15-p102">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="2ce15-p103">È necessario essere membri del gruppo di ruoli gestione eDiscovery in Office 365 Security &amp; centro conformità per creare un caso eDiscovery e aggiungere membri a esso. Per aggiungersi al gruppo di ruoli di gestione di eDiscovery in sicurezza &amp; centro conformità, è necessario essere un amministratore globale dell'organizzazione Office 365. Se non si è un amministratore globale, è necessario contattare l'amministratore globale per aggiungere il gruppo di ruoli di gestione di eDiscovery. Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="2ce15-p103">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it. To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization. If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group. For more information, see:</span></span>
    
  - [<span data-ttu-id="2ce15-116">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="2ce15-116">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="2ce15-117">Assegnare le autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="2ce15-117">Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="2ce15-118">Passaggio 1: Assegnare agli utenti le autorizzazioni di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2ce15-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="2ce15-p104">Il primo passaggio consiste nel assegnare agli utenti le autorizzazioni requisito per la protezione &amp; Allinea al centro conformità in modo che è possibile me aggiunto come membro di un caso eDiscovery. Dopo l'aggiunta di un utente come membro di un caso di sicurezza &amp; centro conformità, saranno in grado di accedere il caso di eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="2ce15-p104">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case. After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="2ce15-121">Per assegnare un utente le autorizzazioni necessarie in modo che può essere aggiunto come membro di un caso di eDiscovery, vedere il passaggio 1 in [casi di eDiscovery in Office 365 Security &amp; centro conformità](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="2ce15-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="2ce15-122">Passaggio 2: Creare un caso eDiscovery e aggiungere membri</span><span class="sxs-lookup"><span data-stu-id="2ce15-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="2ce15-p105">Il passaggio successivo consiste nel creare un nuovo caso nella protezione &amp; centro conformità e aggiungere membri. Membri del caso quindi sarà in grado di accedere il caso di eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="2ce15-p105">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members. Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="2ce15-125">Per creare un nuovo caso, vedere Passaggio 2 in [casi di eDiscovery in Office 365 Security &amp; centro conformità](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="2ce15-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="2ce15-126">Per aggiungere membri a un caso eDiscovery, vedere il passaggio 3 [casi di eDiscovery in Office 365 Security &amp; centro conformità](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="2ce15-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="2ce15-127">Passaggio 3: Accedere a un caso di eDiscovery avanzate</span><span class="sxs-lookup"><span data-stu-id="2ce15-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="2ce15-p106">Dopo aver creato un caso eDiscovery e aggiungere membri, si (o qualsiasi membro di caso) può accedere il caso di eDiscovery avanzate corrispondente. Per accedere a un caso di eDiscovery avanzate, vedere il passaggio 8 in [casi di eDiscovery in Office 365 Security &amp; centro conformità](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="2ce15-p106">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery. To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2ce15-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ce15-130">See also</span></span>

[<span data-ttu-id="2ce15-131">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2ce15-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2ce15-132">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="2ce15-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 