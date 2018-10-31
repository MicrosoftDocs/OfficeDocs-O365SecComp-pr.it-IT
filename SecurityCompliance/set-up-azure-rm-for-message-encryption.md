---
title: Configurare Azure Rights Management per Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: La versione precedente di Office 365 Message Encryption dipende da Microsoft Azure Rights Management (precedentemente noto come Windows Azure Active Directory Rights Management).
ms.openlocfilehash: f8759da8628d4c78fe5409f5c47e3fc2b3e9484e
ms.sourcegitcommit: c05076501dfe118e575998ecfc08ad69d13c8abc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2018
ms.locfileid: "25853071"
---
# <a name="this-article-applies-to-the-previous-version-of-ome"></a>In questo articolo si applica alla versione precedente di OME
Se si ancora non sono stati spostati organizzazione Office 365 per le nuove funzionalità OME, ma sono già stati distribuiti OME, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia che si intende spostare le nuove funzionalità OME non appena è ragionevole per l'organizzazione. Per ulteriori informazioni, vedere [impostare le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md). Se si desidera trovare ulteriori informazioni sul funzionamento innanzitutto le nuove funzionalità, vedere [Office 365 Message Encryption](ome.md). Il resto di questo articolo si riferisce al comportamento OME prima del rilascio delle nuove funzionalità OME.

# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>Configurare Azure Rights Management per la versione precedente di Office 365 Message Encryption

In questo argomento vengono descritti i passaggi da seguire per poter attivare e quindi impostare backup Azure Rights Management (RMS), parte di Azure Information Protection per l'utilizzo con la crittografia messaggi Office 365 (OME).
  
## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Prerequisiti per l'utilizzo della versione precedente di Office 365 Message Encryption
<a name="warmprereqs"> </a>

Office 365 messaggio crittografia dei, tra cui IRM, dipende dall'Azure Rights Management (Azure RMS). RMS Azure è la tecnologia di protezione utilizzata per la protezione delle informazioni di Azure. Per utilizzare OME, l'organizzazione Office 365 deve includere una sottoscrizione di Exchange Online o Exchange Online Protection che, a sua volta, include una sottoscrizione di Azure Rights Management.
  
- Se non si è certi della sottoscrizione include, vedere la descrizione del servizio Exchange Online [Message Policy, Recovery e conformità](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).
    
- Se non si dispone di una sottoscrizione di RMS Azure per Exchange Online o Exchange Online Protection, è necessario acquistare una sottoscrizione e attivarlo prima.
    
    Per informazioni sull'acquisto di una sottoscrizione per Azure Rights Management, vedere [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). Nella sezione successiva vengono fornite informazioni relative all'attivazione di Azure Rights Management.
    
- Se si dispone di Azure Rights Management, ma non è configurato per Exchange Online o Exchange Online Protection, in questo articolo viene illustrato come attivare Azure Rights Management e quindi il viene descritto il modo migliore per impostare OME per funzionare con Azure Rights Management.
    
- Se già stato configurato OME per funzionare con Azure Rights Management per Exchange Online o Exchange Online Protection, a seconda della modalità di configurazione, potrebbe essere possibile iniziare a utilizzare le funzionalità nuove e OME immediatamente. In questo articolo viene illustrato come determinare se è stato impostato OME correttamente, come procedere se è necessario modificare la configurazione, e cosa succede se si sceglie di non modificare il programma di installazione. Ad esempio, per poter utilizzare le nuove funzionalità, è necessario utilizzare RMS Azure con OME. È possibile utilizzare le nuove funzionalità con un RMS di locale Active Directory.
    
## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Attivare Azure Rights Management per la versione precedente di OME in Office 365
<a name="activatewarm"> </a>

È necessario attivare Azure Rights Management in modo che gli utenti dell'organizzazione possono applicare la protezione delle informazioni per i messaggi inviati e aprire messaggi e file sono protetti dal servizio Azure Rights Management. Per ulteriori informazioni, vedere [Attivazione di Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Dopo aver completato l'attivazione, tornare a questa e continuare con le attività descritte in questo articolo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Impostare la versione precedente di OME da utilizzare RMS Azure mediante l'importazione di pubblicazione trusted (domini di pubblicazione trusted)
<a name="importTPDs"> </a>

