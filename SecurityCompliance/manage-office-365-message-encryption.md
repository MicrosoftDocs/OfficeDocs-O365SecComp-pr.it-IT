---
title: Gestire Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: Dopo aver configurato Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in vari modi. Ad esempio, è possibile configurare la possibilità di abilitare i codici Pass una tantum, visualizzare il pulsante Proteggi in Outlook sul Web e altro ancora. Le attività descritte in questo articolo illustrano come fare.
ms.openlocfilehash: 8b044898efb1ef86790773cd3f8e8061523b0ec0
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213756"
---
# <a name="manage-office-365-message-encryption"></a>Gestire Office 365 Message Encryption

Dopo aver configurato Office 365 Message Encryption (OME), è possibile personalizzare la configurazione della distribuzione in vari modi. Ad esempio, è possibile configurare la possibilità di abilitare i codici Pass una tantum, **** visualizzare il pulsante Proteggi in Outlook sul Web e altro ancora. Le attività descritte in questo articolo illustrano come fare.
  
||
|:-----|
|Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e professionisti IT. Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Gestione del fatto che i destinatari di Google, Yahoo e Microsoft account possano utilizzare questi account per accedere al portale di crittografia dei messaggi di Office 365

Per impostazione predefinita, quando si configurano le nuove funzionalità di crittografia dei messaggi di Office 365, gli utenti dell'organizzazione possono inviare messaggi ai destinatari esterni all'organizzazione di Office 365. Se il destinatario utilizza un *ID sociale* , ad esempio un account Google, un account Yahoo o un account Microsoft, il destinatario può accedere al portale ome utilizzando l'ID sociale. Se lo si desidera, è possibile scegliere di non consentire ai destinatari di utilizzare gli ID di social networking per accedere al portale OME.
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a>Per gestire se consentire o meno ai destinatari di utilizzare gli ID di social networking per accedere al portale OME
  
