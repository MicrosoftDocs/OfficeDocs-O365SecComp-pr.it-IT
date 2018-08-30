---
title: Funzionalità di reporting di Office 365
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
description: Spiegazione dei report di caratteristiche in Office 365.
ms.openlocfilehash: 5a448089de5d517b81551269416c4a6f91599725
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531387"
---
# <a name="office-365-reporting-features"></a>Funzionalità di reporting di Office 365 

## <a name="introduction"></a>Introduzione
La caratteristica di report in Office 365 offre diversi report di controllo per la gestione dei dispositivi, esaminare supervisione e prevenzione della perdita di dati (DLP) Azure Active Directory (AD), Exchange Online. Questi sono diversi dai rapporti sull'attività di Office 365.

## <a name="office-365-reports-dashboard"></a>Dashboard i report di Office 365
Il dashboard i report nel riquadro di anteprima di interfaccia di amministrazione di Office 365 consente di visualizzare attività di utilizzo in Office 365. Gli amministratori globali di Office 365, o un Exchange Online, SharePoint Online o Skype per l'amministratore aziendale, è possibile ottenere granulare comprendere l'utilizzo del servizio. Report possono fornire informazioni quali il numero di utenti che utilizzano un particolare servizio di Office 365, il numero di utenti che è stato attivato Office Professional Plus e la quantità posta viene trasferito all'interno dell'organizzazione. I report sono disponibili negli ultimi 7, 30, 90 e 180 giorni.

