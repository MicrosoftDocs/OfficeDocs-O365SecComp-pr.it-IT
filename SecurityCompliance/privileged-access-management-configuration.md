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
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="8fd2f-103">Configurazione di gestione con privilegi di accesso in Office 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fd2f-104">In questo argomento vengono illustrate la distribuzione e configurazione indicazioni per la funzionalità attualmente disponibili solo in Office 365 E5 e avanzate SKU di conformità.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="8fd2f-p101">In questo argomento viene illustrato come procedura abilitazione e configurazione di gestione con privilegi di accesso nella propria organizzazione Office 365. È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Exchange Management PowerShell per gestire e utilizzare accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="8fd2f-107">Abilitare e configurare la gestione dei privilegi di accesso</span><span class="sxs-lookup"><span data-stu-id="8fd2f-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="8fd2f-108">Eseguire la procedura seguente per configurare e utilizzare i privilegi di accesso nella propria organizzazione Office 365:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="8fd2f-109">Passaggio 1: Creare il gruppo del revisore</span><span class="sxs-lookup"><span data-stu-id="8fd2f-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="8fd2f-p102">Prima di iniziare a utilizzare accesso privilegi, determinare chi avrà autorità approvazione delle richieste in ingresso per l'accesso alle attività con privilegi elevate e privilegiata. Qualsiasi utente che fa parte del gruppo dei responsabili approvazione saranno in grado di approvare le richieste di accesso. Questa opzione è attivata mediante la creazione di un gruppo di protezione abilitati alla posta elettronica in Office 365.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="8fd2f-113">Passaggio 2: Abilitare l'accesso con privilegiato</span><span class="sxs-lookup"><span data-stu-id="8fd2f-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="8fd2f-114">Accesso privilegiato deve essere attivata in modo esplicito in Office 365 gruppo responsabile approvazione predefinito, incluso un set di account di sistema che si desidera vengano esclusi dal controllo dell'accesso Gestione accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="8fd2f-115">Passaggio 3: Creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="8fd2f-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="8fd2f-p103">Creazione di criteri di approvazione consente di definire i requisiti specifici di approvazione con ambiti a singole attività. Le opzioni di tipo approvazione sono **automatica** o **manuale**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="8fd2f-118">Passaggio 4: Le richieste di accesso con privilegi di invio/approvare</span><span class="sxs-lookup"><span data-stu-id="8fd2f-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="8fd2f-p104">Dopo l'attivazione, con privilegiato di accesso richiede approvazioni per l'esecuzione di tutte le attività che dispone di un criterio di approvazione associato definito. Gli utenti che necessitano di eseguire le attività incluse nel necessario richiedere e concesso accesso approvazione per disporre delle autorizzazioni necessarie per eseguire l'attività di un criterio di approvazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="8fd2f-p105">Dopo l'approvazione, l'utente richiedente può eseguire l'operazione e accesso con privilegi verrà autorizzare ed eseguire l'attività per conto degli utenti. L'approvazione rimane valido per l'oggetto durata (durata predefinito è 4 ore), durante il quale il richiedente può eseguire l'operazione più volte. Tutti questi esecuzioni vengono registrate e resi disponibili per la protezione e il controllo della conformità.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="8fd2f-p106">Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire la procedura descritta in [Connect to Exchange Online PowerShell con l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) per connettersi a Exchange Online PowerShell con Office 365 credenziali. Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione Office 365 eseguire la procedura per abilitare l'accesso con privilegiato durante la connessione a Exchange Online PowerShell. La connessione con l'autenticazione a più fattori crea un token OAuth utilizzato per l'accesso con privilegiato per le richieste di firma.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="8fd2f-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="8fd2f-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="8fd2f-128">Passaggio 1 - creare gruppo del revisore</span><span class="sxs-lookup"><span data-stu-id="8fd2f-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="8fd2f-129">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8fd2f-130">Nell'interfaccia di amministrazione di accedere ai **gruppi** > **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="8fd2f-131">Selezionare il tipo di gruppo **gruppo di protezione abilitati alla posta elettronica** e quindi completare i campi **nome**, **indirizzo di posta elettronica di gruppo**e **Descrizione** per il nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="8fd2f-p107">Salvare il gruppo. Potrebbe richiedere alcuni minuti per il gruppo da configurare completamente e verrà visualizzato nell'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="8fd2f-134">Selezionare gruppo del nuovo responsabile dell'approvazione e selezionare **Modifica** per aggiungere utenti al gruppo.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="8fd2f-135">Salvare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-135">Save the group.</span></span>

