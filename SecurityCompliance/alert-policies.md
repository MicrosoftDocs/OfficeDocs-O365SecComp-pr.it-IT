---
title: Avviso criteri in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 8927b8b9-c5bc-45a8-a9f9-96c732e58264
description: Creare criteri di avviso in Office 365 Security &amp; centro conformità per monitorare le potenziali minacce, la perdita di dati e problema di autorizzazioni. È quindi possibile visualizzare e gestire gli avvisi generati quando gli utenti eseguono le attività che soddisfano le condizioni di un criterio di avviso.
ms.openlocfilehash: 6bdbf9c4c352bf16fd1a7b5c9f7b0af7eb4fadfd
ms.sourcegitcommit: a2afa4c06e9b762cf689b0d2a0653076f9b00c49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328142"
---
# <a name="alert-policies-in-the-office-365-security-amp-compliance-center"></a>Avviso criteri in Office 365 Security &amp; centro conformità

È possibile utilizzare il nuovo criterio di avviso e dashboard avviso strumenti in Office 365 Security &amp; centro conformità per creare criteri di avviso e quindi visualizzare gli avvisi generati quando gli utenti eseguono le attività che soddisfano le condizioni di un criterio di avviso. I criteri si basano sulle e aumentano la funzionalità di avvisi attività grazie alla possibilità di classificare i criteri di avviso, applicare il criterio a tutti gli utenti nell'organizzazione, impostare un livello di soglia per quando viene generato un avviso, di avviso e decidere se utilizzare o meno ricezione della posta elettronica notifiche. È inoltre disponibile una pagina **Visualizza avvisi** di sicurezza &amp; degli avvisi centro conformità dove è possibile visualizzare e filtrare i set di stato che consentono di gestire gli avvisi e quindi chiudere degli avvisi dopo aver risolto o risolto il problema sottostante. È stata espansa anche il tipo di eventi che è possibile creare avvisi per. Ad esempio, è possibile creare criteri degli avvisi per tenere traccia delle attività di malware e risolte perdita di dati. Infine, è stato incluso anche un numero di criteri di avviso predefinito che consentono di monitorare l'assegnazione dei privilegi di amministrazione di Exchange Online, attacchi malware e insoliti livelli di eliminazioni di file e condivisione esterna. 
  
> [!NOTE]
> Avvisi criteri sono disponibili per le organizzazioni con Office 365 Enterprise o Office 365 US Government E1/G1, E3/G3 o E5/G5 sottoscrizione. Tuttavia, alcune funzionalità avanzate è disponibile solo per le organizzazioni con una sottoscrizione E5/G5 o per le organizzazioni che dispongono di un E1/G1 o E3/G3 sottoscrizione e una sottoscrizione di componente aggiuntivo Business Intelligence di Office 365 rischio o conformità avanzate di Office 365. Le funzionalità che richiede una sottoscrizione E5/G5 o un componente aggiuntivo viene evidenziata in questo argomento. Si noti inoltre che i criteri degli avvisi sono disponibili in Office 365 le, le elevato e negli ambienti government DoD negli Stati Uniti.
  
## <a name="how-alert-policies-work"></a>Come avviso lavoro criteri

Ecco una rapida panoramica di come avviso lavoro criteri e gli avvisi che rappresentano trigger quando l'utente o l'amministratore attività corrispondenti alle condizioni di un criterio di avviso.
  
![Panoramica di come avviso lavoro criteri](media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)
  
1. Un amministratore dell'organizzazione consente di creare, configurare e consente di attivare un criterio di avviso utilizzando la pagina **criteri di avviso** per la protezione &amp; centro conformità. È inoltre possibile creare criteri di avviso utilizzando il cmdlet **New-ProtectionAlert** in PowerShell. 
    
2. Un utente esegue un'attività che soddisfa le condizioni di un criterio di avviso. Nel caso di attacchi malware, messaggi di posta elettronica che contengono un virus inviati agli utenti dell'organizzazione verranno generato un avviso.
    
3. Office 365 genera un avviso che viene visualizzato nella pagina **Visualizza avvisi** di protezione &amp; centro conformità. Inoltre, se le notifiche di posta elettronica sono abilitate per il criterio di avviso, Office 365 invia una notifica ai destinatari elenco. 
    
