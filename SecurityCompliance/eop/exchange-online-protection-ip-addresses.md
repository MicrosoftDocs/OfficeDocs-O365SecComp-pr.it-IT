---
title: Indirizzi IP di EOP (Exchange Online Protection)
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: I seguenti indirizzi IP del data center Microsoft vengono utilizzati da Microsoft Exchange Online Protection (EOP) durante l'invio o la ricezione della posta elettronica o per i servizi amministrativi e del portale di Exchange Online Protection. Per inviare e ricevere i messaggi da EOP o utilizzare i servizi amministrativi, verificare che la rete accetti connessioni da questi indirizzi IP.
ms.openlocfilehash: 1b5dad69fb300f36bc94c9d264492f9c9be8948f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026323"
---
# <a name="exchange-online-protection-ip-addresses"></a>Indirizzi IP di EOP (Exchange Online Protection)

I seguenti indirizzi IP del data center Microsoft vengono utilizzati da Microsoft Exchange Online Protection (EOP) durante l'invio o la ricezione della posta elettronica o per i servizi amministrativi e del portale di Exchange Online Protection. Per inviare e ricevere i messaggi da EOP o utilizzare i servizi amministrativi, verificare che la rete accetti connessioni da questi indirizzi IP.
 
> [!NOTE]
> Microsoft sta sviluppando un servizio web basato su REST per l'indirizzo IP e le voci FQDN in questa pagina. Questo nuovo servizio consentono di configurare e aggiornare i dispositivi di rete perimetrale, ad esempio firewall e server proxy. È possibile scaricare l'elenco di endpoint, la versione corrente dell'elenco o modifiche specifiche. Questo servizio in futuro sostituirà il documento XML, feed RSS e l'indirizzo IP e le voci FQDN in questa pagina. Per provare a utilizzare questo nuovo servizio, accedere al [servizio Web](https://support.office.com/article/managing-office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#webservice). 
 
## <a name="eop-ip-address-ranges"></a>Intervalli di indirizzi IP di EOP

Di seguito è riportato l'elenco completo degli intervalli di indirizzi IP di EOP a partire da **2/7/2018**. 

||||
|:-----|:-----|:-----|
|**Intervalli di indirizzi IPv4** <br/> |**Intervalli di indirizzi IPv6** <br/> |
| 23.103.132.0/22 | c 2a01:111:f400:7 00::/ / 54 |
| 23.103.136.0/21 | 2a01:111:f400:fc00::/ / 54 |
| 23.103.144.0/20 | 2a01:111:f403:: 48 |
| 23.103.198.0/23 |  |
| 23.103.200.0/22 |  |
| 40.92.0.0/14 |  |
| 40.107.0.0/17 |  |
| 52.100.0.0/14 |  |
| 52.238.78.88/32 |  |
| 65.55.88.0/24 |  |
| 65.55.169.0/24 |  |
| 94.245.120.64/26 |  |
| 104.47.0.0/17 |  |
| 157.55.234.0/24 |  |
| 157.56.110.0/23 |  |
| 157.56.112.0/24 |  |
| 207.46.100.0/24 |  |
| 207.46.163.0/24 |  |
| 213.199.154.0/24 |  |
| 213.199.180.128/26 |  |
| 216.32.180.0/23 |  |
||||
 
> [!IMPORTANT]
> Gli intervalli di indirizzi IP descritti di seguito vengono utilizzati solo per l'inoltro tramite i connettori di clienti. Modifiche all'elenco di indirizzi IP sono rare e vengono comunicate in anticipo. Per garantire che i messaggi inviati a partner commerciali, uno smart host o una route di ambiente locale e del servizio pubblicata intervallo di indirizzi IP, è necessario configurare il connettore corretto per il routing a ogni destinazione. Per ulteriori informazioni sui connettori, vedere [Decidere quale connettore da utilizzare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail). gli indirizzi IP in questo argomento possono cambiare nel tempo. Per un record dell'indirizzo IP di tutti gli indirizzi che sono stati aggiunti, modificati o obsoleti lo scorso anno, vedere [Modifica delle notifiche per gli indirizzi IP di EOP](change-notification-for-eop-ip-addresses.md). 
 
Per informazioni sugli indirizzi IP utilizzati da Microsoft Office 365, vedere [URL e intervalli di indirizzi IP per Office 365](https://go.microsoft.com/fwlink/p/?LinkId=324165).
 
## <a name="ip-ranges-by-region"></a>Intervalli IP per area geografica

Exchange Online Protection consente di instradare la posta nel modo più efficiente, mantenendo la conformità con gli obblighi contrattuali nei confronti degli utenti. Premesso ciò, gli endpoint di EOP seguenti rappresentano l'elenco attuale degli intervalli IPv4 locali. Tuttavia, è possibile eseguire il provisioning di questi intervalli IP senza preavviso per un'altra funzione all'interno di EOP per supportare capacità ed efficienza. In questi casi, il flusso di posta non verrà interrotto in base agli obblighi contrattuali e verrà fornito un elenco di endpoint aggiornato regolarmente in seguito alle modifiche apportate. Al momento non sono mantenuti elenchi degli endpoint locali per altri elementi di Office 365.
 
||||
|:-----|:-----|:-----|
|**Americhe** <br/> |**EMEA** <br/> |**APAC** <br/> |
| 23.103.132.0/22 | 23.103.132.0/22 |23.103.136.0/21 |
| 23.103.136.0/21 | 23.103.144.0/22 |23.103.152.0/22 |
| 23.103.148.0/22 | 40.92.0.0/18 |40.92.128.0/17 |
| 23.103.152.0/21 | 40.93.0.0/18 |40.93.128.0/17 |
| 23.103.156.0/22 | 40.94.0.0/18 |40.94.128.0/17 |
| 23.103.198.0/24 | 40.95.0.0/18 |40.95.128.0/17 |
| 23.103.200.0/22 | 40.107.0.0/18 |52.100.128.0/17 |
| 40.92.64.0/18 | 52.100.0.0/18 |52.101.128.0/17 |
| 40.93.64.0/18 | 52.101.0.0/18 |52.102.128.0/17 |
| 40.94.64.0/18 | 52.102.0.0/18 |52.103.128.0/17 |
| 40.95.64.0/18 | 52.103.0.0/18 |65.55.88.0/24 |
| 40.107.64.0/18 | 94.245.120.64/27 |104.47.64.0/18 |
| 52.100.64.0/18 | 104.47.0.0/19 |c 2a01:111:f400:7 00::/ / 54 |
| 52.101.64.0/18 | 157.55.234.0/24 |  |
| 52.102.64.0/18 | 157.56.112.0/24 | |
| 52.103.64.0/18 | 213.199.154.0/24 | |
| 65.55.169.0/24 | 213.199.180.128/26 | |
| 104.47.32.0/19 | 2a01:111:f400:7e00::/ / 56 | |
| 157.56.110.0/23 | 2a01:111:f400:fe00::/ / 56 | |
| 207.46.100.0/24 |  | |
| 207.46.163.0/24 |  | |
| 216.32.180.0/23 |  | |
| c 2a01:111:f400:7 00::/ / 54 |  | |
||||
