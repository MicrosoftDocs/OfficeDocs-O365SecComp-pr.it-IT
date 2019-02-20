---
title: Configurazione della gestione degli accessi con privilegi in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilizzare questo argomento per ulteriori informazioni sulla configurazione della gestione degli accessi con privilegi in Office 365
ms.openlocfilehash: 63780da59afb245b35916a1e7a5b2eb780d535a8
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090918"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="fc5c0-103">Configurazione della gestione degli accessi con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc5c0-104">In questo argomento vengono illustrate le linee guida per la distribuzione e la configurazione per le funzionalità disponibili solo in Office 365 E5 e SKU di conformità avanzate.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="fc5c0-p101">In questo argomento viene illustrata l'abilitazione e la configurazione della gestione degli accessi con privilegi nell'organizzazione di Office 365. È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Exchange Management PowerShell per gestire e utilizzare accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="fc5c0-107">Abilitare e configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="fc5c0-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="fc5c0-108">Seguire questa procedura per configurare e usare l'accesso privilegiato nell'organizzazione di Office 365:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="fc5c0-109">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="fc5c0-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="fc5c0-p102">Prima di iniziare a utilizzare l'accesso ai privilegi, determinare chi avrà l'autorità di approvazione per le richieste in arrivo per l'accesso a attività con privilegi elevati. Qualsiasi utente che fa parte del gruppo responsabili approvazione sarà in grado di approvare le richieste di accesso. Questa impostazione viene abilitata creando un gruppo di sicurezza abilitato alla posta elettronica in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="fc5c0-113">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="fc5c0-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="fc5c0-114">L'accesso privilegiato deve essere attivato in modo esplicito in Office 365 con il gruppo di approvazione predefinito e includendo un set di account di sistema che si desidera escludere dal controllo di accesso a gestione accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="fc5c0-115">Passaggio 3: creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="fc5c0-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="fc5c0-p103">La creazione di un criterio di approvazione consente di definire i requisiti di approvazione specifici con ambito a singole attività. Le opzioni relative al tipo \*\*\*\* di approvazione sono automatiche o **manuali**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="fc5c0-118">Passaggio 4: invio/approvazione delle richieste di accesso privilegiate</span><span class="sxs-lookup"><span data-stu-id="fc5c0-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="fc5c0-p104">Una volta abilitata, l'accesso con privilegi richiede le approvazioni per l'esecuzione di tutte le attività che hanno un criterio di approvazione associato definito. Gli utenti che desiderano eseguire le attività incluse nel criterio di approvazione devono richiedere e ricevere l'approvazione dell'accesso per avere le autorizzazioni necessarie per eseguire l'attività.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="fc5c0-p105">Dopo aver concesso l'approvazione, l'utente richiedente può eseguire l'attività desiderata e l'accesso privilegiato autorizzerà ed eseguirà l'attività a nome degli utenti. L'approvazione rimane valida per la durata richiesta (la durata predefinita è di 4 ore), durante la quale il richiedente può eseguire l'attività desiderata più volte. Tutte queste esecuzioni vengono registrate e rese disponibili per il controllo di sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="fc5c0-p106">Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire la procedura descritta in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to Connect to Exchange Online PowerShell with your Office 365 credenziali. Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione di Office 365 per l'utilizzo dei passaggi per abilitare l'accesso privilegiato durante la connessione a PowerShell di Exchange Online. La connessione con l'autenticazione a più fattori consente di creare un token OAuth utilizzato dall'accesso privilegiato per la firma delle richieste.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="fc5c0-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5c0-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="fc5c0-128">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="fc5c0-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="fc5c0-129">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="fc5c0-130">Nell'interfaccia di amministrazione, andare a **gruppi** > **aggiungere un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="fc5c0-131">Selezionare il tipo di gruppo gruppo di **sicurezza abilitato alla posta elettronica** e quindi completare il **nome**, l' **indirizzo di posta elettronica del gruppo**e i campi **Descrizione** per il nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="fc5c0-p107">Salvare il gruppo. Il gruppo può richiedere alcuni minuti completamente configurati e visualizzarlo nell'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="fc5c0-134">Selezionare il gruppo del nuovo responsabile approvazione e selezionare **modifica** per aggiungere gli utenti al gruppo.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="fc5c0-135">Salvare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-135">Save the group.</span></span>

