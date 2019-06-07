---
title: Criteri di avviso nel centro sicurezza e conformità
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: 8927b8b9-c5bc-45a8-a9f9-96c732e58264
description: Creare criteri di avviso nel centro sicurezza e conformità di Office 365 e Microsoft 365 per monitorare le potenziali minacce, la perdita di dati e il problema delle autorizzazioni. È quindi possibile visualizzare e gestire gli avvisi generati quando gli utenti eseguono attività che soddisfano le condizioni di un criterio di avviso.
ms.openlocfilehash: 3d1859c22f5a371a542251c0f64d8d429352a744
ms.sourcegitcommit: ff1d18aaddde2048f1cf88338c916295cf8c354e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2019
ms.locfileid: "34748589"
---
# <a name="alert-policies-in-the-security-and-compliance-center"></a>Criteri di avviso nel centro sicurezza e conformità

È possibile utilizzare il nuovo criterio di avviso e gli strumenti del dashboard di avviso nei centri di sicurezza e conformità di Office 365 e Microsoft 365 per creare criteri di avviso e quindi visualizzare gli avvisi generati quando gli utenti eseguono attività che soddisfano le condizioni di un criterio di avviso. . I criteri di avviso consentono di creare ed espandere la funzionalità degli avvisi di attività consentendo di categorizzare i criteri di avviso, applicare il criterio a tutti gli utenti dell'organizzazione, impostare un livello di soglia per il momento in cui viene attivato un avviso e decidere se ricevere la posta elettronica notifiche. È inoltre disponibile una pagina **Visualizza avvisi** nel centro sicurezza e conformità in cui è possibile visualizzare e filtrare gli avvisi, impostare lo stato di avviso per la gestione degli avvisi e quindi ignorare gli avvisi dopo aver affrontato o risolto l'evento sottostante. È stato inoltre esteso il tipo di eventi per cui è possibile creare avvisi. Ad esempio, è possibile creare criteri di avviso per monitorare l'attività di malware e gli incidenti di perdita di dati. Infine, sono stati inclusi anche alcuni criteri di avviso predefiniti che consentono di monitorare l'assegnazione dei privilegi di amministratore in Exchange Online, attacchi di malware e livelli inusuali di eliminazione di file e condivisione esterna. 
  
> [!NOTE]
> I criteri di avviso sono disponibili per le organizzazioni che dispongono di un abbonamento a Office 365 Enterprise o Office 365 US Government E1/G1, E3/G3 o E5/G5. Tuttavia, alcune funzionalità avanzate sono disponibili solo per le organizzazioni con un abbonamento E5/G5 o per organizzazioni che dispongono di un abbonamento E1/G1 o E3/G3 e di un componente aggiuntivo di Office 365 Advanced Threat Protection (ATP) P2 o Office 365 Advanced Compliance. abbonamento. In questo argomento è evidenziata la funzionalità che richiede un abbonamento E5/G5 o un componente aggiuntivo. Si noti inoltre che i criteri di avviso sono disponibili in Office 365 GCC, GCC High e DoD US Government environments.
  
## <a name="how-alert-policies-work"></a>Funzionamento di criteri di avviso

Di seguito viene illustrata una breve panoramica del funzionamento dei criteri di avviso e degli avvisi attivati quando l'attività dell'utente o dell'amministratore corrisponde alle condizioni di un criterio di avviso.
  
![Panoramica della modalità di funzionamento dei criteri di avviso](media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)
  
1. Un amministratore dell'organizzazione crea, configura e attiva un criterio di avviso utilizzando la pagina **criteri di avviso** nel centro sicurezza e conformità. È inoltre possibile creare criteri di avviso utilizzando il cmdlet **New-ProtectionAlert** in PowerShell per il centro sicurezza & Compliance. Per creare criteri di avviso, è necessario assegnare il ruolo Gestisci avvisi o il ruolo Configurazione organizzazione nel centro sicurezza e conformità.  
    
2. Un utente esegue un'attività che soddisfa le condizioni di un criterio di avviso. In caso di attacchi di malware, i messaggi di posta elettronica infetti inviati agli utenti nell'organizzazione attivano un avviso.
    
3. Office 365 genera un avviso visualizzato nella pagina **Visualizza avvisi** nel centro sicurezza e conformità. Inoltre, se le notifiche di posta elettronica sono abilitate per il criterio di avviso, Office 365 invia una notifica a un elenco di destinatari. Gli avvisi che un amministratore o altri utenti possono vedere che nella pagina Visualizza avvisi è determinato dai ruoli assegnati all'utente. Per ulteriori informazioni, vedere la sezione [autorizzazioni RBAC necessarie per visualizzare gli avvisi](#rbac-permissions-required-to-view-alerts) .
    
4. Un amministratore gestisce gli avvisi nel centro sicurezza e conformità. La gestione degli avvisi consiste nell'assegnare uno stato di avviso che consenta di monitorare e gestire qualsiasi indagine.
    
