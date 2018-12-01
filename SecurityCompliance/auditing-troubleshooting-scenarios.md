---
title: Il Registro di controllo di Office 365 per risolvere i problemi di scenari comuni di ricerca
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
description: È possibile utilizzare lo strumento di ricerca di Office 365 audit log che consentono di risolvere i problemi comuni, ad esempio un'analisi di un account compromesso o che configurare l'inoltro di posta elettronica per una cassetta postale di individuazione.
ms.openlocfilehash: 930e311712e49214ca2a51e256c29e5f959deab8
ms.sourcegitcommit: c34f1a0d560117153fc9a7b8da8994bc6fc53791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2018
ms.locfileid: "27123899"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a>Il Registro di controllo di Office 365 per risolvere i problemi di scenari comuni di ricerca

In questo articolo viene descritto come utilizzare lo strumento di ricerca di Office 365 audit log per risolvere i problemi comuni scenari di supporto. Questa condizione utilizzando il Registro di controllo:

- Trovare l'indirizzo IP del computer utilizzato per accedere a un account compromesso
- Determinare chi configurare l'inoltro di posta elettronica per una cassetta postale di
- Determinare se un utente di eliminata gli elementi di posta elettronica nella cassetta postale
- Determinare se un utente di creata una regola di posta in arrivo

## <a name="using-the-office-365-audit-log-search-tool"></a>Utilizzando lo strumento di ricerca di Office 365 audit log

Ognuno degli scenari di risoluzione dei problemi descritti in questo articolo si basano sui utilizzando lo strumento di ricerca del Registro di controllo nel centro conformità protezione di Office 365. In questa sezione sono elencate le autorizzazioni necessarie per la ricerca nel Registro di controllo e vengono descritti i passaggi necessari per accedere ed eseguire ricerche del Registro di controllo. Nella sezione ogni scenario vengono fornite indicazioni specifiche su come configurare una query di ricerca del Registro di controllo e sugli aspetti da considerare informazioni dettagliate nei record di verifica che soddisfano i criteri di ricerca.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Autorizzazioni necessarie per utilizzare lo strumento di ricerca del Registro di controllo

È necessario disporre del ruolo registri di controllo View-Only o i registri di controllo di Exchange Online per la ricerca nel Registro di controllo di Office 365. Per impostazione predefinita, questi ruoli vengono assegnati a gruppi di ruolo Gestione della conformità e la gestione dell'organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [gruppi di ruoli di gestione in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

### <a name="running-audit-log-searches"></a>Eseguire ricerche del Registro di controllo

