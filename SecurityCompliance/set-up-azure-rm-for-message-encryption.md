---
title: Configurare Microsoft Azure AD Rights Management per la crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 'Crittografia dei messaggi di Office 365 dipende da Microsoft Azure Rights Management (precedentemente noto come Windows Azure Active Directory Rights Management). '
ms.openlocfilehash: 99c8de49330cf99545d28d81e0c99c2138797356
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530850"
---
# <a name="set-up-azure-rights-management-for-office-365-message-encryption"></a><span data-ttu-id="8f7c8-103">Configurare Microsoft Azure AD Rights Management per la crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="8f7c8-103">Set up Azure Rights Management for Office 365 Message Encryption</span></span>

<span data-ttu-id="8f7c8-104">In questo argomento vengono descritti i passaggi da seguire per poter attivare e quindi impostare backup Azure Rights Management (RMS), parte di Azure Information Protection per l'utilizzo con la crittografia messaggi Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="8f7c8-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with Office 365 Message Encryption (OME).</span></span>
  
## <a name="prerequisites-for-using-office-365-message-encryption"></a><span data-ttu-id="8f7c8-105">Prerequisiti per l'utilizzo della crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="8f7c8-105">Prerequisites for using Office 365 Message Encryption</span></span>
<span data-ttu-id="8f7c8-106"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="8f7c8-106"></span></span>

<span data-ttu-id="8f7c8-p101">Office 365 messaggio crittografia dei, tra cui IRM, dipende dall'Azure Rights Management (Azure RMS). RMS Azure è la tecnologia di protezione utilizzata per la protezione delle informazioni di Azure. Per utilizzare OME, l'organizzazione Office 365 deve includere una sottoscrizione di Exchange Online o Exchange Online Protection che, a sua volta, include una sottoscrizione di Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p101">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS). Azure RMS is the protection technology used by Azure Information Protection. To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="8f7c8-110">Se non si è certi della sottoscrizione include, vedere la descrizione del servizio Exchange Online [Message Policy, Recovery e conformità](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span><span class="sxs-lookup"><span data-stu-id="8f7c8-110">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>
    
- <span data-ttu-id="8f7c8-111">Se non si dispone di una sottoscrizione di RMS Azure per Exchange Online o Exchange Online Protection, è necessario acquistare una sottoscrizione e attivarlo prima.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-111">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>
    
    <span data-ttu-id="8f7c8-p102">Per informazioni sull'acquisto di una sottoscrizione per Azure Rights Management, vedere [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). Nella sezione successiva vengono fornite informazioni relative all'attivazione di Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p102">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). The next section gives you information about activating Azure Rights Management.</span></span>
    
- <span data-ttu-id="8f7c8-114">Se si dispone di Azure Rights Management, ma non è configurato per Exchange Online o Exchange Online Protection, in questo articolo viene illustrato come attivare Azure Rights Management e quindi il viene descritto il modo migliore per impostare OME per funzionare con Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-114">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>
    
- <span data-ttu-id="8f7c8-p103">Se già stato configurato OME per funzionare con Azure Rights Management per Exchange Online o Exchange Online Protection, a seconda della modalità di configurazione, potrebbe essere possibile iniziare a utilizzare le funzionalità nuove e OME immediatamente. In questo articolo viene illustrato come determinare se è stato impostato OME correttamente, come procedere se è necessario modificare la configurazione, e cosa succede se si sceglie di non modificare il programma di installazione. Ad esempio, per poter utilizzare le nuove funzionalità, è necessario utilizzare RMS Azure con OME. È possibile utilizzare le nuove funzionalità con un RMS di locale Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p103">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away. This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup. For example, in order to use the new capabilities, you must use Azure RMS with OME. You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>
    
## <a name="activate-azure-rights-management-for-ome-in-office-365"></a><span data-ttu-id="8f7c8-119">Attivare Azure Rights Management per OME in Office 365</span><span class="sxs-lookup"><span data-stu-id="8f7c8-119">Activate Azure Rights Management for OME in Office 365</span></span>
<span data-ttu-id="8f7c8-120"><a name="activatewarm"> </a></span><span class="sxs-lookup"><span data-stu-id="8f7c8-120"></span></span>

