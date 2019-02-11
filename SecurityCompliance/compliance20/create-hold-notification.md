---
title: Creare una notifica di conservazione a fini giudiziari
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8db5a21f60a1d73c11e28bc2765a95c23646115d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706077"
---
# <a name="create-a-legal-hold-notice"></a>Creare una notifica di conservazione a fini giudiziari

Utilizzo di communications depositaria eDiscovery avanzate (anteprima), le organizzazioni possono gestire il flusso di lavoro utilizzando la comunicazione con depositari. Tramite lo strumento Communications team legale può inviare, raccogliere e tenere traccia delle notifiche di conservazione a fini giudiziari sistematicamente. Il processo di creazione flessibili consente inoltre ai team di personalizzare il flusso di lavoro di notifica di attesa e il contenuto negli avvisi inviati a depositari. 

L'articolo vengono illustrati i passaggi del flusso di lavoro di notifica di attesa.

## <a name="step-1-specify-communication-details"></a>Passaggio 1: Specificare i dettagli di comunicazione

Il primo passaggio consiste nello specificare i dettagli appropriati per le notifiche di conservazione a fini giudiziari o altre comunicazioni depositaria. 

1. In sicurezza & centro conformità, passare a **eDiscovery gt _ avanzate eDiscovery (Preview)** per visualizzare l'elenco dei casi nell'organizzazione.
   
2. Fare clic sulla scheda **comunicazioni** e quindi fare clic su **nuova comunicazione**.
   
3. Nella pagina **comunicazione nome** specificare i seguenti dettagli di comunicazione (obbligatorio).

    - **Nome**: si tratta del nome per la comunicazione.
    
    - **Responsabile della emissione**: nell'elenco a discesa Visualizza un elenco di un caso membri. Ogni notifica al depositari verrà inviato per conto di responsabile della emittente specificato.

4. Fare clic su **Avanti**.

## <a name="step-2-define-the-portal-content"></a>Passaggio 2: Definire il contenuto del portale

Successivamente, è possibile creare e aggiungere il contenuto della notifica di attesa. Nella pagina **definire il contenuto del portale** della procedura guidata **Crea comunicazione** , specificare il contenuto della notifica di attesa. Il contenuto verrà automaticamente accodato agli avvisi di pubblicazione, nuova pubblicazione, promemoria e riassegnazione. Inoltre, questo contenuto verrà visualizzati nel portale di conformità del depositaria. 

Per creare il contenuto del portale:

1. Tipo (o Taglia e paster da un altro documento) nella casella di testo per il contenuto del portale osservare l'attesa. 

2. Inserire il segnalatore di personalizzare l'avviso e condividere il portale di conformità depositaria variabili di unione.

