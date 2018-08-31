---
title: Servizio di crittografia di Office 365
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
description: 'Riepilogo: Informazioni su resilienza dei dati in Microsoft Office 365.'
ms.openlocfilehash: 1273cd5556bf51dcdac9bbde1b3e8003ab818811
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530803"
---
# <a name="office-365-service-encryption"></a>Servizio di crittografia di Office 365

Oltre a utilizzare la crittografia a livello di volume, Exchange Online, Skype per Business, SharePoint Online e OneDrive for Business utilizzare servizio di crittografia per crittografare i dati dei clienti. Servizio di crittografia consente di due opzioni di gestione delle chiavi:
- Microsoft gestisce tutte le chiavi di crittografiche. (Questa opzione è attualmente disponibile in SharePoint Online, OneDrive for Business e Skype per le aziende. È attualmente nella Guida di orientamento per Exchange Online).
- I clienti sono disponibili chiavi radice utilizzare in combinazione con la crittografia del servizio e il cliente gestisce queste chiavi utilizzando Azure chiave archivio. Microsoft gestisce tutte le altre chiavi. Questa opzione viene chiamata chiave cliente ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for Business. (Precedentemente noto come crittografia avanzata con BYOK. Vedere [ottimizzazione trasparenza e controllo per i clienti di Office 365](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) per l'annuncio originale).

La crittografia del servizio offre più vantaggi. Ad esempio, se:
- Fornisce i diritti di caratteristiche di protezione e gestione su di protezione di crittografia avanzata.
- include l'opzione chiave cliente che consente ai servizi multi-tenant per la gestione delle chiavi per tenant.
- vengono fornite da separazione tra amministratori del sistema operativo Windows l'accesso ai dati dei clienti archiviate o elaborate dal sistema operativo.
- aumenta la capacità di Office 365 per soddisfare le esigenze dei clienti che hanno requisiti di conformità alla crittografia.

## <a name="customer-key"></a>Chiave cliente
Chiave cliente consente di generare il proprio mediante un modulo di sicurezza hardware locale o di Azure chiave cassaforte le chiavi di crittografia. Indipendentemente dal modo viene generata la chiave, i clienti utilizzano Azure chiave cassaforte per controllare e gestire le chiavi di crittografia utilizzate da Office 365. Dopo che le chiavi sono archiviate in Azure chiave cassaforte, possono essere assegnati a carichi di lavoro, ad esempio Exchange Online e SharePoint Online e consente di come la radice del keychain utilizzato per crittografare i dati delle cassette postali e i file. Uno dei vantaggi dell'utilizzo chiave cliente deve controllare la capacità di Microsoft di elaborazione dei dati dei clienti. Questa funzionalità è presente in modo che un cliente che si desidera rimuovere i dati da Office 365 (ad esempio, quando un cliente termina servizio con Microsoft o rimuove una parte di dati archiviati nel cloud) può farlo e utilizzare chiave cliente come controllo tecnico per assicurarsi che nessuno , tra cui Microsoft, possono accedere o elaborare i dati. Si tratta di addizione (e un complemento) alla funzionalità archivio protetto cliente che può essere utilizzata per controllare l'accesso ai dati personali da personale Microsoft.

Per informazioni su come configurare chiave cliente per Office 365 per Exchange Online, Skype per Business, SharePoint Online e OneDrive for Business, vedere [il controllo dei dati in Office 365 con chiave cliente](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). Per ulteriori informazioni, vedere la [Chiave di clienti per domande frequenti di Office 365](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)e [Gestione e controllo dei dati e consentono di soddisfare conformità devono con clienti chiave](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).
