---
title: Creare un certificato APNs per i dispositivi iOS
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: Per gestire i dispositivi iOS come iPad e iPhone in gestione dispositivi mobili per Office 365, eseguire la procedura seguente per creare un certificato di APNs.
ms.openlocfilehash: 5f82690f0add5f1aae95a089d9cdfc0b320ae596
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220456"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Creare un certificato APNs per i dispositivi iOS

 Per gestire i dispositivi iOS come iPad e iPhone in gestione dispositivi mobili per Office 365 è necessario creare un certificato di APNs. 
  
A tale scopo, seguire i passaggi del collegamento **set up** nella pagina del portale. (Andare a **Security &amp; Compliance Center** \> **Security Policies** \> **gestione** \> dispositivi **gestire le impostazioni**).
  
![Configurare i passaggi necessari e consigliati per la gestione dei dispositivi mobili](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. Accanto a **Configure a APNs certificate for iOS Devices**, selezionare **set up**.
    
2. Selezionare **Scarica il file CSR** e salvare la richiesta di firma del certificato in un punto qualsiasi del computer che si ricorderà. 
    
    ![Finestra di dialogo Installa certificato APN](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. Selezionare **Avanti**.
    
4. Creare un certificato APN.
    
  - Selezionare il **portale Apple APNs** per aprire il portale Apple Push Certificates. 
    
    ![Installare la finestra di dialogo CERT notifica APN con il portale di APNS Apple selezionato](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Accedere con un ID Apple.
    
    > [!IMPORTANT]
    > Utilizzare un ID Apple aziendale associato a un account di posta elettronica che rimarrà nell'organizzazione anche se l'utente che gestisce l'account parte. Salvare questo ID perché è necessario utilizzare lo stesso ID quando è il momento di rinnovare il certificato. 
  
  - Selezionare **Create a certificate** e accettate le condizioni per l' **utilizzo**.
    
  - **Passare** alla richiesta di firma del certificato scaricata nel computer da Office 365 e selezionare **carica**.
    
  - **Scaricare** il certificato APN creato dal portale Apple Push certificate nel computer in uso. 
    
    > [!TIP]
    > Se si verificano problemi durante il download del certificato, aggiornare il browser. 
  
5. Tornare a Office 365 e selezionare **Avanti** per accedere alla pagina **carica APNs certificate** . 
    
6. Passare al certificato APN scaricato dal portale Apple Push Certificates.
    
    ![Fare clic sul pulsante Sfoglia per selezionare APNS Cert scaricato da Apple](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. Selezionare **fine**.
    
Tornare a **Security &amp; Compliance Center** \> **Security Policies** \> **gestione** \> dispositivi **gestire le impostazioni** per completare l'installazione. 
  

