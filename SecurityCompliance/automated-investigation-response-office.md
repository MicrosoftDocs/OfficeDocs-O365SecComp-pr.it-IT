---
title: Indagine automatizzata e risposta (aria) con Office 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Informazioni sulle funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection.
ms.openlocfilehash: 3e74fd7a12727880164797f076d254416325713a
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598522"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a>Indagine automatizzata e risposta (aria) con Office 365

L'analisi e la risposta automatizzate (AIR) (attualmente nell'anteprima pubblica come una delle numerose [funzionalità di analisi e risposta alle minacce di Office 365](office-365-ti.md)) consentono di eseguire indagini e correzioni automatizzate su minacce ben note che esistono oggi. Leggere questo articolo per ottenere una panoramica di AIR e del modo in cui può essere utile per i team delle operazioni di sicurezza e dell'organizzazione attenuare le minacce in modo più efficace ed efficiente. 

Per ulteriori informazioni su quando saranno disponibili le funzionalità AEREe, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="alerts"></a>Avvisi

Gli [avvisi](alert-policies.md#viewing-alerts) rappresentano trigger per i flussi di lavoro del team di operazioni di sicurezza per la risposta agli incidenti. Definire la priorità del set di avvisi appropriato per l'analisi, assicurandosi che non vi siano minacce non indirizzate. Quando le indagini sugli avvisi vengono eseguite manualmente, i team delle operazioni di sicurezza devono cercare e correlare le entità (ad esempio, il contenuto, i dispositivi e gli utenti) a rischio di minacce. Tali attività e flussi di lavoro richiedono molto tempo e coinvolgono più strumenti e sistemi. Con AIR, l'analisi e la risposta vengono automatizzate in avvisi chiave per la sicurezza e la gestione delle minacce che attivano automaticamente gli schemi di risposta alla sicurezza. 

Nella versione iniziale di AIR del 2019 aprile, gli avvisi generati dai criteri di avviso dei singoli eventi vengono analizzati automaticamente. 

1. È stato rilevato un clic URL potenzialmente dannoso
2. Messaggi di posta elettronica segnalati dall'utente come phishing *
3. Messaggi di posta elettronica contenenti malware rimossi dopo il recapito *
4. Messaggi di posta elettronica contenenti gli URL di phishing rimossi dopo il recapito *

> [!NOTE]
> A questi avvisi è stata assegnata una gravità "informativa" nei rispettivi criteri di avviso nel centro sicurezza & conformità con le notifiche di posta elettronica disattivate. Questi possono essere attivati tramite la configurazione dei criteri di avviso.

Per visualizzare gli avvisi, nel centro sicurezza & conformità scegliere **avvisi** > **Visualizza avvisi**. Selezionare un avviso per visualizzare i dettagli, quindi utilizzare il collegamento **Visualizza analisi** per passare all' [analisi](#investigation-graph)corrispondente. Tenere presente che gli avvisi informativi sono nascosti nella visualizzazione avviso per impostazione predefinita. Per visualizzarli, è necessario modificare il filtro degli avvisi per includere gli avvisi informativi.

Se l'organizzazione gestisce gli avvisi di sicurezza tramite un sistema di gestione degli avvisi, un sistema di gestione dei servizi o un sistema di gestione eventi e informazioni di sicurezza, è possibile inviare avvisi di Office 365 a tale sistema tramite notifica tramite posta elettronica o tramite la [ API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). Le notifiche degli avvisi di analisi tramite posta elettronica o API includono collegamenti per accedere agli avvisi nel centro sicurezza & conformità, consentendo all'amministratore della sicurezza assegnato di passare rapidamente all'indagine.

![Avvisi relativi al collegamento alle indagini](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a>Schemi di sicurezza

Gli schemi di sicurezza sono criteri di back-end che sono al centro dell'automazione in Microsoft Threat Protection. Gli schemi di sicurezza forniti in AIR sono basati su scenari comuni di sicurezza del mondo reale. Un playbook di sicurezza viene avviato automaticamente quando un avviso viene attivato all'interno dell'organizzazione. Dopo che l'avviso è stato attivato, l'oggetto PlayBook associato viene eseguito automaticamente. Il PlayBook esegue un'indagine, esaminando tutti i metadati associati (compresi messaggi di posta elettronica, utenti, soggetti, mittenti e così via). In base ai risultati del PlayBook, AIR consiglia una serie di azioni che il team di sicurezza dell'organizzazione può intraprendere per controllare e mitigare la minaccia. 

Gli schemi di sicurezza che otterrete con AIR sono studiati per affrontare le minacce più frequenti che le organizzazioni devono affrontare oggi. Sono basati sull'input dalle operazioni di sicurezza e dai team di risposta agli incidenti, compresi quelli che aiutano a difendere Microsoft e le risorse dei clienti.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Gli schemi di sicurezza vengono implementati in fasi

Come parte di AIR, i PlayBook di sicurezza stanno per essere implementati in fasi

- **Fase 1 (2019 aprile)**: i PlayBook includono suggerimenti per le azioni riesaminate e approvate dagli amministratori di sicurezza. La fase 1 includerà gli schemi seguenti:
    - Messaggio phishing visualizzato dall'utente
    - URL fare clic su modifica verdetto 
    - Malware rilevato dopo il recapito (ZAP malware)
    - Phishing rilevato dopo il recapito dello ZAP (phishing ZAP)
    - Indagini manuali tramite posta elettronica (tramite Esplora minacce)

- **Fase 2 (seconda metà del 2019)**: diversi nuovi PlayBook e miglioramenti al PlayBook, oltre all'opzione per gli amministratori della sicurezza di configurare gli schemi di sicurezza per intraprendere alcune azioni automaticamente senza interazione amministrativa. 

### <a name="playbooks-include-investigation-and-recommendations"></a>I PlayBook includono analisi e suggerimenti

Ogni PlayBook include: 
- un'indagine radice, 
- passaggi necessari per identificare e correlare altre potenziali minacce e 
- azioni di correzione delle minacce consigliate.

Ogni passaggio di alto livello include numerosi passaggi secondari eseguiti per fornire una risposta profonda, dettagliata ed esaustiva alle minacce.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Esempio: un messaggio di phishing riferito dall'utente avvia un playbook di analisi

Quando un utente dell'organizzazione invia un messaggio di posta elettronica e lo segnala a Microsoft utilizzando il [componente aggiuntivo per i messaggi di report per Outlook o Outlook Web Access](enable-the-report-message-add-in.md), il report viene inviato anche al sistema ed è visibile in Esplora nella visualizzazione segnalata dall'utente. Questo messaggio visualizzato dall'utente ora attiva un avviso informativo basato sul sistema, che avvia automaticamente il PlayBook di analisi.

Durante la fase di analisi radice, vengono valutati vari aspetti del messaggio di posta elettronica. Queste funzionalità sono:
- Determinazione del tipo di minaccia che potrebbe essere;
- Chi lo ha inviato;
- In cui è stato inviato il messaggio di posta elettronica (infrastruttura di invio);
- Se sono state recapitate o bloccate altre istanze del messaggio di posta elettronica;
- Una valutazione dei nostri analisti;
- Se il messaggio di posta elettronica è associato a qualsiasi campagna Nota;
- e altro ancora.

Dopo aver completato l'analisi radice, il PlayBook fornisce un elenco delle azioni consigliate da intraprendere sul messaggio di posta elettronica originale e le entità ad esso associate.
  
Successivamente, vengono eseguiti diversi passaggi di indagine e di ricerca di minacce:

- Vengono ricercati messaggi di posta elettronica simili in altri cluster di posta elettronica.
- Il segnale viene condiviso con altre piattaforme, ad esempio [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Si determina se gli utenti hanno fatto clic su eventuali collegamenti dannosi nei messaggi di posta elettronica sospetti.
- Viene effettuato un controllo in Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) e Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) per verificare se sono presenti altri messaggi simili segnalati dagli utenti.
- Viene effettuato un controllo per verificare se un utente è stato compromesso. Questa verifica utilizza i segnali di [Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security) e [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlando eventuali anomalie relative all'attività degli utenti. 

Durante la fase di caccia, i rischi e le minacce sono assegnati a vari passaggi di caccia. 

La correzione è la fase finale del PlayBook. Durante questa fase, vengono eseguite le operazioni di correzione, in base alle fasi di ricerca e caccia. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Esempio: un amministratore della sicurezza attiva un'indagine da Esplora minacce

Oltre alle indagini automatiche attivate da un avviso, il team delle operazioni di sicurezza dell'organizzazione può attivare un'analisi automatica da una visualizzazione in [Esplora minacce](use-explorer-in-security-and-compliance.md).

Si supponga, ad esempio, di visualizzare i dati in Esplora informazioni sui messaggi segnalati dall'utente. È possibile selezionare un elemento nell'elenco dei risultati e quindi fare clic su **indaga**.

![Messaggi segnalati dall'utente in Esplora con il pulsante indaga](media/Explorer-UserReported-Investigate.png)

Come un altro esempio, si supponga di visualizzare i dati relativi ai messaggi di posta elettronica rilevati come contenenti malware e che sono stati rilevati diversi messaggi di posta elettronica come contenenti malware. È possibile selezionare la scheda **posta elettronica** , selezionare uno o più messaggi di posta elettronica e quindi scegliere **indaga**dal menu **azioni** . 

![Avvio di un'indagine per malware in Esplora risorse](media/Explorer-Malware-Email-ActionsInvestigate.png)

Analogamente ai PlayBook attivati da un avviso, le indagini automatiche che vengono attivate da una visualizzazione in Esplora risorse includono un'analisi radice, procedure per identificare e correlare le minacce e le azioni consigliate per attenuare tali minacce.

## <a name="get-started"></a>Attività iniziali

Per accedere alle indagini, come un amministratore globale di Office 365, un amministratore della sicurezza o un lettore di sicurezza, passare al centro sicurezza &[https://protection.office.com](https://protection.office.com)conformità () ed eseguire l'accesso. Eseguire una delle operazioni seguenti:

- Nella barra di spostamento a sinistra, **** > passare a avvisi**visualizzazione**avvisi, aprire uno degli avvisi correlati all'analisi, quindi fare clic sul collegamento **Visualizza analisi** nella parte inferiore del riquadro a comparsa di avviso. 

    oppure

- Nella barra di spostamento a sinistra, andare a > **indagini**sulla **gestione delle minacce**.

    oppure

- Visitare il dashboard di gestione delle minacce (nel centro sicurezza & conformità, accedere a **Threat Management** > **Dashboard**).

![Widget aria](media/air-widgets.png)

I widget aria verranno visualizzati nella parte superiore del dashboard di [sicurezza](security-dashboard.md). Selezionare un widget per iniziare.

È inoltre possibile accedere a un'indagine direttamente dagli avvisi correlati.

### <a name="automated-investigations"></a>Indagini automatizzate

Nella pagina indagini automatizzate vengono visualizzate le indagini dell'organizzazione e gli stati correnti.

![Pagina di ricerca principale per AIR](media/air-maininvestigationpage.png) 
  
È possibile:
- Passare direttamente a un'indagine (selezionare un **ID di ricerca**).
- Applicare filtri. Scegliere tra il **tipo di analisi**, l'intervallo di **tempo**, **lo stato**o una combinazione di questi.
- Esportare i dati in un file CSV.

Lo stato dell'indagine indica lo stato di avanzamento dell'analisi e delle azioni. Durante l'esecuzione dell'indagine, lo stato cambierà per indicare se sono state trovate minacce e indicare se le azioni sono state approvate. 
- **Inizio**: l'analisi viene accodata per iniziare a breve
- **Running**: l'inchiesta è iniziata e sta conducendo la propria analisi
- **Non sono state trovate minacce**: l'inchiesta ha completato l'analisi e non sono state trovate minacce
- **Terminato dal sistema**: l'inchiesta non è stata chiusa ed è scaduta dopo 7 giorni
- **Azione in sospeso**: l'inchiesta ha rilevato minacce con azioni consigliate
- **Minacce trovate**: l'inchiesta ha rilevato minacce, ma le minacce non sono disponibili in Air
- **Correzione**: la investgation è stata completata ed è stata completamente rimediata (tutte le azioni sono state approvate)
- **Parzialmente**rimediato: l'inchiesta è terminata e sono state approvate alcune delle azioni consigliate
- **Terminato dall'utente**: un amministratore ha terminato l'indagine
- **Failed**: si è verificato un errore durante l'analisi che impediva di raggiungere una conclusione sulle minacce
- **Accodamento tramite limitazione**: l'analisi è in attesa di essere analizzata a causa di limitazioni di elaborazione del sistema (per proteggere le prestazioni del servizio)
- **Terminata mediante limitazione**: l'analisi non è stata completata in tempi sufficienti a causa di limitazioni dell'elaborazione del volume e del sistema di analisi. È possibile riattivare l'indagine selezionando il messaggio di posta elettronica in Esplora risorse e selezionando l'azione indaga.

### <a name="investigation-graph"></a>Grafico di analisi

Quando si apre una specifica indagine, viene visualizzata la pagina del grafico delle indagini. In questa pagina vengono illustrate tutte le diverse entità: messaggi di posta elettronica, utenti (e loro attività) e dispositivi che sono stati analizzati automaticamente come parte dell'avviso che è stato attivato.

![Pagina del grafico dell'indagine aerea](media/air-investigationgraphpage.png)

È possibile:
- Ottenere una panoramica visiva dell'indagine corrente.
- Visualizzare un riepilogo della durata dell'indagine.
- Selezionare un nodo nella visualizzazione per visualizzare i dettagli per il nodo.
- Selezionare una scheda all'interno della parte superiore per visualizzare i dettagli per tale scheda.

### <a name="alert-investigation"></a>Indagine sugli avvisi

Nella scheda **avvisi** per un'indagine, è possibile visualizzare gli avvisi rilevanti per l'indagine. I dettagli includono l'avviso che ha attivato l'indagine e altri avvisi, ad esempio l'accesso a rischio, il download di massa e così via, che sono correlati all'inchiesta. Da questa pagina, un analista di sicurezza può anche visualizzare ulteriori dettagli sui singoli avvisi.

![Pagina avvisi aria](media/air-investigationalertspage.png)

È possibile:
- Ottenere una panoramica visiva dell'avviso di attivazione corrente e degli eventuali avvisi associati.
- Selezionare un avviso nell'elenco per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.

### <a name="email-investigation"></a>Indagine tramite posta elettronica

Nella scheda **posta elettronica** per un'indagine, è possibile visualizzare tutti i cluster di messaggi di posta elettronica identificati come parte dell'indagine. 

Dato il volume totale di messaggi di posta elettronica che gli utenti di un'organizzazione inviano e ricevono, il processo di 
- clustering dei messaggi di posta elettronica basati su attributi simili provenienti da un'intestazione, corpo, URL e allegati del messaggio; 
- separazione di messaggi di posta elettronica dannosi dal buon messaggio di posta elettronica; e 
- esecuzione di un'azione su messaggi di posta elettronica dannosi 

può richiedere molte ore. AIR ora automatizza questo processo, salvando il tempo e lo sforzo del team di sicurezza dell'organizzazione. 

Durante il passaggio di analisi della posta elettronica sono stati identificati due tipi di cluster di posta elettronica, ovvero i cluster di somiglianza e gli indicatori. 
- I cluster di somiglianza sono messaggi di posta elettronica che contengono attributi di contenuto e mittente simili. Tali cluster vengono valutati per i contenuti dannosi in base ai risultati di rilevamento originali. I cluster di posta elettronica che contengono un numero sufficiente di rilevamenti dannosi saranno considerati dannosi.
- I cluster di indicatori sono messaggi di posta elettronica che contengono la stessa entità indicatore (hash di file o URL) del messaggio di posta elettronica originale. Quando l'entità file/URL originale viene identificata come dannosa, l'aria applicherà l'indicatore verdetto all'intero gruppo di messaggi di posta elettronica che contiene tale entità. Come un file identificato come malware significherà che il cluster di messaggi di posta elettronica che contiene il file verrà considerato come messaggio di posta elettronica antimalware.

L'obiettivo del clustering consiste nel reperire altri messaggi di posta elettronica correlati inviati dallo stesso mittente come parte di un attacco o di una campagna.

La scheda **posta elettronica** mostrerà anche gli elementi di posta elettronica relativi all'indagine, ad esempio i dettagli di posta elettronica segnalati dall'utente, il messaggio di posta elettronica originale riportato, i messaggi di posta elettronica con zapping a causa di malware/phishing e così via.

Il numero di messaggi di posta elettronica identificati nella scheda posta elettronica rappresenta attualmente la somma totale di tutti gli SMS visualizzati nella scheda **posta elettronica** . Poiché i messaggi di posta elettronica saranno presenti in più cluster, il conteggio totale effettivo dei messaggi di posta elettronica identificati (ed è influenzato dalle azioni correttive) sarà il numero di messaggi di posta elettronica univoci presenti in tutti i cluster e la posta elettronica dei destinatari originali. messaggi. 

Entrambi i messaggi di posta elettronica di Explorer e conteggio aria sono per ogni destinatario, in quanto i verdetti di sicurezza, le azioni e i percorsi di recapito variano in base al destinatario. Pertanto, un messaggio di posta elettronica originale inviato a tre utenti conterà come un totale di tre messaggi di posta elettronica anziché un solo messaggio di posta elettronica. Nota potrebbero verificarsi casi in cui un messaggio di posta elettronica viene contato due o più volte, poiché il messaggio di posta elettronica può avere più azioni su di esso e potrebbe essere più copie del messaggio di posta elettronica una volta che tutte le azioni si verificano. Ad esempio, un messaggio di posta elettronica antimalware rilevato al momento del parto può comportare sia un messaggio di posta elettronica bloccato (in quarantena) che un messaggio di posta elettronica sostituito (file di minacce sostituito da un file di avviso, quindi recapitato alla cassetta postale Poiché vi sono letteralmente due copie del messaggio di posta elettronica nel sistema, queste possono essere entrambe conteggiate nei conteggi dei cluster. 

I conteggi dei messaggi di posta elettronica vengono calcolati al momento dell'indagine e alcuni conteggi vengono ricalcolati quando si apre l'indagine comparsa (in base a una query sottostante). Il numero di messaggi di posta elettronica visualizzati per i cluster di posta elettronica nella scheda posta elettronica e il valore della quantità di posta elettronica visualizzato nel riquadro a comparsa del cluster vengono calcolati al momento dell'indagine. Il numero di posta elettronica visualizzato nella parte inferiore della scheda posta elettronica del riquadro a comparsa del cluster e il numero di messaggi di posta elettronica visualizzati in Esplora riflettono i messaggi di posta elettronica ricevuti dopo l'analisi iniziale dell'indagine. In questo modo un cluster di posta elettronica che mostra una quantità originale di 10 messaggi di posta elettronica mostrerà una lista di posta elettronica pari a 15 quando 5 messaggi di posta elettronica arrivano tra la fase di analisi dell'inchiesta e quando l'amministratore esamina l'indagine. La visualizzazione di entrambi i conteggi in visualizzazioni diverse viene eseguita per indicare l'impatto della posta elettronica al momento dell'indagine e l'impatto corrente fino al momento in cui viene eseguita la correzione.

Si consideri, ad esempio, lo scenario seguente. Il primo gruppo di tre messaggi di posta elettronica è stato ritenuto phishing. Un altro gruppo di messaggi simili con lo stesso IP e l'oggetto è stato trovato e considerato dannoso, in quanto alcuni di essi sono stati identificati come phishing durante il rilevamento iniziale. 

![Pagina di ricerca della posta elettronica AEREa](media/air-investigationemailpage.png)

È possibile:
- Ottenere una panoramica visiva dei risultati del clustering corrente e delle minacce trovate.
- Fare clic su un'entità cluster o su un elenco di minacce per aprire una pagina di volo che Visualizza i dettagli degli avvisi completi.
- Esaminare ulteriormente il cluster di posta elettronica facendo clic sul collegamento ' Apri in Esplora risorse ' nella parte superiore della scheda ' dettagli cluster di posta elettronica '

![Messaggi di posta elettronica di analisi AEREa con dettagli a comparsa](media/air-investigationemailpageflyoutdetails.png)

* Nota: nel contesto della posta elettronica, è possibile che venga visualizzata una superficie di minaccia per l'anomalia dei volumi come parte dell'indagine. Un'anomalia del volume indica un picco nei messaggi di posta elettronica simili nei pressi del tempo dell'evento di indagine rispetto ai tempi precedenti. Questo picco del traffico di posta elettronica con caratteristiche simili (ad esempio, dominio del mittente e del soggetto, somiglianza del corpo e IP del mittente) è tipico dell'inizio delle campagne di posta elettronica o degli attacchi. Tuttavia, la massa, la posta indesiderata e le campagne di posta elettronica legittime condividono queste caratteristiche. Le anomalie dei volumi rappresentano una potenziale minaccia e, di conseguenza, potrebbero essere meno gravi rispetto alle minacce di malware o phishing identificate con motori anti-virus, detonazione o reputazione dannosa.

### <a name="user-investigation"></a>Analisi degli utenti

Nella scheda **utenti** è possibile visualizzare tutti gli utenti identificati come parte dell'indagine. Gli utenti verranno visualizzati nell'inchiesta quando è presente un evento o un'indicazione del fatto che l'utente può essere influenzato o compromesso.

Ad esempio, nell'immagine seguente, l'aria ha identificato indicatori di compromesso e anomalie basate su una nuova regola di posta in arrivo che è stata creata. Ulteriori dettagli (prova) dell'indagine sono disponibili tramite visualizzazioni dettagliate all'interno di questa scheda. gli indicatori di compromesso e anomalie possono includere anche rilevamenti di anomalie dalla [sicurezza delle app cloud di Microsoft](https://docs.microsoft.com/cloud-app-security).

![Pagina utenti di analisi AEREa](media/air-investigationuserspage.png)

È possibile:
- Ottenere una panoramica visiva dei risultati e dei rischi individuati dall'utente.
- Selezionare un utente per l'apertura di una pagina di fly-out che Visualizza i dettagli degli avvisi completi.

### <a name="machine-investigation"></a>Indagine del computer

Nella scheda **computer** , è possibile visualizzare tutti i computer identificati come parte dell'indagine. 

![Pagina macchina dell'analisi aerea](media/air-investigationmachinepage.png)

Nell'ambito dell'inchiesta, AIR correla le minacce alla posta elettronica ai dispositivi. Ad esempio, un'analisi passa un hash di file dannosi a [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) per esaminare. Questo consente l'analisi automatizzata delle macchine rilevanti per gli utenti, per garantire che le minacce vengano affrontate sia nel cloud che negli endpoint. 

È possibile:
- Ottenere una panoramica visiva dei computer e delle minacce correnti trovati.
- Selezionare un computer per aprire una visualizzazione che si riferisce alle [indagini ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) correlate in Microsoft Defender Security Center.

### <a name="entity-investigation"></a>Indagine su entità

Nella scheda **entità** , è possibile visualizzare tutte le entità identificate come parte dell'indagine. 

In questa sezione, è possibile visualizzare le entità indagate e i dettagli dei tipi di entità, ad esempio i messaggi di posta elettronica, i cluster, gli indirizzi IP, gli utenti e altro ancora. È inoltre possibile vedere quante entità sono state analizzate e le minacce che sono state associate a ognuna di esse. 

![Pagina delle entità di indagine AEREa](media/air-investigationentitiespage.png)

È possibile:
- Ottenere una panoramica visiva delle entità investigative e delle minacce trovate.
- Selezionare un'entità per aprire una pagina di fly-out che Visualizza i dettagli dell'entità correlata.

![Dettagli sulle entità di indagine AEREa](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Registro PlayBook

Nella scheda **log** , è possibile visualizzare tutti i passaggi del PlayBook che si sono verificati durante l'indagine. Il log acquisisce un inventario completo di tutte le azioni completate dalle funzionalità di analisi automatica di Office 365 come parte di AIR. Viene fornita una chiara visualizzazione di tutti i passaggi, tra cui l'azione stessa, una descrizione e la durata dell'effettivo dall'inizio alla fine. 

![Pagina del registro delle indagini AEREe](media/air-investigationlogpage.png)

È possibile:
- Ottenere una panoramica visiva dei passaggi di PlayBook eseguiti.
- Esportare i risultati in un file CSV.
- Filtrare la visualizzazione.

### <a name="recommended-actions"></a>Azioni consigliate

Nella scheda **azioni** , è possibile visualizzare tutte le azioni di PlayBook consigliate per la correzione dopo il completamento dell'indagine. 

Azioni acquisire i passaggi consigliati da Microsoft al termine di un'indagine. È possibile eseguire le azioni di correzione selezionando una o più azioni. Se si fa clic su **approva** , verrà avviata la correzione. (Sono necessarie autorizzazioni appropriate: il ruolo ' Search and Purge ' è necessario per eseguire azioni da Explorer e AIR). Ad esempio, un lettore di sicurezza è in grado di visualizzare le azioni, ma non di approvarle. Nota: non è necessario approvare ogni azione. Se non si è d'accordo con l'azione consigliata o l'organizzazione non sceglie alcuni tipi di azioni, è possibile scegliere di **rifiutare** le azioni o semplicemente ignorarle e non eseguire alcuna azione. L'approvazione e/o il rifiuto di tutte le azioni consentiranno di chiudere completamente l'indagine, lasciando che alcune azioni incomplete provochino lo stato di indagine che cambia in uno stato parzialmente rimediato.

![Pagina azione indagini AEREe](media/air-investigationactionspage.png)

È possibile:
- Ottenere una panoramica visiva delle azioni consigliate in PlayBook.
- Selezionare una singola azione o più azioni.
- Approvare o rifiutare le azioni consigliate con i commenti.
- Esportare i risultati in un file CSV.
- Filtrare la visualizzazione.

## <a name="how-to-get-air"></a>Come ottenere aria

Attualmente, le funzionalità di Office 365 AIR sono in anteprima. Quando si è in genere disponibili, le funzionalità di Office 365 AIR verranno incluse nei seguenti abbonamenti:

- Microsoft 365 Enterprise E5
- Office 365 Enterprise E5
- Microsoft Threat Protection
- Office 365 Advanced Threat Protection piano 2

Per ulteriori informazioni sulla disponibilità delle funzionalità, visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).
