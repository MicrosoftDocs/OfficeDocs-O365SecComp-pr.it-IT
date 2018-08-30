---
title: Gestire la crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: Dopo la configurazione di Office 365 messaggio crittografia dei è terminata, è possibile personalizzare la configurazione della distribuzione in vari modi. Ad esempio, è possibile configurare se si desidera abilitare occasionale passcode, visualizzare il pulsante di protezione in Outlook sul web e altro ancora. In questo articolo viene descritta la modalità.
ms.openlocfilehash: ddc86bdf0d0ce5480587862a4ed438b6c138987f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530538"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="a23b4-105">Gestire la crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="a23b4-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="a23b4-p102">Dopo la configurazione di Office 365 messaggio crittografia dei è terminata, è possibile personalizzare la configurazione della distribuzione in vari modi. Ad esempio, è possibile configurare se si desidera abilitare occasionale passcode, visualizzare il pulsante di **protezione** in Outlook sul web e altro ancora. In questo articolo viene descritta la modalità.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p102">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how.</span></span> 
  
||
|:-----|
|<span data-ttu-id="a23b4-p103">In questo articolo fa parte di una serie di dimensioni maggiore di articoli su Office 365 Message Encryption. In questo articolo è destinato ai professionisti IT e amministratori. Se si è appena per informazioni su inviare né ricevere un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 messaggio crittografia dei](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and IT Pros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
   
## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="a23b4-112">Gestione se Google, Yahoo e Account Microsoft i destinatari possono utilizzare questi account per l'accesso al portale di Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="a23b4-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>
<span data-ttu-id="a23b4-113"><a name="PermitSocialID"> </a></span><span class="sxs-lookup"><span data-stu-id="a23b4-113"></span></span>

<span data-ttu-id="a23b4-p104">Per impostazione predefinita, quando si imposta le nuove funzionalità di Office 365 Message Encryption, gli utenti dell'organizzazione possono inviare messaggi per i destinatari sono esterni all'organizzazione Office 365. Se il destinatario utilizza un *ID di social networking* , ad esempio un account di Google, Yahoo account o account Microsoft, il destinatario può effettuare l'accesso al portale OME utilizzando l'ID del social networking. Se si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare gli ID di social networking per accedere al portale OME.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p104">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a  *social ID*  such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span> 
  
 <span data-ttu-id="a23b4-117">**Per gestire o meno consentire ai destinatari di utilizzare gli ID di social networking per accedere al portale OME**</span><span class="sxs-lookup"><span data-stu-id="a23b4-117">**To manage whether or not to allow recipients to use social IDs to sign in to the OME portal**</span></span>
  
1. <span data-ttu-id="a23b4-118">[Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a23b4-118">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="a23b4-119">Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a23b4-119">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true |$false >
  ```

    <span data-ttu-id="a23b4-120">Ad esempio, per disattivare gli ID di social networking:</span><span class="sxs-lookup"><span data-stu-id="a23b4-120">For example, to disable social IDs:</span></span>
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
  ```

    <span data-ttu-id="a23b4-121">Per abilitare gli ID di social networking:</span><span class="sxs-lookup"><span data-stu-id="a23b4-121">To enable social IDs:</span></span>
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
  ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="a23b4-122">Gestione dell'utilizzo dei codici unico passaggio per l'accesso al portale di Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="a23b4-122">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>
<span data-ttu-id="a23b4-123"><a name="GenerateOTPC"> </a></span><span class="sxs-lookup"><span data-stu-id="a23b4-123"></span></span>

<span data-ttu-id="a23b4-p105">Per impostazione predefinita, se il destinatario del messaggio crittografato per OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceve un collegamento di visualizzazione di durata limitata web che consente di leggere il messaggio. Includono un passcode occasionale. In qualità di amministratore, è possibile gestire unico passaggio codici possono essere utilizzati per accedere al portale OME o meno.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p105">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
 <span data-ttu-id="a23b4-127">**Per gestire o meno occasionale passcode vengono generate per OME**</span><span class="sxs-lookup"><span data-stu-id="a23b4-127">**To manage whether or not one-time pass codes are generated for OME**</span></span>
  
1. <span data-ttu-id="a23b4-128">[Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a23b4-128">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="a23b4-129">Eseguire il cmdlet Set-OMEConfiguration con il parametro OTPEnabled come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a23b4-129">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter as follows:</span></span>
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true |$false >
  ```

    <span data-ttu-id="a23b4-130">Ad esempio, per disattivare i codici unico passaggio:</span><span class="sxs-lookup"><span data-stu-id="a23b4-130">For example, to disable one-time pass codes:</span></span>
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
  ```

    <span data-ttu-id="a23b4-131">Per attivare i codici unico passaggio:</span><span class="sxs-lookup"><span data-stu-id="a23b4-131">To enable one-time pass codes:</span></span>
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
  ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="a23b4-132">La gestione della visualizzazione del pulsante Protect in Outlook sul web</span><span class="sxs-lookup"><span data-stu-id="a23b4-132">Managing the display of the Protect button in Outlook on the web</span></span>
<span data-ttu-id="a23b4-133"><a name="DisplayProtectButton"> </a></span><span class="sxs-lookup"><span data-stu-id="a23b4-133"></span></span>

<span data-ttu-id="a23b4-p106">Per impostazione predefinita, il pulsante di **protezione** in Outlook sul web non è abilitato quando si imposta OME. In qualità di amministratore, è possibile gestire o meno visualizzare questo pulsante per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p106">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users.</span></span> 
  
 <span data-ttu-id="a23b4-136">**Per gestire o meno Protect viene visualizzato il pulsante in Outlook sul web**</span><span class="sxs-lookup"><span data-stu-id="a23b4-136">**To manage whether or not the Protect button appears in Outlook on the web**</span></span>
  
1. <span data-ttu-id="a23b4-137">[Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a23b4-137">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="a23b4-138">Eseguire il cmdlet Set-IRMConfiguration con il parametro - SimplifiedClientAccessEnabled come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a23b4-138">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter as follows:</span></span>
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true |$false >
  ```

    <span data-ttu-id="a23b4-139">Ad esempio, per disattivare il pulsante **Protect** :</span><span class="sxs-lookup"><span data-stu-id="a23b4-139">For example, to disable the **Protect** button:</span></span> 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

    <span data-ttu-id="a23b4-140">Per abilitare il pulsante **Protect** :</span><span class="sxs-lookup"><span data-stu-id="a23b4-140">To enable the **Protect** button:</span></span> 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
  ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="a23b4-141">Abilitare la decrittografia lato del servizio di messaggi di posta elettronica per gli utenti di app di iOS posta</span><span class="sxs-lookup"><span data-stu-id="a23b4-141">Enable service-side decryption of email messages for iOS mail app users</span></span>
<span data-ttu-id="a23b4-142"><a name="EnableServiceSideDecrypt"> </a></span><span class="sxs-lookup"><span data-stu-id="a23b4-142"></span></span>

<span data-ttu-id="a23b4-p107">App di posta elettronica iOS non possono decrittografare i messaggi protetti con crittografia dei messaggi di Office 365. Amministratore di Office 365, è possibile applicare la decrittografia lato del servizio per i messaggi inviati a app di posta elettronica iOS. Quando si sceglie di eseguire questa operazione, il servizio invia una copia del messaggio crittografata al dispositivo iOS. Il messaggio viene archiviato decrittografati del dispositivo client. Il messaggio mantiene anche informazioni sui diritti di utilizzo anche se l'app di posta elettronica iOS non è applicabile diritti di utilizzo sul lato client per utente. Ciò significa che l'utente può copiare o stampare il messaggio, anche se non è stato originariamente dispongono dei diritti per eseguire questa operazione. Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio inoltrare il messaggio, il server non consente l'azione se l'utente non è stato originariamente dispone del diritto di utilizzo non venga richiesto. Tuttavia, gli utenti finali possono risolvere non inoltrare limitazione dell'utilizzo per inoltrare il messaggio da un account diverso nelle app di posta elettronica iOS indipendentemente dall'impostazione di decrittografia lato del servizio di posta, tutti gli allegati crittografate e i diritti protetti da posta non è possibile visualizzare le app di posta elettronica iOS.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p107">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="a23b4-p108">Se si sceglie di non consentire i messaggi decrittografati vengano inviate a iOS gli utenti di app di posta, gli utenti ricevono un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio. Per impostazione predefinita, non è abilitata sul lato servizio la decrittografia dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p108">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="a23b4-154">Per ulteriori informazioni e per una visualizzazione dell'esperienza client, vedere la sezione "[visualizzare messaggi crittografati all'iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)" in [visualizzare messaggi crittografati all'iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="a23b4-154">For more information, and for a view of the client experience, see the section, "[View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)" in [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
 <span data-ttu-id="a23b4-155">**Per gestire gli utenti di app di posta iOS o meno possibile visualizzare i messaggi protetti da Office 365 Message Encryption**</span><span class="sxs-lookup"><span data-stu-id="a23b4-155">**To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption**</span></span>
  
1. <span data-ttu-id="a23b4-156">[Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a23b4-156">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="a23b4-157">Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a23b4-157">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter as follows:</span></span>
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true |$false >
  ```

    <span data-ttu-id="a23b4-158">Ad esempio, per configurare il servizio per decrittografare i messaggi prima che vengano inviati a App unenlightened come il iOS posta app:</span><span class="sxs-lookup"><span data-stu-id="a23b4-158">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
  ```

    <span data-ttu-id="a23b4-159">Ad esempio, per configurare il servizio non consente di inviare i messaggi decrittografati per le applicazioni unenlightened:</span><span class="sxs-lookup"><span data-stu-id="a23b4-159">For example, to configure the service not to send decrypted messages to unenlightened apps:</span></span>
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
  ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="a23b4-160">Abilitare la decrittografia lato del servizio di allegati di posta elettronica per i client di posta elettronica web browser</span><span class="sxs-lookup"><span data-stu-id="a23b4-160">Enable service-side decryption of email attachments for web browser mail clients</span></span>
<span data-ttu-id="a23b4-161"><a name="EnableServiceSideDecrypt"> </a></span><span class="sxs-lookup"><span data-stu-id="a23b4-161"></span></span>

<span data-ttu-id="a23b4-p109">In genere, quando si utilizza la crittografia dei messaggi di Office 365, gli allegati vengono automaticamente crittografati. Amministratore di Office 365, è possibile applicare la decrittografia lato del servizio per gli allegati di posta elettronica che gli utenti il download da un web browser.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p109">Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span> 
  
<span data-ttu-id="a23b4-p110">Quando si sceglie di eseguire questa operazione, il servizio invia una copia del file decrittografata al dispositivo. Il messaggio è ancora crittografato. Allegato di posta elettronica mantiene anche informazioni sui diritti di utilizzo, anche se il browser non si applica diritti di utilizzo sul lato client per utente. Ciò significa che l'utente può copiare o stampare l'allegato di posta elettronica, anche se non è stato originariamente dispongono dei diritti per eseguire questa operazione. Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'allegato di inoltro il server non consente l'azione se l'utente non è stato originariamente dispone del diritto di utilizzo non venga richiesto.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p110">When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="a23b4-169">Indipendentemente dal fatto se è impostata la decrittografia lato del servizio di allegati, degli allegati per crittografata e posta elettronica protetta diritti non può essere visualizzato in app di posta elettronica iOS.</span><span class="sxs-lookup"><span data-stu-id="a23b4-169">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="a23b4-p111">Se si sceglie di non consentire gli allegati di posta elettronica crittografato, ovvero l'impostazione predefinita, gli utenti ricevono un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato. \* \* \* Inserisci immagine?</span><span class="sxs-lookup"><span data-stu-id="a23b4-p111">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment. \*\*\* insert picture?</span></span>
  
<span data-ttu-id="a23b4-172">Per ulteriori informazioni su come viene implementata la crittografia dei messaggi di posta elettronica e allegati di posta elettronica con l'opzione solo crittografa Office 365, vedere [Crittografa sola opzione di messaggi di posta elettronica.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="a23b4-172">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
 <span data-ttu-id="a23b4-173">**Per gestire o meno gli allegati di posta elettronica vengano decrittografati al momento del download da un web browser**</span><span class="sxs-lookup"><span data-stu-id="a23b4-173">**To manage whether or not email attachments are decrypted on download from a web browser**</span></span>
  
1. <span data-ttu-id="a23b4-174">[Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a23b4-174">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="a23b4-175">Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentFromPortal come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a23b4-175">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter as follows:</span></span>
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal <$true |$false >
  ```

    <span data-ttu-id="a23b4-176">Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando l'utente li scarica da un web browser:</span><span class="sxs-lookup"><span data-stu-id="a23b4-176">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $true
  ```

    <span data-ttu-id="a23b4-177">Per configurare il servizio per lasciare invariati gli allegati di posta elettronica crittografati durante il download:</span><span class="sxs-lookup"><span data-stu-id="a23b4-177">To configure the service to leave encrypted email attachments as they are upon download:</span></span>
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $false
  ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="a23b4-178">Personalizzazione dell'aspetto dei messaggi di posta elettronica e il portale OME</span><span class="sxs-lookup"><span data-stu-id="a23b4-178">Customizing the appearance of email messages and the OME portal</span></span>
<span data-ttu-id="a23b4-179"><a name="CustomizeAppearance"> </a></span><span class="sxs-lookup"><span data-stu-id="a23b4-179"></span></span>

<span data-ttu-id="a23b4-180">Per informazioni dettagliate su come personalizzare OME per l'organizzazione, vedere [aggiungere marchio dell'organizzazione per i messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a23b4-180">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="a23b4-181">Disabilitazione delle nuove funzionalità per OME</span><span class="sxs-lookup"><span data-stu-id="a23b4-181">Disabling the new capabilities for OME</span></span>
<span data-ttu-id="a23b4-182"><a name="CustomizeAppearance"> </a></span><span class="sxs-lookup"><span data-stu-id="a23b4-182"></span></span>

<span data-ttu-id="a23b4-p112">È una sorpresa che non proviene e specifiche, ma se è necessario, disabilitare le nuove funzionalità per OME è molto semplice. È necessario rimuovere qualsiasi flusso regole di posta che sono stati creati che utilizzano le nuove funzionalità OME. Per informazioni sulla rimozione di regole del flusso di posta elettronica, vedere [Gestisci regole di flusso di posta elettronica](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Quindi, eseguire la procedura seguente in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a23b4-p112">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.</span></span>
  
 <span data-ttu-id="a23b4-187">**Per disabilitare le nuove funzionalità per OME**</span><span class="sxs-lookup"><span data-stu-id="a23b4-187">**To disable the new capabilities for OME**</span></span>
  
1. <span data-ttu-id="a23b4-188">[Connessione a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a23b4-188">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="a23b4-189">Se è abilitato il pulsante di protezione in Outlook sul web, disabilitarla eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a23b4-189">If you enabled the Protect button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter as follows:</span></span>
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

3. <span data-ttu-id="a23b4-190">Eseguire il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a23b4-190">Run the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter as follows:</span></span>
    
  ```
  Set-IRMConfiguration -AzureRMSLicensingEnabled $false
  ```