<span data-ttu-id="8fd2f-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="8fd2f-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="8fd2f-137">Passaggio 2: abilitare l'accesso con privilegiato</span><span class="sxs-lookup"><span data-stu-id="8fd2f-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8fd2f-138">Utilizzando l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8fd2f-139">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8fd2f-140">Nell'interfaccia di amministrazione di accedere a **Impostazioni > sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8fd2f-141">Attivare il controllo **richiedono approvazioni per l'accesso con privilegiato** .</span><span class="sxs-lookup"><span data-stu-id="8fd2f-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="8fd2f-142">Assegnare il gruppo del responsabile approvazione creato nel passaggio 1 come **responsabili approvazione gruppo predefinito**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="8fd2f-143">**Salva** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="8fd2f-144">Utilizzo di PowerShell per Exchange Management</span><span class="sxs-lookup"><span data-stu-id="8fd2f-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="8fd2f-145">Eseguire il seguente comando in Exchange Online PowerShell per abilitare l'accesso con privilegiato e per assegnare gruppo al responsabile approvazione:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="8fd2f-146">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="8fd2f-147">Gli account di sistema caratteristica viene resa disponibile per verificare che determinati automatizzazioni all'interno di organizzazioni possono lavorare senza dipendenza accesso privilegiato, tuttavia, è consigliabile che tali esclusioni eccezionali e quelle consentite deve essere approvati e controllati regolarmente.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="8fd2f-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="8fd2f-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="8fd2f-149">Passaggio 3: creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="8fd2f-149">Step 3 - Create an access policy</span></span>

