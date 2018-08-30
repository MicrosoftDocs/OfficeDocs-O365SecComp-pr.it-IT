---
title: Controlli di isolamento di Office 365
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
description: 'Riepilogo: Una spiegazione dei controlli di isolamento in Office 365.'
ms.openlocfilehash: 3a5c06d0675a4503d9f5e5edd58535688fb9180a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531460"
---
# <a name="office-365-isolation-controls"></a>Controlli di isolamento di Office 365 

Microsoft può essere utilizzato in modo continuativo per verificare che l'architettura multi-tenant di Office 365 supporta protezione a livello aziendale, la riservatezza, privacy, l'integrità e disponibilità [standard](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons), nonché gli standard locali e internazionali. Data la scala e l'ambito dei servizi forniti da Microsoft, si potrebbe essere difficile ed economiche per gestire Office 365 se automatizzate significativi sono state necessarie. Servizi di Office 365 sono disponibili tramite più datacenter distribuita a livello globale, in modo altamente automatizzato, dove estremamente numero ridotto di operazioni datacenter richiede un tocco risorse umano e anche meno operazioni richiedono l'accesso al contenuto dei clienti. Staff supporta questi servizi e Datacenter utilizzando strumenti automatici e accesso remoto a protezione avanzata. Per alcune informazioni dettagliate su come servizi su larga scala vengono utilizzati in Office 365, vedere [dietro che aspetto in Office 365 per professionisti IT in background](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).

Office 365 è costituita da più servizi che forniscono funzionalità aziendali importanti e di collaborazione per l'intera esperienza di Office 365. Ognuno di questi servizi è progettato per essere autonomi e per l'integrazione tra loro. Office 365 ha i principi di un' [Architettura orientata ai servizi](https://msdn.microsoft.com/library/aa480021.aspx), in cui è definito come progettazione e sviluppo di software sotto forma di servizi interoperabili che forniscono funzionalità di business ben definito e [sicurezza operativa Controllo](http://www.microsoft.com/download/details.aspx?id=40872), un framework che incorpora le conoscenze acquisite tramite un'ampia gamma di funzionalità che sono univoche per Microsoft, tra cui Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)e approfondita consapevolezza di orizzontale le minacce alla sicurezza informatica.

Servizi di Office 365 interagiscono tra loro, ma è progettati e implementati in modo che può essere distribuiti e utilizzati come servizi autonomi reciprocamente indipendenti. Microsoft isola i diritti di dogana e le aree di responsabilità per Office 365 per ridurre le opportunità per non autorizzato o non intenzionale o improprio delle risorse dell'organizzazione. Team di Office 365 sono definiti i ruoli come parte di un meccanismo di controllo completo dell'accesso basato sui ruoli.

## <a name="customer-content-isolation"></a>Isolamento del contenuto dei clienti
Tutto il contenuto dei clienti che appartengono a un tenant è isolato da altro tenant e dai sistemi e operazioni di dati utilizzati per la gestione di Office 365. Sono state implementate più moduli di protezione in Office 365 per ridurre al minimo il rischio di compromissione di qualsiasi servizio di Office 365 applicazione o qualsiasi acquisire di accesso non autorizzato alle informazioni del tenant o nello stesso sistema di Office 365. Per informazioni su come viene implementata la logica isolamento dei dati relativi al tenant in Office 365 Microsoft, vedere [Isolamento Tenant Office 365](office-365-tenant-isolation-overview.md).
