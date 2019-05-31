---
title: Protezione dalle minacce in Office 365
ms.author: tracyp
author: msfttracyp
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 05/09/2019
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Utilizzare questo articolo come guida per configurare ora le funzionalità di protezione dalle minacce.
ms.openlocfilehash: 6700e2714ea607f675b487204404d53c1d51db93
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590579"
---
# <a name="protect-against-threats-in-office-365"></a>Protezione dalle minacce in Office 365

Office 365 include una vasta gamma di funzionalità di protezione dalle minacce. Di seguito è illustrata una guida introduttiva che è possibile utilizzare come elenco di controllo per verificare che le funzionalità di protezione delle minacce siano configurate per l'organizzazione. Se si è nuovi per le funzionalità di protezione dalle minacce in Office 365 o si è sicuri di dove iniziare, utilizzare le linee guida seguenti come punto di partenza. 

> [!IMPORTANT]
> **Per ogni tipo di criterio sono incluse le impostazioni consigliate iniziali, tuttavia sono disponibili molte opzioni ed è possibile modificare le impostazioni in base alle esigenze specifiche dell'organizzazione**. Consenti circa 30 minuti affinché i criteri o le modifiche vengano elaborati tramite il Data Center.

## <a name="requirements"></a>Requisiti

### <a name="subscriptions"></a>Sottoscrizioni

Le funzionalità di protezione dalle minacce sono incluse in tutte le sottoscrizioni di Office 365; Tuttavia, alcuni abbonamenti includono funzionalità più avanzate. Nella tabella seguente sono elencate le funzionalità di protezione incluse in questo articolo, insieme ai requisiti minimi di sottoscrizione.<br/>

|Tipo di protezione  |Requisito di sottoscrizione  |
|---------|---------|
|Protezione anti-malware    | [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) EOP        |
|Protezione da URL e file dannosi nei documenti di posta elettronica e di Office    | [Protezione avanzata dalle minacce di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) ATP       |
|Protezione anti-phishing    | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)      |
|Protezione anti-phishing avanzata    | [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)   |
|Protezione dalla posta indesiderata     | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)       |
|Spurgo automatico zero-hour (per la posta elettronica)    | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)        |
|Registrazione di controllo (utilizzata per la creazione di report)    | [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)        |

### <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

