---
title: Panoramica delle cassette postali inattive in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/1/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: Informazioni su come conservare il contenuto delle cassette postali per gli ex dipendenti trasformando la cassetta postale in una cassetta postale inattiva. A tale scopo, inserire la cassetta postale sul blocco per controversia legale o applicare un criterio di conservazione di Office 365 alla cassetta postale e quindi rimuovere l'account di Office 365 corrispondente.
ms.openlocfilehash: 67027ecd06771c0369e7f150c9eaa3e2030e2aab
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216686"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>Panoramica delle cassette postali inattive in Office 365

L'organizzazione potrebbe dover mantenere la posta elettronica di un ex dipendente dopo l'uscita dall'organizzazione. In base ai requisiti di conservazione dell'organizzazione, potrebbe essere necessario conservare il contenuto delle cassette postali per alcuni mesi o anni dopo l'orario di lavoro oppure potrebbe essere necessario conservare il contenuto delle cassette postali per un periodo di tempo indefinito. Indipendentemente dal tempo necessario per mantenere la posta elettronica, è possibile creare cassette postali inattive in Office 365 per mantenere la cassetta postale di ex dipendenti. 
  
## <a name="what-are-inactive-mailboxes"></a>Cosa sono le cassette postali inattive?

Quando un dipendente lascia l'organizzazione (o prosegue un congedo prolungato), è possibile rimuovere il proprio account di Office 365. I dati della cassetta postale del dipendente vengono conservati per 30 giorni dopo che l'account è stato rimosso. Durante questo periodo, è comunque possibile ripristinare i dati della cassetta postale eliminando l'account. Dopo 30 giorni, i dati vengono rimossi definitivamente.
  
Tuttavia, se l'organizzazione deve conservare il contenuto delle cassette postali per gli ex dipendenti, è possibile trasformare la cassetta postale in una cassetta postale inattiva posizionando la cassetta postale sul blocco per controversia legale o applicando un criterio &amp; di conservazione di Office 365 alla cassetta postale nella sicurezza di Office 365. Centro conformità e quindi rimozione dell'account Office 365 corrispondente. I contenuti di una cassetta postale inattiva vengono conservati per la durata del blocco per controversia legale posto sulla cassetta postale o il periodo di conservazione del criterio di conservazione di Office 365 applicato all'oggetto prima che la cassetta postale sia stata eliminata. È comunque possibile recuperare l'account utente corrispondente per un periodo di 30 giorni. Tuttavia, dopo 30 giorni, la cassetta postale inattiva viene conservata in Office 365 fino a quando non viene rimosso il blocco o il criterio di conservazione. 
  
**Importante:** La data di scadenza del 1 ° luglio 2017 è stata posticipata per la creazione di nuove esenzioni sul posto per rendere inattiva una cassetta postale. Ma entro la fine dell'anno o all'inizio del prossimo anno, non sarà possibile creare nuove archiviazioni sul posto in Exchange Online. A quel punto, è possibile utilizzare solo controversia legale e i criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti che si trovano in archiviazione sul posto continueranno a essere supportate ed è possibile continuare a gestire le archiviazioni sul posto sulle cassette postali inattive. Ciò include la modifica della durata di un blocco sul posto e l'eliminazione definitiva di una cassetta postale inattiva rimuovendo il blocco sul posto. 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>Le cassette postali inattive e i criteri di conservazione di Office 365

Oltre alla conservazione per controversia legale, l'utilizzo della nuova caratteristica criteri di ritenzione di &amp; Office 365 nel centro sicurezza e conformità è un altro modo per rendere inattiva una cassetta postale. Per utilizzare un criterio di conservazione per rendere una cassetta postale inattiva: 
  
