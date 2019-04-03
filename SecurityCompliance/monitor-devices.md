---
title: Monitorare i dispositivi in Sicurezza Microsoft 365
description: Descrive in che modo è possibile mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, dispositivi
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 31d89b8bbcad98814ff33764bad24bffbbba4968
ms.sourcegitcommit: 8213c353954b92f5c3979bee4aa049da0fd28a18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2019
ms.locfileid: "31043257"
---
# <a name="monitor-devices-in-microsoft-365-security"></a>Monitorare i dispositivi in Sicurezza Microsoft 365

Mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nel centro sicurezza Microsoft 365.

## <a name="view-device-alerts"></a>Visualizzare gli avvisi per i dispositivi

Ottenere avvisi aggiornati sull'attività di violazione e altre minacce sui dispositivi da Windows Defender ATP (disponibile con una licenza E5). Microsoft 365 Security Center contiene diverse schede che consentono di monitorare efficacemente gli avvisi a un livello superiore, a seconda del flusso di lavoro preferito.

### <a name="monitor-high-impact-alerts"></a>Monitorare gli avvisi ad impatto elevato

Ogni avviso di Windows Defender ATP ha un livello di gravità corrispondente, alto, medio, basso o informativo, che indica il potenziale impatto della rete se non è presente.  

Utilizzare la scheda **gravità avviso dispositivo** per concentrarsi in modo specifico sugli avvisi più gravi e potrebbe richiedere una risposta immediata. Da questa scheda, è possibile visualizzare ulteriori informazioni su Windows Defender Security Center Portal.