È necessario essere assegnati a un ruolo appropriato per configurare i criteri nel [Centro sicurezza _AMP_ Compliance](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Nella tabella seguente sono inclusi alcuni esempi: 

|Ruolo o gruppo di ruoli  |Altre informazioni  |
|---------|---------|
|Amministratore globale di Office 365 |[Informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Amministratore della sicurezza |[Autorizzazioni per il ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gestione dell'organizzazione di Exchange Online |[Autorizzazioni in Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>e<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="part-1---anti-malware-protection"></a>Parte 1-protezione antimalware

La [protezione antimalware](anti-malware-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description). 

1. Nel [Centro sicurezza & Compliance](https://protection.office.com)scegliere**anti-malware** **Management** > **policy** > .

2. Fare doppio clic sul criterio **predefinito** e quindi scegliere **Impostazioni**.

3. Specificare le impostazioni seguenti:

    - Nella sezione **risposta di rilevamento malware** mantenere l'impostazione predefinita **Nr**.

    - Nella sezione **filtro tipi di allegati comuni** scegliere attivato ****.

4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni di criteri anti-malware, vedere [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Parte 2-protezione da URL e file dannosi

La protezione del tempo di clic da URL e file dannosi è disponibile in abbonamenti che includono [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) ed è configurata tramite gli [allegati sicuri di ATP](atp-safe-attachments.md) e i criteri dei [collegamenti sicuri di ATP](atp-safe-links.md) .

### <a name="atp-safe-attachments-policies"></a>Criteri per gli allegati sicuri ATP

Per configurare gli [allegati sicuri di ATP](atp-safe-attachments.md), è necessario definire almeno un criterio per gli allegati sicuri ATP. 

1. Nel [Centro sicurezza & Compliance](https://protection.office.com)selezionare i **** > **criteri** > di gestione delle minacce per gli**allegati sicuri ATP**.

2. Selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams**.

3. Nella sezione **Proteggi allegati di posta elettronica** , fare clic sul**+** segno più ().

4. Specificare le impostazioni seguenti:

    - Nella casella **nome** Digitare `Block malware`.

    - Nella sezione Response scegliere **Block**.

    - Nella sezione **allegato di reindirizzamento** selezionare l'opzione **Abilita reindirizzamento**e quindi specificare l'indirizzo di posta elettronica per l'amministratore o l'operatore di sicurezza dell'organizzazione che rivedrà i file rilevati.

    - Nella sezione **applicato a** scegliere **il dominio del destinatario**. Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.

5. Fare clic su **Salva**.

6. (**Passaggio aggiuntivo consigliato**) Come amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con il parametro **DisallowInfectedFileDownload** impostato su *true* per l'ambiente Office 365. In questo modo si impedisce l'apertura, lo spostamento, la copia o la condivisione di file che vengono rilevati come dannosi.  

Per ulteriori informazioni, vedere [configurare i criteri per gli allegati sicuri ATP di office 365](set-up-atp-safe-attachments-policies.md) e [abilitare Office 365 ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Criteri per i collegamenti sicuri ATP

Per configurare i [collegamenti sicuri di ATP](atp-safe-links.md), esaminare e modificare il criterio predefinito e aggiungere un criterio per utenti specifici.

1. Nel [Centro sicurezza & Compliance](https://protection.office.com)scegliere**criteri** > di **gestione** > delle minacce**ATP collegamenti sicuri**.

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

## <a name="part-3---anti-phishing-protection"></a>Parte 3-protezione anti-phishing

La [protezione anti-phishing](anti-phishing-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description). La protezione anti-phishing avanzata è disponibile in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Nella procedura seguente viene descritto come configurare un criterio anti-phishing ATP. I passaggi sono simili per la configurazione di un criterio anti-phishing (senza ATP).

1. Nel [Centro sicurezza & Compliance](https://protection.office.com), scegliere il**criterio** > di **gestione** > delle minacce**ATP anti-phishing**.

2. Fare clic su **criteri predefiniti**.

3. Nella sezione **rappresentazione** fare clic su **modifica**e quindi specificare le impostazioni seguenti:

    - Nella scheda **Aggiungi utenti da proteggere** , attiva la protezione. Aggiungere quindi gli utenti, ad esempio i membri del Consiglio dell'organizzazione, il CEO, il CFO e altri leader senior. (È possibile digitare un singolo indirizzo di posta elettronica o fare clic per visualizzare un elenco).

    - Nella scheda **Aggiungi domini da proteggere** , attiva **automaticamente Includi i domini che possiedo**. Se si dispone di domini personalizzati, aggiungere anche quelli.

    - Nella scheda **azioni** selezionare **Sposta messaggio nelle cartelle di posta indesiderata dei destinatari** per entrambi gli utenti rappresentati e per il dominio rappresentato e attiva suggerimenti per la sicurezza.

    - Nella scheda **Intelligence della cassetta postale** , verificare che l'intelligence della cassetta postale sia attivata.

    - Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**.

4. Nella sezione **spoofing** fare clic su **modifica**e quindi specificare le impostazioni seguenti:

    - Nella scheda **Impostazioni filtro spoofing** verificare che la protezione anti-spoofing sia attivata.

    - Nella scheda **azioni** scegliere Sposta messaggio nelle cartelle di posta indesiderata dei destinatari.

    - Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**. Se non sono state apportate modifiche, fare clic su **Annulla**.

5. Chiudere la pagina impostazioni di criteri predefinite.

Per ulteriori informazioni sulle opzioni relative ai criteri di anti-phishing, vedere [set up anti-phishing Policies](set-up-anti-phishing-policies.md).

## <a name="part-4---anti-spam-protection"></a>Parte 4-protezione dalla posta indesiderata

La [protezione da posta](anti-spam-protection.md) indesiderata è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).

1. Nel [Centro sicurezza & Compliance](https://protection.office.com), scegliere protezione dalla**posta**indesiderata **dei** > **criteri** > di gestione delle minacce.

2. Nella scheda **personalizzato** , attiva **impostazioni personalizzate** .

3. Espandere **criteri di filtro della posta indesiderata predefiniti**, fare clic su **modifica criteri**e quindi specificare le impostazioni seguenti:

    - Nella sezione **azioni di posta indesiderata e di massa** impostare la soglia su un valore pari a 5 o 6.

    - Nella sezione **Consenti elenchi** esaminare (e, se necessario, modificare) i propri mittenti e domini consentiti.

4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni relative ai criteri di protezione da posta indesiderata, vedere [Configure the antispam](configure-the-anti-spam-policies.md)Policy.

## <a name="part-5---additional-settings-to-configure"></a>Parte 5-impostazioni aggiuntive da configurare

Oltre alla configurazione della protezione da malware, URL e file dannosi, phishing e posta indesiderata, è consigliabile configurare le impostazioni di eliminazione automatica e registrazione di controllo di zero-hour.

### <a name="zero-hour-auto-purge-for-email"></a>Spurgo automatico zero-hour per la posta elettronica

[Spurgo automatico zero-hour](zero-hour-auto-purge.md) (ZAP) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description). Questa protezione è attivata per impostazione predefinita. Tuttavia, le condizioni seguenti devono essere soddisfatte affinché la protezione sia attiva:

- Le azioni di posta indesiderata sono impostate in modo da **spostare messaggi nella cartella posta** indesiderata nei criteri di protezione dalla [posta](anti-spam-protection.md)

- Gli utenti hanno mantenuto le [Impostazioni](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)predefinite per la posta indesiderata e non hanno disattivato la protezione della posta indesiderata.

Per ulteriori informazioni, vedere [zero-hour auto Purge-protezione da posta indesiderata e malware](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Registrazione di controllo per i report e le indagini

La registrazione di controllo è disponibile in abbonamenti che includono [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description). Per visualizzare i dati nei rapporti di protezione dalle minacce, ad esempio il [dashboard di sicurezza](security-dashboard.md), i report sulla sicurezza della [posta elettronica](view-email-security-reports.md)e l' [esploratore](use-explorer-in-security-and-compliance.md), la registrazione di controllo deve essere attivata per l'organizzazione. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Attività successive all'installazione

Dopo aver configurato le funzionalità di protezione dalle minacce, verificare la modalità di funzionamento di tali caratteristiche, rivedere e rivedere i criteri in base alle esigenze e guardare le nuove funzionalità e gli aggiornamenti dei servizi.

|cosa fare  |Risorse per ulteriori informazioni  |
|---------|---------|
|Vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione visualizzando i report    |[Dashboard di sicurezza](security-dashboard.md)<br/>[Rapporti di sicurezza della posta elettronica](view-email-security-reports.md)<br/>[Report per Office 365 ATP](view-reports-for-atp.md)<br/>[Esplora minacce](use-explorer-in-security-and-compliance.md)    |
|Rivedere e rivedere periodicamente i criteri di protezione dalle minacce in base alle esigenze    |[Secure Score](microsoft-secure-score.md)<br/>[Smart report e informazioni dettagliate](reports-and-insights-in-security-and-compliance.md)<br/>[Funzionalità di analisi e risposta alle minacce di Office 365](keep-users-safe-with-office-365-ti.md)          |
|Controllare le nuove funzionalità e gli aggiornamenti dei servizi     |[Opzioni standard e di rilascio mirato](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[Centro messaggi](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Descrizioni dei servizi](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)         |
