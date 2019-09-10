---
title: Gestire i messaggi e i file in quarantena come amministratore in Office 365
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 09/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a visualizzare e gestire i messaggi in quarantena nel centro sicurezza & conformità di Office 365.
ms.openlocfilehash: 0b67abe3dbf21650925b53d2882bc40096d6a646
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822526"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Gestire i messaggi e i file in quarantena come amministratore in Office 365

Come amministratore, è possibile visualizzare, rilasciare ed eliminare i messaggi in quarantena e segnalare i messaggi in quarantena falsi positivi in Office 365. È inoltre possibile visualizzare, scaricare ed eliminare i file in quarantena acquisiti da Advance Threat Protection (ATP) per SharePoint Online, OneDrive for business e Microsoft teams. È possibile configurare i criteri in modo che Office 365 filtri i messaggi e li invii in quarantena per diversi motivi: perché sono stati identificati come posta indesiderata, messaggi in blocco, messaggi di phishing, contenenti malware o perché corrispondono a una regola del flusso di posta.

Per impostazione predefinita, Office 365 invia i messaggi di phishing e i messaggi contenenti malware direttamente in quarantena. Gli altri messaggi filtrati vengono inviati alla cartella posta indesiderata degli utenti, a meno che non sia stato impostato un criterio per inviarli alla quarantena.

Per visualizzare ed eseguire azioni sui messaggi in quarantena nel centro sicurezza & Compliance, è necessario che l'account disponga di una delle autorizzazioni seguenti:

**Ruolo destinatari di sola visualizzazione**: visualizzare l'elenco dei messaggi in quarantena.

**Ruolo lettore di sicurezza**: consente di visualizzare l'elenco dei messaggi in quarantena e le relative intestazioni del messaggio.

**Ruolo amministratore sicurezza**: consente di visualizzare l'elenco dei messaggi in quarantena e le relative intestazioni del messaggio. visualizzare in anteprima, rilasciare, eliminare e scaricare i messaggi in quarantena.