- Deve essere applicato alle cassette postali di Exchange o a percorsi di Skype for Business (perché i contenuti correlati di Skype vengono archiviati nella cassetta postale dell'utente). 
    
- Deve essere configurato per conservare i contenuti o conservare e poi eliminare i contenuti. Se il criterio di conservazione è configurato solo per eliminare i contenuti, una cassetta postale alla quale viene applicato il criterio non diventerà inattiva quando la cassetta postale viene eliminata.
    
- Può essere basato su query affinché conservi quindi solo elementi corrispondenti a una query di ricerca. 
    
Per ulteriori informazioni sulla configurazione dei criteri di conservazione di Office 365, vedere [Panoramica dei criteri di conservazione in Office 365](retention-policies.md).
  
Se si usa un criterio di conservazione di Office 365 per rendere inattiva una cassetta postale, Office 365 continuerà a elaborare il criterio di conservazione nella cassetta postale inattiva. Questo significa che se i criteri di conservazione sono configurato per mantenere ed eliminare contenuto, gli elementi verranno spostati nella cartella Elementi ripristinabili alla scadenza del periodo di conservazione e verranno alla fine eliminati dalla cassetta postale inattiva. Se il criterio di conservazione Office 365 non è configurato per la posta eliminata, allora gli elementi che non vengano eliminati definitivamente dall'utente (prima che la cassetta postale è stata resa inattiva) non verranno spostati nella cartella Elementi ripristinabili e verranno conservati indefinitamente dopo la disattivazione della cassetta postale. 
  
È consigliabile creare un criterio di conservazione Office 365 specifico per le cassette postali inattive. Vengono elencati di seguito alcuni motivi di tale operazione e considerazioni importanti da valutare:
  
- È possibile configurare i criteri di conservazione per conservare il contenuto della cassetta postale solo purché necessari per soddisfare i requisiti dell'organizzazione per ex dipendenti.
    
- Si tratta di un modo semplice per identificare le cassette postali inattive perché il criterio di conservazione viene applicato solo alle cassette postali inattive.
    
- È possibile identificare facilmente i criteri di conservazione assegnati alle cassette postali inattive nell'organizzazione. In questo modo è più facile modificare le impostazioni di conservazione (o eliminazione), se necessario. Sarà inoltre più facile eliminare definitivamente una cassetta postale inattiva perché è possibile rimuoverla dal criterio utilizzando il Centro sicurezza &amp; e conformità. In caso contrario, è necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva o utilizzare PowerShell di centro conformità di sicurezza &amp; per escludere una cassetta postale inattiva da un criterio di conservazione di Office 365 a livello di organizzazione.
    
- Se si crea un criterio di conservazione Office 365 specifico per le cassette postali inattive, è possibile aggiungere un massimo di 1.000 cassette postali al criterio. Se si è un'organizzazione di dimensioni molto grandi, potrebbe essere necessario creare più criteri di conservazione Office 365 da utilizzare per le cassette postali inattive.
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Le cassette postali inattive e i blocchi dei casi di eDiscovery

Se una conservazione associata a un caso di eDiscovery nel centro sicurezza &amp; e conformità è posizionata su una cassetta postale e quindi viene eliminata la cassetta postale o l'account Office 365 dell'utente, la cassetta postale diventerà una cassetta postale inattiva. Tuttavia, non è consigliabile utilizzare eDiscovery case holds per rendere inattiva una cassetta postale. Ciò è dovuto al fatto che i casi di eDiscovery sono destinati a casi specifici relativi a un problema legale. A un certo punto, probabilmente si concluderà un caso legale e le esenzioni associate al caso verranno rimosse e il caso di eDiscovery verrà chiuso. In effetti, se una conservazione che viene inserita in una cassetta postale inattiva è associata a un caso di eDiscovery e quindi il blocco viene rilasciato o il caso eDiscovery è chiuso (o eliminato), la cassetta postale inattiva viene eliminata definitivamente. Inoltre, non è possibile creare un blocco di eDiscovery basato sul tempo. Questo significa che il contenuto di una cassetta postale inattiva verrà mantenuto per sempre o finché il blocco non viene rimosso e la cassetta postale inattiva viene eliminata. Pertanto, si consiglia di utilizzare un blocco per controversia legale o un criterio di conservazione per le cassette postali inattive di Office 365.
  
Per ulteriori informazioni sui casi e le esenzioni di eDiscovery, vedere [eDiscovery Cases in &amp; The Office 365 Security Compliance Center](ediscovery-cases.md).
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>Le cassette postali inattive e le etichette di Office 365

Le etichette in Office 365 consentono di classificare i dati della posta elettronica nell'organizzazione per governance e di applicare le regole di conservazione in base a tale classificazione. Un'etichetta può essere applicata a un elemento di posta elettronica manualmente dagli utenti o automaticamente dagli amministratori e a un elemento di posta elettronica può essere assegnata una sola etichetta. Se a un singolo elemento di posta in una cassetta postale utente è stata assegnata un'etichetta e la cassetta postale o l'account utente di Office 365 viene eliminato, la cassetta postale diventerà una cassetta postale inattiva. Come per i blocchi dei casi di eDiscovery, non è consigliabile utilizzare le etichette per rendere inattiva una cassetta postale. Pertanto, è consigliabile usare il blocco per controversia legale o un criterio di conservazione di Office 365. Tenere presente che in caso di etichette, si potrebbe non rendersi conto che un'etichetta è stata applicata a un elemento di posta elettronica e quindi si potrebbe inavvertitamente rendere una cassetta postale inattiva quando si elimina l'account dell'utente. 
  
Per ulteriori informazioni, vedere [Panoramica delle etichette in Office 365](labels.md).
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Le cassette postali inattive e i criteri di conservazione di Exchange MRM

Se un criterio di conservazione di Exchange (la funzionalità di gestione dei record di messaggistica, o di messaggistica istantanea in Exchange Online) è stato applicato alla cassetta postale quando è stato reso inattivo, tutti i criteri di eliminazione (ovvero i tag di conservazione configurati con un'azione di conservazione **Delete** ) verranno continuare a essere elaborati nella cassetta postale inattiva. Questo significa che gli elementi contrassegnati con un criterio di eliminazione verranno spostati nella cartella elementi ripristinabili quando scade il periodo di conservazione. Tali elementi vengono eliminati dalla cassetta postale inattiva quando scade la durata del blocco. Se non viene specificata una durata di conservazione per la cassetta postale inattiva, gli elementi nella cartella Ripristina elementi vengono conservati a tempo indeterminato. 
  
Al contrario, qualsiasi criterio di archiviazione (vale a dire tag di configurazione configurati con un'azione conservazione **MoveToArchive**) incluso in un criterio di conservazione assegnato a una cassetta postale inattiva viene ignorato. Questo significa che gli elementi in una cassetta postale inattiva contrassegnati con un criterio di archiviazione rimarranno nella cassetta postale principale quando scade il periodo di conservazione. Non vengono spostati nella cassetta postale di archiviazione o nella cartella Elementi ripristinabili nella cassetta postale di archiviazione. Verranno conservati a tempo indeterminato. 
  
## <a name="creating-an-inactive-mailbox"></a>Creazione di una cassetta postale inattiva

Per rendere inattiva una cassetta postale, deve essere assegnata una licenza di Exchange Online (piano 2), in modo che sia possibile applicare un blocco per controversia legale o un criterio di conservazione di Office 365 alla cassetta postale prima che venga eliminata. Dopo che la cassetta postale è stata eliminata, la licenza di Exchange Online associata sarà disponibile per l'assegnazione a un nuovo utente. Le cassette postali inattive non richiedono licenze in uscita.
  
Nella tabella seguente viene riepilogato il processo di esecuzione di una cassetta postale inattiva per diversi scenari di conservazione. Per ulteriori informazioni, vedere [gestire le cassette postali inattive in Office 365](create-and-manage-inactive-mailboxes.md).
  
|**Per...**|**Eseguire questa operazione...**|**Risultato**|
|:-----|:-----|:-----|
|Conservare il contenuto della cassetta postale a tempo indeterminato dopo che un impiegato lascia l'organizzazione  <br/> | Attivare il blocco per controversia legale in una cassetta postale o applicare un criterio di conservazione di Office 365 alla cassetta postale.  <br/>  Non specificare la durata di un blocco per il blocco per controversia legale oppure non configurare Office 365 criterio di conservazione per eliminare gli elementi; in alternativa è possibile utilizzare un criterio di conservazione che conserva gli elementi per sempre.  <br/>  Rimuovere l'account utente di Office 365.  <br/> |Tutto il contenuto della cassetta postale inattiva, inclusi gli elementi nella cartella elementi ripristinabili, viene mantenuto a tempo indeterminato.  <br/> |
|Conservare il contenuto della cassetta postale per un periodo specifico dopo che un impiegato lascia l'organizzazione e quindi eliminarlo  <br/> | Applicare un criterio di conservazione di Office 365 alla cassetta postale.  <br/>  Configurare il criterio di conservazione per mantenere e quindi eliminare gli elementi al termine della scadenza del periodo di conservazione.  <br/>  Rimuovere l'account utente di Office 365.  <br/> |Quando il periodo di conservazione per un elemento della cassetta postale scade, l'elemento viene spostato nella cartella elementi ripristinabili e quindi viene eliminato definitivamente (eliminato) dalla cassetta postale inattiva quando scade il periodo di conservazione degli elementi eliminati (per le cassette postali di Exchange). Il periodo di conservazione dei criteri di conservazione di Office 365 può essere configurato in base alla data originale di ricezione o creazione di un elemento della cassetta postale o al momento dell'Ultima modifica.  <br/> |
   
**Nota:** Se un blocco per controversia legale è già stato inserito in una cassetta postale o se è già stato applicato un criterio di conservazione di Office 365, è necessario eliminare l'account utente di Office 365 corrispondente per creare una cassetta postale inattiva. 
  
## <a name="managing-inactive-mailboxes"></a>Gestione di una cassetta postale inattiva

Dopo aver reso inattiva una cassetta postale, è possibile eseguire varie attività di gestione nelle cassette postali inattive.
  
- **Modificare la durata del blocco per una cassetta postale inattiva** Dopo aver reso inattiva una cassetta postale, è possibile modificare la durata del blocco per controversia legale o il criterio di conservazione di Office 365 applicato alla cassetta postale inattiva. Per le procedure dettagliate, vedere [modificare la durata del blocco per una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
    
- **Recuperare una cassetta postale inattiva** Se un ex dipendente (o un dipendente in congedo) torna alla propria organizzazione o se un nuovo dipendente viene assunto per assumersi le responsabilità professionali dell'ex dipendente, è possibile recuperare il contenuto della cassetta postale inattiva. Quando si ripristina una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, il contenuto e la struttura delle cartelle della cassetta postale inattiva vengono mantenuti e la cassetta postale è collegata a un nuovo account utente. Dopo il ripristino, la cassetta postale inattiva non esiste più. Per le procedure dettagliate e le informazioni su ciò che accade quando si recupera una cassetta postale inattiva, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- **Ripristinare una cassetta postale inattiva** Se un altro dipendente assume le responsabilità del lavoro di un ex dipendente o se un'altra persona ha bisogno dell'accesso al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva a una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane una cassetta postale inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando gli strumenti di eDiscovery, i suoi contenuti possono essere ripristinati in un'altra cassetta postale e può essere recuperata o eliminata in un secondo momento. Per le procedure dettagliate, vedere [ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
    
- **Eliminare una cassetta postale inattiva** Quando non è più necessario conservare il contenuto di una cassetta postale inattiva, è possibile eliminarlo definitivamente rimuovendo tutti i criteri di conservazione o di Office 365 applicati alla cassetta postale inattiva. Se una cassetta postale è stata resa inattiva più di 30 giorni fa, verrà contrassegnata per l'eliminazione definitiva dopo aver rimosso il blocco. Se la cassetta postale è stata resa inattiva negli ultimi 30 giorni, è possibile riattivarla dopo aver rimosso il blocco o il criterio di conservazione. Per le procedure dettagliate, vedere [eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md).