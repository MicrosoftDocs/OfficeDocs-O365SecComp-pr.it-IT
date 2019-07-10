---
title: Trovare e rilasciare i messaggi in quarantena come utente in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: "Come utente di Office 365, è possibile gestire i messaggi in quarantena per la posta indesiderata in uno dei due modi seguenti: rispondendo alle notifiche di posta indesiderata inviate direttamente (se l'amministratore ha configurato questa funzionalità) oppure utilizzando la funzionalità di &amp; quarantena della posta indesiderata nella conformità alla sicurezza Centro."
ms.openlocfilehash: 47c17e59f6f54d973eeaf761ecee6a1ac5a3dbba
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599352"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Trovare e rilasciare i messaggi in quarantena come utente in Office 365

Come utente di Office 365, è possibile gestire i messaggi che sono stati inviati alla quarantena invece di essere inviati in uno dei due modi seguenti: [rispondendo alle notifiche di posta indesiderata inviate direttamente](use-spam-notifications-to-release-and-report-quarantined-messages.md) (se l'amministratore ha impostato questo) oppure utilizzando il &amp; Centro sicurezza e conformità. 
  
> [!NOTE]
> Se si è un amministratore, è possibile [gestire i messaggi](manage-quarantined-messages-and-files.md) in quarantena per gli altri utenti dell'organizzazione. 
  
## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a>Visualizzare i messaggi che sono stati inviati alla quarantena invece che a te

1. Accedere a Office 365 e [passare al centro sicurezza e conformità](go-to-the-securitycompliance-center.md) utilizzando l'account aziendale o dell'Istituto di istruzione. 
    
2. A sinistra espandere **gestione minacce**, scegliere **Revisione**e quindi **quarantena**.
    
    > [!TIP]
    > Per passare direttamente alla pagina **** di quarantena nel centro sicurezza &amp; e conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
Per impostazione predefinita, il &amp; Centro sicurezza e conformità Visualizza tutti i messaggi di posta elettronica messi in quarantena come posta indesiderata. I messaggi vengono ordinati dal più recente al più vecchio in base alla **Data** in cui il messaggio è stato ricevuto. Per ogni messaggio vengono visualizzati anche il **mittente**, l' **oggetto**e la data di scadenza (in **scadenza** ). È possibile ordinare su un campo facendo clic sull'intestazione di colonna corrispondente. fare clic su un'intestazione di colonna una seconda volta per invertire la sequenza di ordinamento. 
  
È possibile visualizzare un elenco di tutti i messaggi in quarantena oppure è possibile cercare messaggi specifici filtrando. È possibile eseguire operazioni in blocco solo su un massimo di 100 elementi, pertanto il filtro può anche contribuire a ridurre il set di risultati se si dispone di un numero superiore. È possibile filtrare rapidamente i messaggi per una singola causa di quarantena scegliendo un'opzione nell'elenco a discesa. Le opzioni includono:
  
- Posta elettronica identificata come posta indesiderata. Questi messaggi in quarantena vengono visualizzati per impostazione predefinita.
    
- Posta identificata come posta in blocco.
    
Dopo aver individuato uno specifico messaggio in quarantena, fare clic sul messaggio per visualizzarne i dettagli e intraprendere le azioni. È possibile rilasciare il messaggio alla cassetta postale, visualizzare in anteprima il messaggio, scaricare il messaggio oppure eliminare immediatamente il messaggio dalla quarantena.
  
> [!NOTE]
> Per utilizzare i messaggi in quarantena inviati ad altri utenti, è necessario disporre delle autorizzazioni di amministratore in Office 365. 
  
## <a name="to-filter-and-find-quarantined-messages"></a>Per filtrare e trovare i messaggi in quarantena

Se si dispone di molti elementi in quarantena, è possibile ridurre il numero a un set gestibile filtrando i numeri.
  
1. Nella pagina **quarantena** scegliere se si desidera visualizzare messaggi di **posta** indesiderata o in quarantena. **** 
    
2. In **Sort results by**scegliere qualsiasi combinazione di condizioni impostando il filtro o i filtri corretti (non è possibile utilizzare i caratteri jolly in questo momento). Sono disponibili diverse condizioni che è possibile scegliere, incluse le seguenti:
    
  - **ID messaggio** Utilizzare questa pagina per selezionare un messaggio specifico quando si conosce l'ID del messaggio. 
    
    Ad esempio, se un messaggio specifico viene inviato o destinato a un utente dell'organizzazione, ma non ha mai raggiunto la destinazione, è possibile cercare il messaggio utilizzando una traccia dei messaggi (vedere [eseguire una traccia dei messaggi e visualizzare i risultati](https://go.microsoft.com/fwlink/?LinkId=799737)). Se si rileva che il messaggio è stato inviato alla quarantena, probabilmente perché corrisponde a una regola del flusso di posta o è stato identificato come posta indesiderata, è possibile trovare facilmente questo messaggio in quarantena specificando l'ID del messaggio. Includere la stringa completa dell'ID del messaggio. Questo potrebbe includere parentesi angolari\<\>(), ad esempio:
    
    \<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\>
    
  - **Indirizzo di posta elettronica del mittente** Scegliere di filtrare in base a un singolo indirizzo di posta elettronica del mittente. 
    
  - **Indirizzo di posta elettronica del destinatario** Scegliere di filtrare in base a un singolo indirizzo di posta elettronica del destinatario. 
    
  - **Oggetto** Immettere l'oggetto di un indirizzo di posta elettronica che si desidera trovare. 
    
  - **Intervallo di date** È possibile scegliere di filtrare in base alla data in cui il messaggio è stato inviato alla quarantena. È possibile specificare la data o un intervallo di date, inclusa l'ora. 
    
  - **Data di scadenza** Per filtrare in base alla data di scadenza, scegliere **filtro avanzato**. È possibile selezionare i messaggi che verranno eliminati dalla quarantena entro le 24 ore successive ( **oggi**), entro le 48 ore successive (prossimi **2 giorni**), entro la settimana successiva ( **prossimi 7 giorni**) oppure è possibile selezionare un intervallo di tempo personalizzato.
    
    > [!IMPORTANT]
    > Per impostazione predefinita, i messaggi di posta indesiderata e di massa vengono mantenuti in quarantena per 30 giorni. Tuttavia, questo periodo di tempo è configurabile e l'amministratore potrebbe aver impostato un periodo di conservazione della quarantena diverso. Quando Office 365 Elimina un messaggio dalla quarantena, non è possibile riottenerlo. 
  
## <a name="view-details-for-a-specific-message"></a>Visualizzare i dettagli relativi a un messaggio specifico

Dopo aver selezionato un messaggio, verrà visualizzato un riepilogo delle proprietà del messaggio in un riquadro a destra della pagina.
  
- **ID messaggio:** Identificatore univoco del messaggio. 
    
- **Indirizzo mittente:** Chi ha inviato il messaggio. 
    
- **Ricevuti:** La data in cui il messaggio è stato ricevuto. 
    
- **Oggetto:** Il testo della riga dell'oggetto del messaggio. 
    
- **Motivo della quarantena:** Indica se un messaggio è stato identificato come **posta** indesiderata o in **blocco**.
    
- **Scade:** La data in cui il messaggio verrà eliminato dalla quarantena. 
    
- **Rilasciato su:** Tutti gli indirizzi di posta elettronica (se presenti) a cui è stato rilasciato il messaggio. 
    
- **Non ancora rilasciato:** Tutti gli indirizzi di posta elettronica (se presenti) a cui il messaggio non è stato rilasciato. È possibile scegliere **rilascia** se si desidera rilasciare il messaggio alla cassetta postale (altre informazioni sul rilascio dei messaggi nella sezione successiva). 
    
È possibile ottenere ulteriori informazioni sul messaggio scegliendo una delle seguenti opzioni:
  
- **Visualizzare l'intestazione del messaggio** Scegliere questo per visualizzare il testo dell'intestazione del messaggio. Per analizzare in modo approfondito l'intestazione, copiare il testo dell'intestazione del messaggio negli Appunti e quindi scegliere **analizzatore intestazione messaggio Microsoft** per accedere all'analizzatore connettività remota (fare clic con il pulsante destro del mouse e scegliere Apri in una nuova scheda se non si desidera lasciare Office 365 a completare questa attività. Incollare l'intestazione del messaggio nella pagina nella sezione Analizzatore intestazioni del messaggio e scegliere Analyze Headers. 
    
- **Messaggio di anteprima** Consente di visualizzare le versioni RAW o HTML del testo del corpo del messaggio. Nella visualizzazione HTML i collegamenti sono disattivati. 
    
## <a name="manage-your-quarantined-messages"></a>Gestire i messaggi in quarantena

Dopo aver selezionato un messaggio o un gruppo di messaggi, sono disponibili diverse opzioni per la gestione dei messaggi in quarantena.
  
- Nessuna operazione. Se si sceglie di non eseguire alcuna operazione, il messaggio verrà eliminato automaticamente da Office 365 alla scadenza. Tenere presente che quando Office 365 Elimina un messaggio dalla quarantena, non è possibile riottenerlo.
    
- **Rilascia il messaggio** Rilasciare un messaggio in quarantena (o un insieme di messaggi) in modo che il messaggio venga inviato alla cassetta postale. Quando si rilascia un messaggio, si ha la possibilità di segnalare il messaggio a Microsoft per l'analisi. 
    
    Quando si sceglie di segnalare un messaggio, chiamato anche segnalazione di un messaggio come falso positivo, il messaggio viene segnalato al team di analisi di posta indesiderata di Microsoft. Il team valuta e analizza i messaggi falsi positivi e, a seconda dei risultati dell'analisi, è possibile modificare le regole di filtro del contenuto della posta indesiderata a livello di servizio per consentire l'attraversamento di tali messaggi.
    
- **Scaricare il messaggio** Consente di scaricare il messaggio come file con estensione eml. Dopo aver scaricato un messaggio, è possibile esaminare il file con estensione EML utilizzando il client di posta elettronica prima di rilasciare il messaggio. 
    
- **Rimuovi dalla quarantena** Elimina il messaggio immediatamente dalla quarantena senza rilasciare il messaggio alla cassetta postale. 
    