1. [Connettersi a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Eseguire il cmdlet Set-OMEConfiguration con il parametro SocialIdSignIn, come indicato di seguito:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   Ad esempio, per disabilitare gli ID di social networking:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Per abilitare gli ID di social networking:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a>Gestione dell'utilizzo di codici pass monouso per l'accesso al portale di crittografia dei messaggi di Office 365

Per impostazione predefinita, se il destinatario di un messaggio crittografato da OME non utilizza Outlook, indipendentemente dall'account utilizzato dal destinatario, il destinatario riceve un collegamento di visualizzazione Web con tempo limitato che consente di leggere il messaggio. Questo include un codice di passaggio una tantum. In qualità di amministratore, è possibile stabilire se è possibile utilizzare o meno codici pass di una tantum per accedere al portale OME.
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a>Per gestire se vengono generati o meno codici di passaggio una tantum per OME
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-OMEConfiguration con il parametro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Ad esempio, per disabilitare i codici pass monouso:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Per abilitare i codici di passaggio una tantum:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a>Gestione della visualizzazione del pulsante Proteggi in Outlook sul Web

Per impostazione predefinita, **** il pulsante Proteggi in Outlook sul Web non è abilitato quando si configura ome. In qualità di amministratore, è possibile decidere se visualizzare o meno questo pulsante per gli utenti finali.
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a>Per gestire se il pulsante Proteggi viene visualizzato in Outlook sul Web
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-IRMConfiguration con il parametro-SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Ad esempio, per disabilitare il **** pulsante Proteggi:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Per abilitare il **** pulsante Proteggi:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Abilitare la decrittografia sul posto del servizio dei messaggi di posta elettronica per gli utenti delle app di posta elettronica iOS

L'app di posta iOS non può decrittografare i messaggi protetti con la crittografia dei messaggi di Office 365. In qualità di amministratore di Office 365, è possibile applicare la decrittografia sul posto di servizio per i messaggi recapitati all'app di posta elettronica iOS. Quando si sceglie di eseguire questa operazione, il servizio invia una copia decrittografata del messaggio al dispositivo iOS. Il messaggio viene archiviato come decrittografato nel dispositivo client. Il messaggio conserva anche informazioni sui diritti di utilizzo anche se l'app di posta iOS non applica i diritti di utilizzo sul fianco del client all'utente. Questo significa che l'utente può copiare o stampare il messaggio anche se in origine non aveva i diritti per farlo. Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'inoltro del messaggio, il server non consentirà l'azione se l'utente non ha originariamente il diritto di utilizzo. Tuttavia, gli utenti finali possono aggirare non inoltrare la restrizione di utilizzo inoltrando il messaggio da un account diverso nell'app di posta iOS. indipendentemente dal fatto che sia stata configurata la decrittografia dei messaggi sul lato del servizio, gli allegati ai messaggi crittografati e protetti da diritti di posta elettronica non può essere visualizzato nell'app di posta elettronica iOS.
  
Se si sceglie di non consentire l'invio di messaggi decrittografati agli utenti delle app di posta elettronica iOS, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare il messaggio. Per impostazione predefinita, la decrittografia sul posto di servizio dei messaggi di posta elettronica non è abilitata.
  
Per ulteriori informazioni e per una panoramica dell'esperienza client, vedere [visualizzare i messaggi crittografati sul vostro iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Per gestire se gli utenti delle app di posta elettronica iOS possono visualizzare i messaggi protetti tramite la crittografia dei messaggi di Office 365
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-ActiveSyncOrganizations con il parametro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Ad esempio, per configurare il servizio per decrittografare i messaggi prima che vengano inviati a app non illuminate come l'app mail iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   In alternativa, per configurare il servizio per non inviare messaggi decrittografati a app non illuminate:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Abilitare la decrittografia sul fianco del servizio degli allegati di posta elettronica per i client di posta del browser Web

In genere, quando si utilizza la crittografia dei messaggi di Office 365, gli allegati vengono crittografati automaticamente. Come amministratore di Office 365, è possibile applicare la decrittografia sul posto di servizio per gli allegati di posta elettronica che gli utenti scaricano da un Web browser.
  
Quando si sceglie di eseguire questa operazione, il servizio invia una copia decrittografata del file al dispositivo. Il messaggio è ancora crittografato. L'allegato di posta elettronica conserva anche informazioni sui diritti di utilizzo anche se il browser non applica i diritti di utilizzo sul fianco del client all'utente. Questo significa che l'utente può copiare o stampare l'allegato di posta elettronica anche se in origine non aveva i diritti per farlo. Tuttavia, se l'utente tenta di eseguire un'azione che richiede il server di posta di Office 365, ad esempio l'inoltro dell'allegato, il server non consentirà l'azione se l'utente non ha originariamente il diritto di utilizzo.
  
Indipendentemente dal fatto che sia stata configurata la decrittografia sul posto del servizio degli allegati, tutti gli allegati ai messaggi crittografati e protetti da diritti non possono essere visualizzati nell'app di posta elettronica iOS.
  
Se si sceglie di non consentire gli allegati di posta elettronica decrittografati, ovvero l'impostazione predefinita, gli utenti riceveranno un messaggio che indica che non dispongono dei diritti per visualizzare l'allegato.
  
Per ulteriori informazioni sul modo in cui Office 365 implementa la crittografia per i messaggi di posta elettronica e gli allegati con l'opzione solo crittografia, vedere l' [opzione crittografia solo per i messaggi di posta elettronica.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Per gestire se gli allegati di posta elettronica vengono decrittografati sul download da un Web browser
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-IRMConfiguration con il parametro DecryptAttachmentFromPortal:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   Ad esempio, per configurare il servizio per decrittografare gli allegati di posta elettronica quando un utente li scarica da un Web browser:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   Per configurare il servizio per lasciare gli allegati di posta elettronica crittografati al momento del download:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizzazione dell'aspetto dei messaggi di posta elettronica e del portale OME

Per informazioni dettagliate su come personalizzare OME per la propria organizzazione, vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disabling-the-new-capabilities-for-ome"></a>Disabilitazione delle nuove funzionalità di OME

Si spera che non venga ad esso, ma se necessario, la disabilitazione delle nuove funzionalità per OME è molto semplice. Per prima cosa, è necessario rimuovere le regole del flusso di posta create che utilizzano le nuove funzionalità OME. Per informazioni sulla rimozione delle regole del flusso di posta, vedere [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Eseguire quindi i passaggi seguenti in PowerShell di Exchange Online.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Per disabilitare le nuove funzionalità di OME
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Se è stato abilitato **** il pulsante Proteggi in Outlook sul Web, disabilitarlo eseguendo il cmdlet Set-IRMConfiguration con il parametro SimplifiedClientAccessEnabled. In caso contrario, ignorare questo passaggio.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Disabilitare le nuove funzionalità di OME eseguendo il cmdlet Set-IRMConfiguration con il parametro AzureRMSLicensingEnabled impostato su false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
