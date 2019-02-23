---
title: Configurare Microsoft Azure AD Rights Management per la versione precedente della Crittografia messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: La versione precedente della crittografia dei messaggi di Office 365 dipende da Microsoft Azure Rights Management (precedentemente noto come Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 89b86035f57699457c86fefb49888b8428f4e01c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214376"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="b17d3-103">Configurare Microsoft Azure AD Rights Management per la versione precedente della Crittografia messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="b17d3-103">Set up Azure Rights Management for the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="b17d3-104">In questo argomento vengono descritti i passaggi da seguire per poter attivare e configurare Azure Rights Management (RMS), parte di Azure Information Protection, per l'utilizzo con la versione precedente di Office 365 Message Encryption (OME).</span><span class="sxs-lookup"><span data-stu-id="b17d3-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="b17d3-105">Questo articolo si applica solo alla versione precedente di OME</span><span class="sxs-lookup"><span data-stu-id="b17d3-105">This article only applies to the previous version of OME</span></span>
<span data-ttu-id="b17d3-p101">Se non è stata ancora spostata l'organizzazione di Office 365 nelle nuove funzionalità OME, ma è già stata distribuita OME, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia di effettuare un piano per passare alle nuove funzionalità OME non appena è ragionevole per la propria organizzazione. Per istruzioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md). Per ulteriori informazioni sul funzionamento delle nuove funzionalità, vedere [crittografia dei messaggi di Office 365](ome.md). Il resto di questo articolo si riferisce al comportamento OME prima del rilascio delle nuove funzionalità OME.</span><span class="sxs-lookup"><span data-stu-id="b17d3-p101">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md). The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="b17d3-111">Prerequisiti per l'utilizzo della versione precedente della crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="b17d3-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="b17d3-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="b17d3-112"></span></span>

<span data-ttu-id="b17d3-p102">La crittografia dei messaggi di Office 365 (OME), tra cui IRM, dipende da Azure Rights Management (Azure RMS). Azure RMS è la tecnologia di protezione utilizzata da Azure Information Protection. Per utilizzare OME, l'organizzazione di Office 365 deve includere un abbonamento a Exchange Online o Exchange Online Protection che, a sua disposizione, include una sottoscrizione di Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="b17d3-p102">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS). Azure RMS is the protection technology used by Azure Information Protection. To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="b17d3-116">Se non si è sicuri di cosa include la sottoscrizione, vedere le descrizioni del servizio Exchange Online per i [criteri dei messaggi, il ripristino e la conformità](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span><span class="sxs-lookup"><span data-stu-id="b17d3-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="b17d3-117">Se non si dispone di una sottoscrizione di Azure RMS per Exchange Online o Exchange Online Protection, è necessario acquistare un abbonamento e attivarlo per primo.</span><span class="sxs-lookup"><span data-stu-id="b17d3-117">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>

    <span data-ttu-id="b17d3-p103">Per informazioni sull'acquisto di una sottoscrizione a Azure Rights Management, vedere [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). Nella sezione successiva vengono fornite informazioni sull'attivazione di Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="b17d3-p103">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). The next section gives you information about activating Azure Rights Management.</span></span>

