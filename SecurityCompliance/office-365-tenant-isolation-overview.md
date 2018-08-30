---
title: Isolamento dei tenant in Office 365
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
description: Riepilogo delle modalità Microsoft impone l'isolamento dei tenant di Office 365.
ms.openlocfilehash: fcf66ee65c2a4cfdf73ae0eac77f54bd555d059d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530863"
---
# <a name="tenant-isolation-in-office-365"></a>Isolamento dei tenant in Office 365

Uno dei principali vantaggi del cloud computing è concetto di un'infrastruttura condivisa, più comune tra più clienti numerose contemporaneamente, con una conseguente economie di scala. Questo concetto viene chiamato *multi-tenancy*. Microsoft si impegna continuamente che le architetture multi-tenant ai servizi cloud supportano gli standard di protezione, riservatezza, privacy, l'integrità e disponibilità di livello aziendale.

Servizi cloud Microsoft basato sull'oggetto significativi investimenti ed esperienza raccolte dallo [Trustworthy Computing](https://www.microsoft.com/en-us/twc/default.aspx) e la [Sicurezza del ciclo di vita dello sviluppo](http://www.microsoft.com/security/sdl/default.aspx), sono stati progettati partendo dal presupposto che tutti i tenant sono potenzialmente dannoso a tutti altri tenant ed è stata implementata misure di protezione per impedire che le azioni di un tenant di modificare la sicurezza o servizio di un altro tenant o accesso al contenuto di un altro tenant.

Di seguito sono riportati i due obiettivi principali del mantenimento isolamento tenant in un ambiente multi-tenant:
1.  Evitare di perdita di o accesso non autorizzato per il contenuto dei clienti tra tenant; e
2.  Impedire che le azioni di un tenant influire negativamente sul servizio per un altro tenant

Più moduli di protezione apportati in Office 365 per evitare che i clienti da servizi di Office 365 compromettere o applicazioni o accesso non autorizzato a informazioni di altri tenant o il sistema di Office 365, tra cui:
- Isolamento logico del contenuto dei clienti all'interno di ogni tenant per i servizi di Office 365 è ottenuta tramite l'autorizzazione di Azure Active Directory e il controllo dell'accesso basato sui ruoli.
- SharePoint Online offre meccanismi di isolamento dei dati a livello di archiviazione.
- Protezione fisica rigorosa, screening in background e una strategia di crittografia stratificata vengono utilizzate da Microsoft per proteggere la riservatezza e l'integrità del contenuto dei clienti. Tutti i centri dati di Office 365 hanno biometrica accedere a controlli, con più che richiedono stampa palmare per ottenere l'accesso fisico. Inoltre, i dipendenti Microsoft basati su US devono per completare correttamente un controllo standard in background come parte del processo di assunzione. Per ulteriori informazioni sui controlli utilizzati per l'accesso amministrativo in Office 365, vedere [Controlli di accesso amministrativo di Office 365](office-365-administrative-access-controls-overview.md).
- Office 365 utilizza tecnologie lato del servizio che crittografa il contenuto dei clienti statici e in transito, tra cui BitLocker, per ogni file per la crittografia, Transport Layer Security (TLS) e Internet Protocol Security (IPsec). Per informazioni dettagliate sulla crittografia in Office 365, vedere [Le tecnologie di crittografia dei dati in Office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).

Protezioni sopra elencate forniscono insieme dei controlli di isolamento logico affidabile che forniscono protezione rischio e attenuazione equivalenti a quelle fornite da utilizzare solo l'isolamento fisico.

## <a name="related-links"></a>Collegamenti correlati
- [Isolamento e controllo di accesso in Azure Active Directory](office-365-isolation-in-azure-active-directory.md)
- [Isolamento del tenant in Office Graph e Delve](office-365-isolation-in-graph-and-delve.md)
- [Ricerca dell’isolamento del tenant in Office 365](office-365-isolation-in-office-365-search.md)
- [Isolamento del tenant in Office 365 Video](office-365-isolation-in-office-365-video.md)
- [Limiti della risorsa](office-365-resource-limits.md)
- [Monitoraggio e verifica dei limiti del tenant](office-365-monitoring-and-testing.md)
- [Isolamento e controllo di accesso in Office 365](office-365-isolation-in-office-365.md)