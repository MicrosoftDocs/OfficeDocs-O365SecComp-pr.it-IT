---
title: Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: Gli amministratori possono viene illustrato come creare posta flusso regole (noto anche come regole di trasporto) per la crittografia e decrittografia con Office 365 messaggio crittografia dei messaggi.
ms.openlocfilehash: ce6b1ce60abb58c5f4e217c66bca013101af5f91
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749360"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365

Amministratore globale di Office 365, è possibile creare posta regole del flusso (noto anche come regole di trasporto) per garantire la protezione dei messaggi di posta elettronica inviati e ricevuti. È possibile impostare le regole per crittografare eventuali messaggi di posta elettronica in uscita e rimuovere la crittografia di messaggi crittografati provenienti da all'interno dell'organizzazione o da risposte ai messaggi crittografati inviati dall'organizzazione. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o Exchange Online PowerShell per creare queste regole. Oltre alle regole di crittografia generale, è possibile abilitare o disabilitare le opzioni di crittografia dei messaggi per gli utenti finali.

Se la migrazione di recente da AD RMS per la protezione delle informazioni di Azure, è necessario controllare le regole di flusso di posta elettronica esistente per garantire che continuano a funzionare nel nuovo ambiente. Inoltre, se si desidera usufruire delle nuove funzionalità di Office 365 messaggio crittografia dei disponibili per l'utente attraverso la protezione delle informazioni di Azure, è necessario aggiornare le regole di flusso di posta elettronica esistente. In caso contrario, gli utenti continua a ricevere messaggi crittografati che utilizza il formato allegato HTML precedente anziché l'esperienza OME nuova e semplice. Se è stata impostata OME ancora, vedere [impostare le nuove funzionalità di Office 365 Message Encryption basate sul Azure Information Protection](set-up-new-message-encryption-capabilities.md) per informazioni.

