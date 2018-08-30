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
# <a name="create-an-apns-certificate-for-ios-devices"></a>Creare un certificato APNs per i dispositivi iOS

 Per gestire i dispositivi iOS come nella gestione del dispositivo Mobile iPhone e iPad per Office 365 è necessario creare un certificato APNs. 
  
A tale scopo, eseguire la procedura dal collegamento **configurare** nella pagina del portale. (Passare a **protezione &amp; centro conformità** \> **criteri di protezione** \> **Device management** \> **Gestisci impostazioni del**.)
  
![Configurare la gestione di dispositivi mobili necessari e dei passaggi consigliati](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. Accanto a **Configura un certificato APNs per i dispositivi iOS**, selezionare **l'impostazione**.
    
2. Selezionare **Scarica i file CSR** e salvare la richiesta di firma del certificato in un punto nel computer da ricordare. 
    
    ![Finestra di dialogo certificato punto di installazione](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. Selezionare **Avanti**.
    
4. Creare un certificato punto.
    
  - Selezionare **Apple APNS Portal** per aprire il portale dei certificati Push di Apple. 
    
    ![Installare finestra di dialogo di notifica punto cert con Apple APNS portale selezionato](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Accedere con un ID di Apple.
    
    > [!IMPORTANT]
    > Utilizzare una società che Apple ID associato a un account di posta elettronica che rimarrà con l'organizzazione anche se l'utente che gestisce l'account non. Salvare questo ID perché è necessario utilizzare lo stesso ID al momento rinnovare il certificato. 
  
  - Selezionare **Crea un certificato** e accettare le **Condizioni per l'utilizzo**.
    
  - **Passare** la richiesta di firma del certificato è stato scaricato nel computer di Office 365 e selezionare **Carica**.
    
  - **Scaricare** il certificato punto creato per il portale certificato Push Apple per il computer. 
    
    > [!TIP]
    > Se si riscontrano problemi con il download del certificato, aggiornare il browser. 
  
5. Tornare a Office 365 e selezionare **Avanti** per accedere alla pagina **APNS caricare certificati** . 
    
6. Selezionare il certificato punto che è stato scaricato dal portale di certificati Push di Apple.
    
    ![Fare clic sul pulsante Sfoglia per selezionare cert APNS scaricati da Apple](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. Selezionare **Fine**.
    
Tornare al **protezione &amp; centro conformità** \> **criteri di protezione** \> **Device management** \> **Gestisci impostazioni** per completare l'installazione. 
  

