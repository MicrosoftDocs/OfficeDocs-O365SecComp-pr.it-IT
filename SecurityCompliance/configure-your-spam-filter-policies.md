---
title: Configurare i criteri di filtro della posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
description: Impostazioni del filtro posta indesiderata base includono selezionando l'azione da eseguire sui messaggi che vengono identificati come posta indesiderata e scegliendo se si desidera filtrare i messaggi scritti in determinate lingue o inviati da determinati paesi o aree.
ms.openlocfilehash: b0a5fa1a5640bd0baab68c29d8098059a6025f7d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026533"
---
# <a name="configure-your-spam-filter-policies"></a>Configurare i criteri di filtro della posta indesiderata
  
Impostazioni del filtro posta indesiderata base includono selezionando l'azione da eseguire sui messaggi che vengono identificati come posta indesiderata e scegliendo se si desidera filtrare i messaggi scritti in determinate lingue o inviati da determinati paesi o aree. Le impostazioni dei criteri di filtro posta indesiderata sono solo i messaggi applicati a in ingresso. È possibile modificare il criterio di filtro posta indesiderata predefiniti per configurare le impostazioni di filtro posta indesiderata a livello di azienda e creare criteri del filtro posta indesiderata personalizzata e quindi applicarle a specifici utenti, gruppi o i domini nell'organizzazione. Criteri personalizzati hanno sempre la precedenza sul criterio predefinito. È possibile modificare l'ordine in cui vengono eseguiti i criteri personalizzati modificando la priorità di ogni criterio personalizzato.
  
> [!IMPORTANT]
> Per i clienti autonomo di Exchange Online Protection (EOP): per impostazione predefinita, il filtro da posta indesiderata EOP invia messaggi di rilevamento posta indesiderata nella cartella posta indesiderata di ogni destinatario. Tuttavia, per assicurare che l'azione **spostare il messaggio nella cartella posta indesiderata** può essere utilizzato per le cassette postali locali, è necessario configurare le regole di trasporto di Exchange sui server locali per rilevare le intestazioni di posta indesiderata che vengono aggiunti da EOP. Per ulteriori informazioni, vedere [verificare che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
## <a name="what-you-must-know-before-you-begin"></a>Che cosa è necessario conoscere prima di iniziare
<a name="sectionSection0"> </a>

Tempo stimato per il completamento: 30 minuti
  
È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce di protezione da posta indesiderata nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-exchange-admin-center-eac-to-configure-spam-filter-policies"></a>Utilizzo dell'Interfaccia di amministrazione di Exchange (EAC) per la configurazione dei criteri di filtro di protezione da posta indesiderata
<a name="sectionSection1"> </a>

1. In Interfaccia di amministrazione di Exchange, accedere a **Protezione** \> **Filtro posta indesiderata**.
    
2. Nella pagina **Generale** eseguire una delle operazioni seguenti: 
    
  - Fare doppio clic sul criterio predefinito per modificare questo criterio al livello dell'azienda.
    
  - Fare clic sull'icona ![Icona Aggiungi](media/ITPro-EAC-AddIcon.png) **Nuovo** per creare un nuovo criterio di filtro di protezione dalla posta indesiderata personalizzato da applicare a utenti, gruppi e domini all'interno della propria organizzazione. Inoltre, è possibile modificare i criteri personalizzati già esistenti facendo doppio clic su di essi. 
    
3. Per i criteri personalizzati, specificare un nome per questo criterio. Facoltativamente, è inoltre possibile specificare una descrizione più dettagliata. Non è possibile rinominare il criterio predefinito.
    
    > [!NOTE]
    > Quando si crea un criterio, tutte le impostazioni di configurazione vengono visualizzati in una sola schermata. Al contrario, quando si modifica un criterio, è necessario spostarsi tra più schermate. Le impostazioni sono gli stessi in entrambi i casi, ma il resto di questa procedura viene descritto come accedere a queste impostazioni quando si modifica un criterio. 
  
