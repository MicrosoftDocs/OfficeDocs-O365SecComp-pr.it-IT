---
title: Protezione dalle minacce in Office 365
ms.author: tracyp
author: msfttracyp
manager: laurawi
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Utilizzare questo articolo come guida per configurare ora le funzionalità di protezione dalle minacce.
ms.openlocfilehash: 065071999130f209d63bcafc09ad72daceceac04
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261634"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="43b28-103">Protezione dalle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="43b28-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="43b28-104">Office 365 include una vasta gamma di funzionalità di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="43b28-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="43b28-105">Di seguito è illustrata una guida introduttiva che è possibile utilizzare come elenco di controllo per verificare che le funzionalità di protezione delle minacce siano configurate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43b28-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="43b28-106">Se si è nuovi per le funzionalità di protezione dalle minacce in Office 365 o si è sicuri di dove iniziare, utilizzare le linee guida seguenti come punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="43b28-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="43b28-107">**Per ogni tipo di criterio sono incluse le impostazioni consigliAte iniziali, tuttavia sono disponibili molte opzioni ed è possibile modificare le impostazioni in base alle esigenze specifiche dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="43b28-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="43b28-108">Consenti circa 30 minuti affinché i criteri o le modifiche vengano elaborati tramite il Data Center.</span><span class="sxs-lookup"><span data-stu-id="43b28-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="43b28-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43b28-109">Requirements</span></span>

### <a name="licenses"></a><span data-ttu-id="43b28-110">Licenze</span><span class="sxs-lookup"><span data-stu-id="43b28-110">Licenses</span></span>

<span data-ttu-id="43b28-111">Le funzionalità di protezione dalle minacce sono incluse in tutte le sottoscrizioni di Office 365; Tuttavia, alcuni abbonamenti includono funzionalità più avanzate, ad esempio quelle di Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="43b28-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features, such as those in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="43b28-112">In questo articolo sono inclusi i requisiti di sottoscrizione per ogni area di protezione.</span><span class="sxs-lookup"><span data-stu-id="43b28-112">In this article we include subscription requirements for each protection area.</span></span>