Per impostazione predefinita, i gruppi di ruoli amministratore sicurezza e gestione organizzazione nel centro sicurezza & conformità dispongono del ruolo di amministratore della sicurezza assegnato (pertanto l'appartenenza a uno di questi gruppi di ruolo fornisce le autorizzazioni). Per ulteriori informazioni, vedere [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!IMPORTANT]
> Per impostazione predefinita, i messaggi di posta indesiderata, di massa e di phishing vengono mantenuti in quarantena per 30 giorni. I messaggi in quarantena perché corrispondono a una regola del flusso di posta vengono mantenuti in quarantena per 7 giorni. I messaggi di malware vengono mantenuti in quarantena per 15 giorni. È possibile personalizzare il tempo di quarantena della posta indesiderata nelle impostazioni di protezione da posta indesiderata nel centro sicurezza & conformità. Quando Office 365 Elimina un messaggio dalla quarantena, non è possibile riottenerlo. Se lo si desidera, è possibile modificare il periodo di conservazione per i messaggi in quarantena nei criteri di filtro della protezione da posta indesiderata. Per ulteriori informazioni, vedere la sezione [impostare il periodo di conservazione della quarantena](#set-the-quarantine-retention-period) in questo argomento.

## <a name="view-your-organizations-quarantined-messages"></a>Visualizzare i messaggi in quarantena dell'organizzazione

1. [Aprire il Centro sicurezza & Compliance](go-to-the-securitycompliance-center.md) e passare alla **quarantena**di **Verifica** \> **della gestione** \> delle minacce.

   > [!TIP]
   > Per passare direttamente alla pagina di **quarantena** , utilizzare questo URL: [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine).

   Per impostazione predefinita, il Centro sicurezza & conformità Visualizza tutti i messaggi di posta elettronica messi in quarantena come posta indesiderata. I messaggi vengono ordinati dal più recente al più vecchio in base alla **Data** in cui il messaggio è stato ricevuto. Per ogni messaggio vengono visualizzati anche il **mittente**, l' **oggetto**e la data di scadenza (in **scadenza**). È possibile ordinare su un campo facendo clic sull'intestazione di colonna corrispondente. fare clic su un'intestazione di colonna una seconda volta per invertire la sequenza di ordinamento.

2. È possibile visualizzare un elenco di tutti i messaggi in quarantena oppure ridurre il set di risultati in base al filtro. È possibile eseguire operazioni in blocco solo su un massimo di 100 elementi, pertanto il filtro può anche contribuire a ridurre il set di risultati se si dispone di un numero superiore. È possibile filtrare rapidamente i messaggi per una singola causa di quarantena scegliendo un'opzione dal filtro nella parte superiore della pagina. Le opzioni includono:

   - Posta elettronica identificata come posta indesiderata

   - Posta in quarantena perché corrisponde a un criterio impostato da una regola del flusso di posta (nota anche come regola di trasporto)

   - Posta elettronica identificata come posta in blocco

   - Posta elettronica identificata come messaggio di phishing

   - Posta in quarantena perché contiene malware

Come amministratore, è anche possibile scegliere di filtrare tutti i messaggi per l'organizzazione o solo i messaggi inviati all'utente. Gli utenti finali possono visualizzare e utilizzare solo i messaggi che sono stati inviati a loro.

È inoltre possibile filtrare i risultati per individuare messaggi specifici. Per suggerimenti, vedere la sezione [filtrare i risultati per trovare i messaggi e i file in quarantena](#filter-the-results-to-find-quarantined-messages-and-files) in questo argomento.

Dopo aver individuato uno specifico messaggio in quarantena, fare clic sul messaggio per visualizzarne i dettagli e intraprendere azioni, ad esempio il rilascio del messaggio alla cassetta postale di un utente.

## <a name="view-your-organizations-quarantined-files"></a>Visualizzare i file in quarantena dell'organizzazione

1. [Aprire il Centro sicurezza & Compliance](go-to-the-securitycompliance-center.md) e passare alla **quarantena**di **Verifica** \> **della gestione** \> delle minacce.

   > [!TIP]
   > Per passare direttamente alla pagina di **quarantena** nel centro sicurezza & conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)

   Per impostazione predefinita, la pagina Visualizza i messaggi di posta elettronica in quarantena. Per visualizzare i file in quarantena, impostare i filtri nella parte superiore della pagina per visualizzare **i file**, in quarantena a causa di **malware**.

   I file sono ordinati dal più recente al più vecchio in base alla data in cui il file è stato messo in quarantena. L' **utente** che ha modificato l'ultima volta il file, il **servizio** a cui è stato inviato il file, il **nome del file**, la **posizione**, la **dimensione del file**e la data di scadenza ( **scade**) sono elencati anche per ogni file. È possibile ordinare su un campo facendo clic su un'intestazione. fare clic su un'intestazione di colonna una seconda volta per invertire la sequenza di ordinamento.

2. È possibile visualizzare un elenco di tutti i file in quarantena oppure è possibile cercare file specifici filtrando. Analogamente ai messaggi, è possibile eseguire operazioni in blocco solo su un massimo di 100 elementi. Attualmente, il Centro sicurezza & conformità consente di visualizzare e gestire i file in quarantena perché sono stati identificati come contenenti malware. Per suggerimenti, vedere la sezione successiva.

## <a name="filter-the-results-to-find-quarantined-messages-and-files"></a>Filtrare i risultati per trovare i messaggi e i file in quarantena

A seconda delle impostazioni, è possibile che vi siano molti messaggi e file in quarantena. Per trovare un messaggio o un file o un insieme di messaggi specifici, è possibile filtrare gli elementi in quarantena in base a una serie di informazioni aggiuntive.

1. Nella pagina **quarantena** verificare che la riga superiore dei filtri sia impostata in modo da visualizzare i messaggi o i file in base alle esigenze:

   - Per cercare i file, impostare i filtri per visualizzare **i file** in quarantena a causa di **malware**.

     Per i file in quarantena, nella pagina vengono visualizzati tutti i file in quarantena, non solo quelli personali, indipendentemente dal tipo di informazioni che si desidera visualizzare.

   - Per cercare i messaggi in quarantena, impostare filtri per visualizzare **tutto** o **solo il mio** **messaggio di posta elettronica**. Per l'ultimo filtro scegliere il tipo di messaggio in quarantena che si sta cercando. È possibile cercare i messaggi in quarantena identificati come **posta indesiderata**, per i messaggi che corrispondono a una regola del flusso di posta (**regola di trasporto**), alla posta in **blocco** , alla posta elettronica di **phishing** o alla posta che contiene **malware**.

2. In **Ordina risultati**fare clic sul filtro o sui filtri che si desidera utilizzare per la ricerca negli elenchi a discesa. Le opzioni variano in base al fatto che si cerchino file o messaggi. I caratteri jolly non sono supportati nei campi di ricerca in questo momento.

   Sia per i file che per i messaggi, è possibile scegliere di filtrare in base alla data in cui il messaggio o il file è stato inviato alla quarantena. È possibile specificare la data o un intervallo di date, inclusa l'ora. È inoltre possibile filtrare i risultati della ricerca in base alla data di scadenza in cui il file o il messaggio verrà eliminato dalla quarantena oppure è possibile utilizzare una combinazione di filtri. Per eseguire la ricerca in base alla data di scadenza, scegliere **filtro avanzato**. In **scadenza**, è possibile selezionare i messaggi che verranno eliminati dalla quarantena entro le 24 ore successive ( **oggi**), entro le 48 ore successive ( **prossimi 2 giorni**), entro la settimana successiva ( **prossimi 7 giorni**) oppure è possibile selezionare un intervallo di tempo personalizzato.

   Per i messaggi, sono disponibili le seguenti opzioni aggiuntive:

   - **ID messaggio**: utilizzarlo per identificare un messaggio specifico quando si conosce l'ID del messaggio.

     Ad esempio, se un messaggio specifico viene inviato o destinato a un utente dell'organizzazione, ma non ha mai raggiunto la destinazione, è possibile cercare il messaggio utilizzando una [traccia dei messaggi](message-trace-scc.md). Se si rileva che il messaggio è stato inviato alla quarantena, probabilmente perché corrisponde a una regola del flusso di posta o è stato identificato come posta indesiderata, è possibile trovare facilmente questo messaggio in quarantena specificando l'ID del messaggio. Assicurarsi di includere la stringa dell'ID del messaggio completo. Questo può includere parentesi angolari\<\>(), ad esempio `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`:.

   - **Indirizzo di posta elettronica del mittente**: scegliere di filtrare in base a un singolo indirizzo di posta elettronica del mittente.

   - **Indirizzo di posta elettronica del destinatario**: scegliere di filtrare in base a un singolo indirizzo di posta elettronica del destinatario.

   - **Oggetto**. Immettere l'oggetto di un indirizzo di posta elettronica che si desidera trovare. Poiché la ricerca con caratteri jolly non è supportata, è necessario utilizzare l'intero oggetto del messaggio affinché la ricerca restituisca il messaggio nei risultati. La ricerca non è con distinzione tra maiuscole e minuscole.

## <a name="view-details-about-quarantined-messages-and-files"></a>Visualizzare i dettagli relativi ai messaggi e ai file in quarantena

Quando si seleziona un elemento visualizzato nell'elenco quarantena, nella parte destra del Centro sicurezza & conformità verrà visualizzato un riepilogo delle relative proprietà nel riquadro dei **Dettagli** .

### <a name="details-displayed-for-quarantined-messages"></a>Dettagli visualizzati per i messaggi in quarantena

- **ID messaggio**: identificatore univoco per il messaggio.

- **Indirizzo mittente**: chi ha inviato il messaggio.

- **Received**: la data e l'ora in cui il messaggio è stato ricevuto.

- **Subject**: il testo della riga dell'oggetto del messaggio.

- **Tipo**: indica se un messaggio è stato identificato come **posta indesiderata**, in **blocco**, **phishing**, corrispondente a una regola del flusso di posta (**regola di trasporto**) oppure è stato identificato come contenente **malware**.

- **Scade**: la data e l'ora in cui il messaggio verrà eliminato automaticamente dalla quarantena.

- **Rilasciato su**: tutti gli indirizzi di posta elettronica (se presenti) a cui è stato rilasciato il messaggio.

- **Non ancora rilasciato**: tutti gli indirizzi di posta elettronica (se presenti) a cui il messaggio non è stato ancora rilasciato.

### <a name="details-displayed-for-quarantined-files"></a>Dettagli visualizzati per i file in quarantena

- **Nome file**: il nome del file in quarantena.

- **Percorso del sito**: URL che definisce il percorso del file in Office 365.

- **Data/ora rilevata**: data e ora in cui il file è stato messo in quarantena.

- **Scade**: la data in cui il messaggio verrà eliminato dalla quarantena.

- **Rilevato da**: il metodo utilizzato per rilevare il malware nel file. Questo può essere ATP (Advanced Threat Protection) o il motore antimalware di Microsoft.

- **Released**: viene descritto se il file è stato rilasciato o meno.

- **Nome malware**: famiglia e nome del malware rilevato nel file.

- **ID documento**: identificatore univoco per il documento.

- **Dimensione del file**: le dimensioni del file in KB.

- **Organizzazione**: ID univoco dell'organizzazione in Office 365.

- **Modified by**: l'account aziendale o dell'Istituto di istruzione dell'utente che ha modificato il file.

- **Dimensione del file**: le dimensioni del file in KB.

- **Hash SHA256**: l'hash del file. È possibile utilizzare questa pagina per cercare altri archivi di reputazione che potrebbero essere presenti o per individuare il percorso in cui si trova il file nell'ambiente in uso.

## <a name="manage-messages-and-files-in-quarantine"></a>Gestire i messaggi e i file in quarantena

Dopo aver selezionato un messaggio o un gruppo di messaggi in quarantena, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi:

- Non eseguire alcuna operazione: se si sceglie di non eseguire alcuna operazione, il messaggio verrà eliminato automaticamente da Office 365 alla scadenza. Per impostazione predefinita, la posta indesiderata, la massa, il malware, il phishing e i messaggi in quarantena perché corrispondono a una regola del flusso di posta vengono mantenuti in quarantena per 30 giorni. Quando Office 365 Elimina un messaggio dalla quarantena, non è possibile riottenerlo. Se lo si desidera, è possibile modificare il periodo di conservazione per i messaggi in quarantena configurando l'impostazione **Mantieni posta indesiderata per (giorni)** nei criteri di protezione da posta indesiderata. Per ulteriori informazioni, vedere la sezione [impostare il periodo di conservazione della quarantena](#set-the-quarantine-retention-period) in questo argomento.

- **Visualizza intestazione messaggio**: scegliere questo collegamento per visualizzare il testo dell'intestazione del messaggio. Per analizzare in modo approfondito l'intestazione, copiare il testo dell'intestazione del messaggio negli Appunti e quindi scegliere **analizzatore intestazione messaggio Microsoft** per accedere all'analizzatore connettività remota (fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si desidera lasciare Office 365 per completare questa attività. Incollare l'intestazione del messaggio nella pagina nella sezione Analizzatore intestazioni del messaggio e scegliere **Analyze Headers**.

- **Anteprima messaggio**: consente di visualizzare le versioni RAW o HTML del testo del corpo del messaggio. Nella visualizzazione HTML i collegamenti sono disattivati.

- **Scaricare** il file del messaggio o del **download**: scegliere questa opzione per scaricare una copia del messaggio o del file nel dispositivo locale. È necessario verificare che i rischi associati al download degli elementi dalla quarantena siano compresi prima che sia possibile farlo. I messaggi vengono salvati nel formato. eml in una cartella specificata. I file in quarantena vengono salvati nel formato originale.

- **Delete**: se lo si desidera, è possibile eliminare immediatamente un elemento in quarantena (o un insieme di elementi) anziché attendere la data di scadenza impostata da Office 365. Per eliminare un messaggio o un file, nell'elenco quarantena selezionare l'elemento e quindi scegliere **Elimina**. Per eliminare contemporaneamente più elementi, selezionare la casella di controllo a sinistra degli elementi nell'elenco quarantena e quindi nella pagina **azioni in blocco** visualizzata, scegliere **Elimina messaggi selezionati** o **Elimina file selezionati**.

- **Release**: rilascia un elemento in quarantena (o un insieme di elementi) e segnala gli elementi in quarantena (falsi positivi) a Microsoft.

  Per rilasciare e segnalare un singolo messaggio o file, nell'elenco quarantena selezionare l'elemento, scegliere **rilascia file** o **rilascia messaggio**. Nella pagina successiva, verificare che sia selezionata l'opzione **segnala i messaggi a Microsoft** per l'analisi o **i file di report a Microsoft per l'analisi** .

  Per rilasciare contemporaneamente più elementi, selezionare la casella di controllo a sinistra degli elementi nell'elenco quarantena e quindi nella pagina **azioni in blocco** visualizzata, scegliere **rilascia file** o **rilascia messaggi**. Nella pagina successiva, verificare che sia selezionata l'opzione **segnala i messaggi a Microsoft** per l'analisi o **i file di report a Microsoft per l'analisi** .

Quando si rilasciano i messaggi, tenere presente quanto segue:

- Quando si esegue una versione in blocco di più messaggi contemporaneamente, i messaggi vengono rilasciati a tutti i destinatari originariamente identificati. Se si desidera solo rilasciare i messaggi solo a destinatari specifici, è necessario rilasciarli uno alla volta e identificare i destinatari singolarmente.

- Un messaggio non può essere rilasciato più di una volta allo stesso destinatario.

- Quando si rilascia un messaggio a più destinatari, solo i destinatari che non sono stati precedentemente ricevuti il messaggio verranno visualizzati nell'elenco dei destinatari potenziali.

- Quando si sceglie di segnalare falsi positivi, se il messaggio o i messaggi rilasciati sono stati messi in quarantena come posta indesiderata, in blocco, in caso di phishing o come contenente malware, il messaggio verrà segnalato anche al team di analisi di posta indesiderata di Microsoft. Il team valuterà e analizzerà il messaggio e, a seconda dei risultati dell'analisi, le regole di filtro del contenuto della posta indesiderata a livello di servizio potrebbero essere modificate per consentire il messaggio.

## <a name="set-the-quarantine-retention-period"></a>Impostare il periodo di conservazione della quarantena

È possibile configurare il tempo di permanenza di messaggi e file in quarantena prima della scadenza. Per impostazione predefinita, gli elementi in quarantena vengono conservati per 30 giorni. Questa impostazione viene configurata per ogni criterio creato. È inoltre possibile modificare il valore per il criterio predefinito, come descritto in questo articolo.

### <a name="modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security--compliance-center"></a>Modificare il periodo di conservazione della quarantena per i criteri di filtro della posta indesiderata predefiniti nel centro sicurezza & conformità

1. [Aprire il Centro sicurezza & conformità](go-to-the-securitycompliance-center.md) e passare a protezione dalla **posta indesiderata**dei **criteri** \> di **gestione** \> delle minacce.

   > [!TIP]
   > Per passare direttamente alla pagina **protezione da posta indesiderata** , utilizzare questo URL:[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)

2. Scegliere **personalizzato** per visualizzare la scheda **impostazioni personalizzate** .

3. Espandere la riga **criteri di filtro posta indesiderata predefinita (sempre attiva)** .

4. Scegliere **modifica criterio**. Le impostazioni per il criterio di filtro di protezione da posta indesiderata predefinito vengono visualizzate in una nuova pagina.

5. Espandere la **posta indesiderata e le azioni in blocco**.

6. In **quarantena**, nella casella di testo **Mantieni posta indesiderata per (giorni)** , immettere il periodo di tempo in cui si desidera che Office 365 mantenga i messaggi e i file in quarantena. Il valore predefinito è 30 giorni. Questo è anche il massimo.

7. Fare clic su **Salva**.
