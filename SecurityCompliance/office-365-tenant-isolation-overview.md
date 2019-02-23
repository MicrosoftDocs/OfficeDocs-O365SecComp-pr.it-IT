---
title: Isolamento del tenant in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Un riepilogo del modo in cui Microsoft impone l'isolamento tenant per Office 365.
ms.openlocfilehash: dceff3b73ac01d3e0422a190d450ee28f7fdfb27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220276"
---
# <a name="tenant-isolation-in-office-365"></a>Isolamento del tenant in Office 365

Uno dei vantaggi principali del cloud computing è il concetto di un'infrastruttura comune condivisa tra i numerosi clienti contemporaneamente, che porta a economie di scala. Questo concetto è denominato *multi-tenant*. Microsoft funziona continuamente per garantire che le architetture multi-tenant dei servizi cloud supportino la sicurezza a livello aziendale, la riservatezza, la privacy, l'integrità e gli standard di disponibilità.

In base ai significativi investimenti e all'esperienza ottenuti dall' [elaborazione affidabile](https://www.microsoft.com/en-us/twc/default.aspx) e dal ciclo di vita [dello sviluppo della sicurezza](http://www.microsoft.com/security/sdl/default.aspx), i servizi cloud Microsoft sono stati concepiti con l'assunto che tutti i tenant siano potenzialmente ostili a tutti altri tenant e sono state implementate misure di sicurezza che impediscono alle azioni di un tenant di influenzare la sicurezza o il servizio di un altro tenant o di accedere al contenuto di un altro tenant.

I due obiettivi principali per mantenere l'isolamento del tenant in un ambiente multi-tenant sono:
1.  Impedire la fuoriuscita o l'accesso non autorizzato al contenuto dei clienti tra i tenant; e
2.  Impedire alle azioni di un tenant di influenzare negativamente il servizio per un altro tenant

Sono state implementate più forme di protezione in Office 365 per impedire ai clienti di compromettere i servizi o le applicazioni di Office 365 o di ottenere un accesso non autorizzato alle informazioni di altri tenant o del sistema Office 365 stesso, tra cui:
- L'isolamento logico del contenuto dei clienti all'interno di ogni tenant per i servizi di Office 365 viene ottenuto tramite l'autorizzazione di Azure Active Directory e il controllo di accesso basato sui ruoli.
- SharePoint Online fornisce meccanismi di isolamento dei dati a livello di archiviazione.
- Microsoft utilizza la sicurezza fisica rigorosa, lo screening di sfondo e una strategia di crittografia a più livelli per proteggere la riservatezza e l'integrità del contenuto dei clienti. Tutti i datacenter di Office 365 dispongono di controlli di accesso biometrici, con la maggior parte delle stampe Palm che richiedono l'accesso fisico. Inoltre, tutti i dipendenti Microsoft basati su Stati Uniti sono necessari per completare correttamente un controllo di sfondo standard come parte del processo di assunzione. Per ulteriori informazioni sui controlli utilizzati per l'accesso amministrativo in Office 365, vedere [office 365 Administrative Access Controls](office-365-administrative-access-controls-overview.md).
- Office 365 utilizza tecnologie sul fianco del servizio che crittografano il contenuto dei clienti a riposo e in transito, tra cui BitLocker, crittografia per file, TLS (Transport Layer Security) e IPsec (Internet Protocol Security). Per informazioni specifiche sulla crittografia in Office 365, vedere [tecnologie di crittografia dei dati in office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).

Insieme, le protezioni elencate di seguito offrono robusti controlli di isolamento logico che forniscono protezione dalle minacce e una mitigazione equivalente a quella fornita solo dall'isolamento fisico.

## <a name="related-links"></a>Collegamenti correlati
- [Isolamento e controllo di accesso in Azure Active Directory](office-365-isolation-in-azure-active-directory.md)
- [Isolamento del tenant in Office Graph e Delve](office-365-isolation-in-graph-and-delve.md)
- [Isolamento del tenant per la funzionalità di ricerca di Office 365](office-365-isolation-in-office-365-search.md)
- [Isolamento del tenant in Office 365 Video](office-365-isolation-in-office-365-video.md)
- [Limiti della risorsa](office-365-resource-limits.md)
- [Monitoraggio e verifica dei limiti del tenant](office-365-monitoring-and-testing.md)
- [Isolamento e controllo di accesso in Office 365](office-365-isolation-in-office-365.md)