In questa sezione vengono descritti i concetti di base per creare ed eseguire ricerche del Registro di controllo. Utilizzare queste istruzioni come punto di partenza per ogni scenario di risoluzione dei problemi in questo articolo. Per ulteriori informazioni dettagliate, vedere [ricerca il controllo di accesso nel centro conformità protezione di Office 365 ](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Passare a [https://protection.office.com](https://protection.office.com).
  
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.

3. Nel riquadro sinistro della sicurezza & centro conformità, fare clic su **ricerca e indagini** > **ricerca dei registri di controllo**.
    
    Verrà visualizzata la pagina di **ricerca dei registri di controllo** . 
    
    ![Configurare criteri e quindi scegliere Cerca per eseguire la ricerca](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. È possibile configurare i seguenti criteri di ricerca. Si noti che ogni scenario di risoluzione dei problemi in questo articolo verrà consigliabile istruzioni specifiche su come configurare questi campi.
    
    r. **delle attività** - scegliere l'elenco a discesa per visualizzare le attività che è possibile cercare. Dopo aver eseguito la ricerca, vengono visualizzati solo i record di verifica per le attività selezionate. Selezionare **Mostra i risultati per tutte le attività** visualizzerà i risultati per tutte le attività che soddisfano i criteri di ricerca. È inoltre necessario lasciare il campo vuoto in alcuni scenari di risoluzione dei problemi.
    
    b. **Data di inizio** e **Data fine** - selezionare un intervallo di data e ora per visualizzare gli eventi che si sono verificati durante questo periodo. Ultimi sette giorni sono selezionati per impostazione predefinita. Data e ora sono disponibili in formato ora UTC (Coordinated Universal Time). L'intervallo di date massimo che è possibile specificare è 90 giorni.

    c. **gli utenti** , fare clic in questa casella e quindi selezionare uno o più utenti per visualizzare Criteri di ricerca di risultati per. Nell'elenco dei risultati vengono visualizzati i record di controllo per l'attività selezionata eseguite dagli utenti che selezionare questa casella. Lasciare vuoto questo per restituire le voci per tutti gli utenti (e gli account di servizio) nella propria organizzazione.
    
    d. **File, cartelle o del sito** - digitare alcuni o tutti un nome file o una cartella per cercare le attività relative al file della cartella che contiene la parola chiave specificata. È inoltre possibile specificare un URL di un file o cartella. Se si utilizza un URL, assicurarsi che il tipo di percorso URL completo o se si digita solo una parte dell'URL, non includere spazi o caratteri speciali. Lasciare vuoto questo per restituire le voci per tutti i file e cartelle all'interno dell'organizzazione. Si noti che questo campo viene lasciato vuoto in tutti gli scenari di risoluzione dei problemi in questo articolo.
    
5. Fare clic su **ricerca** per eseguire la ricerca utilizzando i criteri di ricerca. 
    
    I risultati della ricerca sono stati caricati e dopo pochi secondi vengono visualizzati nell'area **risultati** della pagina di **ricerca dei registri di controllo** . Ogni le sezioni seguenti verranno vengono fornite informazioni su aspetti da considerare per lo scenario di risoluzione dei problemi specifico.

    Per ulteriori informazioni sulla visualizzazione, il filtro o l'esportazione dei risultati di ricerca di log di controllo, vedere:

    - [Visualizza risultati di ricerca](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtrare i risultati di ricerca](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Esportare i risultati della ricerca](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Ricerca dell'indirizzo IP del computer utilizzato per accedere a un account compromesso

L'indirizzo IP corrispondente a un'attività eseguita da un utente è incluso nella maggior parte dei record di verifica. Informazioni sui client utilizzato sono anche incluso nel controllo record.

Di seguito viene descritto come configurare una query di ricerca di registro di controllo per questo scenario:

**Attività** - se rilevanti per il case, selezionare un'attività specifica da cercare. Per la risoluzione dei problemi compromesso gli account utilizzati per valutare la scelta dell'attività **utente l'accesso alla cassetta postale** tra **le attività di cassette postali di Exchange**. Restituisce i record di controllo che mostra l'indirizzo IP che è stata utilizzare durante l'accesso alla cassetta postale. In caso contrario, lasciare vuota la per restituire i record di controllo per tutte le attività. 

> [!TIP]
> Se si lascia vuoto questo campo restituirà **UserLoggedIn** attività, ovvero un'attività di Azure Active Directory che indica che un utente ha eseguito l'accesso a un account utente di Office 365. Utilizzare il filtro nei risultati della ricerca per visualizzare i record di verifica **UserLoggedIn** .

**Data di inizio** e **Data fine** - selezionare un intervallo di date valide per le indagini.

**Gli utenti** - se si sta analisi di un account compromesso, selezionare l'utente il cui account è stata danneggiata. Restituisce i record di controllo per le attività eseguite dall'account utente.

**File, cartelle o del sito** - lasciare vuoto questo campo.

Dopo aver eseguito la ricerca, l'indirizzo IP per ogni attività viene visualizzato nella colonna **indirizzo IP** nei risultati della ricerca. Fare clic sul record nei risultati della ricerca per visualizzare informazioni più dettagliate sulla pagina comparsa.

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a>Determinare chi configurare l'inoltro di posta elettronica per una cassetta postale di

Quando l'inoltro della posta è configurato per una cassetta postale, messaggi di posta elettronica inviati alla cassetta postale vengono inviati a un'altra cassetta postale. I messaggi possono essere inoltrati agli utenti interni o esterni all'organizzazione. Quando l'inoltro della posta è impostato su una cassetta postale, il cmdlet di Exchange Online sottostante utilizzato è **Set-Mailbox**.

Di seguito viene descritto come configurare una query di ricerca di registro di controllo per questo scenario:

**Attività** - lasciare vuoto in modo che la ricerca restituisce record di controllo per tutte le attività in questo campo. Questa operazione è necessaria per restituire una qualsiasi controllo record correlati al cmdlet **Set-Mailbox** .

**Data di inizio** e **Data fine** - selezionare un intervallo di date valide per le indagini.

**Gli utenti** , a meno che non si sta analisi di un messaggio di posta elettronica inoltro problema per un utente specifico, lasciare vuoto questo campo. Ciò consentirà di identificare se inoltro della posta è stato configurato per alcun utente.

**File, cartelle o del sito** - lasciare vuoto questo campo.

Dopo aver eseguito la ricerca, fare clic su **filtrare i risultati** nella pagina dei risultati della ricerca. Nella casella sotto l'intestazione di colonna **attività** digitare **Set-Mailbox** in modo che vengano visualizzati solo i record di controllo relativi al cmdlet **Set-Mailbox** .

![Filtrando i risultati di una ricerca dei registri di controllo](media/emailforwarding1.png)

A questo punto, è necessario esaminare i dettagli di ogni record di controllo per determinare se l'attività è correlato all'inoltro della posta elettronica. Fare clic sul record di controllo per visualizzare la pagina di comparsa **Dettagli** e quindi fare clic su **ulteriori informazioni**. I seguente cattura di schermata e descrizioni argomenti di rilievo di informazioni che indicano l'inoltro della posta è state impostate sulla cassetta postale.

![Informazioni dettagliate dal record di controllo](media/emailforwarding2.png)

r. nel campo **ObjectId** , l'alias della cassetta postale di inoltro della posta elettronica è stata impostata su viene visualizzato. Questa cassetta postale viene visualizzata anche nella colonna **elemento** nella pagina dei risultati della ricerca.

b. nel campo **parametri** , il valore *ForwardingSmtpAddress* indica che è stata impostata Inoltra posta elettronica della cassetta postale. In questo esempio, inoltro della posta per l'indirizzo di posta elettronica mike@contoso.com, che è all'esterno dell'organizzazione alpinehouse.onmicrosoft.com.

c. il valore *True* per il parametro *DeliverToMailboxAndForward* indica che una copia dei messaggi recapitati sarad@alpinehouse.onmicrosoft.com *e* viene inoltrata all'indirizzo specificato da *ForwardingSmtpAddress *parametro, che in questo esempio viene mike@contoso.com. Se il valore del parametro *DeliverToMailboxAndForward* è impostato su *False*, posta elettronica viene inoltrata solo all'indirizzo specificato dal parametro *ForwardingSmtpAddress* . Non viene recapitato alla cassetta postale specificata nel campo **ObjectId** .

d. il campo **ID utente** è indicato l'utente che ha imposta l'inoltro di posta elettronica della cassetta postale specificata nel campo campo **ObjectId** . L'utente viene visualizzato anche nella colonna **utente** nella pagina dei risultati della ricerca. In questo caso, si ritiene che il proprietario della cassetta postale di imposta l'inoltro di posta elettronica nella propria cassetta postale.

Se ritiene che inoltro di posta elettronica non è necessario impostare la cassetta postale, è possibile rimuovere eseguendo il comando seguente in Exchange Online PowerShell:

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Vedere l'articolo [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) per ulteriori informazioni sui parametri correlati all'inoltro della posta elettronica.

## <a name="determining-if-a-user-deleted-email-items"></a>Determinare se un utente ha eliminato gli elementi di posta elettronica

Prima dell'eliminazione di record del Registro di controllo sugli elementi di posta elettronica vengono salvati nel Registro di controllo di Office 365, il controllo della cassetta postale deve essere abilitata per ciascuna cassetta postale utente nell'organizzazione. Inoltre, le azioni di cassette postali SoftDelete e HardDelete devono essere attivati per il controllo. Per ulteriori informazioni, vedere [abilitare il controllo in Office 365](enable-mailbox-auditing.md). Se il controllo delle cassette postali è già abilitato per gli utenti, utilizzare la procedura seguente per cercare il Registro di controllo per eventi relativi agli elementi di posta elettronica eliminati.

Di seguito viene descritto come configurare una query di ricerca di registro di controllo per questo scenario:

**Attività** - sotto **le attività di cassette postali di Exchange**, selezionare una o entrambe le attività seguenti:

- **I messaggi eliminati dalla cartella Posta eliminata** - questa attività corrisponde alla cassetta postale **SoftDelete** controllo azione. Questa attività viene registrata anche quando viene eliminato definitivamente un elemento selezionandolo e premendo **MAIUSC + CANC**. Dopo che un elemento viene eliminato definitivamente, l'utente recuperarla fino alla scadenza del periodo di mantenimento elementi eliminati.

- **Purged messaggi dalla cassetta postale** - questa attività corrisponde alla cassetta postale **HardDelete** controllo azione. Viene registrata quando un utente elimina un elemento dalla cartella elementi ripristinabili. Gli amministratori possono usare lo strumento di ricerca del contenuto nel centro conformità protezione di Office 365 per cercare e gli elementi eliminato recupero fino alla scadenza del periodo di mantenimento elementi eliminati o se più cassette postali dell'utente sono in attesa.

**Data di inizio** e **Data fine** - selezionare un intervallo di date valide per le indagini.

**Gli utenti** - se si seleziona un utente in questo campo, lo strumento di controllo Registro ricerca verrà restituiti i record di controllo per gli elementi di posta elettronica che sono stati eliminati (SoftDeleted o HardDeleted) dall'utente specificato. In alcuni casi, l'utente che consente di eliminare un messaggio di posta elettronica potrebbe non essere proprietario della cassetta postale.

**File, cartelle o del sito** - lasciare vuoto questo campo.

Dopo aver eseguito la ricerca, è possibile filtrare i risultati della ricerca per visualizzare i record di verifica per gli elementi eliminate o per disco rigido eliminata. Fare clic sul record di controllo per visualizzare la pagina di comparsa **Dettagli** e quindi fare clic su **ulteriori informazioni**. Ulteriori informazioni sull'elemento eliminato, ad esempio la riga dell'oggetto e la posizione dell'elemento quando è stata eliminata, viene visualizzate nel campo **AffectedItems** . Le schermate seguente mostra un esempio del campo **AffectedItems** da un elemento eliminate e una voce eliminata definitivamente.

**Esempio del campo AffectedItems per elemento eliminate**

![Record di controllo per l'elemento eliminate](media/softdeleteditem.png)

**Esempio del campo AffectedItems per elemento rigido eliminati**

![Record di controllo per l'elemento di posta elettronica eliminata definitivamente](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a>Ripristino degli elementi di posta elettronica eliminati

Gli utenti possono recuperare elementi eliminati reversibile se non è scaduto il periodo di conservazione degli elementi eliminati. In Exchange Online, il periodo di conservazione degli elementi eliminato predefinito è 14 giorni, ma gli amministratori possono aumentare questa impostazione per un massimo di 30 giorni. Agli utenti di punto di [ripristino degli elementi eliminati o un messaggio di posta elettronica in Outlook Web App](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) articolo per istruzioni dettagliate sul ripristino degli elementi eliminati.

Come indicato in precedenza, gli amministratori potrebbero essere in grado di recuperare elementi eliminati rigido se non è scaduto il periodo di mantenimento elementi eliminati o se la cassetta postale è in attesa, nel qual caso gli elementi vengono mantenuti finché non scade la durata dell'attesa. Quando si esegue una ricerca di contenuto, eliminate ed eliminata definitivamente gli elementi nella cartella elementi ripristinabili vengono restituiti nei risultati della ricerca se corrispondono alla query di ricerca. Per ulteriori informazioni su come eseguire ricerche di contenuto, vedere [Il contenuto di ricerca in Office 365](content-search.md).

> [!TIP]
> Per cercare gli elementi di posta elettronica eliminati, cercare tutto o parte della riga dell'oggetto che viene visualizzata nel campo **AffectedItems** del record di controllo.

## <a name="determining-if-a-user-created-an-inbox-rule"></a>Determinare se un utente creato una regola di posta in arrivo

Quando gli utenti di creare una regola di posta in arrivo per la cassetta postale di Exchange Online, un record di controllo corrispondente viene salvato nel Registro di controllo. Per ulteriori informazioni sulle regole della posta in arrivo, vedere:

- [Utilizzare le regole posta in arrivo di Outlook sul web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Gestire i messaggi di posta elettronica in Outlook utilizzando regole](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Di seguito viene descritto come configurare una query di ricerca di registro di controllo per questo scenario:

**Attività** - sotto **le attività di cassette postali di Exchange**, selezionare **Create a New-InboxRule/modificare/abilitare/disabilitare la regola posta in arrivo**.

**Data di inizio** e **Data fine** - selezionare un intervallo di date valide per le indagini.

**Gli utenti** , a meno che non si sta analisi di un utente specifico, lasciare vuoto questo campo. Ciò consentirà di identificare le nuove regole posta in arrivo impostare da qualsiasi utente.

**File, cartelle o del sito** - lasciare vuoto questo campo.

Dopo aver eseguito la ricerca, i record di controllo per questa attività vengono visualizzati nei risultati della ricerca. Fare clic su un record di controllo per visualizzare la pagina di comparsa **Dettagli** e quindi fare clic su **ulteriori informazioni**. Informazioni sulle impostazioni della regola posta in arrivo vengono visualizzati nel campo di **parametri** . Cattura di schermata e descrizioni seguenti vengono evidenziate le informazioni sulle regole della posta in arrivo.

![Record di controllo per la nuova regola di posta in arrivo](media/NewInboxRuleRecord.png)

r. nel campo **ObjectId** , viene visualizzato il nome completo della regola di posta in arrivo. Questo nome include l'alias della cassetta postale dell'utente (ad esempio SaraD) e il nome della regola di posta in arrivo (ad esempio, "spostare i messaggi da admin").

b. nel campo **parametri** , viene visualizzata la condizione della regola di posta in arrivo. In questo esempio la condizione viene specificata dal parametro *da* . Il valore definito per il parametro *da* indica che la regola di posta in arrivo agisce sulla posta elettronica inviato da admin@alpinehouse.onmicrosoft.com. Per un elenco completo dei parametri che possono essere utilizzati per definire le condizioni delle regole posta in arrivo, vedere l'articolo [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) .

c. il parametro *MoveToFolder* specifica l'azione per la regola di posta in arrivo. In questo esempio, i messaggi ricevuti da admin@alpinehouse.onmicrosoft.com vengono spostati nella cartella denominata *AdminSearch*. Inoltre, vedere l'articolo di [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) per un elenco completo di parametri che è possibile utilizzare per definire l'azione di una regola di posta in arrivo.

d. il campo **ID utente** di indicare l'utente che ha creato la regola di posta in arrivo specificata nel campo **ObjectId** . L'utente viene visualizzato anche nella colonna **utente** nella pagina dei risultati della ricerca.