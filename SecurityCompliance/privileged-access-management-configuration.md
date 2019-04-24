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
ms.openlocfilehash: e086e93c268fe4de627bef30d3ac7aed8e6b1f98
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265238"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="da217-103">Configurazione della gestione degli accessi con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="da217-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da217-104">In questo argomento vengono illustrate le linee guida per la distribuzione e la configurazione per le funzionalità disponibili solo in Office 365 E5 e SKU di conformità avanzate.</span><span class="sxs-lookup"><span data-stu-id="da217-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="da217-105">In questo argomento viene illustrata la possibilità di abilitare e configurare la gestione degli accessi con privilegi nell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="da217-105">This topic guides you through enabling and configuring privileged access management in your Office 365 organization.</span></span> <span data-ttu-id="da217-106">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Exchange Management PowerShell per gestire e utilizzare accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="da217-106">You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="da217-107">Abilitare e configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="da217-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="da217-108">Seguire questa procedura per configurare e usare l'accesso privilegiato nell'organizzazione di Office 365:</span><span class="sxs-lookup"><span data-stu-id="da217-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="da217-109">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="da217-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="da217-110">Prima di iniziare a utilizzare l'accesso ai privilegi, determinare chi deve disporre dell'autorizzazione di approvazione per le richieste in arrivo per l'accesso a attività con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="da217-110">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="da217-111">Qualsiasi utente che fa parte del gruppo responsabili approvazione è in grado di approvare le richieste di accesso.</span><span class="sxs-lookup"><span data-stu-id="da217-111">Any user who is part of the Approvers’ group is able to approve access requests.</span></span> <span data-ttu-id="da217-112">Questa impostazione viene abilitata creando un gruppo di sicurezza abilitato alla posta elettronica in Office 365.</span><span class="sxs-lookup"><span data-stu-id="da217-112">This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="da217-113">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="da217-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="da217-114">L'accesso con privilegi deve essere abilitato in modo esplicito in Office 365 con il gruppo di approvazione predefinito, incluso un set di account di sistema che si desidera escludere dal controllo di accesso alla gestione degli accessi con privilegi.</span><span class="sxs-lookup"><span data-stu-id="da217-114">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="da217-115">Passaggio 3: creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="da217-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="da217-116">La creazione di un criterio di approvazione consente di definire i requisiti di approvazione specifici con ambito a singole attività.</span><span class="sxs-lookup"><span data-stu-id="da217-116">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="da217-117">Le opzioni relative al tipo \*\*\*\* di approvazione sono automatiche o **manuali**.</span><span class="sxs-lookup"><span data-stu-id="da217-117">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="da217-118">Passaggio 4: invio/approvazione delle richieste di accesso privilegiate</span><span class="sxs-lookup"><span data-stu-id="da217-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="da217-119">Una volta abilitata, l'accesso con privilegi richiede le approvazioni per qualsiasi attività in cui sia stato definito un criterio di approvazione associato.</span><span class="sxs-lookup"><span data-stu-id="da217-119">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="da217-120">Per le attività incluse in un criterio di approvazione, è necessario che gli utenti dispongano dell'autorizzazione di accesso e che dispongano delle autorizzazioni necessarie per eseguire l'attività.</span><span class="sxs-lookup"><span data-stu-id="da217-120">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="da217-121">Dopo aver concesso l'approvazione, l'utente richiedente può eseguire l'attività desiderata e l'accesso privilegiato autorizzerà ed eseguirà l'attività per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="da217-121">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="da217-122">L'approvazione rimane valida per la durata richiesta (la durata predefinita è di 4 ore), durante la quale il richiedente può eseguire l'attività desiderata più volte.</span><span class="sxs-lookup"><span data-stu-id="da217-122">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="da217-123">Tutte queste esecuzioni vengono registrate e rese disponibili per il controllo di sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="da217-123">All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="da217-124">Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire la procedura descritta in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to Connect to Exchange Online PowerShell with your Office 365 credenziali.</span><span class="sxs-lookup"><span data-stu-id="da217-124">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="da217-125">Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione di Office 365 per l'utilizzo dei passaggi per abilitare l'accesso privilegiato durante la connessione a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="da217-125">You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="da217-126">La connessione con l'autenticazione a più fattori consente di creare un token OAuth utilizzato dall'accesso privilegiato per la firma delle richieste.</span><span class="sxs-lookup"><span data-stu-id="da217-126">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="da217-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="da217-127"></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="da217-128">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="da217-128">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="da217-129">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da217-129">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="da217-130">Nell'interfaccia di amministrazione, andare a **gruppi** > **aggiungere un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="da217-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="da217-131">Selezionare **gruppo di sicurezza abilitato alla posta elettronica** e quindi completare il **nome**, l' **indirizzo di posta elettronica del gruppo**e i campi **Descrizione** per il nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="da217-131">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="da217-132">Salvare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="da217-132">Save the group.</span></span> <span data-ttu-id="da217-133">Il gruppo può richiedere alcuni minuti completamente configurati e comparire nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da217-133">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="da217-134">Selezionare il gruppo del nuovo responsabile approvazione e selezionare **modifica** per aggiungere gli utenti al gruppo.</span><span class="sxs-lookup"><span data-stu-id="da217-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="da217-135">Salvare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="da217-135">Save the group.</span></span>

