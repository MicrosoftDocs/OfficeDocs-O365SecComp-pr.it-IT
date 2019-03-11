---
title: Utilizzo di Esplora minacce nel centro &amp; sicurezza e conformità
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Informazioni su Explorer (denominato anche Esplora minacce) nel centro sicurezza &amp; e conformità.
ms.openlocfilehash: 626d827712760aa0b7b6faf75d94f525cfe38dc2
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524010"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>Utilizzo di Esplora minacce nel centro &amp; sicurezza e conformità

Se l'organizzazione dispone di [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)e si dispone delle autorizzazioni necessarie, è possibile utilizzare l'esploratore di minacce per identificare e analizzare le minacce. Ad esempio, è possibile identificare ed eliminare messaggi di posta elettronica dannosi che sono stati recapitati oppure vedere malware rilevati dalle funzionalità di sicurezza di Office 365. L'esploratore di minacce (noto anche come esploratore) è uno strumento potente quasi in tempo reale che consente ai team di operazioni di sicurezza di analizzare e rispondere &amp; alle minacce nel centro sicurezza e conformità.
  
![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Per utilizzare Esplora risorse, nel centro &amp; sicurezza e conformità, accedere a **gestione** \> **** minacce.

> [!IMPORTANT]
> Office 365 Threat Intelligence è ora parte di Office 365 Advanced Threat Protection Plan 2, con ulteriori funzionalità di protezione dalle minacce. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).
      
## <a name="explorer-overview"></a>Panoramica di Esplora risorse

In Esplora risorse vengono visualizzate informazioni su malware e phishing sospetti nei messaggi di posta elettronica e nei file di Office 365, oltre ad altre minacce e rischi per la sicurezza per l'organizzazione. Quando si apre Explorer per la prima volta, la visualizzazione predefinita Visualizza i rilevamenti di malware per i messaggi di posta elettronica negli ultimi 7 giorni. Esplora risorse può anche mostrare le funzionalità di protezione della sicurezza in Office 365, inclusi i [collegamenti sicuri](atp-safe-links.md) e gli [allegati sicuri](atp-safe-attachments.md) e può essere modificato in modo da visualizzare i dati negli ultimi 30 giorni. Se si dispone di una versione di valutazione di abbonamento per Office 365 Advanced Threat Protection Plan 2 o Office 365 E5, verranno visualizzati solo i rilevamenti e i dati della posta elettronica per gli ultimi 7 giorni.
  