- <span data-ttu-id="b17d3-120">Se si dispone di Azure Rights Management, ma non è configurato per Exchange Online o Exchange Online Protection, in questo articolo viene illustrato come attivare Azure Rights Management e quindi viene descritto il modo migliore per configurare OME per l'utilizzo con Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="b17d3-120">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="b17d3-p104">Se la OME è già stata configurata per l'utilizzo con Azure Rights Management per Exchange Online o Exchange Online Protection, a seconda del modo in cui è stata configurata, potrebbe essere possibile iniziare a utilizzare OME e le sue nuove funzionalità subito. In questo articolo viene illustrato come determinare se è stato impostato correttamente OME, cosa fare se è necessario modificare la configurazione e cosa succede se si sceglie di non modificare la configurazione. Ad esempio, per poter utilizzare le nuove funzionalità, è necessario utilizzare Azure RMS con OME. Non è possibile utilizzare le nuove funzionalità con un RMS di Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="b17d3-p104">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away. This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup. For example, in order to use the new capabilities, you must use Azure RMS with OME. You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="b17d3-125">Attivare Azure Rights Management per la versione precedente di OME in Office 365</span><span class="sxs-lookup"><span data-stu-id="b17d3-125">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="b17d3-p105">È necessario attivare Azure Rights Management in modo che gli utenti dell'organizzazione possano applicare la protezione delle informazioni ai messaggi inviati e aprire i messaggi e i file protetti dal servizio Azure Rights Management. Per istruzioni, vedere [attivazione di Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Dopo aver completato l'attivazione, tornare qui e continuare con le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b17d3-p105">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service. For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="b17d3-129">Impostare la versione precedente di OME per l'utilizzo di Azure RMS importando domini di pubblicazione trusted (pubblicazione trusted)</span><span class="sxs-lookup"><span data-stu-id="b17d3-129">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="b17d3-p106">Un dominio di pubblicazione trusted è un file XML che contiene informazioni sulle impostazioni di gestione dei diritti dell'organizzazione. Ad esempio, il dominio di pubblicazione trusted contiene informazioni sul certificato concessore di licenze server (SLC) utilizzato per la firma e la crittografia dei certificati e della licenza, gli URL utilizzati per la gestione delle licenze e la pubblicazione e così via. Si importa il dominio di pubblicazione trusted nell'organizzazione di Office 365 utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b17d3-p106">A TPD is an XML file that contains information about your organization's rights management settings. For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on. You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b17d3-p107">In precedenza, è possibile scegliere di importare pubblicazione trusted dal servizio Active Directory Rights Management (AD RMS) nell'organizzazione di Office 365. Tuttavia, in questo modo si eviterà di utilizzare le nuove funzionalità OME e non è consigliabile. Se l'organizzazione di Office 365 è attualmente configurata in questo modo, Microsoft consiglia di creare un piano per eseguire la migrazione dal server RMS di Active Directory locale alla protezione delle informazioni di Azure basata su cloud. Per ulteriori informazioni, vedere [migrazione da ad RMS a Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Non sarà possibile utilizzare le nuove funzionalità OME fino a quando non è stata completata la migrazione a Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="b17d3-p107">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization. However, doing so will prevent you from using the new OME capabilities and is not recommended. If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection. For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="b17d3-138">**Per importare pubblicazione trusted da Azure RMS**</span><span class="sxs-lookup"><span data-stu-id="b17d3-138">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="b17d3-139">[Connettersi a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b17d3-139">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="b17d3-140">Scegliere l'URL di condivisione delle chiavi corrispondente alla posizione geografica dell'organizzazione di Office 365:</span><span class="sxs-lookup"><span data-stu-id="b17d3-140">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>

