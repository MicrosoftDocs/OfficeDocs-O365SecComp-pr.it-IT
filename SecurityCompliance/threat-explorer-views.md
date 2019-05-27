---
title: Visualizzazioni in Esplora minacce e rilevamenti in tempo reale
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: Informazioni sui vari tipi di visualizzazioni disponibili in Esplora minacce e sui rilevamenti in tempo reale.
ms.openlocfilehash: 14cdbbd602e53615abec12bedbac2f16be40111f
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408321"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Visualizzazioni in Esplora minacce e rilevamenti in tempo reale

![Esplora minacce](media/ThreatExplorerFirstOpened.png)

[Esplora minacce](use-explorer-in-security-and-compliance.md) (e il rapporto rilevamento in tempo reale) è uno strumento potente e quasi in tempo reale che consente ai team di operazioni di sicurezza di analizzare e rispondere alle minacce &amp; nel centro sicurezza e conformità. Explorer (e il rapporto rilevamenti in tempo reale) Visualizza le informazioni sui sospetti malware e phishing nei messaggi di posta elettronica e nei file di Office 365, oltre ad altre minacce e rischi per la sicurezza per l'organizzazione. 

- Se si dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) piano 2, è necessario disporre di Esplora risorse.
- Se si dispone di Office 365 ATP piano 1, è possibile rilevare i rilevamenti in tempo reale.

Quando si apre Explorer (o il rapporto rilevamenti in tempo reale), la visualizzazione predefinita Visualizza i rilevamenti di malware per la posta elettronica negli ultimi 7 giorni. Questo rapporto può anche mostrare rilevamenti di ATP, ad esempio URL dannosi rilevati da [collegamenti sicuri](atp-safe-links.md)e file dannosi rilevati da [allegati sicuri](atp-safe-attachments.md). Questo report può essere modificato in modo da visualizzare i dati negli ultimi 30 giorni, a meno che non si utilizzi una sottoscrizione di valutazione. Gli abbonamenti di valutazione includeranno i dati solo per i sette giorni scorsi.

Utilizzare il menu **Visualizza** per modificare le informazioni visualizzate. Le descrizioni comandi consentono di determinare la visualizzazione da utilizzare.
  
![Menu Visualizza Esplora minacce](media/ThreatExplorerViewMenu.png)

Dopo aver selezionato una visualizzazione, è possibile applicare filtri e configurare le query per eseguire un'ulteriore analisi. Nelle sezioni seguenti viene fornita una breve panoramica delle diverse visualizzazioni disponibili in Esplora risorse (o rilevamenti in tempo reale).  

## <a name="email--malware"></a>Malware > di posta elettronica

Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** > **messaggio di posta elettronica** > **malware**. Questa visualizzazione Mostra informazioni sui messaggi di posta elettronica che sono stati identificati come contenenti malware.  

![Visualizzare i dati relativi alla posta elettronica identificata come malware](media/ExplorerEmailMalwareMenu.png) 

Fare clic su **sender** per aprire l'elenco delle opzioni di visualizzazione. Utilizzare questo elenco per visualizzare i dati in base a mittente, destinatari, dominio del mittente, oggetto, tecnologia di rilevamento, stato di protezione e altro ancora. 

Ad esempio, per sapere quali azioni sono state eseguite nei messaggi di posta elettronica rilevati, scegliere **stato protezione** nell'elenco. Selezionare un'opzione e quindi fare clic sul pulsante Aggiorna per applicare il filtro al report.

![Opzioni di stato di protezione dalle minacce per Esplora minacce](media/ThreatExplorerProtectionStatusOptions.png)

Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi specifici. Quando si seleziona un elemento nell'elenco, viene aperto un riquadro di volo, in cui è possibile ottenere ulteriori informazioni sull'elemento selezionato. 

