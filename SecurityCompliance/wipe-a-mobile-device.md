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
# <a name="wipe-a-mobile-device-in-office-365"></a>A comparsa da un dispositivo mobile in Office 365
  
È possibile utilizzare Gestione predefinito per dispositivi mobili per Office 365 per eseguire una cancellazione selettiva per rimuovere solo le informazioni dell'organizzazione o una cancellazione completa per eliminare tutte le informazioni da un dispositivo mobile e ripristinare le impostazioni predefinite.
  
## <a name="what-to-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

- I dispositivi mobili possono archiviare informazioni riservate dell'organizzazione e consentire l'accesso a risorse di Office 365 dell'organizzazione. Per proteggere le informazioni dell'organizzazione, è possibile eseguire una cancellazione completa o una cancellazione selettiva:
    
  - **Cancellazione completa**: consente di eliminare tutti i dati nel dispositivo mobile dell'utente, incluse le applicazioni installate, le foto e informazioni personali. Una volta completata la cancellazione, il dispositivo viene ripristinato le impostazioni predefinite. 
    
  - **A comparsa da selettiva**: rimuove solo dati aziendali e le applicazioni installate ha lasciato, foto e informazioni personali nel dispositivo mobile dell'utente. 
    
- Quando un dispositivo viene cancellato (cancellazione completa o cancellazione selettiva), il dispositivo viene rimosso dall'elenco dei dispositivi gestiti.
    
- È possibile impostare il criterio di gestione un dispositivo mobile che verrà annullata automaticamente (cancellazione completa) un dispositivo dopo che l'utente non riesce a immettere la password del dispositivo un determinato numero di volte. Seguire i passaggi descritti in [creazione e la distribuzione di criteri di protezione dispositivo](create-device-security-policies.md).
    
- Se si desidera conoscere quali un utente rileveranno quando si annulla il dispositivo, vedere [Qual è l'impatto utente e dei dispositivi?](wipe-a-mobile-device.md#BKMK_Impact).
    
## <a name="wipe-a-mobile-device"></a>Cancellazione di un dispositivo mobile

1. Visitare il [ ![fare clic qui per visualizzare l'interfaccia di amministrazione di Office 365.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

2. Accedere a [accedere a Office 365 Security &amp; centro conformità](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) \> **prevenzione della perdita di dati** \> **la gestione dei dispositivi**.
    
3. Selezionare il dispositivo che si desidera cancellare i dati.
    
4. Selezionare il tipo di cancellazione remota da eseguire.
    
  - Per eseguire una cancellazione selettiva ed eliminare solo Office 365 informazioni sull'organizzazione, nel riquadro destro selezionare **selettiva cancellare i dati**.
    
  - Per eseguire una cancellazione completa e il ripristino del dispositivo per le impostazioni predefinite, nel riquadro destro selezionare **cancellazione completa**.
    
![Selezionare un dispositivo e quindi scegliere il tipo di cancellazione da eseguire.](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. Selezionare **Sì** per confermare. 
    
Fino al termine della transizione, come **RetirePending** o **RetireIssued**verranno visualizzati lo **stato del dispositivo** .
  
### <a name="how-do-i-know-it-worked"></a>Come sapere se che ha avuto esito positivo?

Non è più vedremo il dispositivo mobile nell'elenco dei dispositivi gestiti.
  
## <a name="why-would-you-want-to-wipe-a-device"></a>Il motivo per cui si desidera cancellare dati da un dispositivo?

Sono diversi i motivi per la cancellazione di dispositivi:
  
- Dispositivi mobili quali Smartphone e Tablet sono sempre più completa sempre. Ciò rende più semplice per gli utenti archiviare le informazioni aziendali riservate (ad esempio, l'identificazione personale o comunicazioni riservate) e accedervi in viaggio. Se uno di questi dispositivi mobili è perduto o rubato, la cancellazione del dispositivo immediatamente consentono di prevenire le informazioni dell'organizzazione da arrivare malintenzionati.
    
- Quando un utente lascia l'organizzazione a un dispositivo personale che partecipano MDM per Office 365, è possibile evitare informazioni sull'organizzazione da seguendo quell'utente eseguendo una cancellazione selettiva.
    
- Se l'organizzazione fornisce i dispositivi mobili per gli utenti, potrebbe essere necessario riassegnare dispositivi nel tempo. Eseguire una cancellazione completa su un dispositivo prima di assegnare a un nuovo consente di utente assicura che le informazioni riservate dal proprietario precedente viene eliminate.
    
## <a name="whats-the-user-and-device-impact"></a>Che cos'è l'utente e l'impatto di dispositivo?

La cancellazione viene inviata immediatamente al dispositivo mobile. Il dispositivo viene inoltre contrassegnato come non in AAD.
  
Nella tabella seguente vengono descritti il contenuto viene rimossa per ogni tipo di dispositivo quando in modo selettivo svuotare o meno un dispositivo.
  
|**Impatto del contenuto**|**Windows Phone 8.1**|**iOS 7.1+**|**Android 4+**|
|:-----|:-----|:-----|:-----|
|Società portale app\* viene disinstallato.  <br/> |N/D  <br/> |✔  <br/> |N/D  <br/> |
|Dati di app di Office 365 ospitati da applicazioni in cui il controllo di accesso è supportato da MDM per Office 365 viene rimosso (attualmente Outlook e OneDrive for Business). Le applicazioni non vengono rimossi.  <br/> Outlook per Android non vengono rimossi i messaggi di posta elettronica memorizzati nella cache.  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Impostazioni dei criteri che sono state applicate dal MDM per Office 365 per i dispositivi non è più vengono applicate nel dispositivo e gli utenti possono modificare le impostazioni.  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Vengono rimossi i profili di posta elettronica creati da MDM per Office 365 e posta elettronica memorizzati nella cache nel dispositivo viene eliminato.  <br/> |N/D  <br/> |✔  <br/> |N/D  <br/> |
   
> [!NOTE]
> \*App portale aziendale è disponibile nell'archivio App di iOS e l'archivio di riprodurre per i dispositivi Android. 
  
## <a name="related-content"></a>Contenuto correlato

[Gestione dei dispositivi mobili in Office 365](set-up-mobile-device-management.md)
  