<span data-ttu-id="da217-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="da217-136"></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="da217-137">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="da217-137">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="da217-138">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da217-138">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="da217-139">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da217-139">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="da217-140">Nell'interfaccia di amministrazione, passare a **Impostazioni > sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="da217-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="da217-141">Abilitare le **autorizzazioni necessarie per il controllo di accesso privilegiato** .</span><span class="sxs-lookup"><span data-stu-id="da217-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="da217-142">Assegnare il gruppo del responsabile approvazione creato nel passaggio 1 come **gruppo dei responsabili approvazione predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="da217-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="da217-143">**Salva** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="da217-143">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="da217-144">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="da217-144">In Exchange Management PowerShell</span></span>

<span data-ttu-id="da217-145">Per abilitare l'accesso con privilegi e assegnare il gruppo del responsabile dell'approvazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="da217-145">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="da217-146">Esempio:</span><span class="sxs-lookup"><span data-stu-id="da217-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="da217-147">La funzionalità account di sistema è disponibile per garantire che alcuni automatismi all'interno delle organizzazioni possano funzionare senza dipendenze dall'accesso privilegiato, tuttavia è consigliabile che tali esclusioni siano eccezionali e quelle consentite debbano essere approvate e controllate regolarmente.</span><span class="sxs-lookup"><span data-stu-id="da217-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="da217-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="da217-148"></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="da217-149">Passaggio 3: creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="da217-149">Step 3: Create an access policy</span></span>

<span data-ttu-id="da217-150">È possibile creare e configurare fino a 30 criteri di accesso privilegiato per l'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="da217-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="da217-151">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da217-151">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="da217-152">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da217-152">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="da217-153">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="da217-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="da217-154">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="da217-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="da217-155">Selezionare **Configure policies** e selezionare **Add a Policy**.</span><span class="sxs-lookup"><span data-stu-id="da217-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="da217-156">Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="da217-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="da217-157">**Tipo di criterio**: attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="da217-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="da217-158">**Ambito di criteri**: Exchange</span><span class="sxs-lookup"><span data-stu-id="da217-158">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="da217-159">**Nome criterio**: scegliere tra i criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="da217-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="da217-160">**Tipo di approvazione**: manuale o automatico</span><span class="sxs-lookup"><span data-stu-id="da217-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="da217-161">**Gruppo di approvazione**: selezionare il gruppo responsabili approvazione creato nel passaggio 1</span><span class="sxs-lookup"><span data-stu-id="da217-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="da217-162">Selezionare **Crea** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="da217-162">Select **Create** and then **Close**.</span></span> <span data-ttu-id="da217-163">È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="da217-163">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="da217-164">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="da217-164">In Exchange Management PowerShell</span></span>

<span data-ttu-id="da217-165">Per creare e definire un criterio di approvazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="da217-165">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="da217-166">Esempio:</span><span class="sxs-lookup"><span data-stu-id="da217-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="da217-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="da217-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="da217-168">Passaggio 4: invio/approvazione delle richieste di accesso privilegiate</span><span class="sxs-lookup"><span data-stu-id="da217-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="da217-169">Richiesta di autorizzazione all'elevazione per l'esecuzione di attività privilegiate</span><span class="sxs-lookup"><span data-stu-id="da217-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="da217-170">Le richieste di accesso con privilegi sono valide per un massimo di 24 ore dopo l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="da217-170">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="da217-171">Se non è stato approvato o negato, le richieste scadono e Access non è approvato.</span><span class="sxs-lookup"><span data-stu-id="da217-171">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="da217-172">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da217-172">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="da217-173">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="da217-173">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="da217-174">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="da217-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="da217-175">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="da217-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="da217-176">Selezionare **nuova richiesta**.</span><span class="sxs-lookup"><span data-stu-id="da217-176">Select **New request**.</span></span> <span data-ttu-id="da217-177">Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="da217-177">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="da217-178">**Tipo di richiesta**: attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="da217-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="da217-179">**Ambito delle richieste**: Exchange</span><span class="sxs-lookup"><span data-stu-id="da217-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="da217-180">**Richiesta per**: selezionare i criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="da217-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="da217-181">**Durata (ore)**: numero di ore di accesso richiesto.</span><span class="sxs-lookup"><span data-stu-id="da217-181">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="da217-182">Non è previsto un limite per il numero di ore che è possibile richiedere.</span><span class="sxs-lookup"><span data-stu-id="da217-182">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="da217-183">**Commenti**: campo di testo per i commenti relativi alla richiesta di accesso</span><span class="sxs-lookup"><span data-stu-id="da217-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="da217-184">Selezionare **Salva** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="da217-184">Select **Save** and then **Close**.</span></span> <span data-ttu-id="da217-185">La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="da217-185">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="da217-186">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="da217-186">In Exchange Management PowerShell</span></span>

