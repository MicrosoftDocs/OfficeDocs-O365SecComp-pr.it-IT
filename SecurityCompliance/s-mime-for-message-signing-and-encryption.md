---
title: S/MIME per la firma e la crittografia dei messaggi in Exchange Online
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Gli amministratori possono acquisire informazioni sull'utilizzo di S/MIME in Exchange Online.
ms.openlocfilehash: ddb244e9e0cb189dbeb78af49e34ed90f64e77cc
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35601093"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME per la firma e la crittografia dei messaggi in Exchange Online

S/MIME (Secure/Multipurpose Internet Mail Extensions) è un metodo ampiamente accettato (o più precisamente un protocollo) per l'invio di messaggi crittografati e firmati digitalmente. S/MIME consente di crittografare i messaggi di posta elettronica e di apporvi la firma digitale. Quando si utilizza S/MIME con un messaggio di posta elettronica, aiuta le persone che ricevono il messaggio per essere certi che quello che vedono nella propria posta in arrivo è il messaggio esatto che è stato avviato con il mittente. Inoltre, gli utenti che ricevono messaggi devono essere certi che il messaggio proviene da un mittente specifico e non da un utente che finge di essere il mittente. A tale scopo, S/MIME fornisce servizi di protezione crittografica quali autenticazione, integrità dei messaggi e non-rifiuto dell'origine (utilizzando le firme digitali). Aiuta anche a migliorare la privacy e la sicurezza dei dati (utilizzando la crittografia) per la messaggistica elettronica. Per un quadro completo della storia e dell'architettura di S/MIME nel contesto della posta elettronica, vedere [Concetti relativi a S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).

In qualità di amministratore di Exchange Online, è possibile abilitare la sicurezza basata su S/MIME per le cassette postali dell'organizzazione. Utilizzare le linee guida negli argomenti correlati insieme a Exchange Online PowerShell per configurare S/MIME. Per utilizzare S/MIME nei client di posta elettronica supportati, gli utenti dell'organizzazione devono disporre di certificati rilasciati per la firma e la crittografia e i dati pubblicati nel servizio di dominio Active Directory locale (AD DS). Il servizio di dominio Active Directory deve trovarsi nei computer in una posizione fisica che è possibile controllare e non in una funzionalità remota o in una rete basata su cloud da qualche parte su Internet. Per ulteriori informazioni su AD DS, vedere [Servizi di dominio Active Directory](https://go.microsoft.com/fwlink/?LinkID=394064).

## <a name="supported-scenarios-and-technical-considerations"></a>Scenari supportati e considerazioni tecniche

È possibile configurare S/MIME per utilizzare uno qualsiasi dei seguenti endpoint:

- Outlook 2010 o versioni successive

- Outlook sul Web (in precedenza noto come Outlook Web App).

- Exchange ActiveSync (EAS)

La procedura da seguire per configurare S/MIME con ognuno di questi punti finali è leggermente diversa. In generale, è necessario eseguire le operazioni seguenti:

- Installare un'autorità di certificazione basata su Windows e configurare un'infrastruttura a chiave pubblica per l'emissione di certificati S/MIME. Sono supportati anche i certificati emessi da provider di certificati di terze parti. Per informazioni dettagliate, vedere [Panoramica di Servizi certificati Active Directory](https://technet.microsoft.com/library/hh831740.aspx).

- Pubblicare il certificato dell'utente in un account di servizi di dominio Active Directory locale negli attributi **userSMIMECertificate** e/o **userCertificate** .

- Per le organizzazioni di Exchange Online, sincronizzare i certificati dell'utente da servizi di dominio Active Directory ad Azure Active di repertorio utilizzando una versione appropriata di DirSync. Questi certificati vengono quindi sincronizzati da Azure Active Directory alla directory di Exchange Online e verranno utilizzati durante la crittografia di un messaggio a un destinatario.

- Configurare una raccolta di certificati virtuali per convalidare S/MIME. Queste informazioni vengono utilizzate da Outlook sul Web per convalidare la firma di un messaggio di posta elettronica e per garantire che sia stato firmato da un certificato attendibile.

- Configurare l'endpoint Outlook o EAS per utilizzare S/MIME.

## <a name="setup-smime-with-outlook-on-the-web"></a>Configurazione di S/MIME con Outlook sul Web

La configurazione di S/MIME per Exchange Online con Outlook sul Web prevede i passaggi principali seguenti:

1. [Configurare le impostazioni S/MIME per Outlook sul web](configure-s-mime-settings-for-outlook-web-app.md)

2. [Configurare la raccolta di certificati virtuali per convalidare S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [Sincronizzare i certificati dell'utente con Office 365 per S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Tecnologie di crittografia del messaggio correlato

Poiché la sicurezza dei messaggi diventa più importante, gli amministratori devono comprendere i principi e i concetti della messaggistica sicura. Questa comprensione è particolarmente importante a causa della crescente varietà di tecnologie correlate alla protezione (tra cui S/MIME) disponibili. Per ulteriori informazioni su S/MIME e su come funziona nel contesto della posta elettronica, vedere [Understanding s/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). Un'ampia gamma di tecnologie di crittografia interagiscono per garantire la protezione dei messaggi a riposo e in transito. S/MIME può funzionare contemporaneamente con le tecnologie seguenti ma non dipende da esse:

- **Transport Layer Security (TLS)** crittografa il tunnel o la route tra i server di posta elettronica al fine di prevenire lo snooping e le intercettazioni.

- **Secure Sockets Layer (SSL)** crittografa la connessione tra i client di posta elettronica e i server di Office 365.

- **BitLocker** crittografa i dati su un disco rigido in un datacenter in modo che se qualcuno ottiene accesso non autorizzato, non riesce a leggerlo.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME rispetto alla crittografia dei messaggi di Office 365

S/MIME richiede un certificato e un'infrastruttura di pubblicazione spesso utilizzata nelle situazioni interaziendali o tra azienda e consumatori. L'utente controlla le chiavi crittografiche in S/MIME e può scegliere se utilizzarle per ogni messaggio inviato. I programmi di posta elettronica come Outlook cercano la posizione di un'autorità di certificazione radice attendibile per eseguire la firma digitale e la verifica della firma. La crittografia dei messaggi di Office 365 è un servizio di crittografia basato su criteri che può essere configurato da un amministratore e non da un singolo utente, per crittografare la posta inviata a chiunque sia all'interno che all'esterno dell'organizzazione. Si tratta di un servizio online basato su Azure Rights Management (RMS) e non si basa su un'infrastruttura a chiave pubblica. La crittografia dei messaggi di Office 365 fornisce anche funzionalità aggiuntive, ad esempio la possibilità di personalizzare la posta con il marchio dell'organizzazione. Per ulteriori informazioni sulla crittografia dei messaggi di Office 365, vedere la crittografia dei messaggi di [office 365](https://go.microsoft.com/fwlink/?LinkID=392525).

## <a name="more-information"></a>Ulteriori informazioni

[Outlook sul web](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)

[Posta sicura (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