4. Gli amministratori consente di gestire gli avvisi di sicurezza &amp; centro conformità. Gestione degli avvisi è costituita assegnazione di stato per tenere traccia e gestire tutte le indagini.
    

  
## <a name="alert-policy-settings"></a>Impostazioni dei criteri degli avvisi

Un criterio di avviso è costituita da un set di regole e le condizioni che definiscono l'utente o l'attività di amministrazione che verrà generato un avviso, un elenco di utenti che attiverà l'avviso effettua le attività e soglia che definisce il numero di volte l'attività è venga sincronizzata prima un avviso n viene attivata. Inoltre suddividere i criteri e assegnare un livello di gravità. Queste due impostazioni consentono di gestire i criteri degli avvisi (e gli avvisi che vengono attivati quando vengono corrispondente alle condizioni del criterio) dal momento che è possibile filtrare queste impostazioni durante la gestione dei criteri e la visualizzazione degli avvisi di sicurezza &amp; centro conformità. Ad esempio, è possibile visualizzare gli avvisi che soddisfano le condizioni dalla categoria stessa o gli avvisi di visualizzazione con lo stesso livello di gravità.
  
Per visualizzare e creare criteri di avviso, passare a **avvisi** \> **criteri degli avvisi** di sicurezza &amp; centro conformità. 
  
![In sicurezza &amp; Complinace interfaccia, fare clic su avvisi, quindi scegliere avviso criteri per visualizzare e creare i criteri di avviso](media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)
  
Un criterio di avviso è costituita da condizioni e le impostazioni seguenti.
  
- **Tiene traccia delle attività dell'avviso** : creazione di un criterio per tenere traccia delle attività o in alcuni casi di alcune attività correlate, ad esempio un condividendo un file con un utente esterno condividerla, assegnando le autorizzazioni di accesso o la creazione di un collegamento anonimo. Quando un utente esegue attività definito dai criteri, viene generato un avviso in base alle impostazioni di soglia di avviso.
    
    > [!NOTE]
    > Le attività che è possibile tenere traccia dipendono dal piano di Office 365 Enterprise o Office 365 US Government dell'organizzazione. In generale, le attività correlate alle campagne di malware e gli attacchi di phishing richiedono una sottoscrizione E5/G5 o una sottoscrizione G1/E1 o E3/G3 con una sottoscrizione a un componente aggiuntivo Business Intelligence di rischio. 
  
- **Condizioni delle attività** - per la maggior parte delle attività, è possibile definire ulteriori condizioni che devono essere soddisfatti per un avviso venga attivato. Condizioni comuni includono IP indirizzi (in modo che un avviso viene generato quando l'utente esegue le attività in un computer con un indirizzo IP specifico o all'interno di un intervallo di indirizzi IP), se è attivato un avviso se un utente specifico o agli utenti di eseguire tale attività e, se l'attività viene eseguita su un nome di file specifico o un URL. È inoltre possibile configurare una condizione che viene generato un avviso quando l'attività viene eseguita da tutti gli utenti nell'organizzazione. Si noti che le condizioni disponibili varia a seconda dell'attività selezionata.
    
- **Quando viene generato l'avviso** - è possibile configurare un'impostazione che definisce la frequenza con cui un'attività può verificarsi prima che venga generato un avviso. In questo modo è possibile impostare un criterio per generare un avviso ogni volta che un'attività soddisfa le condizioni di criteri, quando una determinata soglia viene superata o quando l'occorrenza dell'attività che inerenti all'avviso diventa insolito dell'organizzazione. 
    
    ![Configurare come gli avvisi verranno attivati, sulla base quando si verifica l'attività, una soglia o insolito attività per l'organizzazione](media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)
  
    Se si seleziona l'impostazione in base all'attività non comune, Office 365 stabilisce un valore di base che definisce la frequenza normale per l'attività selezionata. sono necessari fino a 7 giorni per stabilire la base, durante i quali non vengono generati avvisi. Una volta stabilita la linea di base, verrà generato un avviso quando la frequenza dell'attività monitorate dal criterio avviso notevolmente supera il valore di base. Per attività di controllo relativo (ad esempio le attività di file e cartelle), è possibile stabilire una linea di base basato su un singolo utente o su tutti gli utenti nell'organizzazione. per le attività correlate a malware, è possibile stabilire una linea di base basato su una famiglia di malware singolo, un singolo destinatario o tutti i messaggi nell'organizzazione.
    
    > [!NOTE]
    > La possibilità di configurare avviso criteri basato su una soglia o in base all'attività non comune richiede una sottoscrizione E5/G5, o un G1/E1 o E3/G3 sottoscrizione a un Intelligence rischio o sottoscrizione di componente aggiuntivo conformità avanzate. Le organizzazioni con una sottoscrizione E1/G1 ed E3/G3 solo possono creare un criterio di avviso in cui è è attivato un avviso ogni volta che si verifica un'attività. 
  