<span data-ttu-id="43b28-113">Per ulteriori informazioni sulle funzionalità di protezione dalle minacce e subsriptions, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b28-113">To learn more about threat protection features and subsriptions, see the following resources:</span></span>
- [<span data-ttu-id="43b28-114">Descrizione del servizio Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="43b28-114">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
- [<span data-ttu-id="43b28-115">Descrizione del servizio Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="43b28-115">Exchange Online Protection Service Description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)
- [<span data-ttu-id="43b28-116">Centro sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="43b28-116">Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

### <a name="roles-and-permissions"></a><span data-ttu-id="43b28-117">Ruoli e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="43b28-117">Roles and permissions</span></span>

<span data-ttu-id="43b28-118">È necessario essere assegnati a un ruolo appropriato per configurare i criteri nel [Centro sicurezza _AMP_ Compliance](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="43b28-118">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="43b28-119">Nella tabella seguente sono inclusi alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="43b28-119">The following table includes some examples:</span></span> 

|<span data-ttu-id="43b28-120">Ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="43b28-120">Role or role group</span></span>  |<span data-ttu-id="43b28-121">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="43b28-121">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="43b28-122">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="43b28-122">Office 365 Global Administrator</span></span> |[<span data-ttu-id="43b28-123">Informazioni sui ruoli di amministratore di Office 365</span><span class="sxs-lookup"><span data-stu-id="43b28-123">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="43b28-124">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="43b28-124">Security Administrator</span></span> |[<span data-ttu-id="43b28-125">Autorizzazioni per il ruolo di amministratore in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="43b28-125">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="43b28-126">Gestione dell'organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="43b28-126">Exchange Online Organization Management</span></span> |[<span data-ttu-id="43b28-127">Autorizzazioni in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="43b28-127">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="43b28-128">e</span><span class="sxs-lookup"><span data-stu-id="43b28-128">and</span></span><br> [<span data-ttu-id="43b28-129">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="43b28-129">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="43b28-130">Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="43b28-130">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="43b28-131">Parte 1-antimalware</span><span class="sxs-lookup"><span data-stu-id="43b28-131">Part 1 - Anti-malware</span></span>

<span data-ttu-id="43b28-132">La [protezione antimalware](anti-malware-protection.md) è disponibile in abbonamenti che includono [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span><span class="sxs-lookup"><span data-stu-id="43b28-132">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span></span> 

1. <span data-ttu-id="43b28-133">Nel [Centro sicurezza & Compliance](https://protection.office.com)scegliere**anti-malware** **Management** > **policy** > .</span><span class="sxs-lookup"><span data-stu-id="43b28-133">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="43b28-134">Fare doppio clic sul criterio **predefinito** e quindi scegliere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="43b28-134">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="43b28-135">Specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b28-135">Specify the following settings:</span></span>
    
    - <span data-ttu-id="43b28-136">Nella sezione **risposta di rilevamento malware** mantenere l'impostazione predefinita **Nr**.</span><span class="sxs-lookup"><span data-stu-id="43b28-136">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
   
    - <span data-ttu-id="43b28-137">Nella sezione **filtro tipi di allegati comuni** scegliere attivato \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="43b28-137">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="43b28-138">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="43b28-138">Click **Save**.</span></span>

<span data-ttu-id="43b28-139">Per ulteriori informazioni sulle opzioni di criteri anti-malware, vedere [Configure anti-malware Policies](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="43b28-139">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="43b28-140">Parte 2-protezione zero-day</span><span class="sxs-lookup"><span data-stu-id="43b28-140">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="43b28-141">La protezione da zero giorni è disponibile in abbonamenti che includono [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) ed è configurato tramite gli [allegati sicuri di ATP](atp-safe-attachments.md) e i criteri per i [collegamenti sicuri di ATP](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="43b28-141">Zero-day protection is available in subscriptions that include [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="43b28-142">Criteri per gli allegati sicuri ATP</span><span class="sxs-lookup"><span data-stu-id="43b28-142">ATP Safe Attachments policies</span></span>

<span data-ttu-id="43b28-143">Per configurare gli [allegati sicuri di ATP](atp-safe-attachments.md), è necessario definire almeno un criterio per gli allegati sicuri ATP.</span><span class="sxs-lookup"><span data-stu-id="43b28-143">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span> 

1. <span data-ttu-id="43b28-144">Nel [Centro sicurezza & Compliance](https://protection.office.com)selezionare i \*\*\*\* > **criteri** > di gestione delle minacce per gli**allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="43b28-144">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="43b28-145">Selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="43b28-145">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="43b28-146">Nella sezione **Proteggi allegati di posta elettronica** , fare clic sul**+** segno più ().</span><span class="sxs-lookup"><span data-stu-id="43b28-146">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="43b28-147">Specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b28-147">Specify the following settings:</span></span>

    - <span data-ttu-id="43b28-148">Nella casella **nome** Digitare `Block malware`.</span><span class="sxs-lookup"><span data-stu-id="43b28-148">In the **Name** box, type `Block malware`.</span></span>

    - <span data-ttu-id="43b28-149">Nella sezione Response scegliere **Block**.</span><span class="sxs-lookup"><span data-stu-id="43b28-149">In the response section, choose **Block**.</span></span>

    - <span data-ttu-id="43b28-150">Nella sezione **allegato di reindirizzamento** selezionare l'opzione **Abilita reindirizzamento**e quindi specificare l'indirizzo di posta elettronica per l'amministratore o l'operatore di sicurezza dell'organizzazione che rivedrà i file rilevati.</span><span class="sxs-lookup"><span data-stu-id="43b28-150">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

    - <span data-ttu-id="43b28-151">Nella sezione **applicato a** scegliere **il dominio del destinatario**.</span><span class="sxs-lookup"><span data-stu-id="43b28-151">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="43b28-152">Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43b28-152">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="43b28-153">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="43b28-153">Click **Save**.</span></span>

6. <span data-ttu-id="43b28-154">(**Passaggio aggiuntivo consigliato**) Come amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con il parametro **DisallowInfectedFileDownload** impostato su *true* per l'ambiente Office 365.</span><span class="sxs-lookup"><span data-stu-id="43b28-154">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="43b28-155">In questo modo si impedisce l'apertura, lo spostamento, la copia o la condivisione di file che vengono rilevati come dannosi.</span><span class="sxs-lookup"><span data-stu-id="43b28-155">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="43b28-156">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="43b28-156">To learn more, see:</span></span> 
- [<span data-ttu-id="43b28-157">Impostare i criteri per gli allegati sicuri ATP di Office 365</span><span class="sxs-lookup"><span data-stu-id="43b28-157">Set up Office 365 ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md)
- [<span data-ttu-id="43b28-158">Attivazione di Office 365 ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43b28-158">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="atp-safe-links-policies"></a><span data-ttu-id="43b28-159">Criteri per i collegamenti sicuri ATP</span><span class="sxs-lookup"><span data-stu-id="43b28-159">ATP Safe Links policies</span></span>

<span data-ttu-id="43b28-160">Per configurare i [collegamenti sicuri di ATP](atp-safe-links.md), esaminare e modificare il criterio predefinito e aggiungere un criterio per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="43b28-160">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="43b28-161">Nel [Centro sicurezza & Compliance](https://protection.office.com)scegliere**criteri** > di **gestione** > delle minacce**ATP collegamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="43b28-161">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="43b28-162">Fare doppio clic sul criterio **predefinito** .</span><span class="sxs-lookup"><span data-stu-id="43b28-162">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="43b28-163">Nella sezione **use Safe Links in** selezionare l'opzione **Office 365 ProPlus, Office per iOS e Android**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="43b28-163">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="43b28-164">Nella sezione **criteri che si applicano a destinatari specifici** fare clic sul segno più**+**().</span><span class="sxs-lookup"><span data-stu-id="43b28-164">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="43b28-165">Specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b28-165">Specify the following settings:</span></span>

    - <span data-ttu-id="43b28-166">Nella casella **nome** Digitare un nome, ad esempio `Safe Links`.</span><span class="sxs-lookup"><span data-stu-id="43b28-166">In the **Name** box, type a name, such as `Safe Links`.</span></span>

    - <span data-ttu-id="43b28-167">Nella sezione **selezionare l'azione** scegliere attivato. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="43b28-167">In the **Select the action** section, choose **On**.</span></span>

    - <span data-ttu-id="43b28-168">Selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b28-168">Select these options:</span></span>

        - <span data-ttu-id="43b28-169">**Utilizzare gli allegati sicuri per analizzare il contenuto scaricabile**</span><span class="sxs-lookup"><span data-stu-id="43b28-169">**Use safe attachments to scan downloadable content**</span></span> 

        - <span data-ttu-id="43b28-170">**Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="43b28-170">**Apply safe links to email messages sent within the organization**</span></span>

        - <span data-ttu-id="43b28-171">**Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale**</span><span class="sxs-lookup"><span data-stu-id="43b28-171">**Do not let users click through safe links to original URL**</span></span>

    - <span data-ttu-id="43b28-172">Nella sezione **applicato a** scegliere **il dominio del destinatario**.</span><span class="sxs-lookup"><span data-stu-id="43b28-172">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="43b28-173">Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43b28-173">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="43b28-174">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="43b28-174">Click **Save**.</span></span>

<span data-ttu-id="43b28-175">Per ulteriori informazioni, vedere [configurare i criteri dei collegamenti sicuri ATP di Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="43b28-175">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="43b28-176">Parte 3-anti-phishing</span><span class="sxs-lookup"><span data-stu-id="43b28-176">Part 3 - Anti-phishing</span></span> 

<span data-ttu-id="43b28-177">La [protezione anti-phishing](anti-phishing-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="43b28-177">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="43b28-178">La protezione anti-phishing avanzata è disponibile in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="43b28-178">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="43b28-179">Nella procedura seguente viene descritto come configurare un criterio anti-phishing ATP.</span><span class="sxs-lookup"><span data-stu-id="43b28-179">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="43b28-180">I passaggi sono simili per la configurazione di un criterio anti-phishing (senza ATP).</span><span class="sxs-lookup"><span data-stu-id="43b28-180">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="43b28-181">Nel [Centro sicurezza & Compliance](https://protection.office.com), scegliere il**criterio** > di **gestione** > delle minacce**ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="43b28-181">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="43b28-182">Fare clic su **criteri predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="43b28-182">Click **Default policy**.</span></span>

3. <span data-ttu-id="43b28-183">Nella sezione **rappresentazione** fare clic su **modifica**e quindi specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b28-183">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

    -  <span data-ttu-id="43b28-184">Nella scheda **Aggiungi utenti da proteggere** , attiva la protezione.</span><span class="sxs-lookup"><span data-stu-id="43b28-184">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="43b28-185">Aggiungere quindi gli utenti, ad esempio i membri del Consiglio dell'organizzazione, il CEO, il CFO e altri leader senior.</span><span class="sxs-lookup"><span data-stu-id="43b28-185">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="43b28-186">(È possibile digitare un singolo indirizzo di posta elettronica o fare clic per visualizzare un elenco).</span><span class="sxs-lookup"><span data-stu-id="43b28-186">(You can type an individual email address, or click to display a list.)</span></span>

    - <span data-ttu-id="43b28-187">Nella scheda **Aggiungi domini da proteggere** , attiva **automaticamente Includi i domini che possiedo**.</span><span class="sxs-lookup"><span data-stu-id="43b28-187">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="43b28-188">Se si dispone di domini personalizzati, aggiungere anche quelli.</span><span class="sxs-lookup"><span data-stu-id="43b28-188">If you have custom domains, add those as well.</span></span>

    - <span data-ttu-id="43b28-189">Nella scheda **azioni** selezionare **Sposta messaggio nelle cartelle di posta indesiderata dei destinatari** per entrambi gli utenti rappresentati e per il dominio rappresentato e attiva suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="43b28-189">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>

    - <span data-ttu-id="43b28-190">Nella scheda **Intelligence della cassetta postale** , verificare che l'intelligence della cassetta postale sia attivata.</span><span class="sxs-lookup"><span data-stu-id="43b28-190">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>

    - <span data-ttu-id="43b28-191">Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="43b28-191">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="43b28-192">Nella sezione **spoofing** fare clic su **modifica**e quindi specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b28-192">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="43b28-193">Nella scheda **Impostazioni filtro spoofing** verificare che la protezione anti-spoofing sia attivata.</span><span class="sxs-lookup"><span data-stu-id="43b28-193">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

    - <span data-ttu-id="43b28-194">Nella scheda **azioni** scegliere Sposta messaggio nelle cartelle di posta indesiderata dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="43b28-194">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>

    - <span data-ttu-id="43b28-195">Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="43b28-195">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="43b28-196">Se non sono state apportate modifiche, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="43b28-196">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="43b28-197">Chiudere la pagina impostazioni di criteri predefinite.</span><span class="sxs-lookup"><span data-stu-id="43b28-197">Close the default policy settings page.</span></span>

<span data-ttu-id="43b28-198">Per ulteriori informazioni sulle opzioni relative ai criteri di anti-phishing, vedere [set up anti-phishing Policies](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="43b28-198">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="43b28-199">Parte 4-protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="43b28-199">Part 4 - Anti-spam</span></span>

<span data-ttu-id="43b28-200">La [protezione da posta](anti-spam-protection.md) indesiderata è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="43b28-200">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="43b28-201">Nel [Centro sicurezza & Compliance](https://protection.office.com), scegliere protezione dalla**posta**indesiderata **dei** > **criteri** > di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="43b28-201">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="43b28-202">Nella scheda **personalizzato** , attiva **impostazioni personalizzate** .</span><span class="sxs-lookup"><span data-stu-id="43b28-202">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="43b28-203">Espandere **criteri di filtro della posta indesideraTa predefiniti**, fare clic su **modifica criteri**e quindi specificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b28-203">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

    - <span data-ttu-id="43b28-204">Nella sezione **azioni di posta indesiderata e di massa** impostare la soglia su un valore pari a 5 o 6.</span><span class="sxs-lookup"><span data-stu-id="43b28-204">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

    - <span data-ttu-id="43b28-205">Nella sezione **Consenti elenchi** esaminare (e, se necessario, modificare) i propri mittenti e domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="43b28-205">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="43b28-206">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="43b28-206">Click **Save**.</span></span>

<span data-ttu-id="43b28-207">Per ulteriori informazioni sulle opzioni relative ai criteri di protezione da posta indesiderata, vedere [Configure the antispam](configure-the-anti-spam-policies.md)Policy.</span><span class="sxs-lookup"><span data-stu-id="43b28-207">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="43b28-208">Parte 5-impostazioni a livello di servizio</span><span class="sxs-lookup"><span data-stu-id="43b28-208">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="43b28-209">Spurgo automatico zero-hour</span><span class="sxs-lookup"><span data-stu-id="43b28-209">Zero-hour auto purge</span></span>

<span data-ttu-id="43b28-210">[Spurgo automatico zero-hour](zero-hour-auto-purge.md) (ZAP) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="43b28-210">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="43b28-211">Questa protezione è attivata per impostazione predefinita. Tuttavia, le condizioni seguenti devono essere soddisfatte affinché la protezione sia attiva:</span><span class="sxs-lookup"><span data-stu-id="43b28-211">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="43b28-212">Le azioni di posta indesiderata sono impostate in modo da **spostare messaggi nella cartella posta** indesiderata nei criteri di protezione dalla [posta](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="43b28-212">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="43b28-213">Gli utenti hanno mantenuto le [Impostazioni](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)predefinite per la posta indesiderata e non hanno disattivato la protezione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="43b28-213">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="43b28-214">Per ulteriori informazioni, vedere [zero-hour auto Purge-protezione da posta indesiderata e malware](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="43b28-214">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="43b28-215">Registrazione di controllo</span><span class="sxs-lookup"><span data-stu-id="43b28-215">Audit logging</span></span>

<span data-ttu-id="43b28-216">La registrazione di controllo è disponibile in abbonamenti che includono [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="43b28-216">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="43b28-217">Per visualizzare i dati nei rapporti di protezione dalle minacce, ad esempio il [dashboard di sicurezza](security-dashboard.md), i report sulla sicurezza della [posta elettronica](view-email-security-reports.md)e l' [esploratore](use-explorer-in-security-and-compliance.md), la registrazione di controllo deve essere attivata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43b28-217">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="43b28-218">Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="43b28-218">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="43b28-219">Attività successive all'installazione</span><span class="sxs-lookup"><span data-stu-id="43b28-219">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="43b28-220">Controllare le nuove funzionalità e gli aggiornamenti dei servizi</span><span class="sxs-lookup"><span data-stu-id="43b28-220">Watch for new features and service updates</span></span>

- [<span data-ttu-id="43b28-221">Configurare le opzioni di rilascio standard o di destinazione</span><span class="sxs-lookup"><span data-stu-id="43b28-221">Set up the Standard or Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)

- [<span data-ttu-id="43b28-222">Accedere al centro messaggi per visualizzare gli annunci delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="43b28-222">Go to your Message center to view feature announcements</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) 

- [<span data-ttu-id="43b28-223">Visitare la Guida di orientamento di Microsoft 365 per visualizzare lo stato delle nuove funzionalità</span><span class="sxs-lookup"><span data-stu-id="43b28-223">Visit the Microsoft 365 Roadmap to see status of new features</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="43b28-224">Esaminare le descrizioni dei servizi di Office 365</span><span class="sxs-lookup"><span data-stu-id="43b28-224">Review the Office 365 Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)

### <a name="see-how-threat-protection-features-are-working-for-your-organization"></a><span data-ttu-id="43b28-225">Vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="43b28-225">See how threat protection features are working for your organization</span></span>

- [<span data-ttu-id="43b28-226">Visitare il dashboard di sicurezza</span><span class="sxs-lookup"><span data-stu-id="43b28-226">Visit your security dashboard</span></span>](security-dashboard.md)

- <span data-ttu-id="43b28-227">[Visualizzare i report per Office 365 ATP](view-reports-for-atp.md), tra cui [Esplora risorse](use-explorer-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="43b28-227">[View the reports for Office 365 ATP](view-reports-for-atp.md), including [Explorer](use-explorer-in-security-and-compliance.md)</span></span>

- [<span data-ttu-id="43b28-228">Visualizzare i report sulla sicurezza della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="43b28-228">View your email security reports</span></span>](view-email-security-reports.md)

### <a name="periodically-review-and-revise-your-threat-protection-policies"></a><span data-ttu-id="43b28-229">Rivedere e rivedere periodicamente i criteri di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="43b28-229">Periodically review and revise your threat protection policies</span></span>

- [<span data-ttu-id="43b28-230">Esaminare il Punteggio sicuro</span><span class="sxs-lookup"><span data-stu-id="43b28-230">Review your Secure Score</span></span>](microsoft-secure-score.md)

- [<span data-ttu-id="43b28-231">Utilizzare gli smart report e le informazioni dettagliate nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="43b28-231">Use your smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 

- [<span data-ttu-id="43b28-232">Mantenere gli utenti sicuri con le funzionalità di analisi e risposta alle minacce di Office 365</span><span class="sxs-lookup"><span data-stu-id="43b28-232">Keep users safe with Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md) 
 