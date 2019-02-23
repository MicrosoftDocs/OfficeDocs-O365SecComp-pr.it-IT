---
title: Dettagli tecnici di riferimento sulla crittografia in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/15/2019
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Visualizzare i dettagli tecnici relativi a Encyption in Office 365.
ms.openlocfilehash: 77e12d0d4872d29e9cc33571b2cd5040d8d45677
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213626"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Dettagli tecnici di riferimento sulla crittografia in Office 365

Fare riferimento a questo articolo per informazioni sui certificati, le tecnologie e i gruppi di crittografia TLS utilizzati per la [crittografia in Office 365](encryption.md). In questo articolo sono inoltre disponibili informazioni dettagliate sulle deprecazioni pianificate.
  
- Se si cercano informazioni generali, vedere [crittografia in Office 365](encryption.md).
- Se si desiderano informazioni sull'installazione, vedere [configurare la crittografia in Office 365 Enterprise](set-up-encryption.md).
- Per informazioni sui gruppi di crittografia supportati da versioni specifiche di Windows, vedere [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gestione e proprietà dei certificati di Microsoft Office 365

Dal momento che Microsoft utilizza il proprio certificato, non è necessario acquistare o mantenere i certificati per Office 365.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Standard di crittografia correnti e deprecazioni pianificate

Per continuare a fornire la crittografia Best-in-class per Office 365, Microsoft esamina periodicamente gli standard di crittografia supportati. A volte, è necessario deprecare gli standard precedenti quando diventano obsoleti e pertanto meno sicuri. In questo argomento vengono descritti i gruppi di crittografia attualmente supportati e altri standard, nonché i dettagli relativi alle deprecazioni pianificate. 

## <a name="fips-compliance-for-office-365"></a>Conformità FIPS per Office 365
Tutti i gruppi di crittografia supportati da Office 365 utilizzano algoritmi accettati in FIPS 140-2. Office 365 eredita le convalide FIPS da Windows (tramite Schannel). Per informazioni su SChannel, vedere [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versioni di TLS supportati da Office 365

Transport Layer Security (TLS) e il precedente Secure Sockets Layer (SSL) sono protocolli crittografici che proteggono la comunicazione in rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. Office 365 supporta diverse versioni di TLS, tra cui:
  
- TLS versione 1.2 (TLS 1.2)
    
- TLS versione 1.1 (TLS 1.1)
    
- TLS versione 1.0 (TLS 1.0)
    
 Il supporto di TLS 1,0 e TLS 1,1 diventerà obsoleto il 31 ottobre 2018. Per ulteriori informazioni, vedere [deprecating support for TLS 1,0 e 1,1 e cosa significa questo per voi](technical-reference-details-about-encryption.md#TLS11and12deprecation) . 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>Supporto obsoleto per TLS 1,0 e 1,1 e cosa significa per te
<a name="TLS11and12deprecation"> </a>

Al 31 ottobre 2018, Office 365 non supporterà più TLS 1,0 e 1,1. Questo significa che Microsoft non correggerà i nuovi problemi che si trovano nei client, nei dispositivi o nei servizi che si connettono a Office 365 utilizzando TLS 1,0 e 1,1.

Si noti che questo non significa che Office 365 bloccherà le connessioni TLS 1,0 e 1,1. Non esiste una data ufficiale per la disabilitazione o la rimozione di TLS 1,0 e 1,1 nel servizio TLS per le connessioni dei clienti. La data di deprecazione finale verrà determinata dalla telemetria del cliente e non è ancora nota. Dopo che è stata presa una decisione, vi sarà un annuncio di sei mesi di anticipo, a meno che non si venga a conoscenza di un compromesso noto, nel qual caso potrebbe essere necessario agire in meno di sei mesi per proteggere i clienti che utilizzano i servizi.

È necessario assicurarsi che tutte le combinazioni client-server e browser-server utilizzino TLS 1,2 (o versione successiva) per mantenere la connessione ai servizi di Office 365. Potrebbe essere necessario aggiornare determinate combinazioni client-server e browser-server. Per informazioni su come questo ha un impatto, vedere [preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Supporto obsoleto per 3DES
<a name="TLS11and12deprecation"> </a>

Al 31 ottobre 2018, Office 365 non supporterà più l'utilizzo di gruppi di crittografia 3DES per la comunicazione a Office 365. In particolare, Office 365 non supporterà più la famiglia di crittografia TLS_RSA_WITH_3DES_EDE_CBC_SHA. I client e i server che comunicano con O365 dopo questa data devono supportare almeno una delle cifrature più sicure elencate in questo argomento (vedere [TLS Cipher Suites supportato da Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Sospensione del supporto relativo al certificato SHA-1 in Office 365
<a name="TLS11and12deprecation"> </a>

A giugno 2016, Office 365 non accetta più un certificato SHA-1 per le connessioni in uscita o in ingresso. Se si sta attualmente utilizzando un certificato con SHA-1 nella catena di certificati, sarà necessario aggiornare la catena per l'utilizzo di SHA-2 (Secure Hash Algorithm 2) o di un algoritmo di hash più robusto.
  
## <a name="deprecating-rc4-support-in-office-365"></a>Sospensione del supporto RC4 in Office 365
<a name="TLS11and12deprecation"> </a>

Nel mese di luglio 2015, è terminato il supporto per il seguente pacchetto di crittografia RC4:
  
- TLS_RSA_WITH_RC4_128_SHA
    
- TLS_RSA_WITH_RC4_128_MD5
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a>Approvazione del supporto di Secure Sockets Layer (SSL) 3,0 in Office 365
<a name="TLS11and12deprecation"> </a>

A partire dal 1 ° dicembre 2014, Office 365 ha iniziato a disabilitare il supporto per Secure Sockets Layer (SSL) 3,0, il predecessore di TLS. Per ulteriori informazioni, vedere [Advisory sulla sicurezza 3009008](https://technet.microsoft.com/library/security/3009008.aspx). Per istruzioni su come garantire che i client utilizzino TLS 1,0 o versione successiva e per disabilitare SSL 3,0, vedere [protectING ssl 3,0 Vulnerability](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/).
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Gruppi di crittografia TLS supportati da Office 365
<a name="TLSCipherSuites"> </a>

Un pacchetto di crittografia è una raccolta di algoritmi di crittografia utilizzati da TLS per stabilire connessioni protette. Nella tabella seguente sono riportati i pacchetti di crittografia supportati da Office 365 in ordine di priorità, a partire dai pacchetti di crittografia dotati di forza maggiore. Quando Office 365 riceve una richiesta di connessione, innanzitutto tenta di stabilire una connessione utilizzando il primo pacchetto di crittografia nell'elenco; in caso di esito negativo, tenta utilizzando il secondo pacchetto di crittografia nell'elenco e così via. Quando Office 365 invia una richiesta di connessione a un altro server o a un client, la scelta del pacchetto di crittografia da utilizzare o della possibilità o meno di utilizzare TLS dipende dal server o dal client ricevente.

> [!IMPORTANT]
> Tenere presente che le versioni di TLS sono obsolete e che *non è consigliabile utilizzare* le versioni obsolete in cui sono disponibili versioni più recenti. In altre parole, in qualsiasi luogo in cui è elencato che TLS 1,0, 1,1 e 1,2 sono supportati, scegliere la versione *più recente* (TLS 1,2).
  
|**Protocolli**|**Nome del pacchetto di crittografia**|**Algoritmo di scambio di chiave**|**Supporto di Perfect Forward Secrecy**|**Algoritmo di autenticazione/forza**|**Crittografia/Forza**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |Sì  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |Sì  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |No  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>Argomenti correlati
[Suite di crittografia TLS in Windows 10 v1607](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Crittografia in Office 365](encryption.md)
  
[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md)
  
[Implementazione di SChannel di TLS 1,0 nell'aggiornamento dello stato di sicurezza di Windows: 24 novembre 2015](https://support.microsoft.com/kb/3117336)
  
[Miglioramenti della crittografia TLS/SSL (centro IT di Windows)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

