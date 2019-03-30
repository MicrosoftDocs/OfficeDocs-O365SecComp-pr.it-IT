---
title: Controlli di isolamento di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
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
ms.openlocfilehash: 46514a33ad9eff6e2acc71a51b073a79b051c521
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004173"
---
# <a name="office-365-isolation-controls"></a>Controlli di isolamento di Office 365 

Microsoft continua a funzionare per garantire che l'architettura multi-tenant di Office 365 supporti la sicurezza a livello aziendale, la riservatezza, la privacy, l'integrità e [gli standard](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)di disponibilità, nonché gli standard locali e internazionali. Data la scalabilità e l'ambito dei servizi forniti da Microsoft, sarebbe difficile e non economico gestire Office 365 se fosse necessaria una significativa interazione umana. I servizi di Office 365 vengono forniti tramite più centri dati distribuiti globalmente, in modo estremamente automatizzato, in cui le operazioni di datacenter estremamente poche richiedono un contatto umano e anche meno operazioni richiedono l'accesso al contenuto del cliente. Il personale supporta questi servizi e i datacenter utilizzando strumenti automatici e l'accesso remoto estremamente sicuro. Per alcuni dettagli sulla modalità di gestione dei servizi su larga scala in Office 365, vedere [a behind the scenes look to office 365 for IT Pros](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).

Office 365 è costituito da più servizi che forniscono importanti funzionalità aziendali e contribuiscono all'intera esperienza di Office 365. Ognuno di questi servizi ha lo scopo di essere autonomo e di integrarsi tra loro. Office 365 è stato progettato con i principi di un' [architettura orientata ai servizi](https://msdn.microsoft.com/library/aa480021.aspx), che è definita come la progettazione e lo sviluppo di software in forma di servizi interoperabili che forniscono funzionalità aziendali ben definite e [sicurezza operativa Assurance](http://www.microsoft.com/download/details.aspx?id=40872), un Framework che incorpora le conoscenze acquisite tramite una serie di funzionalità esclusive di Microsoft, tra cui il ciclo di vita [dello sviluppo della sicurezza](https://www.microsoft.com/sdl/default.aspx)Microsoft, [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)e Deep consapevolezza del panorama delle minacce di Cybersecurity.

I servizi di Office 365 interagiscono tra loro, ma sono stati disegnati e implementati in modo che possano essere distribuiti e gestiti come servizi autonomi, indipendentemente l'uno dall'altro. Microsoft segrega i compiti e le aree di responsabilità di Office 365 per ridurre le opportunità di modifiche non autorizzate o involontarie o di uso improprio dei cespiti dell'organizzazione. I team di Office 365 dispongono di ruoli definiti come parte di un meccanismo completo di controllo dell'accesso basato sui ruoli.

## <a name="customer-content-isolation"></a>Isolamento del contenuto del cliente
Tutto il contenuto del cliente che appartiene a un tenant è isolato da altri tenant e dai dati operativi e dei sistemi utilizzati nella gestione di Office 365. Più forme di protezione sono state implementate in Office 365 per ridurre al minimo il rischio di un compromesso di qualsiasi servizio o applicazione di Office 365 o qualsiasi acquisizione di accesso non autorizzato alle informazioni dei tenant o del sistema Office 365 stesso. Per informazioni su come Microsoft implementa l'isolamento logico dei dati del tenant all'interno di Office 365, vedere [tenant isolation in office 365](office-365-tenant-isolation-overview.md).
