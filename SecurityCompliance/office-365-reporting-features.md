---
title: Funzionalità di creazione di report di Office 365
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
- M365-analytics
description: Una spiegazione delle funzionalità di Reporting all'interno di Office 365.
ms.openlocfilehash: 150928ccfb99da8b762cf5d5b99bf152a91949fa
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262398"
---
# <a name="office-365-reporting-features"></a>Funzionalità di creazione di report di Office 365 

## <a name="introduction"></a>Introduzione
La caratteristica rapporti di Office 365 offre una vasta gamma di report di controllo per Azure Active Directory (AD), Exchange Online, gestione dei dispositivi, revisione di supervisione e prevenzione della perdita di dati (DLP). Questi sono diversi e separati dai rapporti attività di Office 365.

## <a name="office-365-reports-dashboard"></a>Dashboard di report di Office 365
Il dashboard report nell'anteprima dell'interfaccia di amministrazione di Microsoft 365 Visualizza l'attività di utilizzo in Office 365. Gli amministratori globali di Office 365 o un amministratore di Exchange Online, SharePoint Online o Skype for business possono ottenere informazioni dettagliate sull'utilizzo del servizio. I report possono fornire informazioni dettagliate, ad esempio il numero di utenti che utilizzano un particolare servizio di Office 365, il numero di utenti che hanno attivato Office Professional Plus e la quantità di posta che scorre nell'organizzazione. I report sono disponibili per gli ultimi 7, 30, 90 e 180 giorni.