- **Categoria di avvisi** - al fine di facilitare la gestione e la gestione di avvisi generati da un criterio, è possibile assegnare uno dei seguenti categorie a un criterio.
    
  - Governance dei dati
    
  - Prevenzione della perdita di dati

  - Flusso di posta
    
  - Autorizzazioni
    
  - Gestione dei rischi
    
  - Altri
    
  Quando si verifica un'attività che soddisfa le condizioni del criterio di avviso, l'avviso viene generato è contrassegnato con la categoria definita in questa impostazione. Ciò consente di tenere traccia e gestire gli avvisi che hanno la stessa categoria impostate nella pagina **visualizzare gli avvisi** di protezione & centro conformità dal momento che è possibile ordinare e avvisi filtri in base alla categoria. 
    
- **Gravità** - simile per la categoria di avviso, assegnare a un attributo del livello di gravità ( **bassa**, **Media**o **alta**) criteri di avviso. Ad esempio la categoria di avviso, quando si verifica un'attività che soddisfa le condizioni del criterio di avviso, l'avviso viene generato contrassegnato con lo stesso livello di gravità impostato per il criterio di avviso. Nuovamente, consente di tenere traccia e gestire gli avvisi che hanno la stessa impostazione di gravità nella pagina **Visualizza avvisi** . Ad esempio, è possibile filtrare l'elenco degli avvisi in modo che vengano visualizzati solo gli avvisi con livello di gravità **alta** . 
    
    > [!TIP]
    > Quando si configura un criterio di avviso, prendere in considerazione l'assegnazione di un livello di gravità superiore alle attività che possono causare tempi di conseguenze negative drasticamente, ad esempio il rilevamento di malware dopo il recapito per gli utenti, la visualizzazione dei dati sensibili o riservati, la condivisione dei dati con utenti esterni, o altre attività che possono causare tempi di rischi di protezione o perdita di dati. Ciò consente di impostare la priorità di avvisi e le azioni per analizzare e risolvere le cause sottostanti. 
  
- **Notifiche tramite posta elettronica** - è possibile impostare i criteri in modo che le notifiche di posta elettronica inviate (o non inviate) a un elenco di utenti quando viene generato un avviso. È inoltre possibile impostare un limite di notifica giornaliero in modo che quando viene raggiunto il numero massimo di notifiche non più notifiche vengono inviate per l'avviso in tale giorno. In aggiuntive per le notifiche di posta elettronica è o altri amministratori possono visualizzare avvisi generati da un criterio nella pagina **Visualizza avvisi** . È consigliabile abilitare le notifiche di posta elettronica per i criteri degli avvisi di una categoria specifica o che hanno un'impostazione di gravità superiore. 
  
## <a name="default-alert-policies"></a>Criteri di avviso predefinito

Office 365 fornisce criteri avvisi incorporati che consentono di identificare uso improprio le autorizzazioni di amministrazione di Exchange, l'attività di malware e i rischi di governance di dati. Nella pagina **criteri di avvisi** , il nome di questi criteri predefiniti sono in grassetto e il tipo di criterio viene definito come **sistema**. Questi criteri vengono attivati per impostazione predefinita. È possibile disattivare questi criteri (o viceversa nella), impostare un elenco dei destinatari a cui inviare notifiche di posta elettronica e impostare un limite di notifica giornaliero. Le altre impostazioni di questi criteri non possono essere modificate.
  
