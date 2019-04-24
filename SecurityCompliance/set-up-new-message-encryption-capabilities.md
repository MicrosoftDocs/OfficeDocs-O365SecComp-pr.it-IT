---
title: Configurare le nuove funzionalità di Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/12/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection, l'organizzazione può utilizzare le comunicazioni di posta elettronica protette con persone all'interno e all'esterno dell'organizzazione. Le nuove funzionalità OME sono compatibili con altre organizzazioni di Office 365, Outlook.com, Gmail e altri servizi di posta elettronica.
ms.openlocfilehash: ea8756d08b1c172c433d6cd8ad1752c4c7ad64e9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260754"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="a248c-104">Configurare le nuove funzionalità di Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="a248c-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="a248c-105">Le nuove funzionalità di crittografia dei messaggi di Office 365 consentono alle organizzazioni di condividere la posta elettronica protetta con chiunque su qualsiasi dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a248c-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="a248c-106">Gli utenti possono scambiare messaggi protetti con altre organizzazioni di Office 365, nonché clienti non di Office 365 utilizzando Outlook.com, Gmail e altri servizi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a248c-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

||
|:-----|
|<span data-ttu-id="a248c-107">Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a248c-107">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="a248c-108">Questo articolo è destinato agli amministratori e ai professionisti IT.</span><span class="sxs-lookup"><span data-stu-id="a248c-108">This article is intended for administrators and IT Pros.</span></span> <span data-ttu-id="a248c-109">Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="a248c-109">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="a248c-110">Attenersi alla procedura riportata di seguito per verificare che le nuove funzionalità OME siano disponibili nell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a248c-110">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="a248c-111">Verificare che Azure Rights Management sia attivo</span><span class="sxs-lookup"><span data-stu-id="a248c-111">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="a248c-112">Le nuove funzionalità OME sfruttano le funzionalità di protezione di Azure [Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), la tecnologia utilizzata da [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) per proteggere i messaggi di posta elettronica e i documenti tramite i controlli di accesso e crittografia.</span><span class="sxs-lookup"><span data-stu-id="a248c-112">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="a248c-113">L'unico prerequisito per l'utilizzo delle nuove funzionalità OME è che [Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) deve essere attivato nel tenant dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a248c-113">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="a248c-114">In caso contrario, Office 365 attiva automaticamente le nuove funzionalità OME e non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="a248c-114">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="a248c-115">Azure RMS viene attivato automaticamente per la maggior parte dei piani idonei, quindi probabilmente non è necessario eseguire alcuna operazione anche in questo caso.</span><span class="sxs-lookup"><span data-stu-id="a248c-115">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="a248c-116">Per ulteriori informazioni, vedere [attivazione di Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) .</span><span class="sxs-lookup"><span data-stu-id="a248c-116">See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a248c-117">Se si utilizza Active Directory Rights Management Service (AD RMS) con Exchange Online, è necessario [eseguire la migrazione a Azure Information Protection prima di](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) poter utilizzare le nuove funzionalità ome.</span><span class="sxs-lookup"><span data-stu-id="a248c-117">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="a248c-118">OME non è compatibile con AD RMS.</span><span class="sxs-lookup"><span data-stu-id="a248c-118">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="a248c-119">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="a248c-119">For more information, see:</span></span>