4. Nella pagina relativa alle **azioni per posta indesiderata e posta inviata in blocco**, in **Posta indesiderata** e **Alta probabilità di posta indesiderata**, selezionare l'operazione da effettuare per la posta elettronica in blocco e la posta indesiderata in arrivo. Per impostazione predefinita, l'opzione **Sposta i messaggi nella cartella Posta indesiderata** è selezionata. Gli altri valori possibili sono: 
    
  - **Elimina messaggio** Elimina l'intero messaggio, inclusi gli allegati. 
    
  - **Messaggio in quarantena** Il messaggio non viene inviato ai destinatari, ma viene messo in quarantena. Selezionando questa opzione nella casella di controllo **Mantieni posta indesiderata per (giorni)**, si specifica per quanti giorni i messaggi indesiderati vengono messi in quarantena (il messaggio viene eliminato automaticamente al termine del tempo trascorso. Il valore predefinito massimo è 15 giorni. Il valore minimo è 1 giorno). 
    
    > [!TIP]
    >  Per informazioni su come gli amministratori possono gestire i messaggi di posta elettronica che risiedono nella quarantena in EAC, vedere [Quarantine](quarantine.md) e [trovare e rilasciare i messaggi in quarantena come amministratore](find-and-release-quarantined-messages-as-an-administrator.md). > Per informazioni su come configurare i messaggi di notifica di posta indesiderata da inviare agli utenti, vedere [Configure dell'utente finale in EOP le notifiche di posta indesiderata](configure-end-user-spam-notifications-in-eop.md) o [Configure End-User spam notifiche di Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
  - **Sposta messaggio nella cartella Posta indesiderata** Sposta i messaggi di destinatari specifici nella cartella Posta indesiderata. Questa è un'azione predefinita per entrambi i livelli di probabilità di posta indesiderata. 
    
    > [!IMPORTANT]
    > Per utenti di Exchange Online Protection (EOP): Affinché tale operazione funzioni con cassette postali locali, è necessario configurare anche due regole di trasporto di Exchange nei server locali per individuare intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
  - **Aggiungere X-header** Invia il messaggio ai destinatari specificati, ma viene inserito testo X-header l'intestazione del messaggio per identificare il messaggio come posta indesiderata. Utilizzando il testo come identificatore, è possibile creare regole posta in arrivo o utilizzare un dispositivo downstream di agire sul messaggio. Il testo X-header predefinito è **viene visualizzato questo messaggio di posta indesiderata**.
    
    È possibile personalizzare il testo dell'intestazione X utilizzando la casella di input **aggiungere tale testo X-header** . Se si personalizza testo X-header, tenere conto delle condizioni seguenti: 
    
  - Se si specifica solo l'intestazione in formato \< *intestazione*\>, in cui non sono disponibili spazi all'interno di \< *intestazione*\>, due punti verranno aggiunto al testo personalizzato, seguito dal testo predefinito. Ad esempio, se si specifica "Questo è-personali-personalizzato-intestazione", il testo X-header verrà visualizzata come "questo è-personali-personalizzato-intestazione: viene visualizzato questo messaggio di posta indesiderata."       
    
  - Se si includono spazi all'interno del testo dell'intestazione personalizzata o se ci si aggiunge due punti (ad esempio "X si tratta di intestazione personalizzata" o "X-This-is-my-custom-header:"), il testo X-header ripristinata l'impostazione predefinita come "X questa-viene-posta indesiderata: viene visualizzato questo messaggio di posta indesiderata."
    
  - Non è possibile specificare il testo dell'intestazione nel formato \< *intestazione*  \>:\<  *valore*  \>. In questo caso, entrambi i valori prima e dopo che i due punti verranno ignorato e viene visualizzato il testo X-header predefinito: "X questa-viene-posta indesiderata: viene visualizzato questo messaggio di posta indesiderata." 
    
  - **Prepend oggetto del messaggio con testo** Invia il messaggio al destinatario ma antepone riga dell'oggetto con il testo specificato nella casella **prefisso** all'oggetto del messaggio con il testo input. Utilizzando il testo come identificatore, se lo si desidera creare le regole per filtrare o instradare i messaggi in base alle necessità. 
    
  - **Reindirizzare i messaggi di posta elettronica** Invia il messaggio a un indirizzo di posta elettronica designati anziché al destinatario. Specificare l'indirizzo "reindirizza" nella casella di input **reindirizzare per questo indirizzo di posta elettronica** . 
    
    > [!NOTE]
    > Per ulteriori informazioni relative ai livelli di probabilità di posta indesiderata, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md). 
  