Nella tabella seguente sono elencati e vengono descritti i criteri di avviso predefiniti disponibili e indica i piani di Office 365 Enterprise e Office 365 US Government necessari per ciascuno di essi. Si noti che alcuni criteri avviso predefiniti sono disponibili se l'organizzazione ha la sottoscrizione al componente aggiuntivo appropriato oltre a una sottoscrizione G1/E1 o E3/G3. 
  
|**Criterio di avviso predefinito**|**Descrizione**|**Sottoscrizione a Office 365 Enterprise**|
|:-----|:-----|:-----|
|**Creazione di regole di inoltro/reindirizza** <br/> |Genera un avviso quando un utente all'interno dell'organizzazione consente di creare una regola di posta in arrivo per la cassetta postale che inoltra o reindirizza i messaggi a un altro account di posta elettronica. Questo criterio tiene traccia solo le regole posta in arrivo che vengono create utilizzando Outlook Web App o Exchange Online PowerShell. Questo criterio è un'impostazione di gravità **bassa** . Per ulteriori informazioni sull'utilizzo di regole posta in arrivo per l'inoltro e il reindirizzamento di posta elettronica in Outlook Web App, vedere [utilizzare le regole in Outlook Web App per inoltrare automaticamente messaggi a un altro account](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed).<br/> |G1/E1, E3/G3 o E5/G5  <br/> |
|**ricerca di eDiscovery avviato o esportati** <br/> |Genera un avviso quando si utilizza lo strumento di ricerca del contenuto in & la sicurezza centro conformità. Viene generato un avviso quando vengono eseguite le attività di ricerca di contenuto seguenti:<br/><br/>• Una ricerca di contenuto sia stato avviato<br/>• Vengono esportati i risultati di ricerca di contenuto<br/>• Esportazione di un report di ricerca del contenuto<br/><br/>Gli avvisi sono inoltre trigged quando vengono eseguite le attività di ricerca del contenuto precedente associata a un caso eDiscovery. Questo criterio è un'impostazione di gravità **Media** . Per ulteriori informazioni sulle attività di ricerca del contenuto, vedere la sezione [ricerca per le attività di eDiscovery in Office 365 Registro di controllo](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities).<br/> |G1/E1, E3/G3 o E5/G5  <br/> |
|**Elevazione dei privilegi di amministrazione di Exchange** <br/> |Genera un avviso quando un utente verrà assegnato autorizzazioni amministrative nell'organizzazione Exchange Online. ad esempio, se un utente viene aggiunto al ruolo Gestione organizzazione gruppo in Exchange Online. Questo criterio è un'impostazione di gravità **bassa** .<br/> |G1/E1, E3/G3 o E5/G5  <br/> |
|**I messaggi sono in ritardo** <br/> |Genera un avviso quando Office 365 non possono offrire messaggi di posta elettronica all'organizzazione locale o un partner di server utilizzando un connettore. Quando ciò verifica, il messaggio viene accodato in Office 365. Questo avviso viene generato quando sono presenti messaggi di 2.000 o più che sono stati accodati per più di un'ora. Questo criterio è impostato gravità **alta** .<br/> |G1/E1, E3/G3 o E5/G5  <br/> |
|**Campagne di malware rilevata dopo il recapito** <br/> |Genera un avviso quando un numero insolitamente elevato di messaggi contenenti malware viene recapitato alle cassette postali nell'organizzazione. Se si verifica questo evento, Office 365 consente di rimuovere i messaggi che contengono un virus dalle cassette postali di Exchange Online. Questo criterio è impostato gravità **alta** .<br/> |Sottoscrizione di componente aggiuntivo E5/G5 o Business Intelligence di rischio di Office 365  <br/> |
|**Campagne di malware rilevato e bloccato** <br/> |Genera un avviso quando un utente ha tentato di inviare un numero insolitamente elevato di messaggi di posta elettronica contenente un determinato tipo di malware per gli utenti dell'organizzazione. Se si verifica questo evento, i messaggi che contengono un virus vengono bloccati da Office 365 e non recapitati alle cassette postali. Questo criterio è un'impostazione di gravità **bassa** .<br/> |Sottoscrizione di componente aggiuntivo E5/G5 o Business Intelligence di rischio di Office 365  <br/> |
|**Campagne di malware rilevata in SharePoint e OneDrive** <br/> |Genera un avviso quando un volume insolitamente elevato di malware o virus vengono rilevati nei file che si trovano in siti di SharePoint o account OneDrive nell'organizzazione. Questo criterio è impostato gravità **alta** .<br/> |Sottoscrizione di componente aggiuntivo E5/G5 o Business Intelligence di rischio di Office 365  <br/> |
|**Attività del file degli utenti esterni non comune** <br/> |Genera un avviso quando un numero elevato in genere di attività viene eseguito nei file di SharePoint o OneDrive dagli utenti esterni all'organizzazione. Sono incluse le attività quali l'accesso ai file, il download dei file e l'eliminazione di file. Questo criterio è impostato gravità **alta** .<br/> |E5/G5 o sottoscrizione di componente aggiuntivo di Business Intelligence di Office 365 rischio o conformità avanzate  <br/> |
|**Volume non comune di condivisione di file esterno** <br/> |Genera un avviso quando un numero elevato in genere di file in SharePoint o OneDrive viene condivise con utenti esterni all'organizzazione. Questo criterio è un'impostazione di gravità **Media** .<br/> |E5/G5 o sottoscrizione di componente aggiuntivo di Business Intelligence di Office 365 rischio o conformità avanzate  <br/> |
|**Volume non comune di eliminazione dei file** <br/> |Genera un avviso quando un numero insolitamente elevato dei file viene eliminato in SharePoint o OneDrive cornice un breve periodo di tempo. Questo criterio è un'impostazione di gravità **Media** .<br/> |E5/G5 o sottoscrizione di componente aggiuntivo di Business Intelligence di Office 365 rischio o conformità avanzate  <br/> |
|**Aumento insolito nel messaggio di posta elettronica riportato come per attività di phishing** <br/> |Genera un avviso quando si verifica un aumento significativo nel numero di utenti nell'organizzazione utilizzando il componente aggiuntivo di report in Outlook per i messaggi di report tramite posta elettronica phishing in. Questo criterio è impostato gravità **alta** . Per ulteriori informazioni su questo componente aggiuntivo, vedere [utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).<br/> |Sottoscrizione di componente aggiuntivo E5/G5 o Business Intelligence di rischio di Office 365  <br/> |
   
