---
title: Risoluzione dei problemi di registrazione dei dispositivi con MDM per Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/17/2015
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c863b2bf-45f3-483a-ba05-29fc7f4d6434
description: Se si esegue problemi quando si tenta di registrare un dispositivo Mobile Device Management (MDM) per Office 365, eseguire i passaggi elencati di seguito per individuare il problema. Se i passaggi generali non risolve il problema, vedere una delle sezioni successive con passaggi specifici per il tipo di dispositivo.
ms.openlocfilehash: 490259fc623b38ab5ad6cf8553c5074c77b77426
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272111"
---
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a><span data-ttu-id="ab9f5-104">Risoluzione dei problemi di registrazione dei dispositivi con MDM per Office 365</span><span class="sxs-lookup"><span data-stu-id="ab9f5-104">Troubleshoot device enrollment with MDM for Office 365</span></span>

<span data-ttu-id="ab9f5-p102">Se si esegue problemi quando si tenta di registrare un dispositivo Mobile Device Management (MDM) per Office 365, eseguire i passaggi elencati di seguito per individuare il problema. Se i passaggi generali non risolve il problema, vedere una delle sezioni successive con passaggi specifici per il tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-p102">If you're running into issues when you try to enroll a device in Mobile Device Management (MDM) for Office 365, try the steps listed here to track down the problem. If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>
  
## <a name="steps-to-try-first"></a><span data-ttu-id="ab9f5-107">Procedure da seguire prima</span><span class="sxs-lookup"><span data-stu-id="ab9f5-107">Steps to try first</span></span>

<span data-ttu-id="ab9f5-108">Per iniziare, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ab9f5-108">To start, check the following:</span></span>
  
- <span data-ttu-id="ab9f5-109">Verificare che il dispositivo non è già registrato con un altro provider di gestione di dispositivi mobili, ad esempio Intune.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-109">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="ab9f5-110">Verificare che il dispositivo sia impostato la data e l'ora.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-110">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="ab9f5-111">Passare a un altro Wi-Fi o rete cellulare del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-111">Switch to a different Wi-Fi or cellular network on the device.</span></span>
    
- <span data-ttu-id="ab9f5-112">Per i dispositivi Android o iOS, disinstallare e reinstallare l'applicazione di portale della società Intune nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-112">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span>
    
## <a name="ios-phone-or-tablet"></a><span data-ttu-id="ab9f5-113">iOS cellulare o tablet</span><span class="sxs-lookup"><span data-stu-id="ab9f5-113">iOS phone or tablet</span></span>

- <span data-ttu-id="ab9f5-114">Assicurarsi di avere effettuato [l'impostazione di un certificato APNs](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).</span><span class="sxs-lookup"><span data-stu-id="ab9f5-114">Make sure that you've [set up an APNs certificate](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).</span></span>
    
- <span data-ttu-id="ab9f5-p103">Nella **sezione Impostazioni** \> **generali** \> **profilo** o **La gestione dei dispositivi**, verificare che un **Profilo di gestione** non sia già installato. Se si tratta, rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-p103">In **Settings** \> **General** \> **Profile** (or **Device Management**), make sure that a **Management Profile** is not already installed. If it is, remove it.</span></span> 
    
- <span data-ttu-id="ab9f5-117">Se viene visualizzato il messaggio di errore "Dispositivo non è riuscito a registrare," accedere a Office 365 e verificare che l'utente che ha eseguito l'accesso al dispositivo è stata assegnata una licenza che include Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-117">If you see the error message, "Device failed to enroll," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="ab9f5-118">Se viene visualizzato il messaggio di errore "Impossibile installare, i profili" provare a eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab9f5-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
  - <span data-ttu-id="ab9f5-119">Verificare che Safari viene impostato come predefinito sul dispositivo e che i cookie non siano disattivati.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
  - <span data-ttu-id="ab9f5-120">Riavviare il dispositivo, quindi passare a portal.manage.microsoft.com, accedere con l'ID utente di Office 365 e la password e tentare di installare manualmente il profilo.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-120">Reboot the device, then navigate to portal.manage.microsoft.com, sign in with your Office 365 user ID and password, and attempt to install the profile manually.</span></span>
    
## <a name="windows-rt-tablet"></a><span data-ttu-id="ab9f5-121">Tablet Windows RT</span><span class="sxs-lookup"><span data-stu-id="ab9f5-121">Windows RT tablet</span></span>

- <span data-ttu-id="ab9f5-122">Verificare che il dominio sia stato [impostato in Office 365 per l'utilizzo con MDM](set-up-mobile-device-management.md).</span><span class="sxs-lookup"><span data-stu-id="ab9f5-122">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="ab9f5-123">Verificare che l'utente viene scelta **Turn On** anziché scelta di **partecipare**.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-123">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>
    
## <a name="windows-phone"></a><span data-ttu-id="ab9f5-124">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="ab9f5-124">Windows Phone</span></span>

- <span data-ttu-id="ab9f5-125">Verificare che il dominio sia stato [impostato in Office 365 per l'utilizzo con MDM](set-up-mobile-device-management.md).</span><span class="sxs-lookup"><span data-stu-id="ab9f5-125">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="ab9f5-126">Verificare che il dispositivo è in esecuzione Windows 8.1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-126">Make sure the device is running Windows 8.1 or later.</span></span>
    
## <a name="android-phone-or-tablet"></a><span data-ttu-id="ab9f5-127">Android cellulare o tablet</span><span class="sxs-lookup"><span data-stu-id="ab9f5-127">Android phone or tablet</span></span>

- <span data-ttu-id="ab9f5-128">Verificare che il dispositivo esegue Android 4.0 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-128">Make sure the device is running Android 4.0 or later.</span></span>
    
- <span data-ttu-id="ab9f5-129">Se viene visualizzato il messaggio di errore "È non è possibile registrare il dispositivo" Accedi a Office 365 e verificare che l'utente che ha eseguito l'accesso al dispositivo è stata assegnata una licenza che include Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-129">If you see the error message, "We couldn't enroll this device," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="ab9f5-130">Selezionare l' **Area di notifica** del dispositivo per verificare se eventuali azioni richiesti per gli utenti sono in sospeso e in caso affermativo, eseguire le operazioni.</span><span class="sxs-lookup"><span data-stu-id="ab9f5-130">Check the **Notification Area** on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span> 
    

