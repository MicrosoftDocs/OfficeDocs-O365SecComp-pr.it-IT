---
title: Configurare i criteri di filtro della posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Le impostazioni di base dei filtri per la posta indesiderata includono la selezione dell'azione da intraprendere per i messaggi identificati come posta indesiderata e la scelta se filtrare i messaggi scritti in determinate lingue o inviati da paesi o aree geografiche specifiche.
ms.openlocfilehash: 44ed773ae95976714d502a142aed75fa24a1b843
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296989"
---
# <a name="configure-your-spam-filter-policies"></a>Configurare i criteri di filtro della posta indesiderata
  
Le impostazioni di base dei filtri per la posta indesiderata includono la selezione dell'azione da intraprendere per i messaggi identificati come posta Le impostazioni dei criteri di filtro della posta inDesiderata vengono applicate solo ai messaggi in ingresso. È possibile modificare i criteri di filtro della posta indesiderata predefiniti per configurare le impostazioni del filtro di posta indesiderata a livello aziendale e creare criteri di filtro della posta indesiderata personalizzati, quindi applicarli a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito. È possibile modificare l'ordine in cui i criteri personalizzati vengono eseguiti modificando la priorità di ogni criterio personalizzato. Tuttavia, solo il criterio di priorità più alto verrà applicato se più criteri soddisfano i criteri impostati. 
  
> [!IMPORTANT]
> Per i clienti autonomi di Exchange Online Protection (EOP): per impostazione predefinita, i filtri di posta indesiderata di EOP inviano messaggi di posta indesiderata alla cartella posta indesiderata di ogni destinatario. Tuttavia, per assicurarsi che il **messaggio di spostamento all'azione della cartella posta** indesiderata funzioni per le cassette postali locali, è necessario configurare le regole di trasporto di Exchange nei server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere Verificare che la posta indesiderata [venga instradata alla cartella posta indesiderata di ogni utente](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
## <a name="what-you-must-know-before-you-begin"></a>Cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento: 30 minuti
  
Prima di poter eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate. Per sapere quali autorizzazioni sono necessarie, vedere la voce protezione da posta indesiderata nell'argomento [autorizzazioni funzionalità in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.
  
## <a name="use-the-security--compliance-center-scc-to-configure-spam-filter-policies"></a>Utilizzare il Centro sicurezza & Compliance (SCC) per configurare i criteri di filtro della posta indesiderata

1. Nel centro sicurezza & Compliance (SCC), passare a protezione dalla **posta**indesiderata **dei** \> **criteri** \> di gestione delle minacce.
    
2. Nella pagina impostazioni di protezione da **posta** indesiderata eseguire una delle operazioni seguenti: 
    
      - Esaminare i criteri predefiniti a livello di azienda nelle impostazioni standard.
    
      - Fare clic sulla scheda **Custom** , cambiare il selettore **delle impostazioni personalizzate** **su**attivato e fare clic sull'![icona](media/ITPro-EAC-AddIcon.gif) * * Aggiungi **un criterio** per creare un nuovo criterio di filtro di posta indesiderata personalizzato che può essere applicato a utenti, gruppi, e i domini nell'organizzazione. È inoltre possibile modificare i criteri personalizzati esistenti facendo doppio clic su di essi. 
    
3. Solo per i criteri personalizzati, specificare un nome per il criterio. Facoltativamente, è anche possibile specificare una descrizione più dettagliata. Non è possibile rinominare il criterio predefinito.<br/><br/>Nota: quando si crea un criterio, tutte le impostazioni di configurazione vengono visualizzate in una singola schermata. Al contrario, quando si modifica un criterio, è necessario spostarsi tra più schermate. Le impostazioni sono le stesse in entrambi i casi, ma nella parte restante di questa procedura viene descritto come accedere a queste impostazioni quando si modifica un criterio. 
  