Si noti che l'attività anomala monitorato da alcuni dei criteri predefiniti si basa sullo stesso processo come descritto in precedenza la soglia di avviso che l'impostazione. Office 365 stabilisce un valore di base che definisce la frequenza normale per l'attività "normale". Gli avvisi vengono quindi attivati quando la frequenza delle attività monitorate dal criterio avviso incorporato notevolmente supera il valore di base.
 
## <a name="viewing-alerts"></a>Visualizzazione degli avvisi

Se un'attività eseguita dagli utenti nell'organizzazione corrispondono alle impostazioni di criteri di avviso, un avviso viene generato e visualizzato nella pagina **Visualizza avvisi** di protezione &amp; centro conformità. A seconda delle impostazioni di criteri di avviso, posta elettronica viene inviata una notifica anche a un elenco di utenti specificati quando viene generato un avviso. Per ciascun avviso, il dashboard nella pagina **Visualizza avvisi** vengono visualizzati il nome del criterio di avviso corrispondente, il livello di gravità e categorie per avviso (definito nei criteri di avviso) e il numero di volte in cui si è verificata un'attività che ha comportato l'avviso viene generare, Questo valore si basa sull'impostazione della soglia del criterio di avviso. Il dashboard è indicato lo stato di ogni avviso. Per ulteriori informazioni sull'utilizzo di proprietà status per gestire gli avvisi, vedere [Managing avvisi](#managing-alerts) . 
  
Per visualizzare gli avvisi, passare a **avvisi** \> **Visualizza avvisi** di sicurezza &amp; centro conformità. 
  
![In sicurezza &amp; Complinace interfaccia, fare clic su avvisi, quindi fare clic su Visualizza avvisi per visualizzare gli avvisi](media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)
  
È possibile utilizzare i filtri seguenti per visualizzare un sottoinsieme di tutti gli avvisi nella pagina **Visualizza avvisi** . 
  
- **Stato** - utilizzare questo filtro per visualizzare gli avvisi che sono assegnati a un determinato stato; il valore predefinito è **attivo**. L'utente o gli altri amministratori possono modificare il valore di stato.
    
- **Criteri** - utilizzare questo filtro per visualizzare gli avvisi che corrispondano all'impostazione di uno o più criteri di avviso. In alternativa, è possibile visualizzare solo tutti gli avvisi per tutti i criteri di avviso.
    
- **Intervallo di tempo** - utilizzare questo filtro per visualizzare gli avvisi generati all'interno di una data e l'intervallo di tempo.
    
- **Gravità** - utilizzare questo filtro per visualizzare gli avvisi che vengono assegnati un livello di gravità specifico.
    
- **Categoria** - utilizzare questo filtro per visualizzare gli avvisi da una o più categorie di avviso.

- **Origine** - utilizzare questo filtro per visualizzare gli avvisi generati dall'avvisi criteri in & la sicurezza centro conformità o gli avvisi generati dal criteri di protezione di Office 365 Cloud App o entrambi. Per ulteriori informazioni sugli avvisi di protezione di applicazioni di Office 365 Cloud, vedere la sezione [avviso di sicurezza di applicazione Cloud visualizzazione](#viewing-cloud-app-security-alerts) .

### <a name="rbac-permissions-required-to-view-alerts"></a>Autorizzazioni RBAC necessarie per visualizzare gli avvisi

> [!NOTE]
> Le funzionalità descritte in questa sezione verranno applicati a partire dal 20 febbraio 2019, le organizzazioni e verranno eseguite in tutto il mondo al termine della 2019 marzo.

Le autorizzazioni di controllo di accesso basi ruoli (RBAC) assegnate agli utenti dell'organizzazione determina quali avvisi gli utenti possono visualizzare la pagina di **visualizzare gli avvisi** . Come eseguire questa operazione? I ruoli di gestione assegnati agli utenti (in base all'appartenenza a gruppi di ruoli in & la sicurezza centro conformità) determinano quali categorie di avvisi possono essere visualizzate nella pagina di **visualizzare gli avvisi** . Di seguito sono riportati alcuni esempi:

