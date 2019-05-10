---
title: Gestire Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Dopo aver configurato Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in diversi modi. Ad esempio, è possibile configurare la possibilità di abilitare i codici Pass una tantum, visualizzare il pulsante Proteggi in Outlook sul Web e altro ancora. Le attività descritte in questo articolo illustrano come fare.
ms.openlocfilehash: 1afaaea3cd744878630598acd3f02dc7dc70e9cb
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834925"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="73058-105">Gestire Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="73058-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="73058-106">Dopo aver configurato Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="73058-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="73058-107">Ad esempio, è possibile configurare la possibilità di abilitare i codici Pass una tantum, \*\*\*\* visualizzare il pulsante Proteggi in Outlook sul Web e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="73058-107">For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more.</span></span> <span data-ttu-id="73058-108">Le attività descritte in questo articolo illustrano come fare.</span><span class="sxs-lookup"><span data-stu-id="73058-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="73058-109">Gestire se i destinatari di Google, Yahoo e Microsoft account possono utilizzare questi account per accedere al portale di crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="73058-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="73058-110">Quando si configurano le nuove funzionalità di crittografia dei messaggi di Office 365, gli utenti dell'organizzazione possono inviare messaggi ai destinatari esterni all'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="73058-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="73058-111">Se il destinatario utilizza un *ID sociale* , ad esempio un account Google, un account Yahoo o un account Microsoft, il destinatario può accedere al portale ome con un ID sociale.</span><span class="sxs-lookup"><span data-stu-id="73058-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="73058-112">Se lo si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare gli ID di social networking per accedere al portale OME.</span><span class="sxs-lookup"><span data-stu-id="73058-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="73058-113">Per gestire se i destinatari possono utilizzare gli ID di social networking per accedere al portale OME</span><span class="sxs-lookup"><span data-stu-id="73058-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="73058-114">[Connettersi a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="73058-114">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="73058-115">Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="73058-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="73058-116">Ad esempio, per disabilitare gli ID di social networking:</span><span class="sxs-lookup"><span data-stu-id="73058-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="73058-117">Per abilitare gli ID di social networking:</span><span class="sxs-lookup"><span data-stu-id="73058-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="73058-118">Gestire l'utilizzo di codici pass monouso per il portale di crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="73058-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="73058-119">Se il destinatario di un messaggio crittografato da OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceverà un collegamento di visualizzazione Web con tempo limitato che consente di leggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="73058-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="73058-120">Questo collegamento include un codice Pass One-Time.</span><span class="sxs-lookup"><span data-stu-id="73058-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="73058-121">In qualità di amministratore, è possibile decidere se i destinatari possono utilizzare codici di passaggio una tantum per accedere al portale OME.</span><span class="sxs-lookup"><span data-stu-id="73058-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="73058-122">Per gestire se la OME genera codici di Pass One-Time</span><span class="sxs-lookup"><span data-stu-id="73058-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="73058-123">Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73058-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="73058-124">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="73058-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="73058-125">Eseguire il cmdlet Set-OMEConfiguration con il parametro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="73058-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="73058-126">Ad esempio, per disabilitare i codici pass monouso:</span><span class="sxs-lookup"><span data-stu-id="73058-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="73058-127">Per abilitare i codici di passaggio una tantum:</span><span class="sxs-lookup"><span data-stu-id="73058-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="73058-128">Gestire la visualizzazione del pulsante Proteggi in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="73058-128">Manage the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="73058-129">Il \*\*\*\* pulsante Proteggi in Outlook sul Web è disabilitato quando si configura ome.</span><span class="sxs-lookup"><span data-stu-id="73058-129">The **Protect** button in Outlook on the web is disabled when you set up OME.</span></span> <span data-ttu-id="73058-130">In qualità di amministratore, è possibile decidere se visualizzare questo pulsante per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="73058-130">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="73058-131">Per gestire se il pulsante Proteggi viene visualizzato in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="73058-131">To manage whether the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="73058-132">Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73058-132">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="73058-133">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="73058-133">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="73058-134">Eseguire il cmdlet Set-IRMConfiguration con il parametro-SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="73058-134">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="73058-135">Ad esempio, per disabilitare il \*\*\*\* pulsante Proteggi:</span><span class="sxs-lookup"><span data-stu-id="73058-135">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="73058-136">Per abilitare il \*\*\*\* pulsante Proteggi:</span><span class="sxs-lookup"><span data-stu-id="73058-136">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="73058-137">Abilitare la decrittografia sul posto del servizio dei messaggi di posta elettronica per gli utenti delle app di posta elettronica iOS</span><span class="sxs-lookup"><span data-stu-id="73058-137">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="73058-138">L'app di posta iOS non può decrittografare i messaggi protetti con la crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="73058-138">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="73058-139">In qualità di amministratore di Office 365, è possibile applicare la decrittografia sul posto di servizio per i messaggi recapitati all'app di posta elettronica iOS.</span><span class="sxs-lookup"><span data-stu-id="73058-139">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="73058-140">Quando si sceglie di utilizzare la decrittografia sul posto del servizio, il servizio invia una copia decrittografata del messaggio al dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="73058-140">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="73058-141">Il dispositivo client archivia una copia decrittografata del messaggio.</span><span class="sxs-lookup"><span data-stu-id="73058-141">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="73058-142">Il messaggio conserva anche informazioni sui diritti di utilizzo anche se l'app di posta iOS non applica i diritti di utilizzo sul fianco del client all'utente.</span><span class="sxs-lookup"><span data-stu-id="73058-142">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="73058-143">L'utente può copiare o stampare il messaggio anche se in origine non dispone dei diritti necessari.</span><span class="sxs-lookup"><span data-stu-id="73058-143">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="73058-144">Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'inoltro del messaggio, il server non consentirà l'azione se l'utente non ha originariamente il diritto di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="73058-144">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="73058-145">Tuttavia, gli utenti finali possono aggirare la restrizione di utilizzo "non inoltrare" inoltrando il messaggio da un account diverso all'interno dell'app di posta iOS.</span><span class="sxs-lookup"><span data-stu-id="73058-145">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="73058-146">Indipendentemente dal fatto che sia stata configurata la decrittografia sul posto del servizio, gli allegati ai messaggi crittografati e i diritti protetti non possano essere visualizzati nell'app mail iOS.</span><span class="sxs-lookup"><span data-stu-id="73058-146">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="73058-147">Se si sceglie di non consentire l'invio di messaggi decrittografati agli utenti delle app di posta elettronica iOS, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="73058-147">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="73058-148">Per impostazione predefinita, la decrittografia sul posto di servizio dei messaggi di posta elettronica non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="73058-148">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="73058-149">Per ulteriori informazioni e per una panoramica dell'esperienza client, vedere [visualizzare i messaggi crittografati sul vostro iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="73058-149">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="73058-150">Per gestire se gli utenti delle app di posta elettronica iOS possono visualizzare i messaggi protetti dalla crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="73058-150">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="73058-151">Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73058-151">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="73058-152">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="73058-152">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="73058-153">Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="73058-153">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="73058-154">Ad esempio, per configurare il servizio per decrittografare i messaggi prima che vengano inviati a app non illuminate come app mail iOS:</span><span class="sxs-lookup"><span data-stu-id="73058-154">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="73058-155">In alternativa, per configurare il servizio per non inviare messaggi decrittografati a app non illuminate:</span><span class="sxs-lookup"><span data-stu-id="73058-155">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="73058-156">Abilitare la decrittografia sul fianco del servizio degli allegati di posta elettronica per i client di posta del browser Web</span><span class="sxs-lookup"><span data-stu-id="73058-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="73058-157">In genere, quando si utilizza la crittografia dei messaggi di Office 365, gli allegati vengono crittografati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="73058-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="73058-158">Come amministratore di Office 365, è possibile applicare la decrittografia sul posto di servizio per gli allegati di posta elettronica che gli utenti scaricano da un Web browser.</span><span class="sxs-lookup"><span data-stu-id="73058-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="73058-159">Quando si utilizza la decrittografia sul posto del servizio, il servizio invia una copia decrittografata del file al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="73058-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="73058-160">Il messaggio è ancora crittografato.</span><span class="sxs-lookup"><span data-stu-id="73058-160">The message is still encrypted.</span></span> <span data-ttu-id="73058-161">L'allegato di posta elettronica conserva anche informazioni sui diritti di utilizzo anche se il browser non applica i diritti di utilizzo sul fianco del client all'utente.</span><span class="sxs-lookup"><span data-stu-id="73058-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="73058-162">L'utente può copiare o stampare l'allegato di posta elettronica anche se in origine non dispone dei diritti necessari.</span><span class="sxs-lookup"><span data-stu-id="73058-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="73058-163">Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'inoltro dell'allegato, il server non consentirà l'azione se l'utente non ha originariamente il diritto di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="73058-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="73058-164">Indipendentemente dal fatto che sia stata configurata la decrittografia sul posto del servizio degli allegati, gli utenti non possono visualizzare gli allegati ai messaggi crittografati e protetti per la posta nell'app di posta elettronica iOS.</span><span class="sxs-lookup"><span data-stu-id="73058-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="73058-165">Se si sceglie di non consentire gli allegati di posta elettronica decrittografati, ovvero l'impostazione predefinita, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato.</span><span class="sxs-lookup"><span data-stu-id="73058-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="73058-166">Per ulteriori informazioni sul modo in cui Office 365 implementa la crittografia per i messaggi di posta elettronica e gli allegati con l'opzione solo crittografia, vedere l' [opzione crittografia solo per i messaggi di posta elettronica.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="73058-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="73058-167">Per gestire se gli allegati di posta elettronica vengono decrittografati per il download da un Web browser</span><span class="sxs-lookup"><span data-stu-id="73058-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="73058-168">Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73058-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="73058-169">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="73058-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="73058-170">Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentFromPortal:</span><span class="sxs-lookup"><span data-stu-id="73058-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="73058-171">Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando un utente li scarica da un Web browser:</span><span class="sxs-lookup"><span data-stu-id="73058-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="73058-172">Per configurare il servizio per lasciare gli allegati di posta elettronica crittografati al momento del download:</span><span class="sxs-lookup"><span data-stu-id="73058-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a><span data-ttu-id="73058-173">Assicurarsi che tutti i destinatari esterni utilizzino il portale OME per leggere la posta crittografata, solo la crittografia dei messaggi avanzata di Office 365</span><span class="sxs-lookup"><span data-stu-id="73058-173">Ensure all external recipients use the OME Portal to read encrypted mail — Office 365 Advanced Message Encryption only</span></span>

<span data-ttu-id="73058-174">Se si dispone della crittografia dei messaggi avanzata di Office 365, è possibile utilizzare modelli di personalizzazione personalizzati per imporre ai destinatari la ricezione di un messaggio di posta elettronica wrapper per la lettura di messaggi crittografati nel portale OME anziché l'utilizzo di Outlook o Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="73058-174">If you have Office 365 Advanced Message Encryption, you can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="73058-175">Potrebbe essere necessario eseguire questa operazione se si desidera utilizzare un maggiore controllo su come i destinatari utilizzano la posta ricevuta.</span><span class="sxs-lookup"><span data-stu-id="73058-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="73058-176">Ad esempio, se i destinatari esterni visualizzano la posta elettronica nel portale Web, è possibile impostare una data di scadenza per il messaggio di posta elettronica ed è possibile revocare il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="73058-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="73058-177">Queste funzionalità sono supportate solo tramite il portale OME.</span><span class="sxs-lookup"><span data-stu-id="73058-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="73058-178">Per creare le regole del flusso di posta, è possibile utilizzare l'opzione Crittografa e l'opzione non inoltrare.</span><span class="sxs-lookup"><span data-stu-id="73058-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a><span data-ttu-id="73058-179">Creare un modello personalizzato per imporre a tutti i destinatari esterni di utilizzare il portale OME e per la posta elettronica crittografata come revocabile e scadere in 7 giorni</span><span class="sxs-lookup"><span data-stu-id="73058-179">Create a custom template to force all external recipients to use the OME Portal and for encrypted email to be revocable and expire in 7 days</span></span>

1. <span data-ttu-id="73058-180">Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365 e avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73058-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="73058-181">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="73058-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="73058-182">Eseguire il cmdlet New-OMEConfiguration:</span><span class="sxs-lookup"><span data-stu-id="73058-182">Run the New-OMEConfiguration cmdlet:</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   <span data-ttu-id="73058-183">dove `template name` è il nome che si desidera utilizzare per il modello di branding personalizzato per la crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="73058-183">where `template name` is the name you want to use for the Office 365 Message Encryption custom branding template.</span></span> <span data-ttu-id="73058-184">For example,</span><span class="sxs-lookup"><span data-stu-id="73058-184">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. <span data-ttu-id="73058-185">Eseguire il cmdlet New-TransportRule:</span><span class="sxs-lookup"><span data-stu-id="73058-185">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="73058-186">dove:</span><span class="sxs-lookup"><span data-stu-id="73058-186">where:</span></span>

   - <span data-ttu-id="73058-187">`mail flow rule name`è il nome che si desidera utilizzare per la nuova regola del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="73058-187">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="73058-188">`option name`è `Encrypt` o `Do Not Forward`.</span><span class="sxs-lookup"><span data-stu-id="73058-188">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="73058-189">`template name`è il nome assegnato al modello personalizzato per la personalizzazione, ad esempio `One week expiration`.</span><span class="sxs-lookup"><span data-stu-id="73058-189">`template name` is the name you gave the custom branding template, for example `One week expiration`.</span></span>

   <span data-ttu-id="73058-190">Per crittografare tutti i messaggi di posta elettronica esterni con il modello "scadenza una settimana" e applicare l'opzione solo crittografia:</span><span class="sxs-lookup"><span data-stu-id="73058-190">To encrypt all external email with the "One week expiration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   <span data-ttu-id="73058-191">Per crittografare tutti i messaggi di posta elettronica esterni con il modello "scadenza una settimana" e applicare l'opzione non inoltrare:</span><span class="sxs-lookup"><span data-stu-id="73058-191">To encrypt all external email with the "One week expiration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="73058-192">Personalizzare l'aspetto dei messaggi di posta elettronica e del portale OME</span><span class="sxs-lookup"><span data-stu-id="73058-192">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="73058-193">Per informazioni dettagliate su come personalizzare OME per la propria organizzazione, vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="73058-193">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="73058-194">Disabilitare le nuove funzionalità di OME</span><span class="sxs-lookup"><span data-stu-id="73058-194">Disable the new capabilities for OME</span></span>

<span data-ttu-id="73058-195">Si spera che non venga ad esso, ma se necessario, la disabilitazione delle nuove funzionalità per OME è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="73058-195">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="73058-196">Per prima cosa, è necessario rimuovere le regole del flusso di posta create che utilizzano le nuove funzionalità OME.</span><span class="sxs-lookup"><span data-stu-id="73058-196">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="73058-197">Per informazioni sulla rimozione delle regole del flusso di posta, vedere [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="73058-197">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="73058-198">Eseguire quindi i passaggi seguenti in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73058-198">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="73058-199">Per disabilitare le nuove funzionalità di OME</span><span class="sxs-lookup"><span data-stu-id="73058-199">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="73058-200">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="73058-200">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="73058-201">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="73058-201">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="73058-202">Se è stato abilitato \*\*\*\* il pulsante Proteggi in Outlook sul Web, disabilitarlo eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="73058-202">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="73058-203">In caso contrario, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="73058-203">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="73058-204">Disabilitare le nuove funzionalità di OME eseguendo il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled impostato su false:</span><span class="sxs-lookup"><span data-stu-id="73058-204">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
