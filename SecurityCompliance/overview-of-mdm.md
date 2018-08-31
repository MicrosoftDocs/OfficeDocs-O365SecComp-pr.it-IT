---
title: Panoramica della gestione dei dispositivi mobili (MDM) per Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365M_MDMConfigDomains
- O365E_MDMConfigDomains
- ms.o365.cc.DevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: faa7d8e5-645d-4d59-839c-c8d4c1869e4a
description: È possibile gestire e proteggere i dispositivi mobili sono connessi alla propria organizzazione Office 365 mediante l'utilizzo di gestione dei dispositivi mobili per Office 365. I dispositivi mobili quali Smartphone e Tablet che consentono di accedere a posta elettronica ufficio, calendario, contatti e documenti riprodurre gran parte da eseguire per verificare che i dipendenti per lavorare in qualsiasi momento, da qualsiasi posizione. In modo da essere critico consentono di proteggere le informazioni dell'organizzazione in cui si utilizzano dispositivi. È possibile utilizzare MDM per Office 365 per impostare la sicurezza dei dispositivi regole criteri e l'accesso e se si sta perduti o rubati a comparsa da dispositivi mobili.
ms.openlocfilehash: f06cef11b68ee0673f13c54738f07f4556495fdd
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272491"
---
# <a name="overview-of-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="1c653-106">Panoramica della gestione dei dispositivi mobili (MDM) per Office 365</span><span class="sxs-lookup"><span data-stu-id="1c653-106">Overview of Mobile Device Management (MDM) for Office 365</span></span>

<span data-ttu-id="1c653-p102">È possibile gestire e proteggere i dispositivi mobili sono connessi alla propria organizzazione Office 365 mediante l'utilizzo di gestione dei dispositivi mobili per Office 365. I dispositivi mobili quali Smartphone e Tablet che consentono di accedere a posta elettronica ufficio, calendario, contatti e documenti riprodurre gran parte da eseguire per verificare che i dipendenti per lavorare in qualsiasi momento, da qualsiasi posizione. In modo da essere critico consentono di proteggere le informazioni dell'organizzazione in cui si utilizzano dispositivi. È possibile utilizzare MDM per Office 365 per impostare la sicurezza dei dispositivi regole criteri e l'accesso e se si sta perduti o rubati a comparsa da dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="1c653-p102">You can manage and secure mobile devices when they're connected to your Office 365 organization by using Mobile Device Management for Office 365. Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere. So it's critical that you help protect your organization's information when people use devices. You can use MDM for Office 365 to set device security policies and access rules, and to wipe mobile devices if they're lost or stolen.</span></span>
  
![MDM sul telefono Android](media/69b9a9f6-13ac-4e36-99ca-95e82e0375aa.png)
  
## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="1c653-112">Quali tipi di dispositivi è possibile gestire?</span><span class="sxs-lookup"><span data-stu-id="1c653-112">What types of devices can you manage?</span></span>

<span data-ttu-id="1c653-p103">È possibile utilizzare MDM per Office 365 per gestire diversi tipi di dispositivi mobili come Windows Phone, Android, iPhone e iPad. Per gestire i dispositivi mobili utilizzati dagli utenti nell'organizzazione, ogni utente deve disporre di una licenza di Office 365 applicabile e i dispositivi devono essere iscritti MDM per Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c653-p103">You can use MDM for Office 365 to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad. To manage mobile devices used by people in your organization, each person must have an applicable Office 365 license and their device must be enrolled in MDM for Office 365.</span></span> 
  
<span data-ttu-id="1c653-115">Per visualizzare elementi supportati per ogni tipo di dispositivo MDM per Office 365, vedere [Funzionalità di gestione dei dispositivi mobili per Office 365](capabilities-of-mobile-device-management.md).</span><span class="sxs-lookup"><span data-stu-id="1c653-115">To see what MDM for Office 365 supports for each type of device, see [Capabilities of Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md).</span></span>
  
## <a name="setup-steps-for-mdm"></a><span data-ttu-id="1c653-116">Procedura di configurazione per MDM</span><span class="sxs-lookup"><span data-stu-id="1c653-116">Setup steps for MDM</span></span>

<span data-ttu-id="1c653-p104">Un amministratore globale di Office 365 è necessario completare la procedura seguente per attivare e configurare MDM per Office 365. Seguire le istruzioni nell'argomento [impostazione MDM per Office 365](set-up-mobile-device-management.md) per visualizzare la procedura dettagliata. Di seguito è riportato un riepilogo rapido:</span><span class="sxs-lookup"><span data-stu-id="1c653-p104">An Office 365 global admin must complete the following steps to activate and set up MDM for Office 365. Follow the guidance in the topic on [setting up MDM for Office 365](set-up-mobile-device-management.md) to see detailed steps. Here's a quick summary:</span></span> 
  