5. In **posta elettronica in blocco**, è possibile selezionare una soglia di trattamento di posta elettronica in blocco come posta indesiderata. Questa soglia si basa sul livello reclamo di blocco del messaggio. È possibile scegliere un'impostazione di soglia compreso tra 1 e 9, dove 1 indica la maggior parte delle posta elettronica in blocco come posta indesiderata e 9 consente la posta elettronica in blocco più possibile recapitare. Il servizio quindi esegue l'azione configurata, ad esempio invia il messaggio nella cartella posta indesiderata del destinatario. Vedere [i valori al livello di blocco reclamo](bulk-complaint-level-values.md) e [Qual è la differenza tra posta indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md) per ulteriori informazioni. 
    
6. Nella pagina **Elenchi contatti bloccati**, è possibile specificare voci, come mittenti o domini, che verranno sempre contrassegnati come Posta indesiderata. Il servizio applica l'azione di probabilità di posta indesiderata configurata alla posta elettronica che corrisponde a tali voci. 
    
  - Aggiungere i mittenti indesiderati all'elenco dei mittenti bloccati. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.png) e, nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **OK** per tornare alla pagina degli **elenchi di indirizzi bloccati**. 
    
  - Aggiungere i domini indesiderati all'elenco dei domini bloccati. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.png) e, nella finestra di dialogo di selezione, aggiungere i domini che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **OK** per tornare alla pagina degli **elenchi di indirizzi bloccati**. 
    
    > [!CAUTION]
    > Se si bloccano domini di livello superiore, è probabile che la posta elettronica desiderata verrà contrassegnata come Posta indesiderata. 
  
7. Nella pagina degli **elenchi di indirizzi consentiti**, è possibile specificare voci, come mittenti e domini, ai quali verranno sempre recapitati messaggi di posta elettronica nella Posta in arrivo. La posta elettronica proveniente da tali voci non viene elaborata dal filtro di protezione da posta indesiderata. 
    
  - Aggiungere i mittenti attendibili a Elenco mittenti consentiti. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.png) e, nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera autorizzare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su OK per tornare alla pagina degli **elenchi elementi consentiti**. 
    
  - Aggiungere i domini attendibili a Elenco di domini consentiti. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.png) e, nella finestra di dialogo di selezione, aggiungere i domini che si desidera autorizzare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su OK per tornare alla pagina degli **elenchi elementi consentiti**. 
    
    > [!CAUTION]
    > Se si consentono domini di livello superiore, è probabile che la posta elettronica indesiderata sarà recapitata in una cartella di Posta in arrivo. 
  
8. Nella pagina **Posta indesiderata internazionale** è possibile filtrare i messaggi di posta elettronica vengono scritti in determinate lingue o inviati da determinati paesi o aree. È possibile configurare fino a 250 aree geografiche diverse e 86 lingue diverse. Il servizio verrà applicata l'azione configurato per la posta indesiderata confidenza elevata. 
    
1. Selezionare la casella di controllo di **filtrare i messaggi di posta elettronica scritti nelle lingue seguenti** per attivare questa funzionalità. Fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.png)e quindi, nella finestra di dialogo Selezione effettuare le scelte (è supportata la selezione multipla). Ad esempio, se si seleziona per filtrare i messaggi scritti in contabilità arabo (clienti) e **messaggi in quarantena** è l'azione configurata per i messaggi di posta indesiderata confidenza elevata, tutti i messaggi scritti in arabo verranno messo in quarantena. Fare clic su **ok** per tornare al riquadro **Della posta indesiderata internazionale** . 
    
2. Selezionare la casella di controllo **filtrare i messaggi di posta elettronica inviati da paesi seguenti** per attivare questa funzionalità. Fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.png)e quindi, nella finestra di dialogo Selezione effettuare le scelte (è supportata la selezione multipla). Ad esempio, se si seleziona per filtrare tutti i messaggi inviati da Australia (AU) e **messaggi in quarantena** è l'azione configurata per i messaggi di posta indesiderata confidenza elevata, quindi i messaggi inviati da Australia verrà messo in quarantena. Fare clic su **ok** per tornare al riquadro **Della posta indesiderata internazionale** . 
    
    > [!NOTE]
    > Per impostazione predefinita, se non sono selezionate opzioni di posta indesiderata interne, il servizio esegue il normale filtro di posta indesiderata sui messaggi inviati in tutte le lingue e da tutte le regioni. I messaggi vengono analizzati e se il messaggio viene rilevato come posta indesiderata o posta indesiderata ad alta probabilità, vengono applicate le azioni configurate. 
  
