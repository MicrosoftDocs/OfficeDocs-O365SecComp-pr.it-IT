---
title: Creare un certificato APNs per i dispositivi iOS
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: Per gestire i dispositivi iOS come nella gestione del dispositivo Mobile iPhone e iPad per Office 365, eseguire la procedura seguente per creare un certificato APNs.
ms.openlocfilehash: 28e8888d7dd57c3052cdcb5994725f11a5f0445f
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272051"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="91177-103">Creare un certificato APNs per i dispositivi iOS</span><span class="sxs-lookup"><span data-stu-id="91177-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="91177-104">Per gestire i dispositivi iOS come nella gestione del dispositivo Mobile iPhone e iPad per Office 365 è necessario creare un certificato APNs.</span><span class="sxs-lookup"><span data-stu-id="91177-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="91177-p101">A tale scopo, eseguire la procedura dal collegamento **configurare** nella pagina del portale. (Passare a **protezione &amp; centro conformità** \> **criteri di protezione** \> **Device management** \> **Gestisci impostazioni del**.)</span><span class="sxs-lookup"><span data-stu-id="91177-p101">To do this, follow the steps from the **Set up** link on the portal page. (Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![Configurare la gestione di dispositivi mobili necessari e dei passaggi consigliati](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="91177-108">Accanto a **Configura un certificato APNs per i dispositivi iOS**, selezionare **l'impostazione**.</span><span class="sxs-lookup"><span data-stu-id="91177-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="91177-109">Selezionare **Scarica i file CSR** e salvare la richiesta di firma del certificato in un punto nel computer da ricordare.</span><span class="sxs-lookup"><span data-stu-id="91177-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![Finestra di dialogo certificato punto di installazione](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="91177-111">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="91177-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="91177-112">Creare un certificato punto.</span><span class="sxs-lookup"><span data-stu-id="91177-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="91177-113">Selezionare **Apple APNS Portal** per aprire il portale dei certificati Push di Apple.</span><span class="sxs-lookup"><span data-stu-id="91177-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![Installare finestra di dialogo di notifica punto cert con Apple APNS portale selezionato](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="91177-115">Accedere con un ID di Apple.</span><span class="sxs-lookup"><span data-stu-id="91177-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="91177-p102">Utilizzare una società che Apple ID associato a un account di posta elettronica che rimarrà con l'organizzazione anche se l'utente che gestisce l'account non. Salvare questo ID perché è necessario utilizzare lo stesso ID al momento rinnovare il certificato.</span><span class="sxs-lookup"><span data-stu-id="91177-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="91177-118">Selezionare **Crea un certificato** e accettare le **Condizioni per l'utilizzo**.</span><span class="sxs-lookup"><span data-stu-id="91177-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="91177-119">**Passare** la richiesta di firma del certificato è stato scaricato nel computer di Office 365 e selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="91177-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="91177-120">**Scaricare** il certificato punto creato per il portale certificato Push Apple per il computer.</span><span class="sxs-lookup"><span data-stu-id="91177-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="91177-121">Se si riscontrano problemi con il download del certificato, aggiornare il browser.</span><span class="sxs-lookup"><span data-stu-id="91177-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="91177-122">Tornare a Office 365 e selezionare **Avanti** per accedere alla pagina **APNS caricare certificati** .</span><span class="sxs-lookup"><span data-stu-id="91177-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="91177-123">Selezionare il certificato punto che è stato scaricato dal portale di certificati Push di Apple.</span><span class="sxs-lookup"><span data-stu-id="91177-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![Fare clic sul pulsante Sfoglia per selezionare cert APNS scaricati da Apple](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="91177-125">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="91177-125">Select **Finish**.</span></span>
    
<span data-ttu-id="91177-126">Tornare al **protezione &amp; centro conformità** \> **criteri di protezione** \> **Device management** \> **Gestisci impostazioni** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="91177-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  

