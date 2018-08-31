---
title: A comparsa da un dispositivo mobile in Office 365
ms.author: dianef
author: dianef77
manager: scotv
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_WipeDevice
- O365E_WipeDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 9d727c7d-8b47-4499-bf24-d046b449214c
description: È possibile utilizzare Gestione predefinito per dispositivi mobili per Office 365 per eseguire una cancellazione selettiva per rimuovere solo le informazioni dell'organizzazione o una cancellazione completa per eliminare tutte le informazioni da un dispositivo mobile e ripristinare le impostazioni predefinite.
ms.openlocfilehash: d3eb28575924ca3bb4a647ae9af2f96b55116a53
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272501"
---
# <a name="wipe-a-mobile-device-in-office-365"></a><span data-ttu-id="4ef28-103">A comparsa da un dispositivo mobile in Office 365</span><span class="sxs-lookup"><span data-stu-id="4ef28-103">Wipe a mobile device in Office 365</span></span>
  
<span data-ttu-id="4ef28-104">È possibile utilizzare Gestione predefinito per dispositivi mobili per Office 365 per eseguire una cancellazione selettiva per rimuovere solo le informazioni dell'organizzazione o una cancellazione completa per eliminare tutte le informazioni da un dispositivo mobile e ripristinare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="4ef28-104">You can use built-in mobile device management for Office 365 to do a selective wipe to remove only organizational information, or a full wipe to delete all information from a mobile device and restore it to its factory settings.</span></span>
  
## <a name="what-to-know-before-you-begin"></a><span data-ttu-id="4ef28-105">Cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4ef28-105">What to know before you begin</span></span>

- <span data-ttu-id="4ef28-p101">I dispositivi mobili possono archiviare informazioni riservate dell'organizzazione e consentire l'accesso a risorse di Office 365 dell'organizzazione. Per proteggere le informazioni dell'organizzazione, è possibile eseguire una cancellazione completa o una cancellazione selettiva:</span><span class="sxs-lookup"><span data-stu-id="4ef28-p101">Mobile devices can store sensitive organizational information and provide access to your organization's Office 365 resources. To help protect your organization's information, you can do a full wipe or a selective wipe:</span></span>
    
  - <span data-ttu-id="4ef28-p102">**Cancellazione completa**: consente di eliminare tutti i dati nel dispositivo mobile dell'utente, incluse le applicazioni installate, le foto e informazioni personali. Una volta completata la cancellazione, il dispositivo viene ripristinato le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="4ef28-p102">**Full wipe**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information. When the wipe is complete, the device is restored to its factory settings.</span></span> 
    
  - <span data-ttu-id="4ef28-110">**A comparsa da selettiva**: rimuove solo dati aziendali e le applicazioni installate ha lasciato, foto e informazioni personali nel dispositivo mobile dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4ef28-110">**Selective wipe**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span> 
    
