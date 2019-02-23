---
title: Indirizzi IP di EOP (Exchange Online Protection)
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: I seguenti indirizzi IP del data center Microsoft vengono utilizzati da Microsoft Exchange Online Protection (EOP) durante l'invio o la ricezione della posta elettronica o per i servizi amministrativi e del portale di Exchange Online Protection. Per inviare e ricevere i messaggi da EOP o utilizzare i servizi amministrativi, verificare che la rete accetti connessioni da questi indirizzi IP.
ms.openlocfilehash: 6c7d8c78a012be3928317eac1e9b6fcdeab64a24
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222825"
---
# <a name="exchange-online-protection-ip-addresses"></a>Indirizzi IP di EOP (Exchange Online Protection)

I seguenti indirizzi IP del data center Microsoft vengono utilizzati da Microsoft Exchange Online Protection (EOP) durante l'invio o la ricezione della posta elettronica o per i servizi amministrativi e del portale di Exchange Online Protection. Per inviare e ricevere i messaggi da EOP o utilizzare i servizi amministrativi, verificare che la rete accetti connessioni da questi indirizzi IP.
 
> [!NOTE]
> Microsoft ha sviluppato un servizio Web basato sul REST per l'indirizzo IP e le voci FQDN in questa pagina. Questo nuovo servizio consente di configurare e aggiornare i dispositivi perimetrali di rete, ad esempio firewall e server proxy. È possibile scaricare l'elenco degli endpoint, la versione corrente dell'elenco o le modifiche specifiche. Questo servizio sostituisce il documento XML, il feed RSS e l'indirizzo IP e le voci FQDN in questa pagina. Per provare questo nuovo servizio, accedere a [Office 365 IP address and URL Web Service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service). 
 
## <a name="eop-ip-address-ranges"></a>Intervalli di indirizzi IP di EOP

||||
|:-----|:-----|:-----|
|**Intervalli di indirizzi IPv4** <br/> |**Intervalli di indirizzi IPv6** <br/> |
| 23.103.132.0/22 | 2a01:111: F400:7c00::/54 |
| 23.103.136.0/21 | 2a01:111: F400: fc00::/54 |
| 23.103.144.0/20 | 2a01:111: F403::/48 |
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
> Gli intervalli di indirizzi IP forniti in questo articolo vengono utilizzati solo per l'inoltro tramite i connettori dei clienti. Le modifiche apPortate all'elenco degli indirizzi IP sono rare e vengono comunicate in anticipo. Per assicurarsi che i messaggi inviati ai partner commerciali, a uno smart host o a una route di ambiente locale tramite l'intervallo di indirizzi IP pubblicato dal servizio, sia necessario configurare il connettore corretto per il routing a ogni destinazione. Per ulteriori informazioni sui connettori, vedere [decidere quale connettore utilizzare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail). gli indirizzi IP in questo argomento possono variare nel tempo.  
 
Per informazioni sugli indirizzi IP utilizzati da Microsoft Office 365, vedere [URL e intervalli di indirizzi IP per Office 365](https://go.microsoft.com/fwlink/p/?LinkId=324165).