<span data-ttu-id="da217-187">Eseguire il seguente comando in PowerShell di Exchange Online per creare e inviare una richiesta di approvazione al gruppo del responsabile dell'approvazione:</span><span class="sxs-lookup"><span data-stu-id="da217-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="da217-188">Esempio:</span><span class="sxs-lookup"><span data-stu-id="da217-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="da217-189">Visualizzare lo stato delle richieste di elevazione</span><span class="sxs-lookup"><span data-stu-id="da217-189">View status of elevation requests</span></span>
<span data-ttu-id="da217-190">Dopo la creazione di una richiesta di approvazione, lo stato della richiesta di elevazione può essere esaminato nell'interfaccia di amministrazione o in Exchange Management PowerShell utilizzando l'ID della richiesta associato.</span><span class="sxs-lookup"><span data-stu-id="da217-190">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="da217-191">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da217-191">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="da217-192">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="da217-192">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="da217-193">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="da217-193">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="da217-194">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="da217-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="da217-195">Selezionare **Visualizza** per filtrare le richieste inviate mediante lo stato **in sospeso**, **approvato**, **negato**o **protetto dall'archivio dei clienti** .</span><span class="sxs-lookup"><span data-stu-id="da217-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="da217-196">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="da217-196">In Exchange Management PowerShell</span></span>

<span data-ttu-id="da217-197">Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare lo stato di una richiesta di approvazione per un ID di richiesta specifico:</span><span class="sxs-lookup"><span data-stu-id="da217-197">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="da217-198">Esempio:</span><span class="sxs-lookup"><span data-stu-id="da217-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="da217-199">Approvazione di una richiesta di autorizzazione elevazione</span><span class="sxs-lookup"><span data-stu-id="da217-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="da217-200">Quando viene creata una richiesta di approvazione, i membri del gruppo di approvazione pertinente ricevono una notifica tramite posta elettronica e possono approvare la richiesta associata all'ID della richiesta.</span><span class="sxs-lookup"><span data-stu-id="da217-200">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="da217-201">Il richiedente riceve una notifica dell'approvazione o della negazione della richiesta tramite il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="da217-201">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="da217-202">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da217-202">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="da217-203">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="da217-203">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="da217-204">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="da217-204">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="da217-205">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="da217-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="da217-206">Selezionare una richiesta elencata per visualizzare i dettagli e per eseguire l'azione sulla richiesta.</span><span class="sxs-lookup"><span data-stu-id="da217-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="da217-207">Selezionare **approva** per approvare la richiesta oppure selezionare **Nega** per rifiutare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="da217-207">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="da217-208">Le richieste approvate in precedenza possono avere accesso revocato selezionando **revoca**.</span><span class="sxs-lookup"><span data-stu-id="da217-208">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="da217-209">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="da217-209">In Exchange Management PowerShell</span></span>

<span data-ttu-id="da217-210">Per approvare una richiesta di autorizzazione elevazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="da217-210">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="da217-211">Esempio:</span><span class="sxs-lookup"><span data-stu-id="da217-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="da217-212">Per rifiutare una richiesta di autorizzazione elevazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="da217-212">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="da217-213">Esempio:</span><span class="sxs-lookup"><span data-stu-id="da217-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="da217-214">Eliminare un criterio di accesso con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="da217-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="da217-215">Se non è più necessario nell'organizzazione, è possibile eliminare un criterio di accesso con privilegi.</span><span class="sxs-lookup"><span data-stu-id="da217-215">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="da217-216">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da217-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="da217-217">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da217-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="da217-218">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="da217-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="da217-219">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="da217-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="da217-220">Selezionare **Configure policies**.</span><span class="sxs-lookup"><span data-stu-id="da217-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="da217-221">Selezionare il criterio che si desidera eliminare, quindi selezionare **Rimuovi criterio**.</span><span class="sxs-lookup"><span data-stu-id="da217-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="da217-222">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="da217-222">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="da217-223">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="da217-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="da217-224">Per eliminare un criterio di accesso con privilegi, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="da217-224">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="da217-225">Disabilitare l'accesso con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="da217-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="da217-226">Se necessario, è possibile disabilitare la gestione degli accessi con privilegi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da217-226">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="da217-227">La disabilitazione dell'accesso con privilegi non comporta l'eliminazione di criteri di approvazione associati o gruppi di approvatori.</span><span class="sxs-lookup"><span data-stu-id="da217-227">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="da217-228">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da217-228">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="da217-229">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da217-229">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="da217-230">Nell'interfaccia di amministrazione, passare a **Impostazioni** > **protezione & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="da217-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="da217-231">Abilitare le **autorizzazioni necessarie per il controllo di accesso privilegiato** .</span><span class="sxs-lookup"><span data-stu-id="da217-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="da217-232">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="da217-232">In Exchange Management PowerShell</span></span>

<span data-ttu-id="da217-233">Per disabilitare l'accesso con privilegi, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="da217-233">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```
Disable-ElevatedAccessControl
```