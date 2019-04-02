---
title: Crittografia in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Con Office 365, il contenuto viene crittografato a riposo e in transito, utilizzando la crittografia, i protocolli e le tecnologie più forti disponibili. Ottenere una panoramica della crittografia in Office 365.
ms.openlocfilehash: 7a73d3d3b24e28f8795ec93ac05dbc383b525906
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026327"
---
# <a name="encryption-in-office-365"></a>Crittografia in Office 365

La crittografia è una parte importante delle strategie di protezione dei file e di protezione delle informazioni. Leggere questo articolo per ottenere una panoramica della crittografia utilizzata per tutte le versioni di Office 365 e ottenere assistenza per le attività di crittografia, dalla configurazione della crittografia per l'organizzazione ai documenti di Office per la protezione delle password.
  
- Se si cercano informazioni su certificati e tecnologie come TLS, vedere [Technical Reference details about Encryption in Office 365](technical-reference-details-about-encryption.md).

- Se si cercano informazioni su come configurare o impostare la crittografia per l'organizzazione, vedere Configurare la [crittografia in Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Che cos'è la crittografia e come funziona in Office 365?

A livello elevato, la crittografia è il processo di codifica dei dati (denominati con testo non crittografato) in testo crittografato che non può essere utilizzato da persone o computer, a meno che il testo crittografato non venga decrittografato. La deCrittografia richiede una chiave di crittografia che dispone solo degli utenti autorizzati. La crittografia consente di garantire che solo i destinatari autorizzati possano decrittografare il contenuto, ad esempio i messaggi di posta elettronica e i file.
  
La crittografia da solo non impedisce che il contenuto, ad esempio i file, i messaggi di posta elettronica, le voci di calendario e così via, entri nelle mani sbagliate. La crittografia è parte di una strategia di protezione delle informazioni più ampia per la propria organizzazione. Utilizzando la crittografia, è possibile garantire che solo gli utenti che devono essere in grado di utilizzare i dati crittografati siano in grado di farlo.
  
È possibile disporre di più livelli di crittografia sul posto contemporaneamente. Ad esempio, è possibile crittografare i messaggi di posta elettronica e anche i canali di comunicazione tramite i quali il flusso di posta elettronica scorre. Con Office 365, i dati vengono crittografati a riposo e in transito, utilizzando diversi protocolli di crittografia avanzata e tecnologie che includono Transport Layer Security/Secure Sockets Layer (TLS/SSL), IPSec (Internet Protocol Security) e Advanced Encryption Standard (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Crittografia dei dati a riposo e dati in transito

 **Esempi di dati a riposo** sono i file caricati in una raccolta di SharePoint, i dati di Project online, i documenti che sono stati caricati in una riunione di Skype for business, i messaggi di posta elettronica e gli allegati archiviati nelle cartelle di Office 365 cassetta postale e file caricati in OneDrive for business. 
  
 Tra gli **esempi di dati in transito** sono inclusi i messaggi di posta elettronica in fase di recapito o le conversazioni che si svolgono in una riunione online. In Office 365, i dati sono in transito ogni volta che il dispositivo di un utente comunica con un server di Office 365 o quando un server Office 365 comunica con un altro server. 
  
Con Office 365, è possibile disporre di più livelli e tipi di crittografia che lavorano insieme per proteggere i dati. Nella tabella seguente sono inclusi alcuni esempi, con collegamenti a ulteriori informazioni.
  
|**Tipi di contenuto**|**Tecnologie di crittografia**|**Risorse per ulteriori informazioni**|
|:-----|:-----|:-----|
|File in un dispositivo. Questo può includere i messaggi di posta elettronica salvati in una cartella, i documenti di Office salvati su un computer, una tavoletta o un telefono o i dati salvati nel cloud Microsoft.  <br/> |BitLocker nei datacenter Microsoft. BitLocker può essere utilizzato anche nei computer client, ad esempio Windows e Tablet  <br/> Distributed Key Manager (DKM) nei datacenter Microsoft  <br/> Chiave cliente per Office 365  <br/> |[Centro IT di Windows: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro protezione Microsoft: crittografia](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [Serie di controlli di sicurezza cloud: crittografia dei dati a riposo](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Come Exchange Online protegge le informazioni riservate della posta elettronica](exchange-online-secures-email-secrets.md) <br/> [Controllare i dati in Office 365 con Customer Key](controlling-your-data-using-customer-key.md) <br/> |
|File in transito tra gli utenti. Questo può includere documenti di Office o elementi di elenchi di SharePoint condivisi tra gli utenti.  <br/> |TLS per i file in transito  <br/> |[Crittografia dei dati in OneDrive for Business e SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for business online: sicurezza e archiviazione](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|Messaggi di posta elettronica in transito tra i destinatari. Sono inclusi i messaggi di posta elettronica ospitati da Exchange Online.  <br/> |Crittografia dei messaggi di Office 365 con Azure Rights Management, S/MIME e TLS per la posta elettronica in transito  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Crittografia della posta elettronica in Office 365](email-encryption.md) <br/> [Come viene utilizzato TLS per proteggere il traffico della posta elettronica in Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Che cosa succede se è necessario un maggiore controllo sulla crittografia per soddisfare I requisiti di sicurezza e conformità?

Oltre alle soluzioni gestite da Microsoft per la crittografia dei volumi, la crittografia di file e la crittografia delle cassette postali in Office 365, è possibile utilizzare le opzioni gestite dal cliente per soddisfare i requisiti di sicurezza e conformità più severi. Tali soluzioni utilizzano Azure Rights Management (Azure RMS) insieme a Office 365.
  
Per ulteriori informazioni, vedere le risorse seguenti:
  
- [Che cos'è Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [Attivare Rights Management nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

## <a name="how-do-i"></a>Come eseguire l'operazione...

|**Per eseguire questa attività**|**Vedere queste risorse**|
|:-----|:-----|
|Configurare la crittografia per l'organizzazione  <br/> |[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md) <br/> |
|Visualizzare i dettagli relativi ai certificati, alle tecnologie e ai gruppi di crittografia TLS in Office 365  <br/> |[Informazioni tecniche sulla crittografia in Office 365](technical-reference-details-about-encryption.md) <br/> |
|Utilizzo dei messaggi crittografati in un dispositivo mobile  <br/> |[Visualizzazione dei messaggi crittografati sul dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Visualizzare i messaggi crittografati sul tuo iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Crittografare un documento mediante la protezione tramite password  <br/><br/>  Attualmente, la protezione tramite password non è supportata in Office Online. Utilizzare le versioni desktop di Word, Excel e PowerPoint per la protezione delle password.           |[Aggiungere o rimuovere la protezione nel documento, nella cartella di lavoro o nella presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) Scegliere una sezione **Aggiungi protezione** e quindi fare clic **su Crittografa con password** .  <br/> |
|Rimuovere la crittografia da un documento  <br/> |[Aggiungere o rimuovere la protezione nel documento, nella cartella di lavoro o nella presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) Scegliere una sezione **Rimuovi protezione** e quindi fare clic su **Rimuovi crittografia password**  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Pianificare le funzionalità di sicurezza e protezione delle informazioni di Office 365](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[Sicurezza e conformità in Office 365 for Business-Guida per gli amministratori](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

