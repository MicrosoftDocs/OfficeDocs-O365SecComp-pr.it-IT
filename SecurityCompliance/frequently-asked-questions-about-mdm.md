---
title: Domande frequenti sulla gestione dei dispositivi mobili per Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 3871f99c-c9db-4a23-86f9-902c1b02f58d
description: In questo articolo è riportate le domande su Mobile Device Management (MDM) per Office 365, una caratteristica che consente di gestire e proteggere i dispositivi mobili in Office 365.
ms.openlocfilehash: 6c4a5b3603d392b3d83769cd0f17450ce70565be
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272271"
---
# <a name="frequently-asked-questions-about-mobile-device-management-for-office-365"></a>Domande frequenti sulla gestione dei dispositivi mobili per Office 365

In questo articolo è riportate le domande su Mobile Device Management (MDM) per Office 365, una caratteristica che consente di gestire e proteggere i dispositivi mobili in Office 365.
  
## <a name="faqs"></a>Domande frequenti

- [Come è possibile ottenere MDM per Office 365? È possibile non viene visualizzato nell'interfaccia di amministrazione di Office 365](#how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center)
    
- [Come posso Guida introduttiva a gestione dei dispositivi in MDM](#how-can-i-get-started-with-device-management-in-mdm)
    
- [Sto cercando impostare MDM ma sembra bloccata. L'integrità dei servizi Office 365 è stato visualizzazione "provisioning" per un po' di tempo. Cosa posso fare?](#im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do)
    
- [È possibile procedere se si verifica un errore di registrazione di dispositivo?](#what-can-i-do-if-device-enrollment-fails)
    
- [Che cos'è la differenza tra Intune e MDM per Office 365?](#whats-the-difference-between-intune-and-mdm-for-office-365)
    
- [Funzionano di criteri per MDM Come configurare tali? Disabilitarli?](#how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them)
    
- [È possibile passare dalla gestione dei dispositivi Exchange ActiveSync a MDM per Office 365?](#can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365)
    
- [È possibile impostare MDM ma ora si desidera rimuoverlo. Che cosa sono i passaggi?](#i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps)
    
- [Ulteriore assistenza](#still-need-help)
    
## <a name="how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center"></a>Come è possibile ottenere MDM per Office 365? È possibile non viene visualizzato nell'interfaccia di amministrazione di Office 365

Aver completato il ripristino dello stato fuori questa caratteristica per i clienti di Office 365. Cercare la scheda **Gestione dei dispositivi** nel [accedere a Office 365 Security &amp; centro conformità](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8). Se non è presente, inviaci i tuoi suggerimenti. Vedere [ulteriore assistenza?](#still-need-help), e si sarà consentono di iniziare. 
  
## <a name="how-can-i-get-started-with-device-management-in-mdm"></a>Come posso Guida introduttiva a gestione dei dispositivi in MDM

Sono disponibili quattro passaggi di base con MDM per Office 365 (ulteriori dettagli nel [Set di backup Mobile Device Management (MDM) in Office 365](set-up-mobile-device-management.md)):
  
1. **Attivare MDM.** Visitare il [passare alla protezione di Office 365 &amp; centro conformità](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) e selezionare **la gestione dei dispositivi**. Selezionare l'opzione **è possibile iniziare** per avviare il processo di attivazione. 
    
2. **Completare la configurazione di MDM**. Ciò potrebbe richiedere aggiornamenti ai record DNS e configurazione dei certificati APNs per il dominio. 
    
3. **Crea i criteri**. Creare criteri di gestione di dispositivi e applicarle a gruppi di utenti che vengono [impostati i gruppi di protezione](create-device-security-policies.md). È consigliabile che si avvia distribuendo i criteri a un gruppo di test di piccole dimensioni. In sicurezza &amp; centro conformità, selezionare i **criteri di protezione dispositivo**.
    
4. **Agli utenti di registrare i dispositivi.** Gli utenti che hanno avuto un criterio applicato alle stesse vengono richiesto di [registrare i dispositivi](enroll-your-mobile-device.md) quando si tenta di accedere ai dati di Office 365 (utilizzando il client di posta elettronica, ad esempio). 
    
## <a name="im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Sto cercando impostare MDM ma sembra bloccata. L'integrità dei servizi Office 365 è stato visualizzazione "provisioning" per un po' di tempo. Cosa posso fare?

Potrebbe richiedere alcuni minuti per prepararsi per è il servizio. Quando viene completato il provisioning di tipo, verrà visualizzata la gestione dei dispositivi mobili per Office 365 pagina. Se si sono il tempo di attesa 24 ore e lo stato è ancora **Provisioning**, vedere [ulteriore assistenza?](#still-need-help) e verranno fornite informazioni utili di identificare la causa del problema. 
  
## <a name="what-can-i-do-if-device-enrollment-fails"></a>È possibile procedere se si verifica un errore di registrazione di dispositivo?

Se si verificano problemi durante il recupero di un dispositivo registrato, innanzitutto verificare le seguenti:
  
- Verificare che il dispositivo non è già registrato con un altro provider di gestione di dispositivi mobili, ad esempio Intune.
    
- Verificare che il dispositivo sia impostato la data e l'ora.
    
- Passare a un altro Wi-Fi o rete cellulare del dispositivo.
    
- Per i dispositivi Android o iOS, disinstallare e reinstallare l'applicazione di portale della società Intune nel dispositivo.
    
Se la registrazione ancora non funziona, [provare a questi passaggi di risoluzione dei problemi aggiuntivi](troubleshoot-mdm.md).
  
## <a name="whats-the-difference-between-intune-and-mdm-for-office-365"></a>Che cos'è la differenza tra Intune e MDM per Office 365?

Entrambe MDM per Office 365 e Intune offrire soluzioni basate su cloud per la gestione dei dispositivi dell'organizzazione. Utilizzare questo [Affianca per confronto](choose-between-mdm-and-intune.md) tra i due servizi che consentono di decidere se utilizzando Intune o MDM per Office 365 è il miglior adattamento. 
  
## <a name="how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them"></a>Funzionano di criteri per MDM Come configurare tali? Disabilitarli?

Al termine dell'installazione iniziale di MDM per Office 365, si [creano criteri e applicarle a gruppi di utenti](create-device-security-policies.md) in [accedere a Office 365 Security &amp; centro conformità](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8). Per gli utenti che si applicano i criteri per i criteri di richiedono agli utenti di registrare i dispositivi in MDM per Office 365 prima che il dispositivo può essere utilizzato per accedere ai dati di Office 365. I criteri che sono stati impostati determinano le impostazioni per i dispositivi mobili, ad esempio, la frequenza con cui è necessario reimpostare le password o se è necessaria la crittografia dei dati. 
  
Microsoft fornisce istruzioni dettagliate per [la creazione e distribuzione di criteri di protezione dispositivo](create-device-security-policies.md). Si crea i criteri di sicurezza &amp; centro conformità ed è possibile disabilitare uno o più criteri restituendo per la protezione &amp; centro conformità e la modifica il criterio per rimuovere il gruppo applicati. In alternativa, è possibile scegliere di non rimuovere completamente il criterio.
  
Se si desidera escludere un gruppo specifico di utenti siano danneggiati dai criteri, è possibile aggiungere un gruppo al gruppo di esclusione. In sicurezza &amp; centro conformità, nella scheda **dispositivi** di selezionare **Gestisci impostazioni di accesso di dispositivi**e quindi aggiungere il gruppo di **sono presenti gruppi di protezione da escludere dal controllo di accesso?** sezione. 
  
## <a name="can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365"></a>È possibile passare dalla gestione dei dispositivi Exchange ActiveSync a MDM per Office 365?

Se già si utilizza [criteri di Exchange ActiveSync](https://go.microsoft.com/fwlink/?LinkId=615145) per gestire i dispositivi mobili, è possibile iniziare a utilizzare MDM per Office 365 seguendo i passaggi per [impostare backup Mobile Device Management (MDM) in Office 365](set-up-mobile-device-management.md).
  
Quando si applicano i criteri creati in MDM per Office 365 a gruppi di utenti, questi criteri per ignorare i criteri cassetta postale di dispositivo mobile Exchange ActiveSync e regole di accesso ai dispositivi precedentemente creato nell'interfaccia di amministrazione di Exchange per gli utenti. 
  
Dopo che un dispositivo è iscritto MDM per Office 365, qualsiasi criterio cassetta postale di dispositivo mobile Exchange ActiveSync o regola di accesso applicata al dispositivo verrà ignorata.
  
## <a name="i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps"></a>È possibile impostare MDM ma ora si desidera rimuoverlo. Che cosa sono i passaggi?

Purtroppo è non è semplicemente "annullamento del provisioning" MDM per Office 365 dopo è stato configurato. Ma è possibile rimuoverlo per gruppi di utenti mediante la rimozione di gruppi di protezione utente dai criteri dispositivi che sono stati creati. In alternativa, è disabilitata per tutti gli utenti da rimuovere i criteri per i dispositivi in modo che non sono presenti sul posto e non vengono eseguite. Informazioni su [come disattivare la gestione dei dispositivi mobili in Office 365](turn-off-mdm.md).
  
## <a name="still-need-help"></a>Ulteriore assistenza?

[![Ottenere assistenza dai forum della community di Office 365](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Amministratori: Accedere e creare una richiesta di assistenza](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Amministratori: Chiama il supporto](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  

  

