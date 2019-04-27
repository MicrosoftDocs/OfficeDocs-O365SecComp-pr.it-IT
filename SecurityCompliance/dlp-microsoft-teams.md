---
title: Prevenzione della perdita di dati e Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/26/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: È ora possibile applicare i criteri DLP alle chat e ai canali di Microsoft teams. Leggere questo articolo per ulteriori informazioni su come funziona.
ms.openlocfilehash: 712729972942d98afb5b3898ad357114ce1a6bae
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2019
ms.locfileid: "33367257"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevenzione della perdita di dati e Microsoft Teams

## <a name="overview-of-dlp-for-microsoft-teams"></a>Panoramica di DLP per Microsoft Teams

Recentemente, le funzionalità di [prevenzione della perdita di dati](data-loss-prevention-policies.md) (DLP) sono state estese per includere Microsoft teams. Se l'organizzazione ha DLP, è ora possibile definire criteri che impediscono agli utenti di condividere le informazioni riservate in un canale di Microsoft teams o in una sessione di chat. Di seguito sono riportati alcuni esempi del funzionamento di questa protezione:

- **Esempio 1: protezione delle informazioni riservate nei messaggi**. Si supponga che un utente tenti di condividere le informazioni riservate in una chat o un canale di team con gli ospiti (utenti esterni). Se è stato definito un criterio DLP per evitare questo, vengono eliminati i messaggi con informazioni riservate inviate a utenti esterni. Questo accade automaticamente, e in pochi secondi, in base al modo in cui viene configurato il criterio DLP.

- **Esempio 2: protezione delle informazioni riservate nei documenti**. Si supponga che un utente tenti di condividere un documento con gli utenti in un canale o in una chat di Microsoft teams e che il documento contenga informazioni riservate. Se si dispone di un criterio DLP definito per evitare questo, il documento non verrà aperto per tali utenti. Si noti che in questo caso, il criterio DLP deve includere SharePoint e OneDrive in modo che la protezione sia sul posto.

## <a name="policy-tips-help-educate-users"></a>Suggerimenti per i criteri per informare gli utenti

