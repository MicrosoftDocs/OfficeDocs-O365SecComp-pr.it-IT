---
title: Dettagli tecnici di riferimento sulla crittografia in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/15/2019
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Visualizzare i dettagli tecnici sulle crittografia in Office 365.
ms.openlocfilehash: c11f152b18a15886fc8a5108e6df66dafe53a758
ms.sourcegitcommit: 6bdba12c13c02f7d9a7297d3042933b100c4e481
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "29966190"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Dettagli tecnici di riferimento sulla crittografia in Office 365

Fare riferimento a questo articolo per informazioni sui certificati, tecnologie e TLS famiglie di prodotti di crittografia utilizzati per [la crittografia in Office 365](encryption.md). In questo articolo sono inoltre disponibili informazioni dettagliate sui deprecate pianificati.
  
- Se si sta cercando panoramica delle informazioni, vedere [crittografia in Office 365](encryption.md).
- Se si sta cercando informazioni sull'installazione, vedere [configurazione di crittografia in Office 365 Enterprise](set-up-encryption.md).
- Per informazioni sui gruppi di crittografia supportato da versioni specifiche di Windows, vedere [Famiglie di prodotti di crittografia in TLS/SSL (provider di servizi condivisi Schannel)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gestione e proprietà dei certificati di Microsoft Office 365

Dal momento che Microsoft utilizza il proprio certificato, non è necessario acquistare o mantenere i certificati per Office 365.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Standard di crittografia corrente e deprecate pianificati

Per continuare a fornire la crittografia ottimale in classe per Office 365, Microsoft vengono esaminati regolarmente standard di crittografia supportato. In alcuni casi, è necessario rendere obsoleti i vecchi standard man mano che diventano aggiornato ed è pertanto meno sicuro. In questo argomento viene pacchetto di crittografia attualmente supportato e altri standard, nonché informazioni dettagliate sulle deprecate pianificati. 

## <a name="fips-compliance-for-office-365"></a>Conformità FIPS per Office 365
Tutti i gruppi di crittografia supportati da Office 365 utilizzano algoritmi accettabili in FIPS 140-2. Office 365 eredita le convalide FIPS da Windows (fino a Schannel). Per informazioni su Schannel, vedere [Famiglie di prodotti di crittografia in TLS/SSL (provider di servizi condivisi Schannel)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versioni di TLS supportati da Office 365

Transport Layer Security (TLS) e il precedente Secure Sockets Layer (SSL) sono protocolli crittografici che proteggono la comunicazione in rete utilizzando certificati di sicurezza per crittografare una connessione tra computer. Office 365 supporta diverse versioni di TLS, tra cui:
  
- TLS versione 1.2 (TLS 1.2)
    
- TLS versione 1.1 (TLS 1.1)
    
- TLS versione 1.0 (TLS 1.0)
    
 Supporto TLS 1.0 e TLS 1.1 diventerà obsoleto 31 ottobre 2018. Per ulteriori informazioni, vedere [supporto Deprecating per TLS 1.0, 1.1 e ciò significa automaticamente](technical-reference-details-about-encryption.md#TLS11and12deprecation) . 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>Sostituire il supporto per TLS 1.0, 1.1 e ciò significa automaticamente
<a name="TLS11and12deprecation"> </a>

A partire da 31 ottobre 2018, Office 365 non supporta più TLS 1.0 e 1.1. Ciò significa che Microsoft non correggerà nuovi problemi presenti nel client, i dispositivi o servizi che si connettono a Office 365 tramite TLS 1.0 e 1.1.

Si noti che non: Office 365 bloccherà TLS 1.0 e 1.1 connessioni. Non è una data ufficiale per la disabilitazione o rimozione di TLS 1.0 e 1.1 nel servizio di TLS per le connessioni dei clienti. La data finale è anche verrà determinata dal telemetria cliente e non è ancora definita. Dopo aver effettuata una decisione, ci sarà un annuncio sei mesi in anticipo a meno che non si possono conoscere un compromesso noto, nel qual caso è di agire in meno di sei mesi per proteggere i clienti che utilizzano i servizi.

È consigliabile verificare che tutte le combinazioni client o server browser utilizzano TLS 1.2 (o versioni successive) per gestire connessioni ai servizi di Office 365. Potrebbe essere necessario aggiornare alcune combinazioni client o server browser. Per informazioni su questo impatto è, vedere [Preparazione per l'utilizzo obbligatorio di TLS 1.2 in Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Sostituire il supporto per 3DES
<a name="TLS11and12deprecation"> </a>

A partire da 31 ottobre 2018, Office 365 non supporterà più l'utilizzo di famiglie di prodotti crittografia 3DES per la comunicazione con Office 365. In particolare, Office 365 non supporta più la famiglia di prodotti di crittografia TLS_RSA_WITH_3DES_EDE_CBC_SHA. Client e server di comunicazione con Office 365 dopo tale data deve supportare almeno una delle cifre più sicuri elencati in questo argomento (vedere [TLS crittografato famiglie di prodotti supportati da Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Sospensione del supporto relativo al certificato SHA-1 in Office 365
<a name="TLS11and12deprecation"> </a>

A partire da giugno 2016, Office 365 non accetta più un certificato SHA-1 per le connessioni in ingresso o in uscita. Se si stanno attualmente utilizzando un certificato con SHA-1 nella catena di certificati, è necessario aggiornare la catena per utilizzare SHA-2 (Secure Hash algoritmo di 2) o un algoritmo hash avanzato.
  
## <a name="deprecating-rc4-support-in-office-365"></a>Sospensione del supporto RC4 in Office 365
<a name="TLS11and12deprecation"> </a>

Nel mese di luglio 2015, è terminato il supporto per il seguente pacchetto di crittografia RC4:
  
- TLS_RSA_WITH_RC4_128_SHA
    
- TLS_RSA_WITH_RC4_128_MD5
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a>Sostituire il supporto di Secure Sockets Layer (SSL) 3.0 in Office 365
<a name="TLS11and12deprecation"> </a>

Avvio di 1 dicembre 2014 Office 365 ha iniziato disabilitando il supporto per SSL Secure Sockets Layer () 3.0 predecessore per TLS. Per ulteriori informazioni, vedere [Security 3009008 consulenza](https://technet.microsoft.com/library/security/3009008.aspx). Per istruzioni su come assicurare che i client utilizzano TLS 1.0 o successiva e per disabilitare SSL 3.0, vedere [vulnerabilità di protezione SSL 3.0](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/).
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Famiglie di prodotti di crittografia TLS supportate da Office 365
<a name="TLSCipherSuites"> </a>

Un pacchetto di crittografia è una raccolta di algoritmi di crittografia utilizzati da TLS per stabilire connessioni protette. Nella tabella seguente sono riportati i pacchetti di crittografia supportati da Office 365 in ordine di priorità, a partire dai pacchetti di crittografia dotati di forza maggiore. Quando Office 365 riceve una richiesta di connessione, innanzitutto tenta di stabilire una connessione utilizzando il primo pacchetto di crittografia nell'elenco; in caso di esito negativo, tenta utilizzando il secondo pacchetto di crittografia nell'elenco e così via. Quando Office 365 invia una richiesta di connessione a un altro server o a un client, la scelta del pacchetto di crittografia da utilizzare o della possibilità o meno di utilizzare TLS dipende dal server o dal client ricevente.

> [!IMPORTANT]
> Tenere presente che rendere obsoleti i versioni TLS e che obsoleto versioni *non deve essere utilizzata* in cui sono disponibili versioni più recenti. In altre parole, via Internet in cui è elencati che TLS 1.0, 1.1 e 1.2 sono supportati, scegliere la versione *più recente* (TLS 1.2).
  
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
[Famiglie di prodotti crittografia TLS in Windows 10 v1607](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Crittografia in Office 365](encryption.md)
  
[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md)
  
[Implementazione di Schannel di TLS 1.0 nell'aggiornamento dello stato di protezione di Windows: 24 novembre 2015](https://support.microsoft.com/kb/3117336)
  
[Miglioramenti della crittografiche TLS/SSL (Windows IT Center)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

