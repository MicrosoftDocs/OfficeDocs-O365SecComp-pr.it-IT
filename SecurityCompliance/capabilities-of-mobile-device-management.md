---
title: Funzionalità di gestione dei dispositivi mobili integrate per Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.DevicePolicySupportedDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: a1da44e5-7475-4992-be91-9ccec25905b0
description: Gestione dei dispositivi mobili per Office 365 consentono di proteggere e gestire i dispositivi mobili quali iPhone, iPad, Androids e Windows Phone utilizzati nell'organizzazione. Creare criteri di gestione di dispositivi mobili con le impostazioni che è possono utilizzare controllo accesso alla posta elettronica di Office 365 e documenti per i dispositivi mobili supportati e App dell'organizzazione e consente di cancellare i dati in modalità remota un dispositivo in caso di furto.
ms.openlocfilehash: b7200eee3b50c2fc6d3e0ea0920236d71837a88b
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272601"
---
# <a name="capabilities-of-built-in-mobile-device-management-for-office-365"></a>Funzionalità di gestione dei dispositivi mobili integrate per Office 365

Gestione dei dispositivi mobili per Office 365 consentono di proteggere e gestire i dispositivi mobili quali iPhone, iPad, Androids e Windows Phone utilizzato dagli utenti con licenza di Office 365 all'interno dell'organizzazione. È possibile creare criteri di gestione di dispositivi mobili con le impostazioni che consentono di controllare l'accesso alla posta elettronica di Office 365 dell'organizzazione e i documenti per i dispositivi mobili supportati e App. Se un dispositivo viene perduto o rubato, è possibile cancellare in remoto il dispositivo per rimuovere informazioni riservate dell'organizzazione.
    
Richiedono maggiori funzionalità rispetto a quella inclusa in MDM per Office 365? Se è presente Microsoft Intune è necessario: [scegliere tra MDM per Office 365 e Microsoft Intune](choose-between-mdm-and-intune.md).
  
## <a name="supported-devices"></a>Dispositivi supportati

È possibile utilizzare MDM per Office 365 per proteggere e gestire i seguenti tipi di dispositivi.
  
- Windows Phone 8.1 +
    
- iOS 7.1 o versioni successive
    
- Android 4 o versioni successive
    
- Windows 8.1\*
    
- Windows 8.1 RT\*
    
- Windows 10\*\*
    
- Windows 10 Mobile\*\*
    
\*Controllo di accesso per i dispositivi Windows 8.1 e round trip Windows 8.1 è limitato a Exchange ActiveSync.
  
\*\*Richiede il dispositivo per essere aggiunto al Azure Active Directory e registrati nel servizio di gestione di dispositivi mobili dell'organizzazione.
  
Se l'organizzazione utilizza dispositivi mobili che non sono supportati da Gestione dei dispositivi mobili per Office 365, è possibile bloccare l'accesso Exchange ActiveSync app di posta elettronica di Office 365 per questi dispositivi, per rendere più sicuro i dati dell'organizzazione. Passaggi per il blocco di Exchange ActiveSync: consultare [gestire le impostazioni di accesso di dispositivi](manage-device-access-settings.md).
  
## <a name="access-control-for-office-365-email-and-documents"></a>Controllo di accesso a documenti e posta elettronica di Office 365

Applicazioni supportate per diversi tipi di dispositivi mobili nella tabella seguente chiedono agli utenti di effettuare la registrazione MDM per Office 365 in cui esiste un nuovo criterio di gestione di dispositivi mobili che si applica ai dispositivi dell'utente e l'utente non è registrato in precedenza il dispositivo. Se un dispositivo dell'utente non è conforme a un criterio, a seconda di come impostare il criterio, potrebbe essere da bloccare un utente di accedere alle risorse di Office 365 in queste applicazioni o potrebbero avere accesso ma Office 365 segnalerà una violazione dei criteri.
  
