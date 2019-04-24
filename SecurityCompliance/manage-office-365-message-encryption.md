---
title: Gestire Office 365 Message Encryption
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- M365-security-compliance
description: Dopo aver configurato Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in vari modi. Ad esempio, è possibile configurare la possibilità di abilitare i codici Pass una tantum, visualizzare il pulsante Proteggi in Outlook sul Web e altro ancora. Le attività descritte in questo articolo illustrano come fare.
ms.openlocfilehash: 7b5297ae42d3efa071408540863c6ff7dbdee407
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259814"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="70677-105">Gestire Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="70677-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="70677-106">Dopo aver configurato Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in vari modi.</span><span class="sxs-lookup"><span data-stu-id="70677-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways.</span></span> <span data-ttu-id="70677-107">Ad esempio, è possibile configurare la possibilità di abilitare i codici Pass una tantum, \*\*\*\* visualizzare il pulsante Proteggi in Outlook sul Web e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="70677-107">For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more.</span></span> <span data-ttu-id="70677-108">Le attività descritte in questo articolo illustrano come fare.</span><span class="sxs-lookup"><span data-stu-id="70677-108">The tasks in this article describe how.</span></span>
  
||
|:-----|
|<span data-ttu-id="70677-109">Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="70677-109">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="70677-110">Questo articolo è destinato agli amministratori e professionisti IT.</span><span class="sxs-lookup"><span data-stu-id="70677-110">This article is intended for administrators and ITPros.</span></span> <span data-ttu-id="70677-111">Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="70677-111">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="70677-112">Gestione del fatto che i destinatari di Google, Yahoo e Microsoft account possano utilizzare questi account per accedere al portale di crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="70677-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="70677-113">Per impostazione predefinita, quando si configurano le nuove funzionalità di crittografia dei messaggi di Office 365, gli utenti dell'organizzazione possono inviare messaggi ai destinatari esterni all'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="70677-113">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="70677-114">Se il destinatario utilizza un *ID sociale* , ad esempio un account Google, un account Yahoo o un account Microsoft, il destinatario può accedere al portale ome utilizzando l'ID sociale.</span><span class="sxs-lookup"><span data-stu-id="70677-114">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID.</span></span> <span data-ttu-id="70677-115">Se lo si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare gli ID di social networking per accedere al portale OME.</span><span class="sxs-lookup"><span data-stu-id="70677-115">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="70677-116">Per gestire se consentire o meno ai destinatari di utilizzare gli ID di social networking per accedere al portale OME</span><span class="sxs-lookup"><span data-stu-id="70677-116">To manage whether or not to allow recipients to use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="70677-117">[Connettersi a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="70677-117">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="70677-118">Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="70677-118">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   <span data-ttu-id="70677-119">Ad esempio, per disabilitare gli ID di social networking:</span><span class="sxs-lookup"><span data-stu-id="70677-119">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="70677-120">Per abilitare gli ID di social networking:</span><span class="sxs-lookup"><span data-stu-id="70677-120">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="70677-121">Gestione dell'utilizzo di codici pass monouso per l'accesso al portale di crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="70677-121">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="70677-122">Per impostazione predefinita, se il destinatario di un messaggio crittografato da OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceve un collegamento di visualizzazione Web con tempo limitato che consente di leggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="70677-122">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="70677-123">Questo include un codice di passaggio una tantum.</span><span class="sxs-lookup"><span data-stu-id="70677-123">This includes a one-time pass code.</span></span> <span data-ttu-id="70677-124">In qualità di amministratore, è possibile stabilire se è possibile utilizzare o meno codici pass di una tantum per accedere al portale OME.</span><span class="sxs-lookup"><span data-stu-id="70677-124">As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a><span data-ttu-id="70677-125">Per gestire se vengono generati o meno codici di passaggio una tantum per OME</span><span class="sxs-lookup"><span data-stu-id="70677-125">To manage whether or not one-time pass codes are generated for OME</span></span>
  
