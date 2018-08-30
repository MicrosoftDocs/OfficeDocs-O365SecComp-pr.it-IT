---
title: Set up Mobile Device Management (MDM) in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_OverviewMDM
- 'O365E_OverviewMDM '
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: dd892318-bc44-4eb1-af00-9db5430be3cd
description: La gestione dei dispositivi mobili incorporate per Office 365 consente di proteggere e gestire i dispositivi mobili degli utenti quali iPhone, iPad, Androids, e i telefoni Windows. Per iniziare a eseguire la procedura seguente per attivare e configurare la gestione dei dispositivi mobili per Office 365.
ms.openlocfilehash: c92290170b2937067e7407787282eaaa368b25b7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272361"
---
# <a name="set-up-mobile-device-management-mdm-in-office-365"></a>Set up Mobile Device Management (MDM) in Office 365

Il protocollo incorporati Mobile Device Management (MDM) per Office 365 consente di proteggere e gestire i dispositivi mobili degli utenti quali iPhone, iPad, Androids, e i telefoni Windows. È possibile creare e gestire criteri per, in remoto a comparsa da un dispositivo e visualizzare i rapporti dettagliati dispositivo.
  
Quesiti? Che abbiamo [le domande frequenti per rispondere alle domande più comuni](frequently-asked-questions-about-mdm.md). Tenere presente che non è possibile utilizzare un [partner: amministrazione delegata offerta](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e) per la gestione di gestione dei dispositivi mobili per Office 365. 
  
Gestione dei dispositivi fa parte della sicurezza &amp; centro conformità pertanto sarà necessario passare disponibili per avviare il programma di installazione MDM.
  
Per configurare la gestione dei dispositivi mobili per Office 365 è necessario:
  