- <span data-ttu-id="a248c-120">[Quali abbonamenti sono necessari per utilizzare le nuove funzionalità ome?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) per verificare se il piano di sottoscrizione include Azure Information Protection (che include funzionalità di Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="a248c-120">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="a248c-121">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) per informazioni sull'acquisto di una sottoscrizione idonea.</span><span class="sxs-lookup"><span data-stu-id="a248c-121">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="a248c-122">Attivazione manuale di Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="a248c-122">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="a248c-123">Se è stato disabilitato Azure RMS o se non è stato attivato automaticamente per qualsiasi motivo, è possibile attivarlo manualmente nel:</span><span class="sxs-lookup"><span data-stu-id="a248c-123">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="a248c-124">Interfaccia di **amministrazione di office 365**: vedere [come attivare Azure Rights Management dall'interfaccia di amministrazione di Office 365](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a248c-124">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="a248c-125">**Portale di Azure**: vedere [come attivare Azure Rights Management dal portale di Azure](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a248c-125">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="a248c-126">Configurare la gestione della chiave tenant di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="a248c-126">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="a248c-127">Questo passo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a248c-127">This is an optional step.</span></span> <span data-ttu-id="a248c-128">L'impostazione predefinita e la procedura consigliata per la maggior parte dei tenant di Office 365 sono le impostazioni predefinite per la gestione della chiave radice per Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="a248c-128">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="a248c-129">In questo caso, non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="a248c-129">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="a248c-130">Esistono diversi motivi, ad esempio i requisiti di conformità, che potrebbero richiedere la generazione e la gestione della chiave radice (nota anche come Bring your own key (BYOK)).</span><span class="sxs-lookup"><span data-stu-id="a248c-130">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="a248c-131">In questo caso, è consigliabile completare i passaggi necessari prima di impostare le nuove funzionalità OME.</span><span class="sxs-lookup"><span data-stu-id="a248c-131">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="a248c-132">Per ulteriori informazioni, vedere [Planning and implementing your Azure Information Protection tenant Key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) .</span><span class="sxs-lookup"><span data-stu-id="a248c-132">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="a248c-133">Verificare la nuova configurazione OME in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a248c-133">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="a248c-134">È possibile verificare che il tenant di Office 365 sia configurato correttamente per l'utilizzo delle nuove funzionalità OME in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a248c-134">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="a248c-135">[Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) utilizzando un account con autorizzazioni di amministratore globale nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a248c-135">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="a248c-136">Eseguire il cmdlet Get-IRMConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a248c-136">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="a248c-137">Verrà visualizzato un valore $True per il parametro AzureRMSEnabled, che indica che OME è configurato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="a248c-137">You should see a value of $True for the AzureRMSEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="a248c-138">In caso contrario, utilizzare Set-IRMConfiguration per impostare il valore di AzureRMSEnabled su $True per abilitare OME.</span><span class="sxs-lookup"><span data-stu-id="a248c-138">If it is not, use Set-IRMConfiguration to set the value of AzureRMSEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="a248c-139">Eseguire il cmdlet Test-IRMConfiguration utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a248c-139">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="a248c-140">**Esempio**:</span><span class="sxs-lookup"><span data-stu-id="a248c-140">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="a248c-141">La disponibilità di un messaggio di posta elettronica del mittente è facoltativa, ma forza il sistema a eseguire ulteriori controlli.</span><span class="sxs-lookup"><span data-stu-id="a248c-141">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="a248c-142">Utilizzare l'indirizzo di posta elettronica di qualsiasi utente nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a248c-142">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="a248c-143">I risultati devono essere simili a:</span><span class="sxs-lookup"><span data-stu-id="a248c-143">Your results should be similar to:</span></span>

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

   - <span data-ttu-id="a248c-144">Il nome dell'organizzazione di Office 365 sostituirà *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="a248c-144">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="a248c-145">I nomi dei modelli predefiniti possono essere diversi da quelli visualizzati in alto.</span><span class="sxs-lookup"><span data-stu-id="a248c-145">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="a248c-146">Per ulteriori informazioni, vedere Configuring [and Managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) .</span><span class="sxs-lookup"><span data-stu-id="a248c-146">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="a248c-147">Eseguire il cmdlet Remove-PSSession per disconnettersi dal servizio Rights Management.</span><span class="sxs-lookup"><span data-stu-id="a248c-147">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="a248c-148">Passaggi successivi: definire le regole del flusso di posta per l'utilizzo delle nuove funzionalità OME</span><span class="sxs-lookup"><span data-stu-id="a248c-148">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="a248c-149">Se sono già state configurate regole del flusso di posta per crittografare la posta elettronica nell'organizzazione di Office 365, è necessario aggiornare le regole esistenti per utilizzare le nuove funzionalità OME.</span><span class="sxs-lookup"><span data-stu-id="a248c-149">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="a248c-150">Per le nuove distribuzioni, è necessario creare nuove regole del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="a248c-150">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a248c-151">Se non si aggiornano le regole del flusso di posta, gli utenti continueranno a ricevere messaggi di posta elettronica crittografati che utilizzano il formato di allegato HTML precedente, anziché la nuova esperienza di integrazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="a248c-151">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="a248c-152">Le regole del flusso di posta determinano in quali condizioni devono essere crittografati i messaggi di posta elettronica, nonché le condizioni per la rimozione della crittografia.</span><span class="sxs-lookup"><span data-stu-id="a248c-152">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="a248c-153">Quando si imposta un'azione per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati quando vengono inviati.</span><span class="sxs-lookup"><span data-stu-id="a248c-153">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="a248c-154">Per la procedura di creazione di regole del flusso di posta per OME, vedere [define Mail Flow Rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="a248c-154">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="a248c-155">Per aggiornare le regole esistenti per l'utilizzo delle nuove funzionalità OME:</span><span class="sxs-lookup"><span data-stu-id="a248c-155">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="a248c-156">Nell'interfaccia di amministrazione di Office 365, accedere a interfaccia di **amministrazione di _GT_ Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a248c-156">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="a248c-157">Nell'interfaccia di amministrazione di Exchange, andare a **flusso di posta _GT_ Rules**.</span><span class="sxs-lookup"><span data-stu-id="a248c-157">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="a248c-158">Per ogni regola, **eseguire le operazioni seguenti**:</span><span class="sxs-lookup"><span data-stu-id="a248c-158">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="a248c-159">Selezionare **modifica la sicurezza dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="a248c-159">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="a248c-160">Selezionare **Apply Office 365 Message Encryption and Rights Protection**.</span><span class="sxs-lookup"><span data-stu-id="a248c-160">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="a248c-161">Selezionare un modello RMS dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a248c-161">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="a248c-162">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a248c-162">Select **Save**.</span></span>
    - <span data-ttu-id="a248c-163">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="a248c-163">Select **OK**.</span></span>
