---
title: Configurare la crittografia in Office 365 Enterprise
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Con Office 365, alcune funzionalità di crittografia vengono attivati per impostazione predefinita. altre funzionalità può essere configurato per soddisfare determinati requisiti legali o conformità.
ms.openlocfilehash: 80deced80283ac36d82ac15cee9af6d390c4749a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530549"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurare la crittografia in Office 365 Enterprise

La crittografia è possibile proteggere il contenuto da letti da utenti non autorizzati. Poiché [la crittografia in Office 365](encryption.md) possono essere eseguite utilizzando diversi metodi e le tecnologie, non vi è una singola posizione da cui attivare o configurare la crittografia. In questo articolo vengono fornite informazioni sui diversi modi, è possibile impostare o configurare la crittografia come parte di una strategia di protezione informazioni. 
  
> [!TIP]
> Se sta cercando dettagli più tecnici sulla crittografia, vedere [informazioni di riferimento tecniche sulla crittografia in Office 365](technical-reference-details-about-encryption.md). 
  
Con Office 365, sono disponibili per impostazione predefinita diverse funzionalità di crittografia. Funzionalità aggiuntive crittografia può essere configurata per soddisfare determinati requisiti legali o conformità. Nella tabella seguente vengono descritti diversi metodi di crittografia per diversi scenari.
  
|**Scenario**|**Metodi di crittografia**|
|:-----|:-----|
|I file vengono salvati nei computer Windows  <br/> |La crittografia a livello di computer può essere eseguita utilizzando BitLocker nei dispositivi Windows. Come un amministratore dell'organizzazione o per professionisti IT, è possibile impostare utilizzando Microsoft Deployment Toolkit (MDT). Vedere [impostare MDT per BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).<br/> |
|I file vengono salvati nei dispositivi mobili  <br/> |Alcuni tipi di dispositivi mobili crittografare i file che vengono salvati in tali dispositivi per impostazione predefinita. Le [funzionalità di gestione incorporati di dispositivo Mobile per Office 365](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0), è possibile impostare criteri che consente di stabilire se consentire o meno i dispositivi mobili per accedere ai dati in Office 365. Ad esempio, è possibile impostare un criterio che consente solo i dispositivi che crittografa il contenuto per accedere ai dati di Office 365. Vedere [creazione e la distribuzione di criteri di protezione dispositivo](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).<br/> Per maggiore controllo su dispositivi mobili come interagire con Office 365, è possibile aggiungere [Microsoft Intune](https://aka.ms/qzln04). Vedere [scelta tra MDM per Office 365 e Microsoft Intune](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22).<br/> |
|È necessario controllare le chiavi di crittografia utilizzati per crittografare i dati di data center di Microsoft  <br/> | Amministratore di Office 365, è possibile controllare le chiavi di crittografia della propria organizzazione e quindi configurare Office 365 per utilizzarli per crittografare i dati statici nei centri dati di Microsoft.  <br/> [Controllare i dati in Office 365 tramite la Chiave cliente](controlling-your-data-using-customer-key.md) <br/> [Chiave cliente per domande frequenti su Office 365](service-encryption-with-customer-key-faq.md) <br/> |
|Gli utenti stanno comunicando tramite posta elettronica (Exchange Online)  <br/> | Amministratore di Exchange Online, sono disponibili diverse opzioni per la configurazione di crittografia di posta elettronica. Tali strumenti comprendono:<br/>  Per consentire agli utenti di inviare messaggi crittografati all'interno o all'esterno dell'organizzazione, utilizzare [la crittografia dei messaggi di Office 365 (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS)  <br/>  Utilizzo di [S/MIME per la crittografia e firma dei messaggi](https://aka.ms/c6dozg) per crittografare e firmare digitalmente i messaggi di posta elettronica  <br/>  Per [impostare i connettori per il flusso di posta elettronica protetta con un'altra organizzazione](https://aka.ms/hs809p) utilizza TLS <br/>  Vedere [crittografia di posta elettronica in Office 365](https://aka.ms/hic3f7).  <br/> |
|I file sono accessibili dal team siti o raccolte documenti (OneDrive for Business o SharePoint Online)  <br/> |Quando gli utenti utilizzano file salvati in OneDrive per Business o SharePoint Online, vengono utilizzate connessioni TLS. Ciò è incorporata in Office 365 automaticamente. Vedere [crittografia dei dati in OneDrive for Business e SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).<br/> |
|File condivisi in riunioni in linea e le conversazioni di messaggistica immediata (Skype Business online)  <br/> |Quando gli utenti utilizzano file mediante Skype Business online, TLS è utilizzato per la connessione. Ciò è incorporata in Office 365 automaticamente. Vedere [Security and Archiving (Skype for Business in linea)](https://aka.ms/nuq4ws).<br/> |
   
## <a name="additional-information"></a>Informazioni aggiuntive

Per ulteriori informazioni sulle soluzioni di protezione dei file che includono le opzioni di crittografia, vedere [Soluzioni di protezione dei File in Office 365](https://www.microsoft.com/en-us/download/details.aspx?id=55523).
  