9. Nella pagina **Opzioni avanzate** , è possibile selezionare **in**, **disattivare**o **Test** per ogni filtro della posta indesiderata opzione. 
    
1. **In** I messaggi vengono attivamente filtrati in base alla regola associato a tale opzione. I messaggi sono contrassegnati come posta indesiderata o verranno hanno i punteggi spam aumentato, a seconda le opzioni che si accende. 
    
2. **Disattiva** Non viene compiuta alcuna azione sui messaggi che soddisfano i criteri del filtro di posta indesiderata. Per impostazione predefinita, tutte le opzioni sono disattivate. 
    
3. **Test** Nei messaggi che soddisfano i criteri di filtro posta indesiderata viene eseguita alcuna azione. Tuttavia, i messaggi possono essere contrassegnati aggiungendo un X-header prima che siano inviati al destinatario previsto. Questo X-header consente di verificare se l'opzione ASF corrispondente. Se è specificato per una qualsiasi delle opzioni avanzate di **Test** , è possibile configurare le seguenti impostazioni di modalità di test da applicare quando viene individuata una corrispondenza a un'opzione abilitati per i test: 
    
  - **Nessuno** Per impostazione predefinita, non vengono intraprese azioni in modalità test sul messaggio. 
    
  - **Aggiungi il valore predefinito di testing testo X-header** Se si seleziona questa opzione Invia il messaggio ai destinatari specificati, ma anche aggiunge un X-header speciali per il messaggio per identificarla come visto corrispondenti a una specifica filtro della posta indesiderata opzione. 
    
  - **Inviare un messaggio Ccn a questo indirizzo** Se si seleziona questa opzione Invia una copia nascosta del messaggio all'indirizzo specificato nella casella di input. 
    
    > [!TIP]
    > Per ulteriori informazioni sulla posta indesiderata filtro opzioni, tra cui descrizioni di ogni opzione e il testo X-header associato a ciascuno di essi, vedere [Opzioni di filtro posta indesiderata](advanced-spam-filtering-asf-options.md). 
  
10. Per i criteri personalizzati solo, fare clic sulla voce di menu **Applica a** e quindi creare una regola basata su condizione per specificare gli utenti, gruppi e i domini a cui applicare il criterio. È possibile creare più condizioni, se sono univoci. 
    
  - Per selezionare gli utenti, selezionare **il destinatario è**. Nella finestra di dialogo successiva, selezionare uno o più mittenti della società dall'elenco di selezione degli utenti e quindi fare clic su **Aggiungi**. Per aggiungere i mittenti che non sono presenti nell'elenco, digitare gli indirizzi di posta elettronica e quindi fare clic su **Controlla nomi**. In questa casella è inoltre possibile utilizzare i caratteri jolly per più indirizzi di posta elettronica (ad esempio: \* @  _domainname_). Dopo aver effettuato le selezioni, fare clic su **ok** per tornare alla schermata principale. 
    
  - Per selezionare gruppi, selezionare **il destinatario è un membro di**. Nella finestra di dialogo successiva, selezionare o specificare i gruppi. Fare clic su **ok** per tornare alla schermata principale. 
    
  - Per selezionare i domini, selezionare **il dominio del destinatario**. Quindi, nella finestra di dialogo successiva, aggiungere i domini. Fare clic su **ok** per tornare alla schermata principale. 
    
    È possibile creare eccezioni all'interno della regola. Ad esempio, è possibile filtrare i messaggi da tutti i domini ad eccezione di un determinato dominio. Fare clic su **Aggiungi eccezione**e quindi creare le condizioni di eccezione allo stesso modo creata altre condizioni.
    
    > [!TIP]
    > Applicare un criterio della posta indesiderata a un gruppo è supportata solo per i **Gruppi di protezione abilitato posta**. 
  
11. Fare clic su **salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri.
    
