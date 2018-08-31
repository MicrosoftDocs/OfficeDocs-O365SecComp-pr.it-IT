---
title: Creare e applicare criteri di gestione delle informazioni
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
description: Criteri di gestione delle informazioni attivare le etichette ai documenti o all'organizzazione di controllo di tempo che deve conservare contenuto, per controllare quali utenti eseguire con il contenuto e per aggiungere i codici a barre. Un criterio consente di applicare la conformità alle normative legali e governative o processi aziendali interni. In qualità di amministratore, è possibile impostare un criterio per controllare la modalità di tenere traccia di documenti e la durata di conservazione di documenti.
ms.openlocfilehash: cc15b7d830e6c13e00045f7e4b672ac4a755a70e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530486"
---
# <a name="create-and-apply-information-management-policies"></a>Creare e applicare criteri di gestione delle informazioni

Criteri di gestione delle informazioni attivare le etichette ai documenti o all'organizzazione di controllo di tempo che deve conservare contenuto, per controllare quali utenti eseguire con il contenuto e per aggiungere i codici a barre. Un criterio consente di applicare la conformità alle normative legali e governative o processi aziendali interni. In qualità di amministratore, è possibile impostare un criterio per controllare la modalità di tenere traccia di documenti e la durata di conservazione di documenti.
  
È possibile creare può Criteri gestione informazioni dislocati tre nella gerarchia del sito dal più ampio per ristretto:
  
- Creare un criterio da utilizzare in più tipi di contenuto all'interno di una raccolta siti.
    
- Creare un criterio per un tipo di contenuto del sito.
    
- Creare un criterio per un elenco o raccolta.
    
Per ulteriori informazioni, vedere [Introduzione ai criteri di gestione delle informazioni](intro-to-info-mgmt-policies.md).
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Creare un criterio per più tipi di contenuto all'interno di una raccolta siti
<a name="__toc261001590"> </a>

Per garantire che un criterio di informazioni viene applicato a tutti i documenti di un tipo di una raccolta siti, è consigliabile creare i criteri a livello di raccolta siti e successivamente applicare i criteri per i tipi di contenuto. Si tratta delle come criteri di raccolta siti. 
  
