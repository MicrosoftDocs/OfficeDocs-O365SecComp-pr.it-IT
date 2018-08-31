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
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a>Risoluzione dei problemi di registrazione dei dispositivi con MDM per Office 365

Se si esegue problemi quando si tenta di registrare un dispositivo Mobile Device Management (MDM) per Office 365, eseguire i passaggi elencati di seguito per individuare il problema. Se i passaggi generali non risolve il problema, vedere una delle sezioni successive con passaggi specifici per il tipo di dispositivo.
  
## <a name="steps-to-try-first"></a>Procedure da seguire prima

Per iniziare, verificare quanto segue:
  
- Verificare che il dispositivo non è già registrato con un altro provider di gestione di dispositivi mobili, ad esempio Intune.
    
- Verificare che il dispositivo sia impostato la data e l'ora.
    
- Passare a un altro Wi-Fi o rete cellulare del dispositivo.
    
- Per i dispositivi Android o iOS, disinstallare e reinstallare l'applicazione di portale della società Intune nel dispositivo.
    
## <a name="ios-phone-or-tablet"></a>iOS cellulare o tablet

- Assicurarsi di avere effettuato [l'impostazione di un certificato APNs](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).
    
- Nella **sezione Impostazioni** \> **generali** \> **profilo** o **La gestione dei dispositivi**, verificare che un **Profilo di gestione** non sia già installato. Se si tratta, rimuoverlo. 
    
- Se viene visualizzato il messaggio di errore "Dispositivo non è riuscito a registrare," accedere a Office 365 e verificare che l'utente che ha eseguito l'accesso al dispositivo è stata assegnata una licenza che include Exchange Online.
    
- Se viene visualizzato il messaggio di errore "Impossibile installare, i profili" provare a eseguire una delle operazioni seguenti:
    
  - Verificare che Safari viene impostato come predefinito sul dispositivo e che i cookie non siano disattivati.
    
  - Riavviare il dispositivo, quindi passare a portal.manage.microsoft.com, accedere con l'ID utente di Office 365 e la password e tentare di installare manualmente il profilo.
    
## <a name="windows-rt-tablet"></a>Tablet Windows RT

- Verificare che il dominio sia stato [impostato in Office 365 per l'utilizzo con MDM](set-up-mobile-device-management.md).
    
- Verificare che l'utente viene scelta **Turn On** anziché scelta di **partecipare**.
    
## <a name="windows-phone"></a>Windows Phone

- Verificare che il dominio sia stato [impostato in Office 365 per l'utilizzo con MDM](set-up-mobile-device-management.md).
    
- Verificare che il dispositivo è in esecuzione Windows 8.1 o versioni successive.
    
## <a name="android-phone-or-tablet"></a>Android cellulare o tablet

- Verificare che il dispositivo esegue Android 4.0 o versioni successive.
    
- Se viene visualizzato il messaggio di errore "È non è possibile registrare il dispositivo" Accedi a Office 365 e verificare che l'utente che ha eseguito l'accesso al dispositivo è stata assegnata una licenza che include Exchange Online.
    
- Selezionare l' **Area di notifica** del dispositivo per verificare se eventuali azioni richiesti per gli utenti sono in sospeso e in caso affermativo, eseguire le operazioni. 
    

