---
title: Controlli di isolamento di Office 365
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
description: "Riepilogo: Descrizione dei controlli di isolamento all'interno di Office 365."
ms.openlocfilehash: 6f5980ae25b412cbbccc20ec3b5726b5a4ceed86
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520686"
---
# <a name="office-365-isolation-controls"></a>Controlli di isolamento di Office 365 

Microsoft continua a funzionare per garantire che l'architettura multi-tenant di Office 365 supporti la sicurezza a livello aziendale, la riservatezza, la privacy, l'integrità, [gli standard](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)locali, internazionali e di disponibilità. La scalabilità e l'ambito dei servizi forniti da Microsoft rendono difficile e non economico la gestione di Office 365 con una significativa interazione umana. I servizi di Office 365 vengono forniti tramite più data center distribuiti a livello globale, ognuno estremamente automatizzato con poche operazioni che richiedono un contatto umano o qualsiasi accesso al contenuto del cliente. Il personale supporta questi servizi e Data Center utilizzando strumenti automatici e l'accesso remoto estremamente sicuro. Per alcuni dettagli sulla modalità di gestione dei servizi su larga scala in Office 365, vedere [a behind the scenes look to office 365 for IT Pros](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).

Office 365 è costituito da più servizi che forniscono importanti funzionalità aziendali e contribuiscono all'intera esperienza di Office 365. Ognuno di questi servizi è autonomo e ha lo scopo di integrarsi tra loro.

Office 365 è stato creato con i principi seguenti:

 - ** [Architettura orientata ai servizi](https://msdn.microsoft.com/library/aa480021.aspx):** la progettazione e lo sviluppo di software in forma di servizi interoperabili che forniscono funzionalità aziendali ben definite.
 - **[Garanzia di sicurezza operativa](http://www.microsoft.com/download/details.aspx?id=40872):** un Framework che incorpora le conoscenze acquisite tramite diverse funzionalità esclusive di Microsoft, tra cui il ciclo di vita [dello sviluppo della sicurezza](https://www.microsoft.com/sdl/default.aspx)Microsoft, la sicurezza di Microsoft [ Response Center](https://technet.microsoft.com/library/dn440717.aspx)e consapevolezza profonda del panorama delle minacce di Cybersecurity.

I servizi di Office 365 interagiscono tra loro, ma sono stati disegnati e implementati in modo che possano essere distribuiti e gestiti come servizi autonomi, indipendenti l'uno dall'altro. Microsoft segrega i compiti e le aree di responsabilità di Office 365 per ridurre le opportunità di modifiche non autorizzate o involontarie o di uso improprio dei cespiti dell'organizzazione. I team di Office 365 dispongono di ruoli definiti come parte di un meccanismo completo di controllo dell'accesso basato sui ruoli.

## <a name="customer-content-isolation"></a>Isolamento del contenuto del cliente

Tutto il contenuto del cliente in un tenant è isolato da altri tenant e dai dati relativi a operazioni e sistemi utilizzati nella gestione di Office 365. Più forme di protezione vengono implementate in Office 365 per ridurre al minimo il rischio di un compromesso di qualsiasi servizio o applicazione di Office 365. Anche più forme di protezione impediscono l'accesso non autorizzato alle informazioni dei tenant o del sistema Office 365 stesso.

Per informazioni su come Microsoft implementa l'isolamento logico dei dati del tenant all'interno di Office 365, vedere [tenant isolation in office 365](office-365-tenant-isolation-overview.md).
