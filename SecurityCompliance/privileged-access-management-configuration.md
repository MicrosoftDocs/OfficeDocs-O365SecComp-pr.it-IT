---
title: Configurazione di gestione con privilegi di accesso in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilizzare questo argomento per ulteriori informazioni sulla configurazione di gestione con privilegi di accesso in Office 365
ms.openlocfilehash: 13d278c8e8555aa069035c2f03b23db69a475b43
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522257"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>Configurazione di gestione con privilegi di accesso in Office 365

> [!IMPORTANT]
> In questo argomento vengono illustrate la distribuzione e configurazione indicazioni per la funzionalità attualmente disponibili solo in Office 365 E5 e avanzate SKU di conformità.

In questo argomento viene illustrato come procedura abilitazione e configurazione di gestione con privilegi di accesso nella propria organizzazione Office 365. È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Exchange Management PowerShell per gestire e utilizzare accesso privilegiato. 

## <a name="enable-and-configure-privileged-access-management"></a>Abilitare e configurare la gestione dei privilegi di accesso

Eseguire la procedura seguente per configurare e utilizzare i privilegi di accesso nella propria organizzazione Office 365:

- [Passaggio 1: Creare il gruppo del revisore](privileged-access-management-configuration.md#step1)

    Prima di iniziare a utilizzare accesso privilegi, determinare chi avrà autorità approvazione delle richieste in ingresso per l'accesso alle attività con privilegi elevate e privilegiata. Qualsiasi utente che fa parte del gruppo dei responsabili approvazione saranno in grado di approvare le richieste di accesso. Questa opzione è attivata mediante la creazione di un gruppo di protezione abilitati alla posta elettronica in Office 365.

- [Passaggio 2: Abilitare l'accesso con privilegiato](privileged-access-management-configuration.md#step2)

    Accesso privilegiato deve essere attivata in modo esplicito in Office 365 gruppo responsabile approvazione predefinito, incluso un set di account di sistema che si desidera vengano esclusi dal controllo dell'accesso Gestione accesso privilegiato.

- [Passaggio 3: Creare un criterio di accesso](privileged-access-management-configuration.md#step3)

    Creazione di criteri di approvazione consente di definire i requisiti specifici di approvazione con ambiti a singole attività. Le opzioni di tipo approvazione sono **automatica** o **manuale**.

- [Passaggio 4: Le richieste di accesso con privilegi di invio/approvare](privileged-access-management-configuration.md#step4)

    Dopo l'attivazione, con privilegiato di accesso richiede approvazioni per l'esecuzione di tutte le attività che dispone di un criterio di approvazione associato definito. Gli utenti che necessitano di eseguire le attività incluse nel necessario richiedere e concesso accesso approvazione per disporre delle autorizzazioni necessarie per eseguire l'attività di un criterio di approvazione.

Dopo l'approvazione, l'utente richiedente può eseguire l'operazione e accesso con privilegi verrà autorizzare ed eseguire l'attività per conto degli utenti. L'approvazione rimane valido per l'oggetto durata (durata predefinito è 4 ore), durante il quale il richiedente può eseguire l'operazione più volte. Tutti questi esecuzioni vengono registrate e resi disponibili per la protezione e il controllo della conformità. 

> [!NOTE]
> Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire la procedura descritta in [Connect to Exchange Online PowerShell con l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) per connettersi a Exchange Online PowerShell con Office 365 credenziali. Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione Office 365 eseguire la procedura per abilitare l'accesso con privilegiato durante la connessione a Exchange Online PowerShell. La connessione con l'autenticazione a più fattori crea un token OAuth utilizzato per l'accesso con privilegiato per le richieste di firma.

<a name="step1"> </a>

## <a name="step-1---create-an-approvers-group"></a>Passaggio 1 - creare gruppo del revisore

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione di accedere ai **gruppi** > **Aggiungi gruppo**.

3. Selezionare il tipo di gruppo **gruppo di protezione abilitati alla posta elettronica** e quindi completare i campi **nome**, **indirizzo di posta elettronica di gruppo**e **Descrizione** per il nuovo gruppo.

4. Salvare il gruppo. Potrebbe richiedere alcuni minuti per il gruppo da configurare completamente e verrà visualizzato nell'interfaccia di amministrazione di Office 365.

5. Selezionare gruppo del nuovo responsabile dell'approvazione e selezionare **Modifica** per aggiungere utenti al gruppo.

6. Salvare il gruppo.

<a name="step2"> </a>

## <a name="step-2---enable-privileged-access"></a>Passaggio 2: abilitare l'accesso con privilegiato

### <a name="using-the-microsoft-365-admin-center"></a>Utilizzando l'interfaccia di amministrazione di Microsoft 365

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione di accedere a **Impostazioni > sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Attivare il controllo **richiedono approvazioni per l'accesso con privilegiato** .

4. Assegnare il gruppo del responsabile approvazione creato nel passaggio 1 come **responsabili approvazione gruppo predefinito**.

5. **Salva** e **Chiudi**.

### <a name="using-exchange-management-powershell"></a>Utilizzo di PowerShell per Exchange Management

Eseguire il seguente comando in Exchange Online PowerShell per abilitare l'accesso con privilegiato e per assegnare gruppo al responsabile approvazione:
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
Esempio:
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> Gli account di sistema caratteristica viene resa disponibile per verificare che determinati automatizzazioni all'interno di organizzazioni possono lavorare senza dipendenza accesso privilegiato, tuttavia, è consigliabile che tali esclusioni eccezionali e quelle consentite deve essere approvati e controllati regolarmente.

<a name="step3"> </a>

## <a name="step-3---create-an-access-policy"></a>Passaggio 3: creare un criterio di accesso

È possibile creare e configurare i criteri di accesso privilegiato fino a 30 per l'organizzazione Office 365.

### <a name="using-the-microsoft-365-admin-center"></a>Utilizzando l'interfaccia di amministrazione di Microsoft 365

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Selezionare **le richieste e gestire i criteri di accesso**.

4. Selezionare **Configura criteri** e selezionare **Aggiungi un criterio**.

5. I campi di riepilogo a discesa, selezionare i valori appropriati per l'organizzazione:
    
    **Tipo di criterio**: attività, ruolo o gruppo di ruoli

    **Ambito dei criteri**: Exchange o Office 365

    **Nome del criterio**: selezionare i criteri disponibili

    **Tipo di approvazione**: manuale o automatico

    **Gruppo di approvazione**: selezionare il gruppo responsabili approvazione creato nel passaggio 1

6. Selezionare **Crea** e quindi **Chiudi**. Potrebbe richiedere alcuni minuti per il criterio da configurare e abilitare completamente.

### <a name="using-exchange-management-powershell"></a>Utilizzo di PowerShell per Exchange Management

Eseguire il comando seguente in Exchange Online PowerShell per creare e definire i criteri di approvazione:

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
Esempio:
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Passaggio 4: Le richieste di accesso con privilegi di invio/approvare

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Richiesta di autorizzazione elevazione di privilegi di eseguire attività con privilegi

Richieste di accesso con privilegiato sono valide per 24 ore dopo l'invio della richiesta. Se non è approvato negato, le richieste di scadono e l'accesso non è stato approvato.

#### <a name="using-the-microsoft-365-admin-center"></a>Utilizzando l'interfaccia di amministrazione di Microsoft 365

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali.

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Selezionare **le richieste e gestire i criteri di accesso**.

4. Selezionare **nuova richiesta**. I campi di riepilogo a discesa, selezionare i valori appropriati per l'organizzazione:

    **Tipo di richiesta**: attività, ruolo o gruppo di ruoli

    **Richiedere ambito**: Exchange

    **Richiedere per**: selezionare i criteri disponibili

    **Durata (ore)**: numero di ore di accesso richiesto. Non vi è un limite al numero di ore che possono essere richiesti.

    **Commenti**: campo di testo per i commenti relativi alla richiesta di accesso

5. Selezionare **Salva** , quindi **Chiudi**. La richiesta verrà inviata al gruppo del revisore tramite posta elettronica.

#### <a name="using-exchange-management-powershell"></a>Utilizzo di PowerShell per Exchange Management

Eseguire il comando seguente in Exchange Online PowerShell per creare e inviare una richiesta di approvazione di gruppo del revisore:
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
Esempio:
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>Visualizzare lo stato delle richieste di elevazione di privilegi
Dopo aver creata una richiesta di approvazione, per esaminare lo stato richiesta di elevazione di privilegi nell'interfaccia di amministrazione o di Exchange PowerShell Management utilizza associato con richiesta ID.

#### <a name="using-the-microsoft-365-admin-center"></a>Utilizzando l'interfaccia di amministrazione di Microsoft 365

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali.

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Selezionare **le richieste e gestire i criteri di accesso**.

4. Selezionare **Visualizza** per filtrare le richieste inviate in base allo stato **in sospeso**, **approvato**, **non consentiti**o **Archivio protetto dei clienti** .

#### <a name="using-exchange-management-powershell"></a>Utilizzo di PowerShell per Exchange Management

Eseguire il comando seguente in Exchange Online PowerShell per visualizzare lo stato richiesta di approvazione per un ID richiesta specifica:
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
Esempio:
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>L'approvazione di una richiesta di autorizzazione elevazione
Quando si crea una richiesta di approvazione, i membri del gruppo responsabile approvazione pertinenti riceveranno una notifica tramite posta elettronica e autorizzati ad approvare la richiesta associata all'ID richiesta. Il richiedente riceverà una notifica dell'approvazione richieste o di tipo denial tramite messaggio di posta elettronica.

#### <a name="using-the-microsoft-365-admin-center"></a>Utilizzando l'interfaccia di amministrazione di Microsoft 365

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali.

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Selezionare **le richieste e gestire i criteri di accesso**.

4. Selezionare una richiesta elencata per visualizzare i dettagli e per eseguire l'azione necessaria la richiesta.

5. Selezionare **Approva** per approvare la richiesta o selezionare **Nega** per rifiutare la richiesta. Le richieste approvate in precedenza possono avere revocato selezionando **revocare**l'accesso.

#### <a name="using-exchange-management-powershell"></a>Utilizzo di PowerShell per Exchange Management

Eseguire il comando seguente in Exchange Online PowerShell per approvare una richiesta di autorizzazione elevazione:

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
Esempio:
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Eseguire il comando seguente in Exchange Online PowerShell per rifiutare una richiesta di autorizzazione elevazione:

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
Esempio:
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Eliminare un criterio di accesso privilegiato in Office 365
Se non è più necessario all'interno dell'organizzazione, è possibile eliminare un criterio di accesso privilegiato.

### <a name="using-the-microsoft-365-admin-center"></a>Utilizzando l'interfaccia di amministrazione di Microsoft 365

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Selezionare **le richieste e gestire i criteri di accesso**.

4. Selezionare **Configura criteri**.

5. Selezionare il criterio che si desidera eliminare e quindi selezionare **Rimuovi elemento**.

6. Selezionare **Chiudi**.

### <a name="using-exchange-management-powershell"></a>Utilizzo di PowerShell per Exchange Management

Eseguire il comando seguente in Exchange Online Powershell per eliminare un criterio di accesso con privilegi:

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Disabilitare l'accesso con privilegiato in Office 365

Se necessario, è possibile disabilitare gestione con privilegi di accesso per l'organizzazione. Disattivazione con privilegi accesso non vengono eliminati tutti criteri di approvazione associato o i gruppi di responsabile approvazione.

### <a name="using-the-microsoft-365-admin-center"></a>Utilizzando l'interfaccia di amministrazione di Microsoft 365

1. Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.

3. Attivare il controllo **richiedono approvazioni per l'accesso con privilegiato** .

### <a name="using-exchange-management-powershell"></a>Utilizzo di PowerShell per Exchange Management

Eseguire il comando seguente in Exchange Online Powershell per disabilitare l'accesso con privilegiato:

```
Disable-ElevatedAccessControl
```