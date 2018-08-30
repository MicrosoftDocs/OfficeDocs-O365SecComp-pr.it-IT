---
title: Gestire i messaggi in quarantena e i file in qualità di amministratore in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/19/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
description: 'Come un amministratore può visualizzare, rilasciare e segnalare i messaggi in quarantena falsi positivi in Office 365. È possibile impostare i criteri in modo che filtra i messaggi di Office 365 e li invia in quarantena per diverse ragioni: perché che sono stati identificati come posta indesiderata, blocco, phishing, malware o perché sono corrispondenti a una regola di flusso di posta elettronica. '
ms.openlocfilehash: f30604da185b3455d89ae7c1206bda2149ef7778
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530851"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a>Gestire i messaggi in quarantena e i file in qualità di amministratore in Office 365

Come amministratore, si può visualizzare, versione ed eliminare i messaggi in quarantena e report messaggi falsi positivi in quarantena in Office 365. È anche possibile visualizzare, scaricare ed eliminare i file in quarantena acquisiti dall'anticipo Threat Protection (degli strumenti di analisi) per SharePoint Online, OneDrive for Business e Teams Microsoft. È possibile impostare i criteri in modo che filtra i messaggi di Office 365 e li invia in quarantena per diverse ragioni: perché che sono stati identificati come posta indesiderata, posta inviata in blocco, posta elettronica di phishing, che contiene malware, o vengono corrispondenti a una regola di flusso di posta elettronica.
  
Per impostazione predefinita, Office 365 invia messaggi di phishing e messaggi che contengono malware direttamente in quarantena. Altri messaggi filtrati vengono inviati alla cartella posta indesiderata degli utenti se non si imposta un criterio di inviarle in quarantena.
  
È necessario disporre delle autorizzazioni di amministratore in Office 365 per l'utilizzo con i messaggi in quarantena inviate ad altri utenti e operare con i file in quarantena.
  
> [!IMPORTANT]
> Per impostazione predefinita, la posta indesiderata, blocco, malware, phishing e messaggi messi in quarantena perché sono corrispondenti a una regola di flusso di posta elettronica vengono mantenuti in quarantena per 30 giorni. È possibile personalizzare il tempo di quarantena in impostazioni di protezione da posta indesiderate in sicurezza &amp; centro conformità. Quando Office 365 consente di eliminare un messaggio in quarantena, è Impossibile annullare l'operazione. Se si desidera, è possibile modificare il periodo di conservazione per i messaggi in quarantena in Criteri di filtro di protezione da posta indesiderata. Per ulteriori informazioni, vedere [impostazione il periodo di conservazione quarantena](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in questo articolo. 
  
## <a name="view-your-organizations-quarantined-messages"></a>Visualizzare i messaggi in quarantena dell'organizzazione

1. Utilizzando un account di lavoro o della scuola con privilegi di amministratore globale in 365organization l'ufficio, accedere a Office 365 e [passare a Centro connessioni di sicurezza e conformità](go-to-the-securitycompliance-center.md).
    
2. Nell'elenco a sinistra espandere **Threat Management**, scegliere **Rivedi**e quindi scegliere **quarantena**.
    
    > [!TIP]
    > Per passare direttamente alla pagina di **quarantena** per la protezione &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
    Per impostazione predefinita, la sicurezza &amp; centro conformità consente di visualizzare tutti i messaggi di posta elettronica in quarantena come posta indesiderata. I messaggi vengono ordinati in ordine cronologico in base alla **Data** stato ricevuto il messaggio. **Mittente**, **oggetto**e la data di scadenza (in **scadenza** ) vengono inoltre visualizzate per ogni messaggio. È possibile ordinare in un campo facendo clic su intestazione di colonna corrispondente; Fare clic su un'intestazione di colonna per annullare l'ordinamento. 
    