<span data-ttu-id="8fd2f-150">È possibile creare e configurare i criteri di accesso privilegiato fino a 30 per l'organizzazione Office 365.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8fd2f-151">Utilizzando l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-151">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8fd2f-152">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8fd2f-153">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8fd2f-154">Selezionare **le richieste e gestire i criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8fd2f-155">Selezionare **Configura criteri** e selezionare **Aggiungi un criterio**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="8fd2f-156">I campi di riepilogo a discesa, selezionare i valori appropriati per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="8fd2f-157">**Tipo di criterio**: attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="8fd2f-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="8fd2f-158">**Ambito dei criteri**: Exchange o Office 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-158">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="8fd2f-159">**Nome del criterio**: selezionare i criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="8fd2f-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="8fd2f-160">**Tipo di approvazione**: manuale o automatico</span><span class="sxs-lookup"><span data-stu-id="8fd2f-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="8fd2f-161">**Gruppo di approvazione**: selezionare il gruppo responsabili approvazione creato nel passaggio 1</span><span class="sxs-lookup"><span data-stu-id="8fd2f-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="8fd2f-p108">Selezionare **Crea** e quindi **Chiudi**. Potrebbe richiedere alcuni minuti per il criterio da configurare e abilitare completamente.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="8fd2f-164">Utilizzo di PowerShell per Exchange Management</span><span class="sxs-lookup"><span data-stu-id="8fd2f-164">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="8fd2f-165">Eseguire il comando seguente in Exchange Online PowerShell per creare e definire i criteri di approvazione:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-165">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="8fd2f-166">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="8fd2f-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="8fd2f-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="8fd2f-168">Passaggio 4: Le richieste di accesso con privilegi di invio/approvare</span><span class="sxs-lookup"><span data-stu-id="8fd2f-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="8fd2f-169">Richiesta di autorizzazione elevazione di privilegi di eseguire attività con privilegi</span><span class="sxs-lookup"><span data-stu-id="8fd2f-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="8fd2f-p109">Richieste di accesso con privilegiato sono valide per 24 ore dopo l'invio della richiesta. Se non è approvato negato, le richieste di scadono e l'accesso non è stato approvato.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p109">Requests for privileged access are valid for up to 24 hours after the request is submitted. If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8fd2f-172">Utilizzando l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-172">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8fd2f-173">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-173">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="8fd2f-174">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8fd2f-175">Selezionare **le richieste e gestire i criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8fd2f-p110">Selezionare **nuova richiesta**. I campi di riepilogo a discesa, selezionare i valori appropriati per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p110">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="8fd2f-178">**Tipo di richiesta**: attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="8fd2f-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="8fd2f-179">**Richiedere ambito**: Exchange</span><span class="sxs-lookup"><span data-stu-id="8fd2f-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="8fd2f-180">**Richiedere per**: selezionare i criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="8fd2f-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="8fd2f-p111">**Durata (ore)**: numero di ore di accesso richiesto. Non vi è un limite al numero di ore che possono essere richiesti.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p111">**Duration (hours)**: Number of hours of requested access. There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="8fd2f-183">**Commenti**: campo di testo per i commenti relativi alla richiesta di accesso</span><span class="sxs-lookup"><span data-stu-id="8fd2f-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="8fd2f-p112">Selezionare **Salva** , quindi **Chiudi**. La richiesta verrà inviata al gruppo del revisore tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p112">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="8fd2f-186">Utilizzo di PowerShell per Exchange Management</span><span class="sxs-lookup"><span data-stu-id="8fd2f-186">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="8fd2f-187">Eseguire il comando seguente in Exchange Online PowerShell per creare e inviare una richiesta di approvazione di gruppo del revisore:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="8fd2f-188">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="8fd2f-189">Visualizzare lo stato delle richieste di elevazione di privilegi</span><span class="sxs-lookup"><span data-stu-id="8fd2f-189">View status of elevation requests</span></span>
<span data-ttu-id="8fd2f-190">Dopo aver creata una richiesta di approvazione, per esaminare lo stato richiesta di elevazione di privilegi nell'interfaccia di amministrazione o di Exchange PowerShell Management utilizza associato con richiesta ID.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-190">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8fd2f-191">Utilizzando l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-191">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8fd2f-192">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-192">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="8fd2f-193">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-193">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8fd2f-194">Selezionare **le richieste e gestire i criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8fd2f-195">Selezionare **Visualizza** per filtrare le richieste inviate in base allo stato **in sospeso**, **approvato**, **non consentiti**o **Archivio protetto dei clienti** .</span><span class="sxs-lookup"><span data-stu-id="8fd2f-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="8fd2f-196">Utilizzo di PowerShell per Exchange Management</span><span class="sxs-lookup"><span data-stu-id="8fd2f-196">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="8fd2f-197">Eseguire il comando seguente in Exchange Online PowerShell per visualizzare lo stato richiesta di approvazione per un ID richiesta specifica:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-197">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="8fd2f-198">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="8fd2f-199">L'approvazione di una richiesta di autorizzazione elevazione</span><span class="sxs-lookup"><span data-stu-id="8fd2f-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="8fd2f-p113">Quando si crea una richiesta di approvazione, i membri del gruppo responsabile approvazione pertinenti riceveranno una notifica tramite posta elettronica e autorizzati ad approvare la richiesta associata all'ID richiesta. Il richiedente riceverà una notifica dell'approvazione richieste o di tipo denial tramite messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p113">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8fd2f-202">Utilizzando l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-202">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8fd2f-203">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-203">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="8fd2f-204">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-204">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8fd2f-205">Selezionare **le richieste e gestire i criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8fd2f-206">Selezionare una richiesta elencata per visualizzare i dettagli e per eseguire l'azione necessaria la richiesta.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="8fd2f-p114">Selezionare **Approva** per approvare la richiesta o selezionare **Nega** per rifiutare la richiesta. Le richieste approvate in precedenza possono avere revocato selezionando **revocare**l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p114">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="8fd2f-209">Utilizzo di PowerShell per Exchange Management</span><span class="sxs-lookup"><span data-stu-id="8fd2f-209">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="8fd2f-210">Eseguire il comando seguente in Exchange Online PowerShell per approvare una richiesta di autorizzazione elevazione:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-210">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="8fd2f-211">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="8fd2f-212">Eseguire il comando seguente in Exchange Online PowerShell per rifiutare una richiesta di autorizzazione elevazione:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-212">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="8fd2f-213">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="8fd2f-214">Eliminare un criterio di accesso privilegiato in Office 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="8fd2f-215">Se non è più necessario all'interno dell'organizzazione, è possibile eliminare un criterio di accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-215">You can delete a privileged access policy if it is no longer needed in your organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8fd2f-216">Utilizzando l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-216">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8fd2f-217">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-217">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8fd2f-218">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-218">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8fd2f-219">Selezionare **le richieste e gestire i criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8fd2f-220">Selezionare **Configura criteri**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="8fd2f-221">Selezionare il criterio che si desidera eliminare e quindi selezionare **Rimuovi elemento**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="8fd2f-222">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-222">Select **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="8fd2f-223">Utilizzo di PowerShell per Exchange Management</span><span class="sxs-lookup"><span data-stu-id="8fd2f-223">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="8fd2f-224">Eseguire il comando seguente in Exchange Online Powershell per eliminare un criterio di accesso con privilegi:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-224">Run the following command in Exchange Online Powershell to delete a privileged access policy:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="8fd2f-225">Disabilitare l'accesso con privilegiato in Office 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="8fd2f-p115">Se necessario, è possibile disabilitare gestione con privilegi di accesso per l'organizzazione. Disattivazione con privilegi accesso non vengono eliminati tutti criteri di approvazione associato o i gruppi di responsabile approvazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-p115">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8fd2f-228">Utilizzando l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8fd2f-228">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8fd2f-229">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-229">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8fd2f-230">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8fd2f-231">Attivare il controllo **richiedono approvazioni per l'accesso con privilegiato** .</span><span class="sxs-lookup"><span data-stu-id="8fd2f-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="8fd2f-232">Utilizzo di PowerShell per Exchange Management</span><span class="sxs-lookup"><span data-stu-id="8fd2f-232">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="8fd2f-233">Eseguire il comando seguente in Exchange Online Powershell per disabilitare l'accesso con privilegiato:</span><span class="sxs-lookup"><span data-stu-id="8fd2f-233">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```