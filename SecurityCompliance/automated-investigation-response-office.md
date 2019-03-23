---
title: Indagine automatizzata e risposta (aria) con Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Informazioni sulle funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection.
ms.openlocfilehash: c6cfc03588e580382f673b2e9be8543bfcaf9ac1
ms.sourcegitcommit: f6073deec39a18581ed12abef18728417a52cdf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747562"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a>Indagine automatizzata e risposta (aria) con Office 365

Indagine automatizzata e risposta (AIR) (prossimamente a [Office 365 Threat Investigation and response capabilities](office-365-ti.md)) consente di eseguire indagini automatizzate e il risanamento di minacce ben note che esistono oggi. Leggere questo articolo per ottenere una panoramica di AIR e del modo in cui può essere utile per i team delle operazioni di sicurezza e dell'organizzazione attenuare le minacce in modo più efficace ed efficiente. Per ulteriori informazioni su quando saranno disponibili altre funzionalità in AIR, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="alerts"></a>Avvisi

Gli [avvisi](alert-policies.md#viewing-alerts) rappresentano trigger per i flussi di lavoro del team di operazioni di sicurezza per la risposta agli incidenti. Definire la priorità del set di avvisi corretti per l'analisi e verificare che non vi siano minacce non indirizzate. Quando le indagini sugli avvisi vengono eseguite manualmente, i team delle operazioni di sicurezza devono cercare e correlare le entità (ad esempio, il contenuto, i dispositivi e gli utenti) a rischio di minacce. Tali attività e flussi di lavoro richiedono molto tempo e coinvolgono più strumenti e sistemi. Con AIR, l'analisi e la risposta vengono automatizzate in avvisi chiave per la sicurezza e la gestione delle minacce che attivano automaticamente gli schemi di risposta alla sicurezza. 

Nella versione iniziale di AIR nell'aprile 2019, vengono esaminati automaticamente gli avvisi generati dal seguito dei criteri di avviso per gli eventi Singel. 

1. È stato rilevato un clic URL potenzialmente dannoso
2. Messaggi di posta elettronica segnalati dall'utente come phishing *
3. Messaggi di posta elettronica contenenti malware rimossi dopo il recapito *
4. Messaggi di posta elettronica contenenti gli URL di phishing rimossi dopo il recapito *

* Nota: a questi avvisi è stata assegnata una gravità "inFormativa" nei rispettivi criteri di avviso nel centro sicurezza e conformità con le notifiche di posta elettronica disattivate. Questi possono essere attivati tramite la configurazione dei criteri di avviso.

per visualizzare gli avvisi, nel centro conformità & sicurezza di Office 365 scegliere **avvisi** > **visualizza avvisi**. Selezionare un avviso per visualizzare i dettagli, quindi utilizzare il collegamento **Visualizza analisi** per passare all' [analisi](#investigation-graph)corrispondente.

![Avvisi relativi al collegamento alle indagini](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a>Schemi di sicurezza

Gli schemi di sicurezza sono criteri di back-end che sono al centro dell'automazione in Microsoft Threat Protection. Gli schemi di sicurezza forniti in AIR sono basati su scenari comuni di sicurezza del mondo reale. Un playbook di sicurezza viene avviato automaticamente quando un avviso viene attivato all'interno dell'organizzazione. Dopo che l'avviso è stato attivato, l'oggetto PlayBook associato viene eseguito automaticamente. Il PlayBook esegue un'indagine, esaminando tutti i metadati associati (inclusi i messaggi di posta elettronica, gli utenti, i soggetti, i mittenti e così via) e, in base ai risultati, consiglia una serie di azioni che il team di sicurezza dell'organizzazione può intraprendere per il controllo e l'attenuazione la minaccia. 

Gli schemi di sicurezza che otterrete con AIR sono studiati per affrontare le minacce più frequenti che le organizzazioni devono affrontare oggi. Sono basati sull'input dalle operazioni di sicurezza e dai team di risposta agli incidenti, compresi quelli che aiutano a difendere Microsoft e le risorse dei clienti.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Gli schemi di sicurezza vengono implementati in fasi

Come parte di AIR, i PlayBook di sicurezza stanno per essere implementati in fasi

- **Fase 1 (2019 aprile)**: i PlayBook includono suggerimenti per le azioni riesaminate e approvate dagli amministratori di sicurezza. 

- **Fase 2 (2019 giugno)**: gli amministratori della sicurezza avranno la possibilità di configurare gli schemi di sicurezza per intervenire automaticamente, senza interazione amministrativa.

La fase 1 includerà gli schemi seguenti:
- Messaggio phishing visualizzato dall'utente
- URL fare clic su modifica verdetto 
- Malware rilevato dopo il recapito (ZAP malware)
- Phishing rilevato dopo il recapito dello ZAP (phishing ZAP)
- Indagini manuali tramite posta elettronica (tramite Esplora minacce)

Sono previste diverse altre PlayBook per la fase 2.

### <a name="playbooks-include-investigation-and-recommendations"></a>I PlayBook includono analisi e suggerimenti

Ogni PlayBook include: 
- un'indagine radice, 
- passaggi necessari per identificare e correlare altre potenziali minacce e 
- azioni di correzione delle minacce consigliate.

Ogni passaggio di alto livello include numerosi passaggi secondari eseguiti per fornire una risposta profonda, dettagliata ed esaustiva alle minacce.

## <a name="example-user-reported-phish-message"></a>Esempio: messaggio phishing riferito dall'utente

Quando un utente dell'organizzazione invia un messaggio di posta elettronica e lo segnala a Microsoft tramite il [componente aggiuntivo segnala messaggio per Outlook o Outlook Web Access](enable-the-report-message-add-in.md). In questo modo viene attivato un avviso informativo basato sul sistema che avvia automaticamente il PlayBook di analisi.

Durante la fase di analisi radice, vengono valutati vari aspetti del messaggio di posta elettronica. Queste funzionalità sono:
- Determinazione del tipo di minaccia che potrebbe essere;
- Chi lo ha inviato;
- In cui è stato inviato il messaggio di posta elettronica (infrastruttura di invio);
- Se sono state recapitate o bloccate altre istanze del messaggio di posta elettronica;
- Una valutazione dei nostri analisti;
- Se il messaggio di posta elettronica è associato a qualsiasi campagna Nota;
- e altro ancora.

Dopo aver completato l'analisi radice, il PlayBook fornisce un elenco delle azioni consigliate da eseguire.
  
Successivamente, vengono eseguiti diversi passaggi di indagine e di ricerca di minacce:

- Vengono ricercati messaggi di posta elettronica simili in altri cluster di posta elettronica.
- Il segnale viene condiviso con altre piattaforme, ad esempio [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).
- Si determina se gli utenti hanno fatto clic su eventuali collegamenti nei messaggi di posta elettronica sospetti.
- Viene effettuato un controllo in Office 365 Exchange Online Protection ([EOP]) (EOP/Exchange-Online-Protection-EOP. MD) e Office 365 Advanced Therat Protection ([ATP]) (Office-365-atp.md) per verificare se sono presenti altri messaggi simili segnalati dagli utenti.
- Viene effettuato un controllo per verificare se un utente è stato compromesso. Questa verifica utilizza i segnali di [Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security) e [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlando eventuali anomalie relative all'attività degli utenti. 

Durante la fase di caccia, i rischi e le minacce sono assegnati a vari passaggi di caccia.  

La correzione è la fase finale del PlayBook. Durante questa fase, vengono eseguite le operazioni di correzione, in base alle fasi di theinvestigation e di caccia.  

## <a name="getting-started"></a>Introduzione

Per accedere alle indagini, come amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza, passare a Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) ed eseguire l'accesso. Eseguire una delle operazioni seguenti:

- Nella barra di spostamento a sinistra, andare a > **indagini**sulla **gestione delle minacce**.

    oppure

- Visitare il dashboard di gestione delle minacce (nel centro sicurezza e conformità di &, accedere a **Threat Management** > **Dashboard**).

![Widget aria](media/air-widgets.png)

I widget aria verranno visualizzati nella parte superiore del dashboard di [sicurezza](security-dashboard.md). Selezionare un widget per iniziare.

È inoltre possibile accedere a un invesitgation direttamente dagli avvisi correlati.

### <a name="automated-investigations"></a>Indagini automatizzate

Nella pagina indagini automatizzate vengono visualizzate le indagini dell'organizzazione e gli stati correnti.

![Pagina di ricerca principale per AIR](media/air-maininvestigationpage.png) 
  
È possibile:
- Passare direttamente a un'indagine (selezionare un **ID di ricerca**).
- Applicare filtri. Scegliere tra il **tipo di analisi**, l'intervallo di **tempo**, **lo stato**o una combinazione di questi.
- Esportare i dati in un file CSV.

### <a name="investigation-graph"></a>Grafico di analisi

Quando si apre una specifica indagine, viene visualizzata la pagina del grafico delle indagini. In questa pagina vengono illustrate tutte le diverse entità: messaggi di posta elettronica, utenti (e loro attività) e dispositivi che sono stati analizzati automaticamente come parte dell'avviso che è stato attivato.

![Pagina del grafico dell'indagine AEREa](media/air-investigationgraphpage.png)

È possibile:
- Ottenere una panoramica visiva dell'indagine corrente.
- Visualizzare un riepilogo dei tempi di analisi.
- Selezionare un nodo nella visualizzazione per visualizzare i dettagli per il nodo.
- Selezionare una scheda all'interno della parte superiore per visualizzare i dettagli per tale scheda.

### <a name="alert-investigation"></a>Indagine sugli avvisi

Nella scheda **avvisi** per un'indagine, è possibile visualizzare gli avvisi rilevanti per l'indagine. I dettagli includono l'avviso che ha attivato l'indagine e altri avvisi, ad esempio l'accesso a rischio, il download di massa e così via, che sono correlati all'inchiesta. Da questa pagina, un analista di sicurezza può anche visualizzare ulteriori dettagli sui singoli avvisi.

![Pagina avvisi aria](media/air-investigationalertspage.png)

È possibile:
- Ottenere una panoramica visiva dell'avviso di attivazione corrente e degli eventuali avvisi associati.
- Selezionare un avviso nell'elenco per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.

### <a name="email-investigation"></a>Indagine tramite posta elettronica

Nella scheda **posta elettronica** per un'indagine, è possibile visualizzare tutti i cluster di posta elettronica identificati come parte dell'indagine. 

Dato il volume totale di messaggi di posta elettronica che gli utenti di un'organizzazione inviano e ricevono, il processo di 
- clustering dei messaggi di posta elettronica basati su attributi simili provenienti da un'intestazione, un corpo, un URL e un allegato del messaggio; 
- separazione di messaggi di posta elettronica dannosi dal buon messaggio di posta elettronica; e 
- esecuzione di un'azione su messaggi di posta elettronica dannosi 

può richiedere molte ore. AIR ora automatizza questo processo, salvando il tempo e lo sforzo del team di sicurezza dell'organizzazione. 

Si consideri, ad esempio, lo scenario seguente. Il primo gruppo di tre messaggi di posta elettronica è stato ritenuto phishing. Un altro gruppo di messaggi simili con lo stesso IP e l'oggetto è stato trovato e considerato dannoso, in quanto alcuni di essi sono stati identificati come phishing durante il rilevamento iniziale. 

![Pagina di ricerca della posta elettronica AEREa](media/air-investigationemailpage.png)

È possibile:
- Ottenere una panoramica visiva dei risultati del clustering corrente e delle minacce trovate.
- Fare clic su un'entità cluster o su un elenco di minacce per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.

![Messaggi di posta elettronica di analisi AEREa con dettagli a comparsa](media/air-investigationemailpageflyoutdetails.png)

* Nota: nel contesto della posta elettronica, è possibile che venga visualizzata una superficie di minaccia per l'anomalia dei volumi come parte dell'indagine. Un'anomalia del volume indica un picco nei messaggi di posta elettronica simili attorno al tempo dell'evento di indagine rispetto ai tempi precedenti. Questo picco del traffico di posta elettronica con caratteristiche simili (ad esempio, dominio del mittente e del soggetto, somiglianza del corpo e IP del mittente) è tipico dell'inizio delle campagne di posta elettronica o degli attacchi. Tuttavia, le campagne di posta elettronica in blocco e spom, a volte condividono anche queste caratteristiche. Le anomalie dei volumi rappresentano una potenziale minaccia e, di conseguenza, potrebbero essere meno gravi rispetto alle minacce di malware o phishing identificate con motori anti-virus, detonazione o reputazione dannosa.

### <a name="user-investigation"></a>Analisi degli utenti

Nella scheda **utenti** è possibile visualizzare tutti gli utenti identificati come parte dell'indagine. 

Ad esempio, nell'immagine seguente, l'aria ha identificato indicatori di compromesso e anomalie basate su una nuova regola di posta in arrivo che è stata creata. Ulteriori dettagli (prova) dell'indagine sono disponibili tramite visualizzazioni dettagliate all'interno di questa scheda. gli indicatori di compromesso e anomalie possono includere anche rilevamenti di anomalie dalla [sicurezza delle app cloud di Microsoft](https://docs.microsoft.com/cloud-app-security).

![Pagina utenti di analisi AEREa](media/air-investigationuserspage.png)

È possibile:
- Ottenere una panoramica visiva dei risultati e dei rischi individuati dall'utente.
- Selezionare un utente per l'apertura di una pagina di fly-out che Visualizza i dettagli degli avvisi completi.

### <a name="machine-investigation"></a>Indagine del computer

Nella scheda **computer** , è possibile visualizzare tutti i computer identificati come parte dell'indagine. 

![Pagina macchina dell'analisi AEREa](media/air-investigationmachinepage.png)

Nell'ambito dell'inchiesta, AIR correla le minacce alla posta elettronica ai dispositivi. Ad esempio, un'analisi passa un hash di file su [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) per esaminare. Questo consente l'analisi automatizzata delle macchine rilevanti per gli utenti e contribuisce a garantire che le minacce vengano affrontate sia nel cloud che nei dispositivi. 

È possibile:
- Ottenere una panoramica visiva dei computer e delle minacce correnti trovati.
- Selezionare un computer per aprire una visualizzazione che si riferisce alle [indagini di Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) ATP correlate in Windows Defender ATP Security Center.

### <a name="entity-investigation"></a>Indagine su entità

Nella scheda **entità** , è possibile visualizzare tutti i computer identificati come parte dell'indagine. 

In questa sezione, è possibile visualizzare le entità indagate. È possibile visualizzare i dettagli dei tipi di entità, ad esempio i messaggi di posta elettronica, i cluster, gli indirizzi IP, gli utenti e altro ancora. È inoltre possibile vedere quante entità sono state analizzate e le minacce che sono state associate a ognuna di esse. 

![Pagina delle entità di indagine AEREa](media/air-investigationentitiespage.png)

È possibile:
- Ottenere una panoramica visiva delle entità investigative e delle minacce trovate.
- Selezionare un'entità per aprire una pagina di volo che Visualizza il dettaglio dell'entità correlata.

![Dettagli sulle entità di indagine AEREa](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Registro PlayBook

Nella scheda **log** , è possibile visualizzare tutti i passaggi del PlayBook che si sono verificati durante l'indagine. Il log acquisisce un inventario completo di tutte le azioni completate dalle funzionalità di analisi automatica di Office 365 come parte di AIR. Viene fornita una chiara visualizzazione di tutti i passaggi, tra cui l'azione stessa, una descrizione e la durata dell'effettiva dall'inizio alla fine. 

![Pagina del registro delle indagini AEREe](media/air-investigationlogpage.png)

È possibile:
- Ottenere una panoramica visiva dei passaggi di PlayBook eseguiti.
- Esportare i risultati in un file CSV.
- Filtrare la visualizzazione.

### <a name="recommended-actions"></a>Azioni consigliate

Nella scheda **azioni** , è possibile visualizzare tutte le azioni di PlayBook consigliate per la correzione dopo il completamento dell'indagine. 

Azioni acquisire i passaggi consigliati da Microsoft al termine di un'indagine. È possibile eseguire le azioni di correzione selezionando una o più azioni. Se si fa clic su **approva** , verrà avviata la correzione. (Sarà necessario disporre delle autorizzazioni appropriate. Ad esempio, un lettore di sicurezza è in grado di visualizzare le azioni, ma non di approvarle.  

![Pagina azione indagini AEREe](media/air-investigationactionspage.png)

È possibile:
- Ottenere una panoramica visiva delle azioni consigliate in PlayBook.
- Selezionare una singola azione o più azioni.
- ApProvare o rifiutare le azioni consigliate con i commenti.
- Esportare i risultati in un file CSV.
- Filtrare la visualizzazione.

## <a name="how-to-get-air"></a>Come ottenere aria

Attualmente, Office 365 AIR è in anteprima. Office 365 AIR verrà incluso nelle sottoscrizioni seguenti:

- Microsoft 365 Enterprise E5
- Office 365 Enterprise E5
- Microsoft Threat Protection
- Office 365 Advanced Threat Protection piano 2

Per ulteriori informazioni sulla disponibilità delle funzionalità, visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).