||**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|
|:-----|:-----|:-----|:-----|
|**Exchange** <br/> Exchange ActiveSync include la posta elettronica integrata e applicazioni di terze parti, ad esempio TouchDown, che utilizzano Exchange ActiveSync 14.1 o versioni successive.  <br/> |![Icona Exchange ActiveSync](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Icona Posta di Exchange per dispositivi mobili](media/5b5312b4-3bfb-4fc7-84ff-d7ab21227c10.png)Posta di Exchange  <br/> |![Icona Exchange ActiveSync](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Icona della posta per dispositivi mobili per iPhone](media/888bdc7a-8354-4013-a0b2-0d4432a9a92e.png)Posta elettronica  <br/> |![Icona Exchange ActiveSync](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Icona posta elettronica di Android](media/20b48492-4adc-40ce-99cf-1b47bd2b389d.png)Posta elettronica  <br/> |
|**Office** e **OneDrive for Business** <br/> |Nessuna app supportata  <br/> |![Icona di Outlook Mobile per iPhone](media/6c63112d-c10c-4040-85cc-feeccc3dd424.png)Outlook  <br/> ![Icona di OneDrive Mobile per iPhone](media/560ec187-82d9-4793-b72f-7ba595972bdc.png)OneDrive  <br/> ![Icona di Word Mobile per iPhone](media/63a3a749-1f98-402f-b211-e46b9224b655.png)Word  <br/> ![Icona di Excel Mobile per iPhone](media/5b8f62c0-96aa-4602-9ed8-f837bbf5fa9e.png)Excel  <br/> ![Icona di PowerPoint Mobile per iPhone](media/17c02dca-f60a-4d13-a610-00d576a40943.png)PowerPoint  <br/> |**Su telefoni e tablet:** <br/> ![Android tablet e telefono cellulare icona di Outlook](media/ed2a813d-f481-46e0-acc9-6422f0d16072.png)Outlook  <br/> ![Icona mobile OneDrive telefono Android](media/64855d02-1684-4795-b4c5-863860f18722.png)OneDrive  <br/> ![Icona di dispositivi mobile Word Android](media/f618fe83-b163-4680-b924-fcedc06ab4ba.png)Word  <br/> ![Icona di dispositivi mobile Android di Excel](media/659c7a5f-5797-4b47-a776-4a0c8f784c89.png)Excel  <br/> ![Icona di dispositivi mobile PowerPoint Android](media/35b98bce-d7cb-40ce-87e3-07b9764207b1.png)PowerPoint  <br/> **Solo su telefoni:** <br/> ![Icona per dispositivi mobili per dispositivi mobili Office](media/1aa9e978-6eb2-40aa-82da-62fb79cee313.png)Office Mobile  <br/> |
   
> [!NOTE]
>  Supporto per iOS 7.1 e versioni successive include dispositivi iPhone e iPad. > Gestione dei dispositivi BlackBerry non è supportata da Gestione dei dispositivi mobili per Office 365. Utilizzare BlackBerry Business Cloud Services (BBCS) da BlackBerry per gestire i dispositivi BlackBerry. > Gli utenti non verrà richiesto di registrare e non venga bloccato o segnalato per violazione dei criteri se si utilizza il browser per dispositivi mobili per accedere ai siti di SharePoint di Office 365, documenti in Office Online o posta elettronica in Outlook Web App. 
  
Nel diagramma seguente viene illustrato il comportamento quando un utente a un nuovo dispositivo accede a un'applicazione che supporta controllo di accesso con MDM per Office 365. Viene bloccato l'utente di accedere alle risorse di Office 365 in app fino a quando non sono registrare il dispositivo.
  
![Viene illustrato il processo di registrazione per il nuovo dispositivo.](media/O365-MDM-Capabilities-EnrollmentExample.png)
  
> [!NOTE]
> Criteri e regole di accesso create nella MDM per Office 365 ignorerà criteri cassetta postale di dispositivo mobile Exchange ActiveSync e le regole di accesso al dispositivo create nell'interfaccia di amministrazione di Exchange. Dopo che un dispositivo è iscritto MDM per Office 365, qualsiasi criterio cassetta postale di dispositivo mobile Exchange ActiveSync o regola di accesso applicata al dispositivo verrà ignorata. Per ulteriori informazioni su Exchange ActiveSync, vedere [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380). 
  
## <a name="policy-settings-for-mobile-devices"></a>Impostazioni criteri per dispositivi mobili

