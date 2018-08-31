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
# <a name="overview-of-mobile-device-management-mdm-for-office-365"></a>Panoramica della gestione dei dispositivi mobili (MDM) per Office 365

È possibile gestire e proteggere i dispositivi mobili sono connessi alla propria organizzazione Office 365 mediante l'utilizzo di gestione dei dispositivi mobili per Office 365. I dispositivi mobili quali Smartphone e Tablet che consentono di accedere a posta elettronica ufficio, calendario, contatti e documenti riprodurre gran parte da eseguire per verificare che i dipendenti per lavorare in qualsiasi momento, da qualsiasi posizione. In modo da essere critico consentono di proteggere le informazioni dell'organizzazione in cui si utilizzano dispositivi. È possibile utilizzare MDM per Office 365 per impostare la sicurezza dei dispositivi regole criteri e l'accesso e se si sta perduti o rubati a comparsa da dispositivi mobili.
  
![MDM sul telefono Android](media/69b9a9f6-13ac-4e36-99ca-95e82e0375aa.png)
  
## <a name="what-types-of-devices-can-you-manage"></a>Quali tipi di dispositivi è possibile gestire?

È possibile utilizzare MDM per Office 365 per gestire diversi tipi di dispositivi mobili come Windows Phone, Android, iPhone e iPad. Per gestire i dispositivi mobili utilizzati dagli utenti nell'organizzazione, ogni utente deve disporre di una licenza di Office 365 applicabile e i dispositivi devono essere iscritti MDM per Office 365. 
  
Per visualizzare elementi supportati per ogni tipo di dispositivo MDM per Office 365, vedere [Funzionalità di gestione dei dispositivi mobili per Office 365](capabilities-of-mobile-device-management.md).
  
## <a name="setup-steps-for-mdm"></a>Procedura di configurazione per MDM

Un amministratore globale di Office 365 è necessario completare la procedura seguente per attivare e configurare MDM per Office 365. Seguire le istruzioni nell'argomento [impostazione MDM per Office 365](set-up-mobile-device-management.md) per visualizzare la procedura dettagliata. Di seguito è riportato un riepilogo rapido: 
  
> Passaggio 1: Attivare MDM per Office 365 seguendo i passaggi descritti in [Set up Mobile Device Management (MDM) in Office 365](set-up-mobile-device-management.md).
    
> Passaggio 2: Impostare MDM per Office 365, ad esempio, creare un certificato APNs per la gestione dei dispositivi iOS e aggiungere un record di sistema DNS (Domain Name) per il dominio per il supporto di Windows Phone.
    
> Passaggio 3: Creare i criteri dei dispositivi e applicarle a gruppi di utenti. A tale scopo, gli utenti riceveranno un [messaggio di registrazione nel dispositivo](enroll-your-mobile-device.md). E, quando è una volta completata la registrazione, i dispositivi saranno limitati dai criteri di che impostare le relative.
    
    ![Creating an MDN device policy under Device security policies](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
## <a name="device-management-tasks"></a>Attività di gestione di dispositivi

Dopo aver ottenuto MDM per configurare Office 365 e gli utenti sono registrati i dispositivi, è possibile gestire i dispositivi, bloccare l'accesso o cancellazione di un dispositivo, se necessario. Ulteriori informazioni su [alcune attività di gestione dei dispositivi comuni](manage-devices-in-mdm.md), tra cui la posizione in cui eseguire le attività.
  
## <a name="other-ways-to-manage-devices-and-apps"></a>Altri modi per gestire i dispositivi e applicazioni

Se è necessario maggiori funzionalità rispetto MDM per Office 365 include, estrarre il [confronto delle funzionalità MDM e Microsoft Intune](choose-between-mdm-and-intune.md) per verificare se una sottoscrizione Intune potrebbe soddisfare le esigenze dell'organizzazione. 
  
Se è necessario Gestione applicazioni per dispositivi mobili (MAM), ad esempio per gli utenti di aggiornamento dei progetti di lavoro nei propri dispositivi Intune è disponibile un'altra opzione oltre la registrazione e gestione di dispositivi. Una sottoscrizione Intune consente di impostare i criteri MAM tramite il portale di Azure, anche se i dispositivi di utenti non vengono iscritti Intune. Vedere [Protect app dati tramite i criteri per MAM](https://go.microsoft.com/fwlink/?LinkId=825439). 
  
## <a name="see-also"></a>Vedere anche

[Ottenere informazioni dettagliate sui dispositivi gestiti da MDM](get-details-about-mdm-managed-devices.md)

[Configurazione di MDM per Office 365](set-up-mobile-device-management.md)
  
[Registrare i dispositivi mobili in MDM](enroll-your-mobile-device.md)
  
[Gestire i dispositivi iscritti MDM](manage-devices-in-mdm.md)