- <span data-ttu-id="4ef28-111">Quando un dispositivo viene cancellato (cancellazione completa o cancellazione selettiva), il dispositivo viene rimosso dall'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="4ef28-111">When a device is wiped (full wipe or selective wipe), the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="4ef28-p103">È possibile impostare il criterio di gestione un dispositivo mobile che verrà annullata automaticamente (cancellazione completa) un dispositivo dopo che l'utente non riesce a immettere la password del dispositivo un determinato numero di volte. Seguire i passaggi descritti in [creazione e la distribuzione di criteri di protezione dispositivo](create-device-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4ef28-p103">You can set up a mobile device management policy that automatically wipes (full wipe) a device after the user unsuccessfully tries to enter the device's password a specific number of times. Follow the steps in [Create and deploy device security policies](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="4ef28-114">Se si desidera conoscere quali un utente rileveranno quando si annulla il dispositivo, vedere [Qual è l'impatto utente e dei dispositivi?](wipe-a-mobile-device.md#BKMK_Impact).</span><span class="sxs-lookup"><span data-stu-id="4ef28-114">If you want to know what a user will experience when you wipe their device, see [What's the user and device impact?](wipe-a-mobile-device.md#BKMK_Impact).</span></span>
    
## <a name="wipe-a-mobile-device"></a><span data-ttu-id="4ef28-115">Cancellazione di un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="4ef28-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="4ef28-116">Visitare il [ ![fare clic qui per visualizzare l'interfaccia di amministrazione di Office 365.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="4ef28-116">Go to the [![Click here to go to the Office 365 admin center.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="4ef28-117">Accedere a [accedere a Office 365 Security &amp; centro conformità](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) \> **prevenzione della perdita di dati** \> **la gestione dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="4ef28-117">Go to [Go to the Office 365 Security &amp; Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **Data loss prevention** \> **Device management**.</span></span>
    
3. <span data-ttu-id="4ef28-118">Selezionare il dispositivo che si desidera cancellare i dati.</span><span class="sxs-lookup"><span data-stu-id="4ef28-118">Select the device you want to wipe.</span></span>
    
4. <span data-ttu-id="4ef28-119">Selezionare il tipo di cancellazione remota da eseguire.</span><span class="sxs-lookup"><span data-stu-id="4ef28-119">Select the type of remote wipe you want to do.</span></span>
    
  - <span data-ttu-id="4ef28-120">Per eseguire una cancellazione selettiva ed eliminare solo Office 365 informazioni sull'organizzazione, nel riquadro destro selezionare **selettiva cancellare i dati**.</span><span class="sxs-lookup"><span data-stu-id="4ef28-120">To do a selective wipe and delete only Office 365 organization information, in the right pane, select **Selective wipe**.</span></span>
    
  - <span data-ttu-id="4ef28-121">Per eseguire una cancellazione completa e il ripristino del dispositivo per le impostazioni predefinite, nel riquadro destro selezionare **cancellazione completa**.</span><span class="sxs-lookup"><span data-stu-id="4ef28-121">To do a full wipe and restore the device to its factory settings, in the right pane, select **Full wipe**.</span></span>
    
![Selezionare un dispositivo e quindi scegliere il tipo di cancellazione da eseguire.](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. <span data-ttu-id="4ef28-123">Selezionare **Sì** per confermare.</span><span class="sxs-lookup"><span data-stu-id="4ef28-123">Select **Yes** to confirm.</span></span> 
    
<span data-ttu-id="4ef28-124">Fino al termine della transizione, come **RetirePending** o **RetireIssued**verranno visualizzati lo **stato del dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="4ef28-124">Until the wipe finishes, the **Device status** will show as **RetirePending** or **RetireIssued**.</span></span>
  
### <a name="how-do-i-know-it-worked"></a><span data-ttu-id="4ef28-125">Come sapere se che ha avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="4ef28-125">How do I know it worked?</span></span>

<span data-ttu-id="4ef28-126">Non è più vedremo il dispositivo mobile nell'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="4ef28-126">You'll no longer see the mobile device in the list of managed devices.</span></span>
  
## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="4ef28-127">Il motivo per cui si desidera cancellare dati da un dispositivo?</span><span class="sxs-lookup"><span data-stu-id="4ef28-127">Why would you want to wipe a device?</span></span>

<span data-ttu-id="4ef28-128">Sono diversi i motivi per la cancellazione di dispositivi:</span><span class="sxs-lookup"><span data-stu-id="4ef28-128">There are several reasons for wiping devices:</span></span>
  
- <span data-ttu-id="4ef28-p104">Dispositivi mobili quali Smartphone e Tablet sono sempre più completa sempre. Ciò rende più semplice per gli utenti archiviare le informazioni aziendali riservate (ad esempio, l'identificazione personale o comunicazioni riservate) e accedervi in viaggio. Se uno di questi dispositivi mobili è perduto o rubato, la cancellazione del dispositivo immediatamente consentono di prevenire le informazioni dell'organizzazione da arrivare malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="4ef28-p104">Mobile devices like smartphones and tablets are becoming more full-featured all the time. This means it's easier for your users to store sensitive corporate information (such as personal identification or confidential communications) and access it on the go. If one of these mobile devices is lost or stolen, wiping the device immediately can help prevent your organization's information from ending up in the wrong hands.</span></span>
    
- <span data-ttu-id="4ef28-132">Quando un utente lascia l'organizzazione a un dispositivo personale che partecipano MDM per Office 365, è possibile evitare informazioni sull'organizzazione da seguendo quell'utente eseguendo una cancellazione selettiva.</span><span class="sxs-lookup"><span data-stu-id="4ef28-132">When a user leaves the organization with a personal device that is enrolled in MDM for Office 365, you can help prevent organizational information from going with that user by doing a selective wipe.</span></span>
    
- <span data-ttu-id="4ef28-p105">Se l'organizzazione fornisce i dispositivi mobili per gli utenti, potrebbe essere necessario riassegnare dispositivi nel tempo. Eseguire una cancellazione completa su un dispositivo prima di assegnare a un nuovo consente di utente assicura che le informazioni riservate dal proprietario precedente viene eliminate.</span><span class="sxs-lookup"><span data-stu-id="4ef28-p105">If your organization provides mobile devices to users, you might need to reassign devices from time to time. Doing a full wipe on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>
    
## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="4ef28-135">Che cos'è l'utente e l'impatto di dispositivo?</span><span class="sxs-lookup"><span data-stu-id="4ef28-135">What's the user and device impact?</span></span>

<span data-ttu-id="4ef28-p106">La cancellazione viene inviata immediatamente al dispositivo mobile. Il dispositivo viene inoltre contrassegnato come non in AAD.</span><span class="sxs-lookup"><span data-stu-id="4ef28-p106">The wipe is sent immediately to the mobile device. The device is also marked as not compliant in AAD.</span></span>
  
<span data-ttu-id="4ef28-138">Nella tabella seguente vengono descritti il contenuto viene rimossa per ogni tipo di dispositivo quando in modo selettivo svuotare o meno un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ef28-138">The following table describes what content is removed for each device type when a device is selectively wiped.</span></span>
  
|<span data-ttu-id="4ef28-139">**Impatto del contenuto**</span><span class="sxs-lookup"><span data-stu-id="4ef28-139">**Content impact**</span></span>|<span data-ttu-id="4ef28-140">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="4ef28-140">**Windows Phone 8.1**</span></span>|<span data-ttu-id="4ef28-141">**iOS 7.1+**</span><span class="sxs-lookup"><span data-stu-id="4ef28-141">**iOS 7.1+**</span></span>|<span data-ttu-id="4ef28-142">**Android 4+**</span><span class="sxs-lookup"><span data-stu-id="4ef28-142">**Android 4+**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ef28-143">Società portale app\* viene disinstallato.</span><span class="sxs-lookup"><span data-stu-id="4ef28-143">Company Portal app\* is uninstalled.</span></span>  <br/> |<span data-ttu-id="4ef28-144">N/D</span><span class="sxs-lookup"><span data-stu-id="4ef28-144">N/A</span></span>  <br/> |<span data-ttu-id="4ef28-145">✔</span><span class="sxs-lookup"><span data-stu-id="4ef28-145">✔</span></span>  <br/> |<span data-ttu-id="4ef28-146">N/D</span><span class="sxs-lookup"><span data-stu-id="4ef28-146">N/A</span></span>  <br/> |
|<span data-ttu-id="4ef28-p107">Dati di app di Office 365 ospitati da applicazioni in cui il controllo di accesso è supportato da MDM per Office 365 viene rimosso (attualmente Outlook e OneDrive for Business). Le applicazioni non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="4ef28-p107">Office 365 app data hosted by apps where access control is supported by MDM for Office 365 is removed (currently Outlook and OneDrive for Business). The apps are not removed.</span></span>  <br/> <span data-ttu-id="4ef28-149">Outlook per Android non vengono rimossi i messaggi di posta elettronica memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="4ef28-149">Outlook for Android does not remove cached emails.</span></span>  <br/> |<span data-ttu-id="4ef28-150">✔</span><span class="sxs-lookup"><span data-stu-id="4ef28-150">✔</span></span>  <br/> |<span data-ttu-id="4ef28-151">✔</span><span class="sxs-lookup"><span data-stu-id="4ef28-151">✔</span></span>  <br/> |<span data-ttu-id="4ef28-152">✔</span><span class="sxs-lookup"><span data-stu-id="4ef28-152">✔</span></span>  <br/> |
|<span data-ttu-id="4ef28-153">Impostazioni dei criteri che sono state applicate dal MDM per Office 365 per i dispositivi non è più vengono applicate nel dispositivo e gli utenti possono modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4ef28-153">Policy settings that were applied by MDM for Office 365 to devices are no longer enforced on the device and users can change the settings.</span></span>  <br/> |<span data-ttu-id="4ef28-154">✔</span><span class="sxs-lookup"><span data-stu-id="4ef28-154">✔</span></span>  <br/> |<span data-ttu-id="4ef28-155">✔</span><span class="sxs-lookup"><span data-stu-id="4ef28-155">✔</span></span>  <br/> |<span data-ttu-id="4ef28-156">✔</span><span class="sxs-lookup"><span data-stu-id="4ef28-156">✔</span></span>  <br/> |
|<span data-ttu-id="4ef28-157">Vengono rimossi i profili di posta elettronica creati da MDM per Office 365 e posta elettronica memorizzati nella cache nel dispositivo viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="4ef28-157">Email profiles created by MDM for Office 365 are removed and cached email on the device is deleted.</span></span>  <br/> |<span data-ttu-id="4ef28-158">N/D</span><span class="sxs-lookup"><span data-stu-id="4ef28-158">N/A</span></span>  <br/> |<span data-ttu-id="4ef28-159">✔</span><span class="sxs-lookup"><span data-stu-id="4ef28-159">✔</span></span>  <br/> |<span data-ttu-id="4ef28-160">N/D</span><span class="sxs-lookup"><span data-stu-id="4ef28-160">N/A</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="4ef28-161">\*App portale aziendale è disponibile nell'archivio App di iOS e l'archivio di riprodurre per i dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="4ef28-161">\* Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="4ef28-162">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="4ef28-162">Related content</span></span>

[<span data-ttu-id="4ef28-163">Gestione dei dispositivi mobili in Office 365</span><span class="sxs-lookup"><span data-stu-id="4ef28-163">Manage mobile devices in Office 365</span></span>](set-up-mobile-device-management.md)
  