3. Fare clic su **Avanti**.

  >[!Tip]
  >Per ulteriori che informazioni su come personalizzare il contenuto e il formato del contenuto del portale, vedere [utilizzare l'Editor Communications](using-communications-editor.md).

## <a name="step-3-set-the-required-notifications"></a>Passaggio 3: Impostare le notifiche necessari

Dopo aver definito il contenuto della notifica di attesa, è possibile impostare i flussi di lavoro intorno l'invio e la gestione del processo di notifica. Le notifiche sono messaggi di posta elettronica inviati a notifica e il completamento con depositari. Ogni depositaria aggiunto alla comunicazione riceverà la notifica stessa. 

Per impostare e inviare una notifica di attesa, è necessario includere emissione, r-pubblicazione e rilasciare le notifiche.

### <a name="issuance-notification"></a>Notifica di pubblicazione 

Dopo aver creata la comunicazione, viene avviata la **Notifica di pubblicazione** per il responsabile della emissione specificato. La notifica di pubblicazione è la prima comunicazione inviata al depositaria per informarli sulle loro obblighi di conservazione. 

Per creare una notifica di pubblicazione:

1. Nella porzione di **pubblicazione** , fare clic su **Modifica**.
   
2. Se necessario, aggiungere ulteriori membri maiuscole o personale per i campi **Cc** e **Ccn** . Per aggiungere più utenti a questi campi, separare gli indirizzi di posta elettronica con un punto e virgola.
   
3. Consente di specificare l' **oggetto** per la notifica (obbligatoria).
   
4. Consente di specificare il contenuto o ulteriori istruzioni che si desidera fornire agli depositaria (obbligatorio). Si noti che il contenuto del portale che è definito nel passaggio 2 viene aggiunto alla fine della notifica di pubblicazione. 
   
5. Fare clic su **Salva**. 

### <a name="re-issuance-notification"></a>Notifiche sulla pubblicazione r 

Nel corso della stessa maiuscole depositari potrebbero essere necessarie per conservare i dati aggiuntivi o meno di è stato indicato in precedenza. Dopo aver aggiornato il contenuto della notifica di attesa, la notifica di re-pubblicazione degli avvisi depositari sulle modifiche apportate al loro obblighi di conservazione.

Per creare una notifica di pubblicazione r: 

1. Nella porzione **ha aggiornato** , fare clic su **Modifica**.
   
2. Se necessario, aggiungere ulteriori membri maiuscole o personale per i campi **Cc** e **Ccn** . Per aggiungere più utenti a questi campi, separare gli indirizzi di posta elettronica con un punto e virgola.
   
3. Consente di specificare l' **oggetto** per la notifica (obbligatoria).
   
4. Consente di specificare il contenuto o ulteriori istruzioni che si desidera fornire agli depositaria (obbligatorio). Si noti che il contenuto del portale che è definito nel passaggio 2 viene aggiunto alla fine della notifica di pubblicazione r.
   
5. Fare clic su **Salva**.

>[!Note]
>Se viene modificata una notifica di attesa, la notifica di re-pubblicazione verrà inviata a tutti i depositari assegnati per l'avviso. Dopo l'invio di notifica, depositari verranno richiesto di confermare nuovamente il segnalatore di attesa. Se sono state impostate qualsiasi promemoria o escalation flussi di lavoro, si verrà nuovamente avviata. 

### <a name="release-notification"></a>Notifiche sulla versione

Dopo aver risolto scelta o se un depositaria non è più soggette a conservare il contenuto, è possibile rilasciare depositaria dal caso. Se il depositaria in precedenza viene eseguita una notifica di attesa, la notifica della versione è utilizzabile per notificare depositari che sono stati rilasciati dal proprio obbligo.

Per creare una notifica di rilascio: 

1. Nella porzione **versione** , fare clic su **Modifica**.
   
2. Se necessario, aggiungere ulteriori membri maiuscole o personale per i campi **Cc** e **Ccn** . Per aggiungere più utenti a questi campi, separare gli indirizzi di posta elettronica con un punto e virgola.
   
3. Consente di specificare l' **oggetto** per la notifica (obbligatoria).
   
4. Consente di specificare il contenuto o ulteriori istruzioni che si desidera fornire agli depositaria (obbligatorio).
   
5. Fare clic su **Salva** e andare al passaggio successivo. 

## <a name="optional-step-4-set-the-optional-notifications"></a>(Facoltativo) Passaggio 4: Impostare le notifiche facoltative

Facoltativamente, è possibile semplificare il flusso di lavoro per i seguenti con depositari che non rispondono escalation e la creazione e della pianificazione promemoria automatizzata delle notifiche.

### <a name="reminders"></a>Promemoria

Dopo aver inviato una notifica di attesa, è possibile follow-up con depositari che non rispondono definendo un flusso di lavoro di promemoria. 

Per pianificare i promemoria:

1. Nella porzione **promemoria** , fare clic su **Modifica**.
   
2. Attivare il flusso di lavoro **promemoria** attivando attiva o disattiva **lo stato** (obbligatorio).
   
3. Specificare l' **intervallo di promemoria (in giorni)** (obbligatorio). Questo è il numero di giorni di attesa prima di inviare le notifiche di follow-up e il promemoria. Ad esempio, se si imposta l'intervallo di promemoria a 7 giorni, quindi il primo promemoria verrà inviato 7 giorni dopo la notifica di attesa viene eseguita inizialmente. Tutti i promemoria successivi potrebbero anche essere inviati ogni 7 giorni.
   
4. Specificare il **numero di promemoria** (obbligatorio). Questo campo specifica quante promemoria per inviare a depositari non risponde. Ad esempio, se si imposta il numero di promemoria su 3, un depositaria riceverebbero un massimo di 3 promemoria. Dopo che un depositaria riconosce la notifica di attesa, non è più promemoria verranno inviati a tale utente.
   
5. Consente di specificare l' **oggetto** per la notifica (obbligatoria). 
   
6. Consente di specificare il contenuto o ulteriori istruzioni che si desidera fornire agli depositaria (obbligatorio). Si noti che il contenuto del portale che è definito nel passaggio 2 viene aggiunto alla fine della notifica di promemoria.
   
7. Fare clic su **Salva** e passare il passaggio successivo.

### <a name="escalations"></a>Misure correttive 

In alcune situazioni, potrebbe essere necessario altri modi per il completamento con depositari che non rispondono. Se un depositaria non riconosce una notifica di attesa dopo aver ricevuto il numero specificato di promemoria, il team legale può specificare un flusso di lavoro per inviare automaticamente un avviso di escalation per conto del manager e il depositaria.

Per pianificare le misure correttive:

1. Nella porzione **Escalation** , fare clic su **Modifica**.
   
2. Attivare il flusso di lavoro **Escalation** attivando attiva o disattiva **lo stato** .
   
3. Specificare l' **intervallo di Escalation (in giorni)** (obbligatorio). 
   
4. Specificare il **numero di escalation** (obbligatorio). Questo campo specifica quante escalation per inviare a depositari non risponde. Ad esempio, se si imposta il numero di escalation su 3, quindi un escalation avviso verrà inviato per conto del manager e il depositaria un massimo di 3 volte. Dopo che un depositaria riconosce la notifica di attesa, non è più escalation verranno inviate. 
   
5. Consente di specificare l' **oggetto** per la notifica (obbligatoria). 
   
6. Consente di specificare il contenuto o ulteriori istruzioni che si desidera fornire agli depositaria (obbligatorio). Si noti che il contenuto del portale che è definito nel passaggio 2 viene aggiunto alla fine della notifica di escalation.
   
7. Fare clic su **Salva** e passare il passaggio successivo.
   
## <a name="step-5-assign-custodians"></a>Passaggio 5: Assegnare depositari 

Dopo avere scelto il contenuto per le notifiche, selezionare depositari a cui inviare le notifiche. 

Per aggiungere depositari:

1. Assegnare depositari per la comunicazione facendo clic sulla casella accanto al nome.

    Dopo aver creata la comunicazione, il flusso di lavoro di notifica verrà automaticamente applicate a depositari selezionati.
   
2. Fare clic su **Avanti** per esaminare le impostazioni di comunicazione e i dettagli.
 
>[!NOTE]
>È possibile aggiungere solo depositari che sono stati aggiunti al caso e sono stati inviati un'altra notifica all'interno del case.

## <a name="step-6-review-settings"></a>Passaggio 6: Impostazioni di revisione

Dopo aver rivedere le impostazioni e fare clic su **Invia** per completare la comunicazione, il sistema verrà automaticamente avviato il flusso di lavoro di comunicazione mediante l'invio di notifica di pubblicazione.