1. [Attivare il servizio di gestione dei dispositivi mobili](#activate-the-mobile-device-management-service)  
2. [Configurazione di gestione dei dispositivi mobili](#set-up-mobile-device-management)
3. [Verificare che gli utenti di registrare i dispositivi](#step-4-recommended-manage-device-security-policies)
  
## <a name="activate-the-mobile-device-management-service"></a>Attivare il servizio di gestione dei dispositivi mobili

1. Accedere a Office 365 con l'account di lavoro o della scuola. 
    
2. Accedere a [protezione &amp; centro conformità](https://protection.office.com).
    
3. Passare a **prevenzione della perdita di dati** \> **Device management** e selezionare l'opzione **è possibile iniziare** per avviare il processo di attivazione. 
    
    ![Configurazione di gestione dei dispositivi mobili per Office 365](media/368e1026-9aa5-431b-a722-8f7cf528f263.png)
  
4. Viene creato un criterio di sicurezza predefinito consente di iniziare. Aggiornare il nome del criterio di protezione in questa pagina e quindi fare clic su **Avvia il programma di installazione**.
    
    ![Impostare i criteri di protezione di gestione dei dispositivi mobili](media/5619a2d1-f900-4268-9050-5d7eb57429a5.png)
  
5. Si verrà visualizzata la schermata di installazione che Visualizza stato sull'impostazione di configurazione del servizio.
    
    ![Avanzamento dell'installazione MDM](media/db45d1bb-d247-4ac0-9deb-1b0c1ace9bfa.png)
  
> [!TIP]
> È inoltre possibile individuare **Il programma di installazione MDM** attraverso la ricerca. Nell'interfaccia di amministrazione di Office 365 \> **Home** page di gestione dei tipi di dispositivi mobili nella casella di **ricerca** . > ![Ricerca per la gestione dei dispositivi mobili nell'interfaccia di amministrazione](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)
  
È possibile richiedere tempo per attivare la gestione dei dispositivi mobili per Office 365, ma quando si è terminato, si riceverà un messaggio di posta elettronica che illustra i passaggi successivi da eseguire.
  
## <a name="set-up-mobile-device-management"></a>Configurazione di gestione dei dispositivi mobili

Quando il servizio è pronto, completare i quattro passaggi seguenti per completare l'installazione. Potrebbe essere necessario fare clic su [Gestisci impostazioni](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx) nella pagina **gestione dei dispositivi** nella protezione &amp; centro conformità per visualizzare le impostazioni seguenti. 
  
![Configurare la gestione di dispositivi mobili necessari e dei passaggi consigliati](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
### <a name="step-1-required-configure-domains-for-mdm"></a>Passaggio 1: Domini (obbligatorio) Configure per MDM

Se non si dispone di un dominio personalizzato associato a Office 365 o se non si sta Gestione dispositivi Windows, è possibile ignorare questa sezione. In caso contrario, sarà necessario aggiungere i record DNS per il dominio nell'host DNS. Se sono stati aggiunti i record già, come parte dell'impostazione del dominio a Office 365, impostazione è stata eseguita. Dopo avere aggiunto i record, vengono reindirizzati gli utenti di Office 365 dell'organizzazione che effettuano l'accesso nel dispositivo Windows con un indirizzo di posta elettronica che utilizza il dominio personalizzato per effettuare la registrazione MDM per Office 365.
  
Bisogno di informazioni di configurazione di record? Individuare il registrar nell'elenco indicato nella [creazione di record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) e selezionare il nome del servizio di registrazione per accedere alla Guida dettagliata per la creazione di record DNS. Utilizzare le istruzioni per aggiungere i record di due operazioni seguenti: 
  
|**Nome host**|**Tipo di record**|**Indirizzo**|**TTL**|
|:-----|:-----|:-----|:-----|
|EnterpriseEnrollment  <br/> |CNAME  <br/> |EnterpriseEnrollment.manage.microsoft.com  <br/> |3600  <br/> |
|EnterpriseRegistration  <br/> |CNAME  <br/> |EnterpriseRegistration.windows.net  <br/> |3600  <br/> |
   
Dopo avere aggiunto i due record, tornare alla protezione &amp; centro conformità e passare alla **gestione dei dispositivi** \> **Gestisci impostazioni** per completare il passaggio successivo. 
  
### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Passaggio 2: Configure (obbligatoria) un certificato APNs per i dispositivi iOS

Per gestire iOS dispositivi quali iPhone e iPad, è necessario creare un certificato APNs.
  
A tale scopo, seguire i passaggi da **configurare** collegamenti nella **pagina di gestione di dispositivi mobili del programma di installazione**.
  
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
    
Dopo aver aggiunto certificato punto, tornare alla protezione &amp; centro conformità e passare alla **gestione dei dispositivi** \> **Gestisci impostazioni** per completare il passaggio successivo. 
  
### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Passaggio 3: (Scelta consigliata) configurazione l'autenticazione a più fattori

Se non viene visualizzata l'autenticazione a più fattori (MFA) in **procedure consigliate**, è possibile ignorare questa sezione. Se questa opzione è elencata, è consigliabile che attivare MFA nel portale di Azure Active Directory per aumentare la protezione della gestione dei dispositivi mobili per il processo di registrazione di Office 365. È disattivata per impostazione predefinita.
  
MFA contribuisce a proteggere l'accesso a Office 365 per l'iscrizione al dispositivo mobile per richiedere una seconda forma di autenticazione. Gli utenti verrà richiesto di confermare una chiamata telefonica, un messaggio di testo o una notifica app nel dispositivo mobile dopo aver immesso correttamente la password di account di lavoro. I dispositivi possono registrare solo una volta completata questa seconda forma dell'autenticazione. Dopo che i dispositivi degli utenti vengono iscritti a gestione dei dispositivi mobili per Office 365, gli utenti possono accedere alle risorse di Office 365 con proprio account di lavoro.
  
Nella casella **impostare l'autenticazione a più fattori**, selezionare **l'impostazione**. Per informazioni su come attivare MFA nel portale di Azure Active Directory, vedere [configurare l'autenticazione a più fattori](https://go.microsoft.com/fwlink/p/?LinkId=519255).
  
Dopo aver impostato MFA, tornare alla protezione &amp; centro conformità e passare alla **gestione dei dispositivi** \> **Gestisci impostazioni** per completare il passaggio successivo. 
  
### <a name="step-4-recommended-manage-device-security-policies"></a>Passaggio 4: Criteri Manage (scelta consigliata)

Il passaggio successivo consiste nel creare e distribuire criteri di protezione di dispositivo per migliorare la protezione dei dati dell'organizzazione Office 365. Ad esempio si consentono di impedire la perdita di dati se un utente viene a mancare proprio dispositivo mediante la creazione di un criterio di blocco dispositivi dopo 5 minuti di inattività e dispone di dispositivi svuotare o meno dopo gli errori di accesso 3.
  
Nella **protezione &amp; centro conformità**, andare a **criteri di protezione** \> **criteri per** creare criteri di protezione dispositivo e le regole di accesso. 
  
![Aggiungere un criterio di protezione di dispositivo](media/69a027f5-fbfb-482a-b850-9ccb280b8c62.png)
  
Per istruzioni dettagliate su come creare un nuovo criterio, vedere [creazione e la distribuzione di criteri di protezione dispositivo](create-device-security-policies.md).
  
> [!TIP]
>  Quando si crea un nuovo criterio, è possibile impostare i criteri per consentire violazione dei criteri di accesso e report in un dispositivo dell'utente non è compatibile con il criterio. È possibile visualizzare il numero di dispositivi mobili verranno interessati dal criterio senza bloccando l'accesso a Office 365. > Prima di distribuire un nuovo criterio a tutti gli utenti nell'organizzazione, è consigliabile che testarla su dispositivi utilizzati da un numero limitato di utenti. >, Inoltre, prima di distribuire i criteri, l'organizzazione informati automaticamente il potenziale impatto della registrazione di un dispositivo di MDM per Office 365. A seconda di come impostare i criteri, i dispositivi che non soddisfano li (dispositivi non Compatible) potrebbero bloccare l'accesso a Office 365. Dispositivi non Compatible potrebbero anche essere apps installate, foto e altre informazioni personali che, in un dispositivo iscritti vengano eliminati se viene cancellato il dispositivo. Ulteriori informazioni sulla: [a comparsa da un dispositivo mobile in Office 365](wipe-a-mobile-device.md). 
  
## <a name="make-sure-users-enroll-their-devices"></a>Verificare che gli utenti di registrare i dispositivi

Dopo aver creato e distribuito un criterio di gestione di dispositivi mobili, ogni utente di Office 365 con licenza all'interno dell'organizzazione che si applica il criterio dispositivi verrà visualizzato un messaggio di registrazione al successivo che accesso a Office 365 da un dispositivo mobile. È necessario eseguire la procedura di attivazione e la registrazione prima di poter accedere a documenti e posta elettronica di Office 365. Vedere [registrazione il dispositivo mobile per lavoro o scuola](enroll-your-mobile-device.md).
  
> [!IMPORTANT]
> Se la lingua preferita dell'utente non è supportata dal processo di registrazione, gli utenti possono ricevere notifica della registrazione e i passaggi nei rispettivi dispositivi mobili in un'altra lingua. Non tutte le lingue supportate in Office 365 sono attualmente supportate per il processo di registrazione su dispositivi mobili. 
  
Gli utenti con dispositivi Android o iOS necessari per installare l'app portale della società come parte del processo di registrazione.
  
## <a name="related-topics"></a>Argomenti correlati

[Funzionalità di gestione dei dispositivi mobili](capabilities-of-mobile-device-management.md)
  
[Creazione e distribuzione dei criteri di sicurezza del dispositivo](create-device-security-policies.md)
  

