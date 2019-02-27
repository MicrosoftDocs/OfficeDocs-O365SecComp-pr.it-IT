---
title: Configurare le nuove funzionalità di Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: Nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection, l'organizzazione può utilizzare le comunicazioni di posta elettronica protette con persone all'interno e all'esterno dell'organizzazione. Le nuove funzionalità OME sono compatibili con altre organizzazioni di Office 365, Outlook.com, Gmail e altri servizi di posta elettronica.
ms.openlocfilehash: 90247a7e3cd7e5978eb144a2b6f66a9de21a8f96
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296189"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="d68a8-104">Configurare le nuove funzionalità di Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="d68a8-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="d68a8-p102">Le nuove funzionalità di crittografia dei messaggi di Office 365 consentono alle organizzazioni di condividere la posta elettronica protetta con chiunque su qualsiasi dispositivo. Gli utenti possono scambiare messaggi protetti con altre organizzazioni di Office 365, nonché clienti non di Office 365 utilizzando Outlook.com, Gmail e altri servizi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d68a8-p102">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device. Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>


>[!NOTE]
><span data-ttu-id="d68a8-p103">Questo articolo è destinato agli amministratori e ai professionisti IT. Se si è un utente finale, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) per le soluzioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="d68a8-p103">This article is intended for administrators and IT professionals. If you're an end-user, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) for appropriate solutions.</span></span>

<span data-ttu-id="d68a8-109">Attenersi alla procedura riportata di seguito per verificare che le nuove funzionalità OME siano disponibili nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d68a8-109">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 tenant.</span></span> 

## <a name="verify-azure-rights-management-arm-is-active"></a><span data-ttu-id="d68a8-110">Verificare che Azure Rights Management (ARM) sia attivo</span><span class="sxs-lookup"><span data-stu-id="d68a8-110">Verify Azure Rights Management (ARM) is active</span></span>

>[!NOTE]
><span data-ttu-id="d68a8-111">Le nuove funzionalità OME sfruttano le funzionalità di protezione di [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), la tecnologia utilizzata da [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms).</span><span class="sxs-lookup"><span data-stu-id="d68a8-111">The new OME capabilities leverage the protection features in [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms).</span></span>

<span data-ttu-id="d68a8-p104">L'unico prerequisito per l'utilizzo delle nuove funzionalità OME è che [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) deve essere attivato nel tenant di Office 365. In caso contrario, Office 365 attiva automaticamente le nuove funzionalità OME e non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="d68a8-p104">The only prerequisite for using the new OME capabilities is that [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your Office 365 tenant. If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span> 

<span data-ttu-id="d68a8-p105">ARM viene attivato automaticamente per la maggior parte dei piani idonei, quindi probabilmente non è necessario eseguire alcuna operazione anche in questo caso. Per ulteriori informazioni, vedere [attivazione di Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) .</span><span class="sxs-lookup"><span data-stu-id="d68a8-p105">ARM is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either. See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d68a8-p106">Se si utilizza Active Directory Rights Management Service (AD RMS) con Exchange Online, è necessario [eseguire la migrazione a Azure Information Protection prima di](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) poter utilizzare le nuove funzionalità ome. AD RMS non è compatibile con ARM.</span><span class="sxs-lookup"><span data-stu-id="d68a8-p106">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities. AD RMS is not compatible with ARM.</span></span>  

<span data-ttu-id="d68a8-118">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="d68a8-118">For more, see:</span></span>

- <span data-ttu-id="d68a8-119">[Quali abbonamenti sono necessari per utilizzare le nuove funzionalità ome?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) per verificare se il piano di sottoscrizione include Azure Information Protection (che include ARM).</span><span class="sxs-lookup"><span data-stu-id="d68a8-119">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes ARM).</span></span>   
-  <span data-ttu-id="d68a8-120">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) per informazioni sull'acquisto di una sottoscrizione idonea.</span><span class="sxs-lookup"><span data-stu-id="d68a8-120">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-arm"></a><span data-ttu-id="d68a8-121">Attivazione manuale del braccio</span><span class="sxs-lookup"><span data-stu-id="d68a8-121">Manually activating ARM</span></span>

<span data-ttu-id="d68a8-122">Se è stato disabilitato ARM o se non è stato attivato automaticamente per qualsiasi motivo, è possibile attivarlo manualmente nel:</span><span class="sxs-lookup"><span data-stu-id="d68a8-122">If you disabled ARM, or if it was not automatically activated for any reason, you can activated it manually in the :</span></span>

- <span data-ttu-id="d68a8-123">Interfaccia di **amministrazione di office 365**: vedere [come attivare Azure Rights Management dall'interfaccia di amministrazione di Office 365](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) per istruzioni</span><span class="sxs-lookup"><span data-stu-id="d68a8-123">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions</span></span>
- <span data-ttu-id="d68a8-124">**Portale di Azure**: vedere [come attivare Azure Rights Management dal portale di Azure](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d68a8-124">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span> 


## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="d68a8-125">Configurare la gestione della chiave tenant di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="d68a8-125">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="d68a8-p107">Si tratta di un passaggio facoltativo. L'impostazione predefinita e la procedura consigliata per la maggior parte dei tenant di Office 365 sono le impostazioni predefinite per la gestione della chiave radice per Azure Information Protection. In questo caso, non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="d68a8-p107">This is an optional step. Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants. If this is the case, you don't need to do anything.</span></span> 

<span data-ttu-id="d68a8-p108">Esistono diversi motivi, ad esempio i requisiti di conformità, che potrebbero richiedere la generazione e la gestione della chiave radice (nota anche come Bring your own key (BYOK)). In questo caso, è consigliabile completare i passaggi necessari prima di impostare le nuove funzionalità OME. Per ulteriori informazioni, vedere [Planning and implementing your Azure Information Protection tenant Key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) .</span><span class="sxs-lookup"><span data-stu-id="d68a8-p108">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)). If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities. See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span> 


## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="d68a8-132">Verificare la nuova configurazione OME in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="d68a8-132">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="d68a8-133">È possibile verificare che il tenant di Office 365 sia configurato correttamente per l'utilizzo delle nuove funzionalità OME in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="d68a8-133">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="d68a8-134">[Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) utilizzando un account con autorizzazioni di amministratore globale nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d68a8-134">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="d68a8-135">Eseguire il cmdlet Test-IRMConfiguration utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="d68a8-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="d68a8-136">**Esempio**:</span><span class="sxs-lookup"><span data-stu-id="d68a8-136">**Example**:</span></span> 
   
     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```
     
     - <span data-ttu-id="d68a8-p109">La disponibilità di un messaggio di posta elettronica del mittente è facoltativa, ma forza il sistema a eseguire ulteriori controlli. Utilizzare l'indirizzo di posta elettronica di qualsiasi utente nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d68a8-p109">Providing a sender email is optional, but forces the system to perform additional checks. Use the email address of any user in your Office 365 tenant.</span></span> 
     
    <span data-ttu-id="d68a8-139">I risultati devono essere simili a:</span><span class="sxs-lookup"><span data-stu-id="d68a8-139">Your results should be similar to:</span></span>

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

   - <span data-ttu-id="d68a8-140">Il nome dell'organizzazione di Office 365 sostituirà *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="d68a8-140">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="d68a8-p110">I nomi dei modelli predefiniti possono essere diversi da quelli visualizzati in alto. Per ulteriori informazioni, vedere Configuring [and Managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) .</span><span class="sxs-lookup"><span data-stu-id="d68a8-p110">The default template names may be different from those displayed above. See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

3. <span data-ttu-id="d68a8-143">Eseguire il cmdlet Remove-PSSession per disconnettersi dal servizio Rights Management.</span><span class="sxs-lookup"><span data-stu-id="d68a8-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="d68a8-144">Aggiornare le regole del flusso di posta per l'utilizzo delle nuove funzionalità OME</span><span class="sxs-lookup"><span data-stu-id="d68a8-144">Update mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="d68a8-p111">Se sono già state configurate [regole del flusso di posta per crittografare la posta elettronica](define-mail-flow-rules-to-encrypt-email.md) nel tenant di Office 365, è necessario aggiornare queste regole esistenti per utilizzare le nuove funzionalità ome. Per le nuove distribuzioni, questo passaggio non è necessario in questa fase.</span><span class="sxs-lookup"><span data-stu-id="d68a8-p111">If there are previously configured [mail flow rules to encrypt email](define-mail-flow-rules-to-encrypt-email.md) in your Office 365 tenant, you need to update these existing rules to use the new OME capabilities. For new deployments, this step is unnecessary at this stage.</span></span>   

>[!Note]
><span data-ttu-id="d68a8-p112">Le regole del flusso di posta definiscono le condizioni in cui i messaggi di posta elettronica vengono crittografati e quando la crittografia deve essere rimossa. Vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="d68a8-p112">Mail flow rules define the conditions under which email messages are encrypted, and when encryption should be removed. See [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md) for more.</span></span>

<span data-ttu-id="d68a8-149">Per aggiornare le regole esistenti per l'utilizzo delle nuove funzionalità OME:</span><span class="sxs-lookup"><span data-stu-id="d68a8-149">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="d68a8-150">Nell'interfaccia di amministrazione di Office 365, accedere a interfaccia di **amministrazione di _GT_ Exchange**.</span><span class="sxs-lookup"><span data-stu-id="d68a8-150">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>

2. <span data-ttu-id="d68a8-151">Nell'interfaccia di amministrazione di Exchange, andare a **flusso di posta _GT_ Rules**.</span><span class="sxs-lookup"><span data-stu-id="d68a8-151">In the Exchange admin center, go to **Mail flow > Rules**.</span></span> 
3. <span data-ttu-id="d68a8-152">Per ogni regola, **eseguire le operazioni seguenti**:</span><span class="sxs-lookup"><span data-stu-id="d68a8-152">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="d68a8-153">Selezionare **modifica la sicurezza dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="d68a8-153">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="d68a8-154">Selezionare **Apply Office 365 Message Encryption and Rights Protection**.</span><span class="sxs-lookup"><span data-stu-id="d68a8-154">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="d68a8-155">Selezionare un modello RMS dall'elenco</span><span class="sxs-lookup"><span data-stu-id="d68a8-155">Select an RMS template from the list</span></span>
    - <span data-ttu-id="d68a8-156">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d68a8-156">Select **Save**.</span></span>
    - <span data-ttu-id="d68a8-157">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d68a8-157">Select **OK**.</span></span>
  
>[!IMPORTANT]
><span data-ttu-id="d68a8-158">Se non si aggiornano le regole del flusso di posta esistenti, gli utenti continueranno a ricevere posta crittografata che utilizza il formato di allegato HTML precedente anziché le nuove funzionalità OME.</span><span class="sxs-lookup"><span data-stu-id="d68a8-158">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new OME capabilities.</span></span>
