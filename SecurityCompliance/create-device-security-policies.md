---
title: Creazione e distribuzione dei criteri di sicurezza del dispositivo
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/9/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewDevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: d310f556-8bfb-497b-9bd7-fe3c36ea2fd6
description: "Passaggi per creare e distribuire criteri di protezione per la gestione dei dispositivi mobili in Office 365 che consentono di proteggere le informazioni dell'organizzazione in Office 365 dall'accesso non autorizzato. "
ms.openlocfilehash: ab1fc1960a3e55eb3080dde7df0ec742c58b2cc7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272071"
---
# <a name="create-and-deploy-device-security-policies"></a>Creazione e distribuzione dei criteri di sicurezza del dispositivo

È possibile utilizzare la gestione dei dispositivi mobili per Office 365 per creare criteri di sicurezza che consentono di proteggere le informazioni dell'organizzazione in Office 365 dall'accesso non autorizzato. È possibile applicare criteri a qualsiasi dispositivo mobile all'interno dell'organizzazione in cui l'utente del dispositivo con una licenza di Office 365 applicabile e ha registrato il dispositivo in MDM per Office 365.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Informazioni sui dispositivi, dispositivo mobile App e le impostazioni di sicurezza che supporta MDM per Office 365. Vedere [funzionalità di gestione dei dispositivi mobili per Office 365](capabilities-of-mobile-device-management.md).
    
- Creare gruppi di sicurezza che includono utenti di Office 365 che si desidera distribuire i criteri per e per gli utenti che si desidera escludere dalla viene bloccato l'accesso a Office 365. È consigliabile prima di distribuire un nuovo criterio per l'organizzazione, testare i criteri per la distribuzione di un numero limitato di utenti. È possibile creare e utilizzare un gruppo di protezione che include solo se stessi o a un piccolo numero Office 365 gli utenti che è possono testare i criteri per la. Per ulteriori informazioni sui gruppi di protezione, vedere [creare, modificare o eliminare un gruppo di sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=518555).
    
- **Importante:** Prima di creare un criterio dispositivi mobili, è necessario attivare e configurare MDM per Office 365. Vedere [Panoramica di gestione dei dispositivi mobili per Office 365](overview-of-mdm.md).
    
- Per creare e distribuire criteri di gestione di dispositivi mobili in Office 365, è necessario essere un amministratore. globali di Office 365 Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1).
    
- Prima di distribuire i criteri, l'organizzazione informati automaticamente il potenziale impatto della registrazione di un dispositivo di MDM per Office 365. A seconda di come impostare i criteri, possono essere bloccati non Compatible dispositivi di accedere a Office 365 e dati, incluse le applicazioni installate, le foto e informazioni personali su un dispositivo iscritti, possono essere eliminati.
    
> [!NOTE]
> Criteri e regole di accesso create nella MDM per Office 365 ignorerà criteri cassetta postale di dispositivo mobile Exchange ActiveSync e le regole di accesso al dispositivo create nell'interfaccia di amministrazione di Exchange. Dopo che un dispositivo è iscritto MDM per Office 365, qualsiasi criterio cassetta postale di dispositivo mobile Exchange ActiveSync o regola di accesso applicata al dispositivo verrà ignorata. Per ulteriori informazioni su Exchange ActiveSync, vedere [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380). 
  
## <a name="step-1-create-a-security-policy-and-deploy-to-a-test-group"></a>Passaggio 1: Creare un criterio di protezione e distribuire a un gruppo di test

Prima di iniziare, assicurarsi di avere attivato e impostare i MDM per Office 365. Per istruzioni, vedere [Panoramica della gestione dei dispositivi mobili per Office 365](overview-of-mdm.md) . 
  
1. In Office 365, in sicurezza &amp; centro conformità, passare a **prevenzione della perdita di dati** \> **criteri di protezione dispositivo**.
    
    > [!NOTE]
    > I **criteri di protezione dispositivo** verrà visualizzato nel menu solo dopo aver attivato la gestione dei dispositivi mobili. 
  