> <span data-ttu-id="1c653-120">Passaggio 1: Attivare MDM per Office 365 seguendo i passaggi descritti in [Set up Mobile Device Management (MDM) in Office 365](set-up-mobile-device-management.md).</span><span class="sxs-lookup"><span data-stu-id="1c653-120">Step 1: Activate MDM for Office 365 by following steps in the [Set up Mobile Device Management (MDM) in Office 365](set-up-mobile-device-management.md).</span></span>
    
> <span data-ttu-id="1c653-121">Passaggio 2: Impostare MDM per Office 365, ad esempio, creare un certificato APNs per la gestione dei dispositivi iOS e aggiungere un record di sistema DNS (Domain Name) per il dominio per il supporto di Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="1c653-121">Step 2: Set up MDM for Office 365 by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>
    
> <span data-ttu-id="1c653-p105">Passaggio 3: Creare i criteri dei dispositivi e applicarle a gruppi di utenti. A tale scopo, gli utenti riceveranno un [messaggio di registrazione nel dispositivo](enroll-your-mobile-device.md). E, quando è una volta completata la registrazione, i dispositivi saranno limitati dai criteri di che impostare le relative.</span><span class="sxs-lookup"><span data-stu-id="1c653-p105">Step 3: Create device policies and apply them to groups of users. When you do this, your users will get an [enrollment message on their device](enroll-your-mobile-device.md). And when they've completed enrollment, their devices will be restricted by the policies you've set up for them.</span></span>
    
    ![Creating an MDN device policy under Device security policies](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
## <a name="device-management-tasks"></a><span data-ttu-id="1c653-125">Attività di gestione di dispositivi</span><span class="sxs-lookup"><span data-stu-id="1c653-125">Device management tasks</span></span>

<span data-ttu-id="1c653-p106">Dopo aver ottenuto MDM per configurare Office 365 e gli utenti sono registrati i dispositivi, è possibile gestire i dispositivi, bloccare l'accesso o cancellazione di un dispositivo, se necessario. Ulteriori informazioni su [alcune attività di gestione dei dispositivi comuni](manage-devices-in-mdm.md), tra cui la posizione in cui eseguire le attività.</span><span class="sxs-lookup"><span data-stu-id="1c653-p106">After you've got MDM for Office 365 set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if needed. Learn more about [some common device management tasks](manage-devices-in-mdm.md), including where to complete the tasks.</span></span>
  
## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="1c653-128">Altri modi per gestire i dispositivi e applicazioni</span><span class="sxs-lookup"><span data-stu-id="1c653-128">Other ways to manage devices and apps</span></span>

<span data-ttu-id="1c653-129">Se è necessario maggiori funzionalità rispetto MDM per Office 365 include, estrarre il [confronto delle funzionalità MDM e Microsoft Intune](choose-between-mdm-and-intune.md) per verificare se una sottoscrizione Intune potrebbe soddisfare le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1c653-129">If you need more functionality than MDM for Office 365 includes, check out this [comparison of MDM and Microsoft Intune features](choose-between-mdm-and-intune.md) to see if an Intune subscription would meet your organization's needs.</span></span> 
  
<span data-ttu-id="1c653-p107">Se è necessario Gestione applicazioni per dispositivi mobili (MAM), ad esempio per gli utenti di aggiornamento dei progetti di lavoro nei propri dispositivi Intune è disponibile un'altra opzione oltre la registrazione e gestione di dispositivi. Una sottoscrizione Intune consente di impostare i criteri MAM tramite il portale di Azure, anche se i dispositivi di utenti non vengono iscritti Intune. Vedere [Protect app dati tramite i criteri per MAM](https://go.microsoft.com/fwlink/?LinkId=825439).</span><span class="sxs-lookup"><span data-stu-id="1c653-p107">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices. An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune. See [Protect app data using MAM policies](https://go.microsoft.com/fwlink/?LinkId=825439).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1c653-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c653-133">See also</span></span>

[<span data-ttu-id="1c653-134">Ottenere informazioni dettagliate sui dispositivi gestiti da MDM</span><span class="sxs-lookup"><span data-stu-id="1c653-134">Get details about devices managed by MDM</span></span>](get-details-about-mdm-managed-devices.md)

[<span data-ttu-id="1c653-135">Configurazione di MDM per Office 365</span><span class="sxs-lookup"><span data-stu-id="1c653-135">Set up MDM for Office 365</span></span>](set-up-mobile-device-management.md)
  
[<span data-ttu-id="1c653-136">Registrare i dispositivi mobili in MDM</span><span class="sxs-lookup"><span data-stu-id="1c653-136">Enroll mobile devices in MDM</span></span>](enroll-your-mobile-device.md)
  
[<span data-ttu-id="1c653-137">Gestire i dispositivi iscritti MDM</span><span class="sxs-lookup"><span data-stu-id="1c653-137">Manage devices enrolled in MDM</span></span>](manage-devices-in-mdm.md)

