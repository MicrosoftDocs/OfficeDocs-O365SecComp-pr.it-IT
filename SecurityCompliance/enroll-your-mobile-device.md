---
title: Registrare il dispositivo mobile in Office 365
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/25/2018
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: c8ac722d-dcaf-4135-8345-3e6327f5d3c5
description: Prima di poter utilizzare servizi di Office 365 con il dispositivo, potrebbe essere necessario eseguire la procedura seguente per registrarsi nella gestione dei dispositivi mobili per Office 365 (MDM). A tale scopo quando si aggiunge il lavoro o scuola account di posta elettronica sul dispositivo per la prima volta.
ms.openlocfilehash: 63e4052d42007d97928f158a704beb9721758a44
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272301"
---
# <a name="enroll-your-mobile-device-in-office-365"></a><span data-ttu-id="d397f-104">Registrare il dispositivo mobile in Office 365</span><span class="sxs-lookup"><span data-stu-id="d397f-104">Enroll your mobile device in Office 365</span></span>

<span data-ttu-id="d397f-p102">Utilizzo del telefono, tablet e altri dispositivi mobili per un determinato è un modo straordinario la possibilità di mantenersi informati e lavorare progetti business mentre si è fuori sede. Prima di poter utilizzare servizi di Office 365 con il dispositivo, è necessario innanzitutto effettuare la registrazione viene gestione dei dispositivi mobili per Office 365 (MDM) utilizzando Microsoft Intune portale della società.</span><span class="sxs-lookup"><span data-stu-id="d397f-p102">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you're away from the office. Before you can use Office 365 services with your device, you may need to first enroll it in Mobile Device Management for Office 365 (MDM) using Microsoft Intune Company Portal.</span></span>
  
<span data-ttu-id="d397f-p103">Organizzazioni scelgono MDM in modo che i dipendenti possono utilizzare dispositivi mobili per garantire un accesso sicuro lavoro posta elettronica, calendari e documenti mentre l'azienda viene protetto tramite dati importanti e soddisfi i requisiti di conformità. [Informazioni sui MDM in Office 365](https://go.microsoft.com/fwlink/?LinkId=615142).</span><span class="sxs-lookup"><span data-stu-id="d397f-p103">Organizations choose MDM so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements. [Learn about MDM in Office 365](https://go.microsoft.com/fwlink/?LinkId=615142).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d397f-p104">Quando si registra il dispositivo in MDM per Office 365, potrebbe essere necessario impostare una password, insieme a consentendo l'opzione per l'organizzazione di lavoro cancellare i dati del dispositivo. Una pulitura del dispositivo può essere eseguito (dall'interfaccia di amministrazione di Office 365), ad esempio, per rimuovere tutti i dati dal dispositivo, se l'immissione della password in modo non corretto più volte o condizioni di utilizzo vengono interrotti.</span><span class="sxs-lookup"><span data-stu-id="d397f-p104">When you enroll your device in MDM for Office 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device. A device wipe can be performed (from the Office 365 admin center), for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span> 
  
 <span data-ttu-id="d397f-111">**Dispositivi supportati**</span><span class="sxs-lookup"><span data-stu-id="d397f-111">**Supported devices**</span></span>
  
<span data-ttu-id="d397f-p105">MDM e InTune può essere utilizzato con la maggior parte, ma non tutti i dispositivi mobili. Di seguito è supportate con MDM per Office 365.</span><span class="sxs-lookup"><span data-stu-id="d397f-p105">MDM and InTune works with most, but not all, mobile devices. The following are supported with MDM for Office 365.</span></span>
  
- <span data-ttu-id="d397f-114">iOS 7.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="d397f-114">iOS 7.1 or later</span></span>
    
- <span data-ttu-id="d397f-115">Android 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="d397f-115">Android 4 or later</span></span>
    
- <span data-ttu-id="d397f-116">Windows 8.1 (telefono e PC) o versioni successive per includere Windows 10</span><span class="sxs-lookup"><span data-stu-id="d397f-116">Windows 8.1 (Phone and PC) and later to include Windows 10</span></span>
    
- <span data-ttu-id="d397f-117">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d397f-117">Windows 10</span></span>
    