1. <span data-ttu-id="70677-126">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70677-126">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70677-127">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70677-127">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70677-128">Eseguire il cmdlet Set-OMEConfiguration con il parametro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="70677-128">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="70677-129">Ad esempio, per disabilitare i codici pass monouso:</span><span class="sxs-lookup"><span data-stu-id="70677-129">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="70677-130">Per abilitare i codici di passaggio una tantum:</span><span class="sxs-lookup"><span data-stu-id="70677-130">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="70677-131">Gestione della visualizzazione del pulsante Proteggi in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="70677-131">Managing the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="70677-132">Per impostazione predefinita, \*\*\*\* il pulsante Proteggi in Outlook sul Web non è abilitato quando si configura ome.</span><span class="sxs-lookup"><span data-stu-id="70677-132">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME.</span></span> <span data-ttu-id="70677-133">In qualità di amministratore, è possibile decidere se visualizzare o meno questo pulsante per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="70677-133">As an administrator, you can manage whether or not to display this button to end users.</span></span>
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="70677-134">Per gestire se il pulsante Proteggi viene visualizzato in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="70677-134">To manage whether or not the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="70677-135">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70677-135">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70677-136">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70677-136">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70677-137">Eseguire il cmdlet Set-IRMConfiguration con il parametro-SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="70677-137">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="70677-138">Ad esempio, per disabilitare il \*\*\*\* pulsante Proteggi:</span><span class="sxs-lookup"><span data-stu-id="70677-138">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="70677-139">Per abilitare il \*\*\*\* pulsante Proteggi:</span><span class="sxs-lookup"><span data-stu-id="70677-139">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="70677-140">Abilitare la decrittografia sul posto del servizio dei messaggi di posta elettronica per gli utenti delle app di posta elettronica iOS</span><span class="sxs-lookup"><span data-stu-id="70677-140">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="70677-141">L'app di posta iOS non può decrittografare i messaggi protetti con la crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="70677-141">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="70677-142">In qualità di amministratore di Office 365, è possibile applicare la decrittografia sul posto di servizio per i messaggi recapitati all'app di posta elettronica iOS.</span><span class="sxs-lookup"><span data-stu-id="70677-142">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="70677-143">Quando si sceglie di eseguire questa operazione, il servizio invia una copia decrittografata del messaggio al dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="70677-143">When you choose to do this, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="70677-144">Il messaggio viene archiviato come decrittografato nel dispositivo client.</span><span class="sxs-lookup"><span data-stu-id="70677-144">The message is stored decrypted on the client device.</span></span> <span data-ttu-id="70677-145">Il messaggio conserva anche informazioni sui diritti di utilizzo anche se l'app di posta iOS non applica i diritti di utilizzo sul fianco del client all'utente.</span><span class="sxs-lookup"><span data-stu-id="70677-145">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="70677-146">Questo significa che l'utente può copiare o stampare il messaggio anche se in origine non aveva i diritti per farlo.</span><span class="sxs-lookup"><span data-stu-id="70677-146">This means that the user can copy or print the message even if they did not originally have the rights to do so.</span></span> <span data-ttu-id="70677-147">Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'inoltro del messaggio, il server non consentirà l'azione se l'utente non ha originariamente il diritto di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="70677-147">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so.</span></span> <span data-ttu-id="70677-148">Tuttavia, gli utenti finali possono aggirare non inoltrare la restrizione di utilizzo inoltrando il messaggio da un account diverso nell'app di posta elettronica iOS.</span><span class="sxs-lookup"><span data-stu-id="70677-148">However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app.</span></span> <span data-ttu-id="70677-149">Indipendentemente dal fatto che sia stata configurata la decrittografia sul posto del servizio della posta, gli allegati ai messaggi crittografati e protetti da diritti non possono essere visualizzati nell'app mail iOS.</span><span class="sxs-lookup"><span data-stu-id="70677-149">Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="70677-150">Se si sceglie di non consentire l'invio di messaggi decrittografati agli utenti delle app di posta elettronica iOS, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="70677-150">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="70677-151">Per impostazione predefinita, la decrittografia sul posto di servizio dei messaggi di posta elettronica non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="70677-151">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="70677-152">Per ulteriori informazioni e per una panoramica dell'esperienza client, vedere [visualizzare i messaggi crittografati sul vostro iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="70677-152">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="70677-153">Per gestire se gli utenti delle app di posta elettronica iOS possono visualizzare i messaggi protetti tramite la crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="70677-153">To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="70677-154">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70677-154">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70677-155">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70677-155">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70677-156">Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="70677-156">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="70677-157">Ad esempio, per configurare il servizio per decrittografare i messaggi prima che vengano inviati a app non illuminate come l'app mail iOS:</span><span class="sxs-lookup"><span data-stu-id="70677-157">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="70677-158">In alternativa, per configurare il servizio per non inviare messaggi decrittografati a app non illuminate:</span><span class="sxs-lookup"><span data-stu-id="70677-158">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="70677-159">Abilitare la decrittografia sul fianco del servizio degli allegati di posta elettronica per i client di posta del browser Web</span><span class="sxs-lookup"><span data-stu-id="70677-159">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="70677-160">In genere, quando si utilizza la crittografia dei messaggi di Office 365, gli allegati vengono crittografati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="70677-160">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="70677-161">Come amministratore di Office 365, è possibile applicare la decrittografia sul posto di servizio per gli allegati di posta elettronica che gli utenti scaricano da un Web browser.</span><span class="sxs-lookup"><span data-stu-id="70677-161">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="70677-162">Quando si sceglie di eseguire questa operazione, il servizio invia una copia decrittografata del file al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="70677-162">When you choose to do this, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="70677-163">Il messaggio è ancora crittografato.</span><span class="sxs-lookup"><span data-stu-id="70677-163">The message is still encrypted.</span></span> <span data-ttu-id="70677-164">L'allegato di posta elettronica conserva anche informazioni sui diritti di utilizzo anche se il browser non applica i diritti di utilizzo sul fianco del client all'utente.</span><span class="sxs-lookup"><span data-stu-id="70677-164">The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user.</span></span> <span data-ttu-id="70677-165">Questo significa che l'utente può copiare o stampare l'allegato di posta elettronica anche se in origine non aveva i diritti per farlo.</span><span class="sxs-lookup"><span data-stu-id="70677-165">This means that the user can copy or print the email attachment even if they did not originally have the rights to do so.</span></span> <span data-ttu-id="70677-166">Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'inoltro dell'allegato, il server non consentirà l'azione se l'utente non ha originariamente il diritto di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="70677-166">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="70677-167">Indipendentemente dal fatto che sia stata configurata la decrittografia sul posto del servizio degli allegati, tutti gli allegati ai messaggi crittografati e protetti da diritti non possono essere visualizzati nell'app di posta elettronica iOS.</span><span class="sxs-lookup"><span data-stu-id="70677-167">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="70677-168">Se si sceglie di non consentire gli allegati di posta elettronica decrittografati, ovvero l'impostazione predefinita, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato.</span><span class="sxs-lookup"><span data-stu-id="70677-168">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="70677-169">Per ulteriori informazioni sul modo in cui Office 365 implementa la crittografia per i messaggi di posta elettronica e gli allegati con l'opzione solo crittografia, vedere l' [opzione crittografia solo per i messaggi di posta elettronica.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="70677-169">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="70677-170">Per gestire se gli allegati di posta elettronica vengono decrittografati sul download da un Web browser</span><span class="sxs-lookup"><span data-stu-id="70677-170">To manage whether or not email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="70677-171">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70677-171">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70677-172">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70677-172">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70677-173">Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentFromPortal:</span><span class="sxs-lookup"><span data-stu-id="70677-173">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="70677-174">Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando un utente li scarica da un Web browser:</span><span class="sxs-lookup"><span data-stu-id="70677-174">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="70677-175">Per configurare il servizio per lasciare gli allegati di posta elettronica crittografati al momento del download:</span><span class="sxs-lookup"><span data-stu-id="70677-175">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="70677-176">Personalizzazione dell'aspetto dei messaggi di posta elettronica e del portale OME</span><span class="sxs-lookup"><span data-stu-id="70677-176">Customizing the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="70677-177">Per informazioni dettagliate su come personalizzare OME per la propria organizzazione, vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="70677-177">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="70677-178">Disabilitazione delle nuove funzionalità di OME</span><span class="sxs-lookup"><span data-stu-id="70677-178">Disabling the new capabilities for OME</span></span>

<span data-ttu-id="70677-179">Si spera che non venga ad esso, ma se necessario, la disabilitazione delle nuove funzionalità per OME è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="70677-179">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="70677-180">Per prima cosa, è necessario rimuovere le regole del flusso di posta create che utilizzano le nuove funzionalità OME.</span><span class="sxs-lookup"><span data-stu-id="70677-180">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="70677-181">Per informazioni sulla rimozione delle regole del flusso di posta, vedere [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="70677-181">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="70677-182">Eseguire quindi i passaggi seguenti in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70677-182">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="70677-183">Per disabilitare le nuove funzionalità di OME</span><span class="sxs-lookup"><span data-stu-id="70677-183">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="70677-184">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70677-184">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70677-185">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70677-185">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70677-186">Se è stato abilitato \*\*\*\* il pulsante Proteggi in Outlook sul Web, disabilitarlo eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="70677-186">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="70677-187">In caso contrario, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="70677-187">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="70677-188">Disabilitare le nuove funzionalità di OME eseguendo il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled impostato su false:</span><span class="sxs-lookup"><span data-stu-id="70677-188">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
