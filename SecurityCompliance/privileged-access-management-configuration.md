---
title: Configurazione della gestione degli accessi con privilegi in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilizzare questo argomento per ulteriori informazioni sulla configurazione della gestione degli accessi con privilegi in Office 365
ms.openlocfilehash: 9d0f5955eb2fd67d245bad3e7a9b1b89769bd947
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001149"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>Configurazione della gestione degli accessi con privilegi in Office 365

> [!IMPORTANT]
> In questo argomento vengono illustrate le linee guida per la distribuzione e la configurazione per le funzionalità disponibili solo in Office 365 E5 e SKU di conformità avanzate.

In questo argomento viene illustrata l'abilitazione e la configurazione della gestione degli accessi con privilegi nell'organizzazione di Office 365. È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Exchange Management PowerShell per gestire e utilizzare accesso privilegiato. 

## <a name="enable-and-configure-privileged-access-management"></a>Abilitare e configurare la gestione degli accessi con privilegi

Seguire questa procedura per configurare e usare l'accesso privilegiato nell'organizzazione di Office 365:

- [Passaggio 1: creare un gruppo del responsabile approvazione](privileged-access-management-configuration.md#step1)

    Prima di iniziare a utilizzare l'accesso ai privilegi, determinare chi avrà l'autorità di approvazione per le richieste in arrivo per l'accesso a attività con privilegi elevati. Qualsiasi utente che fa parte del gruppo responsabili approvazione sarà in grado di approvare le richieste di accesso. Questa impostazione viene abilitata creando un gruppo di sicurezza abilitato alla posta elettronica in Office 365.

- [Passaggio 2: abilitare l'accesso con privilegi](privileged-access-management-configuration.md#step2)

    L'accesso privilegiato deve essere attivato in modo esplicito in Office 365 con il gruppo di approvazione predefinito e includendo un set di account di sistema che si desidera escludere dal controllo di accesso a gestione accesso privilegiato.

- [Passaggio 3: creare un criterio di accesso](privileged-access-management-configuration.md#step3)

    La creazione di un criterio di approvazione consente di definire i requisiti di approvazione specifici con ambito a singole attività. Le opzioni relative al tipo **** di approvazione sono automatiche o **manuali**.

- [Passaggio 4: invio/approvazione delle richieste di accesso privilegiate](privileged-access-management-configuration.md#step4)

    Una volta abilitata, l'accesso con privilegi richiede le approvazioni per l'esecuzione di tutte le attività che hanno un criterio di approvazione associato definito. Gli utenti che desiderano eseguire le attività incluse nel criterio di approvazione devono richiedere e ricevere l'approvazione dell'accesso per avere le autorizzazioni necessarie per eseguire l'attività.

Dopo aver concesso l'approvazione, l'utente richiedente può eseguire l'attività desiderata e l'accesso privilegiato autorizzerà ed eseguirà l'attività a nome degli utenti. L'approvazione rimane valida per la durata richiesta (la durata predefinita è di 4 ore), durante la quale il richiedente può eseguire l'attività desiderata più volte. Tutte queste esecuzioni vengono registrate e rese disponibili per il controllo di sicurezza e conformità. 

> [!NOTE]
> Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire la procedura descritta in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to Connect to Exchange Online PowerShell with your Office 365 credenziali. Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione di Office 365 per l'utilizzo dei passaggi per abilitare l'accesso privilegiato durante la connessione a PowerShell di Exchange Online. La connessione con l'autenticazione a più fattori consente di creare un token OAuth utilizzato dall'accesso privilegiato per la firma delle richieste.

<a name="step1"> </a>

## <a name="step-1---create-an-approvers-group"></a>Passaggio 1: creare un gruppo del responsabile approvazione

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, andare a **gruppi** > **aggiungere un gruppo**.

3. Selezionare il tipo di gruppo gruppo di **sicurezza abilitato alla posta elettronica** e quindi completare il **nome**, l' **indirizzo di posta elettronica del gruppo**e i campi **Descrizione** per il nuovo gruppo.

4. Salvare il gruppo. Il gruppo può richiedere alcuni minuti completamente configurati e comparire nell'interfaccia di amministrazione di Microsoft 365.

5. Selezionare il gruppo del nuovo responsabile approvazione e selezionare **modifica** per aggiungere gli utenti al gruppo.

6. Salvare il gruppo.

<a name="step2"> </a>

## <a name="step-2---enable-privileged-access"></a>Passaggio 2: abilitare l'accesso con privilegi

### <a name="using-the-microsoft-365-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, passare a **Impostazioni > sicurezza & privacy** > **accesso privilegiato**.

3. Abilitare le **autorizzazioni necessarie per il controllo di accesso privilegiato** .

4. Assegnare il gruppo del responsabile approvazione creato nel passaggio 1 come **gruppo dei responsabili approvazione predefiniti**.

5. **Salva** e **Chiudi**.

### <a name="using-exchange-management-powershell"></a>Utilizzo di Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per abilitare l'accesso con privilegi e assegnare il gruppo del responsabile dell'approvazione:
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
Esempio:
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> La funzionalità account di sistema è disponibile per garantire che alcuni automatismi all'interno delle organizzazioni possano funzionare senza dipendenze dall'accesso privilegiato, tuttavia è consigliabile che tali esclusioni siano eccezionali e quelle consentite debbano essere approvate e controllate regolarmente.

<a name="step3"> </a>

## <a name="step-3---create-an-access-policy"></a>Passaggio 3: creare un criterio di accesso

È possibile creare e configurare fino a 30 criteri di accesso privilegiato per l'organizzazione di Office 365.

### <a name="using-the-microsoft-365-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **Configure policies** e selezionare **Add a Policy**.

5. Nei campi a discesa selezionare i valori corretti per l'organizzazione:
    
    **Tipo di criterio**: attività, ruolo o gruppo di ruoli

    **Ambito di criteri**: Exchange

    **Nome criterio**: scegliere tra i criteri disponibili

    **Tipo di approvazione**: manuale o automatico

    **Gruppo di approvazione**: selezionare il gruppo responsabili approvazione creato nel passaggio 1

6. Selezionare **Crea** e quindi **Chiudi**. È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti.

### <a name="using-exchange-management-powershell"></a>Utilizzo di Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per creare e definire un criterio di approvazione:

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
Esempio:
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Passaggio 4: invio/approvazione delle richieste di accesso privilegiate

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Richiesta di autorizzazione all'elevazione per l'esecuzione di attività privilegiate

Le richieste di accesso con privilegi sono valide per un massimo di 24 ore dopo l'invio della richiesta. Se non è stato approvato o negato, le richieste scadono e Access non è approvato.

#### <a name="using-the-microsoft-365-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le proprie credenziali.

2. Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **nuova richiesta**. Nei campi a discesa selezionare i valori corretti per l'organizzazione:

    **Tipo di richiesta**: attività, ruolo o gruppo di ruoli

    **Ambito delle richieste**: Exchange

    **Richiesta per**: selezionare i criteri disponibili

    **Durata (ore)**: numero di ore di accesso richiesto. Non è previsto un limite per il numero di ore che è possibile richiedere.

    **Commenti**: campo di testo per i commenti relativi alla richiesta di accesso

5. Selezionare **Salva** e quindi **Chiudi**. La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.

#### <a name="using-exchange-management-powershell"></a>Utilizzo di Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per creare e inviare una richiesta di approvazione al gruppo del responsabile dell'approvazione:
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
Esempio:
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>Visualizzare lo stato delle richieste di elevazione
Dopo la creazione di una richiesta di approvazione, lo stato della richiesta di elevazione può essere esaminato nell'interfaccia di amministrazione o in Exchange Management PowerShell utilizzando l'ID della richiesta associato.

#### <a name="using-the-microsoft-365-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le proprie credenziali.

2. Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **Visualizza** per filtrare le richieste inviate mediante lo stato **in sospeso**, **approvato**, **negato**o **protetto dall'archivio dei clienti** .

#### <a name="using-exchange-management-powershell"></a>Utilizzo di Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare lo stato di una richiesta di approvazione per un ID di richiesta specifico:
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
Esempio:
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Approvazione di una richiesta di autorizzazione elevazione
Quando viene creata una richiesta di approvazione, i membri del gruppo responsabile approvazione ricevono una notifica tramite posta elettronica e possono approvare la richiesta associata all'ID della richiesta. Il richiedente riceverà una notifica dell'approvazione o della negazione della richiesta tramite il messaggio di posta elettronica.

#### <a name="using-the-microsoft-365-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le proprie credenziali.

2. Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare una richiesta elencata per visualizzare i dettagli e per eseguire l'azione sulla richiesta.

5. Selezionare **approva** per approvare la richiesta oppure selezionare **Nega** per rifiutare la richiesta. Le richieste approvate in precedenza possono avere accesso revocato selezionando **revoca**.

#### <a name="using-exchange-management-powershell"></a>Utilizzo di Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per approvare una richiesta di autorizzazione elevazione:

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
Esempio:
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Eseguire il seguente comando in PowerShell di Exchange Online per negare una richiesta di autorizzazione elevazione:

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
Esempio:
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Eliminare un criterio di accesso con privilegi in Office 365
È possibile eliminare un criterio di accesso con privilegi se non è più necessario nell'organizzazione.

### <a name="using-the-microsoft-365-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **Configure policies**.

5. Selezionare il criterio che si desidera eliminare, quindi selezionare **Rimuovi criterio**.

6. Selezionare **Chiudi**.

### <a name="using-exchange-management-powershell"></a>Utilizzo di Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per eliminare un criterio di accesso privilegiato:

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Disabilitare l'accesso con privilegi in Office 365

Se necessario, è possibile disabilitare la gestione degli accessi con privilegi per l'organizzazione. La disabilitazione dell'accesso con privilegi non comporta l'eliminazione di criteri di approvazione associati o gruppi di approvatori.

### <a name="using-the-microsoft-365-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.

3. Abilitare le **autorizzazioni necessarie per il controllo di accesso privilegiato** .

### <a name="using-exchange-management-powershell"></a>Utilizzo di Exchange Management PowerShell

Eseguire il seguente comando in PowerShell di Exchange Online per disabilitare l'accesso con privilegi:

```
Disable-ElevatedAccessControl
```