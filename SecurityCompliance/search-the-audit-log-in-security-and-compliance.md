---
title: Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365AC_AlternativeEmailAddress
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: "Utilizzare la protezione di Office 365 &amp; centro conformità per cercare il Registro di controllo unificato per visualizzare l'attività di utenti e amministratori nella propria organizzazione Office 365. "
ms.openlocfilehash: 3fe8b4ade1b82cc76fcc300284127693b7e5fc07
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530450"
---
# <a name="search-the-audit-log-in-the-office-365-security-amp-compliance-center"></a>Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità di Office 365

Sai dove trovare se un utente di visualizzata un documento specifico o eliminato un elemento dalla cassetta postale? Se, utilizzare la protezione di Office 365 &amp; centro conformità per cercare il Registro di controllo unificato per visualizzare l'attività di utenti e amministratori nella propria organizzazione Office 365. Perché un controllo unificato accedere? Dal momento che è possibile cercare i tipi di attività di amministrazione e utente in Office 365 seguenti:
  
- Attività dell'utente in SharePoint Online e OneDrive for Business
    
- Attività degli utenti in Exchange Online (registrazione di controllo delle cassette postali di Exchange)
    
    > [!IMPORTANT]
    > Controllo delle cassette postali registrazione deve essere attivata per ciascuna cassetta postale utente prima che verrà eseguito l'attività dell'utente in Exchange Online. Per ulteriori informazioni, vedere [abilitare il controllo in Office 365](enable-mailbox-auditing.md).
  
- Attività di amministrazione di SharePoint Online
    
- Attività di amministrazione di Azure Active Directory (il servizio directory per Office 365)
    