- I membri del gruppo di ruoli di gestione dei record possono visualizzare solo gli avvisi generati dall'avvisi criteri che sono assegnati la categoria di **governance di dati** .
- Membri del gruppo di ruoli amministratore conformità non possono visualizzare gli avvisi generati dall'avvisi criteri che sono assegnati la categoria di **gestione delle minacce** . 
- Membri del gruppo di ruoli gestione eDiscovery non possono visualizzare avvisi dal momento che nessuno dei ruoli assegnati forniscono l'autorizzazione per visualizzare gli avvisi provenienti da qualsiasi categoria di avviso.

Questa struttura (in base alle autorizzazioni RBAC) consente di determinare quali gli avvisi possono essere visualizzati (e gestiti) dagli utenti in ruoli specifici dell'organizzazione. 

Nella tabella seguente sono elencati i ruoli necessari per visualizzare gli avvisi di 6 diverse categorie di avviso. La prima colonna nelle tabelle sono elencati tutti i ruoli di protezione & centro conformità.  Un segno di spunta indica che un utente cui è stato assegnato il ruolo può visualizzare avvisi dalla categoria avviso corrispondente elencato nella riga superiore.

|<br/>|Governance dei dati|Prevenzione della perdita di dati|Flusso di posta|Autorizzazioni|Gestione dei rischi|Altri | 
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Registri di controllo <br/> |         ||         |         |         |         |
|Gestione dei casi <br/>|         |         |         |         |         |         |
|Amministratore di conformità<br/>|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Ricerca di conformità<br/>|         |         |         |         |         |         |
|Gestione dei dispositivi<br/>|         |         |         |         |         |         |
|Gestione di eliminazione<br/>|         |         |         |         |         |         |
|Gestione della conformità DLP<br/>|         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |
|Esportazione<br/>|         |         |         |         |         |         |
|Archiviazione<br/>|         |         |         |         |         |         |
|Gestione avvisi<br/>|         |         |         |         |         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configurazione dell'organizzazione|         |         |         |         |         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Anteprima <br/>|         |         |         |         |         |         |
|Gestione dei record <br/>|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|Gestione di conservazione <br/>| ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|Revisione  <br/>|         |         |         |         |         |         |
|Decrittografia RMS<br/>|         |         |         |         |         |         |
|Gestione dei ruoli<br/>|         |         |         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |
|Ricerca ed eliminazione<br/>|         |         |         |         |         |         |
|Amministratore della sicurezza<br/>||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| | ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Lettore di sicurezza<br/>|         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| | ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)
|Servizio controllo visualizzazione<br/>|         |         |         |         |         |         |
|Amministratore di revisione supervisione<br/>|         |         |         |         |         |         |
|Registri di controllo sola visualizzazione<br/>|         |         |         |         |         |         |
|Gestione dei dispositivi di sola visualizzazione<br/>|         |         |         |         |         |         |
|Gestione della conformità DLP sola visualizzazione<br/>|         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |
|Sola visualizzazione Gestione avvisi<br/>|         |         |         |         |         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Destinatari solo visualizzazione<br/>|         |         |  ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       |         ||         |
|Gestione Record di sola visualizzazione<br/>|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|Gestione conservazione sola visualizzazione<br/>|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|         |         |         |         |         |         |