<span data-ttu-id="fc5c0-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5c0-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="fc5c0-137">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="fc5c0-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="fc5c0-138">Utilizzo dell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="fc5c0-139">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="fc5c0-140">Nell'interfaccia di amministrazione, passare a **Impostazioni > sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fc5c0-141">Abilitare le **autorizzazioni necessarie per il controllo di accesso privilegiato** .</span><span class="sxs-lookup"><span data-stu-id="fc5c0-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="fc5c0-142">Assegnare il gruppo del responsabile approvazione creato nel passaggio 1 come **gruppo dei responsabili approvazione predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="fc5c0-143">**Salva** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="fc5c0-144">Utilizzo di Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5c0-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="fc5c0-145">Eseguire il seguente comando in PowerShell di Exchange Online per abilitare l'accesso con privilegi e assegnare il gruppo del responsabile dell'approvazione:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="fc5c0-146">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="fc5c0-147">La funzionalità account di sistema è disponibile per garantire che alcuni automatismi all'interno delle organizzazioni possano funzionare senza dipendenze dall'accesso privilegiato, tuttavia è consigliabile che tali esclusioni siano eccezionali e quelle consentite debbano essere approvate e controllate regolarmente.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="fc5c0-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5c0-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="fc5c0-149">Passaggio 3: creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="fc5c0-149">Step 3 - Create an access policy</span></span>