<span data-ttu-id="d397f-118">Se il dispositivo non è elencato di sopra e si desidera utilizzare con MDM e Intune, rivolgersi all'amministratore di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="d397f-118">If your device is not listed above, and you need to use it with MDM and Intune, contact your work or school administrator.</span></span>
  
> [!TIP]
> <span data-ttu-id="d397f-119">Se si verificano problemi durante la registrazione del dispositivo, vedere: [risolvere i problemi registrazione dispositivo con MDM per Office 365](troubleshoot-mdm.md).</span><span class="sxs-lookup"><span data-stu-id="d397f-119">If you're having trouble enrolling your device, see: [Troubleshoot device enrollment with MDM for Office 365](troubleshoot-mdm.md).</span></span> 
  
## <a name="set-up-your-mobile-device-with-intune-and-mdm-for-office-365"></a><span data-ttu-id="d397f-120">Impostare il dispositivo mobile con Intune e MDM per Office 365</span><span class="sxs-lookup"><span data-stu-id="d397f-120">Set up your mobile device with Intune and MDM for Office 365</span></span>

<span data-ttu-id="d397f-121">Il portale aziendale Intune consente a un dispositivo da gestire Office 365 e MDM.</span><span class="sxs-lookup"><span data-stu-id="d397f-121">The Intune Company Portal enables a device to be managed by Office 365 and MDM.</span></span>
  
### <a name="iphone-or-ipad"></a><span data-ttu-id="d397f-122">iPhone o iPad</span><span class="sxs-lookup"><span data-stu-id="d397f-122">iPhone or iPad</span></span>

> [!TIP]
> <span data-ttu-id="d397f-123">Non sarà in grado di inviare e ricevere posta elettronica fino a completare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d397f-123">You won't be able to send and receive email until you complete this step.</span></span> 
  
> <span data-ttu-id="d397f-124">Passare a App Store Apple, scaricare e installare Intune portale della società.</span><span class="sxs-lookup"><span data-stu-id="d397f-124">Go to the Apple App Store, download and install Intune Company Portal.</span></span>
    
> <span data-ttu-id="d397f-125">[Eseguire la procedura seguente per configurare e connettere](https://go.microsoft.com/fwlink/?linkid=875316) il telefono iOS o tablet con il portale di società a Office 365.</span><span class="sxs-lookup"><span data-stu-id="d397f-125">[Follow these steps to configure and connect](https://go.microsoft.com/fwlink/?linkid=875316) your iOS phone or tablet with the Company portal to Office 365.</span></span> 
    
### <a name="android-phone-or-tablet"></a><span data-ttu-id="d397f-126">Android cellulare o tablet</span><span class="sxs-lookup"><span data-stu-id="d397f-126">Android phone or tablet</span></span>

> [!TIP]
> <span data-ttu-id="d397f-127">Non sarà in grado di inviare e ricevere posta elettronica fino a completare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d397f-127">You won't be able to send and receive email until you complete this step.</span></span> 
  
> <span data-ttu-id="d397f-128">Passare all'archivio di Google Play, scaricare e installare Intune portale della società.</span><span class="sxs-lookup"><span data-stu-id="d397f-128">Go to the Google Play store, download and install Intune Company Portal.</span></span>
    
> <span data-ttu-id="d397f-129">[Eseguire la procedura seguente per configurare e connettere](https://go.microsoft.com/fwlink/?linkid=875317) il telefono Android o tablet con il portale di società a Office 365.</span><span class="sxs-lookup"><span data-stu-id="d397f-129">[Follow these steps to configure and connect](https://go.microsoft.com/fwlink/?linkid=875317) your Android phone or tablet with the Company portal to Office 365.</span></span> 
    
## <a name="whats-next"></a><span data-ttu-id="d397f-130">Che cos'è successiva</span><span class="sxs-lookup"><span data-stu-id="d397f-130">What's next</span></span>

<span data-ttu-id="d397f-131">Dopo che il dispositivo è iscritto MDM per Office 365, iniziare a utilizzare Office apps sul dispositivo per l'utilizzo con posta elettronica, calendario, contatti e documenti.</span><span class="sxs-lookup"><span data-stu-id="d397f-131">After your device is enrolled in MDM for Office 365, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
  

