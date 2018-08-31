---
title: Come disattivare la gestione dei dispositivi mobili in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- GPA150
- MET150
ms.assetid: 2709cafb-0a8b-44bc-8494-7e2fccfa2b19
description: Eseguire la procedura seguente per arrestare criteri MDM impedita per i dispositivi mobili nella propria organizzazione Office 365.
ms.openlocfilehash: 6b8f0036ed999b10263f5cc074df27175769e604
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272221"
---
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a><span data-ttu-id="cf393-103">Come disattivare la gestione dei dispositivi mobili in Office 365</span><span class="sxs-lookup"><span data-stu-id="cf393-103">How to turn off Mobile Device Management in Office 365</span></span>

<span data-ttu-id="cf393-104">Per disattivare in modo efficace MDM per Office 365, rimuovere gruppi di utenti (definiti dai gruppi di sicurezza) dai criteri di gestione dei dispositivi o rimuovere i criteri di se stessi.</span><span class="sxs-lookup"><span data-stu-id="cf393-104">To effectively turn off MDM for Office 365, you remove groups of people (defined by security groups) from the device management policies, or remove the policies themselves.</span></span> 
  
- <span data-ttu-id="cf393-105">Rimuovere gruppi di utenti mediante la rimozione di gruppi di protezione utente dai criteri dispositivi che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="cf393-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span> 
    
- <span data-ttu-id="cf393-106">Rimozione di tutti i criteri per i dispositivi MDM disabilitare MDM per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cf393-106">Disable MDM for everyone by removing all MDM device policies.</span></span> 
    
<span data-ttu-id="cf393-p101">Queste opzioni rimuoverà imposizione MDM per i dispositivi nell'organizzazione. Purtroppo è non è semplicemente "annullamento del provisioning" MDM per Office 365 dopo è stato configurato.</span><span class="sxs-lookup"><span data-stu-id="cf393-p101">These options will remove MDM enforcement for devices in your organization. Unfortunately, you can't simply "unprovision" MDM for Office 365 after you've set it up.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cf393-p102">Tenere presente l'impatto sulle dispositivi degli utenti quando si eliminano gruppi di protezione utente da criteri oppure rimuovere i criteri di se stessi. Ad esempio postaelettronica profili e messaggi di posta elettronica memorizzati nella cache può essere rimosso, in base al dispositivo. Vedere: [Qual è l'impatto dei criteri di protezione per diversi tipi di dispositivo?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span><span class="sxs-lookup"><span data-stu-id="cf393-p102">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves. For example, email profiles and cached emails may be removed, depending on the device. See: [What is the impact of security policies on different device types?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span></span>
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a><span data-ttu-id="cf393-112">Rimuovere i criteri dei dispositivi MDM gruppi di protezione utente</span><span class="sxs-lookup"><span data-stu-id="cf393-112">Remove user security groups from MDM device policies</span></span>

1. <span data-ttu-id="cf393-113">Accedere a **protezione &amp; centro conformità** \> **prevenzione della perdita di dati** \> **dei criteri di protezione di dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="cf393-113">Go to **Security &amp; Compliance Center**\> **Data loss prevention** \> **Device security polices**.</span></span>
    
2. <span data-ttu-id="cf393-114">Selezionare un criterio dispositivi e fare clic su ![sull'icona Modifica](media/O365-MDM-CreatePolicy-EditIcon.gif) **modificare i criteri**.</span><span class="sxs-lookup"><span data-stu-id="cf393-114">Select a device policy, and click ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif) **Edit policy**.</span></span>
    
3. <span data-ttu-id="cf393-115">In **distribuzione**, fare clic su **- rimuovere**.</span><span class="sxs-lookup"><span data-stu-id="cf393-115">Under **Deployment**, click **- Remove**.</span></span>
    
    <span data-ttu-id="cf393-116">In **gruppi**, selezionare un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cf393-116">Under **Groups**, select a security group.</span></span>
    
4.  <span data-ttu-id="cf393-117">Fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="cf393-117">Click **Remove**.</span></span>
    
5. <span data-ttu-id="cf393-118">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cf393-118">Click **Save**.</span></span>
    
## <a name="remove-mdm-device-policies"></a><span data-ttu-id="cf393-119">Rimuovere i criteri dei dispositivi MDM</span><span class="sxs-lookup"><span data-stu-id="cf393-119">Remove MDM device policies</span></span>

1. <span data-ttu-id="cf393-120">Accedere a **protezione &amp; centro conformità** \> **criteri di protezione** \> **criteri di protezione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="cf393-120">Go to **Security &amp; Compliance Center**\> **Security policies** \> **Device security policies**.</span></span>
    
2. <span data-ttu-id="cf393-p103">Selezionare un criterio del dispositivo e quindi fare clic su ![immagine del Cestino può icona. ](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Eliminare criteri**.</span><span class="sxs-lookup"><span data-stu-id="cf393-p103">Select a device policy, and then click ![Image of the trash can icon.](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Delete policy**.</span></span>
    
3. <span data-ttu-id="cf393-123">Nella finestra di dialogo **avviso** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="cf393-123">In the **Warning** dialog, click **Yes**.</span></span> 
    