|<span data-ttu-id="b17d3-141">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="b17d3-141">**Location**</span></span>|<span data-ttu-id="b17d3-142">**URL del percorso di condivisione della chiave**</span><span class="sxs-lookup"><span data-stu-id="b17d3-142">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b17d3-143">Nord America</span><span class="sxs-lookup"><span data-stu-id="b17d3-143">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="b17d3-144">Unione Europea</span><span class="sxs-lookup"><span data-stu-id="b17d3-144">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="b17d3-145">Asia</span><span class="sxs-lookup"><span data-stu-id="b17d3-145">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="b17d3-146">Sud America</span><span class="sxs-lookup"><span data-stu-id="b17d3-146">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="b17d3-147">Office 365 per il governo (Government Community Cloud)</span><span class="sxs-lookup"><span data-stu-id="b17d3-147">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="b17d3-148">Questo percorso di condivisione della chiave di RMS è riservato ai clienti che hanno acquistato Office 365 per gli SKU governativi.</span><span class="sxs-lookup"><span data-stu-id="b17d3-148">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="b17d3-149">Configurare il percorso di condivisione della chiave eseguendo il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b17d3-149">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="b17d3-150">Ad esempio, per configurare il percorso di condivisione della chiave se l'organizzazione si trova in Nord America:</span><span class="sxs-lookup"><span data-stu-id="b17d3-150">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="b17d3-151">Eseguire il cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con l'opzione-RMSOnline per importare il dominio di pubblicazione trusted da Azure Rights Management:</span><span class="sxs-lookup"><span data-stu-id="b17d3-151">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="b17d3-p108">Dove *TPDName* è il nome che si desidera utilizzare per il dominio di pubblicazione trusted. Ad esempio, "contoso North American di pubblicazione trusted".</span><span class="sxs-lookup"><span data-stu-id="b17d3-p108">Where  *TPDName*  is the name you want to use for the TPD. For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="b17d3-154">Per verificare che l'organizzazione di Office 365 sia stata configurata correttamente per l'utilizzo del servizio Azure Rights Management, eseguire il cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con l'opzione-RMSOnline, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b17d3-154">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="b17d3-155">Tra le altre cose, questo cmdlet consente di verificare la connettività con il servizio Azure Rights Management, di scaricare il dominio di pubblicazione trusted e di verificarne la validità.</span><span class="sxs-lookup"><span data-stu-id="b17d3-155">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="b17d3-156">Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come segue per disabilitare i modelli di Azure Rights Management disponibili in Outlook sul Web e Outlook:</span><span class="sxs-lookup"><span data-stu-id="b17d3-156">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="b17d3-157">Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come segue per abilitare Azure Rights Management per l'organizzazione di posta elettronica basata sul cloud e configurarla per l'utilizzo di Azure Rights Management per la crittografia dei messaggi di Office 365:</span><span class="sxs-lookup"><span data-stu-id="b17d3-157">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="b17d3-p109">Per verificare di aver importato correttamente il dominio di pubblicazione trusted e abilitato Azure Rights Management, utilizzare il cmdlet Test-IRMConfiguration per testare la funzionalità di Azure Rights Management. Per ulteriori informazioni, vedere l'esempio 1 in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b17d3-p109">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality. For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="b17d3-160">La versione precedente di OME è stata configurata con Active Directory Rights Management non Azure Information Protection, cosa fare?</span><span class="sxs-lookup"><span data-stu-id="b17d3-160">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="b17d3-161"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="b17d3-161"></span></span>

<span data-ttu-id="b17d3-p110">È possibile continuare a utilizzare le regole del flusso di posta di crittografia dei messaggi di Office 365 con Active Directory Rights Management, ma non è possibile configurare o utilizzare le nuove funzionalità OME. Al contrario, è necessario eseguire la migrazione a Azure Information Protection. Per informazioni sulla migrazione e su cosa significa per la propria organizzazione, vedere [migrazione da ad RMS a Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span><span class="sxs-lookup"><span data-stu-id="b17d3-p110">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities. Instead, you need to migrate to Azure Information Protection. For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b17d3-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b17d3-165">Next steps</span></span>
<span data-ttu-id="b17d3-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="b17d3-166"></span></span>

<span data-ttu-id="b17d3-167">Dopo aver completato il programma di installazione di Azure Rights Management, se si desidera abilitare le nuove funzionalità OME, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span><span class="sxs-lookup"><span data-stu-id="b17d3-167">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="b17d3-168">Dopo aver configurato l'organizzazione per l'utilizzo delle nuove funzionalità OME, è possibile [definire le regole del flusso di posta per proteggere i messaggi di posta elettronica con le nuove funzionalità ome](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="b17d3-168">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b17d3-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b17d3-169">Related topics</span></span>
<span data-ttu-id="b17d3-170"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="b17d3-170"></span></span>

[<span data-ttu-id="b17d3-171">Crittografia in Office 365</span><span class="sxs-lookup"><span data-stu-id="b17d3-171">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="b17d3-172">Dettagli tecnici di riferimento sulla crittografia in Office 365</span><span class="sxs-lookup"><span data-stu-id="b17d3-172">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="b17d3-173">Che cos'è Azure Rights Management?</span><span class="sxs-lookup"><span data-stu-id="b17d3-173">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