3. È possibile visualizzare un elenco di tutti i messaggi in quarantena oppure è possibile ridurre dal filtro set di risultati. È possibile solo eseguire operazioni su un massimo di 100 elementi, in blocco in modo che il filtro consente inoltre di ridurre il set di risultati se un numero superiore di. È possibile filtrare i messaggi per un motivo di quarantena singolo rapidamente selezionando un'opzione di filtro nella parte superiore della pagina. Opzioni includono:
    
  - Posta identificata come posta indesiderata
    
  - Posta elettronica in quarantena perché corrispondeva a un criterio per impostare una regola del flusso di posta (denominata anche una regola di trasporto)
    
  - Posta identificata come posta inviata in blocco
    
  - Posta identificata come posta phishing
    
  - Posta elettronica in quarantena perché contiene malware
    
Inoltre, l'amministratore, è possibile scegliere di filtrare tutti i messaggi per l'organizzazione o solo i messaggi inviati all'utente. Visualizza solo gli utenti possono terminare e con i messaggi inviati a tali.
  
È inoltre possibile filtrare i risultati per individuare i messaggi specifici. Per suggerimenti, vedere [per filtrare i risultati e individuare i file e i messaggi in quarantena](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in questo articolo. 
  
Dopo aver individuato uno specifico messaggio in quarantena, fare clic sul messaggio per visualizzarne i dettagli ed eseguire azioni, ad esempio rilasciare il messaggio di posta in arrivo di una persona.
  
## <a name="view-your-organizations-quarantined-files"></a>Visualizzare i file in quarantena dell'organizzazione

1. Utilizzo di un account di lavoro o della scuola con privilegi di amministratore globale dell'organizzazione Office 365, accedere a Office 365 e [passare a Centro connessioni di sicurezza e conformità](go-to-the-securitycompliance-center.md).
    
2. A sinistra, espandere **Threat Management**, scegliere **Rivedi**e quindi scegliere **quarantena**. 
    
    > [!TIP]
    > Per passare direttamente alla pagina di **quarantena** per la protezione &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
3. Per impostazione predefinita, la pagina Visualizza messaggi di posta elettronica in quarantena. Per visualizzare i file in quarantena, impostare i filtri nella parte superiore della pagina da visualizzare i **file**, in quarantena a causa di **malware**. È necessario disporre delle autorizzazioni di amministratore in Office 365 per l'utilizzo con i file in quarantena. 
    
4. I file sono ordinati in ordine cronologico sulla base della data che il file è stato messo in quarantena. L'ultimo **utente** che ha modificato il file, il **servizio** a cui è stato registrato il file, il **Nome del File**, **posizione**, **Dimensioni dei File**, e vengono elencate anche la data di scadenza ( **scadenza**) per ogni file. È possibile ordinare in un campo facendo clic su un'intestazione; Fare clic su un'intestazione di colonna per annullare l'ordinamento.
    
È possibile visualizzare un elenco di tutti i file in quarantena oppure è possibile cercare i file specifici da un filtro. Proprio come messaggi, è possibile solo eseguire operazioni su un massimo di 100 elementi in blocco. Attualmente, la sicurezza &amp; centro conformità consente di visualizzare e gestire i file che si trovano in quarantena perché sono stati identificati come contenente malware. Per suggerimenti, vedere [per filtrare i risultati e individuare i file e i messaggi in quarantena](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in questo articolo. 
  
## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a>Per filtrare i risultati e individuare i file e i messaggi in quarantena
<a name="BKMK_AdvSearch"> </a>

A seconda delle impostazioni, potrebbe essere una quantità elevata di file e i messaggi in quarantena. Per trovare un messaggio specifico o file o un insieme di file o i messaggi, è possibile filtrare elementi messi in quarantena in base a una serie di informazioni aggiuntive.
  
1. Nella pagina di **quarantena** , verificare che la riga superiore dei filtri è impostata su Visualizza messaggi o i file: 
    
  - Per cercare i file, impostare i filtri per visualizzare i **file** in quarantena a causa di **malware**.
    
    Per i file in quarantena, nella pagina viene visualizzato in quarantena tutti i file, non solo il proprio, indipendentemente dal fatto che cosa indicano it da visualizzare.
    
  - Per cercare i messaggi in quarantena, impostare i filtri per Mostra **tutto** o **solo personale** **posta elettronica**. Per l'ultimo filtro scegliere il tipo di messaggio in quarantena che si sta cercando. È possibile cercare i messaggi in quarantena identificati come **posta indesiderata**per i messaggi corrispondenti a un flusso di posta o **della regola di trasporto**, posta **inviata in blocco** , posta elettronica di **phishing** o posta che contiene **malware**.
    
2. Nella sezione **Ordina per**, selezionare il filtro o i filtri da utilizzare per la ricerca negli elenchi a discesa. Le opzioni variano in base alle se si esegue la ricerca per i file o i messaggi. I caratteri jolly non sono supportati nei campi di ricerca in questa fase.
    
    Per i file e messaggi, è possibile scegliere di filtrare in base alla data del messaggio o file è stato messo in quarantena. È possibile specificare la data o un intervallo di date, incluso il tempo. È inoltre possibile filtrare i risultati della ricerca per la data di scadenza in cui il file o il messaggio verrà eliminato dalla quarantena oppure è possibile utilizzare una combinazione dei filtri. Per eseguire la ricerca dalla data di scadenza, scegliere **filtro avanzato**. In **scadenza**, è possibile selezionare i messaggi che verranno eliminati dalla quarantena entro le prossime 24 ore ( **ora**), entro le prossime 48 ore ( **successivo 2 giorni**), della settimana successiva ( **successivo 7 giorni**) o è possibile selezionare un intervallo di tempo personalizzato.
    
    Per i messaggi, sono disponibili le opzioni aggiuntive seguenti:
    
  - **ID del messaggio**. Utilizzare questa opzione per identificare un messaggio specifico quando si conosce l'ID del messaggio. 
    
    Ad esempio, se inviato da un messaggio specifico o progettato per un utente all'interno dell'organizzazione, ma non raggiunto la destinazione, è possibile cercare il messaggio utilizzando una traccia dei messaggi (vedere [eseguire una traccia dei messaggi e visualizzare i risultati](https://go.microsoft.com/fwlink/?LinkId=799737)). Se si rileva che è stato inviato il messaggio in quarantena, ad esempio perché corrispondenti a una regola del flusso di posta elettronica o è stato identificato come posta indesiderata, è possibile trovare con facilità questo messaggio in quarantena, specificando il relativo ID del messaggio. È necessario includere la stringa di ID messaggio completo. Ciò potrebbe includere parentesi angolari (\<\>), ad esempio:
    
    \<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\>
    
  - **Indirizzo di posta elettronica del mittente**. Scegliere filtrare in base a un indirizzo di posta elettronica singolo mittente. 
    
  - **Indirizzo di posta elettronica destinatario**. Scegliere filtrare in base a un indirizzo di posta elettronica del destinatario singolo. 
    
  - **Oggetto**. Immettere l'oggetto di un indirizzo di posta elettronica che si desidera trovare. Dal momento che la ricerca con caratteri jolly non è supportata, è necessario utilizzare l'intero oggetto del messaggio nell'ordine indicato per la ricerca per restituire il messaggio nei risultati. La ricerca non è tra maiuscole e minuscole. 
    
## <a name="view-details-about-quarantined-messages-and-files"></a>Visualizzare i dettagli relativi file e i messaggi in quarantena
<a name="BKMK_ViewDetails"> </a>

Quando si seleziona un elemento visualizzato nell'elenco di quarantena, verrà visualizzato un riepilogo delle proprietà nel riquadro **dei dettagli** sul lato destro della sicurezza &amp; centro conformità. 
  
 **Dettagli visualizzati per i messaggi in quarantena**
  
- **ID del messaggio**. Identificatore univoco per il messaggio. 
    
- **Indirizzo del mittente**. Che ha inviato il messaggio. 
    
- **Ricevuti**. Data e ora che il messaggio è stato ricevuto. 
    
- **Oggetto**. Il testo della riga dell'oggetto del messaggio. 
    
- **Tipo**. Mostra se un messaggio è stato identificato come **posta indesiderata**, **blocco**, **per attività di phishing**, corrispondenti a una regola di flusso di posta elettronica ( **regola di trasporto**) o è stato identificato come contenente **Malware**.
    
- Non **scade**. Data e ora in cui il messaggio verrà automaticamente eliminato dalla quarantena. 
    
- **Rilasciato a**. Tutti gli indirizzi di posta elettronica (se esistenti) a cui il messaggio è stato rilasciato. 
    
- **Non è ancora rilasciato a**. Tutti gli indirizzi di posta elettronica (se esistenti) a cui il messaggio non ancora rilasciato. 
    
 **Dettagli visualizzati per i file in quarantena**
  
- **Nome di file** Il nome del file in quarantena. 
    
- **Percorso del sito** URL che definisce la posizione del file in Office 365. 
    
- **Rilevato data / ora** Data e ora che il file è stato messo in quarantena. 
    
- **Scadenza** Data quando il messaggio verrà eliminato dalla quarantena. 
    
- **Rilevato dal** Il metodo utilizzato per rilevare il malware nel file. Può trattarsi di strumenti di analisi (Advanced Threat Protection) o motore antimalware di Microsoft. 
    
- **Rilasciato** Descrive se il file è stato rilasciato. 
    
- **Nome del malware** Famiglia e il nome del malware rilevato nel file. 
    
- **ID documento** Un identificatore univoco per il documento. 
    
- **Dimensioni dei file** La dimensione del file in KB. 
    
- **Organizzazione** ID univoco dell'organizzazione in Office 365. 
    
- **Modificato da** L'account di lavoro o della scuola dell'ultimo utente che ha modificato il file. 
    
- **Dimensioni dei file** La dimensione del file in KB. 
    
- **Hash SHA256** Il valore hash del file. È possibile utilizzare questo per cercare altri archivi reputazione possono avere o provare a utilizzare altre posizioni qualora sia il file nel proprio ambiente. 
    
## <a name="managing-messages-and-files-in-quarantine"></a>Gestione di file e i messaggi in quarantena
<a name="BKMK_ManageQuarantinedItem"> </a>

Dopo aver selezionato un messaggio o un gruppo di messaggi sono disponibili diverse opzioni per la gestione dei messaggi in quarantena.
  
- Non effettuare alcuna operazione. Se si sceglie di non eseguire alcuna operazione, il messaggio verrà eliminato da Office 365 automaticamente alla scadenza. Per impostazione predefinita, la posta indesiderata, blocco, malware, phishing e i messaggi in quarantena perché sono corrispondenti a una regola di flusso di posta elettronica vengono mantenuti in quarantena per 30 giorni. Quando Office 365 consente di eliminare un messaggio in quarantena, è Impossibile annullare l'operazione. Se si desidera, è possibile modificare il periodo di conservazione per i messaggi in quarantena configurando l'impostazione della **posta indesiderata Mantieni per (giorni)** in Criteri di protezione da posta indesiderati. Per ulteriori informazioni, vedere [impostazione il periodo di conservazione quarantena](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in questo articolo. 
    
- **Intestazione del messaggio di visualizzazione** Selezionare questo collegamento per visualizzare il testo dell'intestazione di messaggio. Per analizzare l'intestazione in modo approfondito, copiare il testo dell'intestazione di messaggio negli Appunti e quindi scegliere **Dell'analizzatore dell'intestazione di messaggio Microsoft** per accedere alla analizzatore connettività remota (pulsante destro del mouse, quindi scegliere **Apri in una nuova scheda** se non si desidera lasciare Office 365 per completare questa attività). Incolla l'intestazione del messaggio alla pagina nella sezione analizzatore dell'intestazione di messaggio e scegliere **Analizza le intestazioni**.
    
- **Anteprima messaggio** Consente di vedere non elaborati o versioni HTML del testo del corpo del messaggio. Nella visualizzazione HTML collegamenti disattivati. 
    
- **Download dei messaggi** o **scaricare i file**. Scegliere questa opzione per scaricare una copia del messaggio o file sul dispositivo locale. È necessario verificare di avere compreso i rischi associati con lo scaricamento degli elementi dalla quarantena prima che si sarà consentito effettuare questa operazione. I messaggi vengono salvati in formato EML a una cartella specificata. Tali file vengono salvati nel formato originale.
    
- **Eliminare** Se si desidera, è possibile eliminare immediatamente un elemento in quarantena (o un insieme di elementi) anziché attendere la data di scadenza impostata da Office 365. Per eliminare un messaggio o file, nell'elenco di quarantena, selezionare l'elemento e quindi fare clic su **Elimina**. Per eliminare più elementi contemporaneamente, selezionare la casella di controllo a sinistra di elementi nell'elenco quarantena e quindi scegliere **Elimina messaggi selezionati** o **eliminare i file selezionati**nella pagina **operazioni globali** che viene visualizzata.
    
- **Versione** Rilasciare un elemento in quarantena (o un insieme di elementi) e segnalare gli elementi come erroneamente messi in quarantena (falsi positivi) a Microsoft. 
    
    Per segnalare un singolo messaggio o file, nell'elenco di quarantena, selezionare l'elemento, scegliere **versione file** o un **messaggio di rilascio**. Nella pagina successiva verificare che sia selezionato **messaggi rapporto a Microsoft per l'analisi** o **i file di report Microsoft per l'analisi** . 
    
    Per rilasciare più elementi contemporaneamente, selezionare la casella di controllo a sinistra di elementi nell'elenco quarantena e quindi nella pagina **operazioni globali** che viene visualizzata scegliere **rilasciare i file** o **rilasciare i messaggi**. Nella pagina successiva verificare che sia selezionato **messaggi rapporto a Microsoft per l'analisi** o **i file di report Microsoft per l'analisi** . 
    
Se si sta rilasciare i messaggi, tenere presente quanto segue:
  
- Quando si esegue una versione di blocco dei messaggi più contemporaneamente, i messaggi vengono rilasciati a tutti i destinatari originariamente identificati. Se si desidera solo rilasciare i messaggi solo a destinatari specifici, è necessario rilasciare i messaggi uno alla volta e identificare i destinatari singolarmente.
    
- Un messaggio non può essere rilasciato più volte al destinatario stesso.
    
- Se si sta rilasciare un messaggio a più di un destinatario, solo i destinatari che non è in precedenza ricevuto il messaggio verranno visualizzato nell'elenco dei destinatari possibili.
    
- Quando si sceglie di segnalare falsi positivi se il messaggio o rilasciare i messaggi messi in quarantena come posta indesiderata, blocco, phishing o come contenente malware, verrà riportato anche il messaggio al Team di analisi della posta indesiderata di Microsoft. Il team verrà valutare e analizzare il messaggio e, in base ai risultati dell'analisi, le regole di filtro dei contenuti da posta indesiderata a livello di servizio possono essere regolate per consentire il messaggio attraverso.
    
## <a name="setting-the-quarantine-retention-period"></a>Impostare il periodo di conservazione quarantena
<a name="BKMK_ModQuarantineTime"> </a>

È possibile configurare quanto a lungo messaggi e file resterà in quarantena prima della scadenza. Per impostazione predefinita, vengono conservati gli elementi in quarantena per 30 giorni. Si configura questa impostazione per ogni criterio creati personalmente. È inoltre possibile modificare il valore per il criterio predefinito, come descritto in questo articolo. 
  
### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a>Per modificare il periodo di conservazione quarantena per il criterio di filtro posta indesiderata predefinito per la protezione e centro conformità

1. Utilizzo di un account di lavoro o della scuola con privilegi di amministratore globale dell'organizzazione Office 365, accedere a Office 365 e [passare a Centro connessioni di sicurezza e conformità](go-to-the-securitycompliance-center.md).
    
2. A sinistra, espandere **Threat Management**, scegliere **criterio**e quindi fare clic su **protezione da posta indesiderata**. 
    
    > [!TIP]
    > Per passare direttamente alla pagina di **protezione da posta indesiderata** in sicurezza &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)
  
3. Scegliere **personalizzato** per visualizzare la scheda **impostazioni personalizzate** . 
    
4. Espandere la riga di **criteri di filtro posta indesiderata predefiniti (sempre via)** . 
    
5. Scegliere **Modifica criterio**. Le impostazioni per il criterio di filtro posta indesiderata predefinito visualizzato in una nuova pagina.
    
6. Espandere **posta indesiderata e operazioni in blocco**.
    
7. In **quarantena**, nella casella di testo **della posta indesiderata Mantieni per (giorni)** immettere la quantità di tempo che si desidera Office 365 per conservare i file e messaggi in quarantena. Il valore predefinito è 30 giorni. Questo è il valore massimo. 
    
8. Fare clic su **Salva**.
    

