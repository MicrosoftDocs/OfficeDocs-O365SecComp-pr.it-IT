---
title: Aggiungere il marchio dell'organizzazione per i messaggi crittografati
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: "Gli amministratori di Exchange, è possibile applicare l'organizzazione personalizzazione ai messaggi di posta elettronica crittografati dell'organizzazione e il contenuto del portale di crittografia. "
ms.openlocfilehash: 2f34b5cea3155f587fd7787f1f69270d1373400b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530818"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Aggiungere il logo della propria organizzazione ai messaggi crittografati

Amministratore di Exchange Online o Exchange Online Protection, è possibile applicare l'azienda di personalizzazione per personalizzare l'aspetto dei messaggi di posta elettronica di Office 365 Message Encryption dell'organizzazione e il contenuto del portale di crittografia. Utilizzando i cmdlet Get-OMEConfiguration e Set-OMEConfiguration Windows PowerShell, è possibile personalizzare gli aspetti seguenti dell'esperienza di visualizzazione per i destinatari dei messaggi di posta elettronica crittografati:
  
- Testo introduttivo del messaggio di posta elettronica contenente il messaggio crittografato
    
- Testo della dichiarazione di non responsabilità del messaggio di posta elettronica contenente il messaggio crittografato
    
- Testo visualizzato nel portale OME
    
- Logo che viene visualizzato il messaggio di posta elettronica e portale OME
    
- Colore di sfondo nel messaggio di posta elettronica e portale OME
    
È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.
  
||
|:-----|
|In questo articolo fa parte di una serie di dimensioni maggiore di articoli su Office 365 Message Encryption. In questo articolo è destinato agli amministratori e ai professionisti IT. Se si è appena per informazioni su inviare né ricevere un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 messaggio crittografia dei](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||
   
**Per personalizzare l'aspetto dei OME portale e posta elettronica messaggi crittografati da OME con marchio dell'organizzazione**
  
1. Connessione a Exchange Online tramite Remote PowerShell, come descritto in [connessione a Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).
    
2. Utilizzare il cmdlet Set-OMEConfiguration come descritto in [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) oppure utilizzare la seguente tabella per istruzioni. 
    
**Opzioni di personalizzazione della crittografia**

|**Per personalizzare questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi**|
|:-----|:-----|
|Testo predefinito che accompagna i messaggi di posta elettronica crittografati. Il testo predefinito visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only."` <br/> |
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> formati di file supportati: .png, .jpg, .bmp o .tiff  <br/> Dimensione ottimale relativa al file del logo: inferiore a 40 KB  <br/> Dimensioni ottimali relative all'immagine del logo: 170x70 pixel  <br/> |
|Colore di sfondo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -BackgroundColor "#ffffff"` <br/> |
   
**Per rimuovere le personalizzazioni del marchio dai OME portale e posta elettronica messaggi crittografati da OME**
  
1. Connessione a Exchange Online tramite Remote PowerShell, come descritto in [connessione a Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Utilizzare il cmdlet Set-OMEConfiguration come descritto in [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). Per rimuovere l'organizzazione del marchio personalizzazioni da DisclaimerText, EmailText, e i valori PortalText, impostare il valore su una stringa vuota `""`. Per tutte le immagini di valori, ad esempio Logo, impostare il valore di `"$null"`.
    
**Opzioni di personalizzazione della crittografia**

**Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia**|**Utilizzare questi comandi**|
|:-----|:-----|
|Testo predefinito che accompagna i messaggi di posta elettronica crittografati  <br/> Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Esempio:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Back ripristino di esempio per impostazione predefinita:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|logo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Back ripristino di esempio per impostazione predefinita:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
|Colore di sfondo  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Back ripristino di esempio per impostazione predefinita:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null` <br/> |
   

