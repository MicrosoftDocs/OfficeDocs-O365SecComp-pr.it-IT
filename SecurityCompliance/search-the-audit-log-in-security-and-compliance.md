---
title: Eseguire una ricerca nel log di controllo nel centro sicurezza e conformità di &
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: "Utilizzare il Centro sicurezza & Compliance per eseguire ricerche nel log di controllo unificato per visualizzare le attività dell'utente e dell'amministratore nell'organizzazione di Office 365. "
ms.openlocfilehash: cb44dd3d7c87928b325a72e783feea85e252dc49
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547991"
---
# <a name="search-the-audit-log-in-the-security--compliance-center"></a>Eseguire una ricerca nel log di controllo nel centro sicurezza e conformità di &

## <a name="introduction"></a>Introduzione

È necessario individuare se un utente ha visualizzato un documento specifico o ha eliminato un elemento dalla propria cassetta postale? In caso affermativo, è possibile utilizzare il centro &amp; sicurezza e conformità di Office 365 per eseguire una ricerca nel registro di controllo unificato per visualizzare le attività dell'utente e dell'amministratore nell'organizzazione di Office 365. Perché un log di controllo unificato? Poiché è possibile cercare i seguenti tipi di attività di utente e di amministratore in Office 365:
  
- Attività degli utenti in SharePoint Online e OneDrive for business
    
- Attività degli utenti in Exchange Online (registrazione di controllo delle cassette postali di Exchange)
    
    > [!IMPORTANT]
    > La registrazione di controllo delle cassette postali deve essere attivata per ogni cassetta postale utente prima che l'attività dell'utente in Exchange Online venga registrata. Per ulteriori informazioni, vedere [abilitare il controllo delle cassette postali in Office 365](enable-mailbox-auditing.md).
  
- Attività di amministrazione in SharePoint Online
    
- Attività di amministratore in Azure Active Directory (servizio directory per Office 365)
    
- Attività di amministratore in Exchange Online (registrazione di controllo dell'amministratore di Exchange)
    
- Attività di utenti e amministratori in Sway
    
- attività di eDiscovery nel centro sicurezza e conformità
    
- Attività di utenti e amministratori in Power BI
    
- Attività di utenti e amministratori in Microsoft Teams

- Attività di utenti e amministratori in Dynamics 365
    
- Attività di utenti e amministratori in Yammer
 
- Attività di utenti e amministratori in Microsoft Flow
    
- Attività di utenti e amministratori in Microsoft Stream

- Attività di Analyst e di amministrazione nell'analisi del luogo di lavoro Microsoft

- Attività di utenti e amministratori in Microsoft PowerApps
    
   
## <a name="before-you-begin"></a>Informazioni preliminari

Assicurarsi di leggere gli elementi seguenti prima di iniziare la ricerca nel registro di controllo di Office 365.
  
- L'utente (o un altro amministratore) deve prima attivare la registrazione di controllo prima di iniziare a eseguire la ricerca nel registro di controllo di Office 365. Per attivarlo, fare clic su **Avvia registrazione attività utente e amministratore** nella pagina di **ricerca del registro di controllo** nel centro sicurezza & Compliance. Se questo collegamento non è visualizzato, il controllo è già stato attivato per l'organizzazione. Dopo averla attivata, viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio d'ore dopo il completamento della preparazione. È necessario eseguire questa operazione una sola volta. 
    
    > [!NOTE]
    > Per impostazione predefinita, è in corso l'attivazione del controllo. Fino a quel momento, è possibile attivarlo come descritto in precedenza. 
  
- È necessario essere assegnati al ruolo di controllo di sola visualizzazione o ai registri di controllo in Exchange Online per eseguire una ricerca nel registro di controllo di Office 365. Per impostazione predefinita, questi ruoli sono assegnati ai gruppi di ruoli Gestione conformità e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Si noti che gli amministratori globali di Office 365 e Microsoft 365 vengono aggiunti automaticamente come membri del gruppo di ruoli Gestione organizzazione in Exchange Online. Per concedere a un utente la possibilità di eseguire ricerche nel log di controllo di Office 365 con il livello minimo di privilegi, è possibile creare un gruppo di ruoli personalizzato in Exchange Online, aggiungere i registri di controllo o i registri di controllo di sola visualizzazione e quindi aggiungere l'utente come membro del nuovo gruppo di ruoli. Per ulteriori informazioni, vedere [gestire i gruppi di ruoli in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).
    
    > [!IMPORTANT]
    > Se si assegna un utente ai registri di controllo di sola visualizzazione o ai registri di controllo nella pagina **autorizzazioni** nel centro conformità di sicurezza &, non sarà possibile eseguire la ricerca nel registro di controllo di Office 365. È necessario assegnare le autorizzazioni in Exchange Online. Ciò è dovuto al fatto che il cmdlet sottostante utilizzato per eseguire la ricerca nel registro di controllo è un cmdlet di Exchange Online. 
  
- Quando un'attività controllata viene eseguita da un utente o da un amministratore, viene generato un record di controllo che viene memorizzato nel registro di controllo di Office 365 per l'organizzazione. Il periodo di tempo in cui un record di controllo viene mantenuto (e ricercabile nel log di controllo) dipende dall'abbonamento a Office 365 e in particolare dal tipo di licenza assegnato a un utente specifico.

     - **Office 365 E3** -i record di controllo vengono conservati per 90 giorni. Questo significa che è possibile eseguire una ricerca nel registro di controllo per le attività eseguite negli ultimi 90 giorni.

     - I record di controllo di **Office 365 E5** vengono conservati anche per 90 giorni. La conservazione dei record di controllo per un anno può essere eventualmente disponibile per gli utenti e gli utenti di E5 con una licenza E3 e una licenza per il componente aggiuntivo per la conformità avanzata di Office 365.

        > [!NOTE]
        > Il programma di anteprima privata per il periodo di conservazione di un anno per i record di controllo per le organizzazioni E5 (o per gli utenti delle organizzazioni E3 che dispongono di licenze per i componenti aggiuntivi per la conformità avanzato) è chiuso alla nuova registrazione. Questo articolo verrà aggiornato quando il periodo di conservazione di un anno è disponibile in anteprima pubblica o rilasciato per la disponibilità generale.

- Se si desidera disattivare la ricerca del registro di controllo in Office 365 per l'organizzazione, è possibile eseguire il comando riportato di seguito in Remote PowerShell connesso all'organizzazione Exchange Online:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Per abilitare di nuovo la ricerca di controllo, è possibile eseguire il comando seguente in PowerShell di Exchange Online:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

    Per ulteriori informazioni, vedere [disattivazione della ricerca del registro di controllo in Office 365](turn-audit-log-search-on-or-off.md).
    
- Come indicato in precedenza, il cmdlet sottostante utilizzato per eseguire la ricerca nel log di controllo è un cmdlet di Exchange Online, ovvero **Search-UnifiedAuditLog**. Questo significa che è possibile utilizzare questo cmdlet per eseguire una ricerca nel registro di controllo di Office 365 anziché utilizzare la pagina di **ricerca del registro di controllo** nel centro sicurezza e conformità di &. È necessario eseguire questo cmdlet in Remote PowerShell connesso all'organizzazione Exchange Online. Per ulteriori informazioni, vedere [Search-UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776).
    
- Se si desidera scaricare dati a livello di programmazione dal registro di controllo di Office 365, è consigliabile utilizzare l'API di attività di gestione di Office 365 anziché utilizzare uno script di PowerShell. L'API di attività di gestione di Office 365 è un servizio Web REST che è possibile utilizzare per sviluppare soluzioni di monitoraggio di operazioni, sicurezza e conformità per l'organizzazione. Per ulteriori informazioni, vedere Guida di [riferimento all'API di attività di gestione di Office 365](https://go.microsoft.com/fwlink/?linkid=852309).
    
- Possono essere necessari fino a 30 minuti o fino a 24 ore dopo che si è verificato un evento per la voce del registro di controllo corrispondente da visualizzare nei risultati della ricerca. Nella tabella seguente vengono illustrati i tempi necessari per i diversi servizi di Office 365.
    
    |**Servizio Office 365**|**30 minuti**|**24 ore**|
    |:-----|:-----|:-----|
    |Protezione avanzata dalle minacce e intelligence delle minacce  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| |
    |Azure Active Directory (eventi di accesso utente)  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |Azure Active Directory (eventi di amministrazione)  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) |
    |Prevenzione della perdita di dati  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       <br/>| |
    |Dynamics 365 CRM <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |eDiscovery  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Exchange Online  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Microsoft Flow  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Project  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Stream  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Teams  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Power BI  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Centro sicurezza e conformità  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |SharePoint Online e OneDrive for Business  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Sway  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |Workplace Analytics<br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> || 
    |Yammer  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
- Azure Active Directory (Azure AD) è il servizio directory per Office 365. Il registro di controllo unificato contiene le attività relative a utenti, gruppi, applicazioni, domini e directory eseguite nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure. Per un elenco completo degli eventi di Azure AD, vedere [eventi del rapporto di controllo di Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).
    
- I log di controllo di Exchange Online sono costituiti da due tipi di eventi: eventi di amministrazione di Exchange (azioni eseguite dagli amministratori) e eventi delle cassette postali (azioni eseguite dagli utenti nelle cassette postali). Si noti che il controllo delle cassette postali non è abilitato per impostazione predefinita. Deve essere abilitata per ogni cassetta postale utente prima che gli eventi della cassetta postale possano essere cercati nel registro di controllo di Office 365. Per ulteriori informazioni sul controllo delle cassette postali e sulle azioni di controllo delle cassette postali registrate, vedere [Enable Mailbox auditing in Office 365](enable-mailbox-auditing.md).
    
- La registrazione di controllo per Power BI non è abilitata per impostazione predefinita. Per cercare le attività di Power BI nel log di controllo di Office 365, è necessario abilitare il controllo nel portale di amministrazione di Power BI. Per istruzioni, vedere la sezione relativa ai registri di controllo in [Power Bi Admin Portal](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).
    
    
## <a name="search-the-audit-log"></a>Eseguire ricerche nel log di controllo

Ecco la procedura per eseguire una ricerca nel log di controllo in Office 365.
  