4. Nella pagina relativa alle **azioni per posta indesiderata e posta inviata in blocco**, in **Posta indesiderata** e **Alta probabilità di posta indesiderata**, selezionare l'operazione da effettuare per la posta elettronica in blocco e la posta indesiderata in arrivo. Per impostazione predefinita, l'opzione **Sposta i messaggi nella cartella Posta indesiderata** è selezionata. Gli altri valori possibili sono: 
    
      - **Elimina messaggio:** Elimina l'intero messaggio, inclusi tutti gli allegati. 
        
      - **Messaggio in quarantena:** Invia il messaggio in quarantena anziché ai destinatari previsti. Se si seleziona questa opzione, nella casella **Mantieni posta indesiderata per (giorni)** specificare il numero di giorni in cui verrà messo in quarantena il messaggio di posta indesiderata. (Verrà eliminato automaticamente dopo il tempo trascorso. Il valore predefinito è 15 giorni, che corrisponde al valore massimo. Il valore minimo è 1 giorno.<br/><br/>Suggerimento: per informazioni su come gli amministratori possono gestire i messaggi di posta elettronica che risiedono nella quarantena nell'interfaccia di amministrazione di Exchange, vedere [Quarantine](quarantine.md) and [Find and release Quarantined messages As an Administrator](find-and-release-quarantined-messages-as-an-administrator.md). > per informazioni su come configurare i messaggi di notifica di posta indesiderata da inviare agli utenti, vedere [configurare le notifiche di posta indesiderata dell'utente finale in EOP](configure-end-user-spam-notifications-in-eop.md) o [configurare le notifiche di posta indesiderata in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
      - **Spostare il messaggio nella cartella posta indesiderata:** Invia il messaggio alla cartella posta inDesiderata dei destinatari specificati. Questa è l'azione predefinita per entrambi i livelli di soglia di confidenza.<br/><br/>**IMPORTANTE: per i clienti di Exchange Online Protection (EOP): affinché questa azione funzioni con le cassette postali locali, è necessario configurare due regole di trasporto di Exchange nei server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere Verificare che la posta indesiderata [venga instradata alla cartella posta indesiderata di ogni utente](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).**
  
      - **Aggiungere X-header:** Invia il messaggio ai destinatari specificati, ma aggiunge il testo X-header all'intestazione del messaggio per identificare il messaggio come posta indesiderata. Se si utilizza questo testo come identificatore, è possibile creare le regole di posta in arrivo o utilizzare un dispositivo downstream per intervenire sul messaggio. Il testo X-header predefinito è **questo messaggio che sembra essere posta**indesiderata.<br/>È possibile personalizzare il testo X-Header utilizzando la casella di immissione di **testo Aggiungi questa x-header** . Se si Personalizza il testo X-header, tenere presente le condizioni seguenti: 
    
      - Se si specifica solo l'intestazione nell' \< *intestazione*\>del formato, in cui non sono presenti spazi all' \<interno dell' *intestazione*\>, i due punti verranno accodati al testo personalizzato, seguito dal testo predefinito. Ad esempio, se si specifica "This-is-My-Custom-Header", il testo X-header verrà visualizzato come "This-is-My-Custom-Header: questo messaggio sembra essere posta indesiderata."       
        
      - Se si includono spazi all'interno del testo dell'intestazione personalizzata oppure se si aggiungono i due punti (ad esempio "X questa è l'intestazione personalizzata" o "X-this-is-My-Custom-Header:"), il testo X-header ritorna al valore predefinito come "X-this-is-spam: questo messaggio sembra essere posta indesiderata."
    
      - Non è possibile specificare il testo dell'intestazione nel \< formato *intestazione*  \>:\<  *valore*  \>. Se si esegue questa operazione, entrambi i valori prima e dopo che i due punti verranno ignorati e il testo X-header predefinito verrà visualizzato invece: "X-this-is-spam: questo messaggio sembra essere posta indesiderata." 
      
      - Tenere presente che i messaggi con questo X-header potrebbero essere ancora spostati nella cartella posta inDesiderata della cassetta postale a causa della configurazione spazzatura delle cassette postali. È possibile modificare questa caratteristica disattivando questa funzionalità con Set-MailboxJunkEmailConfiguration.
        
      - **Anteporre la riga dell'oggetto al testo:** Invia il messaggio ai destinatari desiderati, ma antepone la riga dell'oggetto al testo specificato nella riga dell' **oggetto prefix con** la casella di immissione di testo. Se si utilizza questo testo come identificatore, è possibile creare regole per filtrare o instradare i messaggi in base alle esigenze. 
        
      - **Reindirizza il messaggio all'indirizzo di posta elettronica:** Invia il messaggio a un indirizzo di posta elettronica designato anziché ai destinatari previsti. Specificare l'indirizzo "redirect" nella casella **di input reindirizza a questo indirizzo di posta elettronica** .<br/><br/>Nota: per ulteriori informazioni sui livelli di probabilità di posta indesiderata, vedere [Spam Confidence levels](spam-confidence-levels.md). 
  
5. In **posta elettronica in blocco**, è possibile selezionare una soglia per trattare la posta elettronica in blocco come posta indesiderata. Questa soglia si basa sul livello di reclamo in blocco del messaggio. È possibile scegliere un'impostazione di soglia tra 1 e 9, dove 1 indica la maggior parte della posta elettronica come posta indesiderata e 9 consente di recapitare la maggior parte della posta elettronica in blocco. Il servizio esegue quindi l'azione configurata, ad esempio l'invio del messaggio alla cartella posta inDesiderata del destinatario. Vedere [i valori dei livelli](bulk-complaint-level-values.md) di reclamo in blocco e [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md) per ulteriori informazioni. 
    
6. Nella pagina **Elenchi contatti bloccati**, è possibile specificare voci, come mittenti o domini, che verranno sempre contrassegnati come Posta indesiderata. Il servizio applica l'azione di probabilità di posta indesiderata configurata alla posta elettronica che corrisponde a tali voci. 
    
      - Aggiungere i mittenti indesiderati all'elenco dei mittenti bloccati. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **OK** per tornare alla pagina degli **elenchi di indirizzi bloccati**. 
        
      - Aggiungere i domini indesiderati all'elenco dei domini bloccati. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere i domini che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **OK** per tornare alla pagina degli **elenchi di indirizzi bloccati**.<br/><br/>**Attenzione: se si bloccano domini di livello superiore, è probabile che la posta elettronica desiderata venga contrassegnata come posta indesiderata.** 
  
7. Nella pagina degli **elenchi di indirizzi consentiti**, è possibile specificare voci, come mittenti e domini, ai quali verranno sempre recapitati messaggi di posta elettronica nella Posta in arrivo. La posta elettronica proveniente da tali voci non viene elaborata dal filtro di protezione da posta indesiderata. 
    
      - Aggiungere i mittenti attendibili a Elenco mittenti consentiti. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera autorizzare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su OK per tornare alla pagina degli **elenchi elementi consentiti**. 
        
      - Aggiungere i domini attendibili a Elenco di domini consentiti. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere i domini che si desidera autorizzare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su OK per tornare alla pagina degli **elenchi elementi consentiti**.<br/><br/>**Attenzione: se si consentono domini di livello superiore, è probabile che la posta elettronica non desiderata venga recapitata in una cartella posta in arrivo.** 
  
8. Nella pagina **posta IndesideraTa internazionale** è possibile filtrare i messaggi di posta elettronica scritti in determinate lingue o inviati da determinati paesi o aree geografiche. È possibile configurare fino a 86 lingue diverse e 250 aree geografiche diverse. Il servizio applica l'azione configurata per la posta indesiderata con elevata attendibilità. 
    
9. Selezionare la casella di controllo **Filtra messaggi di posta elettronica scritti nelle lingue seguenti** per abilitare questa funzionalità. Fare ![clic su](media/ITPro-EAC-AddIcon.gif)icona Aggiungi, quindi nella finestra di dialogo di selezione fare le scelte (è supportata la selezione multipla). Ad esempio, se si sceglie di filtrare i messaggi scritti in arabo (AR) e il **messaggio** di quarantena è l'azione configurata per i messaggi di posta indesiderata con elevata sicurezza, tutti i messaggi scritti in arabo verranno messi in quarantena. Fare clic su **OK** per tornare al riquadro di **posta indesiderata internazionale** . 
    
10. Selezionare la casella di controllo **Filtra i messaggi di posta elettronica inviati dai seguenti paesi o aree geografiche** per abilitare questa funzionalità. Fare ![clic su](media/ITPro-EAC-AddIcon.gif)icona Aggiungi, quindi nella finestra di dialogo di selezione fare le scelte (è supportata la selezione multipla). Ad esempio, se si sceglie di filtrare tutti i messaggi inviati dall'Australia (AU) e il **messaggio** di quarantena è l'azione configurata per i messaggi di posta indesiderata con elevata attendibilità, tutti i messaggi inviati dall'Australia verranno messi in quarantena. Fare clic su **OK** per tornare al riquadro di **posta indesiderata internazionale** .<br/><br/>Per impostazione predefinita, se non sono selezionate opzioni di posta indesiderata interne, il servizio esegue il normale filtro di posta indesiderata sui messaggi inviati in tutte le lingue e da tutte le regioni. I messaggi vengono analizzati e se il messaggio viene rilevato come posta indesiderata o posta indesiderata ad alta probabilità, vengono applicate le azioni configurate. 
  
11. Nella pagina **Opzioni avanzate** , è possibile selezionare attivato ****, **disattivato**o **Verifica** per ogni opzione di filtro per la posta indesiderata avanzata. 
    
12. **In** I messaggi vengono filtrati attivamente in base alla regola associata a tale opzione. I messaggi vengono contrassegnati come posta indesiderata o saranno aumentati i punteggi di posta indesiderata, a seconda delle opzioni che si attivano. 
    
13. **Disattiva** Non viene compiuta alcuna azione sui messaggi che soddisfano i criteri del filtro di posta indesiderata. Per impostazione predefinita, tutte le opzioni sono disattivate. 
    
14. **Verifica** Non viene eseguita alcuna azione sui messaggi che soddisfano i criteri di filtro della posta indesiderata. Tuttavia, i messaggi possono essere contrassegnati aggiungendo un X-header prima che vengano recapitati al destinatario previsto. Questo X-header consente di sapere quale opzione ASF è stata confrontata. Se è stato specificato **test** per una qualsiasi delle opzioni avanzate, è possibile configurare le seguenti impostazioni della modalità di test da applicare quando viene effettuata una corrispondenza a un'opzione abilitata per i test: 
    
      - **Nessuno** Per impostazione predefinita, non vengono intraprese azioni in modalità test sul messaggio. 
        
      - **Aggiungere il testo X-header predefinito del test** Se si seleziona questa opzione, il messaggio viene inviato ai destinatari specificati, ma viene aggiunto anche un X-header speciale al messaggio per identificarlo come corrispondente a una specifica opzione di filtro per la posta indesiderata avanzata. 
        
      - **Inviare un messaggio Ccn a questo indirizzo** Selezionando questa opzione viene inviata una copia nascosta del messaggio all'indirizzo di posta elettronica specificato nella casella di input. <br/><br/>Per ulteriori informazioni sulle opzioni di filtro della posta indesiderata avanzate, incluse le descrizioni di ogni opzione e il testo X-header associato a ognuno, vedere [Opzioni avanzate](advanced-spam-filtering-asf-options.md)per il filtro della posta indesiderata. 
  
15. Solo per i criteri personalizzati, fare clic sulla voce **di menu applica a** e quindi creare una regola basata sulle condizioni per specificare gli utenti, i gruppi e i domini in cui applicare il criterio. Se sono univoci, è possibile creare più condizioni. 
    
      - Per selezionare gli utenti, selezionare **il destinatario**. Nella finestra di dialogo successiva, selezionare uno o più mittenti dalla propria società dall'elenco di selezione utenti, quindi fare clic su **Aggiungi**. Per aggiungere mittenti non presenti nell'elenco, digitare i relativi indirizzi di posta elettronica e quindi fare clic su **Controlla nomi**. In questa casella è inoltre possibile utilizzare i caratteri jolly per più indirizzi di posta elettronica (ad \* @ esempio, _DomainName_). Dopo aver effettuato le selezioni, fare clic su **OK** per tornare alla schermata principale. 
        
      - Per selezionare i gruppi, selezionare **il destinatario è un membro di**. Nella finestra di dialogo successiva selezionare o specificare i gruppi. Fare clic su **OK** per tornare alla schermata principale. 
        
      - Per selezionare i domini, selezionare **il dominio del destinatario**. Nella finestra di dialogo successiva aggiungere i domini. Fare clic su **OK** per tornare alla schermata principale.<br/><br/>È possibile creare eccezioni all'interno della regola. Ad esempio, è possibile filtrare i messaggi da tutti i domini ad eccezione di un determinato dominio. Fare clic su **Aggiungi eccezione**e quindi creare le condizioni di eccezione simili alla modalità di creazione delle altre condizioni.<br/><br/>Applicare un criterio di posta indesiderata a un gruppo è supportato solo per i **gruppi di sicurezza abilitati alla posta**. 
  
16. Fare clic su **salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri.

Il criterio predefinito non può essere disabilitato o eliminato e i criteri personalizzati hanno sempre la precedenza sul criterio predefinito. Per i criteri personalizzati, è possibile selezionare o deselezionare le caselle di controllo nella colonna **Enabled** per abilitarli o disabilitarli. Per impostazione predefinita, tutti i criteri sono abilitati. Per eliminare un criterio personalizzato, selezionare il criterio, fare clic ![sull'icona](media/ITPro-EAC-DeleteIcon.gif) **** Elimina icona Elimina e quindi confermare che si desidera eliminare il criterio.

> [!TIP]
>  È possibile modificare la priorità (ordine di esecuzione) dei criteri personalizzati facendo clic sull' ![icona](media/ITPro-EAC-UpArrowIcon.gif) freccia su verso l'alto ![freccia su e](media/ITPro-EAC-DownArrowIcon.gif) freccia giù freccia giù. Il criterio con **priorità** **0** verrà eseguito per primo, seguito da **1**, **2**e così via. 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>Utilizzo di PowerShell per la configurazione dei criteri di filtro di protezione dalla posta indesiderata

È inoltre possibile configurare e applicare i criteri di filtro della posta indesiderata in PowerShell. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [connessione a Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) Visualizzare le impostazioni di filtro di protezione dalla posta indesiderata. 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) Modificare le impostazioni di filtro di protezione dalla posta indesiderata. 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) Creare un nuovo criterio di filtro di protezione dalla posta indesiderata personalizzato. 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) Eliminare un criterio di filtro di protezione dalla posta indesiderata personalizzato. 
    
