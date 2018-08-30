---
title: Conservazione dei dati, eliminazione e distruzione in Office 365
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
description: Panoramica di criteri di Microsoft per Office 365 sulla conservazione dei dati, eliminazione e distruzione.
ms.openlocfilehash: 4d952058df8d0efb664f23e5495796fdb9e006f2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530559"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Conservazione dei dati, eliminazione e distruzione in Office 365

## <a name="introduction"></a>Introduzione
Microsoft ha un criterio di gestione dati Standard per Office 365 che specifica quanto tempo i dati dei clienti verranno mantenuti dopo l'eliminazione. In generale, in Office 365, esistono due scenari in cui viene eliminati i dati dei clienti:
- **Attiva l'eliminazione** - un utente consente di eliminare dati o dati privati a un utente viene eliminati dopo che l'utente viene eliminato dall'amministratore di un tenant attivo.
- **Eliminazione passiva** - sottoscrizione tenant termina.

Criteri di Data gestione Standard di Microsoft per Office 365 specificano quanto tempo i dati verranno mantenuti in ognuno di questi scenari. Nelle sezioni seguenti vengono descritte le categorie di dati (basati Office 365 risorse classificazione Standard di Microsoft) e i periodi di conservazione per gli scenari di eliminazione attive e passive.

## <a name="active-deletion-retention"></a>Conservazione eliminazione attivo

| Categoria di dati | Mantenere almeno | Mantenere al massimo |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| Dati di controllo di accesso | N/D | N/D |
| Contenuto dei clienti | 7 giorni | 30 giorni |
| Informazioni personali dell'utente finale | 90 giorni | 180 giorni |
| Dati relativi agli account | 1 anno | 3 anni |
| Organizzazione informazioni personali | 90 giorni | 180 giorni |
| Metadati di sistema | Vedere i registri di protezione | Vedere i registri di protezione |
| Registri di sicurezza | Min 1 anno | Max 1 anno |
| Registri archiviazione di Exchange Online | Min 3 anni | Max 3 anni |

## <a name="passive-deletion-retention"></a>Conservazione eliminazione passiva

| Categoria di dati | Mantenere almeno | Mantenere al massimo |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| Dati di controllo di accesso | 90 giorni (per il ripristino di contenuto) | 180 giorni (per il ripristino di contenuto) |
| Contenuto dei clienti | 90 giorni (funzione limited account) | 180 giorni |
| Informazioni personali dell'utente finale | 90 giorni | 180 giorni |
| Dati relativi agli account | 1 anno | 3 anni |
| Organizzazione informazioni personali | 90 giorni | 180 giorni |
| Metadati di sistema | Vedere i registri di protezione | Vedere i registri di protezione |
| Registri di sicurezza | Min 1 anno | Max 1 anno |
| Registri archiviazione di Exchange Online | Min 3 anni | Max 3 anni |

## <a name="subscription-rentention"></a>Rentention sottoscrizione

Il contenuto dei clienti è definito come il contenuto delle cassette postali di Exchange Online (body, voci del calendario e il contenuto degli allegati di posta elettronica, di posta elettronica e, se applicabile, Skype per il contenuto di Business), contenuto del sito SharePoint Online e i file archiviati all'interno dei siti e i file caricati in OneDrive per Business o Skype per le aziende.

AT ininterrotta durante il termine di una sottoscrizione di un sottoscrittore può accedere ed estrarre i dati dei clienti archiviati in Office 365. Ad eccezione di valutazione gratuita e servizi di LinkedIn, Microsoft consente di conservare dati archiviati in Office 365 in un account limitato funzione per 90 giorni dopo la scadenza o cessazione della sottoscrizione per attivare il server di sottoscrizione per estrarre i dati relativi ai clienti. (Nel caso di una versione di valutazione gratuita quando scade la versione di valutazione, si sposta in un periodo di prova, avendo 30 giorni (per la maggior parte delle versioni di valutazione, nella maggior parte dei paesi,) acquistare Office 365. Se si decide di non acquistare Office 365, è possibile consentire la scadenza di prova o annullarla. Subito dopo il periodo di prova di 30 giorni, le informazioni sull'account di prova e dati viene definitivamente cancellata.)

Al termine del periodo di conservazione di 90 giorni, consente di disabilitare l'account Microsoft e consente di eliminare i dati dei clienti. Non più di 180 giorni dopo la scadenza o alla chiusura di una sottoscrizione a Office 365, Microsoft sarà disabilitare l'account ed eliminare tutti i dati relativi ai clienti dall'account. Una volta trascorso il periodo di conservazione massima per tutti i dati, i dati vengono visualizzati sul mercato irreversibili.

Microsoft offre anche un criterio Standard di gestione dei dati in grado di risolvere il riciclo e l'eliminazione del server non riuscito o ritirare e unità disco. Prima di utilizzare nuovamente le unità disco in Office 365, Microsoft esegue un processo il filtraggio fisici che sia compatibile con SP NIST 800 88. Unità disco che non possono essere riutilizzate eliminate utilizzando un processo di eliminazione fisica che viene eseguito sul posto all'interno del datacenter che contiene i dischi in corso l'eliminazione. Queste procedure vengono eseguite dall'infrastruttura Microsoft Cloud e operazioni (MCIO). Per ulteriori informazioni, vedere il MCIO report in [Anteprima di attendibilità del servizio](https://aka.ms/STP)di controllo.

## <a name="expedited-deletion"></a>Eliminazione accelerata
AT ininterrotta durante il termine di una sottoscrizione di un sottoscrittore può contattare richiesta expedited sottoscrizione deprovisioning e supporto di Microsoft. In questo processo, tutti i dati utente, ad esempio dati di SharePoint in linea, Exchange Online che potrebbero essere in attesa o archiviati nelle cassette postali inattive, viene eliminati tre giorni dopo che l'amministratore dovrà immettere il codice del blocco fornito da Microsoft. Per ulteriori informazioni su deprovisioning accelerate, vedere [annullare Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).

## <a name="related-links"></a>Collegamenti correlati
- [Eliminazione dei dati di Exchange Online](/office365/enterprise/office-365-exchange-online-data-deletion)
- [Eliminazione dei dati di SharePoint Online](/office365/enterprise/office-365-sharepoint-online-data-deletion)
- [Eliminazione dei dati di Skype for Business](/office365/enterprise/office-365-skype-data-deletion)
- [Non modificabilità in Office 365](/office365/enterprise/office-365-data-immutability)
- [Distruzione dei dati](/office365/enterprise/office-365-data-destruction)