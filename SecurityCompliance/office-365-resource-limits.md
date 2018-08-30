---
title: Limiti delle risorse di Office 365
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
description: 'Riepilogo: Informazioni sulle risorse i limiti per le diverse applicazioni in Office 365.'
ms.openlocfilehash: a2e7ef42f9bf224363f3b10a5e450d6127f11585
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531465"
---
# <a name="resource-limits"></a>Limiti della risorsa

Limiti delle risorse vengono applicati tramite le quote (limiti) e la limitazione. Utilizzano entrambi i singoli servizi di Office 365 e Azure Active Directory. Limiti sono specifiche del servizio e in tempo reale con l'aggiunta di nuove funzionalità. Per ulteriori informazioni sui limiti correnti per i diversi servizi, vedere gli argomenti seguenti:
- [Azure Active Directory service limiti e limitazioni](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [Limiti Exchange Online Limits](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [Limiti Exchange Online Protection](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [Limiti e limitazioni del software SharePoint Online](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Skype i limiti aziendali](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [Limiti di velocità e API REST di Yammer](https://developer.yammer.com/docs/rest-api-rate-limits)
- [Limiti di dimensione file in oscillazione](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

Oltre a questi limiti vengono utilizzati più meccanismi di limitazione in Office 365 e Azure Active Directory. Limitazione delle richieste all'interno del servizio è particolarmente importante, dal momento che le risorse di rete nei Data Center di Microsoft ottimizzate per l'ampia gamma di clienti che utilizzano i servizi. Meccanismi di limitazione includono:
- Azure Active Directory e Office 365 caratteristica a livello utente limitazione cui limitare il numero di transazioni o chiamate simultanee, tramite script o codice, che possono essere eseguite da un singolo utente.
- Predefinito PowerShell criterio di limitazione viene assegnato a ogni tenant durante la creazione del tenant. Queste impostazioni influiscono su altri elementi, ad esempio il numero massimo di sessioni simultanee di PowerShell che può essere aperto da un unico amministratore.
- Ogni cliente Exchange Online è un criterio di servizi Web Exchange (EWS) predefinito che è ottimizzato per le operazioni dei client servizi Web Exchange e di limitazione che si applica a tutti i client di Outlook.
