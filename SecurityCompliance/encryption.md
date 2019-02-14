---
title: Crittografia in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
description: Con Office 365, il contenuto viene crittografato statici e in transito, utilizzando la crittografia, i protocolli e le tecnologie disponibili più sicuro. Panoramica della crittografia in Office 365.
ms.openlocfilehash: 5f64d6e758818d410f54370adee549f565d4f042
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995107"
---
# <a name="encryption-in-office-365"></a>Crittografia in Office 365

La crittografia è un aspetto importante delle strategie di protezione protezione e le informazioni dei file. In questo articolo viene fornita una panoramica di crittografia utilizzato per tutte le versioni di Office 365 e ottenere assistenza per attività di crittografia, dall'impostazione di crittografia per l'organizzazione ai documenti di Office protetti da password.
  
- Se si sta cercando informazioni sui certificati e le tecnologie come TLS, vedere [informazioni di riferimento tecniche sulla crittografia in Office 365](technical-reference-details-about-encryption.md).
    
- Se sta cercando informazioni su come configurare o la crittografia per l'organizzazione, vedere [configurazione di crittografia in Office 365 Enterprise](set-up-encryption.md).
    
## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Che cos'è la crittografia e come funziona in Office 365?

Un livello elevato, la crittografia è il processo di codifica dei dati (noto come testo non crittografato) in testo crittografato che non può essere utilizzato dal computer o utenti fino a quando il testo crittografato viene decrittografato e. Decrittografia richiede una chiave di crittografia contenenti solo gli utenti autorizzati. Crittografia garantisce che solo i destinatari autorizzati possono decrittografare il contenuto, ad esempio file e messaggi di posta elettronica.
  
Crittografia di per sé non impedisce contenuto, ad esempio i file, messaggi di posta elettronica, le voci di calendario e così via, di recupero in malintenzionati. Crittografia fa parte di una strategia di protezione più grande per l'organizzazione. Utilizzando la crittografia, si possono contribuire ad assicurare che solo agli utenti che devono essere in grado di utilizzare i dati crittografati siano in grado di.
  
Più livelli di crittografia in locale possono essere contemporaneamente. Ad esempio, è possibile crittografare i messaggi di posta elettronica, nonché i canali di comunicazione attraverso il quale passa la posta elettronica. Con Office 365, i dati vengono crittografati statici e in transito, utilizzando diversi protocolli di crittografia avanzata e le tecnologie che includono Transport Layer Security/Secure Sockets Layer (TLS/SSL), Internet Protocol Security (IPSec) e la crittografia avanzata Standard (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Crittografia per i dati statici e dati in transito

 Esempi **di dati statici** i file che sono stati caricati in una raccolta di SharePoint, Project Online dei dati, i documenti che sono stati caricati in Skype per riunioni aziendali, messaggi di posta elettronica e allegati che vengono memorizzati in cartelle in Office 365 cassette postali e i file caricati OneDrive for Business. 
  
 **Esempi di dati in transito** includono i messaggi di posta elettronica presenti in fase di invio o conversazioni che sono in corso in una riunione online. In Office 365, dati sono in corso ogni volta che un dispositivo dell'utente comunica con un server di Office 365 o quando un server di Office 365 comunica con un altro server. 
  
Con Office 365, è possibile disporre di più livelli e i tipi di crittografia che interagiscono per proteggere i dati. Nella tabella seguente sono riportati alcuni esempi, con collegamenti a ulteriori informazioni.
  
|**Tipi di contenuto**|**Tecnologie di crittografia**|**Risorse per ulteriori informazioni**|
|:-----|:-----|:-----|
|File in un dispositivo. Può trattarsi di messaggi di posta elettronica salvati in una cartella, documenti di Office salvati in un computer, tablet o telefono o dati salvati nel cloud Microsoft.  <br/> |BitLocker nei data center Microsoft. BitLocker può essere utilizzato anche nei computer client, ad esempio computer Windows e Tablet  <br/> Distribuita chiave Manager (DKM) nei data center Microsoft  <br/> Chiave cliente per Office 365  <br/> |[Windows IT Center: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro protezione di Microsoft: la crittografia](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [Protezione cloud controlla series: la crittografia dei dati statici](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Come Exchange Online protegge le informazioni riservate della posta elettronica](exchange-online-secures-email-secrets.md) <br/> [Controllare i dati in Office 365 con Customer Key](controlling-your-data-using-customer-key.md) <br/> |
|File in transito tra gli utenti. Può trattarsi di documenti di Office o elementi di elenchi SharePoint condivisi tra gli utenti.  <br/> |TLS per i file in transito  <br/> |[Crittografia dei dati in OneDrive for Business e SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype per le aziende Online: sicurezza e archiviazione](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|In transito tra i destinatari di posta elettronica. Sono incluse le e-mail ospitata da Exchange Online.  <br/> |Crittografia dei messaggi di Office 365 con Azure Rights Management, S/MIME e TLS per la posta elettronica in transito  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Crittografia della posta elettronica in Office 365](email-encryption.md) <br/> [Come viene utilizzato TLS per proteggere il traffico della posta elettronica in Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
   
## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Se è possibile necessari maggiore controllo sulle crittografia per soddisfare i requisiti di sicurezza e conformità?

Oltre alle soluzioni gestite di Microsoft di crittografia del volume, la crittografia dei file e la crittografia delle cassette postali in Office 365, opzioni gestite clienti è utilizzabile per soddisfare ulteriori requisiti sicurezza e conformità. Tali soluzioni utilizzano Azure Rights Management (Azure RMS) insieme a Office 365.
  
Le risorse seguenti per ulteriori informazioni, vedere:
  
- [Che cos'è Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
    
- [Attivare Rights Management nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)
    
- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)
    
## <a name="how-do-i"></a>Procedura

|**Per eseguire questa operazione**|**Vedere le risorse**|
|:-----|:-----|
|Configurare la crittografia per l'organizzazione  <br/> |[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md) <br/> |
|Visualizzare informazioni dettagliate sui certificati, tecnologie e famiglie di prodotti crittografia TLS in Office 365  <br/> |[Dettagli tecnici sulla crittografia in Office 365](technical-reference-details-about-encryption.md) <br/> |
|Lavorare con i messaggi crittografati su un dispositivo mobile  <br/> |[Visualizzare messaggi crittografati nel dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Visualizzare messaggi crittografati all'iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Crittografa un documento con la protezione con password  <br/><br/>  Attualmente, la protezione con password non è supportata in Office Online. Utilizzare le versioni del desktop di Word, Excel e PowerPoint per la protezione con password.           |[Protezione di aggiunta o la rimozione di un documento, una cartella di lavoro o presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) (Scegliere una sezione **protezione Aggiungi** e quindi vedere **Crittografa con Password** )  <br/> |
|Rimuovere la crittografia da un documento  <br/> |[Protezione di aggiunta o la rimozione di un documento, una cartella di lavoro o presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) (Scegliere una sezione di **rimuovere la protezione** e quindi vedere **rimuovere la crittografia delle password** )  <br/> |
   
## <a name="related-topics"></a>Argomenti correlati

[Pianificare la funzionalità di Office 365 informazioni sulla sicurezza e protezione](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[Sicurezza e conformità in Office 365 per aziende - della Guida di amministrazione](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

