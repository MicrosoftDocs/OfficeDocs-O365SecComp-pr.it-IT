---
title: Sostituire Office 365 messaggio crittografia Visualizzatore App
ms.author: krowley
author: kccross
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
description: In 15 agosto 2018, si intende rimuovere l'applicazione mobile Visualizzatore Office 365 messaggio crittografia dall'archivi Android e Apple. L'applicazione mobile di Office 365 Message Encryption Viewer era necessario per leggere i messaggi di posta elettronica e allegati che sono stati crittografati con la versione precedente di OME Apple e telefoni Android. Oltre a rimuovere l'app OME visualizzatore, non siamo in tutte le altre modifiche alla versione precedente di OME.
ms.openlocfilehash: 43e514bd8336d283aaf774ffa4f49565f86e7102
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530202"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a>Sostituire Office 365 messaggio crittografia Visualizzatore App

In 15 agosto 2018, si intende rimuovere l'applicazione mobile Visualizzatore Office 365 messaggio crittografia dall'archivi Android e Apple. L'applicazione mobile di Office 365 Message Encryption Viewer era necessario per leggere i messaggi di posta elettronica e allegati che sono stati crittografati con la versione precedente di OME Apple e telefoni Android. Oltre a rimuovere l'app OME visualizzatore, non siamo in tutte le altre modifiche alla versione precedente di OME.
  
## <a name="changes-beginning-august-2018"></a>Modifiche iniziano 2018 agosto

Come annunciato settembre ultimo, è stato rilasciato una nuova versione di [Office 365 Message Encryption](https://aka.ms/ome2017) in modo che gli utenti possono inviare crittografati e protetti i messaggi a tutti gli utenti interni o esterni all'organizzazione senza la necessità di app per dispositivi mobili. In seguito, sono state aggiunte funzionalità aggiuntive: 
  
- [Modello di crittografare sola](https://aka.ms/encryptonly)
    
- [Controllo per decrittografare gli allegati](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
Con questa modifica, gli utenti non sono più saranno in grado di scaricare l'app per dispositivi mobili di Office 365 Message Encryption Viewer iniziano 1 agosto. Di conseguenza, i destinatari della posta potrebbero non essere in grado di leggere i messaggi crittografati con la versione precedente di OME in alcuni dispositivi mobili Android e Apple. Tuttavia, ancora saranno in grado di leggere i messaggi personal computer (tramite browser desktop). Gli utenti che già stato scaricato l'app continuerà a essere in grado di accedervi.
  
## <a name="why-this-change-was-made"></a>Il motivo per cui è stata effettuata la modifica

La nuova versione OME non richiede un'app per dispositivi mobili per leggere i messaggi di posta elettronica protetta e gli allegati. I clienti di Office 365 utilizzando OME nuove funzionalità possono visualizzare il messaggio protetto in Outlook mobile e i clienti non Office 365 possono visualizzare protetti i messaggi in un browser.
  
Richiedere agli utenti di scaricare un'applicazione per dispositivi mobili è un altro ostacolo per i clienti visualizzare i messaggi protetti. Le nuove funzionalità di Office 365 Message Encryption offrono un'esperienza migliore per dispositivi mobili.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>È possibile utilizzare la versione precedente di Office 365 Message Encryption

La versione precedente di Office 365 Message Encryption non essere deprecata in questa fase, tuttavia, è stata introdotta miglioramenti significativi rispetto alla nuova versione di Office 365 Message Encryption, che rendono più semplice crittografare i diritti e proteggere dati riservati a tutti gli utenti e su qualsiasi dispositivo - inclusa la possibilità per gli utenti di Office 365 leggere i messaggi protetti direttamente in Outlook (desktop, mobile e web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Che cosa è necessario eseguire per preparare la modifica

Se l'organizzazione invia attualmente crittografati allegati ai destinatari che richiedono l'app OME Viewer, è necessario aggiornare la documentazione e risorse di formazione.
  
È consigliabile aggiornare esistente regole del flusso di posta elettronica di Exchange per utilizzare la versione corrente di OME in modo che l'organizzazione può usufruire delle funzionalità nuove e migliorate. Una volta impostate le nuove funzionalità OME, i destinatari non sarà necessaria l'app OME visualizzatore per leggere messaggi crittografati nei dispositivi mobili.
  
Microsoft consiglia che si intende spostare le nuove funzionalità OME non appena è ragionevole per l'organizzazione. Per ulteriori informazioni, vedere [impostare le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md). Se si desidera trovare ulteriori informazioni sul funzionamento innanzitutto le nuove funzionalità, vedere [Office 365 Message Encryption](ome.md).
  