1. Nella home page del sito insieme \> **Impostazioni**![pulsante SharePoint 2016 impostazioni sulla barra del titolo. ](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Impostazioni sito**.
    
    In un sito connesso al gruppo di SharePoint, fare clic su **Impostazioni**, fare clic su **Contenuto del sito**e quindi fare clic su **Impostazioni sito**. 
    
2. Nella pagina Impostazioni sito, in **Amministrazione raccolta siti** \> **Modelli di criteri di tipi di contenuto**. 
  
![Collegamento Modelli di criteri tipo di contenuto nella pagina Impostazioni sito](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Nella pagina criteri \> **Create**. 
    
4. Immettere un nome e una descrizione per il criterio e quindi scrivere una breve informativa che spiega agli utenti che cos'è per il criterio.
    
5. Vedere la sezione successiva sulla creazione di criteri per un tipo di contenuto del sito per informazioni su come configurare le funzionalità che si desidera associare al criterio. 
    
6. Scegliere **OK**.
    
## <a name="create-a-policy-for-a-site-content-type"></a>Creare un criterio per un tipo di contenuto del sito
<a name="__create_a_policy"> </a>

Aggiunta di un criterio di gestione delle informazioni a un tipo di contenuto semplifica associare caratteristiche dei criteri a più elenchi o raccolte. È possibile scegliere di aggiungere un criterio di gestione delle informazioni esistente a un tipo di contenuto o creare un criterio univoco specifico a un singolo tipo di contenuto.
  
 È inoltre possibile aggiungere criteri di gestione delle informazioni a un tipo di contenuto specifico di elenchi. Questo è l'effetto dell'applicazione del criterio solo agli elementi presenti nell'elenco che utilizzano il tipo di contenuto. 
  
1. Nella home page del sito insieme \> **Impostazioni**![pulsante SharePoint 2016 impostazioni sulla barra del titolo. ](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Impostazioni sito**.
    
    In un sito connesso al gruppo di SharePoint, fare clic su **Impostazioni**, fare clic su **Contenuto del sito**e quindi fare clic su **Impostazioni sito**. 
    
2. Nella sezione **Raccolte Designer Web** della pagina Impostazioni sito \> **tipi di contenuto del sito**.
  
![Collegamento Tipi di contenuto del sito nella pagina Impostazioni sito](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. Nella pagina Impostazioni del tipo di contenuto del sito, selezionare il tipo di contenuto che si desidera aggiungere un criterio.
    
4. Nella pagina tipo di contenuto del sito, in **Impostazioni** \> **impostazioni dei criteri di gestione delle informazioni**.
    
5. Nella pagina Modifica criterio immettere un nome e una descrizione per il criterio e quindi scrivere una breve descrizione che spiega agli utenti che cos'è per il criterio.
    
6. Nelle sezioni che seguono, selezionare le singole caratteristiche che si desidera aggiungere i criteri di gestione delle informazioni. 
  
![Tipi di criteri del contenuto](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. Per specificare un periodo di conservazione per documenti ed elementi sono al criterio, selezionare **Abilita conservazione**e quindi specificare il periodo di conservazione e le azioni che devono essere svolte scadenza degli elementi.
    
    Per specificare un periodo di conservazione
    
||||||**1.**|* * Scegliere * * aggiungere fase di conservazione per i record a... * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | Selezionare un'opzione periodo di conservazione per specificare quando documenti o elementi sono impostati per scadere. Effettuare una delle operazioni seguenti:<br/>  Per impostare la data di scadenza basata su una proprietà di data, sotto **evento** \> **questa fase si basa una proprietà di data nell'elemento**e quindi selezionare l'azione documento o un elemento (ad esempio creati o modificati) e l'incremento di tempo dopo che questa azione ( ad esempio, il numero di giorni, mesi o anni) quando si desidera che l'elemento scada.  <br/>  Per utilizzare una formula di conservazione personalizzata per determinare la scadenza, selezionare **impostato da una formula di conservazione personalizzata è installata nel server**.  <br/> > [!NOTE]> Questa opzione è disponibile solo se una formula personalizzata è stata impostata dall'amministratore.           |
||||||3.  <br/> |L'opzione **Avvia un flusso di lavoro** è disponibile solo se si sta definendo un criterio per un elenco, una raccolta o un tipo di contenuto che dispone già di un flusso di lavoro associato. Sarà quindi possibile una scelta dei flussi di lavoro da selezionare.<br/> |
||||||4.  <br/> |Nella sezione **ricorrenza** selezionare **ripetere l'azione di questa fase...** e immettere la frequenza con cui si desidera utilizzare l'azione a ripresentarsi.  <br/> > [!NOTE]> Questa opzione è disponibile solo se l'azione che è stata selezionata può essere ripetuta. Ad esempio, è possibile impostare ricorrenza per l'azione di **Eliminazione definitiva**.           |
||||||5.  <br/> |Scegliere **OK**.  <br/> |
   
1. Per abilitare il controllo per i documenti e gli elementi che sono soggetti a questi criteri, selezionare **Attiva controllo**e quindi specificare gli eventi che si desidera controllare.
    
    Per abilitare il controllo
    
||||||1. * * *|Nella pagina Modifica criterio * * **sotto** **controllo** **\>** **attivare il controllo** * *, e quindi selezionare le caselle di controllo accanto agli eventi che si desidera mantenere un audit riepilogo for.* * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |**Per richiedere agli utenti di inserire i codici a barre nei documenti,** **scegliere** **Richiedi agli utenti di inserire un codice a barre prima del salvataggio o della stampa** **.** <br/> |
||||||**3.** <br/> |**Scegliere** **OK** * * per applicare la caratteristica di controllo per il criterio. ** <br/> |
|||||||La caratteristica dei Criteri controllo consente alle organizzazioni di creare e analizzare l'audit trail per i documenti e voci di elenco, ad esempio elenchi di attività, gli elenchi di problemi, i gruppi di discussione e calendari. La caratteristica rende disponibile un registro di controllo che consente di registrare eventi, ad esempio quando contenuto viene visualizzato, modificato o eliminato.  <br/> |
|||||||Quando è abilitato il controllo come parte di un criterio di gestione delle informazioni, gli amministratori possono visualizzare i dati di controllo nei report di utilizzo dei criteri che si basano in Microsoft Excel e che riepilogare i dati di utilizzo corrente. Gli amministratori possono utilizzare questi rapporti per determinare come viene utilizzate informazioni all'interno dell'organizzazione. Questi rapporti anche consente alle organizzazioni per verificare e documentare la conformità alle normative o per analizzare i potenziali problemi.  <br/> |
|||||||Nel registro di controllo vengono registrate le informazioni seguenti: nome dell'evento, data e ora dell'evento e nome di sistema dell'utente che ha eseguito l'azione.  <br/> |
   
1. Quando vengono attivati i codici a barre come parte di un criterio, vengono aggiunti alla proprietà del documento e visualizzati nell'area di intestazione del documento a cui è applicato il codice a barre. Analogamente alle etichette, codici a barre può inoltre essere manualmente eliminato da un documento. È possibile specificare se è necessario richiedere agli utenti da includere il codice a barre per la stampa o il salvataggio di un elemento o se il codice a barre devono essere inserite manualmente nella scheda **Inserisci** in 2010 Office release programmi. 
    
    Per abilitare i codici a barre
    
||||||1. * * *|**Nella pagina Modifica criterio, in **codici a barre** \> **Attiva codici a barre**.**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |Per richiedere agli utenti di inserire i codici a barre nei documenti, selezionare **Richiedi agli utenti di inserire un codice a barre prima del salvataggio o della stampa**.  <br/> |
||||||**3.** <br/> |Fare clic su **OK** per applicare la caratteristica del codice a barre ai criteri.  <br/> |
|||||||
 Il criterio del codice a barre genererà codice 39 standard codici a barre. Ogni immagine codice a barre include il testo che segue il simbolo di codice a barre che rappresenta il valore del codice a barre. In questo modo i dati del codice a barre essere utilizzato anche quando la scansione hardware non è disponibile. Gli utenti possono manualmente digitare il numero di codice a barre nella casella Cerca per individuare l'elemento in un sito.  <br/> |
   
1. Per richiedere che i documenti sono soggetti a questi criteri dispongono di etichette, scegliere **Attiva etichette**e quindi specificare le impostazioni che si desidera utilizzare per le etichette.
    
    Per attivare le etichette
    
||||||**1.**|* * Per richiedere agli utenti di aggiungere un'etichetta a un documento, selezionare **Richiedi agli utenti di inserire un'etichetta prima del salvataggio o della stampa**.  <br/> > [!NOTE]> Se si desidera che le etichette siano facoltative, non selezionare questa casella di controllo.        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |Per bloccare un'etichetta in modo che possa essere modificata dopo essere stata inserita, selezionare **Impedisci modifiche alle etichette dopo che sono state aggiunte**.  <br/>  Questa impostazione impedisce il testo dell'etichetta di aggiornamento dopo l'etichetta è stato inserito in un elemento all'interno di un'applicazione client, ad esempio Word, Excel o PowerPoint. Se si desidera che l'etichetta da aggiornare quando vengono aggiornate le proprietà di documento o dell'elemento, non selezionare questa casella di controllo.<br/> |
||||||3.  <br/> |Nella casella Formato etichetta, immettere il testo dell'etichetta che si desidera venga visualizzato. Etichette possono contenere un massimo di 10 riferimenti a colonne, ognuna delle quali può contenere un massimo di 255 caratteri. Per creare il formato per l'etichetta, eseguire le operazioni seguenti:  <br/> Digitare i nomi delle colonne in cui si desidera includere nell'etichetta nell'ordine in cui si desidera vengano visualizzati. Racchiudere i nomi di colonna racchiuso tra parentesi graffe ({}), come illustrato nell'esempio nella pagina Modifica criterio.  <br/> Digitare le parole per identificare le colonne all'esterno delle parentesi, come illustrato nell'esempio nella pagina Modifica criterio.  <br/> |
||||||4.  <br/> |Per aggiungere un'interruzione di riga, immettere **\n** in cui si desidera venga visualizzato l'interruzione di riga.  <br/> |
||||||5.  <br/> |Selezionare la dimensione del carattere e lo stile desiderato e specificare se si desidera che l'etichetta posizionato a sinistra, al centro o destra all'interno del documento.  <br/>  Selezionare un tipo di carattere e lo stile che sono disponibili nei computer degli utenti. La dimensione del tipo di carattere influisce sulla quantità di testo possono essere visualizzati nell'etichetta.  <br/> |
||||||6.  <br/> |Immettere l'altezza e la larghezza dell'etichetta. Altezza dell'etichetta compreso tra.25 pollici per 20 pollici e larghezza dell'etichetta può variare da.25 pollici per 20 pollici. Testo dell'etichetta è sempre verticale allineato al centro all'interno dell'immagine etichetta.  <br/> |
||||||7.  <br/> |Selezionare **Aggiorna** per visualizzare in anteprima il contenuto dell'etichetta.  <br/> |
   
1. Scegliere **OK**.
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Creare un criterio per un elenco, una raccolta o cartella (criteri di conservazione basati sulla posizione)
<a name="__create_a_policy"> </a>

È possibile definire un criterio di conservazione che si applica solo a un elenco specifico, raccolta o cartella. Tuttavia, se si crea un criterio di conservazione in questo modo, non è possibile riutilizzare questo criterio su altri elenchi, raccolte, cartelle o siti e non è possibile applicare un criterio della raccolta siti a un criterio di posizione basato su.
  
Se si desidera applicare un criterio di conservazione singolo a tutti i tipi di contenuto in un'unica posizione, è probabile che si desidera utilizzare conservazione basata su percorso. In molti altri casi, è possibile verificare che sia stato specificato un criterio di conservazione per tutti i tipi di contenuto.
  
 Ogni sottocartella eredita il criterio di conservazione dell'elemento padre, a meno che non è possibile interrompere l'ereditarietà e definire un nuovo criterio di conservazione a livello di figlio. 
  
Se si desidera definire un criterio di gestione delle informazioni diversa dalla conservazione per un elenco o raccolta, è necessario definire un criterio di gestione delle informazioni per ogni tipo di contenuto di elenco associato a tale elenco o raccolta.
  
 Se in qualsiasi momento si decide di passare dal tipo di contenuto a criteri basati sul percorso per un elenco o raccolta, il criterio di conservazione da utilizzare come criteri basati sul percorso. Tutti gli altri criteri di gestione (verifiche, codici a barre e i codici a barre) verranno ereditati dai tipi di contenuto associati. 
  
 I criteri basati su percorso possono essere disattivati per una raccolta siti mediante la disattivazione della caratteristica raccolta e conservazione basata sulle cartelle. In questo modo gli amministratori della raccolta siti garantire che i criteri tipo di contenuto non vengono ignorati i criteri di posizione basato su di un amministratore elenco. 
  
È necessario almeno dell'autorizzazione Gestione elenchi per modificare le impostazioni dei criteri di gestione delle informazioni per un elenco o raccolta.
  
1. Passare all'elenco o alla raccolta per cui si desidera specificare criteri di gestione delle informazioni. 
    
2. Sulla barra multifunzione fare clic sulla scheda **raccolta** o **elenco** \> **Impostazioni elenco**o **Impostazioni raccolta** .
    
    In SharePoint Online, fare clic su **Impostazioni** e quindi fare clic su **Impostazioni elenco** o **Impostazioni raccolta**. 
    
3. In **autorizzazioni e gestione** \> **impostazioni dei criteri di gestione delle informazioni**.
  
![Collegamento ai criteri gestione informazioni nella pagina di impostazioni per una raccolta documenti](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Nella pagina Impostazioni dei criteri di gestione delle informazioni, verificare che l'origine della conservazione per l'elenco o una libreria è impostata su raccolta e cartelle. 
  
Se viene visualizzato **Il tipo di contenuto** come origine, fare clic su **Cambia origine**e quindi fare clic su **raccolta e cartelle**. Si riceverà un avviso che verranno ignorati i criteri di conservazione tipo di contenuto. Fare clic su **OK**. 
    
5. Nella pagina Modifica criterio, in **Pianificazione della libreria di conservazione basati su**, immettere una breve descrizione per il criterio che si sta creando. 
    
6. Scegliere **Aggiungi fase di conservazione...**
    
     Si noti che in record, è possibile definire criteri di conservazione diversi per i record selezionando le fasi di conservazione diversi definire per l'opzione di record. 
    
7. Nella finestra di dialogo proprietà Stage, selezionare un'opzione periodo di conservazione per specificare quando set di documenti o elementi per scadere. Effettuare una delle operazioni seguenti:
    
  - Per impostare la data di scadenza basata su una proprietà di data, sotto **evento** \> **questa fase si basa una proprietà di data nell'elemento**e quindi selezionare l'azione documento o un elemento (ad esempio creati o modificati) e l'incremento di tempo dopo che questa azione ( ad esempio, il numero di giorni, mesi o anni) quando si desidera che l'elemento scada. 
    
  - Per utilizzare una formula di conservazione personalizzata per determinare la scadenza, selezionare **impostato da una formula di conservazione personalizzata è installata nel server**. 
    
    > [!NOTE]
    >  Questa opzione è disponibile solo se una formula personalizzata è stata impostata dall'amministratore. 
  
  - In **azione**, specificare gli elementi da eseguire alla scadenza del documento o dell'elemento. Per attivare un'azione specifica si verifica per il documento o un elemento (ad esempio l'eliminazione), selezionare un'azione dall'elenco. 
    
8. L'opzione **Avvia un flusso di lavoro** è disponibile solo se si sta definendo un criterio per un elenco, una raccolta o un tipo di contenuto che dispone già di un flusso di lavoro associato. Sarà quindi possibile una scelta dei flussi di lavoro da selezionare. 
    
9. In **ricorrenza**, scegliere **ripetere l'azione di questa fase...** e immettere la frequenza con cui si desidera utilizzare l'azione a ripresentarsi. 
    
    > [!NOTE]
    >  Questa opzione è disponibile solo se l'azione che è stata selezionata può essere ripetuta. Ad esempio, è possibile impostare ricorrenza per l'azione di **Eliminazione definitiva**. 
  
10. Scegliere **OK**.
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Applicare un criterio di raccolta siti a un tipo di contenuto
<a name="__apply_a_site"> </a>

Criteri di gestione delle informazioni sono già stati creati per il sito come criteri di raccolta siti, è possibile applicare uno dei criteri per un tipo di contenuto. In questo modo, è possibile applicare gli stessi criteri per più tipi di contenuto in una raccolta siti che non condividono lo stesso tipo di contenuto principale.
  
 Se si desidera applicare i criteri per più tipi di contenuto in una raccolta siti e aver configurato un servizio metadati gestiti, è possibile utilizzare contenuto di tipo di pubblicazione per la pubblicazione fuori la gestione dei criteri a più raccolte siti. Vedere la sezione [applicare un criterio ai tipi di contenuto tra raccolte siti](create-info-mgmt-policies.md#__apply_a_policy) per ulteriori informazioni. 
  
1. Passare all'elenco o raccolta che contiene il tipo di contenuto a cui si desidera applicare un criterio.
    
2. Sulla barra multifunzione fare clic sulla scheda **raccolta** o **elenco** \> **Impostazioni elenco**o **Impostazioni raccolta** .
    
    In SharePoint Online, fare clic su **Impostazioni** e quindi fare clic su **Impostazioni elenco** o **Impostazioni raccolta**. 
    
3. In **autorizzazioni e gestione** \> **impostazioni dei criteri di gestione delle informazioni**.
  
![Collegamento ai criteri gestione informazioni nella pagina di impostazioni per una raccolta documenti](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Verificare che l'origine del criterio è impostato per **Tipi di contenuto**e, in **Criteri tipo di contenuto** selezionare il tipo di contenuto che si desidera applicare il criterio. 
    
5. In **specificare il criterio** \> **Usa criterio raccolta siti**e quindi selezionare il criterio che si desidera applicare dall'elenco. 
    
    > [!NOTE]
    >  Se l'opzione **Usa criterio raccolta siti** non è disponibile, nessun criterio raccolta siti è stato definito per la raccolta siti. 
  
6. Scegliere **OK**.
    
     Se l'elenco o una raccolta in uso supporta la gestione di più tipi di contenuto, è possibile scegliere il tipo di contenuto per cui si desidera specificare criteri di gestione delle informazioni in **Tipi di contenuto** . Verrà visualizzata direttamente al passaggio 5. 
    
## <a name="apply-a-policy-across-site-collections"></a>Applicare un criterio tra le raccolte siti
<a name="__toc260646789"> </a>

Condividere tipi di contenuto tra raccolte siti utilizzando un'applicazione di servizio metadati gestiti per configurare la pubblicazione di tipo di contenuto. Pubblicazione del tipo di contenuto consente di gestire il contenuto e metadati in modo coerente nei siti perché i tipi di contenuto possono essere creati e aggiornati in modo centralizzato e aggiornamenti possono essere pubblicati fuori in più raccolte siti con sottoscrizione o applicazioni Web.
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Creare un modello da un criterio esistente per l'utilizzo tra le raccolte siti
<a name="__toc262125409"> </a>

È possibile definire criteri di gestione delle informazioni e quindi il nome di un modello da utilizzare in base alle esigenze in più raccolte siti. Questo metodo può essere utilizzato se si desidera disporre di un backup di criteri di informazioni o può essere utilizzato anche come un metodo alternativo all'utilizzo di pubblicazione del tipo di contenuto per applicare un criterio tra le raccolte siti. Per creare un modello o un backup del criterio, esportare i criteri da una raccolta siti e la successiva importazione in un percorso salvato o a un'altra raccolta siti.
  
> [!IMPORTANT]
>  Se si utilizza l'importazione/esportazione feature come un modo per rendere un set di modelli di criteri, tenere presente che esiste un identificatore univoco del file con estensione XML dei criteri. Per questo motivo, è possibile importare quel criterio in un sito a più volte senza modificare l'identificatore univoco. 
  
### <a name="export-a-policy"></a>Esportare un criterio
<a name="__toc260646790"> </a>

1. Nella home page della raccolta siti scegliere **Impostazioni**![ingranaggio piccole impostazioni che è stata effettuata delle impostazioni del sito. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Impostazioni sito**.
    
    In un sito connesso al gruppo di SharePoint, fare clic su **Impostazioni**, fare clic su **Contenuto del sito**e quindi fare clic su **Impostazioni sito**. 
    
2. Nella pagina Impostazioni sito, in **Amministrazione raccolta siti** \> **Modelli di criteri di tipi di contenuto**. 
  
![Collegamento Modelli di criteri tipo di contenuto nella pagina Impostazioni sito](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Scegliere i criteri che si desidera esportare \> scorrere fino alla fine \> **esportazione**.
    
4. Al prompt dei comandi alla Salva o si apre il file, scegliere **Salva**e quindi selezionare un percorso in cui salvare il file. Assicurarsi di selezionare un percorso disponibile per le raccolte siti che si importano il criterio.
    
5. Quando viene visualizzata la finestra di dialogo Download completato, scegliere **Chiudi**.
    
### <a name="import-a-policy-to-a-different-site-collection"></a>Importare un criterio a un'altra raccolta siti
<a name="__toc260646791"> </a>

Importazione di un criterio di gestione delle informazioni consente di applicare più tipi di contenuto a livello di sito o un elenco di qualsiasi raccolta siti specificata. I vantaggi di questa operazione sono duplice: non è necessario rieseguire definire e applicare i criteri per ogni tipo di contenuto e con maggiore semplicità, è possibile gestire le modifiche dei criteri apportando modifiche al criterio in un'unica posizione.
  
1. Nella home page della raccolta siti a cui si desidera applicare il criterio, scegliere **Impostazioni**![ingranaggio piccole impostazioni che è stata effettuata delle impostazioni del sito. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Impostazioni sito**.
    
    In un sito connesso al gruppo di SharePoint, fare clic su **Impostazioni**, fare clic su **Contenuto del sito**e quindi fare clic su **Impostazioni sito**. 
    
2. Nella pagina Impostazioni sito, in **Amministrazione raccolta siti** \> **Modelli di criteri di tipi di contenuto**.
    
3. Nella pagina criteri \> **importazione** \> **Sfoglia** per individuare il file XML per il criterio. 
    
4. Selezionare il file XML in cui è stato salvato il criterio \> **aperto**. 
    
5. Durante l'importazione criterio raccolta siti di pagina \> **importazione** per aggiungere il criterio della raccolta siti. 
    
I criteri importati possono ora applicato a uno o più tipi di contenuto a livello di sito o elenco. 
  
[Criteri di gestione delle informazioni attivare le etichette ai documenti o all'organizzazione di controllo di tempo che deve conservare contenuto, per controllare quali utenti eseguire con il contenuto e per aggiungere i codici a barre. Un criterio consente di applicare la conformità alle normative legali e governative o processi aziendali interni. In qualità di amministratore, è possibile impostare un criterio per controllare la modalità di tenere traccia di documenti e la durata di conservazione di documenti. È possibile creare può Criteri gestione informazioni dislocati tre nella gerarchia del sito dal più ampio per ristretto: creare un criterio da utilizzare in più tipi di contenuto all'interno di una raccolta siti. Creare un criterio per un tipo di contenuto del sito. Creare un criterio per un elenco o raccolta. Per ulteriori informazioni, vedere Introduzione ai criteri di gestione delle informazioni.](create-info-mgmt-policies.md#__top)
  

