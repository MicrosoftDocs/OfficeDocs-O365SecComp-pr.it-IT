---
title: Limiti relativi alle risorse di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "Riepilogo: informazioni sui limiti delle risorse per le diverse applicazioni all'interno di Office 365."
ms.openlocfilehash: d4315923ea1ab09e2e7651fb2fcaddb085871d4d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262408"
---
# <a name="resource-limits"></a>Limiti della risorsa

I limiti delle risorse vengono applicati utilizzando le quote (limiti) e la limitazione. Azure Active Directory e i singoli servizi di Office 365 utilizzano entrambi. I limiti sono specifici del servizio e cambiano nel tempo man mano che vengono aggiunte nuove funzionalità. Per informazioni dettagliate sui limiti correnti per i diversi servizi, vedere i seguenti argomenti:
- [Limiti e restrizioni dei servizi di Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [Limiti di Exchange Online](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [Limiti di Exchange Online Protection](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [Confini e limiti del software di SharePoint Online](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Limiti relativi a Skype for business](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [API REST di Yammer e limiti di velocità](https://developer.yammer.com/docs/rest-api-rate-limits)
- [Limiti relativi alle dimensioni dei file in Sway](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

Oltre a questi limiti, vengono utilizzati diversi meccanismi di limitazione in Azure Active Directory e Office 365. La limitazione all'interno del servizio è particolarmente importante, dato che le risorse di rete nei datacenter di Microsoft sono ottimizzate per il vasto insieme di clienti che utilizzano i servizi. I meccanismi di limitazione includono:
- Azure Active Directory e Office 365 dispongono di limitazione a livello di utente, che limitano il numero di transazioni o di chiamate simultanee (tramite script o codice) che possono essere eseguite da un singolo utente.
- Un criterio di limitazione predefinito di PowerShell viene assegnato a ogni tenant alla creazione del tenant. Queste impostazioni influiscono su altri elementi, ad esempio il numero massimo di sessioni di PowerShell simultanee che possono essere aperte da un singolo amministratore.
- Ogni cliente di Exchange Online ha un criterio di servizi Web Exchange (EWS) predefinito che è stato ottimizzato per le operazioni client EWS e la limitazione che si applica a tutti i client Outlook.