[Passaggio 1: eseguire una ricerca nel registro di controllo](#step-1-run-an-audit-log-search)
  
[Passaggio 2: visualizzazione dei risultati della ricerca](#step-2-view-the-search-results)

[Passaggio 3: filtrare i risultati della ricerca](#step-3-filter-the-search-results)

[Passaggio 4: esportare i risultati della ricerca in un file](#step-4-export-the-search-results-to-a-file)
  
### <a name="step-1-run-an-audit-log-search"></a>Passaggio 1: eseguire una ricerca nel registro di controllo

1. Passare a [https://protection.office.com](https://protection.office.com).
    
    > [!TIP]
    > Utilizzare una sessione di esplorazione privata (non una sessione regolare) per accedere al centro sicurezza & Compliance perché in questo modo si eviterà che vengano utilizzate le credenziali a cui si è connessi. Per aprire una sessione di InPrivate Browsing in Internet Explorer o Microsoft Edge, è sufficiente premere CTRL + MAIUSC + P. Per aprire una sessione di esplorazione privata in Google Chrome (denominata finestra in incognito), premere CTRL + MAIUSC + N. 
  
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro del Centro sicurezza & Compliance fare clic su **Cerca**e quindi su **Ricerca log di controllo**.
    
    Viene visualizzata la pagina di **ricerca del registro di controllo** . 
    
    ![Configurare i criteri e quindi fare clic su Cerca per eseguire il report](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
    > [!NOTE]
    > Prima di poter eseguire una ricerca nel registro di controllo, è necessario prima di tutto abilitare la registrazione di controllo. Se viene visualizzato il collegamento **Inizia registrazione utente e attività amministratore** , fare clic su di esso per attivare il controllo. Se questo collegamento non è visualizzato, il controllo è già stato attivato per l'organizzazione. 
  
4. Configurare i seguenti criteri di ricerca:
    
    un. **Attività** Fare clic sull'elenco a discesa per visualizzare le attività di cui è possibile eseguire la ricerca. Le attività di utenti e amministratori sono organizzate in gruppi di attività correlate. È possibile selezionare attività specifiche oppure fare clic sul nome del gruppo di attività per selezionare tutte le attività del gruppo. È inoltre possibile fare clic su un'attività selezionata per cancellare la selezione. Dopo aver eseguito la ricerca, vengono visualizzate solo le voci del registro di controllo per le attività selezionate. Se si seleziona **Mostra risultati per tutte le attività** , verranno visualizzati i risultati di tutte le attività eseguite dall'utente o dal gruppo di utenti selezionato. 
    
    Nel registro di controllo di Office 365 sono registrate più di 100 utenti e attività amministrative. Fare clic sulla scheda **attività controllate** nell'argomento di questo articolo per visualizzare le descrizioni di ogni attività in ognuno dei diversi servizi di Office 365. 
    
    b. Data di **inizio** e **Data di fine** gli ultimi sette giorni sono selezionati per impostazione predefinita. Selezionare un intervallo di data e ora per visualizzare gli eventi che si sono verificati entro quel periodo. La data e l'ora vengono visualizzate in formato UTC (Coordinated Universal Time). L'intervallo di date massimo che è possibile specificare è 90 giorni. Se l'intervallo di date selezionato è maggiore di 90 giorni, verrà visualizzato un messaggio di errore. 
    
    > [!TIP]
    > Se si utilizza l'intervallo di date massimo di 90 giorni, selezionare l'ora corrente per la **Data di inizio**. In caso contrario, verrà visualizzato un messaggio di errore che indica che la data di inizio è precedente alla data di fine. Se il controllo è stato attivato negli ultimi 90 giorni, l'intervallo di date massimo non può essere avviato prima della data di attivazione del controllo. 
  
    c. **Utenti** Fare clic in questa casella e quindi selezionare uno o più utenti per visualizzare i risultati della ricerca. Le voci del registro di controllo per l'attività selezionata eseguita dagli utenti selezionati in questa casella vengono visualizzate nell'elenco dei risultati. Lasciare vuota questa casella per restituire le voci per tutti gli utenti (e gli account di servizio) nell'organizzazione. 
    
    d. **File, cartella o sito** Digitare il nome di un file o di una cartella per la ricerca di attività correlate al file della cartella che contiene la parola chiave specificata. È inoltre possibile specificare un URL di un file o di una cartella. Se si utilizza un URL, accertarsi che il percorso URL completo sia digitato o se si digita solo una parte dell'URL, non includere caratteri o spazi speciali. 
    
    Lasciare vuota questa casella per restituire le voci per tutti i file e le cartelle nell'organizzazione.
    
   **CONSIGLI**

   - Se si cercano tutte le attività relative a un **sito**, aggiungere il simbolo di carattere jolly\*() dopo l'URL per restituire tutte le voci per il sito. ad esempio, **"https://contoso-my.sharepoint.com/personal/*"**.

   - Se si cercano tutte le attività relative a un **file**, aggiungere il simbolo di carattere jolly\*() prima che il nome del file restituisca tutte le voci per il file. ad esempio, **"* Customer_Profitability_Sample. csv"**.
    

    
5. Fare clic su **Cerca** per eseguire la ricerca utilizzando i criteri di ricerca. 
    
    I risultati della ricerca vengono caricati e, dopo alcuni istanti, vengono visualizzati in **risultati**. Al termine della ricerca, viene visualizzato il numero di risultati trovati. Tenere presente che al massimo 5.000 eventi verranno visualizzati nel riquadro dei **risultati** con incrementi di 150 eventi. Se più di 5.000 eventi soddisfano i criteri di ricerca, vengono visualizzati gli eventi 5.000 più recenti. 
    
    ![Dopo il completamento della ricerca, il numero di risultati viene visualizzato.](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)
  
  
#### <a name="tips-for-searching-the-audit-log"></a>Suggerimenti per la ricerca nel registro di controllo

- È possibile selezionare attività specifiche da cercare facendo clic sul nome dell'attività. In alternativa, è possibile cercare tutte le attività di un gruppo, ad esempio **attività di file e cartelle**, facendo clic sul nome del gruppo. Se è selezionata un'attività, è possibile fare clic su di essa per annullare la selezione. È inoltre possibile utilizzare la casella di ricerca per visualizzare le attività che contengono la parola chiave digitata.
    
    ![Fare clic su nome gruppo attività per selezionare tutte le attività](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)
  
- Per visualizzare gli eventi dal registro di controllo di amministrazione di Exchange, è necessario selezionare **Mostra risultati per tutte le attività** nell'elenco **attività** . Gli eventi di questo log di controllo visualizzano il nome di un cmdlet, ad esempio **Set-Mailbox** , nella colonna **attività** nei risultati. Per ulteriori informazioni, fare clic sulla scheda **attività controllate** in questo argomento, quindi fare clic su **attività di amministrazione di Exchange**.
    
    Analogamente, esistono alcune attività di controllo che non dispongono di un elemento corrispondente nell'elenco delle **attività** . Se si conosce il nome dell'operazione per queste attività, è possibile cercare tutte le attività e quindi filtrare i risultati digitando il nome dell'operazione nella casella relativa alla colonna **attività** . Per ulteriori informazioni sul filtraggio dei risultati, vedere [passaggio 3: filtrare i risultati della ricerca](#step-3-filter-the-search-results) . 
    
- Fare clic su **Annulla** per cancellare i criteri di ricerca correnti. L'intervallo di date restituisce il valore predefinito degli ultimi sette giorni. È inoltre possibile fare clic su **Cancella tutto per visualizzare i risultati di tutte le attività** per annullare tutte le attività selezionate. 
    
- Se si verificano 5.000 risultati, è probabile che siano presenti più di 5.000 eventi che soddisfano i criteri di ricerca. È possibile affinare i criteri di ricerca e rieseguire la ricerca per restituire meno risultati oppure esportare tutti i risultati della ricerca selezionando **Esporta risultati** \> per **scaricare tutti i risultati**.

  
### <a name="step-2-view-the-search-results"></a>Passaggio 2: visualizzazione dei risultati della ricerca

I risultati di una ricerca del registro di controllo vengono visualizzati sotto **risultati** nella pagina di **ricerca del registro di controllo** . Come indicato in precedenza, al massimo 5.000 eventi (più recenti) vengono visualizzati in incrementi di 150. Per visualizzare altri eventi, è possibile utilizzare la barra di scorrimento nel riquadro **dei risultati** oppure premere **MAIUSC + fine** per visualizzare i successivi 150 eventi. 
  
I risultati contengono le seguenti informazioni su ogni evento restituito dalla ricerca.
  
- **Data:** La data e l'ora (in formato UTC) quando si è verificato l'evento. 
    
- **Indirizzo IP:** L'indirizzo IP del dispositivo utilizzato quando è stata registrata l'attività. L'indirizzo IP viene visualizzato in un formato di indirizzo IPv4 o IPv6. 
    
- **Utente:** L'utente (o l'account di servizio) che ha eseguito l'azione che ha attivato l'evento. 
    
- **Attività:** Attività eseguita dall'utente. Questo valore corrisponde alle attività selezionate nell'elenco a discesa **attività** . Per un evento proveniente dal registro di controllo di amministrazione di Exchange, il valore di questa colonna è un cmdlet di Exchange. 
    
- **Elemento:** Oggetto creato o modificato come risultato dell'attività corrispondente. Ad esempio, il file che è stato visualizzato o modificato o l'account utente che è stato aggiornato. Non tutte le attività hanno un valore in questa colonna. 
    
- **Dettaglio:** Dettagli aggiuntivi su un'attività. Anche in questo caso, non tutte le attività avranno un valore. 
    
> [!TIP]
> Fare clic su un'intestazione di colonna in **risultati** per ordinare i risultati. È possibile ordinare i risultati dalla a alla Z o alla Z in a. fare clic sull'intestazione della **Data** per ordinare i risultati dal più vecchio al più recente o più recente al più vecchio. 
  
#### <a name="view-the-details-for-a-specific-event"></a>Visualizzare i dettagli di un evento specifico

È possibile visualizzare ulteriori dettagli su un evento facendo clic sul record dell'evento nell'elenco dei risultati della ricerca. Viene visualizzata una pagina dei **Dettagli** che contiene le proprietà dettagliate del record di evento. Le proprietà visualizzate dipendono dal servizio Office 365 in cui si verifica l'evento. Per visualizzare i dettagli, fare clic su **altre informazioni**. Per le descrizioni, vedere [proprietà dettagliate nel log di controllo di Office 365](detailed-properties-in-the-office-365-audit-log.md).
  
![Fare clic su ulteriori informazioni per visualizzare le proprietà dettagliate del record di evento del registro di controllo](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

  
### <a name="step-3-filter-the-search-results"></a>Passaggio 3: filtrare i risultati della ricerca

Oltre all'ordinamento, è anche possibile filtrare i risultati di una ricerca nel registro di controllo. Si tratta di un'ottima funzionalità che consente di filtrare rapidamente i risultati per un utente o un'attività specifici. Inizialmente è possibile creare una ricerca estesa e quindi filtrare rapidamente i risultati per visualizzare gli eventi specifici. Successivamente, è possibile restringere i criteri di ricerca ed eseguire di nuovo la ricerca per restituire un insieme di risultati più piccolo e conciso.
  
Per filtrare i risultati:
  
1. Eseguire una ricerca nel registro di controllo.
    
2. Quando vengono visualizzati i risultati, fare clic su **Filtra risultati**.
    
    Le caselle di parole chiave vengono visualizzate sotto ogni intestazione di colonna.
    
3. Fare clic su una delle caselle all'interno di un'intestazione di colonna e digitare una parola o una frase, a seconda della colonna in base alla quale si sta applicando il filtro. I risultati verranno riadattati dinamicamente per visualizzare gli eventi che corrispondono al filtro.
    
    ![Digitare una parola nel filtro per visualizzare gli eventi che corrispondono al filtro](media/542dc323-a997-402c-934b-cc5e218e50bc.png)
  
4. Per cancellare un filtro, fare clic sulla **X** nella casella filtro oppure fare clic su **Nascondi filtro**.
    
> [!TIP]
> Per visualizzare gli eventi dal registro di controllo di amministrazione di Exchange **-** , digitare a (Dash) nella casella filtro **attività** . Verranno visualizzati i nomi dei cmdlet, che sono mostrati nella colonna **attività** per gli eventi di amministrazione di Exchange. È quindi possibile ordinare i nomi dei cmdlet in ordine alfabetico. 

### <a name="step-4-export-the-search-results-to-a-file"></a>Passaggio 4: esportare i risultati della ricerca in un file

È possibile esportare i risultati di una ricerca nel registro di controllo in un file con valori delimitati da virgole (CSV) nel computer locale. È possibile aprire il file in Microsoft Excel e utilizzare funzionalità quali la ricerca, l'ordinamento, il filtraggio e la suddivisione di una singola colonna (che contiene celle a più valori) in più colonne.
  
1. Eseguire una ricerca nel registro di controllo e quindi rivedere i criteri di ricerca fino a quando non si hanno i risultati desiderati.
    
2. Fare clic su **Esporta risultati** e selezionare una delle opzioni seguenti: 
    
  - **Salvare i risultati caricati** Scegliere questa opzione per esportare solo le voci visualizzate in results **** on the * * Audit Log Search * * Page. Il file CSV scaricato contiene le stesse colonne (e i dati) visualizzati nella pagina (data, utente, attività, elemento e dettagli). Una colonna aggiuntiva (denominata **more**) è inclusa nel file CSV che contiene altre informazioni dalla voce del registro di controllo. Poiché si stanno esportando gli stessi risultati caricati (e visualizzabili) nella pagina di **ricerca del registro di controllo** , vengono esportate al massimo 5.000 voci. 
    
  - **Scaricare tutti i risultati** Scegliere questa opzione per esportare tutte le voci dal registro di controllo di Office 365 che soddisfano i criteri di ricerca. Per un set di risultati di ricerca di grandi dimensioni, scegliere questa opzione per scaricare tutte le voci dal registro di controllo oltre ai risultati di 5.000 che possono essere visualizzati nella pagina di **ricerca del registro di controllo** . Questa opzione consente di scaricare i dati non elaborati dal registro di controllo in un file CSV e contiene informazioni aggiuntive dalla voce del registro di controllo in una colonna denominata **AuditData**. Se si sceglie questa opzione di esportazione, potrebbe essere necessario più tempo per scaricare il file, in quanto il file potrebbe essere molto più grande di quello scaricato se si sceglie l'opzione altro.
    
    > [!IMPORTANT]
    > È possibile scaricare un massimo di 50.000 voci in un file CSV da una singola ricerca del registro di controllo. Se 50.000 voci vengono scaricate nel file CSV, è probabile che siano presenti più di 50.000 eventi che soddisfano i criteri di ricerca. Per esportare più di questo limite, provare a utilizzare un intervallo di date per ridurre il numero di voci del registro di controllo. Potrebbe essere necessario eseguire più ricerche con intervalli di date inferiori per esportare più di 50.000 voci. 
  
3. Dopo aver selezionato un'opzione di esportazione, nella parte inferiore della finestra viene visualizzato un messaggio in cui viene richiesto di aprire il file CSV, salvarlo nella cartella Downloads o salvarlo in una cartella specifica.

  
#### <a name="more-information-about-exporting-audit-log-search-results"></a>Ulteriori informazioni sull'esportazione dei risultati di ricerca del registro di controllo

- L'opzione **Download All Results** consente di scaricare i dati non elaborati dal registro di controllo di Office 365 in un file CSV. Questo file contiene nomi di colonna diversi (CreationDate, UserIds, Operation, AuditData) rispetto al file scaricato se si seleziona l'opzione **Salva risultati caricati** . È anche possibile che i valori dei due file CSV diversi per la stessa attività siano diversi. Ad esempio, l'attività nella colonna **azione** nel file CSV e può avere un valore diverso da quello della versione "facile da usare" che viene visualizzata nella colonna **attività** nella pagina di **ricerca del registro di controllo** . ad esempio, MailboxLogin vs utente ha eseguito l'accesso alla cassetta postale.
    
- Se si scaricano tutti i risultati, il file CSV contiene una colonna denominata **AuditData**, che contiene informazioni aggiuntive su ogni evento. Come indicato in precedenza, questa colonna contiene una proprietà multivalore per più proprietà del record del registro di controllo. Ognuna delle coppie **proprietà: valore** di questa proprietà multivalore è separata da una virgola. È possibile utilizzare la query di alimentazione in Excel per dividere la colonna in più colonne in modo che ogni proprietà disponga di una colonna. In questo modo si consente di ordinare e filtrare una o più di queste proprietà. Per informazioni su come eseguire questa operazione, vedere la sezione "dividere una colonna per delimitatore" in [dividere una colonna di testo (Power query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662).
    
    Dopo aver suddiviso la colonna **AuditData** , è possibile filtrare nella colonna **operazioni** per visualizzare le proprietà dettagliate per un tipo specifico di attività. 
    
- È presente un limite di 3.060 caratteri per i dati visualizzati nel campo **AuditData** per un record di controllo. Se il limite di 3.060 caratteri viene superato, i dati in questo campo vengono troncati. 
    
- Quando si scaricano tutti i risultati da una query di ricerca che contiene eventi provenienti da diversi servizi di Office 365, la colonna **AuditData** nel file CSV contiene proprietà diverse a seconda del servizio in cui è stata eseguita l'azione. Ad esempio, le voci dei log di controllo di Exchange e di Azure AD includono una proprietà denominata **ResultStatus** che indica se l'azione ha avuto esito positivo o meno. Questa proprietà non è inclusa per gli eventi in SharePoint. Analogamente, gli eventi di SharePoint dispongono di una proprietà che identifica l'URL del sito per attività correlate a file e cartelle. Per attenuare questo comportamento, prendere in considerazione l'utilizzo di ricerche diverse per esportare i risultati per le attività da un singolo servizio. 
    
    Per una descrizione delle proprietà elencate nella colonna **AuditData** nel file CSV quando si scaricano tutti i risultati e il servizio a cui si applica ognuno, vedere [proprietà dettagliate nel log di controllo di Office 365](detailed-properties-in-the-office-365-audit-log.md).

## <a name="audited-activities"></a>Attività controllate

Nelle tabelle di questa sezione vengono descritte le attività di cui è stato eseguito il controllo in Office 365. È possibile cercare questi eventi eseguendo una ricerca nel registro di controllo nel centro sicurezza e conformità.
  
Queste tabelle raggruppano le attività correlate o le attività di un servizio specifico di Office 365. Nelle tabelle è incluso il nome descrittivo visualizzato nell'elenco a discesa **attività** e il nome dell'operazione corrispondente che viene visualizzata nelle informazioni dettagliate di un record di controllo e nel file CSV quando si esportano i risultati della ricerca. Per le descrizioni delle informazioni dettagliate, vedere [proprietà dettagliate nel log di controllo di Office 365](detailed-properties-in-the-office-365-audit-log.md).
  
Fare clic su uno dei collegamenti seguenti per passare a una tabella specifica.
  
||||
|:-----|:-----|:-----|
|[Attività di file e pagine](#file-and-page-activities)<br/> |[Attività cartella](#folder-activities)<br/> |[Attività dell'elenco di SharePoint](#sharepoint-list-activities)<br/>|
|[Attività di condivisione e accesso alle richieste](#sharing-and-access-request-activities)<br/> |[Attività di sincronizzazione](#synchronization-activities)<br/> |[Attività amministrative del sito](#site-administration-activities)<br/> |
|[Attività relative alle cassette postali di Exchange](#exchange-mailbox-activities)<br/> |[Attività di Sway](#sway-activities) <br/> |[Attività di amministrazione degli utenti](#user-administration-activities) <br/> |
|[Attività di amministrazione di gruppi di Azure AD](#azure-ad-group-administration-activities) <br/> |[Attività di amministrazione dell'applicazione](#application-administration-activities) <br/> |[Attività di amministrazione del ruolo](#role-administration-activities) <br/> |
|[Attività di amministrazione della directory](#directory-administration-activities) <br/>|[attività di eDiscovery](#ediscovery-activities) <br/> |[Attività avanzate di eDiscovery](#advanced-ediscovery-activities)<br/> |
|[Attività di Power BI](#power-bi-activities) <br/> |[Analisi del luogo di lavoro Microsoft](#microsoft-workplace-analytics-activities)<br/>|[Attività di Microsoft Teams](#microsoft-teams-activities) <br/> |
|[Attività di Yammer](#yammer-activities) <br/> |[Attività di flusso Microsoft](#microsoft-flow-activities) <br/>|[Attività di Microsoft PowerApps](#microsoft-powerapps)<br/>|
|[Attività di Microsoft Stream](#microsoft-stream-activities) <br/>|[Attività di amministrazione di Exchange](#exchange-admin-audit-log)<br/>|
||||
  
### <a name="file-and-page-activities"></a>Attività di file e pagine
  
Nella tabella seguente vengono descritte le attività relative a file e pagine in SharePoint Online e OneDrive for business.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|File a cui si accede  <br/> |Fileaccessed  <br/> |L'utente o l'account del sistema accede a un file.  <br/> |
|nessuno  <br/> |FileAccessedExtended  <br/> |Questa operazione è correlata all'attività "file di accesso" (fileaccessed). Un evento FileAccessedExtended viene registrato quando la stessa persona accede continuamente a un file per un periodo di tempo prolungato (fino a 3 ore). Lo scopo della registrazione degli eventi di FileAccessedExtended consiste nel ridurre il numero di eventi fileaccessed che vengono registrati quando si accede continuamente a un file. In questo modo è possibile ridurre il rumore di più record fileaccessed per ciò che è essenzialmente la stessa attività utente e consente di concentrarsi sull'evento iniziale (e più importante) fileaccessed.  <br/> |
|File archiviato  <br/> |Filecheckedin  <br/> |L'utente verifica un documento Estratto da una raccolta documenti.  <br/> |
|File Estratto  <br/> |FileCheck-out  <br/> |L'utente estrae un documento che si trova in una raccolta documenti. Gli utenti possono estrarre e apportare modifiche ai documenti che sono stati condivisi con essi.  <br/> |
|File copiato  <br/> |Filecopied  <br/> |L'utente copia un documento da un sito. Il file copiato può essere salvato in un'altra cartella nel sito.  <br/> |
|File eliminato  <br/> |FileDeleted  <br/> |L'utente elimina un documento da un sito.  <br/> |
|File eliminato dal Cestino  <br/> |FileDeletedFirstStageRecycleBin  <br/> |L'utente elimina un file dal Cestino di un sito.  <br/> |
|File eliminato dal Cestino secondario  <br/> |FileDeletedSecondStageRecycleBin  <br/> |L'utente elimina un file dal Cestino secondario di un sito.  <br/> |
|Mancata corrispondenza di sensibilità del documento rilevata <br/>|DocumentSensitivityMismatchDetected<br/>|L'utente carica un documento classificato con un'etichetta di riservatezza che ha una priorità più alta rispetto all'etichetta di riservatezza applicata al sito a cui viene caricato il documento. Nota Questo evento non viene attivato se l'etichetta di riservatezza applicata a un sito ha una priorità più alta rispetto all'etichetta di riservatezza applicata a un documento caricato nel sito. Per ulteriori informazioni sulla priorità delle etichette di riservatezza, vedere la sezione "priorità dell'etichetta" in [Panoramica delle etichette di riservatezza](sensitivity-labels.md#label-priority-order-matters).<br/>|
|Malware rilevato nel file  <br/> |FileMalwareDetected  <br/> |Il motore di protezione di SharePoint rileva malware in un file.  <br/> |
|Estrazione file scartata  <br/> |FileCheckOutDiscarded  <br/> |L'utente elimina (o annulla) un file estratto. Ciò significa che eventuali modifiche apportate al file al momento dell'estrazione vengono eliminate e non vengono salvate nella versione del documento nella raccolta documenti.  <br/> |
|File scaricato  <br/> |Filedownloaded  <br/> |L'utente scarica un documento da un sito.  <br/> |
|File modificato  <br/> |Filemodified  <br/> |L'account utente o di sistema consente di modificare il contenuto o le proprietà di un documento che si trova in un sito.  <br/> |
|nessuno  <br/> |FileModifiedExtended  <br/> |Questa operazione è correlata all'attività "file modificato" (filemodified). Un evento FileModifiedExtended viene registrato quando la stessa persona modifica continuamente un file per un periodo di tempo prolungato (fino a 3 ore). Lo scopo della registrazione degli eventi di FileModifiedExtended consiste nel ridurre il numero di eventi filemodified che vengono registrati quando un file viene continuamente modificato. In questo modo si riduce il rumore di più record filemodified per ciò che è essenzialmente la stessa attività utente e consente di concentrarsi sull'evento di filemodified iniziale (e più importante).  <br/> |
|File spostato  <br/> |Filemoved  <br/> |L'utente sposta un documento dal percorso corrente di un sito a un nuovo percorso.  <br/> |
|Recycled tutte le versioni secondarie del file  <br/> |FileVersionsAllMinorsRecycled  <br/> |L'utente Elimina tutte le versioni secondarie dalla cronologia delle versioni di un file. Le versioni eliminate vengono spostate nel cestino del sito.  <br/> |
|Recycled tutte le versioni di file  <br/> |FileVersionsAllRecycled  <br/> |L'utente Elimina tutte le versioni dalla cronologia delle versioni di un file. Le versioni eliminate vengono spostate nel cestino del sito.  <br/> |
|Versione riciclata del file  <br/> |FileVersionRecycled  <br/> |L'utente elimina una versione dalla cronologia delle versioni di un file. La versione eliminata viene spostata nel cestino del sito.  <br/> |
|File rinominato  <br/> |FileRinomina  <br/> |L'utente ridenomina un documento in un sito.  <br/> |
|File ripristinato  <br/> |FileRestore  <br/> |L'utente ripristina un documento dal Cestino di un sito.  <br/> |
|File caricato  <br/> |Fileuploaded  <br/> |L'utente carica un documento in una cartella di un sito.  <br/> |
|Pagina visualizzata  <br/> |Visualizzazione a pagina  <br/> |L'utente visualizza una pagina in un sito. Questo non include l'utilizzo di un Web browser per visualizzare i file che si trovano in una raccolta documenti.  <br/> |
|nessuno  <br/> |PageViewedExtended  <br/> |Questa operazione è correlata all'attività "visualizzazione pagina" (visualizzata in una pagina). Un evento PageViewedExtended viene registrato quando la stessa persona Visualizza continuamente una pagina Web per un periodo di tempo prolungato (fino a 3 ore). Lo scopo della registrazione degli eventi di PageViewedExtended consiste nel ridurre il numero di eventi visualizzati in visualizzazione che vengono registrati quando una pagina viene visualizzata continuamente. In questo modo, è possibile ridurre il rumore dei record a più pagine visualizzate in base alla stessa attività dell'utente e consentire di concentrarsi sull'evento iniziale (e più importante) di visualizzazione.  <br/> |
|Visualizzazione segnalata dal client <br/>|ClientViewSignaled<br/>|Il client di un utente (ad esempio, il sito Web o l'app per dispositivi mobili) ha segnalato che la pagina indicata è stata visualizzata dall'utente. Questa attività viene spesso registrata dopo un evento PagePrefetched per una pagina. <br/><br/>**Nota**: poiché gli eventi di ClientViewSignaled sono segnalati dal client anziché dal server, è possibile che l'evento non venga registrato dal server e che pertanto non venga visualizzato nel registro di controllo. È inoltre possibile che le informazioni nel record di controllo potrebbero non essere attendibili. Tuttavia, dal momento che l'identità dell'utente viene convalidata dal token utilizzato per creare il segnale, l'identità dell'utente elencata nel record di controllo corrispondente è accurata. |
|nessuno <br/>|PagePrefetched<br/>|Il client di un utente (ad esempio, il sito Web o l'app per dispositivi mobili) ha richiesto la pagina indicata per migliorare le prestazioni se l'utente lo Sfoglia. Questo evento viene registrato per indicare che il contenuto della pagina è stato servito al client dell'utente. Questo evento non è un'indicazione definitiva che l'utente ha effettivamente esplorato alla pagina. Quando viene eseguito il rendering del contenuto della pagina dal client (secondo la richiesta dell'utente), è necessario che venga generato un evento ClientViewSignaled. Tenere presente che non tutti i client supportano l'indicazione di una prelettura e pertanto alcune attività precompilate potrebbero essere registrate come eventi di visualizzazione.<br/>|
||||
  
### <a name="folder-activities"></a>Attività cartella
  
Nella tabella seguente vengono descritte le attività della cartella in SharePoint Online e OneDrive for business.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Cartella copiata  <br/> |FolderCopied  <br/> |L'utente copia una cartella da un sito in un'altra posizione in SharePoint o OneDrive for business.  <br/> |
|Cartella creata  <br/> |FolderCreated  <br/> |L'utente crea una cartella in un sito.  <br/> |
|Cartella eliminata  <br/> |FolderDeleted  <br/> |L'utente elimina una cartella da un sito.  <br/> |
|Cartella eliminata dal Cestino  <br/> |FolderDeletedFirstStageRecycleBin  <br/> |L'utente elimina una cartella dal Cestino di un sito.  <br/> |
|Cartella eliminata dal Cestino secondario  <br/> |FolderDeletedSecondStageRecycleBin  <br/> |L'utente elimina una cartella dal Cestino secondario in un sito.  <br/> |
|Cartella modificata  <br/> |FolderModified  <br/> |L'utente modifica una cartella in un sito. Ciò include la modifica dei metadati della cartella, ad esempio la modifica di tag e proprietà.  <br/> |
|Cartella spostata  <br/> |FolderMoved  <br/> |L'utente sposta una cartella in un percorso diverso in un sito.  <br/> |
|Cartella rinominata  <br/> |FolderRenamed  <br/> |L'utente ridenomina una cartella in un sito.  <br/> |
|Cartella ripristinata  <br/> |FolderRestored  <br/> |L'utente ripristina una cartella eliminata dal Cestino di un sito.  <br/> |
||||
  
### <a name="sharepoint-list-activities"></a>Attività dell'elenco di SharePoint
  
Nella tabella seguente vengono descritte le attività correlate a quando gli utenti interagiscono con gli elenchi e gli elementi di elenco in SharePoint Online.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
| Elenco creato              | ListCreated              | Un utente ha creato un nuovo elenco di SharePoint.|
| Colonna di elenco creata       | ListColumnCreated        | Un utente ha creato una nuova colonna dell'elenco di SharePoint. Una colonna di elenco è una colonna associata a uno o più elenchi di SharePoint. |
| Tipo di contenuto elenco creato | ListContentTypeCreated   | Un utente ha creato un nuovo tipo di contenuto dell'elenco. Un tipo di contenuto elenco è un tipo di contenuto associato a uno o più elenchi di SharePoint.|
| Elemento di elenco creato         | ListItemCreated          | Un utente ha creato un nuovo elemento in un elenco di SharePoint esistente.|
| Colonna del sito creata       | SiteColumnCreated        | Un utente ha creato una nuova colonna del sito di SharePoint. Una colonna del sito è una colonna non associata a un elenco. Una colonna del sito è anche una struttura di metadati che può essere utilizzata da qualsiasi elenco in un determinato sito Web.|
| Tipo di contenuto del sito creato | ContentType del sito creato | Un utente ha creato un nuovo tipo di contenuto del sito. Un tipo di contenuto del sito è un tipo di contenuto associato al sito padre.|
| Elenco eliminato              | ListDeleted              | Un utente ha eliminato un elenco di SharePoint.|
| Colonna dell'elenco eliminato       | Colonna di elenco eliminata      | Un utente ha eliminato una colonna di un elenco di SharePoint.|
| Tipo di contenuto elenco eliminato | ListContentTypeDeleted   | Un utente ha eliminato un tipo di contenuto elenco. |
| Elemento di elenco eliminato         | Elemento dell'elenco eliminato        | Un utente ha eliminato una voce di elenco di SharePoint.|
| Colonna del sito eliminato       | SiteColumnDeleted        | Un utente ha eliminato una colonna del sito di SharePoint. |
| Tipo di contenuto del sito eliminato | SiteContentTypeDeleted   | Un utente ha eliminato un tipo di contenuto del sito.|
| Elemento di elenco riciclato        | ListItemRecycled         | Un utente ha spostato una voce di elenco di SharePoint nel Cestino.|
| Elenco ripristinato             | ListRestored             | Un utente ha ripristinato un elenco di SharePoint dal Cestino.|
| Elemento di elenco ripristinato        | ListItemRestored         | Un utente ha ripristinato una voce di elenco di SharePoint dal Cestino.|
| Elenco aggiornato              | ListUpdated              | Un utente ha aggiornato un elenco di SharePoint modificando una o più proprietà.|
| Colonna elenco aggiornata       | ListColumnUpdated        | Un utente ha aggiornato una colonna di un elenco di SharePoint modificando una o più proprietà.|
| Tipo di contenuto elenco aggiornato | ListContentTypeUpdated   | Un utente ha aggiornato un tipo di contenuto elenco modificando una o più proprietà.|
| Elemento di elenco aggiornato         | ListItemUpdated          | Un utente ha aggiornato una voce di elenco di SharePoint modificando una o più proprietà.|  
| Colonna del sito aggiornata       | SiteColumnUpdated        | Un utente ha aggiornato una colonna del sito di SharePoint modificando una o più proprietà.|
| Tipo di contenuto del sito aggiornato | SiteContentTypeUpdated   | Un utente ha aggiornato un tipo di contenuto del sito modificando una o più proprietà.|
||||

### <a name="sharing-and-access-request-activities"></a>Attività di condivisione e accesso alle richieste
  
Nella tabella seguente vengono descritte le attività relative alla condivisione e alla richiesta di accesso degli utenti in SharePoint Online e OneDrive for business. Per gli eventi di condivisione, la colonna **Dettagli** in **results** identifica il nome dell'utente o del gruppo a cui è stato condiviso l'elemento e se quell'utente o gruppo è un membro o un ospite nell'organizzazione. Per ulteriori informazioni, vedere [use sharing audit in the Office 365 audit log](use-sharing-auditing.md).
  
> [!NOTE]
> Gli utenti possono essere *membri* o *Guest* in base alla proprietà UserType dell'oggetto User. Un membro è in genere un dipendente e un ospite è in genere un collaboratore esterno all'organizzazione. Quando un utente accetta un invito alla condivisione (e non è già incluso nell'organizzazione), viene creato un account guest nella directory dell'organizzazione. Una volta che l'utente ospite ha un account nella directory, le risorse possono essere condivise direttamente con esse (senza richiedere un invito). 
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Richiesta di accesso accettata  <br/> |AccessRequestAccepted  <br/> |È stata accettata una richiesta di accesso a un sito, una cartella o un documento e all'utente richiedente è stato concesso l'accesso.  <br/> |
|Invito alla condivisione accettata  <br/> |SharingInvitationAccepted  <br/> |L'utente (membro o ospite) ha accettato un invito alla condivisione ed è stato concesso l'accesso a una risorsa. Questo evento include informazioni sull'utente che è stato invitato e l'indirizzo di posta elettronica utilizzato per accettare l'invito (potrebbero essere diversi). Questa attività è spesso accompagnata da un secondo evento in cui viene descritto come all'utente è stato concesso l'accesso alla risorsa, ad esempio l'aggiunta di un utente a un gruppo che ha accesso alla risorsa.  <br/> |
|Livello di autorizzazione aggiunto per la raccolta siti  <br/> |PermissionLevelAdded  <br/> |È stato aggiunto un livello di autorizzazione a una raccolta siti.  <br/> |
|Invito per la condivisione bloccata  <br/> |SharingInvitationBlocked  <br/> | Un invito alla condivisione inviato da un utente nell'organizzazione è bloccato a causa di un criterio di condivisione esterna che consente o nega la condivisione esterna in base al dominio dell'utente di destinazione. In questo caso, l'invito alla condivisione è stato bloccato perché:  <br/>  Il dominio dell'utente di destinazione non è incluso nell'elenco dei domini consentiti.  <br/>  Oppure  <br/>  Il dominio dell'utente di destinazione è incluso nell'elenco dei domini bloccati.  <br/>  Per ulteriori informazioni su come consentire o bloccare la condivisione esterna in base ai domini, vedere Restricted [Domains sharing in SharePoint Online e OneDrive for business](https://support.office.com/article/5d7589cd-0997-4a00-a2ba-2320ec49c4e9).  <br/> |
|Creazione di un collegamento condiviso con la società  <br/> |CompanyLinkCreated  <br/> |L'utente ha creato un collegamento a livello di società a una risorsa. i collegamenti a livello di azienda possono essere utilizzati solo dai membri dell'organizzazione. Non possono essere utilizzati dagli ospiti.  <br/> |
|Richiesta di accesso creata  <br/> |AccessRequestCreated  <br/> |L'utente richiede l'accesso a un sito, una cartella o un documento in cui non dispongono delle autorizzazioni per l'accesso.  <br/> |
|Creato un collegamento anonimo  <br/> |AnonymousLinkCreated  <br/> |L'utente ha creato un collegamento anonimo a una risorsa. Tutti gli utenti che dispongono di questo collegamento possono accedere alla risorsa senza dover essere autenticati.  <br/> |
|Collegamento protetto creato  <br/> |SecureLinkCreated  <br/> |È stato creato un collegamento di condivisione sicura per questo elemento.  <br/> |
|Invito alla condivisione creato  <br/> |SharingInvitationCreated  <br/> |L'utente ha condiviso una risorsa in SharePoint Online o OneDrive for business con un utente che non si trova nella directory dell'organizzazione.  <br/> |
|Collegamento protetto eliminato  <br/> |SecureLinkDeleted  <br/> |È stato eliminato un collegamento di condivisione sicura.  <br/> |
|Richiesta di accesso negato  <br/> |AccessRequestDenied  <br/> |È stata negata una richiesta di accesso a un sito, una cartella o un documento.  <br/> |
|Rimozione di un collegamento condiviso con la società  <br/> |CompanyLinkRemoved  <br/> |L'utente ha rimosso un collegamento a livello di società a una risorsa. Il collegamento non può più essere utilizzato per accedere alla risorsa.  <br/> |
|Rimosso un collegamento anonimo  <br/> |AnonymousLinkRemoved  <br/> |L'utente ha rimosso un collegamento anonimo a una risorsa. Il collegamento non può più essere utilizzato per accedere alla risorsa.  <br/> |
|File, cartella o sito condiviso  <br/> |SharingSet  <br/> |L'utente (membro o ospite) ha condiviso un file, una cartella o un sito in SharePoint o OneDrive for business con un utente nella directory dell'organizzazione. Il valore nella colonna **dettaglio** per questa attività identifica il nome dell'utente a cui è stata condivisa la risorsa e se l'utente è un membro o un ospite. Questa attività è spesso accompagnata da un secondo evento che descrive il modo in cui l'utente ha concesso l'accesso alla risorsa. ad esempio, se si aggiunge l'utente a un gruppo che ha accesso alla risorsa.  <br/> |
|Richiesta di accesso aggiornata  <br/> |AccessRequestUpdated  <br/> |È stata aggiornata una richiesta di accesso a un elemento.  <br/> |
|Aggiornamento di un collegamento anonimo  <br/> |AnonymousLinkUpdated  <br/> |L'utente ha aggiornato un collegamento anonimo a una risorsa. Il campo aggiornato è incluso nella proprietà EventData quando si esportano i risultati della ricerca.  <br/> |
|Invito alla condivisione aggiornato  <br/> |SharingInvitationUpdated  <br/> |È stato aggiornato un invito per la condivisione esterna.  <br/> |
|Utilizzo di un collegamento anonimo  <br/> |AnonymousLinkUsed  <br/> |Un utente anonimo ha eseguito l'accesso a una risorsa utilizzando un collegamento anonimo. L'identità dell'utente potrebbe essere sconosciuta, ma è possibile ottenere altri dettagli, ad esempio l'indirizzo IP dell'utente.  <br/> |
|File, cartella o sito non condiviso  <br/> |SharingRevoked  <br/> |Utente (membro o ospite) ha ripartito un file, una cartella o un sito precedentemente condiviso con un altro utente.  <br/> |
|Utilizzo di un collegamento condivisibile aziendale  <br/> |CompanyLinkUsed  <br/> |L'utente ha eseguito l'accesso a una risorsa utilizzando un collegamento a livello di società.  <br/> |
|Collegamento sicuro utilizzato  <br/> |SecureLinkUsed  <br/> |Un utente ha utilizzato un collegamento sicuro.  <br/> |
|Aggiunta di un utente al collegamento protetto  <br/> |AddedToSecureLink  <br/> |Un utente è stato aggiunto all'elenco di entità che possono utilizzare un collegamento di condivisione sicura.  <br/> |
|Utente rimosso dal collegamento protetto  <br/> |RemovedFromSecureLink  <br/> |Un utente è stato rimosso dall'elenco di entità che possono utilizzare un collegamento di condivisione sicura.  <br/> |
|Invito alla condivisione ritirato  <br/> |SharingInvitationRevoked  <br/> |L'utente ha ritirato un invito di condivisione a una risorsa.  <br/> |
||||
  
### <a name="synchronization-activities"></a>Attività di sincronizzazione
  
Nella tabella seguente sono elencate le attività di sincronizzazione dei file in SharePoint Online e OneDrive for business.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Computer consentito per la sincronizzazione dei file  <br/> |ManagedSyncClientAllowed  <br/> |L'utente stabilisce correttamente una relazione di sincronizzazione con un sito. La relazione di sincronizzazione ha esito positivo perché il computer dell'utente è un membro di un dominio che è stato aggiunto all'elenco dei domini (denominato *elenco destinatari attendibili* ) che può accedere alle raccolte documenti nell'organizzazione.  <br/> Per ulteriori informazioni su questa funzionalità, vedere [utilizzo dei cmdlet di Windows PowerShell per abilitare la sincronizzazione di OneDrive per i domini presenti nell'elenco destinatari attendibili](https://go.microsoft.com/fwlink/p/?LinkID=534609).  <br/> |
|Computer bloccato dalla sincronizzazione dei file  <br/> |UnmanagedSyncClientBlocked  <br/> |L'utente tenta di stabilire una relazione di sincronizzazione con un sito da un computer che non è un membro del dominio dell'organizzazione o che è un membro di un dominio che non è stato aggiunto all'elenco di domini (denominato *elenco destinatari attendibili)* che può accedere al documento raccolte nell'organizzazione. La relazione di sincronizzazione non è consentita e il computer dell'utente è bloccato dalla sincronizzazione, dal download o dal caricamento di file in una raccolta documenti.  <br/> Per informazioni su questa funzionalità, vedere [utilizzo dei cmdlet di Windows PowerShell per abilitare la sincronizzazione di OneDrive per i domini presenti nell'elenco destinatari attendibili](https://go.microsoft.com/fwlink/p/?LinkID=534609).  <br/> |
|File scaricati nel computer  <br/> |FileSyncDownloadedFull  <br/> |L'utente stabilisce una relazione di sincronizzazione e Scarica i file per la prima volta nel proprio computer da una raccolta documenti.  <br/> |
|Modifiche ai file scaricati nel computer  <br/> |FileSyncDownloadedPartial  <br/> |L'utente scarica correttamente le modifiche apportate ai file da una raccolta documenti. Questa attività indica che tutte le modifiche apportate ai file nella raccolta documenti sono state scaricate nel computer dell'utente. Sono state scaricate solo le modifiche perché la raccolta documenti è stata scaricata in precedenza dall'utente (come indicato dai **file scaricati all'** attività del computer).  <br/> |
|File caricati nella raccolta documenti  <br/> |FileSyncUploadedFull  <br/> |L'utente stabilisce una relazione di sincronizzazione e carica correttamente i file per la prima volta dal proprio computer a una raccolta documenti.  <br/> |
|Modifiche ai file caricati nella raccolta documenti  <br/> |FileSyncUploadedPartial  <br/> |Le modifiche apportate ai file in una raccolta documenti vengono caricate correttamente dall'utente. Questo evento indica che tutte le modifiche apportate alla versione locale di un file da una raccolta documenti vengono caricate correttamente nella raccolta documenti. Solo le modifiche vengono caricate perché tali file sono stati precedentemente caricati dall'utente (come indicato dai **file caricati nell'attività raccolta documenti** ).  <br/> |
||||

### <a name="site-permissions-activities"></a>Attività relative alle autorizzazioni del sito

Nella tabella seguente sono elencati gli eventi relativi all'assegnazione delle autorizzazioni in SharePoint e l'utilizzo dei gruppi per l'accesso ai siti.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta dell'amministratore della raccolta siti  <br/> |SiteCollectionAdminAdded  <br/> |L'amministratore o il proprietario della raccolta siti aggiunge una persona come amministratore della raccolta siti per un sito. Gli amministratori della raccolta di siti dispongono di autorizzazioni di controllo complete per la raccolta di siti e per tutti i siti secondari. Questa attività viene inoltre registrata quando un amministratore si concede l'accesso all'account OneDrive di un utente (modificando il profilo utente nell'interfaccia di amministrazione di SharePoint o [utilizzando il centro di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data#part-1---get-access-to-the-former-employees-onedrive-for-business-documents)). <br/> |
|Aggiunta di un utente o un gruppo a un gruppo di SharePoint  <br/> |AddedToGroup  <br/> |L'utente ha aggiunto un membro o un ospite a un gruppo di SharePoint. Potrebbe trattarsi di un'azione intenzionale o del risultato di un'altra attività, ad esempio un evento di condivisione.  <br/> |
|Ereditarietà a livello di autorizzazione interrotta  <br/> |PermissionLevelsInheritanceBroken  <br/> |Un elemento è stato modificato in modo che non erediti più i livelli di autorizzazione dall'elemento padre.  <br/> |
|Ha interrotto l'ereditarietà della condivisione  <br/> |SharingInheritanceBroken  <br/> |Un elemento è stato modificato in modo che non erediti più le autorizzazioni di condivisione dal relativo elemento padre.  <br/> |
|Gruppo creato  <br/> |GroupAdded  <br/> |L'amministratore del sito o il proprietario crea un gruppo per un sito o esegue un'attività che genera un gruppo in fase di creazione. Ad esempio, la prima volta che un utente crea un collegamento per la condivisione di un file, viene aggiunto un gruppo di sistema al sito di OneDrive for business dell'utente. Questo evento può anche essere il risultato della creazione da parte dell'utente di un collegamento con autorizzazioni di modifica in un file condiviso.  <br/> |
|Gruppo eliminato  <br/> |GroupRemoved  <br/> |L'utente elimina un gruppo da un sito.  <br/> |
|Impostazione delle richieste di accesso modificate  <br/> |WebRequestAccessModified  <br/> |Le impostazioni delle richieste di accesso sono state modificate in un sito.  <br/> |
|Modifica dell'impostazione ' membri in grado di condividere '  <br/> |WebMembersCanShareModified  <br/> |I **membri possono condividere** l'impostazione è stata modificata in un sito.  <br/> |
|Livello di autorizzazione modificato per la raccolta siti  <br/> |PermissionLevelModified  <br/> |Un livello di autorizzazione è stato modificato in una raccolta siti.  <br/> |
|Autorizzazioni del sito modificate  <br/> |SitePermissionsModified  <br/> |L'amministratore del sito o il proprietario (o l'account di sistema) modifica il livello di autorizzazione assegnato a un gruppo in un sito. Questa attività viene inoltre registrata se tutte le autorizzazioni sono state rimosse da un gruppo.  <br/><br/> **Nota**: questa operazione è stata deprecata in SharePoint Online. Per trovare gli eventi correlati, è possibile cercare altre attività correlate all'autorizzazione, ad esempio l' **aggiunta di amministratore della raccolta siti**, l' **utente o il gruppo aggiunto al gruppo di SharePoint**, l' **utente consentito per la creazione di gruppi**, il **gruppo creato**e l' **eliminazione gruppo.**|
|Livello di autorizzazione rimosso dalla raccolta siti  <br/> |PermissionLevelRemoved  <br/> |Un livello di autorizzazione è stato rimosso da una raccolta siti.  <br/> |
|Amministratore della raccolta siti rimosso  <br/> |SiteCollectionAdminRemoved <br/> |L'amministratore o il proprietario della raccolta siti consente di rimuovere una persona come amministratore della raccolta siti per un sito. Questa attività viene inoltre registrata quando un amministratore si rimuove dall'elenco degli amministratori delle raccolte siti per l'account OneDrive di un utente (modificando il profilo utente nell'interfaccia di amministrazione di SharePoint).  Si noti che per restituire questa attività nei risultati di ricerca del registro di controllo, è necessario cercare tutte le attività. <br/> |
|Utenti o gruppi rimossi dal gruppo di SharePoint  <br/> |RemovedFromGroup  <br/> |L'utente ha rimosso un membro o un ospite da un gruppo di SharePoint. Potrebbe trattarsi di un'azione intenzionale o del risultato di un'altra attività, ad esempio un evento di annullamento della condivisione.  <br/> |
|Autorizzazioni di amministratore del sito richieste  <br/> |SiteAdminChangeRequest  <br/> |Richieste degli utenti da aggiungere come amministratore della raccolta siti per una raccolta siti. Gli amministratori della raccolta di siti dispongono di autorizzazioni di controllo complete per la raccolta di siti e per tutti i siti secondari.  <br/> |
|Ereditarietà della condivisione ripristinata  <br/> |SharingInheritanceReset  <br/> |È stata apportata una modifica in modo che un elemento erediti le autorizzazioni di condivisione dal relativo elemento padre.  <br/> |
|Gruppo aggiornato  <br/> |GroupUpdated  <br/> |L'amministratore del sito o il proprietario modifica le impostazioni di un gruppo per un sito. Ciò può includere la modifica del nome del gruppo, degli utenti in grado di visualizzare o modificare l'appartenenza al gruppo e del modo in cui vengono gestite le richieste di appartenenza.  <br/> |
||||

  
### <a name="site-administration-activities"></a>Attività amministrative del sito
  
Nella tabella seguente sono elencati gli eventi che risultano dalle attività di amministrazione del sito in SharePoint Online.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta della posizione dei dati consentita<br/>|AllowedDataLocationAdded|Un amministratore di SharePoint o globale ha aggiunto una posizione dati consentita in un ambiente multi-geografico. <br/>|
|Aggiunta di un agente utente di esenzione  <br/> |ExemptUserAgentSet  <br/> |Un amministratore di SharePoint o globale ha aggiunto un agente utente all'elenco degli agenti utente esenti nell'interfaccia di amministrazione di SharePoint.  <br/> |
|Aggiunta dell'amministratore della posizione geografica<br/>|GeoAdminAdded<br/>|Un amministratore di SharePoint o globale ha aggiunto un utente come amministratore geografico di una posizione. <br/>|
|Utente consentito per la creazione di gruppi  <br/> |AllowGroupCreationSet  <br/> |L'amministratore del sito o il proprietario aggiunge un livello di autorizzazione a un sito che consente a un utente a cui è stata assegnata l'autorizzazione di creare un gruppo per il sito.  <br/> |
|Spostamento Geo del sito cancellato  <br/> |SiteGeoMoveCancelled  <br/> |Un amministratore di SharePoint o globale Annulla correttamente una mossa geografica del sito di SharePoint o OneDrive. La funzionalità multi-Geo consente a un'organizzazione di Office 365 di suddividere più aree geografiche di Office 365 datacenter, denominate GEOS. Per ulteriori informazioni, vedere [multi-Geo capabilities in OneDrive e SharePoint online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).  <br/> |
|Modifica di un criterio di condivisione  <br/> |SharingPolicyChanged  <br/> |Un amministratore di SharePoint o globale ha modificato un criterio di condivisione di SharePoint utilizzando il portale di amministrazione di Office 365, il portale di amministrazione di SharePoint o SharePoint Online Management Shell. Tutte le modifiche apportate alle impostazioni nel criterio di condivisione nell'organizzazione verranno registrate. I criteri modificati vengono identificati nel campo **ModifiedProperties** nelle proprietà dettagliate del record di evento.  <br/> |
|Criteri di accesso ai dispositivi modificati  <br/> |DeviceAccessPolicyChanged  <br/> |Un amministratore di SharePoint o globale ha modificato i criteri per i dispositivi non gestiti per l'organizzazione. Questo criterio consente di controllare l'accesso a SharePoint, OneDrive e Office 365 da dispositivi che non sono stati aggiunti all'organizzazione. La configurazione di questo criterio richiede una sottoscrizione Enterprise Mobility + Security. Per altre informazioni, vedere [Controllare l'accesso da dispositivi non gestiti](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622).  <br/> |
|Agenti utente esenti modificati  <br/> |CustomizeExemptUsers  <br/> |Un amministratore di SharePoint o globale ha personalizzato l'elenco degli agenti utente esenti nell'interfaccia di amministrazione di SharePoint. È possibile specificare quali agenti utente esentare dalla ricezione di un'intera pagina Web da indicizzare. Questo significa che quando un agente utente specificato come esenzione incontra un modulo di InfoPath, il modulo verrà restituito come file XML, invece di un'intera pagina Web. In tal modo l'indicizzazione dei moduli di InfoPath è più rapida.  <br/> |
|Criteri di accesso alla rete modificati  <br/> |NetworkAccessPolicyChanged  <br/> |Un amministratore di SharePoint o globale ha modificato il criterio di accesso basato sulla posizione (denominato anche limite di rete attendibile) nell'interfaccia di amministrazione di SharePoint o tramite PowerShell di SharePoint Online. Questo tipo di criteri controlla chi può accedere alle risorse di SharePoint e OneDrive nell'organizzazione in base agli intervalli di indirizzi IP autorizzati specificati. Per ulteriori informazioni, vedere [controllare l'accesso ai dati di SharePoint Online e OneDrive in base al percorso di rete](https://support.office.com/article/b5a5f1f1-1174-4c6b-91d0-9273a6b6971f).  <br/> |
|Spostamento geografico completato del sito  <br/> |SiteGeoMoveCompleted  <br/> |Una mossa geografica del sito pianificata da un amministratore globale dell'organizzazione è stata completata correttamente. La funzionalità multi-Geo consente a un'organizzazione di Office 365 di suddividere più aree geografiche di Office 365 datacenter, denominate GEOS. Per ulteriori informazioni, vedere [multi-Geo capabilities in OneDrive e SharePoint online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).  <br/> |
|Creato inviato alla connessione  <br/> |SendToConnectionAdded  <br/> |Un amministratore di SharePoint o globale crea una nuova connessione per l'invio nella pagina di gestione dei record nell'interfaccia di amministrazione di SharePoint. Una connessione Invia a specifica le impostazioni per un archivio di documenti o centro record. Quando si crea una connessione Invia a, un Content Organizer può inviare documenti al percorso specificato.  <br/> |
|Raccolta siti creata  <br/> |SiteCollectionCreated  <br/> |Un amministratore di SharePoint o globale crea una nuova raccolta siti nell'organizzazione di SharePoint Online o un utente che applica il sito di OneDrive for business.  <br/> |
|Sito hub orfano eliminato<br/>|HubSiteOrphanHubDeleted<br/>|Un amministratore di SharePoint o globale ha eliminato un sito hub orfano, che è un sito hub a cui non sono associati siti. È probabile che un hub isolato sia causato dall'eliminazione del sito Hub originale. <br/>|
|Eliminato inviato alla connessione  <br/> |SendToConnectionRemoved  <br/> |Un amministratore di SharePoint o globale elimina una connessione Send to nella pagina Gestione record nell'interfaccia di amministrazione di SharePoint.  <br/> |
|Sito eliminato  <br/> |SiteDeleted  <br/> |L'amministratore del sito Elimina un sito.  <br/> |
|Anteprima del documento attivata  <br/> |PreviewModeEnabledSet  <br/> |L'amministratore del sito Abilita l'anteprima del documento per un sito.  <br/> |
|Flusso di lavoro legacy abilitato  <br/> |LegacyWorkflowEnabledSet  <br/> |L'amministratore o il proprietario del sito aggiunge il tipo di contenuto di attività di flusso di lavoro di SharePoint 2013 al sito. Gli amministratori globali possono inoltre abilitare i flussi di lavoro per l'intera organizzazione nell'interfaccia di amministrazione di SharePoint.  <br/> |
|Office abilitato su richiesta  <br/> |OfficeOnDemandSet  <br/> |L'amministratore del sito abilita Office su richiesta, che consente agli utenti di accedere alla versione più recente delle applicazioni desktop di Office. Office su richiesta è abilitato nell'interfaccia di amministrazione di SharePoint e richiede un abbonamento a Office 365 che include le applicazioni di Office complete e installate.  <br/> |
|Origine dei risultati abilitata per le ricerche di utenti<br/>|PeopleResultsScopeSet<br/>|L'amministratore del sito crea l'origine dei risultati per le ricerche degli utenti di un sito.<br/>|
|Feed RSS abilitati  <br/> |NewsFeedEnabledSet  <br/> |L'amministratore del sito o il proprietario attiva i feed RSS per un sito. Gli amministratori globali possono abilitare i feed RSS per l'intera organizzazione nell'interfaccia di amministrazione di SharePoint.  <br/> |
|Sito aggiunto al sito hub<br/>|HubSiteJoined<br/>|Un proprietario del sito associa il sito a un sito hub.<br/>|
|Sito hub registrato<br/>|HubSiteRegistered<br/>|Un amministratore di SharePoint o globale crea un sito hub. I risultati sono che il sito è stato registrato come sito hub. <br/>|
|Posizione dei dati consentita rimossa<br/>|AllowedDataLocationDeleted<br/>|Un amministratore di SharePoint o globale ha rimosso una posizione dati consentita in un ambiente multi-geografico.<br/>|
|Amministratore della posizione geografica rimossa<br/>|GeoAdminDeleted<br/>|Un amministratore di SharePoint o globale ha rimosso un utente come amministratore geografico di una posizione.<br/>|
|Rinominato sito  <br/> |SiteRenamed  <br/> |L'amministratore del sito o il proprietario ridenomina un sito  <br/> |
|Spostamento geografico del sito pianificato  <br/> |SiteGeoMoveScheduled  <br/> |Un amministratore di SharePoint o globale pianifica correttamente una mossa geografica del sito di SharePoint o OneDrive. La funzionalità multi-Geo consente a un'organizzazione di Office 365 di suddividere più aree geografiche di Office 365 datacenter, denominate GEOS. Per ulteriori informazioni, vedere [multi-Geo capabilities in OneDrive e SharePoint online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).  <br/> |
|Impostare il sito host  <br/> |HostSiteSet  <br/> |Un amministratore di SharePoint o globale modifica il sito designato per ospitare i siti personali o OneDrive for business.  <br/> |
|Impostare la quota di archiviazione per la posizione geografica  <br/> |GeoQuotaAllocated<br/> |Un amministratore di SharePoint o globale ha configurato la quota di archiviazione per una posizione geografica in un ambiente multi-geografico.<br/> |
|Sito non contiguo dal sito hub<br/>|HubSiteUnjoined<br/>|Un proprietario del sito annulla l'associazione del sito da un sito hub.<br/>|
|Sito hub non registrato<br/>|HubSiteUnregistered<br/>|Un amministratore di SharePoint o globale annulla la registrazione di un sito come sito hub. Quando viene annullata la registrazione di un sito hub, non funziona più come sito hub. <br/>|
||||
  
### <a name="exchange-mailbox-activities"></a>Attività relative alle cassette postali di Exchange
  
Nella tabella seguente sono elencate le attività che possono essere registrate tramite la registrazione di controllo delle cassette postali. Le attività delle cassette postali eseguite dal proprietario della cassetta postale, da un utente delegato o da un amministratore vengono registrate. Per impostazione predefinita, il controllo delle cassette postali in Office 365 non è attivato. La registrazione di controllo delle cassette postali deve essere attivata per ogni cassetta postale prima che venga registrata l'attività della cassetta postale. Per ulteriori informazioni, vedere [abilitare il controllo delle cassette postali in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta delle autorizzazioni per le cassette postali delegate  <br/> |Add-MailboxPermission  <br/> |Un amministratore ha assegnato l'autorizzazione cassetta postale di FullAccess a un utente (noto come delegato) alla cassetta postale di un'altra persona. L'autorizzazione FullAccess consente al delegato di aprire la cassetta postale dell'altra persona e di leggere e gestire il contenuto della cassetta postale.  <br/> |
|Messaggio classificato come record  <br/> |ApplyRecordLabel<br/> |Un messaggio è stato classificato come record. Questo problema si verifica quando un'etichetta di conservazione che classifica il contenuto come record viene applicata manualmente o automaticamente a un messaggio.<br/> |
|Copia dei messaggi in un'altra cartella  <br/> |Copia  <br/> |Messaggio copiato in un'altra cartella.  <br/> |
|Elemento della cassetta postale creato  <br/> |Creazione  <br/> |Elemento creato nella cartella Calendario, Contatti, Note o Attività nella cassetta postale; ad esempio, viene creata una nuova convocazione di riunione. Si noti che la creazione, l'invio o la ricezione di un messaggio non viene controllato. Inoltre, la creazione di una cartella delle cassette postali non viene controllata.  <br/> |
|Nuova regola di posta in arrivo creata in Outlook Web App  <br/> |NewInboxRule<br/> |Un utente ha creato una nuova regola di posta in arrivo in Outlook Web App (OWA).<br/> |
|Messaggi eliminati dalla cartella Posta eliminata  <br/> |SoftDelete  <br/> |Messaggio eliminato in modo definitivo dalla cartella Posta eliminata. Questi elementi vengono spostati nella cartella elementi ripristinabili. I messaggi vengono spostati nella cartella elementi ripristinabili anche quando un utente la seleziona e preme **MAIUSC + CANC**.  <br/> |
|Spostamento dei messaggi in un'altra cartella  <br/> |Move  <br/> |Messaggio spostato in un'altra cartella.  <br/> |
|Spostamento dei messaggi nella cartella Posta eliminata  <br/> |MoveToDeletedItems  <br/> |Messaggio eliminato e spostato nella cartella Posta eliminata.  <br/> |
|Autorizzazione per la cartella modificata  <br/> |UpdateFolderPermissions  <br/> |È stata modificata un'autorizzazione per la cartella. Autorizzazioni per le cartelle controllare quali utenti dell'organizzazione possono accedere alle cartelle delle cassette postali e ai messaggi presenti nella cartella.  <br/> |
|Messaggi eliminati dalla cassetta postale  <br/> |HardDelete  <br/> |Un messaggio è stato eliminato dalla cartella elementi ripristinabili (eliminato definitivamente dalla cassetta postale).  <br/> |
|Autorizzazioni di cassetta postale delegate rimosse  <br/> |Remove-MailboxPermission  <br/> |Un amministratore ha rimosso l'autorizzazione FullAccess (assegnata a un delegato) dalla cassetta postale di una persona. Dopo la rimozione dell'autorizzazione FullAccess, il delegato non è in grado di aprire la cassetta postale dell'altra persona o di accedere a qualsiasi contenuto.  <br/> |
|Messaggio inviato utilizzando le autorizzazioni Invia come  <br/> |SendAs  <br/> |Messaggio inviato utilizzando l'autorizzazione SendAs. Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.  <br/> |
|Messaggio inviato utilizzando le autorizzazioni Invia per conto di  <br/> |SendOnBehalf  <br/> |Messaggio inviato utilizzando l'autorizzazione SendOnBehalf. Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario la persona per conto della quale è stato inviato il messaggio e l’utente che ha effettivamente inviato il messaggio.  <br/> |
|Accesso delegato aggiornato alla cartella del calendario  <br/> |UpdateCalendarDelegation  <br/> |Una delega del calendario è stata assegnata a una cassetta postale. La delega del calendario fornisce a un altro utente nella stessa organizzazione le autorizzazioni per la gestione del calendario del proprietario della cassetta postale.  <br/> |
|Messaggio aggiornato  <br/> |Aggiornamento  <br/> |Modifiche apportate a un messaggio o alle relative proprietà.  <br/> |
|Utente che ha eseguito l'accesso alla cassetta postale  <br/> |MailboxLogin  <br/> |Accesso effettuato dall'utente alla propria cassetta postale.  <br/> |
|nessuno  <br/> |UpdateInboxRules  <br/> |È stata aggiunta, rimossa o modificata una regola di posta in arrivo. Le regole di posta in arrivo vengono utilizzate per elaborare i messaggi nella posta in arrivo dell'utente in base alle condizioni specificate e intraprendere azioni quando vengono soddisfatte le condizioni di una regola, ad esempio lo spostamento di un messaggio in una cartella specificata o l'eliminazione di un messaggio.  <br/> Per restituire le voci per le attività della regola di posta in arrivo, è necessario selezionare **Mostra risultati per tutte** le attività nell'elenco **attività** . Utilizzare le caselle Intervallo di date e l'elenco **utenti** per restringere i risultati della ricerca.  <br/> |
||||

### <a name="sway-activities"></a>Attività di Sway
  
Nella tabella seguente sono elencate le attività di utenti e amministratori in Sway. Sway è un'app di Office 365 che consente agli utenti di raccogliere, formattare e condividere idee, storie e presentazioni in un'area di lavoro interattiva basata sul Web. Per ulteriori informazioni, vedere [Frequently Asked Questions about Sway-Admin Help](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075).
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Livello di condivisione di influenza modificato  <br/> |SwayChangeShareLevel  <br/> |L'utente modifica il livello di condivisione di un dominio. Questo evento consente di acquisire l'utente modificando l'ambito di condivisione associato a un dominio. ad esempio, Public versus all'interno dell'organizzazione.  <br/> |
|Ondeggiamento creato  <br/> |SwayCreate  <br/> |L'utente crea un dominio.  <br/> |
|Ondeggiamento eliminato  <br/> |SwayDelete  <br/> |L'utente elimina un dominio.  <br/> |
|Duplicazione di Sway disabilitata  <br/> |SwayDisableDuplication  <br/> |L'utente disattiva la duplicazione di un ondeggiamento.  <br/> |
|Ondeggiamento duplicato  <br/> |SwayDuplicate  <br/> |L'utente duplica un dominio.  <br/> |
|Ondeggiamento modificato  <br/> |SwayEdit  <br/> |L'utente modifica un dominio.  <br/> |
|Attivata la duplicazione degli ondeggiamenti  <br/> |EnableDuplication  <br/> |L'utente abilita la duplicazione di un ondeggiamento; la possibilità per un utente di abilitare la duplicazione di un dominio è abilitata per impostazione predefinita.  <br/> |
|Condivisione degli ondeggiamenti revocati  <br/> |SwayRevokeShare  <br/> |L'utente interrompe la condivisione di un dominio revocando l'accesso. La revoca dell'accesso cambia i collegamenti associati a un dominio.  <br/> |
|Influenza condivisa  <br/> |SwayShare  <br/> |L'utente intende condividere un dominio. Questo evento acquisisce l'azione dell'utente facendo clic su una destinazione di condivisione specifica all'interno del menu Condividi influenza. L'evento non indica se l'utente ha completato l'azione Condividi.  <br/> |
|Disattivata la condivisione esterna di Sway  <br/> |SwayExternalSharingOff  <br/> |L'amministratore disattiva la condivisione degli ondeggiamenti esterni per l'intera organizzazione tramite l'interfaccia di amministrazione di Microsoft 365.  <br/> |
|Attivata la condivisione esterna di Sway  <br/> |SwayExternalSharingOn  <br/> |L'amministratore abilita la condivisione degli ondeggiamenti esterni per l'intera organizzazione tramite l'interfaccia di amministrazione di Microsoft 365.  <br/> |
|Disattivazione del servizio Sway  <br/> |SwayServiceOff  <br/> |L'amministratore disattiva l'influenza per l'intera organizzazione tramite l'interfaccia di amministrazione di Microsoft 365.  <br/> |
|Attivata la funzione Sway  <br/> |SwayServiceOn  <br/> |L'amministratore consente di influenzare l'intera organizzazione utilizzando l'interfaccia di amministrazione di Microsoft 365 (il servizio Sway è abilitato per impostazione predefinita).  <br/> |
|Ondeggiamento visualizzato  <br/> |SwayView  <br/> |L'utente visualizza un ondeggiamento.  <br/> |
||||

  
### <a name="user-administration-activities"></a>Attività di amministrazione degli utenti
  
Nella tabella seguente sono elencate le attività di amministrazione degli utenti registrate quando un amministratore aggiunge o modifica un account utente tramite l'interfaccia di amministrazione di Microsoft 365 o il portale di gestione di Azure.
  
|**Attività**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Utente aggiunto  <br/> |Aggiungi utente  <br/> |È stato creato un account utente di Office 365.  <br/> |
|Licenza utente modificata  <br/> |Modificare la licenza utente  <br/> |La licenza assegnata a un utente che cosa è cambiato. Per sapere quali licenze sono state modificate, vedere l'attività **utente aggiornata** corrispondente.  <br/> |
|Password utente modificata  <br/> |Modificare la password dell'utente  <br/> |L'amministratore ha modificato la password per un utente.  <br/> |
|Utente eliminato  <br/> |Delete user  <br/> |Un account utente di Office 365 è stato eliminato.  <br/> |
|Reimpostare la password dell'utente  <br/> |Reimpostare la password dell'utente  <br/> |L'amministratore reimposta la password per un utente.  <br/> |
|Impostare la proprietà che impone all'utente di modificare la password  <br/> |Impostare Force Change password utente  <br/> |Amministratore impostare la proprietà che impone a un utente di modificare la propria password al successivo accesso dell'utente a Office 365.  <br/> |
|Impostare le proprietà della licenza  <br/> |Impostare le proprietà della licenza  <br/> |Administrator consente di modificare le proprietà di una licenza assegnata a un utente.  <br/> |
|Utente aggiornato  <br/> |Aggiornare l'utente  <br/> |L'amministratore modifica una o più proprietà di un account utente. Per un elenco delle proprietà degli utenti che possono essere aggiornate, vedere la sezione "aggiornare gli attributi degli utenti" negli [eventi del report di controllo di Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).  <br/> |
||||
  
### <a name="azure-ad-group-administration-activities"></a>Attività di amministrazione di gruppi di Azure AD
  
Nella tabella seguente sono elencate le attività di amministrazione del gruppo registrate quando un amministratore o un utente crea o modifica un gruppo di Office 365 o quando un amministratore crea un gruppo di sicurezza utilizzando l'interfaccia di amministrazione di Microsoft 365 o il portale di gestione di Azure. Per ulteriori informazioni sui gruppi di Office 365, vedere [visualizzare, creare ed eliminare gruppi nell'interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7).
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Gruppo aggiunto  <br/> |Aggiungi gruppo  <br/> |È stato creato un gruppo.  <br/> |
|Aggiunta di un membro al gruppo  <br/> |Aggiungere un membro al gruppo  <br/> |È stato aggiunto un membro a un gruppo.  <br/> |
|Gruppo eliminato  <br/> |Elimina gruppo  <br/> |Un gruppo è stato eliminato.  <br/> |
|Membri rimossi dal gruppo  <br/> |Rimuovi membro da un gruppo  <br/> |Un membro è stato rimosso da un gruppo.  <br/> |
|Gruppo aggiornato  <br/> |Gruppo di aggiornamento  <br/> |È stata modificata una proprietà di un gruppo.  <br/> |
||||
   
### <a name="application-administration-activities"></a>Attività di amministrazione dell'applicazione
  
Nella tabella seguente sono elencate le attività di amministrazione dell'applicazione registrate quando un amministratore aggiunge o modifica un'applicazione registrata in Azure AD. Tutte le applicazioni che si basano su Azure AD per l'autenticazione devono essere registrate nella directory.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta della voce di delega  <br/> |Aggiungere una voce di delega  <br/> |Un'autorizzazione di autenticazione è stata creata/concessa a un'applicazione in Azure AD.  <br/> |
|Aggiunta dell'entità servizio  <br/> |Aggiungere l'entità servizio  <br/> |Un'applicazione è stata registrata in Azure AD. Un'applicazione è rappresentata da un'entità di servizio nella directory.  <br/> |
|Aggiunta di credenziali a un'entità di servizio  <br/> |Aggiungere le credenziali dell'entità servizio  <br/> |Le credenziali sono state aggiunte a un'entità di servizio in Azure AD. Un principio del servizio rappresenta un'applicazione nella directory.  <br/> |
|Voce di delega rimossa  <br/> |Rimuovi voce di delega  <br/> |Un'autorizzazione di autenticazione è stata rimossa da un'applicazione in Azure AD.  <br/> |
|Rimozione di un'entità di servizio dalla directory  <br/> |Rimuovi entità servizio  <br/> |Un'applicazione è stata eliminata o annullata la registrazione da Azure AD. Un'applicazione è rappresentata da un'entità di servizio nella directory.  <br/> |
|Credenziali rimosse da un'entità di servizio  <br/> |Rimuovere le credenziali dell'entità servizio  <br/> |Le credenziali sono state rimosse da un'entità di servizio in Azure AD. Un principio del servizio rappresenta un'applicazione nella directory.  <br/> |
|Impostare la voce di delega  <br/> |Impostare la voce di delega  <br/> |È stata aggiornata un'autorizzazione di autenticazione per un'applicazione in Azure AD.  <br/> |
||||

### <a name="role-administration-activities"></a>Attività di amministrazione del ruolo
  
Nella tabella seguente sono elencate le attività di amministrazione dei ruoli di Azure AD registrate quando un amministratore gestisce i ruoli di amministratore nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta di un membro a un ruolo  <br/> |Aggiungere un membro ruolo al ruolo  <br/> |Aggiunta di un utente a un ruolo di amministratore in Office 365.  <br/> |
|Rimozione di un utente da un ruolo di directory  <br/> |Rimuovi ruolo membro dal ruolo  <br/> |Rimozione di un utente da un ruolo di amministratore in Office 365.  <br/> |
|Impostare le informazioni di contatto della società  <br/> |Impostare le informazioni di contatto della società  <br/> |Sono state aggiornate le preferenze di contatto a livello aziendale per l'organizzazione di Office 365. Sono inclusi gli indirizzi di posta elettronica per i messaggi di posta elettronica relativi alla sottoscrizione inviati da Office 365, nonché le notifiche tecniche sui servizi di Office 365.  <br/> |
||||
   
### <a name="directory-administration-activities"></a>Attività di amministrazione della directory
  
Nella tabella seguente sono elencate le attività di directory e di dominio di Azure AD correlate registrate quando un amministratore gestisce la propria organizzazione di Office 365 nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta di un dominio alla società  <br/> |Aggiungere un dominio alla società  <br/> |È stato aggiunto un dominio all'organizzazione di Office 365.  <br/> |
|Aggiunta di un partner alla directory  <br/> |Aggiungere un partner alla società  <br/> |Aggiunta di un partner (amministratore delegato) alla propria organizzazione di Office 365.  <br/> |
|Dominio rimosso dalla società  <br/> |Rimuovi dominio dalla società  <br/> |È stato rimosso un dominio dall'organizzazione di Office 365.  <br/> |
|Rimosso un partner dalla directory  <br/> |Rimuovi partner dalla società  <br/> |È stato rimosso un partner (amministratore delegato) dall'organizzazione di Office 365.  <br/> |
|Impostare le informazioni sulla società  <br/> |Impostare le informazioni sulla società  <br/> |Sono state aggiornate le informazioni sulla società per l'organizzazione di Office 365. Sono inclusi gli indirizzi di posta elettronica per i messaggi di posta elettronica relativi alla sottoscrizione inviati da Office 365, nonché le notifiche tecniche sui servizi di Office 365.  <br/> |
|Impostare l'autenticazione del dominio  <br/> |Impostare l'autenticazione del dominio  <br/> |È stata modificata l'impostazione di autenticazione del dominio per l'organizzazione di Office 365.  <br/> |
|Aggiornamento delle impostazioni di federazione per un dominio  <br/> |Impostazione delle impostazioni di federazione sul dominio  <br/> |Sono state modificate le impostazioni di federazione (condivisione esterna) per l'organizzazione di Office 365.  <br/> |
|Impostare i criteri per le password  <br/> |Impostare i criteri per le password  <br/> |Sono stati modificati i vincoli di lunghezza e di carattere per le password degli utenti nell'organizzazione di Office 365.  <br/> |
|Attivata la sincronizzazione di Azure AD  <br/> |Impostare il flag DirSyncEnabled sulla società  <br/> |Impostare la proprietà che Abilita una directory per Azure AD Sync.  <br/> |
|Dominio aggiornato  <br/> |Aggiornamento del dominio  <br/> |Sono state aggiornate le impostazioni di un dominio nell'organizzazione di Office 365.  <br/> |
|Dominio verificato  <br/> |Verificare un dominio  <br/> |Verificato che l'organizzazione sia il proprietario di un dominio.  <br/> |
|Dominio verificato per la posta elettronica verificato  <br/> |Verificare il dominio verificato tramite posta elettronica  <br/> |Verifica della posta elettronica utilizzata per verificare che l'organizzazione sia il proprietario di un dominio.  <br/> |
||||
   
### <a name="ediscovery-activities"></a>attività di eDiscovery
  
Le attività relative alla ricerca e al contenuto di eDiscovery eseguite nel centro sicurezza e conformità o eseguendo i cmdlet di PowerShell corrispondenti vengono registrate nel registro di controllo. Sono incluse le attività seguenti:
  
- Creazione e gestione dei casi di eDiscovery
    
- Creazione, avvio e modifica di ricerche di contenuto
    
- Esecuzione di azioni di ricerca del contenuto, ad esempio la visualizzazione in anteprima, l'esportazione e l'eliminazione dei risultati della ricerca
    
- Configurazione del filtro delle autorizzazioni per la ricerca di contenuto
    
- Gestione del ruolo di amministratore di eDiscovery
    
Per un elenco e una descrizione dettagliata delle attività di eDiscovery registrate, vedere [cercare le attività di eDiscovery nel registro di controllo di Office 365](search-for-ediscovery-activities-in-the-audit-log.md).
  
> [!NOTE]
> Sono necessari fino a 30 minuti per gli eventi che risultano dalle attività elencate in **attività di eDiscovery** nell'elenco a discesa **attività** da visualizzare nei risultati della ricerca. Al contrario, sono necessari fino a 24 ore affinché gli eventi corrispondenti dalle attività del cmdlet di eDiscovery vengano visualizzati nei risultati della ricerca. 
  
### <a name="advanced-ediscovery-activities"></a>Attività avanzate di eDiscovery

Nella tabella seguente sono elencate le attività che derivano da IT e professionisti legali che eseguono attività in Advanced eDiscovery in Microsoft 365. Per ulteriori informazioni, vedere [Overview of the Advanced eDiscovery Solution in Microsoft 365](compliance20/overview-ediscovery-20.md).

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
| Aggiunta di dati a un altro set di Revisione<br/>         | AddWorkingSetQueryToWorkingSet<br/>  |  Gli utenti hanno aggiunto documenti da un set di revisione a un diverso set di revisione.<br/>|
| Aggiunta dei dati al set di Revisione <br/>                | AddQueryToWorkingSet<br/>            |  L'utente ha aggiunto i risultati della ricerca da una ricerca di contenuto associata a un caso avanzato di eDiscovery a un set di revisione.<br/>|
| Aggiunta dei dati non di Office 365 ai set di Revisione<br/>  | AddNonOffice365DataToWorkingSet<br/> |  L'utente ha aggiunto dati non di Office 365 a un set di revisione.<br/>|
| Aggiunta di documenti corretti al set di Revisione<br/> | AddRemediatedData<br/>               |  L'utente carica documenti con errori di indicizzazione che sono stati fissati a un set di revisione.<br/>|
| Dati analizzati nel set di Revisione <br/>             | RunAlgo<br/>                         |  L'utente ha eseguito l'analisi dei documenti in un set di revisione. <br/>|
| Documento con annotazioni nel set di Revisione <br/>        | AnnotateDocument<br/>                |  L'utente ha annotato un documento in un set di revisione. L'annotazione include il contenuto di relazioni in un documento. <br/>|
| Set di carichi confrontati <br/>                      | LoadComparisonJob<br/>               |L'utente ha confrontato due set di carico diversi in un set di revisione. Un set di carichi è il momento in cui i dati di una ricerca di contenuto associata al caso vengono aggiunti a un set di revisione.  <br/>|
| Convertito documenti redatti in formato PDF<br/>      | BurnJob<br/>                         |L'utente ha convertito tutti i documenti redatti in un set di revisione in file PDF.<br/>|
| Set di revisione creato<br/>                       | CreateWorkingSet<br/>                |L'utente ha creato un set di revisione.<br/>|
| Ricerca di set di revisione creata<br/>                | CreateWorkingSetSearch<br/>          |L'utente ha creato una query di ricerca che esegue la ricerca nei documenti in un set di revisione. <br/>|
| Tag creato<br/>                              | CreateTag<br/>                       |L'utente ha creato un gruppo di tag in un set di revisione. Un gruppo di tag può contenere uno o più tag figlio. Questi tag vengono quindi utilizzati per contrassegnare i documenti nel set di revisione.<br/>|
| Ricerca di set di revisione eliminata <br/>               | DeleteWorkingSetSearch<br/>          |L'utente ha eliminato una query di ricerca in un set di revisione.<br/>|
| Tag eliminato<br/>                              | DeleteTag<br/>                       |L'utente ha eliminato un tag o un gruppo di tag in un set di revisione.<br/>|
| Documento scaricato<br/>                      | DownloadDocument<br/>                |L'utente ha scaricato un documento da un set di revisione.<br/>|
| Tag modificato <br/>                              | DownloadDocument<br/>                |L'utente ha modificato un tag in un set di revisione.<br/>|
| Documenti esportati dal set di Revisione <br/>      | ExportJob<br/>                       |Documenti esportati dall'utente da un set di revisione.<br/>|
| Impostazione del caso modificato <br/>                   | UpdateCaseSettings<br/>              | L'utente ha modificato le impostazioni per un caso. Le impostazioni del caso includono le informazioni sui casi, le autorizzazioni di accesso e le impostazioni che controllano il comportamento di ricerca e analisi.<br/>|
| Ricerca modifica set di Revisione<br/>               | UpdateWorkingSetSearch<br/>          |  L'utente ha modificato una query di ricerca in un set di revisione.<br/>|
| Ricerca set di revisione in anteprima <br/>             | PreviewWorkingSetSearch<br/>         |  L'utente ha visualizzato in anteprima i risultati di una query di ricerca in un set di revisione.<br/>|
| Documenti di errore corretti <br/>              | ErrorRemediationJob<br/>             |  L'utente corregge i file che contengono errori di indicizzazione. <br/>|
| Documento con tag<br/>                          | TagFiles<br/>                        |  Tag utente un documento in un set di revisione.<br/>|
| Risultati di una query con tag<br/>                | TagJob<br/>                          |  Tag utente tutti i documenti che soddisfano i criteri di query di ricerca in un set di revisione.<br/>|
| Documento visualizzato nel set di Revisione<br/>            | ViewDocument<br/>                    |  L'utente ha visualizzato un documento in un set di revisione.<br/>|
|||

### <a name="power-bi-activities"></a>Attività di Power BI
  
È possibile eseguire una ricerca nel registro di controllo per le attività in Power BI. Per informazioni sulle attività di Power BI, vedere la sezione "attività controllate da Power Power BI" nell' [utilizzo del controllo all'interno dell'organizzazione](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi).
  
Si noti che la registrazione di controllo per Power BI non è abilitata per impostazione predefinita. Per cercare le attività di Power BI nel log di controllo di Office 365, è necessario abilitare il controllo nel portale di amministrazione di Power BI. Per istruzioni, vedere la sezione relativa ai registri di controllo in [Power Bi Admin Portal](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).
  
### <a name="microsoft-workplace-analytics-activities"></a>Attività di analisi del luogo di lavoro Microsoft

L'analisi dei luoghi di lavoro fornisce informazioni su come i gruppi collaborano nell'organizzazione di Office 365. Nella tabella seguente sono elencate le attività eseguite dagli utenti a cui è assegnato il ruolo di amministratore o i ruoli dell'analista nell'analisi dei luoghi di lavoro. Gli utenti assegnati al ruolo Analyst hanno accesso completo a tutte le funzionalità del servizio e utilizzano il prodotto per eseguire l'analisi. Gli utenti assegnati al ruolo di amministratore possono configurare le impostazioni di privacy e i valori predefiniti del sistema e possono preparare, caricare e verificare i dati dell'organizzazione nell'analisi dei luoghi di lavoro. Per maggiori informazioni, vedere [Workplace Analytics](https://docs.microsoft.com/en-us/workplace-analytics/index-orig).

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Collegamento OData con accesso <br/> |AccessedOdataLink <br/> |Analista ha eseguito il collegamento OData per una query.|
|Query annullata <br/> |CanceledQuery <br/> |Analista ha annullato una query in esecuzione.|
|Esclusione della riunione creata <br/> |MeetingExclusionCreated <br/> |Analyst ha creato una nuova regola di esclusione delle riunioni.|
|Risultato eliminato <br/> |DeletedResult <br/> |Analista ha eliminato un risultato di query.|
|Report scaricato <br/> |DownloadedReport <br/> |Analista ha scaricato un file dei risultati della query.|
|Query eseguita <br/> |ExecutedQuery <br/> |Analista ha eseguito una query.|
|Impostazioni di accesso ai dati aggiornate <br/> |UpdatedDataAccessSetting <br/> |Impostazioni di accesso ai dati aggiornate dall'amministratore.|
|Impostazione privacy aggiornata <br/> |UpdatedPrivacySetting <br/> |Impostazioni di privacy aggiornate dall'amministratore; ad esempio, dimensioni minime del gruppo.|
|Dati dell'organizzazione caricati <br/> |UploadedOrgData <br/> |File di dati dell'organizzazione caricato dall'amministratore.|
|Visualizzazione Esplora <br/> |ViewedExplore <br/> |Visualizzazioni degli analisti visualizzati in una o più schede di pagina Esplora.|
||||

### <a name="microsoft-teams-activities"></a>Attività di Microsoft Teams
  
Nella tabella seguente sono elencate le attività di utenti e amministratori in Microsoft teams registrate nel registro di controllo di Office 365. Microsoft teams è un'area di lavoro con centro chat in Office 365. Questo porta le conversazioni, le riunioni, i file e le note di un team in un'unica posizione. Per ulteriori informazioni e collegamenti agli argomenti della guida, vedere:
  
- [Domande frequenti su Microsoft Teams-Guida per gli amministratori](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)
    
- [Guida di Microsoft Teams](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta di bot al team  <br/> |BotAddedToTeam  <br/> |Un utente aggiunge un bot a un team.  <br/> |
|Canale aggiunto  <br/> |ChannelAdded  <br/> |Un utente aggiunge un canale a un team.  <br/> |
|Connettore aggiunto  <br/> |ConnectorAdded  <br/> |Un utente aggiunge un connettore a un canale.  <br/> |
|Aggiunta di membri al team  <br/> |MemberAdded  <br/> |Un proprietario del team aggiunge i membri a un team.  <br/> |
|Scheda aggiunta  <br/> |TabAdded  <br/> |Un utente aggiunge una tabulazione a un canale.  <br/> |
|Impostazione del canale modificata  <br/> |ChannelSettingChanged  <br/> | L'operazione ChannelSettingChanged viene registrata quando i membri del team eseguono le attività seguenti. Per ognuna di queste attività, nella colonna **elemento** dei risultati di ricerca del registro di controllo viene visualizzata una descrizione dell'impostazione modificata, visualizzata tra parentesi.  <br/> <br/>-Cambia il nome di un canale del team ( **nome del canale**).  <br/>  <br/>-Modifica la descrizione di un canale del team ( **Descrizione del canale**).  <br/> |
|Impostazione dell'organizzazione modificata  <br/> |TeamsTenantSettingChanged  <br/> | L'operazione TeamsTenantSettingChanged viene registrata quando le attività seguenti vengono eseguite da un amministratore globale (utilizzando l'interfaccia di amministrazione di Microsoft 365). Si noti che queste attività incidono sulle impostazioni di Microsoft Teams a livello dell'organizzazione. Per ulteriori informazioni, vedere [impostazioni di amministratore per Microsoft teams](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2).  <br/>  Per ognuna di queste attività, nella colonna **elemento** dei risultati di ricerca del registro di controllo viene visualizzata una descrizione dell'impostazione modificata, visualizzata tra parentesi.  <br/><br/>-Consente di abilitare o disabilitare Microsoft teams per l'organizzazione ( **Microsoft teams**).  <br/><br/>-Consente di abilitare o disabilitare l'interoperabilità tra Microsoft teams e Skype for business per l'organizzazione (interoperabilità **Skype for business**).<br/><br/>-Abilita o Disabilita la visualizzazione organigramma nei client Microsoft Teams ( **org Chart View**).  <br/><br/>-Abilita o Disabilita la possibilità per i membri del team di pianificare riunioni private ( **pianificazione riunione privata**).  <br/><br/>-Abilita o Disabilita la possibilità per i membri del team di pianificare le riunioni dei canali (pianificazione delle riunioni di **canale**).  <br/><br/>-Abilita o Disabilita la videochiamata nelle riunioni dei team ( **video per le riunioni Skype**).  <br/><br/>-Abilita o Disabilita la condivisione dello schermo nei Meetup di Microsoft teams per l'organizzazione ( **condivisione dello schermo per le riunioni Skype**).  <br/><br/>-Abilita o Disabilita la possibilità di aggiungere immagini animate (denominate Giphys) a conversazioni di Teams ( **Immagini animate**).  <br/><br/>-Modifica l'impostazione di valutazione del contenuto per l'organizzazione ( **valutazione del contenuto**). La valutazione del contenuto limita il tipo di immagine animata che può essere visualizzata nelle conversazioni.  <br/><br/>-Abilita o Disabilita la possibilità per i membri del team di aggiungere immagini personalizzabili (denominate memi personalizzati) da Internet alle conversazioni del team ( **Immagini personalizzabili da Internet**).  <br/><br/>-Abilita o Disabilita la possibilità per i membri del team di aggiungere immagini modificabili (denominate adesivi) alle conversazioni del team ( **immagini modificabili**).<br/><br/>-Abilita o Disabilita la possibilità per i membri del team di usare i bot nelle chat e nei canali di Microsoft Teams ( **bot a livello di organizzazione**).<br/><br/>-Abilita bot specifici per Microsoft Teams; Questo non include il T-bot, che è teams Help bot disponibile quando i bot sono abilitati per l'organizzazione ( **singoli bot**).  <br/><br/>-Abilita o Disabilita la possibilità per i membri del team di aggiungere estensioni o tabulazioni ( **estensioni o tabulazioni**).  <br/><br/>-Attiva o disattiva il caricamento laterale dei bot proprietari per Microsoft Teams ( **caricamento laterale dei bot**).  <br/><br/>-Abilita o Disabilita la possibilità per gli utenti di inviare messaggi di posta elettronica a un canale Microsoft Teams ( **canale di posta elettronica**).  <br/> |
|Ruolo cambiato dei membri del team  <br/> |MemberRoleChanged  <br/> |Un proprietario del team modifica il ruolo dei membri di un team. I valori riportati di seguito indicano il tipo di ruolo assegnato all'utente.  <br/><br/><br/> **1** -indica il ruolo del proprietario.<br/>**2** -indica il ruolo del membro. <br/>**3** -indica il ruolo Guest. <br/>La proprietà Members include anche il nome dell'organizzazione e l'indirizzo di posta elettronica del membro.  <br/> |
|Impostazione del team modificata  <br/> |TeamSettingChanged  <br/> | L'operazione TeamSettingChanged viene registrata quando le attività seguenti vengono eseguite da un proprietario del team. Per ognuna di queste attività, nella colonna **elemento** dei risultati di ricerca del registro di controllo viene visualizzata una descrizione dell'impostazione modificata, visualizzata tra parentesi.  <br/><br/>-Cambia il tipo di accesso per un team. I team possono essere impostati come privato o pubblico ( **tipo di accesso del team**). Quando un team è privato (impostazione predefinita), gli utenti possono accedere al team solo tramite invito. Quando un team è pubblico, è individuabile da tutti gli utenti.  <br/><br/>-Modifica la classificazione delle informazioni di un team ( **classificazione del team**).  <br/>  I dati del team, ad esempio, possono essere classificati come impatto aziendale elevato, impatto aziendale medio o impatto aziendale basso.<br/><br/>-Cambia il nome di un team ( **nome del team**).  <br/><br/>-Modifica la descrizione del team ( **Descrizione del team**). <br/><br/>-Modifiche apportate a una qualsiasi delle impostazioni del team. Un proprietario del team può accedere a queste impostazioni in un client di team facendo clic con il pulsante destro del mouse su un team, scegliendo **Gestisci team**e quindi facendo clic sulla scheda **Impostazioni** . Per queste attività, il nome dell'impostazione modificata viene visualizzato nella colonna **elemento** dei risultati di ricerca del registro di controllo.  <br/> |
|Team creato  <br/> |TeamCreated  <br/> |Un utente crea un nuovo team.  <br/> |
|Canale eliminato  <br/> |ChannelDeleted  <br/> |Un utente elimina un canale da un team.  <br/> |
|Team eliminato  <br/> |TeamDeleted  <br/> |Un proprietario del team Elimina un team.  <br/> |
|Rimozione del bot dal team  <br/> |BotRemovedFromTeam  <br/> |Un utente rimuove un bot da un team.  <br/> |
|Connettore rimosso  <br/> |ConnectorRemoved  <br/> |Un utente rimuove il connettore da un canale.  <br/> |
|Membri rimossi dal team  <br/> |MemberRemoved  <br/> |Un proprietario del team rimuove i membri di un team.  <br/> |
|Scheda rimossa  <br/> |TabRemoved  <br/> |Un utente rimuove una scheda da un canale.  <br/> |
|Connettore aggiornato  <br/> |ConnectorUpdated  <br/> |Un utente ha modificato un connettore in un canale.  <br/> |
|Scheda aggiornato  <br/> |TabUpdated  <br/> |Un utente ha modificato una scheda in un canale.  <br/> |
|L'utente ha eseguito l'accesso ai team  <br/> |TeamsSessionStarted  <br/> |Un utente accede a un client Microsoft teams.  <br/> |
||||

### <a name="yammer-activities"></a>Attività di Yammer
  
Nella tabella seguente sono elencate le attività dell'utente e dell'amministratore in Yammer registrate nel registro di controllo di Office 365. Per restituire le attività relative a Yammer dal registro di controllo di Office 365, è necessario selezionare **Mostra risultati per tutte le attività** nell'elenco **attività** . Utilizzare le caselle Intervallo di date e l'elenco **utenti** per restringere i risultati della ricerca. 
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Criteri di conservazione dei dati modificati  <br/> |SoftDeleteSettingsUpdated  <br/> |L'amministratore verificato aggiorna l'impostazione per i criteri di conservazione dei dati di rete su Elimina o Elimina temporaneamente. Solo gli amministratori verificati sono in grado di eseguire questa operazione.  <br/> |
|Configurazione di rete modificata  <br/> |NetworkConfigurationUpdated  <br/> |La rete o l'amministratore verificato modifica la configurazione della rete Yammer. Questo include l'impostazione dell'intervallo per l'esportazione dei dati e l'abilitazione della chat.  <br/> |
|Impostazioni del profilo di rete modificate  <br/> |ProcessProfileFields  <br/> |La rete o l'amministratore verificato modifica le informazioni visualizzate nei profili membri per la rete degli utenti di rete.  <br/> |
|Modalità di contenuto privato modificata  <br/> |SupervisorAdminToggled  <br/> |L'amministratore verificato attiva o disattiva la *modalità di contenuto privato* . Questa modalità consente a un amministratore di visualizzare i post in gruppi privati e di visualizzare i messaggi privati tra singoli utenti (o gruppi di utenti). Solo gli amministratori verificati sono in grado di eseguire questa operazione.  <br/> |
|Configurazione della sicurezza modificata  <br/> |NetworkSecurityConfigurationUpdated  <br/> |L'amministratore verificato aggiorna la configurazione di sicurezza della rete Yammer. Questo include l'impostazione di criteri di scadenza delle password e restrizioni sugli indirizzi IP. Solo gli amministratori verificati sono in grado di eseguire questa operazione.  <br/> |
|File creato  <br/> |Filecreato  <br/> |L'utente carica un file.  <br/> |
|Gruppo creato  <br/> |GroupCreation  <br/> |L'utente crea un nuovo gruppo.  <br/> |
|Gruppo eliminato  <br/> |GroupDeletion  <br/> |Un gruppo viene eliminato da Yammer.  <br/> |
|Messaggio eliminato  <br/> |MessageDeleted  <br/> |L'utente elimina un messaggio.  <br/> |
|File scaricato  <br/> |Filedownloaded  <br/> |L'utente scarica un file.  <br/> |
|Dati esportati  <br/> |DataExport  <br/> |L'amministratore verificato Esporta i dati di rete di Yammer. Solo gli amministratori verificati sono in grado di eseguire questa operazione.  <br/> |
|File condiviso  <br/> |Fileshared  <br/> |L'utente condivide un file con un altro utente.  <br/> |
|Utente della rete sospesa  <br/> |NetworkUserSuspended  <br/> |La rete o l'amministratore verificato sospende (Disattiva) un utente di Yammer.  <br/> |
|Utente sospeso  <br/> |UserSuspension  <br/> |L'account utente è sospeso (disattivata).  <br/> |
|Descrizione file aggiornata  <br/> |FileUpdateDescription  <br/> |L'utente modifica la descrizione di un file.  <br/> |
|Nome file aggiornato  <br/> |Fileupdatename  <br/> |L'utente modifica il nome di un file.  <br/> |
|File visualizzato  <br/> |Filevisiting  <br/> |L'utente visualizza un file.  <br/> |
||||
   
### <a name="microsoft-flow-activities"></a>Attività di flusso Microsoft

È possibile eseguire una ricerca nel registro di controllo per le attività in Microsoft Flow. Tali attività includono la creazione, la modifica e l'eliminazione dei flussi e la modifica delle autorizzazioni di flusso. Per informazioni sul controllo per le attività di flusso, vedere il Blog [Microsoft Flow Audit Events now available in Security _AMP_ Compliance Center](https://flow.microsoft.com/blog/security-and-compliance-center).

### <a name="microsoft-powerapps"></a>Microsoft PowerApps

È possibile eseguire una ricerca nel registro di controllo per le attività relative all'applicazione in PowerApps. Tali attività includono la creazione, l'avvio e la pubblicazione di un'app. Anche l'assegnazione delle autorizzazioni per le app è controllata. Per una descrizione di tutte le attività di PowerApps, vedere [registrazione attività per PowerApps](https://docs.microsoft.com/en-us/power-platform/admin/logging-powerapps#what-events-are-audited).

### <a name="microsoft-stream-activities"></a>Attività di Microsoft Stream
  
È possibile eseguire una ricerca nel registro di controllo per le attività in Microsoft Stream. Tali attività includono attività video eseguite da utenti, attività di canale di gruppo e attività amministrative quali la gestione degli utenti, la gestione delle impostazioni dell'organizzazione e l'esportazione di report. Per una descrizione di queste attività, vedere la sezione "attività registrate in Microsoft Stream" nei [registri di controllo in Microsoft Stream](https://docs.microsoft.com/stream/audit-logs).

### <a name="exchange-admin-audit-log"></a>Log di controllo dell'amministratore di Exchange
  
La registrazione di controllo dell'amministratore di Exchange, abilitata per impostazione predefinita in Office 365, consente di registrare un evento nel registro di controllo di Office 365 quando un amministratore (o un utente a cui sono state assegnate autorizzazioni amministrative) apporta una modifica all'organizzazione di Exchange Online. Le modifiche apportate mediante l'interfaccia di amministrazione di Exchange o l'esecuzione di un cmdlet in Windows PowerShell vengono registrate nel registro di controllo di amministrazione di Exchange. Per informazioni più dettagliate sulla registrazione dei controlli di amministrazione in Exchange, vedere [registrazione di controllo dell'amministratore](https://go.microsoft.com/fwlink/p/?LinkID=619225).
  
Di seguito sono riportate alcune indicazioni per la ricerca di attività nel log di controllo di amministrazione di Exchange:
  
- Per restituire le voci dal registro di controllo di amministrazione di Exchange, è necessario selezionare **Mostra risultati per tutte le attività** nell'elenco **attività** . Utilizzare le caselle Intervallo di date e l'elenco **utenti** per limitare i risultati della ricerca per i cmdlet eseguiti da un amministratore di Exchange specifico all'interno di un intervallo di date specifico. 
    
- Per visualizzare gli eventi dal registro di controllo di amministrazione di Exchange, filtrare i risultati della **-** ricerca e digitare a (Dash) nella casella filtro **attività** . Verranno visualizzati i nomi dei cmdlet, che sono mostrati nella colonna **attività** per gli eventi di amministrazione di Exchange. È quindi possibile ordinare i nomi dei cmdlet in ordine alfabetico. 
    
    ![Digitare un trattino nella casella attività per filtrare gli eventi di amministrazione di Exchange](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)
  
- Per ottenere informazioni su quale cmdlet è stato eseguito, quali parametri e valori di parametro sono stati utilizzati e quali oggetti sono stati interessati, sarà necessario esportare i risultati della ricerca e selezionare l'opzione **Scarica tutti i risultati** . 
    
- È inoltre possibile visualizzare gli eventi nel registro di controllo di amministrazione di Exchange utilizzando l'interfaccia di amministrazione di Exchange. Per istruzioni, vedere [visualizzare il registro di controllo dell'amministratore](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx).
  
## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove è possibile trovare informazioni sulle caratteristiche offerte dal servizio di controllo di Office 365?**

Per ulteriori informazioni sulle funzionalità di controllo e Reporting disponibili in Office 365, vedere [Auditing and Reporting in office 365](office-365-auditing-and-reporting-overview.md). 

**Quali sono i diversi servizi di Office 365 attualmente controllati?**

I servizi di Office 365 più utilizzati come Exchange Online, SharePoint Online, OneDrive for business, Azure Active Directory, Microsoft teams, Dynamics 365, Advanced Threat Protection e Power BI sono controllati. Vedere l' [inizio di questo articolo](search-the-audit-log-in-security-and-compliance.md) per un elenco dei servizi controllati.

**Quali attività vengono controllate tramite il servizio di controllo in Office 365?**

Vedere la sezione [attività controllate](#audited-activities) in questo articolo per un elenco e una descrizione delle attività controllate in Office 365.

**Quanto tempo occorre per rendere disponibile un record di controllo dopo che si è verificato un evento?**

La maggior parte dei dati di controllo è disponibile entro 30 minuti, ma potrebbe richiedere fino a 24 ore dopo che si è verificato un evento per la voce del registro di controllo corrispondente da visualizzare nei risultati della ricerca. Vedere la tabella nella sezione [prima di iniziare](#before-you-begin) di questo articolo, che mostra il tempo necessario per la disponibilità di eventi nei diversi servizi di Office 365.

**Per quanto tempo vengono mantenuti i record di controllo?**

Come spiegato in precedenza, il periodo di conservazione dei record di controllo dipende dall'abbonamento a Office 365 dell'organizzazione.  

- **Office 365 E3** -i record di controllo vengono conservati per 90 giorni.

- I record di controllo di **Office 365 E5** vengono conservati anche per 90 giorni. La conservazione dei record di controllo per un anno può essere eventualmente disponibile per gli utenti e gli utenti di E5 con una licenza E3 e una licenza per il componente aggiuntivo per la conformità avanzata di Office 365.

     > [!NOTE]
     > Come spiegato in precedenza, il programma di anteprima privata per il periodo di conservazione di un anno per i record di controllo per le organizzazioni E5 (o le organizzazioni E3 con licenze per i componenti aggiuntivi per la conformità avanzate) è chiuso alla nuova registrazione. Questo articolo verrà aggiornato quando il periodo di conservazione di un anno è disponibile in anteprima pubblica o rilasciato per la disponibilità generale.

Si noti inoltre che la durata del periodo di conservazione per i record di controllo si basa sulla gestione delle licenze per utente. Ad esempio, se a un utente dell'organizzazione è assegnata una licenza di Office 365 E3 o E5, i record di controllo per le attività eseguite dall'utente vengono conservati per 90 giorni.

**È possibile accedere ai dati di controllo a livello di programmazione?**

Sì. L'API di attività di gestione di Office 365 viene utilizzata per recuperare i registri di controllo a livello di programmazione.  Per iniziare, vedere [Introduzione a Office 365 Management Apis](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

**Esistono altri modi per ottenere registri di controllo diversi da quelli utilizzati dal centro sicurezza e conformità o dall'API di attività di gestione di Office 365?**

No. Questi sono gli unici due modi per ottenere i dati dal servizio di controllo di Office 365. 

**È necessario abilitare singolarmente il controllo in ogni servizio di cui si desidera acquisire I registri di controllo?**

Nella maggior parte dei servizi di Office 365, il controllo è abilitato per impostazione predefinita dopo l'attivazione iniziale del controllo per l'organizzazione di Office 365, come descritto nella sezione [prima di iniziare](#before-you-begin) in questo articolo. Tuttavia, è necessario abilitare il controllo delle cassette postali in Exchange Online per ogni cassetta postale che si desidera controllare.   Per impostazione predefinita, viene attivato il controllo delle cassette postali per tutte le cassette postali in un'organizzazione di Office 365. Per ulteriori informazioni, vedere "il controllo delle cassette postali di Exchange verrà abilitato per impostazione predefinita" nel [Blog Microsoft sulla sicurezza, la privacy e la conformità](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Exchange-Mailbox-Auditing-will-be-enabled-by-default/ba-p/215171).

**Il servizio di controllo di Office 365 supporta la deduplicazione dei record?**

No. La pipeline del servizio di controllo è quasi in tempo reale e pertanto non è in grado di supportare la deduplicazione.
 
**Office 365 controlla il flusso di dati tra aree geografiche?**

No. Al momento sono presenti distribuzioni di pipeline di controllo nelle aree NA (Nord America), EMEA (Europa, Medio Oriente e Africa) e APAC (Asia-Pacifico). Tuttavia, è possibile che il flusso dei dati tra queste aree venga eseguito per il bilanciamento del carico e solo durante i problemi del sito Live. Quando eseguiamo queste attività, i dati in transito sono crittografati.   
 
**I dati di controllo sono crittografati?**

I dati di controllo vengono archiviati nelle cassette postali di Exchange (dati a riposo) nella stessa area in cui viene distribuita la pipeline di controllo. Questi dati non sono crittografati. Tuttavia, i dati in transito sono sempre crittografati. 
