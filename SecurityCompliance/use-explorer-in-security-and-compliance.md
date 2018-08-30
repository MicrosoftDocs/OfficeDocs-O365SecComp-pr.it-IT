---
title: Utilizzare Esplora in sicurezza &amp; centro conformità
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
description: Informazioni sulle soluzioni (denominato anche Explorer rischio) la sicurezza &amp; centro conformità.
ms.openlocfilehash: 51228101ba75eb2d51b2594db50f679ff107ed46
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531380"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a>Utilizzare Esplora in sicurezza &amp; centro conformità

Se si dispone necessarie [le autorizzazioni nel centro conformità di protezione di Office 365 e](permissions-in-the-security-and-compliance-center.md)l'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md), è possibile utilizzare Explorer per identificare e analizzare le minacce. Ad esempio, è possibile identificare ed eliminare dannoso posta elettronica che è stato recapitato o vedere malware che è stato rilevato dalla funzionalità di protezione di Office 365. Explorer (anche noto come Explorer rischio) è un potente quasi in tempo reale report nella protezione &amp; centro conformità.
  
![Passare a gestione rischio \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Utilizzare Esplora, in sicurezza &amp; centro conformità, passare a **gestione delle minacce** \> **Explorer**.
      
## <a name="explorer-overview"></a>Panoramica delle soluzioni

Explorer vengono visualizzate informazioni su sospetto malware nella posta elettronica e i file in Office 365, nonché altri minacce per la protezione e rischi per la propria organizzazione. Quando si apre Explorer, la visualizzazione predefinita mostra i rilevamenti di malware da antivirus. Explorer anche possibile visualizzare sicurezza funzionalità di protezione in Office 365, inclusi [Collegamenti sicuri](atp-safe-links.md) e [Gli allegati sicuri](atp-safe-attachments.md).
  
![Explorer consente di visualizzare informazioni su malware principali e gli utenti di destinazione](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
Utilizzare il menu Visualizza per modificare le informazioni da visualizzare.
  
![Dal menu Visualizza per elenco delle cartelle](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
Explorer filtro diverse e l'esecuzione di query funzionalità che consentono di penetrare nei dettagli, ad esempio inizio destinate agli utenti, le famiglie di malware principali e altro ancora. Ogni tipo di rapporto sono disponibili diversi modi per visualizzare ed esplorare dati, come descritto nella tabella seguente.
  
|**Opzione**|**Per visualizzare i dati**|
|:-----|:-----|
|**Messaggio di posta elettronica** \> **Malware** <br/> |Messaggi di posta elettronica identificati come contenente malware.  <br/> Visualizzare le informazioni del grafico dalla tecnologia di rilevamento (come malware rilevato), dominio mittente, mittente IP, lo stato di protezione (azioni effettuate dal criteri in Office 365 e funzionalità di protezione di rischio) e dalla famiglia di malware.  <br/> ![Visualizzare i dati relativi a malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)           <br/> Sotto il grafico, visualizzare i dettagli relativi famiglie di malware principali, top destinate agli utenti e ulteriori dettagli sui messaggi specifici.  <br/> |
|**Messaggio di posta elettronica** \> **Rilevatore attività** <br/> |I messaggi identificati come tentativi di phishing della posta elettronica.  <br/> Visualizzare le informazioni sul dominio mittente, IP mittente e lo stato di protezione (azioni effettuate dal criteri in Office 365 e funzionalità di protezione di rischio).  <br/> ![Visualizzare i dati sulla posta identificata come tentativi di phishing](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png)           <br/> Sotto il grafico consente di visualizzare ulteriori dettagli sui messaggi specifici.  <br/> |
|**Messaggio di posta elettronica** \> **Segnalati dagli utenti** <br/> |Messaggio di posta elettronica che gli utenti hanno segnalato come posta indesiderata, non indesiderata e phishing.  <br/> Consente di visualizzare informazioni per il tipo di report (determinazione dell'utente che è stata la posta indesiderata, non indesiderata o per attività di phishing) e per motivi di recapito (motivi per cui sono diventato posta elettronica in una posizione specifica, ad esempio un criterio di filtro posta indesiderata, una regola del flusso di posta, un elenco di mittenti bloccati, un elenco dei mittenti, ecc.).  <br/> ![Visualizzare i dati sugli utenti di posta elettronica segnalati come posta indesiderata, non indesiderata o phishing](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)           <br/> Sotto il grafico consente di visualizzare ulteriori dettagli sui messaggi di posta elettronica specifico, ad esempio l'oggetto del messaggio, indirizzo IP del mittente, l'utente che ha segnalato il messaggio come posta indesiderata, non posta indesiderata, o per attività di phishing e altro ancora.  <br/> |
|**Messaggio di posta elettronica** \> **Tutta la posta** <br/> |Una visualizzazione di tutti i backup di attività di posta elettronica, inclusa la posta elettronica identificato come dannosi a causa di phishing o malware, come e di tutti i messaggi non intenzionale (normale posta elettronica, posta indesiderata e posta elettronica in blocco).  <br/> > [!NOTE]> Se si verifica un errore indicante **Too quantità di dati da visualizzare**, aggiungere un filtro e, se necessario, limitare l'intervallo di date si stanno visualizzando. Per applicare un filtro, scegliere **mittente**, selezionare un elemento nell'elenco e quindi fare clic sul pulsante Aggiorna. In questo esempio viene utilizzata **la tecnologia di rilevamento** come filtro (sono disponibili diverse opzioni disponibili).           Visualizzare le informazioni di mittente, dominio del mittente, destinatari, subject, nome del file allegato, famiglia di malware, lo stato di protezione (azioni effettuate dal criteri in Office 365 e funzionalità di protezione di rischio), la tecnologia di rilevamento (come malware rilevato), e ulteriori.<br/> ![Visualizzare i dati sulla posta elettronica rilevato dalla tecnologia di rilevamento](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)           <br/> Sotto il grafico consente di visualizzare ulteriori dettagli sui messaggi di posta elettronica specifico, ad esempio l'oggetto del messaggio, destinatario, mittente, lo stato e così via.  <br/> |
|**Contenuto** \> **Malware** <br/> |File che sono stati identificati come dannose in SharePoint Online, OneDrive for Business e Teams Microsoft.  <br/> Visualizza informazioni dalla tecnologia di rilevamento della famiglia, malware (come malware rilevato) e il carico di lavoro (OneDrive, SharePoint o team).  <br/> ![Visualizzare i dati relativi a malware rilevato](media/d11dc568-b091-4159-b261-df13d76b520b.png)           <br/> Sotto il grafico consente di visualizzare ulteriori informazioni sui file specifici, ad esempio il nome del file allegato, carico di lavoro, le dimensioni del file che ha modificato il file e altro ancora.  <br/> |
  
## <a name="new-click-to-filter-capabilities"></a>(Nuovo)! Fare clic su filtro a funzionalità

Nuova a soluzioni è la possibilità di fare clic su per filtrare l'elenco. A partire da ritardo 2018 maggio, quando si fa clic su un elemento nella legenda, che l'elemento diventa un filtro per il report. Si supponga ad esempio che siamo la visualizzazione di Malware in soluzioni:
  
![Passare a gestione rischio \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Fare clic su **Detonazione degli strumenti di analisi** nei risultati grafico in una visualizzazione simile alla seguente: 
  
![Explorer filtrato in modo da visualizzare solo i risultati detonazione ATO](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
In questa visualizzazione ora stiamo dati per i file che sono stati detonated per [Gli allegati sicuri di Office 365 degli strumenti di analisi](atp-safe-attachments.md). Sotto il grafico, è possibile visualizzare i dettagli relativi messaggi di posta elettronica specifico con allegati che sono stati rilevati per gli allegati sicuri degli strumenti di analisi.
  
![Informazioni specifiche sui messaggi di posta elettronica con allegati rilevati](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
Selezionando uno o più elementi viene attivato il menu **Azioni** , che è disponibili diverse opzioni per la scelta per gli elementi selezionati da. 
  
![Seleziona una voce attiva dal menu Azioni](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
La possibilità di filtrare un clic e accedere a informazioni specifiche possibile evitare molto tempo nell'analisi dei rischi.
  
## <a name="how-do-i-get-explorer"></a>Come ottenere Explorer

Soluzioni sono incluse funzionalità di [Business Intelligence di Office 365 rischio](office-365-ti.md). È necessario disporre appropriato [di assegnazione delle autorizzazioni nel centro conformità di protezione di Office 365 e](permissions-in-the-security-and-compliance-center.md), come amministratore della sicurezza o lettore di sicurezza, per poter visualizzare e utilizzare Explorer.
  
## <a name="related-topics"></a>Argomenti correlati

[Report e sui concetti di Office 365 Security &amp; centro conformità](reports-and-insights-in-security-and-compliance.md)
  
[Trovare e analizzare dannoso posta elettronica che è stato recapitato (Business Intelligence rischio di Office 365)](investigate-malicious-email-that-was-delivered.md)
  
[Protezione antispam e antimalware in Office 365](anti-spam-and-anti-malware-protection.md)
  

