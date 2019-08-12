---
title: Configurare le nuove funzionalità di Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Con le nuove funzionalità di Office 365 Message Encryption predefinite in Azure Information Protection, l'organizzazione può usare la comunicazione tramite posta elettronica protetta con le persone interne ed esterne all'organizzazione. Le nuove funzionalità OME funzionano con le altre organizzazioni di Office 365, Outlook.com, Gmail e altri servizi di posta elettronica.
ms.openlocfilehash: 835b1d6f40868684536dbea8f75dab0665950210
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854800"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="9c1ec-104">Configurare le nuove funzionalità di Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="9c1ec-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="9c1ec-105">Le nuove funzionalità di Office 365 Message Encryption (OME) consentono alle organizzazioni di condividere la posta elettronica protetta con qualsiasi dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="9c1ec-106">Gli utenti possono scambiare messaggi protetti con altre organizzazioni di Office 365, oltre che con clienti non di Office 365 che usano Outlook.com, Gmail e altri servizi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

||
|:-----|
|<span data-ttu-id="9c1ec-107">Questo articolo fa parte di una serie di articoli più ampia relativa a Office 365 Message Encryption.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-107">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="9c1ec-108">Quest’articolo è destinato ad amministratori e professionisti IT.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-108">This article is intended for administrators and IT Pros.</span></span> <span data-ttu-id="9c1ec-109">Per informazioni sull'invio o sulla ricezione di un messaggio crittografato, vedere l'elenco di articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo più adatto alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-109">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="9c1ec-110">Seguire questa procedura per verificare che le nuove funzionalità di OME siano disponibili nell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-110">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="9c1ec-111">Verificare che Azure Rights Management sia attivo</span><span class="sxs-lookup"><span data-stu-id="9c1ec-111">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="9c1ec-112">Le nuove funzionalità di OME sfruttano le caratteristiche di protezione di Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/it-IT/azure/information-protection/what-is-information-protection), la tecnologia usata da [Azure Information Protection](https://docs.microsoft.com/it-IT/azure/information-protection/what-is-azure-rms) per proteggere i messaggi di posta elettronica e i documenti tramite crittografia e controlli di accesso.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-112">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="9c1ec-113">L'unico requisito necessario per usare le nuove funzionalità di OME è che [Azure Rights Management](https://docs.microsoft.com/it-IT/azure/information-protection/what-is-azure-rms) debba essere attivato nel tenant dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-113">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="9c1ec-114">In tal caso, Office 365 attiva automaticamente le nuove funzionalità di OME e non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-114">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="9c1ec-115">Azure RMS viene attivato automaticamente anche per la maggior parte dei piani idonei, pertanto non è necessario eseguire alcuna operazione a tal riguardo.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-115">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="9c1ec-116">Per altre informazioni, vedere [Attivazione di Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-116">See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9c1ec-117">Se si usa Active Directory Rights Management Services (AD RMS) con Exchange Online, è necessario eseguire la migrazione ad Azure Information Protection](https://docs.microsoft.com/it-IT/azure/information-protection/migrate-from-ad-rms-to-azure-rms) prima di poter usare le nuove funzionalità di OME.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-117">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="9c1ec-118">OME non è compatibile con AD RMS.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-118">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="9c1ec-119">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="9c1ec-119">For more information, see:</span></span>

- <span data-ttu-id="9c1ec-120">[Quali abbonamenti sono necessari per usare le nuove funzionalità di OME? ](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) per verificare se il piano di abbonamento include Azure Information Protection (che include le funzionalità di Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-120">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="9c1ec-121">Per informazioni sull'acquisto di un abbonamento idoneo, vedere [Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-121">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="9c1ec-122">Attivazione manuale di Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="9c1ec-122">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="9c1ec-123">Se è stato disabilitato Azure RMS o se non è stato attivato automaticamente, è possibile attivarlo manualmente in:</span><span class="sxs-lookup"><span data-stu-id="9c1ec-123">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="9c1ec-124">Interfaccia di amministrazione di Microsoft 365\*\*: per istruzioni, vedere [Come attivare Azure Rights Management dall'interfaccia di amministrazione](https://docs.microsoft.com/it-IT/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-124">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="9c1ec-125">**Portale di Azure**: per istruzioni, vedere [Come attivare Azure Rights Management dal Portale di Azure](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-125">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="9c1ec-126">Configurare la gestione della chiave tenant di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="9c1ec-126">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="9c1ec-127">Questo passo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-127">This is an optional step.</span></span> <span data-ttu-id="9c1ec-128">La gestione della chiave radice di Azure Information Protection da parte di Microsoft è un’impostazione predefinita e la procedura consigliata per la maggior parte dei tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-128">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="9c1ec-129">Se questo è il caso, non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-129">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="9c1ec-130">Ci sono diversi motivi, ad esempio i requisiti di conformità, che possono richiedere di generare e gestire una chiave radice, nota anche come bring your own key (BYOK).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-130">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="9c1ec-131">In questo caso, è consigliabile completare i passaggi necessari prima di configurare le nuove funzionalità di OME.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-131">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="9c1ec-132">Per altre informazioni, vedere [Pianificazione e implementazione della chiave tenant di Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-132">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="9c1ec-133">Verificare la nuova configurazione di OME in PowerShell di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9c1ec-133">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="9c1ec-134">È possibile verificare se il tenant di Office 365 sia configurato correttamente per l'uso delle nuove funzionalità di OME disponibili in [PowerShell di Exchange Online](https://docs.microsoft.com/it-IT/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-134">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="9c1ec-135">Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/it-IT/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando un account con autorizzazioni di amministratore globale nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-135">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="9c1ec-136">Eseguire il cmdlet Get-IRMConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-136">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="9c1ec-137">Dovrebbe essere visualizzato un valore di $True per il parametro AzureRMSLicensingEnabled, che indica che OME è configurato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-137">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="9c1ec-138">Se non lo è, usare Set-IRMConfiguration per impostare il valore di AzureRMSLicensingEnabled su $True per abilitare OME.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-138">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="9c1ec-139">Eseguire il cmdlet Test-IRMConfiguration usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9c1ec-139">Run the script by using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="9c1ec-140">**Esempio**:</span><span class="sxs-lookup"><span data-stu-id="9c1ec-140">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="9c1ec-141">L'inserimento di un indirizzo di posta elettronica del mittente è facoltativo, ma forza il sistema a eseguire ulteriori controlli.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-141">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="9c1ec-142">Usare l'indirizzo di posta elettronica di un utente nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-142">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="9c1ec-143">Il risultato dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9c1ec-143">Your results should be similar to:</span></span>

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

   - <span data-ttu-id="9c1ec-144">Il nome dell'organizzazione di Office 365 sostituisce *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-144">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="9c1ec-145">I nomi dei modelli predefiniti potrebbero essere diversi rispetto a quelli visualizzati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-145">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="9c1ec-146">Per altre informazioni, vedere [Configurazione e gestione dei modelli per Azure Information Protection](https://docs.microsoft.com/it-IT/azure/information-protection/configure-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-146">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="9c1ec-147">Eseguire il cmdlet Remove-PSSession per disconnettersi dal servizio Rights Management.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-147">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="9c1ec-148">Passaggi successivi: definire le regole del flusso di posta per usare le nuove funzionalità di OME</span><span class="sxs-lookup"><span data-stu-id="9c1ec-148">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="9c1ec-149">Se in precedenza sono state configurate regole del flusso di posta per crittografare la posta elettronica nell'organizzazione di Office 365, è necessario aggiornare le regole esistenti per usare le nuove funzionalità di OME.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-149">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="9c1ec-150">Per le nuove distribuzioni, è necessario creare nuove regole per il flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-150">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9c1ec-151">In caso contrario, gli utenti continueranno a ricevere messaggi crittografati che usano il formato dell'allegato HTML precedente invece della nuova esperienza di OME.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-151">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="9c1ec-152">Le regole del flusso di posta elettronica determinano le condizioni con cui i messaggi di posta elettronica devono essere crittografati e le condizioni per rimuovere la crittografia.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-152">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="9c1ec-153">Quando si imposta un'azione per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati al momento dell'invio.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-153">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="9c1ec-154">Per altre passaggi sulla creazione delle regole del flusso di posta elettronica di OME, vedere [Definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="9c1ec-154">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="9c1ec-155">Aggiornare le regole esistenti per usare le nuove funzionalità di OME:</span><span class="sxs-lookup"><span data-stu-id="9c1ec-155">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="9c1ec-156">Nell'interfaccia di amministrazione di Microsoft 365, passare a **Interfacce di amministrazione > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-156">In the Microsoft 365 admin center, in the left pane, go to **Admin centersMicrosoft Search**</span></span>
2. <span data-ttu-id="9c1ec-157">Nell'interfaccia di amministrazione di Exchange, passare a **Flusso di posta > Regole**.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-157">In the Exchange admin center (EAC), go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="9c1ec-158">Per ogni regola, in **Fai quanto segue**:</span><span class="sxs-lookup"><span data-stu-id="9c1ec-158">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="9c1ec-159">Selezionare **Modifica la sicurezza del messaggio**.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-159">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="9c1ec-160">Selezionare Applica Office 365 Message Encryption e la protezione tramite diritti\*\*.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-160">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="9c1ec-161">Selezionare un modello RMS dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-161">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="9c1ec-162">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-162">Select **Save**.</span></span>
    - <span data-ttu-id="9c1ec-163">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c1ec-163">Select **OK**.</span></span>