- Attività di amministrazione di Exchange Online (registrazione di controllo dell'amministratore di Exchange)
    
- Attività di amministratore e utente oscillazione
    
- attività di eDiscovery in Office 365 Security &amp; centro conformità
    
- Attività di amministrazione e utente in Power BI per Office 365
    
- Attività amministratore e utente in Microsoft Teams
    
- Attività di amministrazione e utente in Yammer
    
- Attività di amministratore e utente Stream Microsoft
    
   
## <a name="before-you-begin"></a>Informazioni preliminari

Assicurarsi di leggere gli elementi seguenti prima di iniziare la ricerca di Office 365 Registro di controllo.
  
- Utente (o un'altra amministrazione) necessario attivare la registrazione di controllo prima di iniziare la ricerca nel Registro di controllo di Office 365. Per attivarlo, fare clic su * * avviare la registrazione delle attività di amministrazione e utente * * nella pagina **ricerca dei registri di controllo** della protezione &amp; centro conformità. (Se non viene visualizzato questo collegamento, il controllo è già stato attivato per la propria organizzazione.) Una volta abilitata, verrà visualizzato un messaggio che informa che il Registro di controllo per la preparazione e che è possibile eseguire una ricerca di due ore dopo aver completata la preparazione. È necessario eseguire questa operazione una sola volta. 
    
    > [!NOTE]
    > È possibile aprire il processo di attivazione del controllo per impostazione predefinita. Nel frattempo, è possibile attivarlo come descritto in precedenza. 
  
- È necessario disporre del ruolo registri di controllo View-Only o i registri di controllo di Exchange Online per la ricerca nel Registro di controllo di Office 365. Per impostazione predefinita, questi ruoli vengono assegnati a gruppi di ruolo Gestione della conformità e la gestione dell'organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Per assegnare a un utente la possibilità di eseguire ricerche nel Registro di controllo di Office 365 con il livello minimo di privilegi, è possibile creare un gruppo di ruoli personalizzati in Exchange Online, aggiungere il ruolo registri di controllo View-Only o i registri di controllo e quindi aggiungere l'utente come membri del nuovo gruppo di ruoli. Per ulteriori informazioni, vedere [gruppi di ruoli di gestione in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).
    
    > [!IMPORTANT]
    > Se si assegna un utente il ruolo registri di controllo View-Only o i registri di controllo nella pagina **autorizzazioni** di sicurezza &amp; centro conformità, non saranno in grado di eseguire ricerche nel Registro di controllo di Office 365. È necessario assegnare le autorizzazioni in Exchange Online. Ciò avviene perché il cmdlet sottostante utilizzato per cercare il Registro di controllo è un cmdlet di Exchange Online. 
  
- Se si desidera disattivare la ricerca dei registri di controllo in Office 365 per l'organizzazione, è possibile eseguire il seguente comando di PowerShell remoto connesso all'organizzazione Exchange Online:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Per attivare controllo ricerca nuovamente, è possibile eseguire il seguente comando in Exchange Online PowerShell:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

    Per ulteriori informazioni, vedere [disattivare la ricerca dei registri di controllo in Office 365](turn-audit-log-search-on-or-off.md).
    
- Come descritto in precedenza, il cmdlet sottostante utilizzato per cercare il Registro di controllo è un cmdlet di Exchange Online, ovvero **UnifiedAuditLog di ricerca**. Che indica che è possibile utilizzare questo cmdlet per la ricerca nel Registro di controllo di Office 365 anziché utilizzare la pagina di **ricerca dei registri di controllo** della protezione &amp; centro conformità. È necessario eseguire questo cmdlet di PowerShell remoto connesso all'organizzazione Exchange Online. Per ulteriori informazioni, vedere [UnifiedAuditLog di ricerca](https://go.microsoft.com/fwlink/p/?linkid=834776).
    
- Se si desidera scaricare a livello di programmazione i dati dal Registro di controllo di Office 365, è consigliabile utilizzare l'API di Office 365 Gestione attività anziché utilizzare uno script di PowerShell. L'API di Office 365 Gestione attività è un servizio web REST che è possibile utilizzare per lo sviluppo di soluzioni di monitoraggio di conformità per l'organizzazione, sicurezza e operazioni. Per ulteriori informazioni, vedere [Guida di riferimento API di attività di gestione di Office 365](https://go.microsoft.com/fwlink/?linkid=852309).
    
- È possibile cercare il Registro di controllo di Office 365 per le attività che sono state eseguite negli ultimi 90 giorni.
    
- Potrebbe richiedere fino a 30 minuti o up a 24 ore dopo l'evento si verifica per la voce del Registro di controllo corrispondente da visualizzare nei risultati della ricerca. Nella tabella seguente mostra il tempo che necessario per i diversi servizi in Office 365.
    
|**Servizio Office 365**|**30 minuti**|**24 ore**|
|:-----|:-----|:-----|
|Azure Active Directory (amministrazione eventi)  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Azure Active Directory (gli eventi account di accesso dell'utente)  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Exchange Online  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Microsoft Teams  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Power BI  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Protezione &amp; centro conformità  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|SharePoint Online e OneDrive for Business  <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Sway  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Yammer  <br/> ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
- Azure Active Directory (Azure Active Directory) è il servizio directory per Office 365. Il Registro di controllo unificato contiene utente, gruppo, applicazione, dominio e directory attività eseguite nell'interfaccia di amministrazione di Office 365 o in Azure nel portale di gestione. Per un elenco completo degli eventi di Azure Active Directory, vedere [Eventi di Azure Active Directory di controllo Report](https://go.microsoft.com/fwlink/p/?LinkID=616549).
    
- I registri di controllo Exchange Online è costituita da due tipi di eventi: Exchange admin eventi (azioni eseguite dagli amministratori) e delle cassette postali (azioni eseguite dagli utenti di cassette postali). Si noti che il controllo delle cassette postali non è abilitato per impostazione predefinita. È necessario abilitare per ciascuna cassetta postale utente prima di eventi delle cassette postali da cercare nel Registro di controllo di Office 365. Per ulteriori informazioni sul controllo delle cassette postali e la cassetta postale il controllo delle azioni connessi, vedere [abilitare il controllo in Office 365](enable-mailbox-auditing.md).
    
- Registrazione di controllo per Power BI non è abilitata per impostazione predefinita. Per eseguire la ricerca per le attività di Power BI nel Registro di controllo di Office 365, è necessario attivare il controllo nel portale di amministrazione di Power BI. Per ulteriori informazioni, vedere [Controllo Power BI](https://docs.microsoft.com/power-bi/service-admin-auditing#enabling-auditing-functionality-in-the-power-bi-admin-portal).
    
    
## <a name="search-the-audit-log"></a>Cercare i log di controllo

Di seguito è il processo per la ricerca nel Registro di controllo in Office 365.
  
[Passaggio 1: Eseguire una ricerca dei registri di controllo](#step-1-run-an-audit-log-search)
  
[Passaggio 2: Visualizzare i risultati della ricerca](#step-2-view-the-search-results)

[Passaggio 3: Filtrare i risultati della ricerca](#step-3-filter-the-search-results)

[Passaggio 4: Esportare i risultati della ricerca in un file](#step-4-export-the-search-results-to-a-file)
  
### <a name="step-1-run-an-audit-log-search"></a>Passaggio 1: Eseguire una ricerca dei registri di controllo

1. Accedere a [https://protection.office.com](https://protection.office.com).
    
    > [!TIP]
    > Utilizzare una sessione di esplorazione privata (non regolare sessione) per accedere a Office 365 Security &amp; Allinea al centro conformità perché questo modo si eviteranno le credenziali che è stato eseguito l'accesso con è vietato. Per aprire una sessione di esplorazione InPrivate in Internet Explorer o Microsoft Edge, è sufficiente premere CTRL + MAIUSC + P. Per aprire una sessione di esplorazione privata in Google Chrome (noti come una finestra incognito), premere CTRL + MAIUSC + N. 
  
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini**e quindi fare clic su **ricerca dei registri di controllo**.
    
    Verrà visualizzata la pagina di **ricerca dei registri di controllo** . 
    
    ![Configurare criteri e quindi scegliere Cerca per eseguire report](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
    > [!NOTE]
    > È necessario prima abilita la registrazione di controllo prima di eseguire una ricerca dei registri di controllo. Se viene visualizzato il collegamento **avviare la registrazione utente e all'attività di amministrazione** , fare clic per attivare il controllo. Se non viene visualizzato questo collegamento, il controllo è già stato attivato per la propria organizzazione. 
  
4. Configurare i criteri di ricerca seguenti:
    
1. **Attività** Fare clic sull'elenco a discesa per visualizzare le attività che è possibile cercare. Attività degli utenti e amministratori sono organizzate in gruppi di attività correlate. È possibile selezionare attività specifiche oppure è possibile scegliere il nome del gruppo di attività per selezionare tutte le attività nel gruppo. È inoltre possibile fare clic su un'attività selezionata per annullare la selezione. Dopo aver eseguito la ricerca, vengono visualizzate solo le voci del Registro di controllo per le attività selezionate. Selezionare **Mostra i risultati per tutte le attività** visualizzerà i risultati per tutte le attività eseguite dall'utente selezionato o gruppo di utenti. 
    
    Attività degli utenti e amministratori oltre 100 vengono registrate nel Registro di controllo di Office 365. Fare clic sulla scheda **attività Audited** all'argomento di questo articolo per vedere le descrizioni di ogni attività in ognuno dei diversi servizi di Office 365. 
    
2. **Data di inizio** e **Data fine** ultimi sette giorni sono selezionati per impostazione predefinita. Selezionare un intervallo di data e ora per visualizzare gli eventi che si sono verificati durante questo periodo. Data e ora sono disponibili in formato ora UTC (Coordinated Universal Time). L'intervallo di date massimo che è possibile specificare è 90 giorni. Viene visualizzato un errore se l'intervallo di date selezionato è maggiore di 90 giorni. 
    
    > [!TIP]
    > Se si utilizza l'intervallo di date numero massimo di 90 giorni, selezionare l'ora corrente per la **Data di inizio**. In caso contrario, viene visualizzato un errore indicante che la data di inizio è precedente alla data di fine. Se è stato attivato il controllo negli ultimi 90 giorni, l'intervallo di date massimo non può avviare prima della data che il controllo è stato attivato. 
  
3. **Utenti** Fare clic su in questa casella e quindi selezionare uno o più utenti da visualizzare i risultati della ricerca. Le voci del Registro di controllo per l'attività selezionata eseguite dagli utenti che selezionare questa casella vengono visualizzate nell'elenco dei risultati. Lasciare vuoto questo per restituire le voci per tutti gli utenti (e gli account di servizio) nella propria organizzazione. 
    
4. **File o una cartella** Digitare parte o un nome file o una cartella per cercare le attività relative al file della cartella che contiene la parola chiave specificata. È inoltre possibile specificare un URL di un file o cartella. Se si utilizza un URL, assicurarsi che il tipo di percorso URL completo o se si digita solo una parte dell'URL, non includere spazi o caratteri speciali. 
    
    Lasciare vuoto questo per restituire le voci per tutti i file e cartelle all'interno dell'organizzazione.
    
5. Fare clic su **ricerca** per eseguire la ricerca utilizzando i criteri di ricerca. 
    
    I risultati della ricerca sono stati caricati e dopo pochi secondi vengono visualizzati nell'area **risultati**. Al termine della ricerca, viene visualizzato il numero di risultati trovati. Si noti che un massimo di 5.000 eventi verrà visualizzato nel riquadro **dei risultati** in incrementi di 150 in caso contrario. Se più di 5.000 eventi soddisfano i criteri di ricerca, vengono visualizzati gli eventi di 5.000 più recenti. 
    
    ![Il numero di risultati viene visualizzato al termine della ricerca](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)
  
  
#### <a name="tips-for-searching-the-audit-log"></a>Suggerimenti per la ricerca nel Registro di controllo

- È possibile selezionare attività specifiche da cercare facendo clic sul nome dell'attività. Oppure è possibile cercare tutte le attività in un gruppo (ad esempio **le attività di File e cartelle**) facendo clic sul nome del gruppo. Se viene selezionata un'attività, è possibile fare clic per annullare la selezione. È inoltre possibile utilizzare la casella di ricerca per visualizzare le attività che contengono la parola chiave digitata.
    
    ![Fare clic sul nome di gruppo di attività per selezionare tutte le attività](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)
  
- È necessario selezionare **Mostra i risultati per tutte le attività** nell'elenco **delle attività** da visualizzare gli eventi nel Registro di controllo di amministrazione di Exchange. Gli eventi dal Registro di controllo visualizzare un nome di cmdlet (ad esempio, **Set-Mailbox** ) nella colonna **attività** nei risultati. Per ulteriori informazioni, fare clic sulla scheda **attività Audited** in questo argomento e quindi fare clic su **attività di amministrazione di Exchange**.
    
    Analogamente, esistono alcune attività di controllo che non dispongono di un elemento corrispondente nell'elenco **delle attività** . Se si conosce il nome dell'operazione di queste attività, è possibile cercare tutte le attività, quindi digitare il nome dell'operazione della finestra per la colonna **attività** di filtrare i risultati. Vedere [passaggio 3: filtrare i risultati della ricerca](#step-3-filter-the-search-results) per ulteriori informazioni su filtrando i risultati. 
    
- Fare clic su **Cancella** per cancellare i criteri di ricerca corrente. L'intervallo di date restituisce il valore predefinito ultimi sette giorni. È inoltre possibile fare clic su **Cancella tutto per visualizzare i risultati per tutte le attività** per annullare tutte le attività selezionate. 
    
- Se vengono rilevati 5.000 risultati, è probabile che può assumere sono presenti più di 5.000 eventi che soddisfano i criteri di ricerca. È possibile filtrare i criteri di ricerca e rieseguire la ricerca per restituire un numero di risultati oppure è possibile esportare tutti i risultati di ricerca tramite la selezione di **esportare i risultati della** \> **scaricare tutti i risultati**.

  
### <a name="step-2-view-the-search-results"></a>Passaggio 2: Visualizzare i risultati della ricerca

I risultati di una ricerca dei registri di controllo vengono visualizzati **nell'area risultati della** pagina **ricerca dei registri di controllo** . Come affermato in precedenza vengono visualizzate al massimo 5.000 eventi (più recenti) incrementi di 150 eventi. Per visualizzare gli eventi più è possibile utilizzare la barra di scorrimento nel riquadro **dei risultati** oppure è possibile premere **MAIUSC + freccia giù** per visualizzare gli eventi successivamente 150. 
  
I risultati includono le seguenti informazioni relative a ogni evento restituito dalla ricerca.
  
- **Data:** Data e ora (in formato UTC) quando si è verificato l'evento. 
    
- **Indirizzo IP:** L'indirizzo IP del dispositivo utilizzato quando ha effettuato l'accesso all'attività. L'indirizzo IP viene visualizzato in formato di indirizzo di un indirizzo IPv4 o IPv6. 
    
- **Utente:** L'utente (o account di servizio) che ha eseguito l'azione che ha attivato l'evento. 
    
- **Attività:** Attività eseguite dall'utente. Questo valore corrisponde all'attività selezionata nell'elenco a discesa **delle attività** . Per un evento dal Registro di controllo di amministrazione di Exchange, il valore di questa colonna è un cmdlet di Exchange. 
    
- **Elemento:** Oggetto che è stato creato o modificato a causa di attività corrispondente. Ad esempio, il file che è stato visualizzato o modificato o l'account utente che è stato aggiornato. Non tutte le attività con un valore in questo articolo. 
    
- **Dettagli:** Ulteriori dettagli su un'attività. Non tutte le attività, saranno necessario un valore. 
    
> [!TIP]
> Fare clic su un'intestazione di colonna nell'area **dei risultati** per ordinare i risultati. È possibile ordinare i risultati dalla alla Z o viceversa a r. fare clic su intestazione **Data** per ordinare i risultati da meno recente su più recente o in ordine cronologico. 
  
#### <a name="view-the-details-for-a-specific-event"></a>Visualizzare i dettagli di un evento specifico

È possibile visualizzare ulteriori dettagli relativi a un evento facendo clic sul record dell'evento nell'elenco dei risultati della ricerca. Viene visualizzata una pagina di **informazioni** che contiene le proprietà dettagliate dal record di eventi. Le proprietà che vengono visualizzate dipendono dal servizio di Office 365 in cui si verifica l'evento. Per visualizzare i dettagli, fare clic su **ulteriori informazioni**. Per descrizioni, vedere [informazioni dettagliate sulla proprietà in Office 365 Registro di controllo](detailed-properties-in-the-office-365-audit-log.md).
  
![Fare clic su ulteriori informazioni per visualizzare le informazioni dettagliate sulla proprietà il record del registro eventi di controllo](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

  
### <a name="step-3-filter-the-search-results"></a>Passaggio 3: Filtrare i risultati della ricerca

Oltre a ordinare, è inoltre possibile filtrare i risultati di una ricerca dei registri di controllo. Si tratta di un'ottima funzionalità che consentono di filtrare rapidamente i risultati per un utente specifico o l'attività. È possibile creare una vasta ricerca e quindi rapidamente consente di filtrare i risultati per visualizzare gli eventi specifici. Quindi è possibile limitare i criteri di ricerca e ripetere la ricerca per restituire un insieme di dimensioni ridotte, più conciso dei risultati.
  
Per filtrare i risultati:
  
1. Eseguire una ricerca dei registri di controllo.
    
2. Quando vengono visualizzati i risultati, fare clic su **filtrare i risultati**.
    
    Le caselle parola chiave vengono visualizzate in ogni intestazione di colonna.
    
3. Fare clic su una delle caselle in un'intestazione di colonna e digitare una parola o frase, a seconda della colonna che si desidera filtrare in. I risultati verranno dinamicamente modificare nuovamente per visualizzare gli eventi che soddisfano il filtro.
    
    ![Digitare una parola nel filtro per visualizzare gli eventi che soddisfano il filtro](media/542dc323-a997-402c-934b-cc5e218e50bc.png)
  
4. Per cancellare un filtro, fare clic su **X** nella casella filtro oppure fare clic su **Nascondi filtro**.
    
> [!TIP]
> Per visualizzare gli eventi nel Registro di controllo di amministrazione di Exchange, digitare un **-** (tratto) nella casella filtro **attività** . Verranno visualizzati i nomi dei cmdlet, che vengono visualizzati nella colonna **attività** per gli eventi di amministrazione di Exchange. È quindi possibile ordinare i nomi in ordine alfabetico. 

### <a name="step-4-export-the-search-results-to-a-file"></a>Passaggio 4: Esportare i risultati della ricerca in un file

È possibile esportare i risultati di una ricerca dei registri di controllo in un file di virgole (CSV) nel computer locale. È possibile aprire il file di Microsoft Excel e utilizzare caratteristiche, ad esempio ricerca, ordinamento, filtro e la divisione di una singola colonna (che contiene le celle multivalore) in più colonne.
  
1. Eseguire una ricerca dei registri di controllo e quindi modificare i criteri di ricerca fino a ottenere i risultati desiderati.
    
2. Fare clic su **Esporta risultati** e selezionare una delle opzioni seguenti: 
    
  - **Salva i risultati caricati** Selezionare questa opzione per esportare solo le voci visualizzate **nell'area risultati** sul * * ricerca dei registri di controllo * * pagina. Il file CSV che può essere scaricato contiene le stesse colonne (e dati) visualizzato nella pagina (data, utente, attività, elemento e i dettagli). Una colonna aggiuntiva (denominata **ulteriori**) è incluso nel file CSV contenente informazioni dalla voce di registro di controllo. Dal momento che vengono esportati gli stessi risultati caricato (e visualizzabili) nella pagina **ricerca dei registri di controllo** vengono esportati fino a 5.000 voci. 
    
  - **Scarica tutti i risultati** Selezionare questa opzione per esportare tutte le voci dal Registro di controllo di Office 365 che soddisfano i criteri di ricerca. Per un elevato numero di risultati della ricerca, selezionare questa opzione per scaricare tutte le voci dal Registro di controllo oltre a 5.000 risultati che possono essere visualizzati nella pagina di **ricerca dei registri di controllo** . Questa opzione scaricherà i dati non elaborati dal Registro di controllo in un file CSV e contiene informazioni aggiuntive dalla voce del Registro di controllo in una colonna denominata **AuditData**. Può richiedere più tempo per scaricare il file se si sceglie questa opzione di esportazione in quanto il file può essere molto più grande di quella che può essere scaricato se si sceglie l'opzione altro.
    
    > [!IMPORTANT]
    > È possibile scaricare un massimo di 50.000 voci in un file CSV da una ricerca dei registri di controllo singolo. Se 50.000 voci vengono scaricate nel file CSV, è probabile che può assumere sono presenti più di 50.000 eventi che soddisfano i criteri di ricerca. Per esportare più di questo limite, provare a utilizzare un intervallo di date per ridurre il numero di voci del Registro di controllo. Potrebbe essere necessario eseguire più ricerche con dimensioni inferiori intervalli di date per esportare le voci più di 50.000. 
  
3. Dopo aver selezionato un'opzione di esportazione, verrà visualizzato un messaggio nella parte inferiore della finestra in cui viene chiesto di aprire il file CSV, salvarlo nella cartella download o salvarlo in una cartella specifica.

  
#### <a name="more-information-about-exporting-audit-log-search-results"></a>Ulteriori informazioni sull'esportazione risultati di ricerca di log di controllo

- L'opzione **Scarica tutti i risultati di** download per i dati non elaborati dal Registro di controllo di Office 365 in un file CSV. Questo file contiene nomi di colonna diversi (CreationDate, UserIds, operazione, AuditData) rispetto al file che può essere scaricato se si seleziona l'opzione **Salva i risultati caricati** . I valori nei due file CSV diversi per la stessa attività possono essere diversi. Ad esempio, l'attività nella colonna **azione** il file CSV di file e con un valore diverso rispetto alla versione "descrittivo" viene visualizzato nella colonna **attività** della pagina di **ricerca dei registri di controllo** . ad esempio, MailboxLogin e utente eseguito l'accesso alla cassetta postale.
    
- Se si scaricano tutti i risultati, il file CSV contiene una colonna denominata **AuditData**, che contiene informazioni aggiuntive su ogni evento. Come descritto in precedenza, questa colonna contiene una proprietà multivalore per diverse proprietà dal record del Registro di controllo. Ognuna delle coppie **: valore della proprietà** nella proprietà multivalore sono separati da una virgola. È possibile utilizzare la potenza di Query in Excel divisa questa colonna più colonne in modo che ogni proprietà è relativa colonna. Ciò consente di ordinare e filtrare su uno o più di queste proprietà. Per informazioni su come eseguire questa operazione, vedere la sezione "Dividere una colonna da delimitatore" in [una colonna di testo (Power Query) diviso](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662).
    
    Dopo la suddivisione della colonna **AuditData** non è possibile filtrare la colonna di **operazioni** per visualizzare le informazioni dettagliate sulla proprietà per un tipo specifico di attività. 
    
- Non esiste un limite di caratteri 3,060 per i dati che viene visualizzati nel campo **AuditData** per un record di controllo. Se viene superato il limite di caratteri 3,060, i dati in questo campo viene troncati. 
    
- Quando si scaricano tutti i risultati di una query di ricerca che contiene tutti gli eventi da diversi servizi di Office 365, la colonna **AuditData** nel file CSV contiene le proprietà diverse in base al quale è stata eseguita l'azione servizio nel. Ad esempio, le voci di registri di controllo di Exchange e Azure Active Directory includono una proprietà denominata **ResultStatus** che indica se l'azione ha avuto esito positivo o meno. Questa proprietà non è inclusa per gli eventi in SharePoint. Analogamente, gli eventi SharePoint presentano una proprietà che identifica il sito URL per file e cartelle attività correlate. Per ovviare a questo problema, è consigliabile utilizzare tipi differenti di ricerche per esportare i risultati per le attività da un singolo servizio. 
    
    Per una descrizione delle proprietà elencate nella colonna **AuditData** nel file CSV quando si scarica tutti i risultati e il servizio ogni si applica alla, vedere [informazioni dettagliate sulla proprietà in Office 365 Registro di controllo](detailed-properties-in-the-office-365-audit-log.md).

  
## <a name="audited-activities"></a>Attività controllata

Nelle tabelle di questa sezione vengono descritte le attività che vengono controllate in Office 365. È possibile eseguire la ricerca per eseguire l'accesso questi eventi cercando il controllo della sicurezza &amp; centro conformità. Fare clic sulla scheda **ricerca nel Registro di controllo** per istruzioni dettagliate. 
  
Queste tabelle gruppo attività correlate o le attività da un servizio specifico di Office 365. Le tabelle includono il nome descrittivo che viene visualizzato nell'elenco a discesa **delle attività** e il nome dell'operazione corrispondente visualizzata nelle informazioni dettagliate di un record di controllo e nel file CSV quando si esportano i risultati della ricerca. Per le descrizioni delle informazioni dettagliate, vedere [informazioni dettagliate sulla proprietà in Office 365 Registro di controllo](detailed-properties-in-the-office-365-audit-log.md).
  
Fare clic su uno dei collegamenti seguenti per accedere a una tabella specifica.
  
||||
|:-----|:-----|:-----|
|[Attività di file e pagina](#file-and-page-activities)<br/> |[Attività di cartella](#folder-activities)<br/> |[Attività di richiesta di condivisione e accesso](#sharing-and-access-request-activities)<br/> |
|[Attività di sincronizzazione](#synchronization-activities)<br/> |[Attività di amministrazione sito](#site-administration-activities)<br/> |[Attività delle cassette postali di Exchange](#exchange-mailbox-activities)<br/> |
|[Sway delle attività](#sway-activities) <br/> |[Attività di amministrazione dell'utente](#user-administration-activities) <br/> |[Attività di amministrazione di Azure Active Directory gruppo](#azure-ad-group-administration-activities) <br/> |
|[Attività di amministrazione di applicazione](#application-administration-activities) <br/> |[Attività di amministrazione ruoli](#role-administration-activities) <br/> |[Attività di amministrazione di directory](#directory-administration-activities) <br/> |
|[attività di eDiscovery](#ediscovery-activities) <br/> |[Attività di Power BI](#power-bi-activities) <br/> |[Attività Teams Microsoft](#microsoft-teams-activities) <br/> |
|[Attività di Yammer](#yammer-activities) <br/> |[Microsoft Stream](#microsoft-stream) <br/> |[Log di controllo di amministrazione di Exchange](#exchange-admin-audit-log) <br/> |
   
  
### <a name="file-and-page-activities"></a>Attività di file e pagina
  
Nella tabella seguente vengono descritte le attività di file e pagina in SharePoint Online e OneDrive for Business.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|File a cui si accede  <br/> |FileAccessed  <br/> |Account utente o il sistema accede a un file.  <br/> |
|(nessuno)  <br/> |FileAccessedExtended  <br/> |Questo è correlato a "accesso file" attività (FileAccessed). Quando la stessa persona continuamente accede a un file per un lungo periodo di tempo (fino a 3 ore), viene registrato un evento FileAccessedExtended. Lo scopo di registrazione di eventi FileAccessedExtended è per ridurre il numero di FileAccessed gli eventi registrati quando viene continuamente accede a un file. Ciò consente di ridurre il rumore di più record FileAccessed per le quali è essenzialmente la stessa attività dell'utente la possibilità di concentrarsi sull'evento FileAccessed iniziale (e più importante).  <br/> |
|Archiviare file  <br/> |FileCheckedIn  <br/> |Utente archivia in un documento estratto da una raccolta documenti.  <br/> |
|File estratto  <br/> |FileCheckedOut  <br/> |Utente consente di estrarre un documento memorizzato in una raccolta documenti. Gli utenti possono estrarre e apportare modifiche ai documenti condivisi con loro.  <br/> |
|File copiato  <br/> |FileCopied  <br/> |Utente copia un documento da un sito. Il file copiato può essere salvato in un'altra cartella nel sito.  <br/> |
|File eliminato  <br/> |FileDeleted  <br/> |Utente elimina un documento da un sito.  <br/> |
|File eliminato dal Cestino secondario  <br/> |FileDeletedFirstStageRecycleBin  <br/> |Utente elimina un file dal Cestino secondario di un sito.  <br/> |
|File eliminato dal Cestino secondario  <br/> |FileDeletedSecondStageRecycleBin  <br/> |Utente elimina un file dal Cestino secondario di un sito.  <br/> |
|Rilevato malware nel file.  <br/> |FileMalwareDetected  <br/> |Motore antivirus di SharePoint viene rilevato malware in un file.  <br/> |
|Estrazione del file annullato  <br/> |FileCheckOutDiscarded  <br/> |L'utente elimina (o annulla) un file estratto. Ciò significa che eventuali modifiche apportate al file al momento dell'estrazione vengono eliminate e non vengono salvate nella versione del documento nella raccolta documenti.  <br/> |
|File scaricato  <br/> |FileDownloaded  <br/> |Utente scarica un documento da un sito.  <br/> |
|File modificato  <br/> |FileModified  <br/> |Account utente o del sistema consente di modificare il contenuto o le proprietà di un documento memorizzato in un sito.  <br/> |
|(nessuno)  <br/> |FileModifiedExtended  <br/> |Questo è correlato a "file modificato" attività (FileModified). Quando la stessa persona modifica continuamente un file per un lungo periodo di tempo (fino a 3 ore), viene registrato un evento FileModifiedExtended. Lo scopo di registrazione di eventi FileModifiedExtended è per ridurre il numero di FileModified gli eventi registrati quando viene modificato continuamente in un file. Ciò consente di ridurre il rumore di più record FileModified per le quali è essenzialmente la stessa attività dell'utente la possibilità di concentrarsi sull'evento FileModified iniziale (e più importante).  <br/> |
|File spostato  <br/> |FileMoved  <br/> |Si sposta un documento dalla posizione corrente in un sito in un nuovo percorso.  <br/> |
|Riciclare tutte le versioni secondarie dei file  <br/> |FileVersionsAllMinorsRecycled  <br/> |Utente consente di eliminare tutte le versioni secondarie dalla cronologia versioni di un file. Le versioni eliminate vengono spostate Cestino del sito.  <br/> |
|Riciclare tutte le versioni dei file  <br/> |FileVersionsAllRecycled  <br/> |Utente consente di eliminare tutte le versioni dalla cronologia versioni di un file. Le versioni eliminate vengono spostate Cestino del sito.  <br/> |
|Riciclati versione del file  <br/> |FileVersionRecycled  <br/> |Utente elimina una versione dalla cronologia versioni di un file. La versione eliminata viene spostata al Cestino del sito.  <br/> |
|File rinominato  <br/> |FileRenamed  <br/> |Utente rinomina un documento in un sito.  <br/> |
|File ripristinato  <br/> |FileRestored  <br/> |Utente consente di ripristinare un documento dal Cestino secondario di un sito.  <br/> |
|File caricato  <br/> |FileUploaded  <br/> |Utente carica un documento in una cartella in un sito.  <br/> |
|Pagina visualizzata  <br/> |PageViewed  <br/> |Si visualizza una pagina in un sito. Ciò non include utilizzando un Web browser per visualizzare i file che si trovano in una raccolta documenti.  <br/> |
|(nessuno)  <br/> |PageViewedExtended  <br/> |Questo è correlato a "pagina visualizzabile" attività (PageViewed). Quando la stessa persona continuamente Visualizza una pagina web per un lungo periodo di tempo (fino a 3 ore), viene registrato un evento PageViewedExtended. Lo scopo di registrazione di eventi PageViewedExtended è per ridurre il numero di PageViewed gli eventi registrati per una pagina viene visualizzata continuamente. Ciò consente di ridurre il rumore di più record PageViewed per le quali è essenzialmente la stessa attività dell'utente la possibilità di concentrarsi sull'evento PageViewed iniziale (e più importante).  <br/> |
  
### <a name="folder-activities"></a>Attività di cartella
  
Nella tabella seguente vengono descritte le attività di cartelle in SharePoint Online e OneDrive for Business.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Cartella copiata  <br/> |FolderCopied  <br/> |Utente copia una cartella da un sito in un'altra posizione in SharePoint o OneDrive for Business.  <br/> |
|Cartella creata  <br/> |FolderCreated  <br/> |Utente consente di creare una cartella in un sito.  <br/> |
|Cartella eliminata  <br/> |FolderDeleted  <br/> |Utente elimina una cartella da un sito.  <br/> |
|Cartella eliminato dal Cestino secondario  <br/> |FolderDeletedFirstStageRecycleBin  <br/> |Utente elimina una cartella dal Cestino secondario in un sito.  <br/> |
|Cartella eliminato dal Cestino secondario  <br/> |FolderDeletedSecondStageRecycleBin  <br/> |Utente elimina una cartella dal Cestino secondario in un sito.  <br/> |
|Cartella modificata  <br/> |FolderModified  <br/> |Utente consente di modificare una cartella in un sito. Include i metadati di cartella, ad esempio modifica proprietà e i tag.  <br/> |
|Cartella spostata  <br/> |FolderMoved  <br/> |Si sposta una cartella in un'altra posizione in un sito.  <br/> |
|Cartella rinominata  <br/> |FolderRenamed  <br/> |Utente rinomina una cartella in un sito.  <br/> |
|Cartella ripristinato  <br/> |FolderRestored  <br/> |Utente consente di ripristinare una cartella eliminata dal Cestino secondario in un sito.  <br/> |
  
### <a name="sharing-and-access-request-activities"></a>Attività di richiesta di condivisione e accesso
  
Nella tabella seguente vengono descritte le attività di richiesta di condivisione e l'accesso utente in SharePoint Online e OneDrive for Business. Per gli eventi di condivisione, la colonna di **dettaglio** nella casella **risultati** identifica il nome dell'utente o gruppo che l'elemento è stato condiviso con e se tale utente o gruppo è un membro o guest nell'organizzazione. Per ulteriori informazioni, vedere [utilizzo di condivisione controllo nel Registro di controllo di Office 365](use-sharing-auditing.md).
  
> [!NOTE]
> Gli utenti possono essere *membri* o *guest* in base alla proprietà UserType dell'oggetto utente. Un membro è in genere un dipendente e guest viene in genere un collaboratore di fuori dell'organizzazione. Quando un utente accetta un invito alla condivisione e non è già parte della propria organizzazione, viene creato un account guest per tali nell'elenco dell'organizzazione. Dopo che l'utente guest dispone di un account nella directory, risorse possono essere condivisa direttamente con loro (senza dover utilizzare un invito). 
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Accettate richieste di accesso  <br/> |AccessRequestAccepted  <br/> |Una richiesta di accesso a un sito, cartelle o documenti è stata accettata e il richiedente utente è stato concesso l'accesso.  <br/> |
|Accettato l'invito alla condivisione  <br/> |SharingInvitationAccepted  <br/> |Utente (membro o guest) accettato un invito alla condivisione ed è stato concesso l'accesso a una risorsa. Questo evento sono incluse informazioni sull'utente invitato e l'indirizzo di posta elettronica utilizzato per accettare l'invito (che potrebbe essere diversi). Questa attività è spesso accompagnata da un secondo evento in cui viene descritto come l'utente è stato concesso l'accesso alla risorsa, ad esempio, aggiungere l'utente a un gruppo che dispone dell'accesso alla risorsa.  <br/> |
|Livello di autorizzazione sono stati aggiunti alla raccolta siti  <br/> |PermissionLevelAdded  <br/> |Un livello di autorizzazione è stato aggiunto a una raccolta siti.  <br/> |
|Aggiunto collegamento sicuro utente  <br/> |AddedToSecureLink  <br/> |Un utente è stato aggiunto all'elenco di entità che è possibile utilizzare questo collegamento condivisione protetto.  <br/> |
|Bloccare l'invito alla condivisione  <br/> |SharingInvitationBlocked  <br/> | Un invito alla condivisione inviato da un utente nell'organizzazione è bloccato a causa di un criterio di condivisione esterno consente o Nega condivisione esterna basati sul dominio dell'utente di destinazione. In questo caso, l'invito alla condivisione è stato bloccato perché:<br/>  Dominio dell'utente di destinazione non è incluso nell'elenco dei domini consentiti.  <br/>  Oppure  <br/>  Dominio dell'utente di destinazione è incluso nell'elenco dei domini bloccati.  <br/>  Per ulteriori informazioni per consentire o bloccare condivisione esterna basato su domini, vedere [domini con restrizioni di condivisione in SharePoint Online e OneDrive for Business](https://support.office.com/article/5d7589cd-0997-4a00-a2ba-2320ec49c4e9).  <br/> |
|Si è interrotta l'ereditarietà a livello di autorizzazione  <br/> |PermissionLevelsInheritanceBroken  <br/> |Un elemento è stato modificato in modo che non erediti più livelli di autorizzazione dall'elemento padre.  <br/> |
|Si è interrotta condivisione ereditarietà  <br/> |SharingInheritanceBroken  <br/> |Un elemento è stato modificato in modo da non ereditare le autorizzazioni di condivisione non è più dall'elemento padre.  <br/> |
|Creazione di un collegamento condivisibile società  <br/> |CompanyLinkCreated  <br/> |Creato un collegamento a livello aziendale per una risorsa dall'utente. collegamenti a livello aziendale consente solo dai membri all'interno dell'organizzazione. Non possono essere utilizzati da Guest.  <br/> |
|Creazione di richieste di accesso  <br/> |AccessRequestCreated  <br/> |Utente richiede l'accesso a un sito, cartelle o documenti che non dispone delle autorizzazioni per accedere.  <br/> |
|Creazione di un collegamento anonimo  <br/> |AnonymousLinkCreated  <br/> |Creato un collegamento anonimo a una risorsa dall'utente. Tutti gli utenti con questo collegamento può accedere alla risorsa senza dover eseguire l'autenticazione.  <br/> |
|Creato collegamento sicuro  <br/> |SecureLinkCreated  <br/> |A questo articolo è stato creato un collegamento sicuro condivisione.  <br/> |
|Creazione di invito alla condivisione  <br/> |SharingInvitationCreated  <br/> |Utente condiviso una risorsa in SharePoint Online o OneDrive for Business con un utente che non è presente nell'elenco dell'organizzazione.  <br/> |
|Collegamento sicuro eliminato  <br/> |SecureLinkDeleted  <br/> |È stato eliminato un collegamento sicuro condivisione.  <br/> |
|Richieste di accesso negato  <br/> |AccessRequestDenied  <br/> |È stata negata una richiesta di accesso a un sito, cartelle o documenti.  <br/> |
|Livello di autorizzazione di modifica nella raccolta siti  <br/> |PermissionLevelModified  <br/> |Un livello di autorizzazione è stato modificato in una raccolta siti.  <br/> |
|Rimuovere un collegamento condivisibile società  <br/> |CompanyLinkRemoved  <br/> |Rimuovere l'utente un collegamento a livello aziendale per una risorsa. Il collegamento non può più essere utilizzato per accedere alla risorsa.  <br/> |
|Rimuovere un collegamento anonimo  <br/> |AnonymousLinkRemoved  <br/> |Rimuovere l'utente un collegamento anonimo a una risorsa. Il collegamento non può più essere utilizzato per accedere alla risorsa.  <br/> |
|Rimozione di livello di autorizzazione dall'insieme di siti  <br/> |PermissionLevelRemoved  <br/> |Un livello di autorizzazione è stato rimosso da una raccolta siti.  <br/> |
|Ripristinare l'ereditarietà di condivisione  <br/> |SharingInheritanceReset  <br/> |È stata apportata una modifica in modo che un elemento eredita le autorizzazioni di condivisione dall'elemento padre.  <br/> |
|File condiviso, cartelle o del sito  <br/> |SharingSet  <br/> |Utente (membro o guest) condiviso un file, cartelle o del sito di SharePoint o OneDrive for Business con un utente nella directory dell'organizzazione. Il valore della colonna di **dettaglio** per questa attività identifica il nome dell'utente che è stato condiviso con la risorsa e se l'utente è membro o guest. Questa attività è spesso accompagnata da un secondo evento in cui viene descritto come l'utente è stato concesso l'accesso alla risorsa; ad esempio, aggiungere l'utente a un gruppo che dispone dell'accesso alla risorsa.<br/> |
|Richieste di accesso aggiornato  <br/> |AccessRequestUpdated  <br/> |Una richiesta di accesso a un elemento è stata aggiornata.  <br/> |
|Aggiornato un collegamento anonimo  <br/> |AnonymousLinkUpdated  <br/> |Utente aggiornato un collegamento anonimo a una risorsa. Il campo aggiornato è incluso nella proprietà EventData quando si esportano i risultati della ricerca.  <br/> |
|Invito alla condivisione aggiornato  <br/> |SharingInvitationUpdated  <br/> |È stato aggiornato un invito alla condivisione esterno.  <br/> |
|Utilizzare un collegamento anonimo  <br/> |AnonymousLinkUsed  <br/> |Un utente anonimo accedere a una risorsa tramite un collegamento anonimo. L'identità dell'utente potrebbe non escluderne noto, ma è possibile ottenere altri dettagli, ad esempio l'indirizzo IP dell'utente.  <br/> |
|La rimozione della condivisione file, cartelle o sito  <br/> |SharingRevoked  <br/> |Utente (membro o guest) la della condivisione file, cartelle o sito che deve essere stato condiviso in precedenza con un altro utente.  <br/> |
|Utilizzare un collegamento condivisibile società  <br/> |CompanyLinkUsed  <br/> |Utente accedere a una risorsa tramite un collegamento a livello aziendale.  <br/> |
|Utilizzare collegamento sicuro  <br/> |SecureLinkUsed  <br/> |Un utente utilizza un collegamento sicuro.  <br/> |
|Aggiunto collegamento sicuro utente  <br/> |AddedToSecureLink  <br/> |Un utente è stato aggiunto all'elenco di entità che è possibile utilizzare un collegamento sicuro condivisione.  <br/> |
|Utente rimosso dal collegamento sicuro  <br/> |RemovedFromSecureLink  <br/> |Un utente è stato rimosso dall'elenco di entità che è possibile utilizzare un collegamento sicuro condivisione.  <br/> |
|Ritiratesi invito alla condivisione  <br/> |SharingInvitationRevoked  <br/> |Utente ritiratesi un invito alla condivisione per una risorsa.  <br/> |
  
### <a name="synchronization-activities"></a>Attività di sincronizzazione
  
Nella tabella seguente sono elencate le attività di sincronizzazione dei file in SharePoint Online e OneDrive for Business.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Computer per sincronizzare i file è consentito  <br/> |ManagedSyncClientAllowed
  <br/> |Utente correttamente stabilisce una relazione di sincronizzazione a un sito. La relazione di sincronizzazione ha esito positivo perché nel computer dell'utente è membro di un dominio in cui è stato aggiunto all'elenco dei domini (denominati nell' *elenco destinatari attendibili* ) che possono accedere alle raccolte documenti all'interno dell'organizzazione.<br/> Per ulteriori informazioni su questa funzionalità, vedere [Use Windows PowerShell cmdlets per abilitare la sincronizzazione di OneDrive per i domini presenti nell'elenco destinatari attendibili](https://go.microsoft.com/fwlink/p/?LinkID=534609).  <br/> |
|Computer da sincronizzare i file bloccati  <br/> |UnmanagedSyncClientBlocked
  <br/> |Utente tenta di stabilire una relazione di sincronizzazione a un sito da un computer in cui non è un membro del dominio dell'organizzazione o è un membro di un dominio non è stato aggiunto all'elenco dei domini (viene chiamato il *elenco destinatari attendibili)* che possono accedere a documenti raccolte nell'organizzazione. La relazione di sincronizzazione non è consentita e nel computer dell'utente è bloccato dalla sincronizzazione in corso, download o caricamento dei file in una raccolta documenti.<br/> Per informazioni su questa funzionalità, vedere [Use Windows PowerShell cmdlets per abilitare la sincronizzazione di OneDrive per i domini presenti nell'elenco destinatari attendibili](https://go.microsoft.com/fwlink/p/?LinkID=534609).  <br/> |
|File scaricati in computer  <br/> |FileSyncDownloadedFull
  <br/> |Utente stabilisce una relazione di sincronizzazione e correttamente consente di scaricare i file per la prima volta al proprio computer da una raccolta documenti.  <br/> |
|File scaricato modifiche al computer  <br/> |FileSyncDownloadedPartial
  <br/> |Utente scarica correttamente le modifiche al file da una raccolta documenti. Questa attività indica che le modifiche apportate ai file nella raccolta documenti sono state scaricate in computer dell'utente. Solo le modifiche sono state scaricate dal momento che la raccolta documenti in precedenza è stata scaricata dall'utente (come indicato dall'attività **scaricati i file di computer** ).<br/> |
|File caricati in raccolta documenti  <br/> |FileSyncUploadedFull
  <br/> |Utente stabilisce una relazione di sincronizzazione e correttamente il caricamento di file per la prima volta dal proprio computer in una raccolta documenti.  <br/> |
|Modifiche ai file caricati in raccolta documenti  <br/> |FileSyncUploadedPartial
  <br/> |Utente carica correttamente le modifiche apportate ai file in una raccolta documenti. Questo evento indica che le modifiche apportate alla versione locale di un file da una raccolta documenti vengano caricate correttamente nella raccolta documenti. Solo le modifiche vengono scaricate in quanto tali file sono stati precedentemente caricati dall'utente (come indicato dal * * i file caricati in raccolta documenti * * attività).  <br/> |
  
### <a name="site-administration-activities"></a>Attività di amministrazione sito
  
Nella tabella seguente sono elencati gli eventi risultanti da attività di amministrazione di siti in SharePoint Online.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta di agenti utente di esenzione  <br/> |ExemptUserAgentSet
  <br/> |Un amministratore globale o SharePoint consente di aggiungere un agente utente all'elenco degli agenti utente di esenzione nell'interfaccia di amministrazione di SharePoint.  <br/> |
|Amministratori di raccolte siti sono stati aggiunti  <br/> |SiteCollectionAdminAdded
  <br/> |Amministratore della raccolta siti o proprietario consente di aggiungere una persona come amministratore della raccolta siti per un sito. Gli amministratori delle raccolte siti dispongono delle autorizzazioni controllo completo per la raccolta siti e tutti i siti secondari.  <br/> |
|Sono stati aggiunti utente o gruppo al gruppo di SharePoint  <br/> |AddedToGroup  <br/> |Utente aggiunto un membro o guest a un gruppo di SharePoint. Potrebbe essere sono stati un'azione intenzionale o il risultato di un'altra attività, ad esempio un evento di condivisione.  <br/> |
|Per creare gruppi di utenti è consentito  <br/> |AllowGroupCreationSet
  <br/> |Amministratore del sito o proprietario consente di aggiungere un livello di autorizzazione per un sito che consente di assegnata l'autorizzazione per creare un gruppo per il sito.  <br/> |
|Spostamento geo siti annullato  <br/> |SiteGeoMoveCancelled  <br/> |Un amministratore globale o SharePoint correttamente Annulla SharePoint o spostare OneDrive sito geo. La funzionalità Multi-Geo consente a un'organizzazione Office 365 estendersi su più Office 365 datacenter aree geografiche, ossia geos. Per ulteriori informazioni, vedere [Funzionalità Multi-Geo in OneDrive e SharePoint Online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).<br/> |
|Modifica un criterio di condivisione  <br/> |SharingPolicyChanged  <br/> |Un amministratore globale o SharePoint modificato SharePoint criterio di condivisione tramite il portale di amministrazione di Office 365, portale di amministrazione di SharePoint o SharePoint Online Management Shell. Verrà registrati eventuali modifiche alle impostazioni del criterio di condivisione nella propria organizzazione. I criteri che è stato modificato viene identificato nel campo **ModifiedProperties** nella proprietà dettagliato il record dell'evento.<br/> |
|Modifica il criterio di accesso di dispositivi  <br/> |DeviceAccessPolicyChanged  <br/> |Un amministratore globale o SharePoint modificato il criterio di dispositivi non gestita per l'organizzazione. Questo criterio controlla l'accesso a SharePoint, OneDrive e Office 365 dai dispositivi che non sono stati aggiunti nell'organizzazione. Si configurano questi criteri è necessario un mobilità aziendale + sottoscrizione di sicurezza. Per ulteriori informazioni, vedere [controllo dell'accesso dai dispositivi non gestiti](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622).<br/> |
|Modifica degli agenti utente di esenzione  <br/> |CustomizeExemptUsers
  <br/> |Un amministratore globale o SharePoint personalizzati l'elenco degli agenti utente di esenzione nell'interfaccia di amministrazione di SharePoint. È possibile specificare che gli agenti utente di esenzione di ricevere un'intera pagina web all'indice. Ciò significa che un agente utente è stato specificato come esenti rileva un modulo di InfoPath, verrà restituito il modulo come file XML, anziché un'intera pagina web. In questo modo più velocemente indicizzazione moduli di InfoPath.  <br/> |
|Modifica il criterio di accesso di rete  <br/> |NetworkAccessPolicyChanged  <br/> |Un amministratore globale o SharePoint modificato il criterio di accesso basato su percorso (denominato anche un limite di rete attendibile) nell'interfaccia di amministrazione di SharePoint o mediante l'utilizzo di PowerShell per SharePoint Online. Questo tipo di controlli dei criteri che possono accedere alle risorse di SharePoint e OneDrive nell'organizzazione basata su autorizzato intervalli di indirizzi IP specificato. Per ulteriori informazioni, vedere [controllo dell'accesso a SharePoint Online e OneDrive dati basati su percorso di rete](https://support.office.com/article/b5a5f1f1-1174-4c6b-91d0-9273a6b6971f).<br/> |
|Spostare geo sito completati  <br/> |SiteGeoMoveCompleted  <br/> |Uno spostamento geo siti che è stato pianificato da un amministratore globale dell'organizzazione è stato completato. La funzionalità Multi-Geo consente a un'organizzazione Office 365 estendersi su più Office 365 datacenter aree geografiche, ossia geos. Per ulteriori informazioni, vedere [Funzionalità Multi-Geo in OneDrive e SharePoint Online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).<br/> |
|Gruppo creato  <br/> |GroupAdded
  <br/> |Amministratore del sito o proprietario consente di creare un gruppo per un sito o consente di eseguire un'attività che i risultati in un gruppo da creare. Ad esempio, la prima volta che un utente crea un collegamento per condividere un file, sistema viene aggiunto un gruppo a OneDrive dell'utente per sito aziendale. Questo evento può essere anche un risultato di un utente che crea un collegamento a modificare le autorizzazioni a un file condiviso.  <br/> |
|Connessione creata inviato a  <br/> |SendToConnectionAdded
  <br/> |Un amministratore globale o SharePoint crea una nuova connessione di Invia a nella pagina Gestione record nell'interfaccia di amministrazione di SharePoint. Una connessione di invio per specifica le impostazioni per un archivio documenti o a un Centro record. Quando si crea una connessione invia a, Content Organizer possono presentare i documenti nella posizione specificata.  <br/> |
|Raccolta di siti creati  <br/> |SiteCollectionCreated
  <br/> |Un amministratore globale o SharePoint crea una nuova raccolta siti all'interno dell'organizzazione di SharePoint Online o un utente effettua il provisioning loro OneDrive per sito aziendale.  <br/> |
|Gruppo eliminato  <br/> |GroupRemoved
  <br/> |Utente elimina un gruppo da un sito.  <br/> |
|Connessione eliminata inviato a  <br/> |SendToConnectionRemoved
  <br/> |Un amministratore globale o SharePoint consente di eliminare una connessione invia a nella pagina Gestione record nell'interfaccia di amministrazione di SharePoint.  <br/> |
|Sito eliminato  <br/> |SiteDeleted  <br/> |Amministratore del sito consente di eliminare un sito.  <br/> |
|Attivata l'anteprima dei documenti  <br/> |PreviewModeEnabledSet
  <br/> |Amministratore del sito Attiva anteprima dei documenti per un sito.  <br/> |
|Abilitato legacy del flusso di lavoro  <br/> |LegacyWorkflowEnabledSet
  <br/> |L'amministratore o il proprietario del sito aggiunge il tipo di contenuto di attività di flusso di lavoro di SharePoint 2013 al sito. Gli amministratori globali possono inoltre abilitare i flussi di lavoro per l'intera organizzazione nell'interfaccia di amministrazione di SharePoint.  <br/> |
|Enabled Office su richiesta  <br/> |OfficeOnDemandSet
  <br/> |Amministratore del sito attiva Office su richiesta, che consente agli utenti di accedere alla versione più recente delle applicazioni desktop di Office. Office su richiesta è abilitata nell'interfaccia di amministrazione di SharePoint e richiede una sottoscrizione a Office 365 che include le applicazioni di Office installate, complete.  <br/> |
|Feed RSS abilitato  <br/> |NewsFeedEnabledSet
  <br/> |Amministratore del sito o proprietario attiva feed RSS per un sito. Gli amministratori globali è possono abilitare i feed RSS per l'intera organizzazione nell'interfaccia di amministrazione di SharePoint.  <br/> |
|Richieste di accesso modificata l'impostazione  <br/> |WebRequestAccessModified  <br/> |Le impostazioni di richieste di accesso sono state modificate in un sito.  <br/> |
|Modifica i membri possono Condividi impostazione  <br/> |WebMembersCanShareModified  <br/> |L'impostazione di **Membri possono condivisione** è stato modificato in un sito.  <br/> |
|Autorizzazioni sito modificato  <br/> |SitePermissionsModified
  <br/> |Amministratore del sito o proprietario (o account di sistema) viene modificato il livello di autorizzazione assegnati a un gruppo in un sito. Questa attività viene registrata anche se tutte le autorizzazioni vengono rimossi da un gruppo.<br/> > [!NOTE]> Questa operazione è diventato obsoleto in SharePoint Online. Per trovare gli eventi correlati, è possibile cercare altre attività relative alla autorizzazione come **amministratore della raccolta siti è stata aggiunta**, **sono stati aggiunti utente o gruppo al gruppo di SharePoint**, **consentito all'utente di creare gruppi**, **gruppo creato**e **Deleted gruppo di.**         |
|Rimuovere l'utente o gruppo dal gruppo di SharePoint  <br/> |RemovedFromGroup  <br/> |Utente rimosso un membro o guest da un gruppo di SharePoint. Potrebbe essere sono stati un'azione intenzionale o il risultato di un'altra attività, ad esempio un evento di annullamento della condivisione.  <br/> |
|Sito rinominato  <br/> |SiteRenamed
  <br/> |Amministratore del sito o proprietario Rinomina un sito  <br/> |
|Autorizzazioni di amministrazione sito richiesto  <br/> |SiteAdminChangeRequest
  <br/> |Richieste degli utenti da aggiungere come amministratore della raccolta siti per una raccolta siti. Gli amministratori delle raccolte siti dispongono delle autorizzazioni controllo completo per la raccolta siti e tutti i siti secondari.  <br/> |
|Spostare geo pianificato del sito  <br/> |SiteGeoMoveScheduled  <br/> |Un amministratore globale o SharePoint correttamente pianifica SharePoint o spostare OneDrive sito geo. La funzionalità Multi-Geo consente a un'organizzazione Office 365 estendersi su più Office 365 datacenter aree geografiche, ossia geos. Per ulteriori informazioni, vedere [Funzionalità Multi-Geo in OneDrive e SharePoint Online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).<br/> |
|Sito host set  <br/> |HostSiteSet
  <br/> |SharePoint o un amministratore globale modifica il sito designato per ospitare personali o OneDrive per i siti.  <br/> |
|Gruppo aggiornata  <br/> |GroupUpdated
  <br/> |Amministratore del sito o proprietario di modifica le impostazioni di un gruppo per un sito. Questo processo può includere la modifica del nome del gruppo, che può visualizzare o modificare l'appartenenza al gruppo e le modalità di gestione delle richieste di appartenenza.  <br/> |
  
### <a name="exchange-mailbox-activities"></a>Attività delle cassette postali di Exchange
  
Nella tabella seguente sono elencate le attività che possono essere registrate dalla cassetta postale di registrazione di controllo. Attività delle cassette postali eseguita dal proprietario della cassetta postale, un utente delegato o un amministratore vengono registrate. Per impostazione predefinita, il controllo delle cassette postali in Office 365 non è attivato. Controllo delle cassette postali registrazione deve essere attivata per ciascuna cassetta postale prima delle cassette postali attività vengono registrate. Per ulteriori informazioni, vedere [abilitare il controllo in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Sono state aggiunte delegare autorizzazioni di cassette postali  <br/> |Aggiungere-MailboxPermission  <br/> |Un amministratore assegnata l'autorizzazione di cassette postali FullAccess a un utente (noto come delegato) alla cassetta postale di un'altra persona. L'autorizzazione FullAccess consente al delegato di aprire la cassetta postale di altra persona, leggere e gestire il contenuto della cassetta postale.  <br/> |
|Messaggi copiati in un'altra cartella  <br/> |Copia  <br/> |Messaggio copiato in un'altra cartella.  <br/> |
|Elemento della cassetta postale creata  <br/> |Creazione  <br/> |Viene creato un elemento nella cartella Calendario, contatti, note o attività nella cassetta postale; ad esempio, viene creata una nuova convocazione riunione. Si noti che non è possibile controllare la creazione, inviare né ricevere un messaggio. Inoltre, non è controllata la creazione di una cartella delle cassette postali.  <br/> |
|Messaggi eliminati dalla cartella Posta eliminata  <br/> |SoftDelete  <br/> |Un messaggio è stato eliminato in modo permanente o eliminato dalla cartella Posta eliminata. Questi elementi vengono spostati nella cartella elementi ripristinabili. I messaggi vengono spostati nella cartella elementi ripristinabili anche quando l'utente viene selezionata e preme **MAIUSC + CANC**.<br/> |
|Spostare i messaggi in un'altra cartella  <br/> |Move  <br/> |Messaggio spostato in un'altra cartella.  <br/> |
|Spostare i messaggi nella cartella Posta eliminata  <br/> |MoveToDeletedItems  <br/> |Messaggio eliminato e spostato nella cartella Posta eliminata.  <br/> |
|Cartella modificata autorizzazione  <br/> |UpdateFolderPermissions  <br/> |È stata modificata un'autorizzazione di cartella. Controllare le autorizzazioni cartella quali utenti all'interno dell'organizzazione possono accedere cartelle delle cassette postali e i messaggi nella cartella.  <br/> |
|Messaggi eliminati dalla cassetta postale  <br/> |HardDelete  <br/> |Un messaggio è stato eliminato dalla cartella elementi ripristinabili (eliminata definitivamente dalla cassetta postale).  <br/> |
|Autorizzazioni delle cassette postali delegato rimosso  <br/> |Remove-MailboxPermission  <br/> |Un amministratore di rimossa l'autorizzazione FullAccess (che è stato assegnato a un delegato) dalla cassetta postale dell'utente. Dopo avere rimosso l'autorizzazione FullAccess, il delegato non può aprire la cassetta postale di altra persona o accedere a qualsiasi contenuto in essa contenuti.  <br/> |
|Utilizzo di autorizzazioni Invia come messaggio è stato inviato  <br/> |SendAs  <br/> |Messaggio inviato utilizzando l'autorizzazione SendAs. Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.  <br/> |
|Utilizzo di autorizzazioni Invia per conto di messaggio è stato inviato  <br/> |SendOnBehalf  <br/> |Messaggio inviato utilizzando l'autorizzazione SendOnBehalf. Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario la persona per conto della quale è stato inviato il messaggio e l’utente che ha effettivamente inviato il messaggio.  <br/> |
|Accesso delegato aggiornato alla cartella Calendario  <br/> |UpdateCalendarDelegation  <br/> |Una delega per il calendario è stata assegnata a una cassetta postale. Delega per il calendario permette di utilizzare un utente nelle stesse autorizzazioni dell'organizzazione per gestire il calendario del proprietario della cassetta postale.  <br/> |
|Messaggio aggiornato  <br/> |Aggiorna  <br/> |Modifiche apportate a un messaggio o alle relative proprietà.  <br/> |
|Effettuato l'accesso alla cassetta postale utente  <br/> |MailboxLogin  <br/> |Accesso effettuato dall'utente alla propria cassetta postale.  <br/> |
|(nessuno)  <br/> |UpdateInboxRules  <br/> |È stato aggiunta, rimossa o modifica una regola di posta in arrivo. Regole posta in arrivo vengono utilizzate per elaborare i messaggi di posta in arrivo dell'utente in base alle condizioni specificate ed eseguire azioni quando vengono soddisfatte le condizioni di una regola, ad esempio lo spostamento di un messaggio in una cartella specificata o eliminazione di un messaggio.<br/> Per restituire le voci per le attività di regola posta in arrivo, è necessario selezionare **Mostra i risultati per tutte le attività** nell'elenco **delle attività** . Utilizzare le caselle di intervallo di data e l'elenco di **utenti** per limitare i risultati di ricerca.<br/> |
  
### <a name="sway-activities"></a>Sway delle attività
  
Nella tabella seguente sono elencate attività degli utenti e amministratori nella oscillazione. Oscillazione è un'applicazione di Office 365 che consente agli utenti di raccogliere, in formato e condividere idee, brani e presentazioni di un'area di lavoro interattivo basate sul web. Per ulteriori informazioni, vedere [domande frequenti su oscillazione - della Guida di amministrazione](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075).
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Livello di condivisione oscillazione modificata  <br/> |SwayChangeShareLevel  <br/> |Utente modifica il livello di condivisione di un oscillazione. Questo evento acquisisce l'utente modifica dell'ambito di condivisione associato a un oscillazione; ad esempio, pubblica rispetto all'interno dell'organizzazione.  <br/> |
|Oscillazione creata  <br/> |SwayCreate  <br/> |Utente consente di creare un oscillazione.  <br/> |
|Oscillazione eliminati  <br/> |SwayDelete  <br/> |L'utente elimina un oscillazione.  <br/> |
|Disabilitata la duplicazione oscillazione  <br/> |SwayDisableDuplication  <br/> |Utente consente di disabilitare la duplicazione di un oscillazione.  <br/> |
|Oscillazione duplicato  <br/> |SwayDuplicate  <br/> |Utente Duplica un oscillazione.  <br/> |
|Oscillazione modificate  <br/> |SwayEdit  <br/> |Utente modifica un oscillazione.  <br/> |
|Duplicazione oscillazione abilitata  <br/> |EnableDuplication  <br/> |Consente la duplicazione di oscillazione; la possibilità per un utente consentire la duplicazione di un oscillazione è abilitata per impostazione predefinita.  <br/> |
|Condivisione oscillazione revocati  <br/> |SwayRevokeShare  <br/> |Utente interrompe la condivisione di un oscillazione da revocare l'accesso a esso. Revoca dell'accesso consente di modificare i collegamenti associati a un oscillazione.  <br/> |
|Oscillazione condivisa  <br/> |SwayShare  <br/> |Si intende condividere un oscillazione. Questo evento consente di acquisire l'azione dell'utente fare clic su una destinazione di condivisione specifico all'interno del menu di condivisione oscillazione. L'evento non indica se l'utente è stata completata l'operazione di condivisione.  <br/> |
|Disattivato condivisione esterna di oscillazione  <br/> |SwayExternalSharingOff  <br/> |Amministratore disabilita oscillazione condivisione esterna per l'intera organizzazione utilizzando l'interfaccia di amministrazione di Office 365.  <br/> |
|Condivisione esterna di oscillazione attivata  <br/> |SwayExternalSharingOn  <br/> |Amministratore Abilita oscillazione condivisione esterna per l'intera organizzazione utilizzando l'interfaccia di amministrazione di Office 365.  <br/> |
|Disattivato oscillazione servizio  <br/> |SwayServiceOff  <br/> |Amministratore disabilita oscillazione per l'intera organizzazione tramite l'interfaccia di amministrazione di Office 365.  <br/> |
|Attivata oscillazione servizio  <br/> |SwayServiceOn  <br/> |Amministratore consente oscillazione per l'intera organizzazione, utilizzando l'interfaccia di amministrazione di Office 365 (oscillazione service è attivata per impostazione predefinita).  <br/> |
|Oscillazione visualizzati  <br/> |SwayView  <br/> |Utente visualizza un'oscillazione.  <br/> |

  
### <a name="user-administration-activities"></a>Attività di amministrazione dell'utente
  
Nella tabella seguente sono elencate le attività di amministrazione utente che vengono registrate quando un amministratore aggiunge o modifica di un account utente utilizzando l'interfaccia di amministrazione di Office 365 o il portale di gestione di Azure.
  
|**Attività**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Utente aggiunto  <br/> |Aggiungi utente  <br/> |È stato creato un account utente di Office 365.  <br/> |
|Licenze utente modificato  <br/> |Licenze utente di modifica  <br/> |La licenza assegnata a un utente le novità. Per verificare le modifiche sono state le licenze, vedere l'attività **dell'utente è stato aggiornato** corrispondente.<br/> |
|Password utente modificato  <br/> |Cambia password utente  <br/> |Amministratore modifica la password per un utente la password.  <br/> |
|Utente eliminato  <br/> |Eliminare l'utente  <br/> |È stato eliminato un account utente di Office 365.  <br/> |
|Reimpostare la password utente  <br/> |Reimpostare la password utente  <br/> |Amministratore di reimpostare la password per un utente.  <br/> |
|Impostare proprietà che consente all'utente di cambiare la password  <br/> |Insieme force Cambia utente password  <br/> |Amministratore di impostarla la proprietà che impone all'utente di modificare la password al successivo accesso utente a Office 365.  <br/> |
|Impostare le proprietà di licenza  <br/> |Impostare le proprietà di licenza  <br/> |Amministratore consente di modificare le proprietà di una licenza assegnata a un utente.  <br/> |
|Utente aggiornata  <br/> |Utente di aggiornamento  <br/> |Amministratore modifica le proprietà di uno o più di un account utente. Per un elenco di proprietà dell'utente che possono essere aggiornate, vedere la sezione "Aggiornamento degli attributi utente" in [Eventi di Azure Active Directory di controllo Report](https://go.microsoft.com/fwlink/p/?LinkID=616549).<br/> |
  
### <a name="azure-ad-group-administration-activities"></a>Attività di amministrazione di Azure Active Directory gruppo
  
Nella tabella seguente sono elencate le attività di amministrazione di gruppo che vengono registrate quando un amministratore o un utente crea o modifica un gruppo di Office 365 o quando un amministratore crea un gruppo di sicurezza utilizzando l'interfaccia di amministrazione di Office 365 o il portale di gestione di Azure. Per ulteriori informazioni sui gruppi in Office 365, vedere [visualizzare, creare ed eliminare gruppi nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7).
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|È stato aggiunto gruppo  <br/> |Aggiungere un gruppo  <br/> |Creazione di un gruppo.  <br/> |
|Membro è stato aggiunto al gruppo  <br/> |Aggiungere membri al gruppo  <br/> |Un membro è stato aggiunto a un gruppo.  <br/> |
|Gruppo eliminato  <br/> |Elimina gruppo  <br/> |Eliminazione di un gruppo.  <br/> |
|Membri rimossi dal gruppo  <br/> |Rimuovere membri dal gruppo  <br/> |Un membro è stato rimosso da un gruppo.  <br/> |
|Gruppo aggiornata  <br/> |Gruppo di aggiornamento  <br/> |È stata modificata una proprietà di un gruppo.  <br/> |
   
### <a name="application-administration-activities"></a>Attività di amministrazione di applicazione
  
Nella tabella seguente sono elencate le attività di amministrazione dell'applicazione che vengono registrate quando un amministratore aggiunge o modifica di un'applicazione viene registrata in Azure Active Directory. Tutte le applicazioni che si basa su Azure Active Directory per l'autenticazione devono essere registrata nella directory.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Sono state aggiunte Delega voce  <br/> |Aggiungere la voce di delega  <br/> |Un'autorizzazione autenticazione è stata creata/concesso a un'applicazione in Azure Active Directory.  <br/> |
|Entità servizio sono stati aggiunti  <br/> |Aggiungere l'entità servizio  <br/> |Un'applicazione è stata registrata in Azure Active Directory. Un'applicazione è rappresentata da un SPN nella directory.  <br/> |
|Sono state aggiunte le credenziali per un'entità servizio  <br/> |Aggiungere credenziali dell'entità servizio  <br/> |Le credenziali sono state aggiunte a un servizio di entità di Azure Active Directory. Un principio servizio rappresenta un'applicazione nella directory.  <br/> |
|Voce rimossa la delega  <br/> |Rimozione della voce di delega  <br/> |Un'autorizzazione autenticazione è stato rimosso da un'applicazione di Azure Active Directory.  <br/> |
|Rimuovere un'entità servizio dalla directory  <br/> |Rimozione dell'entità servizio  <br/> |Un'applicazione è stato eliminato/non registrata da Azure Active Directory. Un'applicazione è rappresentata da un SPN nella directory.  <br/> |
|Credenziali rimosse da un servizio di entità  <br/> |Rimuovere le credenziali dell'entità servizio  <br/> |Le credenziali sono state rimosse da un servizio di entità di Azure Active Directory. Un principio servizio rappresenta un'applicazione nella directory.  <br/> |
|Voce del set di delega  <br/> |Voce del set di delega  <br/> |Un'autorizzazione autenticazione è stata aggiornata per un'applicazione in Azure Active Directory.  <br/> |

### <a name="role-administration-activities"></a>Attività di amministrazione ruoli
  
Nella tabella seguente sono elencate le attività di amministrazione ruoli Azure Active Directory che vengono registrate quando un amministratore di gestione ruoli di amministratore nell'interfaccia di amministrazione di Office 365 o nel portale di gestione di Azure.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiungere membri al ruolo  <br/> |Aggiungere membro del ruolo al ruolo  <br/> |Aggiungere un utente a un ruolo di amministratore in Office 365.  <br/> |
|Rimuovere un utente da un ruolo di directory  <br/> |Rimuovere membro del ruolo dal ruolo  <br/> |Rimuovere un utente a un ruolo di amministratore in Office 365.  <br/> |
|Impostare informazioni sui contatti della società  <br/> |Impostare informazioni sui contatti della società  <br/> |Aggiornare le preferenze dei contatti della società a livello dell'organizzazione Office 365. Sono inclusi gli indirizzi di posta elettronica per la posta elettronica relativi alla sottoscrizione inviati dall'Office 365, nonché le notifiche di documentazione tecniche sui servizi di Office 365.  <br/> |
   
### <a name="directory-administration-activities"></a>Attività di amministrazione di directory
  
Tabella seguente sono Azure Active directory e dominio relativi le attività che vengono registrate quando un amministratore di Gestione organizzazione Office 365 nell'interfaccia di amministrazione di Office 365 o nel portale di gestione di Azure.
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Dominio aggiunto alla società  <br/> |Aggiungere il dominio a società  <br/> |Aggiunta di un dominio all'organizzazione di Office 365.  <br/> |
|Aggiungere un partner alla directory  <br/> |Aggiungere società partner  <br/> |Aggiungere un partner (amministratore delegato) nell'organizzazione di Office 365.  <br/> |
|Dominio rimosso dalla società  <br/> |Rimuovere dominio dall'azienda  <br/> |Rimuovere un dominio dall'organizzazione Office 365.  <br/> |
|Rimuovere un partner dalla directory  <br/> |Rimuovere dalla società partner  <br/> |Rimuovere un partner (amministratore delegato) dall'organizzazione Office 365.  <br/> |
|Informazioni sull'impostazione di società  <br/> |Informazioni sull'impostazione di società  <br/> |Aggiornare le informazioni sulla società per l'organizzazione Office 365. Sono inclusi gli indirizzi di posta elettronica per la posta elettronica relativi alla sottoscrizione inviati dall'Office 365, nonché le notifiche di documentazione tecniche sui servizi di Office 365.  <br/> |
|Impostare l'autenticazione dominio  <br/> |Impostare l'autenticazione dominio  <br/> |Modificare l'impostazione di autenticazione di dominio per l'organizzazione Office 365.  <br/> |
|Aggiornare le impostazioni di federazione per un dominio  <br/> |Impostare le impostazioni di federazione nel dominio  <br/> |Modificare le impostazioni di federazione (condivisione esterna) per l'organizzazione Office 365.  <br/> |
|Set di criteri di password  <br/> |Set di criteri di password  <br/> |Modificare i vincoli di caratteri e la lunghezza per le password degli utenti nell'organizzazione Office 365.  <br/> |
|Attivato la sincronizzazione di Azure Active Directory  <br/> |Impostare un contrassegno DirSyncEnabled nella società  <br/> |Impostare la proprietà che può essere una directory di sincronizzazione di Azure Active Directory.  <br/> |
|Dominio aggiornato  <br/> |Dominio di aggiornamento  <br/> |Aggiornare le impostazioni di un dominio all'interno dell'organizzazione Office 365.  <br/> |
|Dominio verificato  <br/> |Verifica dominio  <br/> |Verificare che l'organizzazione è il proprietario di un dominio.  <br/> |
|Dominio verificato verificato posta elettronica  <br/> |Verificare la posta elettronica dominio verificato  <br/> |Verifica della posta elettronica utilizzato per verificare che l'organizzazione è il proprietario di un dominio.  <br/> |
   
### <a name="ediscovery-activities"></a>attività di eDiscovery
  
Ricerca e attività correlate ai eDiscovery che vengono eseguite in Office 365 protezione del contenuto &amp; centro conformità o eseguendo il corrispondente di Windows PowerShell cmdlet registrati nel Registro di controllo di Office 365. Sono incluse le attività seguenti:
  
- Creazione e gestione dei casi eDiscovery
    
- Creazione, avvio e modifica di ricerche di contenuto
    
- Esecuzione di azioni di ricerca del contenuto, ad esempio l'anteprima, esportazione e l'eliminazione di una ricerca
    
- Configurazione delle autorizzazioni di filtro per la ricerca del contenuto
    
- Gestire il ruolo di amministratore di eDiscovery
    
Per un elenco e una descrizione dettagliata delle attività di eDiscovery che vengono registrati, vedere la sezione [ricerca per le attività di eDiscovery in Office 365 Registro di controllo](search-for-ediscovery-activities-in-the-audit-log.md).
  
> [!NOTE]
> Necessario fino a 30 minuti per gli eventi risultanti dalle attività elencate sotto **le attività di eDiscovery** nell'elenco a discesa **delle attività** da visualizzare nei risultati della ricerca. Al contrario, viene 24 ore per gli eventi corrispondenti da eDiscovery cmdlet attività venga visualizzato nei risultati della ricerca. 
  
### <a name="power-bi-activities"></a>Attività di Power BI
  
Nella tabella seguente sono elencati utente e le attività di amministrazione in Power BI che vengono registrate nel Registro di controllo di Office 365.
  
 **Importante:** Registrazione di controllo per Power BI non è abilitata per impostazione predefinita. Per eseguire la ricerca per le attività di Power BI nel Registro di controllo di Office 365, è necessario attivare il controllo nel portale di amministrazione di Power BI. Per ulteriori informazioni, vedere [Controllo Power BI](https://docs.microsoft.com/power-bi/service-admin-auditing#enabling-auditing-functionality-in-the-power-bi-admin-portal).
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Sono stati aggiunti membri del gruppo Power BI  <br/> |AddGroupMembers  <br/> |Viene aggiunto un membro di un'area di lavoro di gruppo Power BI.  <br/> |
|Set di dati di Power BI analizzati  <br/> |AnalyzedByExternalApplication  <br/> |Un set di dati viene analizzata tramite un'applicazione esterna.  <br/> |
|Create dashboard Power BI  <br/> |CreateDashboard  <br/> |Viene creato un nuovo dashboard.  <br/> |
|Gruppo creato Power BI  <br/> |CreateGroup  <br/> |Viene creato un gruppo.  <br/> |
|Creazione dell'organizzazione pack contenuto Power BI  <br/> |CreateOrgApp  <br/> |Viene creato un pacchetto di contenuti dell'organizzazione.  <br/> |
|Dashboard di Power BI eliminati  <br/> |DeleteDashboard  <br/> |Viene eliminato un dashboard.  <br/> |
|Set di dati di Power BI eliminati  <br/> |DeleteDataset  <br/> |Viene eliminato un set di dati.  <br/> |
|Eliminati report Power BI  <br/> |DeleteReport  <br/> |Un report viene eliminato.  <br/> |
|Report Power BI scaricato  <br/> |DownloadReport  <br/> |Un utente scarica un report Power BI dal servizio al proprio computer.  <br/> |
|Modificato dashboard Power BI  <br/> |EditDashboard  <br/> |Ridenominazione di un dashboard.  <br/> |
|Esportato dati visual del report Power BI  <br/> |ExportReport  <br/> |Dati vengono esportati da una porzione di report.  <br/> |
|Dati esportati porzione di Power BI  <br/> |ExportTile  <br/> |Dati vengono esportati da una porzione di dashboard.  <br/> |
|Dashboard di Power BI stampate  <br/> |PrintDashboard  <br/> |Viene stampato un dashboard.  <br/> |
|Pagina del report Power BI stampata  <br/> |PrintReport  <br/> |Stampare un report.  <br/> |
|Pubblicato report Power BI web  <br/> |PublishToWebReport  <br/> |Un report viene pubblicato sul web.  <br/> |
|Dashboard di Power BI condivisa  <br/> |ShareDashboard  <br/> |Un dashboard è condivisa.  <br/> |
|Versione di valutazione di iniziata Power BI  <br/> |OptInForProTrial  <br/> |Un utente avvia una sottoscrizione di prova Power BI Pro.  <br/> |
|Impostazioni di Power BI dell'organizzazione aggiornato  <br/> |UpdatedAdminFeatureSwitch  <br/> |Un amministratore modifica un'impostazione dell'organizzazione nel portale di amministrazione di Power BI.  <br/> |
|Dashboard visualizzati Power BI  <br/> |ViewDashboard  <br/> |Viene visualizzato un dashboard.  <br/> |
|Visualizzati report Power BI  <br/> |Visualizza report  <br/> |Visualizzare un report.  <br/> |
  
### <a name="microsoft-teams-activities"></a>Attività Teams Microsoft
  
Nella tabella seguente sono elencati l'utente e Registro di controllo attività di amministrazione di Microsoft Teams che vengono registrati in Office 365. Microsoft Teams è un'area di lavoro allineato al centro di chat in Office 365. Combina un team conversazioni, riunioni, i file e le note in un'unica posizione. Per ulteriori informazioni e collegamenti ad argomenti della Guida, vedere:
  
- [Domande frequenti su Microsoft Teams - della Guida di amministrazione](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)
    
- [Guida di Microsoft Teams](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Robot sono stati aggiunti al team  <br/> |BotAddedToTeam  <br/> |Un utente aggiunge un robot a un team.  <br/> |
|Sono state aggiunte canale  <br/> |ChannelAdded  <br/> |Un utente aggiunge un canale a un team.  <br/> |
|Connettore è stato aggiunto  <br/> |ConnectorAdded  <br/> |Un utente aggiunge un connettore a un canale.  <br/> |
|Sono stati aggiunti i membri di team  <br/> |MemberAdded  <br/> |Il proprietario di un team consente di aggiungere membri a un team.  <br/> |
|Scheda aggiunta  <br/> |TabAdded  <br/> |Un utente aggiunge un oggetto tab a un canale.  <br/> |
|Modificare l'impostazione del canale  <br/> |ChannelSettingChanged  <br/> | L'operazione ChannelSettingChanged viene registrata quando vengono eseguite le attività seguenti da un membro del team. Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione che è stato modificato (illustrato nella parentesi riportata di seguito) nella colonna **elemento** nei risultati della ricerca di log di controllo.<br/> <br/>-Modifica il nome di un canale team ( **nome del canale**).  <br/>  <br/>-Consente di modificare la descrizione di un canale team ( **descrizione del canale**).  <br/> |
|Modifica impostazioni organizzazione  <br/> |TeamsTenantSettingChanged  <br/> | L'operazione TeamsTenantSettingChanged viene registrata quando vengono eseguite le attività seguenti da un amministratore globale utilizzando l'interfaccia di amministrazione di Office 365. Si noti che queste attività influiscono sulle impostazioni a livello di organizzazione Microsoft Teams. Per ulteriori informazioni, vedere [impostazioni di amministrazione per team di Microsoft](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2).<br/>  Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione che è stato modificato (illustrato nella parentesi riportata di seguito) nella colonna **elemento** nei risultati della ricerca di log di controllo.  <br/><br/>-Abilita o disabilita Teams Microsoft per l'organizzazione ( **Team Microsoft che**).  <br/><br/>-Abilita o disabilita l'interoperabilità tra Microsoft Teams e Skype for Business per l'organizzazione ( **Skype per l'interoperabilità Business**).<br/><br/>-Abilita o disabilita la visualizzazione organigramma nel client Microsoft Teams ( **visualizzazione grafico organizzazione**).  <br/><br/>-Attiva o disattiva la possibilità per i membri del team pianificare le riunioni private ( **la pianificazione delle riunioni Private**).  <br/><br/>-Attiva o disattiva la possibilità per i membri del team pianificare riunioni channel ( **canale la pianificazione delle riunioni**).  <br/><br/>-Abilita o disabilita chiamata video in team riunioni ( **Video per le riunioni Skype**).  <br/><br/>-Abilita o disabilita la condivisione in meetups Teams Microsoft per l'organizzazione ( **condivisione dello schermo per le riunioni Skype**) della schermata.  <br/><br/>-Attiva o disattiva la possibilità di aggiungere immagini animate (denominate Giphys) conversazioni team ( **immagini animato**).  <br/><br/>-Cambia il contenuto di valutazione di impostazione per l'organizzazione ( **classificazione del contenuto**). La classificazione del contenuto consente di limitare il tipo di immagine animata che può essere visualizzati nelle conversazioni.<br/><br/>-Attiva o disattiva la possibilità per i membri del team aggiungere immagini personalizzabili (denominate memes personalizzato) da Internet alle conversazioni del team ( **personalizzabile immagini da Internet**).  <br/><br/>-Attiva o disattiva la possibilità per i membri del team aggiungere immagini modificabile (denominate etichette) conversazioni team ( **modificabile immagini**).<br/><br/>-Attiva o disattiva la possibilità per i membri del team da utilizzare robot in chat Teams Microsoft e i canali ( **robot di livello di organizzazione**).<br/><br/>-Abilita robot specifico per Microsoft Teams; Ciò non include i Bot T, ovvero robot Guida team che è disponibile quando robot sono abilitate per l'organizzazione ( **robot singoli**).  <br/><br/>-Attiva o disattiva la possibilità per i membri del team aggiungere le estensioni o schede ( **estensioni o schede**).  <br/><br/>-Abilita o disabilita il caricamento sul lato del proprietario robot per Microsoft Teams ( **caricamento lato dei robot**).  <br/><br/>-Attiva o disattiva la possibilità per gli utenti di inviare messaggi di posta elettronica a un canale Microsoft Teams ( **posta elettronica canale**).  <br/> |
|Ruolo modificata dei membri di team  <br/> |MemberRoleChanged  <br/> |Il proprietario di un team viene modificato il ruolo di membri di un team. I valori seguenti indicano il tipo di ruolo assegnato all'utente.<br/><br/><br/> **1** - indica il ruolo di proprietario.<br/>**2** - indica il ruolo del membro. <br/>**3** - indica il ruolo Guest. <br/>La proprietà Members include anche il nome dell'organizzazione e indirizzo di posta elettronica del membro.  <br/> |
|Modifica impostazione di team  <br/> |TeamSettingChanged  <br/> | L'operazione TeamSettingChanged viene registrata quando vengono eseguite le attività seguenti per il proprietario di un team. Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione che è stato modificato (illustrato nella parentesi riportata di seguito) nella colonna **elemento** nei risultati della ricerca di log di controllo.<br/><br/>-Cambia il tipo di accesso per un team. I team possono essere impostato come privato o pubblico ( **tipo di accesso Team**). Quando un team è privato (impostazione predefinita), gli utenti possono accedere al team solo dall'invito. Quando un team è pubblico, è individuabile da tutti gli utenti.<br/><br/>-Consente di modificare la classificazione delle informazioni di un team ( **classificazione Team**).  <br/>  Ad esempio, i dati del team possono essere classificati come alto impatto aziendale, impatto aziendale medio o basso impatto aziendale.<br/><br/>-Modifica il nome di un team ( **Nome Team**).  <br/><br/>-Consente di modificare la descrizione del team ( **descrizione del Team**). <br/><br/>-Le modifiche apportate a una delle impostazioni del team. Il proprietario di un team può accedere a queste impostazioni in un client team facendo clic su un team, fare clic su **Gestisci team**e quindi facendo clic sulla scheda **Impostazioni** . Per queste attività, viene visualizzato il nome dell'impostazione che è stato modificato nella colonna **elemento** nei risultati della ricerca di log di controllo.<br/> |
|Creazione team  <br/> |TeamCreated  <br/> |Un utente crea un nuovo team.  <br/> |
|Canale eliminati  <br/> |ChannelDeleted  <br/> |Un utente elimina un canale da un team.  <br/> |
|Team eliminato  <br/> |TeamDeleted  <br/> |Il proprietario di un team elimina un team.  <br/> |
|Robot rimosso dal team  <br/> |BotRemovedFromTeam  <br/> |Un utente consente di rimuovere un robot di un team.  <br/> |
|Connettore rimosse  <br/> |ConnectorRemoved  <br/> |Un utente rimuove connettore da un canale.  <br/> |
|Membri rimossi dal team  <br/> |MemberRemoved  <br/> |Il proprietario di un team consente di rimuovere membri da un team.  <br/> |
|Scheda rimossa  <br/> |TabRemoved  <br/> |Un utente consente di rimuovere una scheda da un canale.  <br/> |
|Connettore aggiornato  <br/> |ConnectorUpdated  <br/> |Un utente di modifica un connettore in un canale.  <br/> |
|Aggiornamento della scheda  <br/> |TabUpdated  <br/> |Un utente di modifica una scheda in un canale.  <br/> |
|Utente effettuato l'accesso al team  <br/> |TeamsSessionStarted  <br/> |Un utente accede a un client di Microsoft Teams.  <br/> |

### <a name="yammer-activities"></a>Attività di Yammer
  
Nella tabella seguente sono elencati l'utente e Registro di controllo attività di amministrazione in Yammer che vengono registrate in Office 365. Per restituire Registro di controllo attività correlate ai Yammer da Office 365, è necessario selezionare **Mostra i risultati per tutte le attività** nell'elenco **delle attività** . Utilizzare le caselle di intervallo di data e l'elenco di **utenti** per limitare i risultati di ricerca. 
  
|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Criterio di conservazione dei dati modificati  <br/> |SoftDeleteSettingsUpdated  <br/> |Amministrazione verificato Aggiorna le impostazioni per il criterio di conservazione dei dati di rete per eliminare disco rigido o eliminare sfumati. Solo gli amministratori verificati possono eseguire l'operazione.  <br/> |
|Configurazione di rete modificate  <br/> |NetworkConfigurationUpdated  <br/> |Rete o amministrazione verificato Modifica configurazione di rete Yammer. Include l'impostazione dell'intervallo per l'esportazione dei dati e abilitazione della chat.  <br/> |
|Impostazioni del profilo di rete modificate  <br/> |ProcessProfileFields  <br/> |Rete o amministrazione verificato modifica le informazioni visualizzate degli utenti per la rete agli utenti di rete.  <br/> |
|Modifica la modalità a contenuti privata  <br/> |SupervisorAdminToggled  <br/> |Amministrazione verificato attiva o disattiva la *Modalità contenuti privati* . Questa modalità consente una visualizzazione amministrazione post nei gruppi privati e visualizzare messaggi privati tra i singoli utenti (o gruppi di utenti). Solo gli amministratori verificati solo è possono eseguire questa operazione.<br/> |
|Configurazione della sicurezza modificate  <br/> |NetworkSecurityConfigurationUpdated  <br/> |Amministrazione verificato Aggiorna configurazione protezione della rete Yammer. Sono incluse le restrizioni sugli indirizzi IP e impostazione di criteri di scadenza password. Solo gli amministratori verificati possono eseguire l'operazione.  <br/> |
|File creato  <br/> |FileCreated  <br/> |Utente carica un file.  <br/> |
|Gruppo creato  <br/> |GroupCreation  <br/> |Utente crea un nuovo gruppo.  <br/> |
|Gruppo eliminato  <br/> |GroupDeletion  <br/> |Viene eliminato un gruppo di Yammer.  <br/> |
|Messaggio eliminato  <br/> |MessageDeleted  <br/> |L'utente elimina un messaggio.  <br/> |
|File scaricato  <br/> |FileDownloaded  <br/> |Utente scarica un file.  <br/> |
|Dati esportati  <br/> |Esportazione dati  <br/> |Amministrazione verificato Esporta i dati di rete Yammer. Solo gli amministratori verificati possono eseguire l'operazione.  <br/> |
|File condiviso  <br/> |FileShared  <br/> |Utente condivide un file con un altro utente.  <br/> |
|Utente di rete in sospeso  <br/> |NetworkUserSuspended  <br/> |Rete o amministrazione verificato sospesa (disattiva) un utente da Yammer.  <br/> |
|Utenti sospesi  <br/> |UserSuspension  <br/> |Account utente è stato sospeso (disattivata).  <br/> |
|Descrizione del file aggiornato  <br/> |FileUpdateDescription  <br/> |L'utente modifica la descrizione di un file.  <br/> |
|Nome del file aggiornato  <br/> |FileUpdateName  <br/> |Utente modifica il nome di un file.  <br/> |
|File visualizzati  <br/> |FileVisited  <br/> |Utente apre un file.  <br/> |
   
### <a name="microsoft-stream"></a>Microsoft Stream
  
È possibile cercare il Registro di controllo per le attività di Microsoft Stream. Queste attività includono video attività eseguite dagli utenti, le attività del canale di gruppo e le attività di amministrazione, ad esempio gestione degli utenti, gestione delle impostazioni dell'organizzazione e l'esportazione di report. Per una descrizione di queste attività, vedere la sezione "Attività registrata nel Microsoft Stream" nei [Registri di controllo nel flusso Microsoft](https://docs.microsoft.com/stream/audit-logs).
  
### <a name="exchange-admin-audit-log"></a>Log di controllo di amministrazione di Exchange
  
Registrazione di controllo dell'amministratore di Exchange, che è abilitata per impostazione predefinita in Office 365, ovvero registra un evento nel Registro di controllo di Office 365 quando un amministratore (o un utente che dispone di autorizzazioni amministrative) apporta una modifica all'interno dell'organizzazione Exchange Online. Modifica apportata tramite l'interfaccia di amministrazione di Exchange oppure eseguire un cmdlet di Windows PowerShell viene registrata nel Registro di controllo di amministrazione di Exchange. Per ulteriori informazioni sull'amministrazione di Exchange la registrazione di controllo, vedere [registrazione di controllo dell'amministratore](https://go.microsoft.com/fwlink/p/?LinkID=619225).
  
Di seguito sono riportati alcuni suggerimenti per la ricerca per l'attività nel Registro di controllo di amministrazione di Exchange:
  
- Per restituire le voci dal Registro di controllo di amministrazione di Exchange, è necessario selezionare **Mostra i risultati per tutte le attività** nell'elenco **delle attività** . Utilizzare le caselle di intervallo di data e l'elenco di **utenti** per limitare i risultati di ricerca di cmdlet eseguiti da un amministratore di Exchange specifico all'interno di un intervallo di date specifiche. 
    
- Per visualizzare gli eventi nel Registro di controllo di amministrazione di Exchange, filtrare i risultati della ricerca e il tipo un **-** (tratto) nella casella filtro **attività** . Verranno visualizzati i nomi dei cmdlet, che vengono visualizzati nella colonna **attività** per gli eventi di amministrazione di Exchange. È quindi possibile ordinare i nomi in ordine alfabetico. 
    
    ![Digitare un trattino nella finestra di attività verranno filtrati gli eventi di amministrazione di Exchange](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)
  
- Per ottenere informazioni è stato eseguito il cmdlet, i parametri e i valori dei parametri utilizzati e gli oggetti sono stati interessati, è necessario esportare i risultati della ricerca e selezionare l'opzione **Scarica tutti i risultati** . 
    
- È inoltre possibile visualizzare gli eventi nel Registro di controllo di amministrazione di Exchange tramite l'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [visualizzare l'amministratore di registro di controllo](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx).
  