![Explorer visualizza informazioni sui principali utenti di malware e di destinazione](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
Utilizzare il menu Visualizza per modificare le informazioni visualizzate.
  
![Menu Visualizza per Esplora risorse](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
In Esplora sono disponibili diverse funzionalità di filtro e query che consentono di eseguire il drill-down nei dettagli, ad esempio gli utenti più mirati, le famiglie di malware più importanti, la tecnologia di rilevamento e altro ancora. Ogni tipo di report offre una vasta gamma di modi per visualizzare ed esplorare i dati.

> [!IMPORTANT]
> Non utilizzare caratteri jolly, ad esempio un asterisco (*) o un punto interrogativo (?), con Esplora risorse. Quando si esegue una ricerca nel campo Subject per i messaggi di posta elettronica, Explorer eseguirà una corrispondenza parziale e restituisce risultati simili a quelli di una ricerca con caratteri jolly.

## <a name="email--malware"></a>Malware \> per la posta elettronica

Questa visualizzazione Mostra i messaggi di posta elettronica identificati come contenenti malware.  

Visualizzare le informazioni nel grafico per la famiglia di malware, il dominio del mittente, l'IP del mittente, lo stato di protezione (azioni intraprese dalle caratteristiche e i criteri di protezione dalle minacce in Office 365) e la tecnologia di rilevamento (come è stato rilevato il malware).  

![Visualizzare i dati relativi al malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

Al di sotto del grafico, visualizzare i dettagli relativi alle famiglie di malware principali, agli utenti più mirati e maggiori dettagli su messaggi specifici. 

## <a name="email--phish"></a>Phishing \> di posta elettronica

Questa visualizzazione Mostra i messaggi di posta elettronica identificati come tentativi di phishing.  

Visualizzare le informazioni in base al dominio del mittente, all'IP del mittente e allo stato di protezione (azioni intraprese dalle caratteristiche e dai criteri di protezione delle minacce in Office 365). 

![Visualizzare i dati relativi alla posta elettronica identificata come tentativi di phishing](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi specifici. 

## <a name="email--user-reported"></a>Messaggio \> di posta elettronica visualizzato dall'utente

Questa visualizzazione Mostra la posta elettronica che gli utenti hanno segnalato come posta indesiderata, non indesiderata o phishing.  

Visualizzare le informazioni in base al tipo di rapporto (la determinazione dell'utente che il messaggio di posta elettronica è stato indesiderato, non indesiderato o phishing) e per motivo di recapito (motivi per cui la posta elettronica è stata indirizzata a una posizione specifica, ad esempio un criterio di filtro per la posta indesiderata, una regola del flusso, un elenco dei mittenti bloccati ecc.).  

![Visualizzare i dati relativi agli utenti di posta elettronica riportati come posta indesiderata, non indesiderata o phishing](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, l'indirizzo IP del mittente, l'utente che ha segnalato il messaggio come posta indesiderata, non indesiderata o phishing e altro ancora. 

## <a name="email--all-mail"></a>Posta \> elettronica tutti i messaggi

Questa visualizzazione Mostra una panoramica completa dell'attività di posta elettronica, inclusi i messaggi di posta elettronica identificati come dannosi a causa di phishing o malware, nonché tutti i messaggi non dannosi (posta elettronica normale, posta indesiderata e messaggi in blocco). 

> [!NOTE]
> Se viene visualizzato un messaggio di errore in cui vengono letti **troppi dati da visualizzare**, aggiungere un filtro e, se necessario, limitare l'intervallo di date che si sta visualizzando. 

Per applicare un filtro, scegliere **mittente**, selezionare un elemento nell'elenco e quindi fare clic sul pulsante Aggiorna. In questo esempio, è stata utilizzata la **tecnologia di rilevamento** come filtro (sono disponibili diverse opzioni). Visualizzare le informazioni per mittente, dominio del mittente, destinatari, oggetto, nome file allegato, famiglia di malware, stato di protezione (azioni intraprese dalle caratteristiche e dai criteri di protezione dalle minacce in Office 365), tecnologia di rilevamento (come è stato rilevato il malware) e più. 

![Visualizzare i dati relativi alla posta elettronica individuata mediante tecnologia di rilevamento](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

Al di sotto del grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, il destinatario, il mittente, lo stato e così via. 

## <a name="content--malware"></a>Malware \> contenuto

Questa visualizzazione Mostra i file che sono stati identificati come dannosi da Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for business e Microsoft teams.

Consente di visualizzare le informazioni per la famiglia di malware, la tecnologia di rilevamento (come è stato rilevato il malware) e il carico di lavoro (OneDrive, SharePoint o Teams). 

![Visualizzare i dati relativi al malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

Al di sotto del grafico, visualizzare ulteriori dettagli sui file specifici, ad esempio il nome del file degli allegati, il carico di lavoro, le dimensioni, l'ultimo che ha modificato il file e altro ancora. 
  
## <a name="new-click-to-filter-capabilities"></a>(Nuovo!) Funzionalità di clic su filtro

Nuovo in Esplora risorse è la possibilità di fare clic per filtrare. Quando si fa clic su un elemento nella legenda, l'elemento diventa un filtro per il report. Si supponga, ad esempio, di esaminare la visualizzazione malware in Esplora risorse:
  
![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Facendo clic su **detonaZione ATP** in questo grafico viene visualizzato un risultato simile al seguente: 
  
![Filtro Esplora risorse per visualizzare solo i risultati di detonazione ATO](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
In questa visualizzazione, vengono ora esaminati i dati per i file che sono stati detonati da [allegati sicuri di Office 365 ATP](atp-safe-attachments.md). Al di sotto del grafico, è possibile visualizzare i dettagli relativi a messaggi di posta elettronica specifici che sono stati rilevati da allegati sicuri di ATP.
  
![Dettagli specifici sui messaggi di posta elettronica con allegati rilevati](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
La selezione di uno o più elementi attiva il menu **azioni** , che offre diverse opzioni tra cui scegliere per gli elementi selezionati. 
  
![La selezione di un elemento attiva il menu azioni](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
La possibilità di filtrare i dati in un clic e di passare a dettagli specifici consente di risparmiare molto tempo nell'analisi delle minacce.
  
## <a name="how-do-i-get-explorer"></a>Come è possibile ottenere Esplora risorse?

Explorer è incluso in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md). 

Per visualizzare e utilizzare Esplora risorse, è necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o a un lettore di sicurezza. Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365](reports-and-insights-in-security-and-compliance.md)
  
[Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Threat Invesitgation e Response)](investigate-malicious-email-that-was-delivered.md)
  
[Protezione antispam e antimalware in Office 365](anti-spam-and-anti-malware-protection.md)
  