## <a name="alert-policy-settings"></a>Impostazioni di criteri di avviso

Un criterio di avviso è costituito da un insieme di regole e condizioni che definiscono l'attività dell'utente o dell'amministratore che genererà un avviso, un elenco di utenti che attiveranno l'avviso se eseguono l'attività e la soglia che definisce il numero di volte in cui l'attività deve essere eseguita prima di un n avviso attivato. È inoltre possibile suddividere in categorie il criterio e assegnargli un livello di gravità. Queste due impostazioni consentono di gestire i criteri di avviso (e gli avvisi attivati quando vengono soddisfatte le condizioni dei criteri) perché è possibile filtrare queste impostazioni quando si gestiscono i criteri e si visualizzano gli avvisi nel centro sicurezza e conformità. Ad esempio, è possibile visualizzare gli avvisi che soddisfano le condizioni della stessa categoria o visualizzare gli avvisi con lo stesso livello di gravità.
  
Per visualizzare e creare criteri di avviso, passare [https://protection.office.com](https://protection.office.com) a e quindi fare clic su **avvisi** \> per i **criteri di avviso**. 
  
![Nel centro sicurezza e conformità fare clic su avvisi, quindi fare clic su criteri avvisi per visualizzare e creare criteri di avviso.](media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)
  
Un criterio di avviso è costituito dalle impostazioni e dalle condizioni seguenti.
  
- **Attività l'avviso è la verifica** – è possibile creare un criterio per tenere traccia di un'attività o in alcuni casi alcune attività correlate, ad esempio la condivisione di un file con un utente esterno, la condivisione, l'assegnazione di autorizzazioni di accesso o la creazione di un collegamento anonimo. Quando un utente esegue l'attività definita dal criterio, viene attivato un avviso in base alle impostazioni della soglia di avviso.
    
    > [!NOTE]
    > Le attività che è possibile monitorare dipendono dal piano di amministrazione dell'organizzazione Office 365 Enterprise o Office 365 US. In generale, le attività relative alle campagne antimalware e agli attacchi di phishing richiedono un abbonamento E5/G5 o un abbonamento E1/G1 o E3/G3 con un abbonamento al componente aggiuntivo di Threat Intelligence. 
  
- **Condizioni di attività** – per la maggior parte delle attività, è possibile definire condizioni aggiuntive che devono essere soddisfatte affinché venga attivato un avviso. Le condizioni comuni includono gli indirizzi IP, in modo che venga attivato un avviso quando l'utente esegue l'attività su un computer con un indirizzo IP specifico o all'interno di un intervallo di indirizzi IP, se un avviso viene attivato se uno specifico utente o utenti eseguono tale attività e se l'attività viene eseguita su un nome di file o un URL specifico. È inoltre possibile configurare una condizione che attiva un avviso quando l'attività viene eseguita da qualsiasi utente dell'organizzazione. Si noti che le condizioni disponibili dipendono dall'attività selezionata.
    
- **Quando si attiva l'avviso** , è possibile configurare un'impostazione che definisce la frequenza con cui è possibile eseguire un'attività prima che venga attivato un avviso. In questo modo è possibile impostare un criterio per generare un avviso ogni volta che un'attività corrisponde alle condizioni dei criteri, quando si supera una determinata soglia o quando si verifica l'insorgenza dell'attività in cui l'avviso è inusuale per la nostra organizzazione. 
    
    ![Configurare la modalità di attivazione degli avvisi, in base al momento in cui si verifica l'attività, a una soglia o a un'attività inusuale per l'organizzazione](media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)
  
    Se si seleziona l'impostazione in base alle attività inusuali, Office 365 stabilisce un valore di base che definisce la frequenza normale per l'attività selezionata. sono necessari fino a 7 giorni per stabilire questa linea di base, durante la quale gli avvisi non verranno generati. Dopo che la linea di base è stata stabilita, viene attivato un avviso quando la frequenza dell'attività registrata dal criterio di avviso è notevolmente superiore al valore di base. Per le attività relative al controllo, ad esempio attività per file e cartelle, è possibile stabilire una linea di base basata su un singolo utente o su tutti gli utenti dell'organizzazione. per le attività correlate al malware, è possibile stabilire una linea di base basata su una singola famiglia di malware, un singolo destinatario o tutti i messaggi nell'organizzazione.
    
    > [!NOTE]
    > La possibilità di configurare i criteri di avviso basati su una soglia o in base a attività insolite richiede un abbonamento E5/G5 o un abbonamento E1/G1 o E3/G3 con un abbonamento a Office 365 ATP P2 o Advanced Compliance Add-on. Le organizzazioni con una sottoscrizione E1/G1 e E3/G3 possono creare solo un criterio di avviso in cui viene attivato un avviso ogni volta che si verifica un'attività. 
  
- **Categoria avviso** – per facilitare la verifica e la gestione degli avvisi generati da un criterio, è possibile assegnare una delle categorie seguenti a un criterio.
    
  - Governance dei dati
    
  - Prevenzione della perdita di dati

  - Flusso di posta
    
  - Autorizzazioni
    
  - Gestione dei rischi
    
  - Altri
    
  Quando si verifica un'attività che corrisponde alle condizioni dei criteri di avviso, l'avviso generato viene contrassegnato con la categoria definita in questa impostazione. In questo modo è possibile monitorare e gestire gli avvisi con la stessa impostazione di categoria nella pagina **Visualizza avvisi** nel centro sicurezza e conformità, in quanto consente di ordinare e filtrare gli avvisi in base alla categoria. 
    
- **Gravità degli avvisi** – analoga alla categoria di avviso, è possibile assegnare un attributo Severity (**basso**, **medio**, **alto**o informativo) ai criteri di avviso. **** Analogamente alla categoria avviso, quando si verifica un'attività che corrisponde alle condizioni del criterio di avviso, l'avviso generato viene contrassegnato con lo stesso livello di gravità impostato per il criterio di avviso. Di nuovo, in questo modo è possibile monitorare e gestire gli avvisi che hanno la stessa impostazione di gravità nella pagina **Visualizza avvisi** . Ad esempio, è possibile filtrare l'elenco di avvisi in modo che vengano visualizzati solo gli avvisi con un livello di gravità **elevato** . 
    
    > [!TIP]
    > Quando si configura un criterio di avviso, è consigliabile assegnare un livello di gravità maggiore alle attività che possono comportare conseguenze gravemente negative, ad esempio il rilevamento di malware dopo il recapito agli utenti, la visualizzazione di dati sensibili o classificati, la condivisione di dati con utenti esterni, o altre attività che possono causare perdite di dati o minacce alla sicurezza. In questo modo è possibile definire la priorità per gli avvisi e le azioni da intraprendere per analizzare e risolvere le cause sottostanti. 
  
- **Notifiche tramite posta elettronica** : è possibile configurare i criteri in modo che le notifiche di posta elettronica vengano inviate (o non inviate) a un elenco di utenti quando si attiva un avviso. È inoltre possibile impostare un limite di notifica giornaliero in modo che, dopo aver raggiunto il numero massimo di notifiche, non vengano inviate altre notifiche per l'avviso durante quel giorno. In aggiunta alle notifiche tramite posta elettronica, l'utente o altri amministratori possono visualizzare gli avvisi attivati da un criterio nella pagina **Visualizza avvisi** . È consigliabile abilitare le notifiche di posta elettronica per i criteri di avviso di una categoria specifica o che dispongono di un'impostazione di gravità maggiore. 
  
## <a name="default-alert-policies"></a>Criteri di avviso predefiniti

Office 365 fornisce criteri di avviso incorporati che consentono di identificare l'abuso delle autorizzazioni di amministratore di Exchange, l'attività antimalware e i rischi di governance dei dati. Nella pagina **criteri di avviso** i nomi di questi criteri incorporati sono in grassetto e il tipo di criterio è definito come **System**. Questi criteri sono attivati per impostazione predefinita. È possibile disattivare questi criteri (o viceversa), configurare un elenco di destinatari a cui inviare notifiche tramite posta elettronica e impostare un limite di notifica giornaliero. Le altre impostazioni per questi criteri non possono essere modificate.
  
Nella tabella seguente sono elencati e descritti i criteri di avviso predefiniti disponibili e la categoria a cui sono assegnati i criteri. Si noti che la categoria viene utilizzata per determinare gli avvisi che un utente può visualizzare nella pagina Visualizza avvisi. Per ulteriori informazioni, vedere la sezione [autorizzazioni RBAC necessarie per visualizzare gli avvisi](#rbac-permissions-required-to-view-alerts) .  

La tabella indica anche il piano Office 365 Enterprise and Office 365 US Government obbligatorio per ognuno di essi. Alcuni criteri di avviso predefiniti sono disponibili se l'organizzazione ha la sottoscrizione del componente aggiuntivo appropriata oltre a una sottoscrizione E1/G1 o E3/G3. 
  
|**Criterio di avviso predefinito**|**Descrizione**|**Categoria**|**Abbonamento a Office 365 Enterprise**|
|:-----|:-----|:-----|:-----|
|**È stato rilevato un clic URL potenzialmente dannoso** <br/> |Genera un avviso quando un utente protetto da [collegamenti sicuri ATP di Office 365](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) nell'organizzazione fa clic su un collegamento dannoso. Questo evento viene attivato quando le modifiche al verdetto degli URL sono identificate da Office 365 ATP o quando gli utenti eseguono l'override delle pagine dei collegamenti sicuri ATP di Office 365 (in base ai criteri dei collegamenti sicuri ATP di Office 365 dell'organizzazione). Questo criterio di avviso ha un'impostazione di gravità **elevata** . Per i clienti di Office 365 ATP P2, E5 e G5, questo avviso attiva automaticamente l' [analisi e la risposta automatizzata di office 365](https://go.microsoft.com/fwlink/?linkid=2084737).  Per ulteriori informazioni sugli eventi che attivano questo avviso, vedere [set up Office 365 ATP Safe Links Policies](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies).  <br/> |Gestione dei rischi <br/> |Sottoscrizione di un componente aggiuntivo per i componenti aggiuntivi di E5/G5 o Office 365 ATP P2  <br/> |
|**Creazione di una regola di inoltro/Reindirizzamento** <br/> |Genera un avviso quando un utente dell'organizzazione crea una regola di posta in arrivo per la propria cassetta postale che inoltra o reindirizza i messaggi a un altro account di posta elettronica. Questo criterio tiene traccia solo le regole della posta in arrivo create utilizzando Outlook sul Web (in precedenza noto come Outlook Web App) o Exchange Online PowerShell. Questo criterio ha un'impostazione di gravità **bassa** . Per ulteriori informazioni sull'utilizzo delle regole di posta in arrivo per inoltrare e reindirizzare la posta elettronica in Outlook sul Web, vedere [use rules in Outlook sul Web per inoltrare automaticamente i messaggi a un altro account](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed).  <br/> |Gestione dei rischi <br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**ricerca eDiscovery avviata o esportata** <br/> |Genera un avviso quando qualcuno utilizza lo strumento di ricerca contenuto nel centro sicurezza e conformità. Viene attivato un avviso quando vengono eseguite le attività di ricerca del contenuto seguenti: <br/><br/>• Viene avviata una ricerca di contenuto<br/>• Vengono esportati i risultati di una ricerca di contenuto<br/>• Viene esportato un report di ricerca contenuto<br/><br/>Gli avvisi vengono attivati anche quando le attività di ricerca di contenuto precedenti vengono eseguite in associazione a un caso di eDiscovery. Questo criterio ha un'impostazione di gravità **media** . Per ulteriori informazioni sulle attività di ricerca del contenuto, vedere [Search for eDiscovery Activities in the Office 365 audit log](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities). <br/> |Gestione dei rischi<br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**Privilegi di amministratore di Exchange per l'elevazione** <br/> |Genera un avviso quando a un utente sono assegnate autorizzazioni amministrative nell'organizzazione di Exchange Online. Ad esempio, quando un utente viene aggiunto al gruppo di ruoli Gestione organizzazione in Exchange Online. Questo criterio ha un'impostazione di gravità **bassa** .  <br/> |Autorizzazioni <br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**Messaggi di posta elettronica contenenti malware rimossi dopo il recapito** <br/> |Genera un avviso quando tutti i messaggi contenenti malware vengono recapitati alle cassette postali dell'organizzazione. Se si verifica questo evento, Office 365 rimuove i messaggi infetti dalle cassette postali di Exchange Online con l' [eliminazione automatica di zero-hour](https://docs.microsoft.com/en-us/office365/securitycompliance/zero-hour-auto-purge). Questo criterio ha un' **** impostazione di severità informativa e attiva automaticamente l' [analisi e la risposta automatizzata di Office 365](https://go.microsoft.com/fwlink/?linkid=2084737).<br/> |Gestione dei rischi <br/> |Sottoscrizione di un componente aggiuntivo per i componenti aggiuntivi di E5/G5 o Office 365 ATP P2  <br/> |
|**Messaggi di posta elettronica contenenti gli URL di phishing rimossi dopo il recapito** <br/> |Genera un avviso quando tutti i messaggi contenenti phishing vengono recapitati alle cassette postali dell'organizzazione. Se si verifica questo evento, Office 365 rimuove i messaggi infetti dalle cassette postali di Exchange Online con l' [eliminazione automatica di zero-hour](https://docs.microsoft.com/en-us/office365/securitycompliance/zero-hour-auto-purge). Questo criterio ha un' **** impostazione di severità informativa e attiva automaticamente l' [analisi e la risposta automatizzata di Office 365](https://go.microsoft.com/fwlink/?linkid=2084737).<br/> |Gestione dei rischi <br/> |Sottoscrizione di un componente aggiuntivo per i componenti aggiuntivi di E5/G5 o Office 365 ATP P2  <br/> |
|**Messaggi di posta elettronica segnalati dall'utente come malware o phishing** <br/> |Genera un avviso quando gli utenti dell'organizzazione segnalano i messaggi come messaggio di posta elettronica di phishing tramite il componente aggiuntivo per i messaggi di report. Questo criterio ha un **** livello di gravità informativo. Per ulteriori informazioni su questo componente aggiuntivo, vedere [use the report Message Add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Per i clienti di Office 365 ATP P2, E5 e G5, questo avviso attiva automaticamente l' [analisi e la risposta automatizzata di office 365](https://go.microsoft.com/fwlink/?linkid=2084737).  <br/> |Gestione dei rischi <br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**I messaggi sono stati ritardati** <br/> |Genera un avviso quando Office 365 non è in grado di recapitare messaggi di posta elettronica all'organizzazione locale o a un server partner utilizzando un connettore. In questo caso, il messaggio viene accodato in Office 365. Questo avviso viene attivato quando sono presenti 2.000 messaggi o più che sono stati accodati per più di un'ora. Questo criterio è impostato **su un livello** di gravità elevato.  <br/> |Flusso di posta<br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**Campagna malware rilevata dopo il recapito** <br/> |Genera un avviso quando un numero insolitamente elevato di messaggi contenenti malware viene recapitato alle cassette postali dell'organizzazione. Se si verifica questo evento, Office 365 rimuove i messaggi infetti dalle cassette postali di Exchange Online. Questo criterio è impostato **su un livello** di gravità elevato.  <br/> |Gestione dei rischi<br/> |Sottoscrizione di un componente aggiuntivo per i componenti aggiuntivi di E5/G5 o Office 365 ATP P2  <br/> |
|**La campagna antimalware è stata rilevata e bloccata** <br/> |Genera un avviso quando un utente ha tentato di inviare un numero insolitamente elevato di messaggi di posta elettronica contenenti un determinato tipo di malware per gli utenti dell'organizzazione. Se si verifica questo evento, i messaggi infetti vengono bloccati da Office 365 e non vengono recapitati alle cassette postali. Questo criterio ha un'impostazione di gravità **bassa** .  <br/> |Gestione dei rischi<br/> |Sottoscrizione di un componente aggiuntivo per i componenti aggiuntivi di E5/G5 o Office 365 ATP P2  <br/> |
|**La campagna antimalware rilevata in SharePoint e OneDrive** <br/> |Genera un avviso quando un volume insolitamente elevato di malware o virus viene rilevato nei file che si trovano in siti di SharePoint o negli account di OneDrive nell'organizzazione. Questo criterio è impostato **su un livello** di gravità elevato.  <br/> |Gestione dei rischi<br/> |Sottoscrizione di un componente aggiuntivo per i componenti aggiuntivi di E5/G5 o Office 365 ATP P2  <br/> |
|**Modelli di invio di messaggi di posta elettronica sospetti** <br/> |Genera un avviso quando un utente dell'organizzazione ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato dall'invio di messaggi di posta elettronica. Si tratta di un avviso iniziale per il comportamento che potrebbe indicare che l'account è stato compromesso, ma non abbastanza grave da limitare l'utente. Questo criterio ha un'impostazione di gravità **media** . Anche se è raro, un avviso generato da questo criterio potrebbe essere un'anomalia. Tuttavia, è consigliabile [verificare se l'account utente è stato compromesso](responding-to-a-compromised-email-account.md). <br/> |Gestione dei rischi<br/> |E1/G1, E3/G3 o E5/G5  <br/>|
|**Attività di file utente esterne insolite** <br/> |Genera un avviso quando un numero insolitamente elevato di attività viene eseguito su file in SharePoint o OneDrive da parte di utenti esterni all'organizzazione. Sono incluse attività quali l'accesso ai file, il download di file e l'eliminazione di file. Questo criterio è impostato **su un livello** di gravità elevato.  <br/> |Governance dei dati<br/> |Abbonamento al componente aggiuntivo per la conformità E5/G5, Office 365 ATP P2 o Advanced Compliance  <br/> |
|**Volume insolito di condivisione di file esterni** <br/> |Genera un avviso quando un numero insolitamente elevato di file in SharePoint o OneDrive viene condiviso con utenti esterni all'organizzazione. Questo criterio ha un'impostazione di gravità **media** .  <br/> |Governance dei dati<br/> |Abbonamento al componente aggiuntivo per la conformità E5/G5, Office 365 ATP P2 o Advanced Compliance  <br/> |
|**Volume insolito di eliminazione dei file** <br/> |Genera un avviso quando un numero insolitamente elevato di file viene eliminato in SharePoint o OneDrive in un intervallo di tempo breve. Questo criterio ha un'impostazione di gravità **media** .  <br/> |Governance dei dati <br/> |Abbonamento al componente aggiuntivo per la conformità E5/G5, Office 365 ATP P2 o Advanced Compliance  <br/> |
|**Aumento insolito del messaggio di posta elettronica riportato come phishing** <br/> |Genera un avviso quando si verifica un aumento significativo del numero di persone nell'organizzazione che utilizzano il componente aggiuntivo segnala messaggio in Outlook per segnalare i messaggi come messaggio di posta elettronica di phishing. Questo criterio è impostato **su un livello** di gravità elevato. Per ulteriori informazioni su questo componente aggiuntivo, vedere [use the report Message Add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).  <br/> |Gestione dei rischi<br/> |Sottoscrizione di un componente aggiuntivo per i componenti aggiuntivi di E5/G5 o Office 365 ATP P2  <br/> |
|**Utente con limitazioni all'invio di posta elettronica** <br/> |Genera un avviso quando un utente dell'organizzazione ha la limitazione di inviare la posta in uscita. Questo in genere risulta quando un account è compromesso e l'utente è elencato nella pagina **utenti con restrizioni** nel centro sicurezza & conformità. Per accedere a questa pagina, passare a **threat management > Review > utenti con restrizioni**). Questo criterio è impostato **su un livello** di gravità elevato. Per ulteriori informazioni sugli utenti con restrizioni, vedere [rimozione di un utente, dominio o indirizzo IP da un elenco di blocco dopo l'invio di posta](https://docs.microsoft.com/office365/securitycompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email)indesiderata.  <br/> |Gestione dei rischi<br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|||||
   
Le attività insolite monitorate da alcuni dei criteri incorporati si basano sullo stesso processo dell'impostazione della soglia di avviso descritta in precedenza. Office 365 stabilisce un valore di base che definisce la frequenza normale per l'attività "usuale". Gli avvisi vengono quindi attivati quando la frequenza delle attività monitorate dal criterio di avviso incorporato supera notevolmente il valore previsto.
 
## <a name="viewing-alerts"></a>Visualizzazione degli avvisi

Quando un'attività eseguita dagli utenti dell'organizzazione corrisponde alle impostazioni di un criterio di avviso, viene generato un avviso e visualizzato nella pagina **Visualizza avvisi** nel centro sicurezza e conformità, a seconda delle impostazioni di un criterio di avviso, di un messaggio di posta elettronica la notifica viene inviata anche a un elenco di utenti specificati quando si attiva un avviso. Per ogni avviso, il dashboard nella pagina **Visualizza avvisi** Visualizza il nome del criterio di avviso corrispondente, la gravità e la categoria dell'avviso (definiti nel criterio di avviso) e il numero di volte in cui si è verificata un'attività che ha provocato l'attivazione dell'avviso. generato. Questo valore si basa sull'impostazione di soglia del criterio di avviso. Il dashboard Visualizza anche lo stato di ogni avviso. Per ulteriori [](#managing-alerts) informazioni sull'utilizzo della proprietà Status per gestire gli avvisi, vedere la sezione managing alerts. 
  
Per visualizzare gli avvisi, passare [https://protection.office.com](https://protection.office.com) a e quindi fare clic su **avvisi** \> **Visualizza**avvisi. 
  
![In sicurezza e conformità, fare clic su avvisi, quindi fare clic su Visualizza avvisi per visualizzare gli avvisi](media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)
  
È possibile utilizzare i seguenti filtri per visualizzare un sottoinsieme di tutti gli avvisi nella pagina **Visualizza avvisi** . 
  
- **Stato** : utilizzare questo filtro per visualizzare gli avvisi a cui è assegnato un determinato stato. Lo stato predefinito è **attivo**. Il valore dello stato può essere modificato da un utente o da altri amministratori.
    
- **Criterio** : utilizzare questo filtro per visualizzare gli avvisi che corrispondono all'impostazione di uno o più criteri di avviso. In alternativa, è possibile visualizzare tutti gli avvisi per tutti i criteri di avviso.
    
- **Intervallo di tempo** : utilizzare questo filtro per visualizzare gli avvisi generati in un intervallo di tempo specifico.
    
- **** Severity – utilizzare questo filtro per visualizzare gli avvisi a cui è assegnata una gravità specifica.
    
- **Categoria** : utilizzare questo filtro per visualizzare gli avvisi di una o più categorie di avvisi.

- **Origine** : utilizzare questo filtro per visualizzare gli avvisi attivati dai criteri di avviso nel centro sicurezza e conformità o gli avvisi attivati dai criteri di protezione delle app di Office 365 cloud o entrambi. Per ulteriori informazioni sugli avvisi di sicurezza per le app di Office 365 cloud, vedere la sezione [Visualizzazione avvisi di sicurezza per le app Cloud](#viewing-cloud-app-security-alerts) .

## <a name="rbac-permissions-required-to-view-alerts"></a>Autorizzazioni RBAC necessarie per visualizzare gli avvisi

Le autorizzazioni di controllo di accesso basato sui ruoli (RBAC) assegnate agli utenti nell'organizzazione determinano gli avvisi che un utente può visualizzare nella pagina **Visualizza avvisi** . Come è possibile eseguire questa operazione? I ruoli di gestione assegnati agli utenti (in base alla loro appartenenza ai gruppi di ruoli nel centro sicurezza & conformità) determinano le categorie di avvisi che un utente può visualizzare nella pagina **Visualizza avvisi** . Ecco alcuni esempi:

- I membri del gruppo di ruoli Gestione record possono visualizzare solo gli avvisi generati dai criteri di avviso a cui viene assegnata la categoria di **governance dei dati** .

- I membri del gruppo di ruoli amministratore conformità non possono visualizzare gli avvisi generati dai criteri di avviso a cui è assegnata la categoria **gestione minacce** . 

- I membri del gruppo di ruoli eDiscovery Manager non sono in grado di visualizzare gli avvisi perché nessuno dei ruoli assegnati fornisce l'autorizzazione per visualizzare gli avvisi da qualsiasi categoria di avviso.

Questa struttura (in base alle autorizzazioni RBAC) consente di determinare gli avvisi che possono essere visualizzati (e gestiti) dagli utenti in ruoli specifici per i processi nell'organizzazione. 

Nella tabella seguente sono elencati i ruoli necessari per visualizzare gli avvisi dalle 6 diverse categorie di avviso. La prima colonna nelle tabelle elenca tutti i ruoli nel centro sicurezza & conformità.  Un segno di spunta indica che un utente a cui è assegnato il ruolo può visualizzare gli avvisi dalla categoria di avviso corrispondente elencata nella riga superiore.

Per visualizzare la categoria a cui è assegnato un criterio di avviso predefinito, vedere la tabella nella sezione [criteri di avviso predefiniti](#default-alert-policies) .

|<br/>|Governance dei dati|Prevenzione della perdita di dati|Flusso di posta|Autorizzazioni|Gestione dei rischi|Altri | 
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Registri di controllo <br/> |         ||         |         |         |         |
|Gestione dei casi <br/>|         |         |         |         |         |         |
|Amministratore di conformità<br/>|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Ricerca di conformità<br/>|         |         |         |         |         |         |
|Gestione dei dispositivi<br/>|         |         |         |         |         |         |
|Gestione della disposizione<br/>|         |         |         |         |         |         |
|Gestione della conformità DLP<br/>|         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |
|Esportazione<br/>|         |         |         |         |         |         |
|Tenere<br/>|         |         |         |         |         |         |
|Gestione avvisi<br/>|         |         |         |         |         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configurazione dell'organizzazione|         |         |         |         |         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Anteprima <br/>|         |         |         |         |         |         |
|Gestione dei record <br/>|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|Gestione della conservazione <br/>| ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|Verifica <br/>|         |         |         |         |         |         |
|Decrittografia RMS<br/>|         |         |         |         |         |         |
|Gestione dei ruoli<br/>|         |         |         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |
|Ricerca ed eliminazione<br/>|         |         |         |         |         |         |
|Amministratore della sicurezza<br/>||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| | ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Lettore di sicurezza<br/>|         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| | ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)
|Visualizzazione garanzia del servizio<br/>|         |         |         |         |         |         |
|Amministratore revisione di supervisione<br/>|         |         |         |         |         |         |
|Registri di controllo di sola visualizzazione<br/>|         |         |         |         |         |         |
|Gestione dei dispositivi di sola visualizzazione<br/>|         |         |         |         |         |         |
|Gestione della conformità DLP solo visualizzazione<br/>|         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |
|Visualizzazione-solo Gestione avvisi<br/>|         |         |         |         |         |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Destinatari solo visualizzazione<br/>|         |         |  ![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       |         ||         |
|Gestione dei record di sola visualizzazione<br/>|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|Gestione della conservazione in sola visualizzazione<br/>|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|         |         |         |         |         |         |

**Suggerimento:** Per visualizzare i ruoli assegnati a ognuno dei gruppi di ruoli predefiniti, eseguire i comandi seguenti in PowerShell per il Centro sicurezza & Compliance: 

```
$RoleGroups = Get-RoleGroup

$RoleGroups | foreach {Write-Output -InputObject `r`n,$_.Name,"-----------------------"; Get-RoleGroup $_.Identity | Select-Object -ExpandProperty Roles}
```
È inoltre possibile visualizzare i ruoli assegnati a un gruppo di ruoli nel centro sicurezza & conformità. Passare alla pagina **autorizzazioni** e fare clic su un gruppo di ruoli. I ruoli assegnati sono elencati nella pagina a comparsa.


## <a name="managing-alerts"></a>Gestione degli avvisi

Dopo che gli avvisi sono stati generati e visualizzati nella pagina **Visualizza avvisi** nel centro sicurezza e conformità, è possibile eseguire la valutazione, l'analisi e la risoluzione dei problemi. Di seguito sono riportate alcune attività che è possibile eseguire per gestire gli avvisi. 
  
- **Assegnare uno stato agli avvisi** – è possibile assegnare uno degli Stati seguenti agli avvisi: **attivo** (valore predefinito), **analisi**, **risoluzione**o annullamento. **** È quindi possibile filtrare su questa impostazione per visualizzare gli avvisi con la stessa impostazione di stato. Questa impostazione di stato può contribuire a monitorare il processo di gestione degli avvisi.
    
- **Visualizzare i dettagli degli avvisi** : è possibile fare clic su un avviso per visualizzare una pagina a comparsa con informazioni dettagliate sull'avviso. Le informazioni dettagliate dipendono dal criterio di avviso corrispondente, ma in genere sono incluse le seguenti: nome dell'operazione effettiva che ha attivato l'avviso (ad esempio, un cmdlet), una descrizione dell'attività che ha attivato l'avviso, l'utente o l'elenco di utenti. Gli utenti che hanno attivato l'avviso e il nome e il collegamento del criterio di avviso corrispondente.
    
  - Nome dell'operazione effettiva che ha attivato l'avviso, ad esempio un cmdlet o un'operazione del registro di controllo.
    
  - Descrizione dell'attività che ha attivato l'avviso.
    
  - L'utente che ha attivato l'avviso. Questo è incluso solo per i criteri di avviso che sono configurati per monitorare un singolo utente o una singola attività.
    
  - Numero di volte in cui è stata eseguita l'attività registrata dall'avviso. Tenere presente che questo numero potrebbe non corrispondere al numero effettivo di avvisi correlati elencati nella pagina Visualizza avvisi perché potrebbero essere stati attivati altri avvisi.
    
  - Collegamento a un elenco di attività che include un elemento per ogni attività eseguita che ha attivato l'avviso. Ogni voce di questo elenco identifica quando si è verificato l'attività, il nome dell'operazione effettiva (ad esempio "fileDeleted") e l'utente che ha eseguito l'attività, l'oggetto, ad esempio un file, un caso di eDiscovery, o una cassetta postale, in cui è stata eseguita l'attività e l'indirizzo IP Indirizzo del computer dell'utente. Per gli avvisi correlati al malware, questo collegamento a un elenco di messaggi.
    
  - Il nome (e il collegamento a) del criterio di avviso corrispondente.
    
- Non **visualizzare le notifiche tramite posta elettronica** : è possibile disattivare (o sopprimere) le notifiche tramite posta elettronica dalla pagina del riquadro a comparsa per un avviso. Quando si eliminano le notifiche tramite posta elettronica, Office 365 non invierà notifiche quando le attività o gli eventi che soddisfano le condizioni del criterio di avviso. Tuttavia, gli avvisi vengono attivati quando le attività eseguite dagli utenti soddisfano le condizioni del criterio di avviso. È inoltre possibile disattivare le notifiche di posta elettronica modificando il criterio di avviso.
    
- **Risoluzione degli avvisi** : è possibile contrassegnare un avviso come risolto nella pagina a comparsa per un avviso (che imposta lo stato dell'avviso su **risolto**). A meno che non si modifichi il filtro, gli avvisi risolti non vengono visualizzati nella pagina **Visualizza avvisi** . 
    
## <a name="viewing-cloud-app-security-alerts"></a>Visualizzazione degli avvisi di sicurezza delle app Cloud
  
Gli avvisi attivati dai criteri di protezione delle app di Office 365 cloud sono ora visualizzati nella pagina **Visualizza avvisi** nel centro sicurezza e conformità. Sono inclusi gli avvisi attivati da criteri di attività e avvisi attivati dai criteri di rilevamento delle anomalie in Office 365 cloud app Security. Questo significa che è possibile visualizzare tutti gli avvisi nel centro sicurezza e conformità. Office 365 cloud app Security è disponibile solo per le organizzazioni con un abbonamento a Office 365 Enterprise E5 o Office 365 US Government G5. Per ulteriori informazioni, vedere [Overview of cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

Le organizzazioni che dispongono di Microsoft cloud app Security come parte di un abbonamento Enterprise Mobility + Security E5 o come servizio autonomo possono anche visualizzare gli avvisi di sicurezza delle app Cloud correlati alle app e ai servizi di Office 365 nel centro sicurezza & Compliance.

Per visualizzare solo gli avvisi di sicurezza delle app Cloud nel centro sicurezza e conformità, utilizzare il filtro di **origine** e selezionare **cloud app Security**.

![Utilizzare il filtro di origine per visualizzare solo gli avvisi di sicurezza delle app Cloud](media/FilterCASAlerts.png)

Analogamente a un avviso attivato da un criterio di avviso per il Centro sicurezza e conformità, è possibile fare clic su un avviso di protezione delle app cloud per visualizzare una pagina a comparsa con informazioni dettagliate sull'avviso. L'avviso include un collegamento per visualizzare i dettagli e gestire l'avviso nel cloud app Security Portal e un collegamento ai criteri di protezione delle app cloud corrispondenti che hanno attivato l'avviso. Vedere [monitorare gli avvisi in cloud app Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts).

![I dettagli degli avvisi contengono collegamenti al portale di cloud app Security](media/CASAlertDetail.png)

> [!IMPORTANT]
> Se si modifica lo stato di un avviso di protezione delle app Cloud nel centro sicurezza e conformità, non verrà aggiornato lo stato della risoluzione per lo stesso avviso nel portale di protezione delle app cloud. Ad esempio, se si contrassegna lo stato dell'avviso come **risolto** nel centro sicurezza e conformità, lo stato dell'avviso nel portale di sicurezza delle app Cloud è invariato. Per risolvere o ignorare un avviso di protezione delle app Cloud, gestire l'avviso nel portale di sicurezza cloud app.