![Esplora minacce con apertura a comparsa](media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>Phishing > di posta elettronica

Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **View** > **email** > **phishing**. Questa visualizzazione Mostra i messaggi di posta elettronica identificati come tentativi di phishing.  

![Visualizzare i dati relativi alla posta elettronica identificata come tentativi di phishing](media/ThreatExplorerEmailPhish.png) 

Fare clic su **sender** per aprire l'elenco delle opzioni di visualizzazione. Utilizzare questo elenco per visualizzare i dati in base a mittente, destinatari, dominio del mittente, IP del mittente, dominio URL, fare clic su verdetto e altro ancora. 

Ad esempio, per sapere quali azioni sono state eseguite quando gli utenti hanno fatto clic su URL identificati come tentativi di phishing, **fare clic su verdetto** nell'elenco, selezionare una o più opzioni e quindi fare clic sul pulsante Aggiorna.

![Fare clic su opzioni di verdetto per il report di phishing](media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Al di sotto del grafico, visualizzare ulteriori dettagli relativi a messaggi specifici, clic URL, URL e origine della posta elettronica. 

![URL rilevati come phishing nei messaggi di posta elettronica](media/ThreatExplorerEmailPhishURLs.png)

Quando si seleziona un elemento nell'elenco, ad esempio un URL rilevato, viene aperto un riquadro di volo, in cui è possibile ottenere ulteriori informazioni sull'elemento selezionato. 

![Dettagli relativi a un URL rilevato](media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--user-reported"></a>Messaggi di posta elettronica > riportati dall'utente

Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** > **la posta elettronica** > **segnalata dall'utente**. Questa visualizzazione Mostra la posta elettronica che gli utenti hanno segnalato come posta indesiderata, non indesiderata o phishing. 

![Messaggi di posta elettronica segnalati dagli utenti](media/ThreatExplorerEmailUserReportedViewOptions.png) 

Fare clic su **sender** per aprire l'elenco delle opzioni di visualizzazione. Utilizzare questo elenco per visualizzare le informazioni per mittente, destinatario, tipo di rapporto (la determinazione dell'utente che la posta elettronica è indesiderata, non indesiderata o phishing) e altro ancora. 

Ad esempio, per visualizzare informazioni sui messaggi di posta elettronica segnalati come tentativi di phishing, fare clic su**tipo di rapporto** **mittente** > , selezionare **phishing**e quindi fare clic sul pulsante Aggiorna.

![Phishing selezionato per il filtro dei tipi di report](media/ThreatExplorerEmailUserReportedPhishSelected.png)

Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, l'indirizzo IP del mittente, l'utente che ha segnalato il messaggio come posta indesiderata, non indesiderata o phishing e altro ancora. 

![Messaggi segnalati come tentativi di phishing](media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Selezionare un elemento nell'elenco per visualizzare ulteriori dettagli.

## <a name="email--all-email"></a>Posta elettronica > tutta la posta elettronica

Per visualizzare questo report, in Esplora, scegliere **Visualizza** > **posta elettronica** > **tutti i messaggi**. Questa visualizzazione Mostra una panoramica completa dell'attività di posta elettronica, inclusi i messaggi di posta elettronica identificati come dannosi a causa di phishing o malware, nonché tutti i messaggi non dannosi (posta elettronica normale, posta indesiderata e messaggi in blocco). 

> [!NOTE]
> Se viene visualizzato un messaggio di errore in cui vengono letti **troppi dati da visualizzare**, aggiungere un filtro e, se necessario, limitare l'intervallo di date che si sta visualizzando. 

Per applicare un filtro, scegliere **mittente**, selezionare un elemento nell'elenco e quindi fare clic sul pulsante Aggiorna. In questo esempio, è stata utilizzata la **tecnologia di rilevamento** come filtro (sono disponibili diverse opzioni). Visualizzare le informazioni per mittente, dominio del mittente, destinatari, oggetto, nome file allegato, famiglia di malware, stato di protezione (azioni intraprese dalle caratteristiche e dai criteri di protezione dalle minacce in Office 365), tecnologia di rilevamento (come è stato rilevato il malware) e più. 

![Visualizzare i dati relativi alla posta elettronica individuata mediante tecnologia di rilevamento](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, il destinatario, il mittente, lo stato e così via. 

## <a name="content--malware"></a>Malware > content

Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **View** > **Content** > **malware**. Questa visualizzazione Mostra i file che sono stati identificati come dannosi da [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for business e Microsoft teams](atp-for-spo-odb-and-teams.md).

Consente di visualizzare le informazioni per la famiglia di malware, la tecnologia di rilevamento (come è stato rilevato il malware) e il carico di lavoro (OneDrive, SharePoint o Teams). 

![Visualizzare i dati relativi al malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

Al di sotto del grafico, visualizzare ulteriori dettagli sui file specifici, ad esempio il nome del file degli allegati, il carico di lavoro, le dimensioni, l'ultimo che ha modificato il file e altro ancora. 
  
## <a name="click-to-filter-capabilities"></a>Funzionalità di clic su filtro

Con Esplora risorse (e rilevamenti in tempo reale), è possibile applicare un filtro in un clic. Fare clic su un elemento nella legenda e quell'elemento diventa un filtro per il report. Si supponga, ad esempio, di esaminare la visualizzazione malware in Esplora risorse:
  
![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Facendo clic su **detonazione ATP** in questo grafico viene visualizzato un risultato simile al seguente: 
  
![Filtro Esplora risorse per visualizzare solo i risultati di detonazione ATP](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
In questa visualizzazione, vengono ora esaminati i dati per i file che sono stati detonati da [allegati sicuri di Office 365 ATP](atp-safe-attachments.md). Al di sotto del grafico, è possibile visualizzare i dettagli relativi a messaggi di posta elettronica specifici che sono stati rilevati da allegati sicuri di ATP.
  
![Dettagli specifici sui messaggi di posta elettronica con allegati rilevati](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
La selezione di uno o più elementi attiva il menu **azioni** , che offre diverse opzioni tra cui scegliere per gli elementi selezionati. 
  
![La selezione di un elemento attiva il menu azioni](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
La possibilità di filtrare i dati in un clic e di passare a dettagli specifici consente di risparmiare molto tempo nell'analisi delle minacce.

## <a name="queries-and-filters"></a>Query e filtri

Explorer (e il rapporto rilevamenti in tempo reale) ha diversi filtri potenti e funzionalità di query che consentono di eseguire il drill-down nei dettagli, ad esempio gli utenti più mirati, le famiglie di malware principali, la tecnologia di rilevamento e altro ancora. Ogni tipo di report offre una vasta gamma di modi per visualizzare ed esplorare i dati.

> [!IMPORTANT]
> Non utilizzare caratteri jolly, ad esempio un asterisco (*) o un punto interrogativo (?), nella barra delle query per Esplora risorse (o rilevamenti in tempo reale). Quando si esegue una ricerca nel campo Subject per i messaggi di posta elettronica, gli esploratori (o i rilevamenti in tempo reale) eseguono una corrispondenza parziale e restituiscono risultati simili a una ricerca con caratteri jolly.
