---
title: Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i report sulla sicurezza della posta elettronica per l'organizzazione con Office 365 Enterprise. I report sulla sicurezza della posta elettronica sono &amp; disponibili nel centro sicurezza e conformità.
ms.openlocfilehash: fb9f8234f1febf98daf0382f2ad8ece3e3ecbbfe
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241998"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a>Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità

Una serie di rapporti sulla sicurezza della posta elettronica sono disponibili nel [Centro sicurezza &amp; e conformità](https://security.microsoft.com) per vedere come le funzionalità di protezione da posta indesiderata e antimalware in Office 365 proteggono l'organizzazione. Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare questi report nel centro sicurezza &amp; e conformità accedendo al **** \> **Dashboard**dei report.
  
![Il dashboard &amp; del Centro sicurezza e conformità consente di individuare la modalità di funzionamento di Advanced Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
I rapporti di sicurezza della posta elettronica includono quanto segue:
  
- [Rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#tps) 
    
- [Rapporto riLevamenti malware](view-email-security-reports.md#maldet)
    
- [Rapporto malware principale](#top-malware-report)
    
- [Report mittenti e destinatari principali](view-email-security-reports.md#topsenders)
    
- [Report di posta contraffatta](#spoof-mail-report)
    
- [Rapporto rilevamento posta inDesiderata](#spam-detections-report)
    
- [Report di posta elettronica inviati e ricevuti](view-email-security-reports.md#sentreceivedemail)
    
- [Report dei messaggi segnalaTi dall'utente](view-email-security-reports.md#userreported) (nuovo!) 
    
## <a name="threat-protection-status-report"></a>Rapporto sullo stato della protezione dalle minacce

Il nuovo rapporto **sullo stato di protezione dalle minacce** è uno smart report che indica che la posta elettronica dannosa è stata rilevata e bloccata da Exchange Online Protection. Questo report Visualizza informazioni su messaggi di posta elettronica identificati come malware o su un tentativo di phishing. 

> [!NOTE]
> Un rapporto sullo stato della protezione dalle minacce è disponibile per i clienti che dispongono di [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto sullo stato di protezione di minacce per i clienti ATP probabilmente conterranno dati diversi da quelli che potrebbero essere visualizzati dai clienti di EOP. Ad esempio, i clienti di EOP possono visualizzare informazioni sui malware rilevati tramite posta elettronica, ma non informazioni sui [file dannosi rilevati in SharePoint Online, OneDrive o Microsoft teams](atp-for-spo-odb-and-teams.md), una funzionalità specifica del trifosfato di adenosina. (Ulteriori[informazioni sui rapporti ATP](view-reports-for-atp.md)).
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **segnala** \> **** \> **lo stato di protezione delle minacce**del dashboard.
  
![Rapporto sullo stato della protezione dalle minacce](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
Quando si apre per la prima volta il rapporto sullo stato di protezione dalle minacce, il report Visualizza i dati per i sette giorni scorsi per impostazione predefinita. Tuttavia, è possibile fare clic su **filtri** e modificare l'intervallo di date fino a 90 giorni di dettaglio. Questo report è utile per visualizzare l'efficacia e l'impatto delle funzionalità di Exchange Online Protection dell'organizzazione e per i trend a più lungo termine. 
  
![Filtri del rapporto sullo stato di protezione dalle minacce](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
È anche possibile scegliere se visualizzare i dati per la posta elettronica identificati come messaggi dannosi, identificati come tentativi di phishing o come messaggi di posta elettronica identificati come contenenti malware.
  
![Opzioni di visualizzazione del rapporto sullo stato di protezione dalle minacce](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a>Rapporto riLevamenti malware

Il rapporto **rilevamento malware** indica il numero di messaggi in ingresso e in uscita che sono stati rilevati come contenenti malware per l'organizzazione. 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **report** \> di **rilevamento di malware**del **Dashboard** \> .
  
![Esempio di rapporto riLevamenti malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
Analogamente ad altri rapporti, come il rapporto sullo stato della protezione dalle minacce, il report Visualizza i dati per i sette giorni scorsi per impostazione predefinita. Tuttavia, è possibile scegliere **filtri** per modificare l'intervallo di date. 
  
## <a name="top-malware-report"></a>Rapporto malware principale

Il rapporto **malware principale** Visualizza i vari tipi di malware rilevati da Exchange Online. 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), andare a **Reports** \> **Dashboard** \> **Top malware**.
  
![SCC-EOP Top malware](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi che sono stati rilevati come aventi quel malware.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
![Questo rapporto Visualizza la parte superiore di malware rilevata per l'organizzazione](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
Al di sotto del grafico, verrà visualizzato un elenco di malware rilevato e il numero di messaggi che sono stati rilevati con malware.
  
## <a name="top-senders-and-recipients-report"></a>Report mittenti e destinatari principali

Il report **mittenti e destinatari principali** è un grafico a torta che mostra i mittenti di posta elettronica principali. 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), andare a **Reports** \> **Dashboard** \> **Top Senders and Recipients**.
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità andare a Reports \> dashboard \> Top Senders and Recipients](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il numero di messaggi inviati o ricevuti.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
Utilizzare l'elenco **Mostra dati per** scegliere se visualizzare i dati per i mittenti principali, i destinatari, gli utenti di posta indesiderata e i destinatari di malware. È inoltre possibile visualizzare gli utenti che hanno ricevuto malware rilevati da Advanced Threat Protection. 
  
![Utilizzare l'elenco Mostra dati per visualizzare informazioni specifiche](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
Al di sotto del grafico, si vedrà chi sono i mittenti di posta elettronica o i destinatari principali, insieme a un numero di messaggi inviati o ricevuti per il periodo di tempo specificato.
  
## <a name="spoof-mail-report"></a>Report di posta contraffatta

Il report di **posta spoof** Visualizza quanti messaggi di posta elettronica contraffatti sono stati rilevati e di quelli, quali sono stati considerati "buoni" (la posta contraffatta è stata realizzata per motivi aziendali legittimi). 
  
Per visualizzare questo report, nel [centro conformità &amp; sicurezza](https://protection.office.com)accedere a **report** \> di **posta**indesiderata del **Dashboard** \> .
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità, accedere a report \> di \> posta indesiderata del dashboard](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile visualizzare il numero di messaggi di posta elettronica contraffatti.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
## <a name="spam-detections-report"></a>Rapporto rilevamento posta inDesiderata

Il rapporto sui riLevamenti di **posta** indesiderata consente di visualizzare tutti i contenuti di posta indesiderata bloccati 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere ai rilevamenti di **posta**indesiderata del **Dashboard** \> dei **report** \> .
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità, accedere a report \> dashboard \> EOP spam detections](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile vedere quanti elementi sono stati bloccati quel giorno, così come gli elementi sono categorizzati. Ad esempio, è possibile visualizzare il numero di messaggi di posta indesiderata filtrati e il numero di elementi provenienti da un indirizzo IP (Internet Protocol) bloccato.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
![Il rapporto sui riLevamenti di posta inDesiderata indica il numero di messaggi di posta indesiderata bloccati o eliminati](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
Al di sotto del grafico, verrà visualizzato un elenco di elementi di posta indesiderata che sono stati rilevati. Selezionare un elemento per visualizzare informazioni aggiuntive, ad esempio se l'elemento di posta indesiderata è in ingresso o in uscita, il relativo ID messaggio e il relativo destinatario.
  
## <a name="sent-and-received-email-report"></a>Report di posta elettronica inviati e ricevuti

Il rapporto **messaggi di posta elettronica inviati e ricevuti** è un report Smart che contiene informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona". 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **Reports** \> **Dashboard** \> **sent and received email**.
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità, accedere a \> Reports \> dashboard sent and received email](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile visualizzare il numero di messaggi in arrivo e il modo in cui i messaggi vengono categorizzati. Ad esempio, è possibile vedere quanti messaggi sono stati rilevati come contenenti malware e quante sono stati identificati come posta indesiderata.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
È possibile utilizzare l'elenco a **discesa** per visualizzare le informazioni per tipo o per direzione (in ingresso e in uscita). 
  
![Utilizzare l'elenco a discesa per visualizzare le informazioni in base al tipo o alla direzione](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
Al di sotto del grafico verrà visualizzato un elenco di categorie di posta elettronica, ad esempio **GoodMail**, **SpamContentFiltered**e così via. Selezionare una categoria per visualizzare altre informazioni, ad esempio le azioni che sono state intraprese per il malware, e se la posta elettronica è in ingresso o in uscita.
  
![Questo rapporto fornisce informazioni sull'antimalware, la protezione da posta indesiderata e altri rilevamenti dei messaggi](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a>Report dei messaggi segnalati dall'utente (nuovo!)

Il rapporto **messaggi segnalaTi dall'utente** Visualizza informazioni sui messaggi di posta elettronica segnalati dagli utenti come posta indesiderata, tentativi di phishing o una buona corrispondenza tramite il [componente aggiuntivo segnala messaggio](enable-the-report-message-add-in.md).
  
I dettagli sono disponibili per ogni messaggio, incluso il motivo del recapito, una regola di protezione da posta indesiderata o un flusso di posta configurata per l'organizzazione. Per visualizzare i dettagli, selezionare un elemento nell'elenco User-Reports e quindi visualizzare le informazioni nelle schede **Riepilogo** e **Dettagli** . 
  
![Il rapporto messaggi segnalati dall'utente Visualizza i messaggi che gli utenti sono contrassegnati come posta indesiderata, non indesiderata o tentativi di phishing.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com)eseguire una delle operazioni seguenti:
  
- Accedere a **messaggi segnalati dall'utente**del \> **Dashboard** \> di **gestione delle minacce** .
    
- Passare a **gestione** \> minacce **esaminare** \> **i messaggi segnalati dall'utente**.
    
![Nel centro sicurezza &amp; e conformità, scegliere messaggi segnalati dall'utente di Threat Management \> Review \>](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> Affinché il rapporto messaggi segnalati dall'utente funzioni correttamente, **è necessario che la registrazione di controllo sia attivata** per l'ambiente Office 365. Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online. Per ulteriori informazioni, vedere [attivazione o disattivaZione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md). 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quali autorizzazioni sono necessarie per visualizzare i rapporti?

Per visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato per il Centro sicurezza &amp; e l'interfaccia di amministrazione di Exchange**.

- Per il centro &amp; sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:
    - Gestione organizzazione
    - Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()
    - Lettore di sicurezza

- Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - Gestione organizzazione
    - Gestione organizzazione in sola visualizzazione
    - Ruolo Destinatari di sola lettura
    - Gestione della conformità

Per ulteriori informazioni, vedere le risorse seguenti:

- [Autorizzazioni nel centro sicurezza &amp; e conformità di Office 365](permissions-in-the-security-and-compliance-center.md)

- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a>Cosa succede se i rapporti non mostrano dati?

Se i dati non vengono visualizzati nei rapporti, verificare che i criteri siano configurati correttamente. Per ulteriori informazioni, vedere [protezione da posta indesiderata e anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)
  
[Report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365](reports-and-insights-in-security-and-compliance.md)
  
[Creare una pianificazione per un report nel centro sicurezza &amp; e conformità](create-a-schedule-for-a-report.md)
  
[Configurare e scaricare un report personalizzato nel centro sicurezza &amp; e conformità](set-up-and-download-a-custom-report.md)
  

