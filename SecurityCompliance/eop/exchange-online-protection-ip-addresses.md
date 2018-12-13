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
ms.openlocfilehash: 5ea1a3df2ba1ea6853e2e44983fa7a97877c0778
ms.sourcegitcommit: 031781d0eecf33baabcd03ea53546d41076062b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240509"
---
# <a name="exchange-online-protection-ip-addresses"></a>Indirizzi IP di EOP (Exchange Online Protection)

I seguenti indirizzi IP del data center Microsoft vengono utilizzati da Microsoft Exchange Online Protection (EOP) durante l'invio o la ricezione della posta elettronica o per i servizi amministrativi e del portale di Exchange Online Protection. Per inviare e ricevere i messaggi da EOP o utilizzare i servizi amministrativi, verificare che la rete accetti connessioni da questi indirizzi IP.
 
> [!NOTE]
> Microsoft ha sviluppato un servizio web basato su REST per l'indirizzo IP e le voci FQDN in questa pagina. Questo nuovo servizio consente di configurare e aggiornare i dispositivi di rete perimetrale, ad esempio firewall e server proxy. È possibile scaricare l'elenco di endpoint, la versione corrente dell'elenco o modifiche specifiche. Questo servizio sostituisce il documento XML, feed RSS e l'indirizzo IP e le voci FQDN in questa pagina. Per provare a utilizzare questo nuovo servizio, passare al [servizio Web di URL e indirizzo IP di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service). 
 
## <a name="eop-ip-address-ranges"></a>Intervalli di indirizzi IP di EOP

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
> Gli intervalli di indirizzi IP descritti di seguito vengono utilizzati solo per l'inoltro tramite i connettori di clienti. Modifiche all'elenco di indirizzi IP sono rare e vengono comunicate in anticipo. Per garantire che i messaggi inviati a partner commerciali, uno smart host o una route di ambiente locale e del servizio pubblicata intervallo di indirizzi IP, è necessario configurare il connettore corretto per il routing a ogni destinazione. Per ulteriori informazioni sui connettori, vedere [Decidere quale connettore da utilizzare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail). gli indirizzi IP in questo argomento possono cambiare nel tempo.  
 
Per informazioni sugli indirizzi IP utilizzati da Microsoft Office 365, vedere [URL e intervalli di indirizzi IP per Office 365](https://go.microsoft.com/fwlink/p/?LinkId=324165).

