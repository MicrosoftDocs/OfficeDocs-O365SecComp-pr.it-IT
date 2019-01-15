---
title: Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: Informazioni su come trovare e utilizzare i rapporti di protezione posta elettronica per l'organizzazione con Office 365 Enterprise. Rapporti sulla protezione posta elettronica sono disponibili nel titolo &amp; centro conformità.
ms.openlocfilehash: 3fc6d3dd8468bc060efcaa7eadec2ff9257fe583
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014988"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a>Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità

Sono disponibili in vari rapporti sulla protezione posta elettronica il [protezione &amp; centro conformità](https://security.microsoft.com) che consentono di vedere modalità di protezione antispam e antimalware caratteristiche di Office 365 dell'organizzazione. Se si dispone [delle autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare questi rapporti in sicurezza &amp; centro conformità accedendo ai **rapporti** \> **Dashboard**.
  
![La sicurezza &amp; dashboard centro conformità risulta utile per determinare dove funzioni avanzate Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
I rapporti di protezione posta elettronica includono quanto segue:
  
- [Relazione sullo stato di protezione di rischio](view-email-security-reports.md#tps) 
    
- [Rapporto sui rilevamenti di malware](view-email-security-reports.md#maldet)
    
- [Rapporto Malware principale](#top-malware-report)
    
- [Report di destinatari e mittenti principali](view-email-security-reports.md#topsenders)
    
- [Consentire l'accesso ai report di posta elettronica](#spoof-mail-report)
    
- [Rapporto sui rilevamenti di posta indesiderata](#spam-detections-report)
    
- [Report di posta elettronica inviati e ricevuti](view-email-security-reports.md#sentreceivedemail)
    
- [Rapporto messaggi segnalati dagli utenti](view-email-security-reports.md#userreported) (nuovo)! 
    
## <a name="threat-protection-status-report"></a>Relazione sullo stato di protezione di rischio

La nuova relazione **Sullo stato di protezione di rischio** è un rapporto intelligente che mostra dannoso posta elettronica che è stato rilevato e bloccato da Exchange Online Protection. Questo rapporto vengono visualizzate informazioni sulla posta elettronica identificato come malware o un tentativo di phishing. 

> [!NOTE]
> Una relazione sullo stato di protezione di rischio è disponibile per i clienti che dispongono di [Strumenti di analisi di Office 365](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto di stato di protezione di rischio per i clienti degli strumenti di analisi probabile che conterrà dati diversi rispetto a ciò che potrebbe essere visualizzato EOP customers. Ad esempio clienti EOP possono visualizzare informazioni su malware rilevato nel messaggio di posta elettronica, ma non informazioni sui [file dannosi rilevato in SharePoint Online, OneDrive o team Microsoft che](atp-for-spo-odb-and-teams.md), una funzionalità specifiche degli strumenti di analisi. ([Ulteriori informazioni sui report degli strumenti di analisi](view-reports-for-atp.md)).
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://protection.office.com), andare al **report** \> **Dashboard** \> **Lo stato di protezione di rischio**.
  
![Relazione sullo stato di protezione di rischio](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
Quando si apre la relazione sullo stato di protezione di rischio, il report mostra i dati per gli ultimi sette giorni per impostazione predefinita. Tuttavia, è possibile fare clic su **filtri** e modificare l'intervallo di date per un massimo di 90 giorni di dettaglio. In questo report è utile per visualizzare l'efficacia e l'impatto delle funzionalità di Exchange Online Protection dell'organizzazione e per l'analisi delle tendenze più lungo termine. 
  
![Filtri del rapporto sullo stato di protezione rischio](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
È anche possibile scegliere se visualizzare i dati per la posta elettronica identificato come dannose, posta identificata come tentativi di phishing, o posta elettronica identificato come contenente malware.
  
![Visualizzare le opzioni di rischio di protezione report](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a>Rapporto sui rilevamenti di malware

Nel rapporto **Rilevamenti di Malware** viene visualizzato il numero di messaggi in ingresso e in uscita sono stato rilevato come contenente malware per l'organizzazione. 
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://protection.office.com), andare al **report** \> **Dashboard** \> **Rilevamenti di Malware**.
  
![Esempio di rapporto sui rilevamenti di malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
Simile ad altri report, ad esempio il rapporto di stato di protezione di rischio, i report vengono visualizzati dati per gli ultimi sette giorni per impostazione predefinita. Tuttavia, è possibile scegliere di **filtri** per modificare l'intervallo di date. 
  
## <a name="top-malware-report"></a>Rapporto Malware principale

Il rapporto **Malware principali** Mostra i vari tipi di malware rilevato da Exchange Online. 
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://protection.office.com), andare al **report** \> **Dashboard** \> **Malware principali**.
  
![Controllo del codice sorgente - EOP Malware principali](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
Quando si sposta su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi sono stato rilevato con tale malware.
  
Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.
  
![In questo rapporto viene visualizzato il malware principali rilevato per l'organizzazione](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
Sotto il grafico verrà visualizzato un elenco di malware rilevato e il numero di messaggi sono stato rilevato con tale malware.
  
## <a name="top-senders-and-recipients-report"></a>Report di destinatari e mittenti principali

Il report **primi mittenti e destinatari** è un grafico a torta che mostra i mittenti di posta elettronica principali. 
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://protection.office.com), andare al **report** \> **Dashboard** \> **primi mittenti e destinatari**.
  
![Per visualizzare il report nella protezione &amp; centro conformità, passare a report \> Dashboard \> primi mittenti e destinatari](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
Quando si sposta su un cuneo nel grafico a torta, è possibile visualizzare un numero di messaggi inviati o ricevuti.
  
Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.
  
Utilizzare l'elenco di **visualizzare i dati relativi** a scegliere se si desidera visualizzare i dati per i mittenti principali, ricevitori, destinatari di posta indesiderata e destinatari di malware. Puoi anche vedere che ha ricevuto malware rilevato dal avanzate per la protezione rischio. 
  
![Utilizzare l'elenco Mostra dati per visualizzare informazioni specifiche](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
Sotto il grafico, si vedrà che i mittenti di posta elettronica principale o i destinatari sono stati, insieme a un numero di messaggi inviati o ricevuti per il periodo di tempo specificato.
  
## <a name="spoof-mail-report"></a>Consentire l'accesso ai report di posta elettronica

Nel rapporto di **Posta elettronica di spoofing** viene visualizzato il numero dei messaggi di posta elettronica spoofing sono stato rilevato e di quelli, quelli che sono state esaminate "good" (SteadyState motivi aziendali legittimi mail spoofing). 
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://protection.office.com), andare al **report** \> **Dashboard** \> **Spoofing posta**.
  
![Per visualizzare il report nella protezione &amp; centro conformità, passare a report \> Dashboard \> spoofing posta](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
Quando si sposta su un giorno del grafico, è possibile visualizzare il numero dei messaggi di posta elettronica spoofing sia il risultato.
  
Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.
  
## <a name="spam-detections-report"></a>Rapporto sui rilevamenti di posta indesiderata

Il rapporto **Sui rilevamenti di posta indesiderata** Visualizza tutto il contenuto di posta indesiderata bloccato da Exchange Online. 
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://protection.office.com), andare al **report** \> **Dashboard** \> **Rilevamenti di posta indesiderata**.
  
![Per visualizzare il report nella protezione &amp; centro conformità, passare a report \> Dashboard \> EOP i rilevamenti di posta indesiderata](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
Quando si sposta su un giorno del grafico, è possibile visualizzare il numero di elementi sono stato bloccato quel giorno il modo in cui sono suddivise in tali elementi. Ad esempio, è possibile visualizzare il numero di messaggi di posta indesiderata sono stato filtrato e il numero di elementi proviene da un indirizzo IP (Internet Protocol) bloccati.
  
Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.
  
![Il rapporto sui rilevamenti di posta indesiderata indica il numero di messaggi di posta indesiderata sono stato bloccato o filtrato](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
Sotto il grafico verrà visualizzato un elenco di elementi di posta indesiderata che sono stati rilevati. Selezionare una voce per visualizzare informazioni aggiuntive, ad esempio se l'elemento di posta indesiderata è stato in ingresso e in uscita, l'ID messaggio e il destinatario.
  
## <a name="sent-and-received-email-report"></a>Report di posta elettronica inviati e ricevuti

Il rapporto **Sent e posta elettronica ricevuta** è un referente smart che mostra informazioni sulla posta elettronica in arrivo e in uscita, tra cui i rilevamenti di posta indesiderata, malware e posta elettronica identificato come "buona". 
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://protection.office.com), andare al **report** \> **Dashboard** \> **inviati e ricevuto posta elettronica**.
  
![Per visualizzare il report nella protezione &amp; centro conformità, passare a report \> Dashboard \> Sent e posta elettronica ricevuta](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
Quando si sposta su un giorno del grafico, è possibile visualizzare il numero di messaggi è stato ricevuto e come i messaggi sono classificati. Ad esempio, è possibile visualizzare il numero di messaggi sono stato rilevato come contenente malware e sono stati identificati come posta indesiderata.
  
Fare clic su (o toccare) nel report viene aperto in una nuova finestra del browser dove è possibile ottenere una visualizzazione più dettagliata del report.
  
È possibile utilizzare l'elenco **suddivisione per** visualizzare informazioni dal tipo o dalla direzione (in ingresso e in uscita). 
  
![Utilizzare l'elenco interruzioni verso il basso da per visualizzare le informazioni dal tipo o la direzione](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
Sotto il grafico verrà visualizzato un elenco delle categorie di posta elettronica, ad esempio **GoodMail**, **SpamContentFiltered**e così via. Selezionare una categoria di visualizzare informazioni aggiuntive, ad esempio azioni intraprese per malware e di posta elettronica se è stato in ingresso o in uscita.
  
![Questo rapporto fornisce le informazioni sulla protezione anti-malware, protezione da posta indesiderata e rilevamenti altri messaggi](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a>Report di messaggi segnalati dagli utenti (nuovo)!

Il report **specificato dall'utente i messaggi** vengono visualizzate informazioni sui messaggi di posta elettronica che gli utenti hanno segnalato come posta indesiderata, tentativi di phishing o posta legittima utilizzando il [componente aggiuntivo di report](enable-the-report-message-add-in.md).
  
Sono disponibili dettagli per ogni messaggio, inclusi il motivo di recapito, ad esempio un eccezione di criteri di posta indesiderata o regola flusso di posta elettronica configurati per l'organizzazione. Per visualizzare i dettagli, selezionare un elemento nell'elenco report utente e quindi visualizzare le informazioni nelle schede **Riepilogo** e **Dettagli** . 
  
![Il rapporto di messaggi User-Reported Mostra agli utenti i messaggi contrassegnati come posta indesiderata, non indesiderata o phishing tentativi.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://protection.office.com), effettuare una delle operazioni seguenti:
  
- Passare a **gestione rischio** \> **Dashboard** \> **messaggi segnalati dagli utenti**.
    
- Passare a **gestione rischio** \> **revisione** \> **messaggi segnalati dagli utenti**.
    
![In sicurezza &amp; centro conformità, scegliere Threat management \> revisione \> messaggi specificato dall'utente](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> Per consentire il rapporto di messaggi segnalati dagli utenti per il corretto funzionamento di **deve essere attivata la registrazione di controllo** per l'ambiente Office 365. Questo viene in genere eseguito da un utente che disponga del ruolo registri di controllo assegnato in Exchange Online. Per ulteriori informazioni, vedere [attivare Office 365 ricerca dei registri di controllo attivato o disattivato](turn-audit-log-search-on-or-off.md). 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>Autorizzazioni necessarie per visualizzare questi rapporti?

Per poter visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato sia la sicurezza &amp; centro conformità e l'interfaccia di amministrazione di Exchange**.

- Per la sicurezza &amp; centro conformità, è necessario disporre dei seguenti ruoli assegnati:
    - Gestione organizzazione
    - Amministratore della sicurezza
    - Lettore di sicurezza

- Per Exchange Online deve essere uno dei seguenti ruoli assegnati:
    - Gestione organizzazione
    - Gestione organizzazione in sola visualizzazione
    - Ruolo Destinatari di sola lettura
    - Gestione della conformità

Per ulteriori informazioni, vedere le risorse seguenti:

- [Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)

- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a>Se il report non vengono visualizzate dati?

Se non si possono visualizzare dati nei report, verificare che i criteri siano configurati correttamente. Per ulteriori informazioni, vedere [protezione antispam e antimalware in Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)
  
[Report e sui concetti di Office 365 Security &amp; centro conformità](reports-and-insights-in-security-and-compliance.md)
  
[Creare una pianificazione per un report nella protezione &amp; centro conformità](create-a-schedule-for-a-report.md)
  
[Impostare e scaricare un report personalizzato per la protezione &amp; centro conformità](set-up-and-download-a-custom-report.md)
  

