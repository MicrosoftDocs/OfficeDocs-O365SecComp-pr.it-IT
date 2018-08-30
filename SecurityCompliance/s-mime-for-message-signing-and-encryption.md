---
title: S/MIME per la crittografia e firma dei messaggi
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: S/MIME consente di crittografare i messaggi di posta elettronica e firmare digitalmente loro. Quando si utilizza S/MIME con un messaggio di posta elettronica, vengono fornite informazioni utili le persone che ricevono messaggio per assicurarsi che nella posta in arrivo visualizzato il messaggio esatto che ha avviato con il mittente.
ms.openlocfilehash: 26c50fb6e4d1b07b7dba26948ae46e7f36eeaec5
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002768"
---
# <a name="smime-for-message-signing-and-encryption"></a>S/MIME per la crittografia e firma dei messaggi

S/MIME (Secure/Multipurpose Internet Mail Extensions) è un metodo diffuso o messaggi crittografati e con maggiore precisione un protocollo, per l'invio di firma digitale. S/MIME consente di crittografare i messaggi di posta elettronica e firmare digitalmente loro. Quando si utilizza S/MIME con un messaggio di posta elettronica, vengono fornite informazioni utili le persone che ricevono messaggio per assicurarsi che nella posta in arrivo visualizzato il messaggio esatto che ha avviato con il mittente. E facilita anche gli utenti che ricevono i messaggi per essere certi che il messaggio proviene solo dal mittente specifico e non da qualcuno FALSO il mittente. A tale scopo, S/MIME sono disponibili per i servizi di protezione di crittografia, ad esempio l'autenticazione, l'integrità del messaggio e non ripudio di origine (utilizzo delle firme digitali). Consente inoltre di migliorare la privacy e sicurezza dei dati (utilizzando la crittografia) per il servizio di posta elettronica. Per uno sfondo approfondito cronologia e architettura di S/MIME nel contesto di posta elettronica, vedere [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). 
  