**Suggerimento:** Per visualizzare i ruoli assegnati a ognuno dei gruppi di ruoli predefinito, eseguire i seguenti comandi in sicurezza & PowerShell centro conformità: 

```
$RoleGroups = Get-RoleGroup

$RoleGroups | foreach {Write-Output -InputObject `r`n,$_.Name,"-----------------------"; Get-RoleGroup $_.Identity | Select-Object -ExpandProperty Roles}
```
È inoltre possibile visualizzare i ruoli assegnati a un gruppo di ruoli di protezione & centro conformità. Passare alla pagina **autorizzazioni** e fare clic su un gruppo di ruoli. Nella pagina comparsa sono elencati i ruoli.


## <a name="managing-alerts"></a>Gestione degli avvisi

Dopo che gli avvisi sono stati generati e visualizzati nella pagina **Visualizza avvisi** di protezione &amp; centro conformità, è possibile esaminare, analizzare e risolverli. Ecco alcune attività eseguibili per gestire gli avvisi. 
  
- **Assegnare uno stato per gli avvisi** - è possibile assegnare uno dei seguenti stati avvisi: **attivo** (valore predefinito), **Investigating**, **risolto**o **Dismissed**. Quindi, è possibile filtrare questa impostazione per visualizzare gli avvisi con la stessa impostazione dello stato. Questa impostazione dello stato consente di tenere traccia del processo di gestione degli avvisi.
    
- **Visualizzare i dettagli degli avvisi** - è possibile fare clic su un avviso per visualizzare una pagina di comparsa con informazioni dettagliate sull'avviso. Informazioni dettagliate dipendono il criterio di avviso corrispondente, ma in genere include le operazioni seguenti: nome dell'operazione effettivo che ha attivato l'avviso (ad esempio un cmdlet), la descrizione dell'attività che ha generato l'avviso, l'utente (o elenco di utenti) che ha attivato l'avviso e il nome e collegamenti dei corrispondente criterio di avviso.
    
  - Nome dell'operazione effettivo che ha attivato l'avviso, ad esempio un cmdlet o un'operazione di registro di controllo.
    
  - Descrizione dell'attività che ha attivato l'avviso.
    
  - L'utente che ha attivato l'avviso; viene incluso solo per i criteri di avviso che sono stati impostati per tenere traccia di un singolo utente o una singola attività.
    
  - Il numero di ripetizioni dell'attività monitorata dall'avviso è stato eseguito. Si noti che questo numero non potrebbe rispondere a tale numero effettivo di avvisi correlati elencata nella pagina Visualizza avvisi perché ulteriori avvisi potrebbe essere attivati.
    
  - Collegamento a un elenco di attività che includa un elemento per ogni attività è stata eseguita che ha attivato l'avviso. Ogni voce nell'elenco di identificare quando si è verificato l'attività, il nome dell'operazione effettivo, (ad esempio "FileDeleted") e l'utente che ha eseguito l'attività, l'oggetto (ad esempio un file, un caso eDiscovery o una cassetta postale) che l'attività è stata eseguita su e l'indirizzo IP indirizzo del computer dell'utente. Per malware correlati avvisi, questo collegamenti a un elenco dei messaggi.
    
  - Nome (e collegamenti a) del criterio di avviso corrispondente.
    