> [!TIP]
>  È possibile selezionare o deselezionare le caselle di controllo nella colonna **attivato** per attivare o disattivare i criteri personalizzati. Per impostazione predefinita, tutti i criteri sono abilitati. Il criterio predefinito non può essere disattivato. > Per eliminare un criterio personalizzato, selezionare il criterio, fare clic sul ![sull'icona cestino](media/ITPro-EAC-DeleteIcon.png) icona **eliminare** , quindi confermare che si desidera eliminare il criterio. Impossibile eliminare il criterio predefinito. > Criteri personalizzati hanno sempre la precedenza sul criterio predefinito. Criteri personalizzati eseguiti nell'ordine inverso in cui è stato creato li (da meno recente al più recente), ma è possibile modificare la priorità (in esecuzione ordine) dei criteri personalizzati facendo clic sul ![sull'icona di freccia su](media/ITPro-EAC-UpArrowIcon.png) freccia su e ![icona di freccia verso il basso](media/ITPro-EAC-DownArrowIcon.png) verso il basso freccia. Il criterio con **priorità** **0** eseguirà primo, seguita da **1**, quindi **2**e così via. 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>Utilizzo di PowerShell per la configurazione dei criteri di filtro di protezione dalla posta indesiderata
<a name="sectionSection2"> </a>

È inoltre possibile configurare e applicare criteri di filtro da posta indesiderata in PowerShell. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) Visualizzare le impostazioni di filtro di protezione dalla posta indesiderata. 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) Modificare le impostazioni di filtro di protezione dalla posta indesiderata. 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) Creare un nuovo criterio di filtro di protezione dalla posta indesiderata personalizzato. 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) Eliminare un criterio di filtro di protezione dalla posta indesiderata personalizzato. 
    
Per applicare un criterio di filtro di protezione dalla posta indesiderata personalizzato a utenti, gruppi e/o domini, utilizzare il cmdlet [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) (per creare una nuova regola di filtro che possa essere applicata ai criteri personalizzati) oppure il cmdlet [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) (per modificare una regola di filtro esistente che possa essere applicata ai criteri personalizzati). Utilizzare il cmdlet [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) oppure il cmdlet [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) per abilitare o disabilitare la regola applicata al criterio. 
  
## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo
<a name="sectionSection3"> </a>

Per assicurarsi di aver identificato correttamente la posta indesiderata, è possibile inviare un messaggio GTUBE tramite il servizio. Come il file di test antivirus EICAR, GTUBE fornisce un test tramite il quale è possibile verificare se il servizio individua la posta indesiderata in arrivo. Un messaggio GTUBE viene sempre identificato come posta indesiderata e le azioni eseguite sul messaggio potrebbero corrispondere alle impostazioni configurate.
  
Includere il seguente testo GTUBE in un messaggio di posta o in una singola riga, senza spazi o interruzioni di riga:
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>Regolazione dei criteri del filtro della posta indesiderata per impedire falsi positivi e falsi negativi
<a name="sectionSection4"> </a>

Se si desidera intraprendere un approccio aggressivo, è possibile attivare opzioni avanzate per il filtro della posta indesiderata. Per informazioni sulle impostazioni relative alla posta indesiderata per un'intera organizzazione, consultare [Evitare che la posta elettronica venga erroneamente contrassegnata come posta indesiderata tramite un elenco di indirizzi attendibili o altre tecniche](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [Bloccare la posta indesiderata con il filtro di posta indesiderata di Office 365 per prevenire il problema dei falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225). Questi articoli sono utili se si svolge il ruolo di amministratore e si desidera impedire la visualizzazione di falsi negativi o di falsi positivi.
  
## <a name="new-to-office-365"></a>Nuovo utente di Office 365?
<a name="sectionSection5"> </a>

||
|:-----|
|![Piccola icona per LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuovo utente di Office 365?**         Sono disponibili esercitazioni video gratuite per **Office 365 admins and IT pros** grazie a LinkedIn Learning. |
   
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection6"> </a>

[Configurare i criteri di filtro di connessione](configure-the-connection-filter-policy.md)
  
[Configurare i criteri di posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Quarantena](quarantine.md)
  
[Evitare che la posta elettronica venga erroneamente contrassegnata come posta indesiderata tramite un elenco di indirizzi attendibili o altre tecniche](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

