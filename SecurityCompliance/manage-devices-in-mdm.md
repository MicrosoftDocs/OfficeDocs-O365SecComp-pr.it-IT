---
title: Gestire i dispositivi iscritti a gestione dei dispositivi mobili in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 28dd276b-beeb-4c5b-8b22-7551186127fe
description: Eseguire la procedura seguente per impostare backup Mobile Device Management (MDM) in Office 365.
ms.openlocfilehash: 3a84b6904b866e07eb4efabe0f39041b282d0ba9
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272311"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-office-365"></a>Gestire i dispositivi iscritti a gestione dei dispositivi mobili in Office 365

La gestione dei dispositivi mobili incorporate per Office 365 consente di proteggere e gestire i dispositivi mobili degli utenti quali iPhone, iPad, Androids, e i telefoni Windows. Il primo passaggio consiste di accedere a Office 365 e [impostare MDM per Office 365](set-up-mobile-device-management.md). 
  
Dopo avere impostato verso l'alto, gli utenti nell'organizzazione è necessario [registrare i dispositivi](enroll-your-mobile-device.md) al servizio. Quindi è possibile utilizzare MDM per Office 365 per gestire i dispositivi nell'organizzazione. Ad esempio, è possibile utilizzare criteri di protezione di dispositivo per limitare l'accesso alla posta elettronica o altri servizi, visualizzare i report di dispositivi e la cancellazione remota di un dispositivo. Sarà in genere, andare al [accedere a Office 365 Security &amp; centro conformità](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) eseguire queste attività. 
  
## <a name="device-management-tasks"></a>Attività di gestione di dispositivi

Per ottenere al pannello di gestione di dispositivi, eseguire la procedura seguente. 
  
1. Passare all'interfaccia di amministrazione di Office 365.
    
2. Digitare gestione dei dispositivi mobili nel campo di ricerca e selezionare nell'elenco dei risultati della **Gestione dei dispositivi mobili** . 
    
    ![Tipo Mobile Device Manager nel campo di ricerca di Office 365](media/e2e2f1c0-e543-431a-959b-e26c2ba328a7.png)
  
Dopo aver ottenuto MDM per configurare Office 365, ecco come è possibile gestire i dispositivi mobili all'interno dell'organizzazione. 
  
|**Per…**|**Esegui questa operazione**|
|:-----|:-----|
|Cancellare un dispositivo  <br/> |Nel Pannello di gestione dei dispositivi, selezionare *nome del dispositivo* , quindi **cancellazione completa** per eliminare tutte le informazioni o **cancellare i dati selettiva** per eliminare solo le informazioni dell'organizzazione nel dispositivo.  <br/> [Cancellazione di un dispositivo in Office 365](wipe-a-mobile-device.md), vedere.  <br/> |
|Bloccare l'accesso dei dispositivi non supportati alla posta elettronica di Exchange tramite Exchange ActiveSync  <br/> |Nel Pannello di gestione dei dispositivi, selezionare **Blocca**.  <br/> |
|Configurare i criteri dei dispositivi come i requisiti delle password e le impostazioni di sicurezza  <br/> |Nel Pannello di gestione dei dispositivi, fare clic su \> **criteri di protezione dispositivo** \> **Aggiungi +**.  <br/> Vedere [creazione e la distribuzione di criteri di protezione dispositivo](create-device-security-policies.md).  <br/> |
|Visualizzare l'elenco dei dispositivi bloccati  <br/> |Nel Pannello di gestione dei dispositivi, in **Selezionare una visualizzazione** selezionare **bloccato**.  <br/> ||
|Sbloccare un dispositivo non conforme o non supportato per un utente o un gruppo di utenti  <br/> | È possibile sbloccare non Compatible dispositivi diversi modi in base alle esigenze. Selezionare una delle operazioni seguenti:<br/>  Rimuovere l'utente o gli utenti dal gruppo di protezione che è stato applicato il criterio. Accedere **all'interfaccia di amministrazione di Office 365** \> **gruppi**e quindi selezionare * Nome gruppo *. Fare clic su **Modifica i membri e gli amministratori**.<br/>  Rimuovere il gruppo di protezione, che gli utenti sono membri dal criterio dispositivi. Accedere a **protezione &amp; centro conformità** \> **criteri di protezione** \> **criteri di protezione dispositivo**. Selezionare * nome del criterio dispositivi *, quindi fare clic su **Modifica** ![sull'icona Modifica](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **distribuzione**.<br/>  Sbloccare tutti i dispositivi non Compatible per un criterio del dispositivo. Accedere a **protezione &amp; centro conformità** \> **criteri di protezione** \> **criteri di protezione dispositivo**. Selezionare *il nome di criterio dispositivo* e quindi fare clic su **Modifica** ![sull'icona Modifica](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **i requisiti di accesso**. Selezionare **Consenti violazione di accesso e report**.<br/>  Per sbloccare un dispositivo non conforme o non supportato per un utente o un gruppo di utenti, vedere la Go to **protezione &amp; centro conformità** \> **criteri di protezione** \> **Device management** \> **accesso dei dispositivi Gestisci impostazioni **. Aggiungere un gruppo di sicurezza con i membri che si desidera escludere dalla viene bloccato l'accesso a Office 365. Vedere [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).<br/> |
|Ottenere informazioni dettagliate sui dispositivi nell'organizzazione  <br/> |Per ottenere ulteriori informazioni, ad esempio quali dispositivi sono iscritti e conformi ai criteri di sicurezza dispositivo, eseguire la procedura descritta [nell'ottenere informazioni dettagliate sui dispositivi gestiti da MDM](get-details-about-mdm-managed-devices.md).  <br/> |
|Rimuovere gli utenti in modo che i dispositivi non è più gestiti da MDM  <br/> |Modificare il gruppo di sicurezza con criteri di gestione di dispositivi per MDM rimuovere l'utente. Vedere [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).<br/> Per rimuovere MDM da tutti gli utenti di Office 365, vedere [disattivare la gestione dei dispositivi mobili in Office 365](turn-off-mdm.md).  <br/> |
   

