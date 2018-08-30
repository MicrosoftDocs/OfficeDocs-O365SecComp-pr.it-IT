---
title: Controllo e creazione di report in Office 365
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
description: Panoramica del controllo e la funzionalità in Office 365, nonché del servizio controllo di reporting.
ms.openlocfilehash: 055a24523260bf14220d5436dcdd010f31f5d8cd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531078"
---
# <a name="auditing-and-reporting-in-office-365"></a>Controllo e creazione di report in Office 365

## <a name="introduction"></a>Introduzione
Servizi cloud Microsoft include diverse controllo e la funzionalità che i clienti possono utilizzare per tenere traccia delle attività amministrative entro i tenant, ad esempio le modifiche apportate alla loro Exchange Online e impostazioni di configurazione di SharePoint Online tenant e utente di reporting e le modifiche apportate dagli utenti ai documenti e altri elementi. I clienti possono utilizzare le informazioni di controllo e rapporti disponibili in dei servizi cloud per gestire l'esperienza utente in modo più efficace, ridurre i rischi e adempiere agli obblighi di conformità.

## <a name="office-365-security--compliance-center"></a>Centro sicurezza e conformità di Office 365
[Protezione di Office 365 e centro conformità](https://support.office.com/article/Go-to-the-Office-365-Security-Compliance-Center-7e696a40-b86b-4a20-afcc-559218b7b1b8) è un unico punto portale per la protezione dei dati in Office 365 e include molti controllo e la funzionalità di reporting. È l'evoluzione del centro conformità di Office 365. Il centro di conformità e sicurezza è progettato per organizzazioni che dispongono di data protection o esigenze di conformità o che desidera controllare l'attività di utenti e amministratori. È possibile utilizzare il centro di conformità e sicurezza per gestire la conformità per tutti i dati dell'organizzazione Office 365. È possibile accedere la sicurezza e centro conformità al [http://protection.office.com](http://protection.office.com/) utilizzando l'account di amministrazione di Office 365.

Il centro di conformità e sicurezza include i riquadri di spostamento che consentono di accedere a diverse funzionalità:
- **Alerts** - consente di gestire gli avvisi, visualizzare gli avvisi relativi alla protezione e gestire gli avvisi avanzati utilizzando la [Gestione della protezione avanzata](https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475). 
- **Le autorizzazioni** - consente di [assegnare le autorizzazioni](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76) , ad esempio l'amministratore di conformità, eDiscovery Manager e gli altri utenti all'interno dell'organizzazione in modo che possano eseguire le attività nel centro conformità sicurezza. È possibile assegnare le autorizzazioni per la maggior parte delle funzionalità nel centro conformità protezione, ma le altre autorizzazioni devono essere configurate utilizzando l'interfaccia di amministrazione di Exchange e l'interfaccia di amministrazione di SharePoint.
- **Gestione delle minacce** - consente di creare e applicare criteri di gestione di dispositivi utilizzando la [Gestione dei dispositivi mobili di Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)per impostare i criteri di [Prevenzione della perdita di dati](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP) per l'organizzazione, configurare la posta elettronica, filtro anti-malware, DomainKeys identificato posta (DKIM), gli allegati sicuri, collegamenti sicuri e le autorizzazioni dell'app.
- **Governance dati** - consente di [importare dati di SharePoint da altri sistemi a Office 365 o messaggio di posta elettronica](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84), [configurare cassette postali di archiviazione](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)e impostare [i criteri di conservazione](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c) per la posta elettronica e altri contenuti all'interno dell'organizzazione.
- **Ricerca e indagini** - sono disponibili strumenti di [ricerca di contenuti](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a), [log di controllo](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c), quarantena e [gestione dei casi eDiscovery](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) per visualizzare rapidamente le attività in Exchange Online le cassette postali, gruppi e le cartelle pubbliche, SharePoint In linea e OneDrive for Business.
- **Relazioni** - consente di accedere rapidamente ai [rapporti](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a) per SharePoint Online, OneDrive for Business, Exchange Online e Azure Active Directory.
- **Controllo del servizio** - vengono fornite informazioni sulle modalità con cui Microsoft gestisce sicurezza, la privacy e la conformità alle norme globali per Office 365, Azure, Microsoft Dynamics CRM Online, Microsoft Intune e altri servizi cloud. Include inoltre l'accesso a terze parti ISO, SOC e altri report di controllo, nonché controllati i controlli, che fornisce informazioni dettagliate sui vari controlli che sono stati testati e verificati dai revisori di terze parti di Office 365.

## <a name="service-assurance"></a>Controllo del servizio
Molti dei nostri clienti in settori regolamentati sono soggetti a requisiti di conformità estesa. Per eseguire i propri le valutazioni dei rischi, i clienti devono spesso informazioni dettagliate sulla gestione di Office 365 la protezione e privacy dei dati. Microsoft si impegna per la protezione e privacy dei dati dei clienti nei relativi servizi cloud e per ottenere la relazione di trust clienti fornendo una visualizzazione trasparente relativi alle operazioni e accesso semplificato ai rapporti di conformità indipendente e valutazioni.

Servizio Assurance offre trasparenza operazioni e le informazioni sulla modalità con cui Microsoft gestisce la sicurezza, privacy e la conformità dei dati relativi ai clienti in Office 365. Include report di controllo di terze parti con una raccolta di white paper, domande frequenti e altro materiale su argomenti relativi a Office 365, ad esempio la crittografia dei dati, resilienza dei dati, gestire la sicurezza degli eventi imprevisti e altro ancora. I clienti possono utilizzare queste informazioni per eseguire i propri le valutazioni dei rischi normativi. Responsabili della conformità possono assegnare il ruolo "Servizio Assurance User" per fornire agli utenti l'accesso al servizio di controllo. L'amministratore tenant può fornire gli utenti esterni, ad esempio revisori indipendenti, accesso alle informazioni personali nel dashboard di controllo del servizio tramite il [Portale di attendibilità servizi di Microsoft Cloud](http://aka.ms/STP) (STP). Per ulteriori informazioni su come accedere il STP, visitare il sito [introduttive al portale di servizi attendibile per Office 365 per aziende, Azure che Dynamics CRM Online per le sottoscrizioni](http://aka.ms/STPHelp).

## <a name="onedrive-for-business-admin-center"></a>OneDrive for Business Admin Center
La nuova interfaccia di amministrazione di Microsoft OneDrive consente rapidamente e facilmente gestire OneDrive dell'organizzazione per le impostazioni di Business in un unico sito. Per utilizzare l'interfaccia di amministrazione di OneDrive, è necessario consentire l'accesso a onedrive.com. È inoltre necessario essere un amministratore globale dell'organizzazione o un amministratore personalizzato con il ruolo di amministratore di SharePoint. Accedere a OneDrive for anteprima di Business admin center in [https://admin.onedrive.com](https://admin.onedrive.com/).

Caratteristiche principali includono un'area di conformità che fornisce agli amministratori con collegamenti per la protezione di Office 365 e centro conformità per scenari di base come la ricerca nel Registro di controllo, working with DLP, conservazione, eDiscovery e avvisi.

## <a name="related-links"></a>Collegamenti correlati
- [Funzionalità di ricerca e di eDiscovery](office-365-ediscovery-and-search-features.md)
- [Funzionalità di reporting di Office 365](office-365-reporting-features.md)
- [API Office 365 Management Activity](office-365-management-activity-api.md)
- [Migrazioni delle cassette postali di Office 365](office-365-mailbox-migrations.md)
- [La registrazione interna per Office 365 Engineering](office-365-internal-logging.md)