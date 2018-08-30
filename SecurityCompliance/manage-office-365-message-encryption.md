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
# <a name="manage-office-365-message-encryption"></a>Gestire la crittografia dei messaggi di Office 365

Dopo la configurazione di Office 365 messaggio crittografia dei è terminata, è possibile personalizzare la configurazione della distribuzione in vari modi. Ad esempio, è possibile configurare se si desidera abilitare occasionale passcode, visualizzare il pulsante di **protezione** in Outlook sul web e altro ancora. In questo articolo viene descritta la modalità. 
  
||
|:-----|
|In questo articolo fa parte di una serie di dimensioni maggiore di articoli su Office 365 Message Encryption. In questo articolo è destinato ai professionisti IT e amministratori. Se si è appena per informazioni su inviare né ricevere un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 messaggio crittografia dei](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
   
## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Gestione se Google, Yahoo e Account Microsoft i destinatari possono utilizzare questi account per l'accesso al portale di Office 365 Message Encryption
<a name="PermitSocialID"> </a>

Per impostazione predefinita, quando si imposta le nuove funzionalità di Office 365 Message Encryption, gli utenti dell'organizzazione possono inviare messaggi per i destinatari sono esterni all'organizzazione Office 365. Se il destinatario utilizza un *ID di social networking* , ad esempio un account di Google, Yahoo account o account Microsoft, il destinatario può effettuare l'accesso al portale OME utilizzando l'ID del social networking. Se si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare gli ID di social networking per accedere al portale OME. 
  
 **Per gestire o meno consentire ai destinatari di utilizzare gli ID di social networking per accedere al portale OME**
  
1. [Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn come indicato di seguito:
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true |$false >
  ```

    Ad esempio, per disattivare gli ID di social networking:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
  ```

    Per abilitare gli ID di social networking:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
  ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a>Gestione dell'utilizzo dei codici unico passaggio per l'accesso al portale di Office 365 Message Encryption
<a name="GenerateOTPC"> </a>

Per impostazione predefinita, se il destinatario del messaggio crittografato per OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceve un collegamento di visualizzazione di durata limitata web che consente di leggere il messaggio. Includono un passcode occasionale. In qualità di amministratore, è possibile gestire unico passaggio codici possono essere utilizzati per accedere al portale OME o meno.
  
 **Per gestire o meno occasionale passcode vengono generate per OME**
  
1. [Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Eseguire il cmdlet Set-OMEConfiguration con il parametro OTPEnabled come indicato di seguito:
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true |$false >
  ```

    Ad esempio, per disattivare i codici unico passaggio:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
  ```

    Per attivare i codici unico passaggio:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
  ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a>La gestione della visualizzazione del pulsante Protect in Outlook sul web
<a name="DisplayProtectButton"> </a>

Per impostazione predefinita, il pulsante di **protezione** in Outlook sul web non è abilitato quando si imposta OME. In qualità di amministratore, è possibile gestire o meno visualizzare questo pulsante per gli utenti finali. 
  
 **Per gestire o meno Protect viene visualizzato il pulsante in Outlook sul web**
  
1. [Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Eseguire il cmdlet Set-IRMConfiguration con il parametro - SimplifiedClientAccessEnabled come indicato di seguito:
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true |$false >
  ```

    Ad esempio, per disattivare il pulsante **Protect** : 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

    Per abilitare il pulsante **Protect** : 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
  ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Abilitare la decrittografia lato del servizio di messaggi di posta elettronica per gli utenti di app di iOS posta
<a name="EnableServiceSideDecrypt"> </a>

App di posta elettronica iOS non possono decrittografare i messaggi protetti con crittografia dei messaggi di Office 365. Amministratore di Office 365, è possibile applicare la decrittografia lato del servizio per i messaggi inviati a app di posta elettronica iOS. Quando si sceglie di eseguire questa operazione, il servizio invia una copia del messaggio crittografata al dispositivo iOS. Il messaggio viene archiviato decrittografati del dispositivo client. Il messaggio mantiene anche informazioni sui diritti di utilizzo anche se l'app di posta elettronica iOS non è applicabile diritti di utilizzo sul lato client per utente. Ciò significa che l'utente può copiare o stampare il messaggio, anche se non è stato originariamente dispongono dei diritti per eseguire questa operazione. Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio inoltrare il messaggio, il server non consente l'azione se l'utente non è stato originariamente dispone del diritto di utilizzo non venga richiesto. Tuttavia, gli utenti finali possono risolvere non inoltrare limitazione dell'utilizzo per inoltrare il messaggio da un account diverso nelle app di posta elettronica iOS indipendentemente dall'impostazione di decrittografia lato del servizio di posta, tutti gli allegati crittografate e i diritti protetti da posta non è possibile visualizzare le app di posta elettronica iOS.
  
Se si sceglie di non consentire i messaggi decrittografati vengano inviate a iOS gli utenti di app di posta, gli utenti ricevono un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio. Per impostazione predefinita, non è abilitata sul lato servizio la decrittografia dei messaggi di posta elettronica.
  
Per ulteriori informazioni e per una visualizzazione dell'esperienza client, vedere la sezione "[visualizzare messaggi crittografati all'iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)" in [visualizzare messaggi crittografati all'iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
 **Per gestire gli utenti di app di posta iOS o meno possibile visualizzare i messaggi protetti da Office 365 Message Encryption**
  
1. [Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps come indicato di seguito:
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true |$false >
  ```

    Ad esempio, per configurare il servizio per decrittografare i messaggi prima che vengano inviati a App unenlightened come il iOS posta app:
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
  ```

    Ad esempio, per configurare il servizio non consente di inviare i messaggi decrittografati per le applicazioni unenlightened:
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
  ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Abilitare la decrittografia lato del servizio di allegati di posta elettronica per i client di posta elettronica web browser
<a name="EnableServiceSideDecrypt"> </a>

In genere, quando si utilizza la crittografia dei messaggi di Office 365, gli allegati vengono automaticamente crittografati. Amministratore di Office 365, è possibile applicare la decrittografia lato del servizio per gli allegati di posta elettronica che gli utenti il download da un web browser. 
  
Quando si sceglie di eseguire questa operazione, il servizio invia una copia del file decrittografata al dispositivo. Il messaggio è ancora crittografato. Allegato di posta elettronica mantiene anche informazioni sui diritti di utilizzo, anche se il browser non si applica diritti di utilizzo sul lato client per utente. Ciò significa che l'utente può copiare o stampare l'allegato di posta elettronica, anche se non è stato originariamente dispongono dei diritti per eseguire questa operazione. Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'allegato di inoltro il server non consente l'azione se l'utente non è stato originariamente dispone del diritto di utilizzo non venga richiesto.
  
Indipendentemente dal fatto se è impostata la decrittografia lato del servizio di allegati, degli allegati per crittografata e posta elettronica protetta diritti non può essere visualizzato in app di posta elettronica iOS.
  
Se si sceglie di non consentire gli allegati di posta elettronica crittografato, ovvero l'impostazione predefinita, gli utenti ricevono un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato. \* \* \* Inserisci immagine?
  
Per ulteriori informazioni su come viene implementata la crittografia dei messaggi di posta elettronica e allegati di posta elettronica con l'opzione solo crittografa Office 365, vedere [Crittografa sola opzione di messaggi di posta elettronica.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
 **Per gestire o meno gli allegati di posta elettronica vengano decrittografati al momento del download da un web browser**
  
1. [Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentFromPortal come indicato di seguito:
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal <$true |$false >
  ```

    Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando l'utente li scarica da un web browser:
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $true
  ```

    Per configurare il servizio per lasciare invariati gli allegati di posta elettronica crittografati durante il download:
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $false
  ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizzazione dell'aspetto dei messaggi di posta elettronica e il portale OME
<a name="CustomizeAppearance"> </a>

Per informazioni dettagliate su come personalizzare OME per l'organizzazione, vedere [aggiungere marchio dell'organizzazione per i messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disabling-the-new-capabilities-for-ome"></a>Disabilitazione delle nuove funzionalità per OME
<a name="CustomizeAppearance"> </a>

È una sorpresa che non proviene e specifiche, ma se è necessario, disabilitare le nuove funzionalità per OME è molto semplice. È necessario rimuovere qualsiasi flusso regole di posta che sono stati creati che utilizzano le nuove funzionalità OME. Per informazioni sulla rimozione di regole del flusso di posta elettronica, vedere [Gestisci regole di flusso di posta elettronica](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Quindi, eseguire la procedura seguente in Exchange Online PowerShell.
  
 **Per disabilitare le nuove funzionalità per OME**
  
1. [Connessione a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).
    
2. Se è abilitato il pulsante di protezione in Outlook sul web, disabilitarla eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled come indicato di seguito:
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

3. Eseguire il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled come indicato di seguito:
    
  ```
  Set-IRMConfiguration -AzureRMSLicensingEnabled $false
  ```


