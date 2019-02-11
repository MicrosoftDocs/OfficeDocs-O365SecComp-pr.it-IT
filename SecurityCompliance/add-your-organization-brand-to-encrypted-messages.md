---
title: Aggiungere il marchio dell'organizzazione per i messaggi crittografati
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: Gli amministratori di Exchange, è possibile applicare l'organizzazione personalizzazione ai messaggi di posta elettronica crittografati dell'organizzazione e il contenuto del portale di crittografia.
ms.openlocfilehash: 4b22b72a8b77c2978a7cf25166978759119c272c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696220"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Aggiungere il logo della propria organizzazione ai messaggi crittografati

Amministratore di Exchange Online o Exchange Online Protection, è possibile applicare l'azienda di personalizzazione per personalizzare l'aspetto dei messaggi di posta elettronica di Office 365 Message Encryption dell'organizzazione e il contenuto del portale di crittografia. Utilizzando i cmdlet Get-OMEConfiguration e Set-OMEConfiguration Windows PowerShell, è possibile personalizzare gli aspetti seguenti dell'esperienza di visualizzazione per i destinatari dei messaggi di posta elettronica crittografati:
  
- Testo introduttivo del messaggio di posta elettronica contenente il messaggio crittografato
- Testo della dichiarazione di non responsabilità del messaggio di posta elettronica contenente il messaggio crittografato
- Testo visualizzato nel portale OME
- Logo che viene visualizzato il messaggio di posta elettronica e portale OME
- Colore di sfondo nel messaggio di posta elettronica e portale OME

È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.

Se si desidera un maggiore controllo, è possibile creare più modelli di messaggi di posta elettronica crittografati proveniente dall'organizzazione. Utilizzo di questi modelli, è possibile controllare solo l'aspetto dei messaggi di posta elettronica, ma anche controllare le parti dell'esperienza dell'utente finale. Ad esempio, è possibile specificare o meno i destinatari di posta che hanno questo modello applicato e che utilizzano Microsoft Accounts, Yahoo e Google possono utilizzare questi account per l'accesso al portale di Office 365 Message Encryption. È possibile utilizzare modelli per soddisfare diverse modalità di utilizzo, ad esempio:

- Modelli per ogni reparto, ad esempio Finance, vendite e così via.
- Modelli per diversi prodotti
- Modelli per i paesi o aree geografiche diverse

Dopo aver creato i modelli, è possibile applicare tali a messaggi di posta elettronica crittografati tramite le regole di flusso della posta di Exchange. Tutti i messaggi che marchio mediante l'utilizzo di questi modelli possono essere revocati.
  
||
|:-----|
|In questo articolo fa parte di una serie di dimensioni maggiore di articoli su Office 365 Message Encryption. In questo articolo è destinato agli amministratori e ai professionisti IT. Se si è appena per informazioni su inviare né ricevere un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 messaggio crittografia dei](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||

## <a name="create-branding-templates"></a>Creare modelli di personalizzazione

Per creare modelli di personalizzazione per l'organizzazione di Windows PowerShell con il cmdlet New-OMEConfiguration. Dopo aver creato il modello, utilizzando il cmdlet Set-OMEConfiguration si definiscono le parti del modello. È possibile creare più modelli.

![Web part personalizzabili posta elettronica](media/ome-template-breakout.png)
  
1. Utilizzo di un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet New-OMEConfiguration per creare un nuovo modello.
     ```powershell
     New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
     ```
     Ad esempio:
     ```powershell
     New-OMEConfiguration -Identity <Branding template 1>
     ```
3. Definire le personalizzazioni per il modello che appena definita utilizzando il cmdlet Set-OMEConfiguration come descritto in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) o utilizzare la seguente tabella per istruzioni.

|**Per personalizzare questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi**|
|:-----|:-----|
|Colore di sfondo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> |
|Logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> formati di file supportati: .png, .jpg, .bmp o .tiff  <br/> Dimensione ottimale relativa al file del logo: inferiore a 40 KB  <br/> Dimensioni ottimali relative all'immagine del logo: 170x70 pixel  <br/> |
|Testo accanto a indirizzo di posta elettronica e nome del mittente| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Testo visualizzato sul pulsante "Lettura dei messaggi"| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Testo visualizzato sopra sotto il pulsante "Lettura dei messaggi"| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|Per abilitare o disabilitare l'autenticazione con un passcode occasionale per questo modello personalizzato| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **Esempi:** <br/>Per abilitare occasionale passcode per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Per disabilitare occasionale passcode per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Per abilitare o disabilitare l'autenticazione con le identità Microsoft, Google o Yahoo per questo modello personalizzato| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **Esempi:** <br/>Per abilitare gli ID di social networking per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Per disattivare gli ID di social networking per questo modello personalizzato <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>Per rimuovere le personalizzazioni del marchio dai OME portale e posta elettronica messaggi crittografati da OME
  