Per applicare un criterio di filtro di protezione dalla posta indesiderata personalizzato a utenti, gruppi e/o domini, utilizzare il cmdlet [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) (per creare una nuova regola di filtro che possa essere applicata ai criteri personalizzati) oppure il cmdlet [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) (per modificare una regola di filtro esistente che possa essere applicata ai criteri personalizzati). Utilizzare il cmdlet [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) oppure il cmdlet [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) per abilitare o disabilitare la regola applicata al criterio. 
  
## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per assicurarsi di aver identificato correttamente la posta indesiderata, è possibile inviare un messaggio GTUBE tramite il servizio. Come il file di test antivirus EICAR, GTUBE fornisce un test tramite il quale è possibile verificare se il servizio individua la posta indesiderata in arrivo. Un messaggio GTUBE viene sempre identificato come posta indesiderata e le azioni eseguite sul messaggio potrebbero corrispondere alle impostazioni configurate.
  
Includere il seguente testo GTUBE in un messaggio di posta o in una singola riga, senza spazi o interruzioni di riga:
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>Regolazione dei criteri del filtro della posta indesiderata per impedire falsi positivi e falsi negativi

Se si desidera intraprendere un approccio aggressivo, è possibile attivare opzioni avanzate per il filtro della posta indesiderata. Per informazioni sulle impostazioni relative alla posta indesiderata per un'intera organizzazione, consultare [Evitare che la posta elettronica venga erroneamente contrassegnata come posta indesiderata tramite un elenco di indirizzi attendibili o altre tecniche](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [Bloccare la posta indesiderata con il filtro di posta indesiderata di Office 365 per prevenire il problema dei falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225). Questi articoli sono utili se si svolge il ruolo di amministratore e si desidera impedire la visualizzazione di falsi negativi o di falsi positivi.
   
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection6"> </a>

[Configurare i criteri di filtro delle connessioni](configure-the-connection-filter-policy.md)
  
[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Quarantena](quarantine.md)
  
[Evitare che la posta elettronica venga erroneamente contrassegnata come posta indesiderata tramite un elenco di indirizzi attendibili o altre tecniche](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

