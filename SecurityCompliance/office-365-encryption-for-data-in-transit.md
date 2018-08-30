---
title: Crittografia di Office 365 per i dati in transito
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: Breve spiegazione di come Microsoft consente di crittografare dati in transito.'
ms.openlocfilehash: 8f4781cf1127fb1b6bf742c267c76e3df39b8209
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530254"
---
# <a name="office-365-encryption-for-data-in-transit"></a>Crittografia di Office 365 per i dati in transito

Oltre a proteggere i dati relativi ai clienti statici, utilizzate da Microsoft tecnologie di crittografia per proteggere i dati dei clienti di Office 365 in transito. 

Dati sono in corso:
- Quando un client comunica con un server di Office 365.
- Quando un server di Office 365 comunica con un altro server di Office 365. e
- Quando un server di Office 365 comunica con un server non Office 365 (ad esempio, Exchange Online recapitando posta elettronica a un server di posta elettronica esterno).

Centro dati tra le comunicazioni tra i server di Office 365 viene eseguita tramite TLS o IPsec e tutti i server per i clienti negoziare una sessione protetta tramite TLS con i computer client (ad esempio, Exchange Online utilizza TLS 1.2 con il livello di crittografia 256 bit utilizzato FIPS (FEDERAL Livello di 140-2 convalidato 2). (Per un elenco delle famiglie di prodotti di crittografia TLS supportate da Office 365, vedere [informazioni di riferimento tecniche sulla crittografia in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) ). Ciò vale per i protocolli utilizzati dai client come Outlook, Skype per le aziende e Outlook sul web (ad esempio, HTTP, POP3 e così via).

I certificati pubblici emessi da Microsoft IT SSL tramite SSLAdmin, uno strumento Microsoft interno per proteggere la riservatezza dei dati trasmesse. Tutti i certificati rilasciati da Microsoft IT dispongono almeno a 2048 bit lunghezza e la conformità [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) richiede SSLAdmin verificare che i certificati emessi solo agli indirizzi IP pubblici e di proprietà di Microsoft. Tutti gli indirizzi IP che non soddisfano questo criterio vengono instradati tramite un processo di eccezione.

Tutti i dettagli di implementazione, ad esempio la versione di TLS in uso, se è abilitata Forward Secrecy (ADFS), l'ordine delle famiglie di prodotti di crittografia e così via, disponibili pubblicamente. Un modo per visualizzare i dettagli consiste nell'utilizzare un sito Web di terze parti, ad esempio Qualys SSL laboratori (www.ssllabs.com). Vengono riportati di seguito i collegamenti a pagine test automatizzato da Qualys che visualizzano le informazioni per i servizi seguenti:
- [Portale di Office 365](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype per le aziende (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype per le aziende (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Per Exchange Online Protection, gli URL variano in base a nomi tenant. Tuttavia, tutti i clienti possono testare Office 365 con **microsoft com.mail.protection.outlook.com**.