<span data-ttu-id="fc5c0-150">È possibile creare e configurare fino a 30 criteri di accesso privilegiato per l'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="fc5c0-151">Utilizzo dell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-151">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="fc5c0-152">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="fc5c0-153">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fc5c0-154">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="fc5c0-155">Selezionare **Configure policies** e selezionare **Add a Policy**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="fc5c0-156">Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="fc5c0-157">**Tipo di criterio**: attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="fc5c0-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="fc5c0-158">**Ambito di criteri**: Exchange o Office 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-158">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="fc5c0-159">**Nome criterio**: scegliere tra i criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="fc5c0-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="fc5c0-160">**Tipo di approvazione**: manuale o automatico</span><span class="sxs-lookup"><span data-stu-id="fc5c0-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="fc5c0-161">**Gruppo di approvazione**: selezionare il gruppo responsabili approvazione creato nel passaggio 1</span><span class="sxs-lookup"><span data-stu-id="fc5c0-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="fc5c0-p108">Selezionare **Crea** e quindi **Chiudi**. È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="fc5c0-164">Utilizzo di Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5c0-164">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="fc5c0-165">Eseguire il seguente comando in PowerShell di Exchange Online per creare e definire un criterio di approvazione:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-165">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="fc5c0-166">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="fc5c0-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5c0-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="fc5c0-168">Passaggio 4: invio/approvazione delle richieste di accesso privilegiate</span><span class="sxs-lookup"><span data-stu-id="fc5c0-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="fc5c0-169">Richiesta di autorizzazione all'elevazione per l'esecuzione di attività privilegiate</span><span class="sxs-lookup"><span data-stu-id="fc5c0-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="fc5c0-p109">Le richieste di accesso con privilegi sono valide per un massimo di 24 ore dopo l'invio della richiesta. Se non è stato approvato o negato, le richieste scadono e Access non è approvato.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p109">Requests for privileged access are valid for up to 24 hours after the request is submitted. If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="fc5c0-172">Utilizzo dell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-172">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="fc5c0-173">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com) utilizzando le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-173">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="fc5c0-174">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fc5c0-175">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="fc5c0-p110">Selezionare **nuova richiesta**. Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p110">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="fc5c0-178">**Tipo di richiesta**: attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="fc5c0-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="fc5c0-179">**Ambito delle richieste**: Exchange</span><span class="sxs-lookup"><span data-stu-id="fc5c0-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="fc5c0-180">**Richiesta per**: selezionare i criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="fc5c0-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="fc5c0-p111">**Durata (ore)**: numero di ore di accesso richiesto. Non è previsto un limite per il numero di ore che è possibile richiedere.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p111">**Duration (hours)**: Number of hours of requested access. There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="fc5c0-183">**Commenti**: campo di testo per i commenti relativi alla richiesta di accesso</span><span class="sxs-lookup"><span data-stu-id="fc5c0-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="fc5c0-p112">Selezionare **Salva** e quindi **Chiudi**. La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p112">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="fc5c0-186">Utilizzo di Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5c0-186">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="fc5c0-187">Eseguire il seguente comando in PowerShell di Exchange Online per creare e inviare una richiesta di approvazione al gruppo del responsabile dell'approvazione:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="fc5c0-188">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="fc5c0-189">Visualizzare lo stato delle richieste di elevazione</span><span class="sxs-lookup"><span data-stu-id="fc5c0-189">View status of elevation requests</span></span>
<span data-ttu-id="fc5c0-190">Dopo la creazione di una richiesta di approvazione, lo stato della richiesta di elevazione può essere esaminato nell'interfaccia di amministrazione o in Exchange Management PowerShell utilizzando l'ID della richiesta associato.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-190">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="fc5c0-191">Utilizzo dell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-191">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="fc5c0-192">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com) utilizzando le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-192">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="fc5c0-193">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-193">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fc5c0-194">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="fc5c0-195">Selezionare **Visualizza** per filtrare le richieste inviate mediante lo stato **in sospeso**, **approvato**, **negato**o **protetto dall'archivio dei clienti** .</span><span class="sxs-lookup"><span data-stu-id="fc5c0-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="fc5c0-196">Utilizzo di Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5c0-196">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="fc5c0-197">Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare lo stato di una richiesta di approvazione per un ID di richiesta specifico:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-197">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="fc5c0-198">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="fc5c0-199">Approvazione di una richiesta di autorizzazione elevazione</span><span class="sxs-lookup"><span data-stu-id="fc5c0-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="fc5c0-p113">Quando viene creata una richiesta di approvazione, i membri del gruppo responsabile approvazione ricevono una notifica tramite posta elettronica e possono approvare la richiesta associata all'ID della richiesta. Il richiedente riceverà una notifica dell'approvazione o della negazione della richiesta tramite il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p113">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="fc5c0-202">Utilizzo dell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-202">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="fc5c0-203">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com) utilizzando le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-203">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="fc5c0-204">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-204">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fc5c0-205">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="fc5c0-206">Selezionare una richiesta elencata per visualizzare i dettagli e per eseguire l'azione sulla richiesta.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="fc5c0-p114">Selezionare **approva** per approvare la richiesta oppure selezionare **Nega** per rifiutare la richiesta. Le richieste approvate in precedenza possono avere accesso revocato selezionando **revoca**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p114">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="fc5c0-209">Utilizzo di Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5c0-209">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="fc5c0-210">Eseguire il seguente comando in PowerShell di Exchange Online per approvare una richiesta di autorizzazione elevazione:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-210">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="fc5c0-211">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="fc5c0-212">Eseguire il seguente comando in PowerShell di Exchange Online per negare una richiesta di autorizzazione elevazione:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-212">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="fc5c0-213">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="fc5c0-214">Eliminare un criterio di accesso con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="fc5c0-215">È possibile eliminare un criterio di accesso con privilegi se non è più necessario nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-215">You can delete a privileged access policy if it is no longer needed in your organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="fc5c0-216">Utilizzo dell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-216">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="fc5c0-217">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-217">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="fc5c0-218">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-218">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fc5c0-219">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="fc5c0-220">Selezionare **Configure policies**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="fc5c0-221">Selezionare il criterio che si desidera eliminare, quindi selezionare **Rimuovi criterio**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="fc5c0-222">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-222">Select **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="fc5c0-223">Utilizzo di Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5c0-223">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="fc5c0-224">Eseguire il seguente comando in PowerShell di Exchange Online per eliminare un criterio di accesso privilegiato:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-224">Run the following command in Exchange Online Powershell to delete a privileged access policy:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="fc5c0-225">Disabilitare l'accesso con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="fc5c0-p115">Se necessario, è possibile disabilitare la gestione degli accessi con privilegi per l'organizzazione. La disabilitazione dell'accesso con privilegi non comporta l'eliminazione di criteri di approvazione associati o gruppi di approvatori.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-p115">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="fc5c0-228">Utilizzo dell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc5c0-228">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="fc5c0-229">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-229">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="fc5c0-230">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="fc5c0-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fc5c0-231">Abilitare le **autorizzazioni necessarie per il controllo di accesso privilegiato** .</span><span class="sxs-lookup"><span data-stu-id="fc5c0-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="fc5c0-232">Utilizzo di Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc5c0-232">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="fc5c0-233">Eseguire il seguente comando in PowerShell di Exchange Online per disabilitare l'accesso con privilegi:</span><span class="sxs-lookup"><span data-stu-id="fc5c0-233">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```