Analogamente a come funziona DLP in [Exchange, Outlook e Outlook sul Web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [siti di SharePoint e OneDrive for business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)e [client desktop di Office, i](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)suggerimenti per i criteri vengono visualizzati quando un'azione è in conflitto con un criterio DLP. Di seguito è riportato un esempio di suggerimento per i criteri:

![Notifica del messaggio bloccato nei team](media/dlp-teams-blockedmessage-notification.png)

In questo caso, il mittente ha tentato di condividere un numero di previdenza sociale in un canale Microsoft teams. **Che cosa è possibile fare?** collegamento consente di aprire una finestra di dialogo in cui sono disponibili opzioni per il mittente per risolvere il problema. Si noti che in questo caso, il mittente può scegliere di ignorare il criterio oppure inviare una notifica a un amministratore per verificarlo e risolverlo.

![Opzioni per la risoluzione del messaggio bloccato](media/dlp-teams-blockedmessage-possibleactions.png)

Nell'organizzazione, è possibile scegliere se consentire agli utenti di ignorare un criterio DLP o meno. Quando si configurano i criteri DLP, è possibile utilizzare i suggerimenti per i criteri predefiniti oppure [personalizzare i suggerimenti](#to-customize-policy-tips) per i criteri per l'organizzazione. 

Tornando all'esempio, in cui un mittente ha condiviso un numero di previdenza sociale in un canale teams, ecco cosa ha visto il destinatario:

![Messaggio bloccato](media/dlp-teams-blockedmessage-notification-to-user.png)

La **che cos'è?** collegamento consente di aprire un [articolo](data-loss-prevention-policies.md) sui criteri DLP, che consente di spiegare perché il messaggio è stato bloccato.

### <a name="to-customize-policy-tips"></a>Per personalizzare i suggerimenti per i criteri

Per eseguire questa attività, è necessario essere assegnati a un ruolo che disponga delle autorizzazioni per la modifica dei criteri DLP. Per ulteriori informazioni, vedere [](data-loss-prevention-policies.md#permissions)Permissions.

1. Accedere al centro conformità di Office 365 Security & ([https://protection.office.com](https://protection.office.com)) ed eseguire l'accesso.

2. Scegliere **i** > **criteri**di prevenzione della perdita di dati. 

3. Selezionare un criterio e fare clic su **modifica**accanto a **impostazioni criterio**.

4. Creare una nuova regola o modificare una regola esistente per il criterio.<br/>![Modifica di una regola per un criterio](media/dlp-teams-editrule.png)<br/>

5. Nella scheda **notifiche utente** selezionare **Personalizza il testo del messaggio di posta elettronica** e/o **Personalizza le opzioni di testo del suggerimento per i criteri** .<br/>![Personalizzare le notifiche degli utenti e i suggerimenti per i criteri](media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Specificare il testo che si desidera utilizzare per le notifiche di posta elettronica e/o suggerimenti per i criteri e quindi scegliere **Salva**. 

7. Nella scheda **impostazioni dei criteri** scegliere **Salva**.

Consentire circa un'ora affinché le modifiche vengano elaborate tramite il Data Center e sincronizzate con gli account utente.
 
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Aggiungere Microsoft teams come percorso ai criteri DLP esistenti

Per eseguire questa attività, è necessario essere assegnati a un ruolo che disponga delle autorizzazioni per la modifica dei criteri DLP. Per ulteriori informazioni, vedere [](data-loss-prevention-policies.md#permissions)Permissions.

1. Accedere al centro conformità di Office 365 Security & ([https://protection.office.com](https://protection.office.com)) ed eseguire l'accesso.

2. Scegliere **i** > **criteri**di prevenzione della perdita di dati. 

3. Selezionare un criterio e esaminare i valori in **percorsi**. Se si visualizzano **i messaggi chat e canali del team**, è tutto pronto. In caso contrario, fare clic su **modifica**.<br/>![Posizioni per i criteri esistenti](media/dlp-teams-editexistingpolicy.png)<br/>

4. Nella colonna **stato** , attiva il criterio per i **messaggi di chat e di canale dei team**.<br/>![DLP per le chat e i canali di Teams](media/dlp-teams-addteamschatschannels.png)<br/>

5. Mantenere le impostazioni predefinite di tutti gli account oppure specificare gli account da includere o escludere.

6. Fare clic su **Salva**.

Consentire circa un'ora affinché le modifiche vengano elaborate tramite il Data Center e sincronizzate con gli account utente.

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definire un nuovo criterio DLP per Microsoft Teams

Per eseguire questa attività, è necessario essere assegnati a un ruolo che disponga delle autorizzazioni per la modifica dei criteri DLP. Per ulteriori informazioni, vedere [](data-loss-prevention-policies.md#permissions)Permissions.

1. Accedere al centro conformità di Office 365 Security & ([https://protection.office.com](https://protection.office.com)) ed eseguire l'accesso.

2. Scegliere **** > **** criteri > di prevenzione della perdita**di dati + creare un criterio**. 

3. Scegliere un [modello](data-loss-prevention-policies.md#dlp-policy-templates)e quindi fare clic su **Avanti**.<br/>In questo esempio, è stato scelto il modello di dati di identificazione personale degli Stati Uniti.<br/>![Modello di privacy per i criteri DLP](media/dlp-teams-createnewpolicy-template.png)<br/>

4. Nella scheda deNominare i **criteri** specificare un nome e una descrizione per il criterio e quindi fare clic su **Avanti**. 

5. Nella scheda **Scegli percorsi** mantenere l'impostazione predefinita di tutti i percorsi oppure selezionare **Consenti percorsi specifici**e quindi scegliere **Avanti**.<br/>Se si è scelto di scegliere percorsi specifici, selezionare le posizioni per il criterio DLP e quindi scegliere **Avanti**.<br/>![Posizioni dei criteri DLP](media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > Se si desidera verificare che i documenti che contengono informazioni riservate non siano condivisi in modo improprio, verificare che i **siti di SharePoint** e gli **account di OneDrive** siano attivati insieme ai **messaggi di chat e dei canali di Team**.
<br/>

6. Nella scheda **impostazioni dei criteri** , in **Personalizza il tipo di contenuto che si desidera proteggere**, mantenere le impostazioni predefinite semplici oppure scegliere **Usa impostazioni avanzate**e quindi scegliere **Avanti**. Se si scelgono le impostazioni avanzate, è possibile creare o modificare regole per i criteri. Per ottenere assistenza, vedere [Simple Settings vs Advanced Settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).

7.  Nella scheda **impostazioni dei criteri** , in **che cosa si desidera eseguire se vengono rilevate informazioni riservate?**, esaminare le impostazioni. (Ecco dove è possibile scegliere se mantenere i suggerimenti per i [criteri e le notifiche di posta elettronica](use-notifications-and-policy-tips.md)predefiniti oppure personalizzarli).<br/>![Impostazioni dei criteri DLP con suggerimenti e notifiche](media/dlp-teams-policysettings-tipsemails.png)<br/>Dopo aver completato la revisione o la modifica delle impostazioni, scegliere **Avanti**.

8. Nella scheda **impostazioni dei criteri** , in **fare in modo che si desideri disattivare il criterio o eseguire prima un test?**, scegliere se abilitare il criterio, [testarlo prima](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)oppure tenerlo disattivato per ora, quindi scegliere **Avanti**.<br/>![Specificare se si desidera che il criterio venga attivato](media/dlp-teams-policysettings-turnonnow.png)<br/>

9. Nella scheda **Verifica le impostazioni** , esaminare le impostazioni per il nuovo criterio. Scegliere **modifica** per apportare modifiche. Al termine, scegliere **Crea**. 

Consentire a circa un'ora che il nuovo criterio funzioni correttamente attraverso il Data Center e sincronizzare gli account utente.

## <a name="related-articles"></a>Articoli correlati

[Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)

[Inviare notifiche di posta elettronica e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](use-notifications-and-policy-tips.md)