2. Scegliere **Crea un criterio +**.
    
    ![Creazione di un criterio dispositivi MDN in Criteri di protezione di dispositivo](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
3. Specificare un **nome** e una **Descrizione** per il nuovo criterio e quindi fare clic su **Avanti**.
    
    ![Impostazione di un nome per il criterio di protezione di dispositivo](media/d382e845-4a7f-4f72-8a09-813ea4cbd0c4.png)
  
4. Nella **i requisiti si desidera avere nei dispositivi?** di pagina, specificare i requisiti che si desidera applicare ai dispositivi mobili all'interno dell'organizzazione e quindi fare clic su **Avanti**.
    
    ![La pagina Impostazioni dei criteri di protezione dispositivo](media/186b3bd5-5e3d-4059-978f-94113111a8ca.png)
  
5. Nella **quali si desidera configurare?** di pagina, specificare eventuali requisiti aggiuntivi che si desidera applicare ai dispositivi mobili all'interno dell'organizzazione e quindi fare clic su **Avanti**.
    
6. Nella **si desidera applicare questi criteri ora?** di pagina, scegliere **Sì**e quindi fare clic su **Aggiungi +**. 
    
    ![Aggiungere i criteri](media/89ab7cab-1b7a-4c78-9aa6-3db7d7667f8e.png)
  
7. Selezionare i gruppi che verranno testare i criteri prima di distribuirlo nell'organizzazione e quindi fare clic su **Aggiungi**.
    
8. Scegliere **Avanti**.
    
9. Esaminare e verificare i dettagli del nuovo criterio dispositivi e quindi fare clic su **Crea questo criterio**.
    
    ![Scegliere Crea questo criterio per la creazione di un criterio dispositivi finsih](media/e410bcf3-8a36-44ed-9fea-00e742db06fb.png)
  
10. Fare clic su **Chiudi**.
    
Ogni utente che si applica il criterio avranno criterio spostato al proprio dispositivo al successivo che accesso a Office 365 dal proprio dispositivo mobile. Se gli utenti sono state ancora applicato al dispositivo mobile prima di un criterio, quindi dopo la distribuzione di criteri, si riceve una notifica sul dispositivo che include i [passaggi per registrare e attivare MDM per Office 365](https://go.microsoft.com/fwlink/?LinkId=615272). Finché non vengono completati la registrazione, accesso alla posta elettronica, OneDrive e altri servizi saranno limitate. Dopo il completamento di registrazione utilizzando l'app Intune portale della società, sarà in grado di utilizzare i servizi e il criterio verrà applicato al proprio dispositivo.
  
## <a name="step-2-verify-your-policy-works"></a>Passaggio 2: Verificare il funzionamento di criteri

Dopo aver creato un criterio di protezione, è necessario verificare che il criterio funzioni nel modo previsto prima di distribuirlo nell'organizzazione.
  
1. In Office 365, passare a **protezione &amp; centro conformità** \> **prevenzione della perdita di dati** \> **la gestione dei dispositivi**.
    
2. Nella pagina **Gestione dei dispositivi mobili per Office 365** , controllare lo stato dei dispositivi di utenti che hanno il criterio applicato. È possibile filtrare oppure ordinare da **tutti** per visualizzare tutti i dispositivi o **bloccato** per visualizzare i dispositivi bloccati. 
    
    ![Visualizzazione dei dispositivi che vengono gestiti da MDM](media/5c9fd069-b716-40d8-9b36-f9cfeae2139f.png)
  
3. È possibile eseguire una cancellazione completa o selettiva nel dispositivo. Per ulteriori informazioni, vedere [a comparsa da un dispositivo mobile in Office 365](wipe-a-mobile-device.md).
    
## <a name="step-3-deploy-a-policy-to-your-organization"></a>Passaggio 3: Distribuire un criterio per l'organizzazione

Dopo aver creato un criterio dispositivi mobili e verificare che funzioni correttamente, distribuirlo nell'organizzazione.
  
1. In Office 365, passare a **protezione &amp; centro conformità** \> **prevenzione della perdita di dati** \> **criteri di protezione dispositivo**.
    
2. Selezionare il criterio che si desidera distribuire e scegliere **Modifica criteri** nel \< _Nome criterio_ \> pannello.  
    
3. Seleziona la scheda **Distribuzione**. 
    
4. Nella scheda **distribuzione** scegliere **Sì** sopra **Selezionare uno o più gruppi di sicurezza che contengono le persone che si desidera applicare questo criterio** e quindi su **Aggiungi**.
    
  - Nel riquadro **Seleziona gruppo** , è possibile ricercare un gruppo da aggiungere, è possibile applicare un filtro tramite alias o in base al nome visualizzato. È inoltre possibile aggiungere un gruppo esistente nell'elenco **gruppi** . 
    
    È possibile aggiungere più gruppi per applicare il criterio.
    
    Scegliere **Aggiungi** nella parte inferiore del riquadro. 
    
5. Nella scheda **distribuzione** , scegliere **Salva** . 
    
    ![Distribuisce MDM criteri dell'organizzazione.](media/dc3e7fe5-201a-4e45-abe3-fc93e0b59028.png)
  
Ogni utente che si applica il criterio avranno criterio spostato al proprio dispositivo al successivo che accesso a Office 365 da un dispositivo mobile. Se gli utenti sono state ancora un criterio applicato al dispositivo mobile, si verrà [visualizzata una notifica nel dispositivo](https://go.microsoft.com/fwlink/?LinkId=615272) con i passaggi per eseguire la registrazione e attivarlo per MDM per Office 365. Dopo che una volta completata la registrazione, il criterio verrà applicato il dispositivo. 
  
## <a name="step-4-block-email-access-for-unsupported-devices"></a>Passaggio 4: Bloccare posta l'accesso per i dispositivi non supportati

Per garantire protezione le informazioni dell'organizzazione, è necessario bloccare l'accesso app di posta elettronica di Office 365 per i dispositivi mobili che non sono supportate da MDM per Office 365. Per un elenco dei dispositivi supportati, vedere [funzionalità di gestione incorporati di dispositivo Mobile per Office 365](capabilities-of-mobile-device-management.md) . A tale scopo: 
  
1. Andare a protezione &amp; centro conformità\> **prevenzione della perdita di dati** \> **criteri di protezione dispositivo**.
    
2. Selezionare **Gestisci impostazioni di accesso dispositivo a livello di organizzazione**.
    
    ![Vai al centro conformità \> dispositivi e fare clic su Collega le impostazioni di accesso di dispositivi Gestisci.](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. Per bloccare i dispositivi non supportati, scegliere **Blocca** in **Se un dispositivo non è supportato dal MDM per Office 365, si desidera consentire o bloccare direttamente dal utilizzando un account di Exchange per accedere alla posta elettronica dell'organizzazione** \> **salvare**.
  
## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Passaggio 5: Scegliere i gruppi di sicurezza da escludere dai controlli dell'accesso condizionale

Se si desidera escludere alcuni utenti dai controlli dell'accesso condizionale sui relativi dispositivi mobili e sono stati creati uno o più gruppi di sicurezza per tali utenti, è possibile aggiungere qui i gruppi di sicurezza. Non saranno applicati criteri ai dispositivi mobili supportati delle persone di questi gruppi.
  
1. Andare a protezione &amp; centro conformità\> **prevenzione della perdita di dati** \> **criteri di protezione dispositivo**.
    
2. Selezionare **Gestisci impostazioni di accesso dispositivo a livello di organizzazione**.
    
    ![Vai al centro conformità \> dispositivi e fare clic su Collega le impostazioni di accesso di dispositivi Gestisci.](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. Selezionare **Aggiungi** per aggiungere il gruppo di sicurezza con gli utenti che si desidera escludere dalla viene bloccato l'accesso a Office 365. Quando un utente è stato aggiunto all'elenco, sarà in grado di accedere alla posta elettronica di Office 365 quando si utilizza un dispositivo non supportato. 
    
4. Selezionare il gruppo di sicurezza da utilizzare nel riquadro **Selezionare gruppo** . 
    
5. Selezionare il nome e **Aggiungi** \> **salvare**.
    
6. Nel riquadro delle **impostazioni di accesso dispositivo a livello di organizzazione** , scegliere **Salva**.
  
## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Qual è l'impatto dei criteri di sicurezza sui diversi tipi di dispositivo?

Quando si applica un criterio ai dispositivi dell'utente, l'impatto su ogni dispositivo varia leggermente tra diversi tipi di dispositivo. Vedere la tabella seguente per visualizzare esempi dell'impatto dei criteri su diversi dispositivi.
  


|**Criterio di sicurezza**|**Windows Phone 8.1 +**|**Android 4+**|**Samsung Knox**|**IOS 6 +**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Richiede un backup crittografato  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |Richiede un backup crittografato di IOS.  <br/> |
|Blocca backup sul cloud  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |Blocca backup Google su Android (in grigio), backup cloud su IOS.  <br/> |
|Blocca sincronizzazione documenti  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS: blocca i documenti nel cloud.  <br/> |
|Blocca sincronizzazione foto  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS (nativo): blocco lo streaming foto.  <br/> |
|Blocca acquisizione schermata  <br/> |✔  <br/> |X  <br/> |✔  <br/> |✔  <br/> |Tentativo bloccato.  <br/> |
|Blocca videoconferenza  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |FaceTime bloccato in iOS, non Skype o altri.  <br/> |
|Blocca invio dati di diagnostica  <br/> |✖  <br/> |X  <br/> |✔  <br/> |✔  <br/> |Blocco invio segnalazione di arresto anomalo di Google su Android.  <br/> |
|Blocca l'accesso all'app store  <br/> |✔  <br/> |X  <br/> |✔  <br/> |✔  <br/> |Icona app store mancante nella home page di Android, disattivata in Windows, mancante in IOS.  <br/> |
|Richiede una password per l'app store  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS: password necessaria per gli acquisti su iTunes.  <br/> |
|Blocca connessione con archivi rimovibili  <br/> |✔  <br/> |X  <br/> |✔  <br/> |ND  <br/> |Android: la scheda SD verrà disattivata nelle impostazioni, Windows invia una notifica all'utente per informarlo che le app installate non sono disponibili  <br/> |
|Blocca connessione Bluetooth  <br/> |✔  <br/> |\*\*\*  <br/> |\*\*\*  <br/> |✖  <br/> |\*\*\*È Impossibile disabilitare BlueTooth come impostazione su Android. In realtà, si disattiva tutte le transazioni che richiedono BlueTooth: distribuzione Audio avanzate, controllo remoto Audio/Video, dispositivi vivavoce, auricolare, accesso Rubrica e porta seriale. Quando si verifica una di queste vengono utilizzata, verrà visualizzato un messaggio popup piccole nella parte inferiore della pagina.  <br/> |
   
## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Cosa accade quando si elimina un criterio o si rimuove un utente dal criterio?

Quando si elimina un criterio o rimuove un utente da un gruppo a cui è stato distribuito il criterio a, le impostazioni dei criteri, il profilo di posta elettronica di Office 365 e messaggi di posta elettronica memorizzati nella cache può rimuovere dal dispositivo dell'utente. Vedere la tabella seguente per determinare quali è stata rimossa per i tipi di dispositivi diversi:
  
|**Contenuto rimosso**|**Windows Phone 8.1 +**|**iOS 6 +**|**Android 4 + (inclusi Samsung Knox)**|
|:-----|:-----|:-----|:-----|
|Profili gestiti tramite posta elettronica\*  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|Impostazioni dei criteri  <br/> |✔  <br/>           Ad eccezione di **Blocca invio dati di diagnostica dal dispositivo.** <br/> |✔  <br/> |✖  <br/> |
   
> [!NOTE]
> \*Se il criterio è stato distribuito con l'opzione **viene gestito il profilo di posta elettronica** selezionato, quindi il profilo di posta elettronica gestita e memorizzati nella cache di messaggi di posta elettronica in quanto profilo verrà eliminato dal dispositivo dell'utente. 
  
Ogni utente a cui è applicato il criterio rimosso avrà il criterio rimosso dal proprio dispositivo al successivo controllato dal proprio dispositivo mobile con MDM per Office 365. Se si distribuisce un nuovo criterio che si applica ai dispositivi di tali utenti, verrà richiesto di registrare nuovamente MDM per Office 365.
  
È inoltre possibile [cancellazione di un dispositivo](wipe-a-mobile-device.md), uno completamente o in modo selettivo a comparsa da informazioni sull'organizzazione dal dispositivo.
  
## <a name="related-topics"></a>Argomenti correlati

[Panoramica di gestione dei dispositivi mobili per Office 365](overview-of-mdm.md)
  
[Funzionalità di gestione dei dispositivi mobili per Office 365](capabilities-of-mobile-device-management.md)
  