Un dominio di pubblicazione Trusted è un file XML che contiene informazioni sulle impostazioni di gestione dei diritti dell'organizzazione. Ad esempio, il dominio di pubblicazione Trusted contiene informazioni sul certificato concessore di licenze server (SLC) utilizzato per la firma e crittografia dei certificati e licenze, gli URL utilizzati per la gestione delle licenze e di pubblicazione e così via. Importare il dominio di pubblicazione Trusted nell'organizzazione Office 365 tramite Windows PowerShell.
  
> [!IMPORTANT]
> In precedenza, è possibile scegliere di importare domini di pubblicazione trusted dal servizio Active Directory Rights Management (AD RMS) nell'organizzazione Office 365. Tuttavia, in questo modo si impedisce di utilizzo delle nuove funzionalità OME e non è consigliato. Se Office 365 dell'organizzazione è attualmente configurato in questo modo, si consiglia di creare un piano per eseguire la migrazione dal RMS Directory locale attivo per la protezione delle informazioni di Azure basate su cloud. Per ulteriori informazioni, vedere [Migrating from AD RMS per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Non sarà in grado di utilizzare le nuove funzionalità OME fino al completamento della migrazione per la protezione delle informazioni di Azure. 
  
 **Per importare domini di pubblicazione trusted da RMS Azure**
  
1. [Connessione a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Scegliere l'URL di condivisione chiave corrispondente alla posizione geografica dell'organizzazione Office 365:
    
|**Posizione**|**URL del percorso di condivisione della chiave**|
|:-----|:-----|
|Nord America  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Unione Europea  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Sud America  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 per il governo (Government Community Cloud)  <br/> Questo percorso di condivisione chiave di RMS è riservato per i clienti che hanno acquistato Office 365 per SKU governative.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. Configurare il percorso di condivisione chiave eseguendo il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) come indicato di seguito: 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    Ad esempio, per configurare il percorso di condivisione se l'organizzazione si trova in Nord America chiave:
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. Eseguire il cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con l'opzione RMSOnline - per importare TPD da Azure Rights Management: 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    Dove *TPDName* è il nome da utilizzare per il dominio di pubblicazione Trusted. Ad esempio, "Contoso North American TPD". 
    
5. Per verificare la corretta configurazione organizzazione Office 365 per l'utilizzo del servizio di Azure Rights Management, eseguire il cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con l'opzione RMSOnline - come indicato di seguito: 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    Tra l'altro, questo cmdlet verifica la connettività con il servizio di Azure Rights Management, scarica il dominio di pubblicazione Trusted e controlla la validità.
    
6. Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come indicato di seguito per disattivare modelli di Azure Rights Management vengano disponibili in Outlook sul web e Outlook: 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come indicato di seguito per attivare Azure Rights Management per la propria organizzazione di posta elettronica basata sul cloud e configurarla per l'utilizzo di Azure Rights Management per la crittografia dei messaggi di Office 365: 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. Per verificare di aver importato il dominio di pubblicazione Trusted e abilitato Azure Rights Management, utilizzare il cmdlet Test-IRMConfiguration per verificare la funzionalità di Azure Rights Management. Per ulteriori informazioni, vedere "Esempi 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>È possibile disporre della versione precedente di OME impostata con Active Directory Rights Management non Azure Information Protection, come è possibile procedere?
<a name="importTPDs"> </a>

È possibile continuare a utilizzare le regole di flusso di posta elettronica la crittografia dei messaggi di Office 365 esistente in Active Directory Rights Management, ma non è possibile configurare o utilizzare le nuove funzionalità OME. In realtà, è necessario eseguire la migrazione per la protezione delle informazioni di Azure. Per informazioni sulla migrazione e ciò significa per l'organizzazione, vedere [Migrating from AD RMS per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Passaggi successivi
<a name="importTPDs"> </a>

Dopo aver completato il programma di installazione di Azure Rights Management, se si desidera abilitare le nuove funzionalità OME, vedere [impostare le nuove funzionalità di Office 365 Message Encryption basate sul Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
Dopo aver configurato l'organizzazione di utilizzare le nuove funzionalità OME, si è pronti per [definire le regole del flusso di posta elettronica per proteggere i messaggi di posta elettronica con le nuove funzionalità OME](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Argomenti correlati
<a name="importTPDs"> </a>

[Crittografia in Office 365](encryption.md)
  
[Dettagli tecnici di riferimento sulla crittografia in Office 365](technical-reference-details-about-encryption.md)
  
[Che cos'è Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

