---
title: 'Avvio veloce: configurare Office 365 Advanced Threat Protection'
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Ecco una guida introduttiva che è possibile utilizzare per assicurarsi che Office 365 Advanced Threat Protection (ATP) sia impostato e configurato per l'organizzazione.
ms.openlocfilehash: 5aecbdb63f30a620812de44907b29dcae838ba36
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693298"
---
# <a name="quick-start-guide-set-up-office-365-advanced-threat-protection"></a>Guida introduttiva: configurare Office 365 Advanced Threat Protection

Di seguito è illustrata una guida introduttiva che è possibile utilizzare come elenco di controllo per assicurarsi che Office 365 Advanced Threat Protection (ATP) sia configurato per l'organizzazione. Se si è nuovi per la protezione dalle minacce in Office 365 o non si è sicuri di dove iniziare, utilizzare le linee guida seguenti come punto di partenza. 

> [!IMPORTANT]
> **Per ogni tipo di criterio sono incluse le impostazioni consigliAte iniziali, tuttavia sono disponibili molte opzioni ed è possibile modificare le impostazioni in base alle esigenze specifiche dell'organizzazione**. Consenti circa 30 minuti affinché i criteri o le modifiche vengano elaborati tramite il Data Center.

## <a name="prerequisites"></a>Prerequisiti

- L'organizzazione deve disporre di un abbonamento che include [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).