Per informazioni sui componenti che costituiscono le regole del flusso di posta elettronica e come le regole di flusso di posta, vedere [(regole di trasporto) le regole di flusso di posta in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Per ulteriori informazioni sul funzionano delle regole del flusso di posta elettronica con Azure Information Protection, vedere [configurazione di Exchange Online regole del flusso di posta elettronica per le etichette di protezione delle informazioni Azure](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Per ambienti ibridi Exchange, gli utenti locali possono inviare messaggi crittografati tramite OME solo se posta elettronica viene instradata tramite Exchange Online. Per configurare OME in un ambiente ibrido di Exchange, è necessario prima [Configurazione ibrida utilizzando la procedura guidata di configurazione ibrida](https://docs.microsoft.com/Exchange/exchange-hybrid) e quindi [configurare la posta per trasmettere dal server di posta elettronica a Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Una volta è stato configurato la posta passi attraverso Office 365, quindi è possibile configurare le regole di flusso di posta elettronica per OME utilizzando questa Guida.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Creare regole per crittografare i messaggi di posta elettronica con le nuove funzionalità OME del flusso di posta elettronica

È possibile definire regole del flusso di posta elettronica per l'attivazione della crittografia dei messaggi con le nuove funzionalità OME utilizzando la shell.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Utilizzare EAC per creare una regola per la crittografia dei messaggi di posta elettronica con le nuove funzionalità OME

1. In un web browser utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere le sezioni di **amministrazione** .

3. In interfaccia di amministrazione di Office 365, scegliere **Interfacce di amministrazione** \> **Exchange**.

4. In EAC, andare a **flusso di posta** \> **regole** e selezionare **New** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Crea una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**digitare un nome per la regola, come Encrypt mail for DrToniRamos@hotmail.com.

6. In **Applica questa regola se** selezionare una condizione e, se necessario, immettere un valore. Ad esempio, per crittografare i messaggi indirizzati a DrToniRamos@hotmail.com:

   1. In **Applica questa regola se**, selezionare **il destinatario è**.

   2. Selezionare un nome esistente dall'elenco dei contatti o digitare un nuovo indirizzo di posta elettronica nella casella **Controlla nomi**.
    
      - Per selezionare un nome esistente, selezionarlo dall'elenco e quindi fare clic su **OK**.

      - Immettere un nuovo nome, digitare un indirizzo di posta elettronica nella casella di **controllo dei nomi** e quindi selezionare **Controlla nomi** \> **OK**.

7. Per aggiungere ulteriori condizioni, selezionare **altre opzioni** e scegliere **Aggiungi condizione** e selezionare dall'elenco.

   Ad esempio, per applicare la regola solo se il destinatario si trova all'esterno dell'organizzazione, selezionare **Aggiungi condizione** e quindi selezionare **il destinatario è interno/esterno** \> **all'esterno dell'organizzazione** \> **OK**.

8. Per abilitare la crittografia utilizzando le nuove funzionalità OME, da **eseguire le operazioni seguenti**, selezionare **Modifica la sicurezza del messaggio** e quindi scegliere **Applica crittografia messaggi Office 365 e protezione dei diritti**. Selezionare un modello RMS dall'elenco, scegliere **Salva**e quindi fare clic su **OK**.
  
  L'elenco dei modelli include tutti i modelli predefiniti e le opzioni e i modelli personalizzati creati per utilizzano Office 365. Se l'elenco è vuoto, verificare che sono state impostate la crittografia dei messaggi di Office 365 con le nuove funzionalità come descritto in [impostare le nuove funzionalità di Office 365 Message Encryption incorporata nella parte superiore della protezione delle informazioni Azure](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [configurazione e gestione dei modelli per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni sull'opzione **Non inoltrare** , vedere [opzione non inoltrare per messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Per informazioni sull'opzione **crittografare solo** , vedere [opzione crittografare solo per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  È possibile scegliere **Aggiungi azione** se si desidera specificare un'altra azione.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Utilizzare EAC per aggiornare una regola di flusso di posta esistente per utilizzare le nuove funzionalità OME

1. In un web browser utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere le sezioni di **amministrazione** .

3. In interfaccia di amministrazione di Office 365, scegliere **Interfacce di amministrazione** \> **Exchange**.

4. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

5. Nell'elenco delle regole del flusso di posta elettronica, selezionare la regola che si desidera modificare per utilizzare le nuove funzionalità OME e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).

6. Per abilitare la crittografia utilizzando le nuove funzionalità OME, da **eseguire le operazioni seguenti**, scegliere **Modifica la sicurezza del messaggio** , quindi **applicare Office 365 Message Encryption e protezione dei diritti**. Selezionare un modello RMS dall'elenco, scegliere **Salva** e quindi fare clic su **OK**.

   L'elenco dei modelli include tutti i modelli predefiniti e le opzioni e i modelli personalizzati creati per utilizzano Office 365. Se l'elenco è vuoto, verificare che sono state impostate la crittografia dei messaggi di Office 365 con le nuove funzionalità come descritto in [impostare le nuove funzionalità di Office 365 Message Encryption incorporata nella parte superiore della protezione delle informazioni Azure](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [configurazione e gestione dei modelli per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni sull'opzione **Non inoltrare** , vedere [opzione non inoltrare per messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Per informazioni sull'opzione **crittografare solo** , vedere [opzione crittografare solo per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   È possibile scegliere **Aggiungi azione** se si desidera specificare un'altra azione.

7. Dall'elenco **eseguire le operazioni seguenti** , rimuovere tutte le azioni che sono assegnate al **Modifica la sicurezza del messaggio** \> **Applica alla versione precedente di OME**.

8. Scegliere **Save**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Creare regole del flusso di posta per Office 365 Message Encryption senza le nuove funzionalità

Se non è ancora passati organizzazione Office 365 per le nuove funzionalità OME, utilizzare queste attività per definire le regole del flusso di posta elettronica per crittografare i messaggi per l'organizzazione. Microsoft consiglia che si intende spostare le nuove funzionalità OME non appena è ragionevole per l'organizzazione. Per ulteriori informazioni, vedere [impostare le nuove funzionalità di Office 365 Message Encryption basate sulla protezione delle informazioni di Azure](set-up-new-message-encryption-capabilities.md).

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Utilizzare EAC per creare una regola di flusso di posta elettronica per la crittografia dei messaggi di posta elettronica senza le nuove funzionalità OME

1. In un web browser utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere le sezioni di **amministrazione** .

3. In interfaccia di amministrazione di Office 365, scegliere **Interfacce di amministrazione** \> **Exchange**.

4. In EAC, andare a **flusso di posta** \> **regole** e selezionare **New** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Crea una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**digitare un nome per la regola, come Encrypt mail for DrToniRamos@hotmail.com.

6. In **Applica questa regola se** selezionare una condizione e, se necessario, immettere un valore. Ad esempio, per crittografare i messaggi indirizzati a DrToniRamos@hotmail.com: 

   1. In **Applica questa regola se**, selezionare **il destinatario è**.

   2. Selezionare un nome esistente dall'elenco dei contatti o digitare un nuovo indirizzo di posta elettronica nella casella **Controlla nomi**.

      - Per selezionare un nome esistente, selezionarlo dall'elenco e quindi fare clic su **OK**.

      - Immettere un nuovo nome, digitare un indirizzo di posta elettronica nella casella di **controllo dei nomi** e quindi selezionare **Controlla nomi** \> **OK**.

7. Per aggiungere ulteriori condizioni, selezionare **altre opzioni** e quindi selezionare **Aggiungi condizione** e selezionare dall'elenco.

   Ad esempio, per applicare la regola solo se il destinatario si trova all'esterno dell'organizzazione, selezionare **Aggiungi condizione** e quindi selezionare **il destinatario è interno/esterno** \> **all'esterno dell'organizzazione** \> **OK**.

8. Per abilitare la crittografia senza utilizzare le nuove funzionalità OME in **effettuare le seguenti operazioni**, selezionare **Modifica la sicurezza del messaggio** \> **Applica alla versione precedente di OME**e quindi fare clic su **Salva**.

  Se viene visualizzato un errore di licenza IRM non è abilitato e quindi è stata impostata per l'organizzazione ancora OME. Se si desidera impostare OME a questo punto, è necessario impostare da utilizzare le nuove funzionalità OME. Per informazioni, vedere [impostare le nuove funzionalità di Office 365 Message Encryption basate sulla protezione delle informazioni di Azure](set-up-new-message-encryption-capabilities.md). Microsoft non è più supportata la configurazione di nuove distribuzioni di OME senza le nuove funzionalità.

  È possibile scegliere **Aggiungi azione** se si desidera specificare un'altra azione.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Utilizzare Exchange Online PowerShell per creare una regola di flusso di posta elettronica per la crittografia dei messaggi di posta elettronica senza le nuove funzionalità OME

1. Connessione a Exchange Online PowerShell. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Creare una regola utilizzando il cmdlet **New-TransportRule** e impostare il parametro _ApplyOME_ su `$true`.

   In questo esempio richiede che tutti i messaggi di posta elettronica inviati a DrToniRamos@hotmail.com devono essere crittografati.

   ```
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **Note**:

   - Il nome univoco della nuova regola è "Crittografa regola per Dott Toni Ramos".

   - Il parametro _SentTo_ consente di specificare i destinatari del messaggio (identificati dal nome, indirizzo di posta elettronica, il nome distinto, ecc.). In questo esempio, il destinatario identificato dall'indirizzo di posta elettronica "DrToniRamos@hotmail.com".

   - Il parametro _SentToScope_ specifica la posizione dei destinatari del messaggio. In questo esempio cassetta postale del destinatario è Hotmail e non fa parte dell'organizzazione di Office 365, pertanto il valore `NotInOrganization` viene utilizzata.

   Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Rimuovere la crittografia dalle risposte di posta elettronica crittografate senza le nuove funzionalità OME

Quando gli utenti di posta elettronica inviano messaggi crittografati, i destinatari dei messaggi possono rispondere con le risposte crittografate. È possibile creare stampa le regole di flusso per rimuovere la crittografia dalle risposte automaticamente in modo che gli utenti di posta elettronica all'interno dell'organizzazione non sono necessario accedere al portale di crittografia per visualizzarli. È possibile utilizzare i cmdlet di Exchange o Windows PowerShell per definire le regole. Se non si è ancora utilizzando le nuove funzionalità OME, è possibile solo decrittografare i messaggi vengono inviati all'interno dell'organizzazione o le risposte ai messaggi inviati da all'interno dell'organizzazione. È possibile decrittografare i messaggi provenienti da esterni all'organizzazione.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Utilizzare EAC per creare una regola per la rimozione di crittografia da risposte di posta elettronica crittografate senza le nuove funzionalità OME

1. In un web browser utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere le sezioni di **amministrazione** .

3. In interfaccia di amministrazione di Office 365, scegliere **Interfacce di amministrazione** \> **Exchange**.

4. In EAC, andare a **flusso di posta** \> **regole** e selezionare **New** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Crea una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**digitare un nome per la regola, come Remove encryption from posta in arrivo.

6. In **Applica questa regola se** , selezionare le condizioni in cui la crittografia deve essere rimossa dai messaggi, ad esempio **il destinatario si trova** \> **all'interno dell'organizzazione**.

7. Nell' **effettuare le seguenti operazioni**, selezionare **Modifica la sicurezza del messaggio** \> **rimuovere le versioni precedenti di OME**.

8. Selezionare **Salva**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Utilizzare Exchange Online PowerShell per creare una regola per rimuovere la crittografia dalle risposte di posta elettronica crittografate senza le nuove funzionalità OME

1. Connessione a Exchange Online PowerShell. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Creare una regola utilizzando il cmdlet **New-TransportRule** e impostare il parametro _RemoveOME_ su `$true`.

   In questo esempio consente di rimuovere la crittografia di tutti i messaggi inviati a destinatari nell'organizzazione di Office 365.

   ```
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **Note**:

   - Il nome univoco della nuova regola è "Remove encryption from incoming mail".

   - Il parametro _SentToScope_ specifica la posizione dei destinatari del messaggio. In questo esempio, il valore `InOrganization` valore viene utilizzato, che indica: 

     - Il destinatario è una cassetta postale, l'utente di posta elettronica, gruppo o cartelle pubbliche abilitate alla posta nell'organizzazione.

       oppure

     - Indirizzo di posta elettronica del destinatario è in un dominio accettato è configurato come dominio di inoltro interno dell'organizzazione _e_ il messaggio è stato inviato o ricevuto tramite una connessione autenticata o un dominio attendibile.

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

## <a name="related-topics"></a>Argomenti correlati

[Crittografia in Office 365](encryption.md)

[Impostare le nuove funzionalità di Office 365 Message Encryption basate sulla protezione delle informazioni di Azure](set-up-new-message-encryption-capabilities.md)

[Aggiungere personalizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md)

[Regole del flusso (regole di trasporto) di posta in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Regole del flusso di posta (regole di trasporto in Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=506708)