Se si crea un criterio per bloccare l'accesso con determinate impostazioni attivate, gli utenti saranno bloccati di accedere alle risorse di Office 365 quando si utilizza un'app supportata che è elencata nel [controllo di accesso per la posta elettronica di Office 365 e documenti](#access-control-for-office-365-email-and-documents). Nelle sezioni seguenti sono le impostazioni che è possono impedire agli utenti di accedere alle risorse di Office 365:
  
- Sicurezza
    
- Crittografia
    
- Modificato
    
- Profilo di posta elettronica gestito
    
Ad esempio, il diagramma seguente mostra cosa succede quando un utente con un dispositivo iscritti non è compatibile con un'impostazione di protezione in un criterio di gestione di dispositivi mobili che si applica a proprio dispositivo. L'utente accede a un'applicazione che supporta controllo di accesso con MDM per Office 365. Sono bloccati di accedere alle risorse di Office 365 in app fino a quando non è conforme proprio dispositivo con l'impostazione di sicurezza.
  
![Mostra utente bloccato quando il dispositivo non è compatibile.](media/O365-MDM-Capabilities-ComplianceExample.png)
  
Nelle sezioni seguenti vengono elencate le impostazioni di criteri che è possibile utilizzare per proteggere e gestire i dispositivi mobili che si connettono a risorse di Office 365 dell'organizzazione. 
  
### <a name="security-settings"></a>Impostazioni di sicurezza

|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Richiesta di una password  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Evitare password semplice  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Richiesta di una password alfanumerica  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Lunghezza minima password  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Numero di errori di accesso prima di cancellare il dispositivo  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Minuti di inattività prima del blocco del dispositivo  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Scadenza password (giorni)  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Ricorda cronologia password e impedisci il riutilizzo  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
   
### <a name="encryption-settings"></a>Impostazioni di crittografia

|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Richiedi crittografia dati nei dispositivi  <br/> |Windows Phone 8.1 è già crittografato e non può essere decrittografato  <br/> |✖  <br/> |✔  <br/> |✔\*  <br/> |
   
\*Con Samsung Knox, è inoltre possibile richiedere la crittografia schede di memoria.
  
### <a name="jail-broken-setting"></a>Impostazione di modifica

|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Il dispositivo non può essere modificato o usato come radice  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
   
### <a name="managed-email-profile-option"></a>Opzione del profilo di posta elettronica gestito

L'opzione seguente può impedire agli utenti di accedere alla loro posta elettronica di Office 365, se si sta utilizzando un profilo di posta elettronica creato manualmente. Gli utenti di dispositivi iOS necessario eliminare il profilo di posta elettronica creato manualmente prima di poter accedere alla posta elettronica. Dopo che elimina il profilo, un nuovo profilo verrà creato automaticamente nel dispositivo.
  
|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Il profilo di posta elettronica è gestito  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="cloud-settings"></a>Impostazioni del cloud

|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Richiede un backup crittografato  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Blocca backup sul cloud  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Blocca sincronizzazione documenti  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Blocca sincronizzazione foto  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Consentire il backup di Google  <br/> |N/D  <br/> |N/D  <br/> |✖  <br/> |✔  <br/> |
|Consenti sincronizzazione automatica di account Google  <br/> |N/D  <br/> |N/D  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="system-settings"></a>Impostazioni di sistema

|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Blocca acquisizione schermata  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
|Blocca invio dati di diagnostica dal dispositivo  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="application-settings"></a>Impostazioni dell'applicazione

|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Blocca videoconferenze sul dispositivo  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Blocca l'accesso all'archivio applicazioni  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
|Richiedi password per l'accesso all'archivio applicazioni  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="device-capabilities-settings"></a>Impostazioni delle funzionalità del dispositivo

|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Blocca connessione con archivi rimovibili  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
|Blocca connessione Bluetooth  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="additional-settings"></a>Impostazioni aggiuntive

È possibile impostare le impostazioni dei criteri aggiuntive seguenti utilizzando i cmdlet di PowerShell. Per ulteriori informazioni, vedere [protezione di Office 365 &amp; cmdlet centro conformità](https://go.microsoft.com/fwlink/p/?LinkId=827804).
  
|**Nome dell'impostazione**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4 + (inclusi Samsung Knox)**|
|:-----|:-----|:-----|:-----|
|CameraEnabled  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|RegionRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|MoviesRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|TVShowsRating  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AppsRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowVoiceDialing  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowVoiceAssistant  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowAssistantWhileLocked  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowPassbookWhileLocked  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|MaxPasswordGracePeriod  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|PasswordQuality  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
|SystemSecurityTLS  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|WLANEnabled   <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="settings-supported-by-windows"></a>Impostazioni supportate da Windows

È possibile gestire i dispositivi Windows 8.1 e Windows 10 eseguendo una registrazione li come i dispositivi mobili. Dopo aver distribuito un criterio applicabile, agli utenti con i dispositivi Windows 8.1 RT e round trip 10 Windows verranno richiesto di effettuare la registrazione MDM per Office 365 la prima volta che utilizzano l'app di posta elettronica incorporati per accedere alla loro posta elettronica di Office 365. 
  
Le impostazioni riportate di seguito sono supportate per i dispositivi Windows 8.1 e 10 Windows che vengono registrati come i dispositivi mobili. Queste impostazioni non impedire agli utenti di accedere alle risorse di Office 365.
  
 **Impostazioni di sicurezza**
  
- Richiesta di una password alfanumerica
    
- Lunghezza minima password
    
- Numero di errori di accesso prima di cancellare il dispositivo
    
- Minuti di inattività prima del blocco del dispositivo
    
- Scadenza password (giorni)
    
- Ricorda cronologia password e impedisci il riutilizzo
    
 **Impostazioni di sistema**
  
Blocca invio dati di diagnostica dal dispositivo
  
 **Impostazioni aggiuntive**
  
Puoi configurare le impostazioni criteri aggiuntive riportate di seguito tramite i cmdlet di PowerShell:
  
- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus
    
- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    
## <a name="remotely-wipe-a-mobile-device"></a>Cancella in remoto un dispositivo mobile

 Se un dispositivo viene perduto o rubato, è possibile rimuovere i dati riservati dell'organizzazione e impedire l'accesso alle risorse di Office 365 dell'organizzazione eseguendo una transizione da **protezione &amp; centro conformità\>prevenzione della perdita di dati\>dispositivo gestione**. È possibile eseguire una cancellazione selettiva per rimuovere solo i dati dell'organizzazione o una cancellazione completa per eliminare tutte le informazioni da un dispositivo e ripristinare le impostazioni predefinite.
  
Per ulteriori informazioni, vedere [a comparsa da un dispositivo mobile in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=518157).
  
## <a name="see-also"></a>Vedere anche

[Panoramica di gestione dei dispositivi mobili per Office 365](overview-of-mdm.md)
  
[Creazione e distribuzione dei criteri di sicurezza del dispositivo](create-device-security-policies.md)