Sono disponibili i report seguenti:
- [Report attività di posta elettronica](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Report sulle attivazioni di Microsoft Office](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [Report sull'utilizzo del sito di SharePoint Online](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [Report sull'utilizzo di OneDrive for business](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Report attività di Yammer](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Report attività in Skype for business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Report attività peer-to-peer di Skype for business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Report organizzatore di conferenze di Skype for business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Report attività partecipante di conferenze in Skype for business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

Per ulteriori informazioni, vedere [report attività nell'interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).


## <a name="azure-active-directory-reports"></a>Report di Azure Active Directory
Office 365 utilizza Azure AD per l'autenticazione e la gestione delle identità. Gli amministratori di Office 365 possono utilizzare i report generati da Azure per cercare attività inusuali e accesso non autorizzato ai dati. È possibile utilizzare i report di accesso e utilizzo in Azure AD per ottenere visibilità nell'integrità e sicurezza della directory dell'organizzazione. Con queste informazioni, un amministratore può determinare meglio dove possono essere i possibili rischi di sicurezza in modo che possano pianificare adeguatamente per attenuare tali rischi.

I report di Azure AD possono essere esportati in Microsoft Excel e correlati ad altri dati provenienti da Office 365, ad esempio i risultati di una ricerca nel registro di controllo, per fornire informazioni sulle attività di accesso, autenticazione e livello di applicazione. I report sull'utilizzo delle risorse e delle anomalie avanzate sono disponibili quando Azure AD Premium è abilitato. Questi report avanzati contribuiscono a migliorare la posizione di sicurezza di un'organizzazione e aiutano le organizzazioni a rispondere a potenziali minacce tramite l'utilizzo di analisi sull'accesso ai dispositivi e sull'uso di applicazioni. Per ulteriori informazioni, vedere [report di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/).

## <a name="exchange-online-audit-reports"></a>Rapporti di controllo di Exchange Online
I report di controllo di Exchange Online includono informazioni dettagliate sull'accesso alle cassette postali e le modifiche apportate dagli amministratori al tenant Exchange Online di un'organizzazione. Dopo aver abilitato il controllo delle cassette postali, è possibile utilizzare le attività descritte nella tabella seguente per eseguire i report ed esportare i log di controllo di Exchange Online.

>**Nota**: è necessario abilitare la registrazione di controllo delle cassette postali per ogni cassetta postale, in modo che gli eventi controllati vengano salvati nel log di controllo della cassetta postale. Se la registrazione di controllo delle cassette postali non è abilitata per una cassetta postale, gli eventi per tale cassetta postale non verranno salvati nel log di controllo e non verranno visualizzati nei report di controllo delle cassette Per ulteriori informazioni, vedere [abilitare il controllo delle cassette postali](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918).

| Attività | Descrizione |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Eseguire un rapporto di accesso non proprietario della cassetta postale](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | Visualizza l'elenco delle cassette postali a cui è stato effettuato l'accesso da parte di un utente diverso dal proprietario della cassetta postale. Il report contiene informazioni sull'utente che ha eseguito l'accesso alla cassetta postale, sulle azioni eseguite nella cassetta postale e sull'eventuale esito positivo. |
| [Esportare i log di controllo delle cassette postali](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | I registri di controllo delle cassette postali contengono informazioni sull'accesso e sulle azioni in una cassetta postale eseguita da un utente diverso dal proprietario della cassetta postale. Gli amministratori possono specificare le cassette postali insieme a un intervallo di date per generare i report. I registri vengono esportati in XML, allegati a un messaggio e inviati a utenti specifici, come determinato dall'amministratore. |
| [Esegui il rapporto di un gruppo di ruoli amministratore](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | Il gruppo di ruoli amministratore viene utilizzato per assegnare privilegi amministrativi agli utenti. Questi privilegi consentono agli utenti di eseguire attività amministrative come reimpostare le password, creare o modificare le cassette postali e assegnare privilegi di amministratore ad altri utenti. Il rapporto del gruppo di ruoli di amministratore Visualizza le modifiche apportate ai gruppi di ruoli, inclusa l'aggiunta o la rimozione dei membri. |
| [Visualizzare il registro di controllo dell'amministratore](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | Il rapporto del log di controllo dell'amministratore elenca tutte le funzioni di creazione, aggiornamento ed eliminazione eseguite dagli amministratori in Exchange Online. Le voci del log forniscono informazioni su quale cmdlet è stato eseguito, quali parametri sono stati utilizzati, chi ha eseguito il cmdlet e quali oggetti sono stati interessati. |
| [Ricerca e conservazione del contenuto delle cassette postali](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | Vengono fornite informazioni dettagliate sulle modifiche apportate alle impostazioni del blocco sul posto di eDiscovery o sul posto nelle cassette postali. |
| [Esportare il registro di controllo dell'amministratore](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | Il registro di controllo dell'amministratore registra specifiche azioni amministrative come la creazione, l'aggiornamento e l'eliminazione in Exchange Online. I risultati del log vengono esportati in XML e gli amministratori possono scegliere di inviare il registro a un gruppo di utenti. |
| [Esegui un rapporto sulla conservazione per controversia legale per singola cassetta postale](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | Vengono fornite informazioni dettagliate sulle modifiche alle impostazioni di conservazione per controversia legale nelle cassette postali. |
| [Visualizzare ed esportare il registro di controllo dell'amministratore esterno](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | Contiene informazioni dettagliate sulle azioni eseguite dagli amministratori esterni. Le voci forniscono informazioni su quale cmdlet è stato eseguito, quali parametri sono stati utilizzati e tutte le azioni che consentono di creare, modificare o eliminare oggetti in Exchange Online. |

## <a name="device-compliance-reports"></a>Rapporti di conformità del dispositivo
È possibile gestire e proteggere i dispositivi mobili quando sono connessi alla propria organizzazione di Office 365 utilizzando la gestione dei dispositivi mobili (MDM) di Office 365. I dispositivi mobili, come smartphone e tablet utilizzati per accedere a posta elettronica, calendario, contatti e documenti di lavoro, svolgono un ruolo importante nel garantire che i dipendenti siano in grado di funzionare in qualsiasi momento e da qualsiasi luogo. Di conseguenza, è importante proteggere le informazioni dell'organizzazione. È possibile utilizzare Office 365 MDM per impostare i criteri di sicurezza del dispositivo e le regole di accesso e per cancellare i dispositivi mobili se sono stati persi o rubati.

I report di conformità MDM offrono una panoramica dei criteri che sono stati configurati da un'organizzazione per proteggere i dispositivi mobili che accedono ai dati di Office 365. Il rapporto consente di filtrare i dispositivi in base allo stato di conformità, alle violazioni segnalate, ai dispositivi bloccati e al numero di dispositivi che sono stati cancellati a causa dei criteri di sicurezza. Per ulteriori informazioni, vedere [Panoramica della gestione dei dispositivi mobili per Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).

## <a name="data-loss-prevention"></a>Prevenzione della perdita di dati
I criteri DLP consentono di gestire la sicurezza e il flusso di informazioni in un'organizzazione. È possibile configurare i criteri per bloccare l'accesso al contenuto, crittografare i dati o informare gli utenti delle violazioni di criteri e criteri utilizzando suggerimenti per i criteri DLP in-Application. I report DLP forniscono informazioni sul numero di corrispondenze di criteri e regole, sostituzioni e falsi positivi.

È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per visualizzare informazioni sul numero di messaggi che vengono rilevati dai criteri DLP in formato grafico o tabella. In particolare, i criteri DLP corrispondono alla posta inviata e ricevuta e alle corrispondenze della regola DLP per la posta inviata e ricevuta. È inoltre possibile visualizzare il numero di corrispondenze, sostituzioni e falsi positivi per ogni criterio nelle ultime 24 ore utilizzando l'interfaccia di amministrazione di Exchange. Tuttavia, questi dati non sono disponibili in formato grafico. Se si scarica un report per l'utilizzo in Excel, è possibile visualizzare ulteriori dettagli, ad esempio l'utente che ha inviato il messaggio, il giorno in cui e quali criteri sono stati attivati. Per ulteriori informazioni, vedere [visualizzare i report sui rilevamenti dei criteri DLP](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx).

## <a name="auditing-in-yammer-enterprise"></a>Controllo in Yammer Enterprise
Yammer Enterprise fornisce agli amministratori la possibilità di esportare i dati delle attività degli utenti dalle rispettive reti Yammer tramite l' [API di esportazione dei dati di Yammer](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)o manualmente tramite la pagina di amministrazione di rete di Yammer. La possibilità di esportare i registri è riservata agli amministratori di rete in Yammer. (Tutti gli amministratori globali di Office 365 sono amministratori di rete di Yammer).

I dati seguenti possono essere esportati:

| Filename | Descrizione |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | Tutti gli utenti nuovi, in sospeso e sospesi nella rete |
| Messages.csv | Tutti i messaggi nella rete |
| File. csv (metadati) | Metadati quali nome file, URL API file, ID caricatore, caricato su, ecc. |
| File. csv (file originali) | File zip dei file originali che sono stati caricati dagli utenti in Yammer |
| Topics.csv | Argomenti creati sulla rete |
| Pages.csv | Pagine (note) create dagli utenti nella rete |
| Admins.csv | Tutti gli amministratori verificati sulla rete |
| Networks.csv | Tutte le reti esterne di Yammer |

*Tabella 3-file di dati di rete di Yammer disponibili per l'esportazione da parte dei clienti*

I dati dell'organizzazione di Yammer sono inoltre disponibili tramite i report attività di Office 365. Inoltre, Yammer sta lavorando attivamente all'esposizione di ulteriori registrazioni tramite l'API di attività di gestione di Office 365 e sulla possibilità di ragionare sui dati utilizzando Power BI. Per ulteriori informazioni su queste funzionalità, vedere la Guida di [orientamento di Office](https://fasttrack.microsoft.com/roadmap?filters=yammer) .
