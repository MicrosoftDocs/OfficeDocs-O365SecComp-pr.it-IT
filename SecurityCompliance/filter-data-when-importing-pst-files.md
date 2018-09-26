---
title: Filtrare i dati per l'importazione di file PST a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: "Utilizzare la nuova funzionalità di importazione intelligente nel servizio di Office 365 importazione per filtrare gli elementi che in realtà, l'importazione alle cassette postali di destinazione. Importazione intelligente consente di decidere in modo proattivo i dati da importare e sugli aspetti da tralasciare. Importazione intelligente offre anche informativa sui dati che si sta importando a Office 365. "
ms.openlocfilehash: c90d9df62c7d8c411196b283acec37959fc95e57
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038199"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a>Filtrare i dati per l'importazione di file PST a Office 365

Utilizzare la nuova funzionalità di importazione intelligente nel servizio di Office 365 importazione per filtrare gli elementi in file PST in realtà, l'importazione alle cassette postali di destinazione. Ecco come funziona:
  
- Dopo aver creato e inviare un processo di importazione file PST, i file PST vengono caricati in un'area di archiviazione Azure nel cloud Microsoft.
    
- Office 365 consente di analizzare i dati in file PST, in modo sicuro e protetto identificando della scadenza di elementi delle cassette postali e i diversi tipi di messaggi inclusi nei file PST.
    
- Al termine dell'analisi ed sono possibile importare i dati, è possibile importare tutti i dati nei file PST o tagliare i dati importati impostando i filtri che consentono di controllare quali dati vengono importati. Ad esempio, è possibile scegliere di:
    
  - Importare solo gli elementi di una certa data.
    
  - Importare i tipi di messaggio selezionato.
    
  - Escludere i messaggi inviati o ricevuti da determinate persone.
    
- Dopo aver configurato le impostazioni del filtro, Office 365 consente di importare solo i dati che soddisfano i criteri di filtro alle cassette postali di destinazione specificate nel processo di importazione.
    
Nella figura seguente viene illustrato il processo di importazione intelligente e vengono evidenziate le attività eseguite e le attività eseguite da Office 365.
  