- **Non visualizzare notifiche del messaggio di posta elettronica** - è possibile disattivare (o eliminare) le notifiche di posta elettronica dalla pagina comparsa di un avviso. Quando si elimina notifiche tramite posta elettronica, Office 365 non inviare notifiche quando le attività o gli eventi che soddisfano le condizioni del criterio degli avvisi. Tuttavia, gli avvisi continuerà a essere trigger quando le attività eseguite dagli utenti corrispondono alle condizioni del criterio di avviso. È inoltre possibile disattivare le notifiche di posta elettronica modificando il criterio di avviso.
    
- **Risolvere gli avvisi** - è possibile contrassegnare un avviso come risolto nella pagina comparsa per un avviso (che imposta lo stato dell'avviso su **risolto**). Se non si modifica il filtro, risolvere gli avvisi non vengono visualizzati nella pagina **Visualizza avvisi** . 
    
## <a name="viewing-cloud-app-security-alerts"></a>Visualizzazione degli avvisi di protezione di applicazione Cloud
  
Avvisi che vengono attivati i criteri di sicurezza di Office 365 Cloud App vengono ora visualizzati nella pagina **Visualizza avvisi** di protezione & centro conformità. Include gli avvisi che vengono attivati i criteri di attività e gli avvisi che vengono attivati i criteri di rilevamento anomalia nella sicurezza App Cloud di Office 365. Ciò significa che è possibile visualizzare tutti gli avvisi in & la sicurezza centro conformità. Si noti che Office 365 Cloud App protezione è disponibile solo per le organizzazioni con una sottoscrizione a Office 365 Enterprise E5 o Office 365 US Government G5. Per ulteriori informazioni, vedere [Overview of Office 365 Cloud App Security](office-365-cas-overview.md).

Inoltre, le organizzazioni con Microsoft Cloud App Security come parte di un mobilità aziendale + sicurezza E5 sottoscrizione o come servizio autonomo inoltre possono visualizzare gli avvisi di protezione di applicazione Cloud correlati alle applicazioni di Office 365 e servizi in & protezione Centro conformità.

Per visualizzare solo gli avvisi di protezione di applicazione Cloud & la sicurezza centro conformità, utilizzare il filtro di **origine** e selezionare **Sicurezza App Cloud**.

![Utilizzare il filtro di origine per visualizzare solo gli avvisi di protezione di applicazione Cloud](media/FilterCASAlerts.png)

Analogamente a un avviso generato da una protezione & criteri avviso centro conformità, è possibile fare clic su un avviso di protezione di applicazione Cloud per visualizzare una pagina di comparsa con informazioni dettagliate sull'avviso. L'avviso è incluso un collegamento per visualizzare i dettagli e gestire l'avviso nel portale di protezione di applicazione Cloud e un collegamento al criterio di protezione di applicazione Cloud corrispondente che ha attivato l'avviso. Vedere [revisione ed esegue azioni avvisi di protezione di Office 365 Cloud App](review-office-365-cas-alerts.md).

![Dettagli dell'avviso contengono collegamenti al portale di protezione di applicazione Cloud](media/CASAlertDetail.png)

> [!IMPORTANT]
> Modifica dello stato di un avviso di protezione di applicazione Cloud in & la sicurezza centro conformità non aggiorna lo stato di risoluzione per l'avviso stesso nel portale di protezione di applicazione Cloud. Ad esempio, se lo stato dell'avviso si contrassegna come **risolto** in & la sicurezza centro conformità, lo stato dell'avviso nel portale di protezione di applicazione Cloud viene modificato. Per risolvere o eliminare un avviso di protezione di applicazione Cloud, gestire l'avviso nel portale di protezione di applicazione Cloud.