- È necessario essere assegnati a un ruolo appropriato per accedere alle funzionalità ATP. Nella tabella seguente sono inclusi alcuni esempi: 

    |Ruolo o gruppo di ruoli  |Altre informazioni  |
    |---------|---------|
    |Amministratore globale di Office 365 |[Informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
    |Amministratore della sicurezza |[Autorizzazioni per il ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
    |Gestione dell'organizzazione di Exchange Online |[Autorizzazioni in Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>e<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

    (Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md)).

## <a name="part-1---anti-malware"></a>Parte 1-antimalware

1. nel [centro conformità di Office 365 Security &](https://protection.office.com), scegliere**Anti-malware**per**criteri** > di **gestione** > .
2. Fare doppio clic sul criterio **predefinito** e quindi scegliere **Impostazioni**.
3. Specificare le impostazioni seguenti:
    - Nella sezione **risposta di rilevamento malware** mantenere l'impostazione predefinita **Nr**.
    - Nella sezione **filtro tipi di allegati comuni** scegliere attivato ****.
4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni di criteri anti-malware, vedere [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---zero-day-protection"></a>Parte 2-protezione zero-day

La protezione da zero giorni è configurata tramite criteri, ad esempio i collegamenti sicuri ATP e i criteri allegati sicuri.

### <a name="atp-safe-attachments-policies"></a>Criteri per gli allegati sicuri ATP

1. nel [centro conformità di Office 365 Security &](https://protection.office.com), selezionare i**criteri** > di **gestione** > delle minacce per gli**allegati sicuri ATP**.
2. Selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams**.
3. Nella sezione **Proteggi allegati di posta elettronica** , fare clic sul**+** segno più ().
4. Specificare le impostazioni seguenti:
    - Nella casella **nome** Digitare `Block malware`.
    - Nella sezione Response scegliere **Block**.
    - Nella sezione **allegato di reindirizzamento** selezionare l'opzione **Abilita reindirizzamento**e quindi specificare l'indirizzo di posta elettronica per l'amministratore o l'operatore di sicurezza dell'organizzazione che rivedrà i file rilevati.
    - Nella sezione **applicato a** scegliere **il dominio del destinatario**. Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.
5. Fare clic su **Salva**.
6. (Passaggio aggiuntivo consigliato) Come amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con il parametro **DisallowInfectedFileDownload** impostato su *true* per l'ambiente Office 365. In questo modo si impedisce l'apertura, lo spostamento, la copia o la condivisione di file che vengono rilevati come dannosi.  

Per ulteriori informazioni, vedere [configurare i criteri per gli allegati sicuri ATP di office 365](set-up-atp-safe-attachments-policies.md) e [abilitare Office 365 ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Criteri per i collegamenti sicuri ATP

Per configurare i collegamenti sicuri di ATP, esaminare i criteri predefiniti e aggiungere un criterio.

1. nel [centro conformità Office 365 Security &](https://protection.office.com), scegliere**criteri** > di **gestione** > delle minacce**ATP collegamenti sicuri**.
2. Fare doppio clic sul criterio **predefinito** .
3. Nella sezione **use Safe Links in** selezionare l'opzione **Office 365 ProPlus, Office per iOS e Android**e quindi fare clic su **Salva**.
4. Nella sezione **criteri che si applicano a destinatari specifici** fare clic sul segno più**+**().
5. Specificare le impostazioni seguenti:
    - Nella casella **nome** Digitare un nome, ad esempio `Safe Links`.
    - Nella sezione **selezionare l'azione** scegliere attivato. ****
    - Selezionare le opzioni seguenti:
        - **Utilizzare gli allegati sicuri per analizzare il contenuto scaricabile** 
        - **Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**
        - **Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale**
    - Nella sezione **applicato a** scegliere **il dominio del destinatario**. Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.
6. Fare clic su **Salva**.

Per ulteriori informazioni, vedere [configurare i criteri dei collegamenti sicuri ATP di Office 365](set-up-atp-safe-links-policies.md). 

## <a name="part-3---anti-phishing"></a>Parte 3-anti-phishing 

1. nel [centro conformità Office 365 Security &](https://protection.office.com), scegliere**criteri** > di **gestione** > delle minacce**ATP anti-phishing**.
2. Fare clic su **criteri predefiniti**.
3. Nella sezione **rappresentazione** fare clic su **modifica**e quindi specificare le impostazioni seguenti:
    -  Nella scheda **Aggiungi utenti da proteggere** , attiva la protezione. Aggiungere quindi gli utenti, ad esempio i membri del Consiglio dell'organizzazione, il CEO, il CFO e altri leader senior. (È possibile digitare un singolo indirizzo di posta elettronica o fare clic per visualizzare un elenco).
    - Nella scheda **Aggiungi domini da proteggere** , attiva **automaticamente Includi i domini che possiedo**. Se si dispone di domini personalizzati, aggiungere anche quelli.
    - Nella scheda **azioni** selezionare **Sposta messaggio nelle cartelle di posta indesiderata dei destinatari** per entrambi gli utenti rappresentati e per il dominio rappresentato e attiva suggerimenti per la sicurezza.
    - Nella scheda **Intelligence della cassetta postale** , verificare che l'intelligence della cassetta postale sia attivata.
    - Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**.
4. Nella sezione **spoofing** fare clic su **modifica**e quindi specificare le impostazioni seguenti:
    - Nella scheda **Impostazioni filtro spoofing** verificare che la protezione anti-spoofing sia attivata.
    - Nella scheda **azioni** scegliere Sposta messaggio nelle cartelle di posta indesiderata dei destinatari.
    - Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**. Se non sono state apportate modifiche, fare clic su **Annulla**.
5. Chiudere la pagina impostazioni di criteri predefinite.

Per ulteriori informazioni sulle opzioni relative ai criteri di anti-phishing, vedere [set up Office 365 ATP anti-phishing and anti-phishing Policies](set-up-anti-phishing-policies.md).

## <a name="part-4---anti-spam"></a>Parte 4-protezione da posta indesiderata

1. nel [centro conformità di Office 365 Security &](https://protection.office.com), scegliere protezione dalla**posta**indesiderata **dei** > **criteri** > di gestione delle minacce.
2. Nella scheda **personalizzato** , attiva **impostazioni personalizzate** .
3. Espandere **criteri di filtro della posta indesideraTa predefiniti**, fare clic su **modifica criteri**e quindi specificare le impostazioni seguenti:
    - Nella sezione **azioni di posta indesiderata e di massa** impostare la soglia su un valore pari a 5 o 6.
    - Nella sezione **Consenti elenchi** esaminare (e, se necessario, modificare) i propri mittenti e domini consentiti.
4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni relative ai criteri di protezione da posta indesiderata, vedere [Configure the antispam](configure-the-anti-spam-policies.md)Policy.

## <a name="part-5---service-wide-settings"></a>Parte 5-impostazioni a livello di servizio

### <a name="zero-hour-auto-purge"></a>Spurgo automatico zero-hour

Zero-hour auto Purge (ZAP) è attivata per impostazione predefinita; Tuttavia, devono essere soddisfatte le condizioni seguenti:
- Le azioni di posta indesiderata sono impostate in modo da **spostare messaggi nella cartella posta** indesiderata nei criteri di protezione dalla posta
- Gli utenti hanno mantenuto le impostazioni predefinite per la posta indesiderata e non hanno disattivato la protezione della posta indesiderata.

Per ulteriori informazioni, vedere [zero-hour auto Purge-protezione da posta indesiderata e malware](zero-hour-auto-purge.md).

### <a name="audit-logging"></a>Registrazione di controllo

Per visualizzare i dati nei report di protezione dalle minacce, ad esempio il [dashboard di sicurezza](security-dashboard.md) e l' [esploratore](use-explorer-in-security-and-compliance.md), è necessario che la registrazione di controllo sia attivata per l'organizzazione.

Vedere [attivazione o disattivazione della ricerca nel registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Attività successive all'installazione

### <a name="watch-for-new-features-and-service-updates"></a>Controllare le nuove funzionalità e gli aggiornamenti dei servizi

- [Visitare la roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [Vedere la descrizione del servizio Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a>Vedere in che modo ATP è in funzione per la propria organizzazione

- [Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)

- [Utilizzo di Esplora risorse nel &amp; Centro sicurezza e conformità](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a>Verifica e revisione periodica dei criteri ATP

- [Mantenere la sicurezza di Office 365 utenti con Office 365 Threat Investigation and Response](keep-users-safe-with-office-365-ti.md) 

- [Utilizzare gli smart report e le informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365](reports-and-insights-in-security-and-compliance.md) 