![Il processo di importazione intelligente in Office 365](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a>Informazioni preliminari

- I passaggi descritti in questo argomento si presuppongono che sia stato creato un processo di importazione file PST nel servizio di Office 365 importazione utilizzando il caricamento di rete o della spedizione di unità. Per istruzioni dettagliate, vedere uno degli argomenti seguenti:
    
  - [Utilizzare il caricamento di rete per importare i file PST su Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Utilizzare la spedizione dell'unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Dopo aver creato un processo di importazione utilizzando il caricamento di rete, lo stato del processo di importazione per l'importazione di pagina in Office 365 Security &amp; centro conformità è impostata su **analisi in corso**, il che significa che Office 365 è analisi dei dati in file PST che si caricato. Fare clic su **Aggiorna**![aggiornamento](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) per aggiornare lo stato del processo di importazione. 
    
- Per l'unità di distribuzione dei processi di importazione, i dati verranno analizzati da Office 365 dopo personale del centro dati Microsoft visualizzato nel disco rigido e caricare i file PST all'area di archiviazione Azure per la propria organizzazione.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtrare i dati importati per le cassette postali

Dopo aver creato un file PST processo di importazione, eseguire la procedura seguente per filtrare i dati prima di importare a Office 365.
  
1. Accedere a [https://protection.office.com/](https://protection.office.com/) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro di Office 365 Security &amp; centro conformità, fare clic su **governance dati** \> **importazione**.
    
    Nella pagina **importazione** sono elencati i processi di importazione per la propria organizzazione. Si noti che il valore **Analisi completata** nella colonna **stato** indica i processi di importazione che sono stati analizzati da Office 365 e si desidera importare. 
    
    ![Indica lo stato di completamento analisi che Office 365 dispone di analizzare i dati in file PST](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Fare clic su **Pronto essere importato a Office 365** per il processo di importazione che si desidera eseguire. 
    
    Volo pagina viene visualizzato con informazioni sui file PST e altre informazioni sul processo di importazione.
    
4. Fare clic su **Importa a Office 365**.
    
    Verrà visualizzata la pagina di **filtrare i dati** . Contiene informazioni dati sui dati in file PST per il processo di importazione, incluse le informazioni sulla validità dei dati. 
    
    ![Il filtro per la pagina di dati Mostra sui concetti di dati dei file PST per il processo di importazione](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. Se si desidera tagliare i dati importati per Office 365, in base **si desidera filtrare i dati?**, effettuare una delle operazioni seguenti:
    
    r. fare clic su **Sì, desidero filtrarla prima dell'importazione** per tagliare i dati da importare e quindi fare clic su **Avanti**.
    
    Verrà visualizzata la pagina **Importa dati alla pagina di Office 365** con sui concetti di dati dettagliati dall'analisi eseguita Office 365. 
    
    ![Office 365 consente di visualizzare informazioni dettagliate dati dall'analisi dei file PST](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    Il grafico in questa pagina Mostra la quantità di dati che verranno importati. Nel grafico vengono visualizzate informazioni su ogni tipo di messaggio disponibile in file PST. È possibile posizionare il cursore su ogni barra per visualizzare informazioni specifiche su tale tipo di messaggio. È inoltre disponibile un elenco a discesa con valori di durata diversi in base all'analisi dei file PST. Quando si seleziona un periodo nell'elenco a discesa, il grafico viene aggiornato per visualizzare la quantità di dati verranno importati per l'età selezionato. 
    
    b. per configurare i filtri di aggiunta per ridurre la quantità di dati importati, fare clic su **ulteriori opzioni di filtro**.
    
    ![Configurare i filtri nella pagina ulteriori opzioni per ridurre i dati importati](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    È possibile configurare questi filtri:
    
      - **Validità** - selezionare un'età in modo che solo gli elementi che sono più recente di validità specificata verrà importata. Vedere la sezione [informazioni](filter-data-when-importing-pst-files.md#moreinfo) per una descrizione su come Office 365 determina i bucket di validità per il filtro di **validità** . 
    
      - **Tipo** : in questa sezione vengono illustrati tutti i tipi di messaggio che sono stati rilevati nei file PST per il processo di importazione. È possibile deselezionare una casella accanto a un tipo di messaggio che si desidera escludere. Si noti che non è possibile escludere il tipo di messaggio. Vedere la sezione [informazioni](filter-data-when-importing-pst-files.md#moreinfo) per un elenco di elementi delle cassette postali inclusi nella categoria. 
    
      - **Gli utenti** , è possibile escludere messaggi inviati o ricevuti da determinate persone. Escludere gli utenti che vengono visualizzati nella From: campo a: campo o Cc: campo dei messaggi, fare clic su **Escludi utenti** accanto a tale tipo di destinatario. Digitare l'indirizzo di posta elettronica (indirizzo SMTP) della persona, fare clic su **Aggiungi**![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) per aggiungerli all'elenco di utenti esclusi per quel tipo di destinatario e quindi fare clic su **Salva** per salvare l'elenco di utenti esclusi. 
    
        > [!NOTE]
        > Office 365 non viene visualizzata sui concetti di dati restituiti dall'impostazione del filtro di **persone** . Tuttavia, se si imposta questo filtro per escludere i messaggi inviati o ricevuti da determinate persone, i messaggi vengono esclusi durante il processo di importazione effettivo. 
  
    c. fare clic su **Applica** in tempo reale **le opzioni di filtro più** pagina per salvare le impostazioni di filtro. 
    
    I dati sui concetti nella pagina **Importa dati a Office 365** vengono aggiornati in base alle impostazioni di filtro, tra cui la quantità totale di dati che verranno importati in base alle impostazioni del filtro. Si noti che anche è riportato un riepilogo delle impostazioni del filtro. È possibile fare clic su **Edit** accanto a un filtro per modificare l'impostazione se necessario. 
    
    ![Approfondimenti dati vengono aggiornati in base alle impostazioni di filtro](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. scegliere **Avanti**.
    
    Viene visualizzata una pagina di stato che mostra le impostazioni di filtro. Nuovamente, è possibile modificare le impostazioni di filtro.
    
    Fare clic su **Importa dati** per avviare l'importazione. Si noti che viene visualizzata la quantità totale di dati che verranno importati. 
    
    Oppure
    
    r. fare clic su **No, desidera importare tutti gli elementi** per importare tutti i dati in file PST di Office 365 e quindi fare clic su **Avanti**.
    
    b. nella pagina **Importa dati a Office 365** , fare clic su **Importa dati** per avviare l'importazione. Si noti che viene visualizzata la quantità totale di dati che verranno importati. 
    
6. Nella pagina **importazione** fare clic su **Aggiorna** ![aggiornamento](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). Nella colonna **stato** viene visualizzato lo stato del processo di importazione. 
    
7. Fare clic su Importa il processo per visualizzare informazioni più dettagliate, ad esempio lo stato di ogni file PST e le impostazioni del filtro che è stato configurato.

  
## <a name="more-information"></a>Ulteriori informazioni

- In che modo Office 365 determinare gli incrementi di filtro per la validità? Quando Office 365 consente di analizzare un file PST, esamina il timestamp inviato o ricevuto di ogni elemento (se un elemento contiene un timestamp inviato e ricevuto, la data meno recente è selezionata). Office 365 quindi cerca il valore dell'anno per tale data/ora e viene confrontata con la data corrente per determinare la validità dell'elemento. Questi età vengono quindi utilizzate come valori nell'elenco a discesa per il filtro di **validità** . Ad esempio, se un file PST con i messaggi provenienti da 2016, 2015 e 2014, quindi i valori di filtro **intervallo** sarà **anno 1**, **2 anni**e **3 anni**.
    
- Nella tabella seguente sono elencati i tipi di messaggi inclusi nella **categoria il filtro di **tipo** in tempo reale **altre opzioni** pagina** (vedere 5b passaggio nella procedura precedente). Attualmente, non è possibile escludere gli elementi nella categoria "" quando si importano i file pst a Office 365. 
    
    |**ID classe messaggio**|**Elementi delle cassette postali che utilizzano questa classe messaggio**|
    |:-----|:-----|
    |IPM. Attività  <br/> |Voci del diario  <br/> |
    |IPM. Documento  <br/> |Documenti e i file (non è associati a un messaggio di posta elettronica)  <br/> |
    |IPM. File  <br/> |(stesso IPM. Documento)  <br/> |
    |IPM. Note.IMC.Notification  <br/> |Report tramite Internet Mail Connect è il gateway Internet del Server di Exchange  <br/> |
    |IPM. Note.Microsoft.Fax  <br/> |Messaggi fax  <br/> |
    |IPM. Note.Rules.Oof.Template.Microsoft  <br/> |Messaggi di risposta automatica fuori sede  <br/> |
    |IPM. Note.Rules.ReplyTemplate.Microsoft  <br/> |Risposte inviate da una regola di posta in arrivo  <br/> |
    |IPM. OLE. Classe  <br/> |Eccezioni per una serie ricorrente  <br/> |
    |IPM. Recall.Report  <br/> |Rapporti richiamo messaggio  <br/> |
    |IPM. Remoto  <br/> |Messaggi di posta remota  <br/> |
    |IPM. Report  <br/> |Relazioni sullo stato elemento  <br/> |
