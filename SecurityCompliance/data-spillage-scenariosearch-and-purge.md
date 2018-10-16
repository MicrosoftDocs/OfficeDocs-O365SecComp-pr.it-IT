---
title: soluzione serie dati perdita scenario eDiscovery - ricerca ed eliminazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Utilizzare gli strumenti di eDiscovery e la ricerca di Office 365 per gestire e rispondere a un problema di perdita dati all'interno dell'organizzazione.
ms.openlocfilehash: d2c5a0a6efcc75a38df97c7c597503e5642f83eb
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575350"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>serie di soluzione di eDiscovery: scenario di perdita dei dati - ricerca ed eliminazione

 **What ' s perdita di dati e perché è importante?** Perdita di dati è rilascio di un documento riservato in un ambiente non attendibile. Quando viene rilevato un problema di perdita di dati, è importante valutare rapidamente le dimensioni e le posizioni della perdita, esaminare le attività dell'utente attorno ad esso e quindi eliminare definitivamente i dati espanso dal sistema. 
  
## <a name="data-spillage-scenario"></a>Scenario di perdita di dati

È possibile aprire un responsabile della sicurezza informazioni lead presso Contoso. L'utente viene informato di una situazione di perdita di dati in un dipendente condivisa involontariamente un documento altamente riservato con più persone tramite posta elettronica. Si desidera valutare rapidamente che ha ricevuto questo documento internamente ed esternamente. Una volta identificato, si desidera condividere le conclusioni maiuscole con altri ricercatori per esaminare e quindi rimuovere in modo permanente i dati da Office 365. Dopo aver completata le indagini, si desidera generare un report di prova di rimozione definitiva e altri dettagli maiuscole per qualsiasi riferimento futuro.
  
### <a name="scope-of-this-article"></a>Ambito di questo articolo

In questo documento viene fornito un elenco delle istruzioni su come rimuovere definitivamente un messaggio da Office 365 in modo che non è accessibile o ripristinabile. Per eliminare un messaggio e renderla recuperabili fino alla scadenza del periodo di mantenimento elementi eliminati, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione Office 365](search-for-and-delete-messages-in-your-organization.md).
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Flusso di lavoro per la gestione dei problemi di perdita di dati

Di seguito è una procedura per gestire un evento imprevisto perdita di dati:

![Passaggio 8 flusso di lavoro per la gestione dei problemi di perdita di dati](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[(Facoltativo) Passaggio 1: Gestire chi può accedere il caso e impostare i limiti di conformità](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Passaggio 2: Creare un caso eDiscovery](#step-2-create-an-ediscovery-case)<br/>
[Passaggio 3: Ricerca per i dati espanso](#step-3-search-for-the-spilled-data)<br/>
[Passaggio 4: Rivedere e convalidare le conclusioni maiuscole](#step-4-review-and-validate-case-findings)<br/>
[Passaggio 5: Utilizzare messaggi registro di traccia per verificare i dati come espanso deve essere stato condiviso](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Passaggio 6: Preparare le cassette postali](#step-6-prepare-the-mailboxes)<br/>
[Passaggio 7: Eliminare definitivamente i dati espanso](#step-7-permanently-delete-the-spilled-data)<br/>
[Passaggio 8: Verificare, fornire un modello di prova di eliminazione e di controllo](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Aspetti da conoscere prima di iniziare

- Quando una cassetta postale è in attesa, un messaggio eliminato rimane nella cartella elementi ripristinabili finché non scade il periodo di conservazione o Rilascia esenzione. [Passaggio 6](#step-6-prepare-the-mailboxes) descrive come rimuovere attesa dalle cassette postali. Prima di rimuovere la conservazione di controllo con la gestione dei record o reparti legali. L'organizzazione potrebbe disporre di un criterio che definisce se una cassetta postale in attesa o un problema di perdita dei dati ha la priorità. 
    
- Per controllare quali cassette postali degli utenti si una perdita dei dati consente di cercare e gestione di utenti che possono accedere il caso, è possibile impostare i limiti di conformità e creare un gruppo di ruolo personalizzato, descritto nel [passaggio 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). A tale scopo, è necessario essere membri del gruppo di ruoli Gestione organizzazione o essere assegnato il ruolo di gestione ruoli. Se si o in amministratore nella propria organizzazione ha già set dei limiti di conformità, è possibile ignorare il passaggio 1.
    
- Per creare un caso, è necessario essere membri del gruppo di ruoli gestione eDiscovery o essere un membro del gruppo di ruoli personalizzato che ha assegnato il ruolo di gestione dei casi. Se non si è un membro, chiedere all'amministratore di Office 365 per [aggiungere l'utente al gruppo di ruoli di gestione di eDiscovery](assign-ediscovery-permissions.md).
    
- Per eliminare i dati che si estende nella propria organizzazione, è necessario utilizzare il comando [DeleteContent Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps) in Exchange Online PowerShell. Inoltre, per utilizzare il parametro *DeleteContent* , è inoltre necessario essere membri del gruppo di ruoli in Exchange Online che è assegnato il ruolo cassette postali importazione/esportazione. Vedere la sezione "Aggiungere un ruolo a un gruppo di ruoli" in [gruppi di ruoli di gestione](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx).
    
- Per cercare le attività di Office 365 audit log eDiscovery nel passaggio 8, il controllo deve essere attivato per la propria organizzazione. È possibile cercare le attività che sono state eseguite negli ultimi 90 giorni. Per ulteriori informazioni su come abilitare e utilizzare il controllo, vedere la sezione [controllo del processo di analisi di perdita dei dati](#auditing-the-data-spillage-investigation-process) nel passaggio 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>(Facoltativo) Passaggio 1: Gestire chi può accedere il caso e impostare i limiti di conformità

A seconda l'esercitazione dell'organizzazione, è necessario controllare quali utenti può accedere il caso di eDiscovery consente di analizzare un evento imprevisto perdita di dati e impostare i limiti di conformità. Il modo più semplice per eseguire questa operazione è aggiungere ricercatori come membri di un gruppo di ruolo esistente nel centro conformità protezione di Office 365 e quindi aggiungere il gruppo di ruoli come membro del caso di eDiscovery. Per informazioni su come aggiungere membri a un caso eDiscovery e i gruppi di ruoli incorporati eDiscovery, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
  
È inoltre possibile creare un nuovo gruppo di ruolo che risulti allineato con le esigenze dell'organizzazione. È possibile ad esempio, un gruppo di ricercatori perdita di dati nell'organizzazione di accedere e collaborare su tutti i casi di perdita di dati. Tale operazione può essere la creazione di un gruppo di ruoli "Si perdita di dati", assegnazione dei ruoli appropriati (esportazione, decrittografia RMS, revisione, Preview, ricerca di conformità e Case gestione), aggiungendo i ricercatori perdita di dati per il gruppo di ruoli e aggiungendo quindi il gruppo di ruoli come membro del caso di eDiscovery perdita di dati. Per informazioni dettagliate su come eseguire questa operazione, vedere [impostare i limiti di conformità per ricerche eDiscovery in Office 365](set-up-compliance-boundaries.md) . 
  
## <a name="step-2-create-an-ediscovery-case"></a>Passaggio 2: Creare un caso eDiscovery

Un caso eDiscovery consente di gestire l'analisi di perdita di dati in modo efficace. È possibile aggiungere membri al gruppo di ruoli creato nel passaggio 1, aggiungere il gruppo di ruoli come membro di nuovo un caso eDiscovery, eseguire ricerche iterative per trovare i dati espanso, esportare un report per condividere, tenere traccia dello stato del caso e quindi fare riferimento ai dettagli della c base se necessario. È consigliabile definire una convenzione di denominazione per i casi di eDiscovery utilizzati per interventi di perdita di dati e vengono fornite le informazioni presenti può maiuscole nome e una descrizione che consentono di individuare e consultare in futuro, se necessario.
  
Per creare un nuovo caso, è possibile utilizzare eDiscovery in sicurezza &amp; centro conformità. Vedere "Creare un nuovo caso" in [casi di eDiscovery nel centro conformità protezione di Office 365](ediscovery-cases.md#step-2-create-a-new-case).
  
## <a name="step-3-search-for-the-spilled-data"></a>Passaggio 3: Ricerca per i dati espanso

Dopo aver creato un caso e gestito l'accesso, è possibile utilizzare nel caso in cui per cercare in modo iterativo per individuare i dati espanso e identificare le cassette postali che contengono dati espanso. Utilizzare la stessa query di ricerca utilizzato per individuare i messaggi di posta elettronica per eliminare i messaggi stessi nel [passaggio 7](#step-7-permanently-delete-the-spilled-data).
  
Per creare un contenuto ricerche associate a un caso di eDiscovery, vedere "Creare ed eseguire che una ricerca del contenuto associato a un caso" in [casi di eDiscovery nel centro conformità protezione di Office 365](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case).
  
 **Importante:** Le parole chiave utilizzati nella query di ricerca possono contenere i dati effettivi espanso che si sta cercando. Ad esempio, se la ricerca di documenti che contengono un numero di previdenza sociale e si utilizza it come parola chiave di ricerca, è necessario eliminare la query in un secondo momento per evitare ulteriori perdita. Vedere [eliminazione di query di ricerca](#deleting-the-search-query) nel passaggio 8. 
  
## <a name="step-4-review-and-validate-case-findings"></a>Passaggio 4: Rivedere e convalidare le conclusioni maiuscole

Dopo aver creato una ricerca di contenuto, è necessario esaminare e verificare che la ricerca dei risultati e verificare che sono costituiti esclusivamente i messaggi di posta elettronica che devono essere eliminati. In una ricerca di contenuto, è possibile visualizzare un'anteprima un campione di 1.000 messaggi di posta elettronica senza esportare i risultati della ricerca per evitare ulteriori perdita di dati. Per ulteriori informazioni sulle limitazioni di anteprima in [limiti per la ricerca del contenuto in Office 365 Security &amp; centro conformità](limits-for-content-search.md).
  
Se si dispone di più di 1.000 cassette postali o più di 100 messaggi di posta elettronica per cassetta postale per la revisione, è possibile suddividere gli iniziale della ricerca in più ricerche tramite parole chiave aggiuntive o condizioni, ad esempio l'intervallo di date o mittente/destinatario ed esaminare i risultati di ricerca ogni singolarmente. Assicurarsi di prendere nota verso il basso tutte le query di ricerca da utilizzare quando si eliminano i messaggi nel [passaggio 7](#step-7-permanently-delete-the-spilled-data).

Se un depositaria o l'utente finale viene assegnata una licenza Office 36 E5, è possibile esaminare contemporaneamente utilizzando Office 365 avanzate eDiscovery fino a 10.000 risultati di ricerca. Se sono presenti più di 10.000 messaggi di posta elettronica per la revisione, è possibile suddividere le query di ricerca dall'intervallo di date ed esaminare ogni risultato singolarmente dalla data di ordinamento dei risultati di ricerca di. In eDiscovery avanzate, è possibile contrassegnare i risultati della ricerca mediante la caratteristica **come etichetta** nel riquadro di anteprima e filtra il risultato della ricerca per il tag che riattiva. Ciò è utile quando si collabora con un revisore secondario. Utilizzando gli strumenti aggiuntivi analitica di eDiscovery avanzate, ad esempio riconoscimento ottico dei caratteri, threading posta elettronica e la scrittura di codice predittiva, è possibile rapidamente elaborare e controllare migliaia di messaggi e tag per un ulteriore esame. Vedere [rapidità di configurazione per Office 365 avanzate eDiscovery](quick-setup-for-advanced-ediscovery.md).

Dopo aver individuato un messaggio di posta elettronica contenente i dati espanso, controllare i destinatari del messaggio per determinare se è stato condiviso esternamente. Per ulteriore analisi un messaggio, è possibile raccogliere le informazioni sul mittente e l'intervallo di date in modo che è possibile utilizzare i registri di traccia dei messaggi, descritto nel [passaggio 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).

Dopo la verifica i risultati della ricerca, è possibile condividere le proprie scoperte con altri utenti per un esame secondario. Persone assegnate al caso nel passaggio 1 consente di esaminare il contenuto sociale in eDiscovery ed eDiscovery avanzate e approvare le conclusioni maiuscole. È inoltre possibile generare un report senza esportare il contenuto effettivo. È inoltre possibile utilizzare questo rapporto stesso come un modello di prova di eliminazione, descritto nel [passaggio 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).
  
 **Per generare un report di statistico:**
  
1. Fare clic sulla ricerca che si desidera generare un rapporto per passare alla pagina di **ricerca** in caso di eDiscovery. 
    
2. Nella pagina tendina fare clic su **più > Esporta report**.
 
      Verrà visualizzata la pagina di report di esportazione.

    ![Selezionare la ricerca e quindi fare clic su altro > Esporta il report nella pagina comparsa](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Selezionare **tutti gli elementi, comprese quelle che hanno il formato non riconosciuto, vengono crittografati o non indicizzati per altri motivi** e quindi fare clic su **Genera rapporto**.

4. Nel caso di eDiscovery, fare clic su **Esporta** per visualizzare l'elenco di processi di esportazione. Potrebbe essere necessario fare clic su **Aggiorna** per aggiornare l'elenco per visualizzare il processo di esportazione che appena creata.

5. Fare clic sul processo di esportazione e quindi fare clic su **Scarica** report nella pagina del riquadro a comparsa.
 
    ![Nella pagina esportazione fare clic su Esporta e quindi fare clic su "Scarica report"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

**Esportare Summary** report contiene il numero di posizioni sono state riscontrate le dimensioni dei risultati della ricerca e i risultati. È possibile utilizzare questo da confrontare con il report generato dopo l'eliminazione e fornire come un modello di prova di eliminazione. Report dei **risultati** contiene un riepilogo dei risultati della ricerca, tra cui subject, mittente, destinatari, se il messaggio di posta elettronica è stato letto, date e dimensioni di ogni messaggio dettagliato. Se uno qualsiasi dei dettagli in questo report contiene dati effettivi espanso, è necessario eliminare definitivamente il file Results.csv durante l'analisi viene completata.

Per ulteriori informazioni sull'esportazione di report, vedere [esportazione di un report di ricerca del contenuto](export-a-content-search-report.md).
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Passaggio 5: Utilizzare messaggi registro di traccia per verificare i dati come espanso deve essere stato condiviso

Per ulteriori informazioni su se è stato condiviso posta elettronica con i dati espanso, è possibile richiedere facoltativamente i registri di traccia dei messaggi con le informazioni sul mittente e le informazioni sull'intervallo di date che raccolte nel passaggio 4. Si noti che il periodo di conservazione per la traccia dei messaggi è 30 giorni di dati in tempo reale e 90 giorni per i dati cronologici.
  
È possibile utilizzare traccia dei messaggi nel centro conformità protezione o utilizzare i cmdlet corrispondenti in Exchange Online PowerShell. È importante tenere presente che traccia dei messaggi non offra ogni garanzia circa la completezza dei dati restituiti. Per ulteriori informazioni sull'utilizzo di traccia dei messaggi, vedere: 
  
- [Messaggi di traccia in Office 365 Security &amp; centro conformità](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [Nuova traccia dei messaggi di protezione di Office 365 &amp; centro conformità](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>Passaggio 6: Preparare le cassette postali

Dopo la revisione e verificare che i risultati della ricerca contiene solo i messaggi che devono essere eliminati, è necessario raccogliere un elenco di indirizzi di posta elettronica delle cassette postali interessati da utilizzare nel passaggio 7 quando si esegue il comando **DeleteContent Search-Mailbox** . Inoltre è necessario preparare le cassette postali prima che è possibile eliminare definitivamente i messaggi di posta elettronica in base al fatto ripristino di singoli elementi è abilitato per le cassette postali che contengono dati espanso o se si verifica una delle cassette postali in attesa.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Ottenere un elenco di indirizzi di cassette postali con dati espanso

Esistono due modi per la raccolta di un elenco di indirizzi di posta elettronica di cassette postali con dati espanso.

**Opzione 1: Ottenere un elenco di indirizzi di cassette postali con dati espanso**

1. Aprire il caso di eDiscovery, passare alla pagina di **ricerca** e selezionare la ricerca di contenuto appropriata. 
    
2. Nella pagina tendina fare clic su **Visualizza risultati**.
    
3. Nell'elenco a discesa **singoli risultati** , fare clic su **informazioni statistiche sulla ricerca**.
    
4. Nell'elenco a discesa **tipo** , fare clic su **percorsi principali**.
    
    ![Ottenere un elenco delle cassette postali che contengono i risultati di ricerca nella pagina percorsi principali statistiche ricerca](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Viene visualizzato un elenco delle cassette postali che contengono i risultati della ricerca. Inoltre viene visualizzato il numero di elementi in ciascuna cassetta postale che corrispondono alla query di ricerca.
    
5. Copiare le informazioni nell'elenco e salvarlo in un file o fare clic su **Download** per scaricare le informazioni in un file CSV. 
    
**Opzione 2: Ottenere le posizioni delle cassette postali dal rapporto esportazione**

Aprire il report di riepilogo di esportazione che è stato scaricato nel [passaggio 4](#step-4-review-and-validate-case-findings). Nella prima colonna nel rapporto, l'indirizzo di posta elettronica di ciascuna cassetta postale è elencato in **percorsi**.
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Preparare le cassette postali in modo che è possibile eliminare i dati espanso

Se il ripristino di singoli elementi è attivato o una cassetta postale viene messa in attesa, un messaggio (eliminato) in modo permanente eliminato verrà mantenuto nella cartella elementi recuperabili. Pertanto prima che è possibile eliminare dati espanso, è necessario controllare le configurazioni delle cassette postali esistenti e disabilitare il ripristino di singoli elementi e rimozione di attesa o criteri di conservazione di Office 365. Tenere presente che è possibile preparare una cassetta postale per volta e quindi eseguire il comando stesso diverse cassette postali o creare uno script di PowerShell per preparare più cassette postali contemporaneamente.

- Vedere "passaggio 1: raccolta delle informazioni sulla cassetta postale" in [Elimina elementi nella cartella delle cassette postali basate su cloud in attesa agli elementi ripristinabili](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) per istruzioni su come verificare se è attivato il ripristino di singoli elementi o se la cassetta postale viene messa in attesa o viene assegnato a un criterio di conservazione. 
    
- Vedere "passaggio 2: preparare la cassetta postale" in [Elimina elementi nella cartella delle cassette postali basate su cloud in attesa agli elementi ripristinabili](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) per ulteriori informazioni sulla disattivazione del ripristino di singoli elementi. 
    
- Vedere "passaggio 3: rimuovere tutte le esenzioni dalla cassetta postale" in [Elimina elementi nella cartella delle cassette postali basate su cloud in attesa agli elementi ripristinabili](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) per istruzioni su come rimuovere un criterio di conservazione o conservazione da una cassetta postale. 

- Vedere "passaggio 4: rimuovere il ritardo attesa dalla cassetta postale" in [Elimina elementi nella cartella delle cassette postali basate su cloud in attesa agli elementi ripristinabili](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) per istruzioni sulla rimozione dell'esenzione ritardo che viene inserito nella cassetta postale dopo la rimozione di qualsiasi tipo di attesa.
    
 **Importante:** Verificare con la gestione dei record o reparti legali prima di rimuovere un criterio di conservazione o conservazione. L'organizzazione può disporre di un criterio che definisce se una cassetta postale in attesa o un problema di perdita dei dati ha la priorità. 
  
Assicurarsi di ripristinare la cassetta postale alle configurazioni precedenti dopo aver verificato che i dati espanso sono stati eliminati in modo permanente. Visualizzare i dettagli nel [passaggio 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Passaggio 7: Eliminare definitivamente i dati espanso

Utilizza i percorsi delle cassette postali che raccolti e preparato nel passaggio 6 e la query di ricerca è stata creata e affinamento nel passaggio 3 per individuare i messaggi di posta elettronica che contengono dati espanso, è possibile ora eliminare definitivamente i dati espanso. Come indicato in precedenza, è necessario essere assegnato il ruolo cassette postali importazione ed esportazione di Exchange Online per eliminare i messaggi utilizzando la procedura seguente.
  
1. [Connettersi a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
2. Eseguire il comando riportato di seguito:
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. Eseguire di nuovo il comando precedente per ogni cassetta postale che contiene i dati espanso, sostituendo il valore per il parametro Identity. Per esempio:

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
Come descritto in precedenza, è possibile creare uno [script di powershell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) ed eseguirlo su un elenco delle cassette postali in modo che lo script consente di eliminare i dati espanso in ciascuna cassetta postale.
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Passaggio 8: Verificare, fornire un modello di prova di eliminazione e di controllo

Il passaggio finale del flusso di lavoro per la gestione di un evento imprevisto perdita di dati consiste nel verificare che i dati espanso è stata rimossa definitivamente dalla cassetta postale a caso eDiscovery quindi eseguire nuovamente la stessa query di ricerca che è stata utilizzata per non eliminare tali dati per verificare che nessuna contabilità clienti risultati e restituite. Dopo avere verificato che i dati espanso sono stata rimossa definitivamente, è possibile esportare un report e includere (e il rapporto originale) come un modello di prova di eliminazione. È possibile [chiudere il caso](ediscovery-cases.md#optional-step-9-close-a-case), che consentono di aprire nuovamente se riferimento a esso in futuro. Inoltre, è inoltre possibile ripristinare le cassette postali allo stato precedente, eliminare la query di ricerca consente di trovare i dati espanso e cercare controllo dei record di attività relative alla gestione dell'evento imprevisto perdita di dati. 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Il ripristino delle cassette postali allo stato precedente

Se si modifica qualsiasi configurazione delle cassette postali nel passaggio 6 per preparare le cassette postali prima dell'eliminazione di dati espanso, è necessario riportarli allo stato precedente. Vedere "passaggio 6: ripristinare la cassetta postale allo stato precedente" in [Elimina elementi nella cartella delle cassette postali basate su cloud in attesa agli elementi ripristinabili](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state).
  
### <a name="deleting-the-search-query"></a>Eliminazione di query di ricerca

Se le parole chiave nella query di ricerca creato e utilizzato nel passaggio 3 contiene alcuni o tutti i dati effettivi espanso, è necessario eliminare la query di ricerca per evitare ulteriori perdita di dati.
  
1. In sicurezza & centro conformità, aprire il caso di eDiscovery, passare alla pagina di **ricerca** e selezionare la ricerca di contenuto appropriata.
    
2. Nella pagina tendina fare clic su **Elimina**.

    ![Selezionare la ricerca e quindi fare clic su Elimina nella pagina comparsa](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>Il controllo del processo di analisi di perdita dei dati

È possibile cercare il Registro di controllo di Office 365 per le attività di eDiscovery che sono stati eseguiti durante le indagini. È inoltre possibile cercare il Registro di controllo per restituire i record di verifica che sono stati creati durante l'esecuzione di comandi **Search-Mailbox DeleteContent** per eliminare i dati espanso. Per ulteriori informazioni, vedere:

- [Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità di Office 365](search-the-audit-log-in-security-and-compliance.md)

- [Ricerca di eDiscovery attività nel Registro di controllo di Office 365](search-for-ediscovery-activities-in-the-audit-log.md)

- Vedere la sezione "Controllati - attività del Registro di controllo di amministrazione di Exchange" in [ricerca il controllo di accesso nel centro conformità protezione di Office 365](search-the-audit-log-in-security-and-compliance.md#audited-activities) per istruzioni su come effettuare una ricerca per i record di controllo relative alle eseguiti i cmdlet di Exchange Online.
  