Sono disponibili i report seguenti:
- [Rapporto attività di posta elettronica](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Report di attivazioni di Microsoft Office](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [Report di utilizzo del sito di SharePoint Online](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [OneDrive per report sull'utilizzo di Business](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Rapporto attività Yammer](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype per rapporto attività aziendali](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Skype per rapporto attività aziendali Peer-to-Peer](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Skype per report organizzatore della conferenza aziendali](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Skype per rapporto attività aziendali partecipante alla conferenza](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

Per ulteriori informazioni, vedere [Rapporti attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).


## <a name="azure-active-directory-reports"></a>Rapporti di Azure Active Directory
Office 365 utilizza Azure Active Directory per l'autenticazione e la gestione delle identità. Gli amministratori di Office 365 è possono utilizzare i rapporti generati da Azure per cercare l'accesso non autorizzato ai propri dati e l'attività non comune. È possibile utilizzare i report di utilizzo e l'accesso di Azure Active Directory per ottenere visibilità l'integrità e la protezione della directory dell'organizzazione. Con questa informazione, un amministratore può determinare meglio in cui potrebbe essere possibile i rischi di sicurezza in modo da pianificare in modo adeguato per ridurre i rischi.

Rapporti di Azure Active Directory possono essere esportate in Microsoft Excel e correlate con altri dati da Office 365, ad esempio i risultati di una ricerca di log di controllo, per consentono di comprendere l'accesso, l'autenticazione e le attività a livello di applicazione. Report di utilizzo avanzate anomalia e le risorse sono disponibili quando è abilitata la Premium di Azure Active Directory. Queste avanzate report della Guida per migliorare le organizzazioni di condizioni generali e Guida di sicurezza di un'organizzazione può rispondere potenziali minacce sfruttare analitica sull'utilizzo di accesso e l'applicazione del dispositivo. Per ulteriori informazioni, vedere [creazione di report di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/).

## <a name="exchange-online-audit-reports"></a>Report di controllo in linea di Exchange
Report di controllo Exchange Online includono informazioni dettagliate sull'accesso alla cassetta postale e le modifiche apportate dagli amministratori tenant Exchange Online dell'organizzazione. Dopo aver abilitato il controllo delle cassette postali, è possibile utilizzare le attività nella tabella seguente per creare i rapporti ed esportare i registri di controllo Exchange Online.

>**Nota**: È necessario abilitare delle cassette postali registrazione di controllo per ciascuna cassetta postale in modo che gli eventi vengono salvati nel Registro di controllo per la cassetta postale. Se il controllo delle cassette postali non è attivata la registrazione per una cassetta postale, gli eventi relativi a tale cassetta postale non vengono salvati nel Registro di controllo e non vengono visualizzati nei rapporti di controllo delle cassette postali. Per ulteriori informazioni, vedere [abilitare il controllo delle cassette postali](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918).

| Attività | Descrizione |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Eseguire un rapporto di accesso non proprietario della cassetta postale](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | Visualizza l'elenco delle cassette postali accessibile da un diverso da quello del proprietario della cassetta postale. Il report contiene informazioni su chi ha accesso alla cassetta postale, le azioni hanno impiegato nella cassetta postale, e le azioni sono state completate. |
| [Esportare i log di controllo delle cassette postali](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | I registri di controllo delle cassette postali sono contenute informazioni su accesso e le azioni in una cassetta postale eseguita da un utente diverso da proprietario della cassetta postale. Gli amministratori possono specificare le cassette postali con un intervallo di date per generare report. I registri vengono esportati in formato XML, allegati a un messaggio e inviati a utenti specifici a determinati dall'amministratore. |
| [Eseguire un rapporto del gruppo di ruoli amministratore](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | Il gruppo di ruoli amministratore viene utilizzato per assegnare privilegi di amministratore agli utenti. Questi privilegi consentono agli utenti di eseguire attività amministrative, ad esempio reimpostare le password, creare o modificare le cassette postali e assegnare i privilegi di amministratore ad altri utenti. Il rapporto di gruppo di ruolo admin Mostra le modifiche ai gruppi di ruolo, tra cui l'aggiunta o rimozione di membri. |
| [Visualizzare il Registro di controllo dell'amministratore](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | Gli elenchi di report Registro di controllo amministrazione tutti creare, aggiornare ed eliminare le funzioni eseguite dagli amministratori in Exchange Online. Le voci del log vengono fornite informazioni su quali cmdlet è stato eseguito, sono stati utilizzati i parametri, che ha eseguito il cmdlet e gli oggetti sono stati interessati. |
| [Attesa e la ricerca del contenuto delle cassette postali](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | Sono inclusi i dettagli delle modifiche apportate alle impostazioni di conservazione In locale o In-Place eDiscovery per le cassette postali. |
| [Esportare il Registro di controllo dell'amministratore](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | I record del Registro di controllo amministrazione specifiche operazioni amministrative ad esempio la creano, aggiornamento ed eliminazione di Exchange Online. Vengono esportati i risultati dal registro in formato XML e gli amministratori possono scegliere di inviare questo registro a un insieme di utenti. |
| [Eseguire un rapporto di attesa di conservazione per controversia per cassetta postale](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | Vengono fornite informazioni dettagliate di qualsiasi modifica apportata alla conservazione per controversia legale le impostazioni di cassette postali. |
| [Visualizzare ed esportare log di controllo dell'amministratore esterno](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | Contiene informazioni dettagliate sulle azioni eseguite dagli amministratori esterni. Le voci vengono fornite informazioni su quali cmdlet è stata portata, sono stati utilizzati i parametri e le azioni che creare, modificare o eliminare gli oggetti in Exchange Online. |

## <a name="device-compliance-reports"></a>Rapporti di conformità di dispositivo
È possibile gestire e proteggere i dispositivi mobili sono connessi alla propria organizzazione Office 365 con Office 365 Mobile Device Management (MDM). I dispositivi mobili quali Smartphone e Tablet che consentono di accedere a posta elettronica ufficio, calendario, contatti e documenti riprodurre gran parte da eseguire per verificare che i dipendenti siano in grado di funzionare in qualsiasi momento e da qualsiasi posizione. Di conseguenza, è fondamentale proteggere le informazioni dell'organizzazione. È possibile utilizzare Office 365 MDM Imposta regole di accesso e criteri di protezione del dispositivo e se si sta perduti o rubati a comparsa da dispositivi mobili.

Rapporti di conformità MDM forniscono una panoramica dei criteri che sono stati impostati da un'organizzazione per proteggere i dispositivi mobili che accedono ai dati di Office 365. Il report consente di filtrare i dispositivi lo stato di conformità, segnalate violazioni, dispositivi bloccati e numero di dispositivi che sono stato cancellato a causa di criteri di sicurezza. Per ulteriori informazioni, vedere [Panoramica della gestione dei dispositivi mobili per Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).

## <a name="data-loss-prevention"></a>Prevenzione della perdita di dati
Criteri DLP consentono di gestire la protezione e il flusso delle informazioni in un'organizzazione. È possibile impostare i criteri per bloccare l'accesso al contenuto, crittografare i dati o notificare agli utenti di criteri e violazioni dei criteri di utilizzo di suggerimenti sui criteri DLP nell'applicazione. Rapporti DLP consentono di comprendere il numero di corrispondenze di criteri e regole, sostituzioni e falsi positivi.

È possibile utilizzare l'interfaccia di amministrazione di Office 365 per visualizzare le informazioni sul numero di messaggi che vengono rilevati per i criteri DLP in formato tabella o grafico. In particolare, corrispondenze di criteri DLP per invio e la ricezione della posta e corrispondenze alle regole DLP posta inviata e ricevuta. È inoltre possibile visualizzare il numero di corrispondenze, sostituzioni e falsi positivi per ogni criterio nelle ultime 24 ore utilizzando l'interfaccia di amministrazione di Exchange. Tuttavia, questi dati non sono disponibili come un grafico. Se si scarica un report per l'utilizzo di Excel, è possibile visualizzare anche ulteriori dettagli, ad esempio il che ha inviato il messaggio, il giorno e genera una corrispondenza per i criteri sono state attivate. Per ulteriori informazioni, vedere [visualizzare i report sui rilevamenti di criteri DLP](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx).

## <a name="auditing-in-yammer-enterprise"></a>Controllo in Yammer Enterprise
Yammer che Enterprise offre agli amministratori la possibilità per esportare i dati di attività degli utenti da loro reti Yammer tramite l' [API di esportazione dei dati di Yammer](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)o manualmente tramite la pagina di amministrazione di rete Yammer. Consente di esportare i registri è limitato agli amministratori di rete in Yammer. (Tutti gli amministratori globali di Office 365 sono gli amministratori di rete Yammer).

Possono essere esportati i dati seguenti:

| Filename | Descrizione |
|----------------------------|-------------------------------------------------------------------------|
| Utenti. csv | Tutti gli utenti nuovi in sospeso e sospesi nella rete |
| Messages.csv | Tutti i messaggi nella rete |
| Files.csv (metadati) | Metadati, ad esempio un nome di file URL API, ID di programma di invio, caricati in e così via. |
| Files.csv (file originali) | File con estensione zip dei file originali che sono stati caricati dagli utenti in Yammer |
| Topics.csv | Argomenti creati in rete |
| Pages.csv | Pagine (notes) create dagli utenti nella rete |
| Admins.csv | Verificare tutti gli amministratori della rete |
| Networks.csv | Tutte le reti esterne Yammer |

*Nella tabella 3 - Yammer dati file di rete disponibile per l'esportazione per i clienti*

Yammer sono disponibili attraverso i rapporti sull'attività di Office 365 anche i dati dell'organizzazione. Inoltre, Yammer è sta lavorando su esporre ulteriori opzioni di registrazione tramite l'API di Office 365 Gestione attività e sulla capacità di motivo su dati di utilizzo di Power BI. Vedere [Roadmap di Office](https://fasttrack.microsoft.com/roadmap?filters=yammer) per ulteriori informazioni su queste funzionalità.