<span data-ttu-id="8f7c8-p104">È necessario attivare Azure Rights Management in modo che gli utenti dell'organizzazione possono applicare la protezione delle informazioni per i messaggi inviati e aprire messaggi e file sono protetti dal servizio Azure Rights Management. Per ulteriori informazioni, vedere [Attivazione di Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Dopo aver completato l'attivazione, tornare a questa e continuare con le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p104">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service. For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="8f7c8-124">Impostare OME da utilizzare RMS Azure mediante l'importazione di pubblicazione trusted (domini di pubblicazione trusted)</span><span class="sxs-lookup"><span data-stu-id="8f7c8-124">Set up OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>
<span data-ttu-id="8f7c8-125"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="8f7c8-125"></span></span>

<span data-ttu-id="8f7c8-p105">Un dominio di pubblicazione Trusted è un file XML che contiene informazioni sulle impostazioni di gestione dei diritti dell'organizzazione. Ad esempio, il dominio di pubblicazione Trusted contiene informazioni sul certificato concessore di licenze server (SLC) utilizzato per la firma e crittografia dei certificati e licenze, gli URL utilizzati per la gestione delle licenze e di pubblicazione e così via. Importare il dominio di pubblicazione Trusted nell'organizzazione Office 365 tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p105">A TPD is an XML file that contains information about your organization's rights management settings. For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on. You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8f7c8-p106">In precedenza, è possibile scegliere di importare domini di pubblicazione trusted dal servizio Active Directory Rights Management (AD RMS) nell'organizzazione Office 365. Tuttavia, in questo modo si impedisce di utilizzo delle nuove funzionalità OME e non è consigliato. Se Office 365 dell'organizzazione è attualmente configurato in questo modo, si consiglia di creare un piano per eseguire la migrazione dal RMS Directory locale attivo per la protezione delle informazioni di Azure basate su cloud. Per ulteriori informazioni, vedere [Migrating from AD RMS per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Non sarà in grado di utilizzare le nuove funzionalità OME fino al completamento della migrazione per la protezione delle informazioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p106">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization. However, doing so will prevent you from using the new OME capabilities and is not recommended. If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection. For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span> 
  
 <span data-ttu-id="8f7c8-134">**Per importare domini di pubblicazione trusted da RMS Azure**</span><span class="sxs-lookup"><span data-stu-id="8f7c8-134">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="8f7c8-135">[Connessione a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8f7c8-135">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="8f7c8-136">Scegliere l'URL di condivisione chiave corrispondente alla posizione geografica dell'organizzazione Office 365:</span><span class="sxs-lookup"><span data-stu-id="8f7c8-136">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>
    
|<span data-ttu-id="8f7c8-137">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="8f7c8-137">**Location**</span></span>|<span data-ttu-id="8f7c8-138">**URL del percorso di condivisione della chiave**</span><span class="sxs-lookup"><span data-stu-id="8f7c8-138">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f7c8-139">Nord America</span><span class="sxs-lookup"><span data-stu-id="8f7c8-139">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="8f7c8-140">Unione Europea</span><span class="sxs-lookup"><span data-stu-id="8f7c8-140">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="8f7c8-141">Asia</span><span class="sxs-lookup"><span data-stu-id="8f7c8-141">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="8f7c8-142">Sud America</span><span class="sxs-lookup"><span data-stu-id="8f7c8-142">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="8f7c8-143">Office 365 per il governo (Government Community Cloud)</span><span class="sxs-lookup"><span data-stu-id="8f7c8-143">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="8f7c8-144">Questo percorso di condivisione chiave di RMS è riservato per i clienti che hanno acquistato Office 365 per SKU governative.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-144">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="8f7c8-145">Configurare il percorso di condivisione chiave eseguendo il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8f7c8-145">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="8f7c8-146">Ad esempio, per configurare il percorso di condivisione se l'organizzazione si trova in Nord America chiave:</span><span class="sxs-lookup"><span data-stu-id="8f7c8-146">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="8f7c8-147">Eseguire il cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con l'opzione RMSOnline - per importare TPD da Azure Rights Management:</span><span class="sxs-lookup"><span data-stu-id="8f7c8-147">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="8f7c8-p107">Dove *TPDName* è il nome da utilizzare per il dominio di pubblicazione Trusted. Ad esempio, "Contoso North American TPD".</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p107">Where  *TPDName*  is the name you want to use for the TPD. For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="8f7c8-150">Per verificare la corretta configurazione organizzazione Office 365 per l'utilizzo del servizio di Azure Rights Management, eseguire il cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con l'opzione RMSOnline - come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8f7c8-150">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="8f7c8-151">Tra l'altro, questo cmdlet verifica la connettività con il servizio di Azure Rights Management, scarica il dominio di pubblicazione Trusted e controlla la validità.</span><span class="sxs-lookup"><span data-stu-id="8f7c8-151">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="8f7c8-152">Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come indicato di seguito per disattivare modelli di Azure Rights Management vengano disponibili in Outlook sul web e Outlook:</span><span class="sxs-lookup"><span data-stu-id="8f7c8-152">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="8f7c8-153">Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come indicato di seguito per attivare Azure Rights Management per la propria organizzazione di posta elettronica basata sul cloud e configurarla per l'utilizzo di Azure Rights Management per la crittografia dei messaggi di Office 365:</span><span class="sxs-lookup"><span data-stu-id="8f7c8-153">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="8f7c8-p108">Per verificare di aver importato il dominio di pubblicazione Trusted e abilitato Azure Rights Management, utilizzare il cmdlet Test-IRMConfiguration per verificare la funzionalità di Azure Rights Management. Per ulteriori informazioni, vedere "Esempi 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p108">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality. For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="8f7c8-156">È possibile avere OME impostata con Active Directory Rights Management non Azure Information Protection, come è possibile procedere?</span><span class="sxs-lookup"><span data-stu-id="8f7c8-156">I have OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="8f7c8-157"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="8f7c8-157"></span></span>

<span data-ttu-id="8f7c8-p109">È possibile continuare a utilizzare le regole di flusso di posta elettronica la crittografia dei messaggi di Office 365 esistente in Active Directory Rights Management, ma non è possibile configurare o utilizzare le nuove funzionalità OME. In realtà, è necessario eseguire la migrazione per la protezione delle informazioni di Azure. Per informazioni sulla migrazione e ciò significa per l'organizzazione, vedere [Migrating from AD RMS per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span><span class="sxs-lookup"><span data-stu-id="8f7c8-p109">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities. Instead, you need to migrate to Azure Information Protection. For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8f7c8-161">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8f7c8-161">Next steps</span></span>
<span data-ttu-id="8f7c8-162"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="8f7c8-162"></span></span>

<span data-ttu-id="8f7c8-163">Dopo aver completato il programma di installazione di Azure Rights Management, se si desidera abilitare le nuove funzionalità OME, vedere [impostare le nuove funzionalità di Office 365 Message Encryption basate sul Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span><span class="sxs-lookup"><span data-stu-id="8f7c8-163">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="8f7c8-164">Dopo aver configurato l'organizzazione di utilizzare le nuove funzionalità OME, si è pronti per [definire le regole del flusso di posta elettronica per proteggere i messaggi di posta elettronica con le nuove funzionalità OME](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="8f7c8-164">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8f7c8-165">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8f7c8-165">Related topics</span></span>
<span data-ttu-id="8f7c8-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="8f7c8-166"></span></span>

[<span data-ttu-id="8f7c8-167">Crittografia in Office 365</span><span class="sxs-lookup"><span data-stu-id="8f7c8-167">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="8f7c8-168">Dettagli tecnici di riferimento sulla crittografia in Office 365</span><span class="sxs-lookup"><span data-stu-id="8f7c8-168">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="8f7c8-169">Che cos'è Azure Rights Management?</span><span class="sxs-lookup"><span data-stu-id="8f7c8-169">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  