![Scheda di gravità avvisi dispositivo](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Informazioni sulle origini degli avvisi

Windows Defender ATP utilizza i dati provenienti da una vasta gamma di sensori di sicurezza e fonti di intelligence per generare avvisi. Ad esempio, è possibile utilizzare le informazioni di rilevamento di Windows Defender Antivirus e antimalware di terze parti, nonché la propria Intelligence di minacce personalizzata fornita tramite l'API del servizio Web.

La scheda fonti di **rilevamento avvisi dispositivo** Visualizza la distribuzione degli avvisi per origine. Questa scheda può essere utile per monitorare le attività relative a determinate origini, in particolare le origini personalizzate. È inoltre possibile utilizzare questa pagina per concentrarsi sugli avvisi provenienti da sensori che non sono configurati per bloccare automaticamente le attività o i componenti dannosi.

![Scheda fonti di rilevamento avvisi dispositivo](./media/security-docs/device-alert-detection-sources.png)

Da questa scheda, è possibile visualizzare ulteriori informazioni su Windows Defender Security Center Portal.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Comprendere i tipi di minacce che attivano gli avvisi

Windows Defender ATP Ordina ogni avviso in una categoria che rappresenta una determinata fase della catena di attacco o un tipo di componente di minaccia. Ad esempio, l'attività di minacce rilevata potrebbe essere categorizzata in "movimento laterale" per indicare che l'attività implicava un tentativo di raggiungere altri dispositivi sulla rete ed è probabile che si sia verificato dopo che i pirati informatici hanno acquisito un punto di appoggio iniziale. Una volta rilevato, un componente di minacce potrebbe essere classificato come "malware" o più specificamente come "ransomware", "furto di credenziali" o altri tipi di software dannoso o indesiderato.

La scheda **categorie minacce dispositivo** Visualizza la distribuzione degli avvisi in queste categorie. È possibile utilizzare queste informazioni per identificare le attività relative alle minacce, ad esempio i tentativi di furto di credenziali, che possono avere un impatto più significativo rispetto ai tentativi di social engineering. È inoltre possibile utilizzare questa pagina per monitorare le minacce potenzialmente distruttive come ransomware.

![Scheda categorie di minacce per dispositivi](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Monitorare gli avvisi attivi

La scheda **stato avviso dispositivo** indica il numero di avvisi che non sono stati risolti e che potrebbero richiedere attenzione. Da questa scheda, è possibile visualizzare ulteriori informazioni su Windows Defender Security Center Portal.

![Scheda stato avviso dispositivo](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Monitorare la classificazione degli avvisi risolti

Durante la risoluzione di un avviso di Windows Defender ATP, il personale di sicurezza può specificare se un avviso è stato verificato come:

* Un avviso vero che identifica le attività di violazione effettive o i componenti di minaccia
* Un falso avviso che ha rilevato erroneamente attività normale

La scheda di **classificazione avviso dispositivo** indica se gli avvisi risolti sono stati classificati come avvisi veri o falsi. Da questa scheda, è possibile visualizzare ulteriori informazioni su Windows Defender Security Center Portal.

Nota: in alcuni casi, le informazioni di classificazione non sono disponibili per determinati avvisi.

![Scheda di classificazione degli avvisi dei dispositivi](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Monitorare la determinazione degli avvisi risolti

Oltre a classificare se un avviso è vero o falso durante la risoluzione, il personale della sicurezza può fornire una determinazione, indicando il tipo di attività normale o dannosa individuata durante la convalida dell'avviso.

La scheda di **determinazione dell'avviso del dispositivo** Visualizza la determinazione fornita per ogni avviso, in particolare:

* **Apt** – Advanced Persistent Threat, che indica che l'attività rilevata o il componente di minaccia è parte di una sofisticata violazione progettata per ottenere un punto di appoggio nella rete in questione  
* **Malware** : file o codice dannoso
* **Personale di sicurezza** – attività normale eseguita dal personale della sicurezza
* **Test di sicurezza** – attività o componenti studiati per simulare le minacce effettive e per attivare i sensori di sicurezza e generare avvisi
* **Software** indesiderato – app e altri software che non sono considerati dannosi, ma violano in altro modo i criteri o gli standard di utilizzo accettabili
* **Altri** – qualsiasi altra determinazione che non rientra nei tipi forniti

Da questa scheda, è possibile visualizzare altre informazioni in Windows Defender Security Center.

![Scheda di determinazione dell'avviso del dispositivo](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Comprendere quali dispositivi sono a rischio

La **protezione del dispositivo** Visualizza il livello di rischio per i dispositivi. Il livello di rischio si basa su fattori quali il tipo e la gravità degli avvisi nel dispositivo.

![Scheda di protezione del dispositivo](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Monitorare e segnalare lo stato dei dispositivi gestiti da Intune

Il monitoraggio e i report seguenti contengono dati provenienti da dispositivi registrati in Intune. I dati dei dispositivi non registrati non sono inclusi. Solo gli amministratori globali possono visualizzare queste schede.

I dati dei dispositivi registrati di Intune includono:

* Conformità del dispositivo
* Dispositivi con malware attivo
* Tipi di malware nei dispositivi
* Malware nei dispositivi
* Dispositivi con rilevamenti di malware
* Utenti con rilevamenti di malware

### <a name="monitor-device-compliance"></a>Monitorare la conformità del dispositivo

La **conformità del dispositivo** indica il numero di dispositivi registrati in Intune conformi ai criteri di configurazione.

![Scheda conformità dispositivo](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Individuare i dispositivi con rilevamenti di malware

I rilevamenti di **malware per dispositivi** forniscono il numero di dispositivi registrati di Intune con malware che non sono stati completamente risolti a causa di azioni in sospeso, ovvero un riavvio, un'analisi completa o azioni utente manuali oppure se l'operazione di correzione non è stata completata correttamente.

![Scheda rilevamenti malware dispositivo](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Informazioni sui tipi di malware rilevati

I **tipi di malware nei dispositivi** mostrano diversi tipi di malware che sono stati rilevati nei dispositivi registrati in Intune. È possibile esaminare ogni tipo in Microsoft 365 Security Center.

![Tipi di malware sulla scheda dispositivi](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Comprendere il malware specifico rilevato nei dispositivi

**Malware nei dispositivi** fornisce un elenco di malware specifici rilevati nei dispositivi.

![Scheda malware su dispositivi](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Informazioni sui dispositivi con la maggior parte dei malware

I **dispositivi con rilevamenti di malware** mostrano quali dispositivi presentano la maggior parte dei rilevamenti di malware. In Microsoft 365 Security Center è possibile verificare se il malware è attivo, chi usa il dispositivo e lo stato di gestione in Intune.

![Scheda dispositivi con rilevamento malware](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Comprendere quali utenti dispongono di dispositivi con la maggior parte dei malware

**Gli utenti con rilevamenti di malware** visualizzano gli utenti con dispositivi con la maggior parte dei rilevamenti di malware. In Microsoft 365 Security Center, è possibile visualizzare il numero di dispositivi assegnati a ciascun utente e ulteriori informazioni su ogni dispositivo e sul tipo di malware.

![Utenti con scheda di rilevamento antimalware](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>Monitorare e gestire la distribuzione e i rilevamenti delle regole ASR

[Le regole di riduzione dell'attacco superficiale (ASR, Attack Surface Reduction)](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) consentono di prevenire azioni e app che vengono in genere utilizzate da malware in cerca di exploit per infettare macchine Queste regole controllano il modo in cui è possibile eseguire i file eseguibili. Ad esempio, è possibile impedire a JavaScript o VBScript di avviare un file eseguibile scaricato, bloccare le chiamate API Win32 dalle macro di Office o bloccare i processi che vengono eseguiti da unità USB.

![Scheda riduzioni superficie attacco](./media/security-docs/attack-surface-reduction-rules.png)

La scheda **regole di riduzione della superficie di attacco** fornisce una panoramica della distribuzione delle regole tra i dispositivi.

Nella barra superiore della scheda viene visualizzato il numero totale di dispositivi presenti nelle modalità di distribuzione seguenti:

* **Modalità di blocco** – dispositivi con almeno una regola configurata per bloccare l'attività rilevata
* **Modalità di controllo** : i dispositivi con nessuna regola impostata per bloccare l'attività rilevata, ma hanno almeno un set di regole per il controllo dell'attività rilevata  
* **Disattivato** : i dispositivi con tutte le regole ASR sono disattivati

Nella parte inferiore della scheda sono riportate le impostazioni per regola tra i dispositivi. Ogni barra indica il numero di dispositivi che sono impostati per bloccare o controllare il rilevamento oppure la regola è stata completamente disattivata.

### <a name="view-asr-detections"></a>Visualizzazione dei rilevamenti ASR

Per visualizzare informazioni dettagliate sui rilevamenti delle regole di ASR nella rete, selezionare **Visualizza** rilevamenti nella scheda **regole di riduzione della superficie di attacco** . Verrà **** aperta la scheda rilevamenti nella pagina rapporto dettagliato.

![Scheda riLevamenti](./media/security-docs/detections-tab.png)

Il grafico nella parte superiore della pagina Visualizza rilevamenti nel tempo di rilevamenti di sovrapposizione che sono stati bloccati o controllati. La tabella in basso elenca i rilevamenti più recenti. Utilizzare le informazioni seguenti nella tabella per comprendere la natura dei rilevamenti:

* **File rilevato** : il file, in genere uno script o un documento, il cui contenuto ha attivato l'attività di attacco sospetta
* **Rule** – nome che descrive le attività di attacco la regola è progettata per essere intercettata. Leggere le regole ASR esistenti
* **App di origine** : l'applicazione che ha caricato o eseguito contenuto che attiva l'attività di attacco sospetta. Potrebbe trattarsi di un'applicazione legittima, ad esempio il Web browser, un'applicazione di Office o uno strumento di sistema come PowerShell.
* **Publisher** : il fornitore che ha rilasciato l'app di origine

### <a name="review-device-asr-rule-settings"></a>Esaminare le impostazioni della regola di ASR del dispositivo

Nella pagina rapporto **regole di riduzione della superficie di attacco** passare alla scheda **configurazione** per esaminare le impostazioni delle regole per i singoli dispositivi. Selezionare un dispositivo per ottenere informazioni dettagliate sul fatto che ogni regola sia in modalità di blocco, modalità di controllo o disattivata completamente.

![Scheda configurazione](./media/security-docs/configuration-tab.png)

Microsoft Intune offre funzionalità di gestione per le regole di ASR. Se si desidera aggiornare le impostazioni, selezionare **Get Started** in **Configure Devices** nella scheda per aprire Gestione dispositivi su Intune.

### <a name="exclude-files-from-asr-rules"></a>Escludi file dalle regole di ASR

Escludendo i file dai rilevamenti, è possibile impedire rilevamenti falsi positivi indesiderati e distribuire in modo più sicuro le regole di riduzione delle superfici di attacco in modalità di blocco.

Mentre le esclusioni dei file per le regole di riduzione della superficie di attacco vengono gestite su Microsoft Intune, Microsoft 365 Security Center fornisce uno strumento di analisi che consente di comprendere i file che stanno attivando i rilevamenti. Consente inoltre di raccogliere i nomi dei file che si desidera escludere.

Per avviare l'analisi di rilevamenti e la raccolta di file per l'esclusione, passare alla scheda **Aggiungi esclusioni** nella pagina rapporto **regole di riduzione delle superfici attacco** .

![Scheda Aggiungi esclusioni](./media/security-docs/add-exclusions-tab.png)

Nella tabella sono elencati tutti i nomi di file rilevati dalle regole di riduzione della superficie di attacco. Dopo aver selezionato un file o più file, è possibile esaminare l'impatto relativo all'aggiunta di tali file alle eccezioni:

* Riduzione del numero totale di rilevamenti
* Riduzione del numero totale di dispositivi coinvolti nei rilevamenti

Per ottenere un elenco dei file selezionati con i percorsi completi per l'esclusione, selezionare **Ottieni percorsi di esclusione**.

Per ulteriori informazioni sulle esclusioni e sulle istruzioni dettagliate su come aggiungerle, vedere [risolvere i problemi relativi alle regole di riduzione della superficie di attacco](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr).