In qualità di amministratore, è possibile abilitare sicurezza basata su S/MIME per l'organizzazione se si dispongono delle cassette postali in Exchange 2013 SP1 o Exchange Online, una parte di Office 365. Utilizzare le istruzioni contenute negli argomenti riportati di seguito collegate con Exchange Management Shell per configurare S/MIME. Per utilizzare S/MIME nelle versioni supportate di Outlook o ActiveSync con Exchange 2013 SP1 o Exchange Online, gli utenti dell'organizzazione devono disporre i certificati emessi per scopi di crittografia e firma e dati pubblicati in Active Directory locale Servizi di dominio (AD DS). Il dominio di Active Directory deve essere collocato nel computer in una posizione fisica che è possibile controllare e non a livello di struttura remoto o servizio basato su cloud in un punto qualsiasi su internet. Per ulteriori informazioni su Active Directory, vedere [Servizi di dominio Active Directory](https://go.microsoft.com/fwlink/?LinkID=394064).
  
## <a name="supported-scenarios-and-technical-considerations"></a>Scenari supportati e considerazioni tecniche
<a name="sectionSection0"> </a>

Se l'organizzazione utilizza Exchange 2013 SP1 o Exchange Online, è possibile configurare S/MIME per utilizzare uno qualsiasi dei seguenti endpoint: 
  
- Outlook 2010
    
- Outlook 2013
    
- Outlook Web App
    
- Exchange ActiveSync (EAS)
    
I passaggi da eseguire per configurare S/MIME con ogni endpoint differiscono lievemente a seconda dell'endpoint scelto. In genere, è necessario completare le seguenti operazioni:
  
- Installare un'autorità di certificazione basato su Windows e configurare un'infrastruttura a chiave pubblica per l'emissione di certificati S/MIME. Sono inoltre supportati i certificati rilasciati dalle autorità di certificazione terze parti. Per ulteriori informazioni, vedere [Panoramica di servizi di Active Directory certificato](https://technet.microsoft.com/library/hh831740.aspx).
    
- Pubblicare il certificato utente in un account AD DS locale negli attributi UserSMIMECertificate e/o UserCertificate.
    
- Per le organizzazioni Exchange Online, sincronizzare i certificati utente da Active Directory in Azure Active Directory utilizzando una versione appropriata di DirSync. Tali certificati saranno ottenere sincronizzati da Azure Active Directory in Exchange Online directory e verranno utilizzati per crittografare i messaggi a un destinatario.
    
- Configurare una raccolta di certificati virtuali per convalidare S/MIME. Queste informazioni vengono utilizzate da OWA per convalidare la firma di un messaggio di posta elettronica e per garantire che sia stato firmato da un certificato attendibile.
    
- Configurare l'endpoint Outlook o EAS per utilizzare S/MIME. 
    
## <a name="setup-smime-with-outlook-web-app"></a>Configurare S/MIME con Outlook Web App
<a name="sectionSection1"> </a>

Configurazione di S/MIME per Exchange 2013 SP1 o Exchange Online con Outlook Web App prevede le operazioni chiave seguenti:
  
1. [Configurazione delle impostazioni S/MIME per Outlook Web App](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [Configurazione della raccolta di certificati virtuali per convalidare S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. [Sincronizzare i certificati utente per Office 365 per S/MIME](sync-user-certificates-to-office-365-for-s-mime.md) Questo passaggio si applica solo a Exchange Online. 
    
## <a name="related-message-encryption-technologies"></a>Tecnologie di crittografia del messaggio correlato
<a name="sectionSection2"> </a>

Man mano che diventano più importanti della protezione dei messaggi, gli amministratori devono conoscere i principi e concetti di protezione dei messaggi. Questa comprensione è particolarmente importante per la crescente varietà di protezione relative tecnologie, ad esempio S/MIME, che sono diventati disponibili. Per ulteriori informazioni sui S/MIME e come funziona nel contesto del messaggio di posta elettronica, vedere [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). Diverse tecnologie di crittografia integrati per assicurare la protezione per messaggi di rest e in transito. S/MIME possono lavorare contemporaneamente con le seguenti tecnologie ma non si basa su di essi:
  
> **Transport Layer Security (TLS)** crittografa il tunnel o la route tra i server di posta elettronica per poter prevenire lo snooping e le intercettazioni telefoniche. 
    
> **Secure Sockets Layer (SSL)** consente di crittografare la connessione tra il client di posta elettronica e i server di Office 365. 
    
> **BitLocker** consente di crittografare i dati su un disco rigido in un Data Center in modo che se qualcuno ottiene accesso non autorizzato, è possibile leggerli. 
    
### <a name="smime-compared-with-office-365-message-encryption"></a>Confronto tra S/MIME e crittografia dei messaggi di Office 365

S/MIME richiede un'infrastruttura di pubblicazione e certificato viene spesso utilizzata nelle situazioni business to business e business to consumer. L'utente consente di controllare le chiavi di crittografia S/MIME e possibile decidere se utilizzarli per ogni messaggio che inviano. Programmi di posta elettronica, ad esempio Outlook ricerca una posizione di autorità radice attendibile del certificato per eseguire la firma digitale e verifica della firma. Office 365 la crittografia dei messaggi è un servizio di crittografia basata su criteri che può essere configurato dall'amministratore e non un singolo utente, per crittografare i messaggi inviati a tutti gli utenti interni o esterni all'organizzazione. È un servizio online che si basa su Azure Rights Management (RMS) e non si basa su un'infrastruttura a chiave pubblica. Crittografia dei messaggi di Office 365 inoltre fornisce funzionalità aggiuntive, ad esempio consente di personalizzare la posta elettronica con il marchio dell'organizzazione. Per ulteriori informazioni sulla crittografia dei messaggi di Office 365, vedere [Office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).
  
## <a name="more-information"></a>Ulteriori informazioni
<a name="sectionSection3"> </a>

[Outlook Web App](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[Secure Mail (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