1. [Connettersi a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Utilizzare il cmdlet Set-OMEConfiguration come descritto in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration). Per rimuovere l'organizzazione del marchio personalizzazioni da DisclaimerText, EmailText, e i valori PortalText, impostare il valore su una stringa vuota `""`. Per tutte le immagini di valori, ad esempio Logo, impostare il valore di `"$null"`.

**Opzioni di personalizzazione della crittografia**

**Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi**|
|:-----|:-----|
|Testo predefinito che accompagna i messaggi di posta elettronica crittografati  <br/> Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Back ripristino di esempio per impostazione predefinita:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|Logo| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Back ripristino di esempio per impostazione predefinita:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|Colore di sfondo| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Back ripristino di esempio per impostazione predefinita:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>Creare una regola di flusso della posta di Exchange che si applica personalizzato personalizzazione ai messaggi di posta elettronica crittografati

Dopo aver creato un modello di personalizzazione, è possibile creare regole del flusso di posta di Exchange per applicare tale personalizzazione in base a determinate condizioni. Tale regola verrà applicata la personalizzazione personalizzati negli scenari seguenti:

- Se il messaggio di posta elettronica è stato crittografato manualmente per l'utente finale dal client Outlook o OWA
- Se il messaggio di posta elettronica è stato crittografato automaticamente da un flusso di posta di Exchange regola o criteri di prevenzione della perdita di dati di Office 365

Per informazioni su come creare una regola di flusso della posta di Exchange che si applica la crittografia, vedere [definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. In un web browser utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere le sezioni di **amministrazione** .

3. In interfaccia di amministrazione di Office 365, scegliere **Interfacce di amministrazione** \> **Exchange**.

4. In EAC, andare a **flusso di posta** \> **regole** e selezionare **New** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Crea una nuova regola**. Per ulteriori informazioni sull'utilizzo di EAC, vedere [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. In **nome**digitare un nome per la regola, ad esempio Branding per reparto vendite.

6. In **Applica questa regola se** selezionare una condizione, selezionare la condizione che **il mittente si trova all'interno dell'organizzazione** , nonché altre condizioni desiderato dall'elenco di condizioni disponibili. Ad esempio, è possibile applicare un determinato modello di personalizzazione per:

     - Crittografati tutti i messaggi di posta elettronica inviati dai membri del reparto finance
     - Crittografati i messaggi di posta elettronica inviati con una determinata parola chiave, ad esempio "Esterno" o "Partner"
     - Crittografati i messaggi di posta elettronica inviati a un dominio specifico

7. **Eseguire le operazioni seguenti**, selezionare **Modifica la sicurezza del messaggio** > **applicare una personalizzazione ai messaggi OME**. Successivamente, dall'elenco a discesa, selezionare un modello di personalizzazione da quelli che è stato creato.
8. (Facoltativo) Se si desidera che la regola di flusso di posta si applicano anche crittografia oltre personalizzato branding da **effettuare le seguenti operazioni**, selezionare **Modifica la sicurezza del messaggio** e quindi scegliere **Applica crittografia messaggi Office 365 e protezione dei diritti**. Selezionare un modello RMS dall'elenco, scegliere **Salva**e quindi fare clic su **OK**.
  
     L'elenco dei modelli include tutti i modelli predefiniti e le opzioni e i modelli personalizzati creati per utilizzano Office 365. Se l'elenco è vuoto, verificare che sono state impostate la crittografia dei messaggi di Office 365 con le nuove funzionalità come descritto in [Set up le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [configurazione e gestione dei modelli per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni sull'opzione **Non inoltrare** , vedere [opzione non inoltrare per messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Per informazioni sull'opzione **crittografare solo** , vedere [opzione crittografare solo per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

     È possibile scegliere **Aggiungi azione** se si desidera specificare un'altra azione.
