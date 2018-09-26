---
title: Trovare e rilasciare i messaggi in quarantena come utente in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/19/2018
ms.audience: Consumer/IW
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
description: "Come un utente di Office 365, è possibile gestire i propri messaggi in quarantena in uno dei due modi: rispondendo per le notifiche inviate direttamente all'utente di posta indesiderata (se l'amministratore ha configurato questa funzionalità), oppure utilizzando la funzionalità di quarantena della posta indesiderata in sicurezza &amp; conformità Al centro."
ms.openlocfilehash: 728273838d9e592e17638638258f481830bc0bbe
ms.sourcegitcommit: f7fff49ae0b1c3056faa58d73c1070cb4e638fbf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018890"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Trovare e rilasciare i messaggi in quarantena come utente in Office 365

Come un utente di Office 365, è possibile gestire i messaggi che sono stati messi in quarantena invece di inviate in uno dei due modi: per [rispondere per le notifiche di posta indesiderata inviate direttamente](use-spam-notifications-to-release-and-report-quarantined-messages.md) (se l'amministratore ha configurato questa) o utilizzando la protezione &amp; centro conformità. 
  
> [!NOTE]
> Se si è un amministratore, è possibile [gestire i messaggi in quarantena](manage-quarantined-messages-and-files.md) per altri utenti nell'organizzazione. 
  
## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a>Visualizzare i messaggi che sono stati messi in quarantena invece che all'utente

1. Accedere a Office 365 e [accedere a Centro connessioni di sicurezza e conformità](go-to-the-securitycompliance-center.md) utilizzando l'account di lavoro o della scuola. 
    
2. A sinistra, espandere **Threat Management**, scegliere **Rivedi**e quindi scegliere **quarantena**.
    
    > [!TIP]
    > Per passare direttamente alla pagina di **quarantena** per la protezione &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
Per impostazione predefinita, la sicurezza &amp; centro conformità consente di visualizzare tutti i messaggi di posta elettronica in quarantena come posta indesiderata. I messaggi vengono ordinati in ordine cronologico in base alla **Data** stato ricevuto il messaggio. **Mittente**, **oggetto**e la data di scadenza (in **scadenza** ) vengono inoltre visualizzate per ogni messaggio. È possibile ordinare in un campo facendo clic su intestazione di colonna corrispondente; Fare clic su un'intestazione di colonna per annullare l'ordinamento. 
  
È possibile visualizzare un elenco di tutti i messaggi in quarantena oppure è possibile cercare messaggi specifici da un filtro. È possibile solo eseguire operazioni su un massimo di 100 elementi, in blocco in modo che il filtro consente inoltre di ridurre il set di risultati se un numero superiore di. È possibile filtrare i messaggi per un motivo di quarantena singolo rapidamente facendo clic su un'opzione dall'elenco a discesa. Opzioni includono:
  
- Posta identificata come posta indesiderata. Per impostazione predefinita, vengono visualizzati questi messaggi in quarantena.
    
- Posta identificata come posta inviata in blocco.
    
Dopo aver individuato uno specifico messaggio in quarantena, fare clic sul messaggio per visualizzarne i dettagli ed eseguire azioni. È per rilasciare il messaggio alla cassetta postale, visualizzare in anteprima il messaggio, scaricare il messaggio o eliminare i messaggi dalla quarantena immediatamente.
  
> [!NOTE]
> È necessario disporre delle autorizzazioni di amministratore in Office 365 per l'utilizzo con i messaggi in quarantena inviate ad altri utenti. 
  
## <a name="to-filter-and-find-quarantined-messages"></a>Per filtrare e individuare i messaggi in quarantena

Se si dispone di una quantità elevata di elementi in quarantena, è possibile ridurre il numero a un insieme gestibile la funzionalità di filtro.
  
1. Nella pagina **quarantena** scegliere se si desidera visualizzare **la posta indesiderata** o **massa** di messaggi in quarantena. 
    
2. Nella sezione **Ordina per**, scegliere una qualsiasi combinazione delle condizioni impostando il filtro appropriata o i filtri (non è possibile utilizzare i caratteri jolly in questa fase). Sono disponibili più condizioni, che è possibile scegliere, incluse le seguenti:
    
  - **ID messaggio** Utilizzare questa opzione per selezionare un messaggio specifico quando si conosce l'ID del messaggio. 
    
    Ad esempio, se inviato da un messaggio specifico o progettato per un utente all'interno dell'organizzazione, ma non raggiunto la destinazione, è possibile cercare il messaggio utilizzando una traccia dei messaggi (vedere [eseguire una traccia dei messaggi e visualizzare i risultati](https://go.microsoft.com/fwlink/?LinkId=799737)). Se si rileva che è stato inviato il messaggio in quarantena, ad esempio perché corrispondenti a una regola del flusso di posta elettronica o è stato identificato come posta indesiderata, è possibile trovare con facilità questo messaggio in quarantena, specificando il relativo ID. È necessario includere l'intera stringa di ID del messaggio. Ciò potrebbe includere parentesi angolari (\<\>), ad esempio:
    
    \<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\>
    
  - **Indirizzo di posta elettronica del mittente** Scegliere filtrare in base a un indirizzo di posta elettronica singolo mittente. 
    
  - **Indirizzo di posta elettronica destinatario** Scegliere filtrare in base a un indirizzo di posta elettronica del destinatario singolo. 
    
  - **Oggetto** Immettere l'oggetto di un indirizzo di posta elettronica che si desidera trovare. 
    
  - **Intervallo di date** È possibile scegliere di filtrare in base alla data che il messaggio è stato messo in quarantena. È possibile specificare la data o un intervallo di date, incluso il tempo. 
    
  - **Data di scadenza** Per filtrare dalla data di scadenza, scegliere **filtro avanzato**. È possibile selezionare i messaggi che verranno eliminati dalla quarantena entro le prossime 24 ore ( **ora**), entro le prossime 48 ore ( **successivo 2 giorni**), della settimana successiva ( **successivo 7 giorni**) oppure è possibile selezionare un intervallo di tempo personalizzato.
    
    > [!IMPORTANT]
    > Per impostazione predefinita, i messaggi di posta indesiderata e blocco vengono mantenuti in quarantena per 30 giorni. Tuttavia, questo periodo di tempo può essere configurato e l'amministratore potrebbe avere impostato un periodo di conservazione diversi quarantena. Quando Office 365 consente di eliminare un messaggio in quarantena, è Impossibile annullare l'operazione. 
  
## <a name="view-details-for-a-specific-message"></a>Visualizzare i dettagli di un messaggio specifico

Dopo aver selezionato un messaggio, si verrà visualizzato un riepilogo delle proprietà di messaggi in un riquadro sul lato destro della pagina.
  
- **ID messaggio:** Identificatore univoco per il messaggio. 
    
- **Indirizzo mittente:** Che ha inviato il messaggio. 
    
- **Ricevuto:** La data di che ricezione del messaggio. 
    
- **Soggetto:** Il testo della riga dell'oggetto del messaggio. 
    
- **Quarantena motivo:** Indica se un messaggio è stato identificato come **posta indesiderata** o **blocco**.
    
- **Scade:** Data quando il messaggio verrà eliminato dalla quarantena. 
    
- **Rilasciato a:** Tutti gli indirizzi di posta elettronica (se esistenti) a cui il messaggio è stato rilasciato. 
    
- **Non ancora rilasciato a:** Tutti gli indirizzi di posta elettronica (se esistenti) a cui non è stato rilasciato il messaggio. È possibile **rilasciare** se si desidera rilasciare il messaggio alla cassetta postale (ulteriori informazioni sui rilasciare i messaggi nella sezione successiva). 
    
È possibile ottenere ulteriori dettagli relativi al messaggio scegliendo una delle opzioni seguenti:
  
- **Intestazione del messaggio di visualizzazione** Selezionare questa opzione per visualizzare il testo dell'intestazione di messaggio. Per analizzare l'intestazione in modo approfondito, copiare il testo dell'intestazione di messaggio negli Appunti e quindi scegliere **Dell'analizzatore dell'intestazione di messaggio Microsoft** per accedere alla analizzatore connettività remota (pulsante destro del mouse e scegliere Apri in una nuova scheda se non si desidera lasciare Office 365 completare questa attività). Incolla l'intestazione del messaggio alla pagina nella sezione analizzatore dell'intestazione di messaggio e scegliere analizza le intestazioni. 
    
- **Anteprima messaggio** Consente di vedere non elaborati o versioni HTML del testo del corpo del messaggio. Nella visualizzazione HTML collegamenti disattivati. 
    
## <a name="manage-your-quarantined-messages"></a>Gestire i messaggi in quarantena

Dopo aver selezionato un messaggio o un gruppo di messaggi, sono disponibili diverse opzioni per la gestione dei messaggi in quarantena.
  
- Non effettuare alcuna operazione. Se si sceglie di non eseguire alcuna operazione, il messaggio verrà eliminato da Office 365 automaticamente alla scadenza. Si tenga presente che quando Office 365 consente di eliminare un messaggio dalla quarantena, è Impossibile ottenere lo.
    
- **Rilascia messaggio** Rilasciare un messaggio in quarantena (o un insieme di messaggi) in modo che il messaggio viene inviato alla cassetta postale. Quando si rilascia un messaggio, è possibile segnalare il messaggio a Microsoft per l'analisi. 
    
    Quando si sceglie di inoltrare un messaggio, l'acronimo di report di un messaggio come falso positivo, il messaggio viene indicato al Team di analisi della posta indesiderata di Microsoft. Il team di valuta e l'analisi di messaggi falsi positivi e, in base ai risultati dell'analisi, le regole di filtro dei contenuti da posta indesiderata a livello di servizio possono essere regolate per consentire i messaggi tramite.
    
- **Download dei messaggi** Consente di scaricare il messaggio come file EML. Dopo avere scaricato un messaggio, è possibile esaminare il file EML utilizzando il client di posta elettronica prima di distribuire il messaggio. 
    
- **Rimuovere dalla quarantena** Elimina il messaggio immediatamente dalla quarantena senza rilasciare il messaggio alla cassetta postale. 
    

