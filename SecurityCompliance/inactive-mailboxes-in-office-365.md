---
title: Panoramica delle cassette postali inattive in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/1/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: Informazioni sulla conservazione del contenuto delle cassette postali per i dipendenti precedenti attivando la cassetta postale in una cassetta postale inattiva. È possibile farlo effettuando la cassetta postale di conservazione per controversia legale o applicare un criterio di conservazione di Office 365 per la cassetta postale e quindi rimuovere l'account di Office 365 corrispondente.
ms.openlocfilehash: 5b421e32df99a10d13528fe7a75e6a0e8fb54fdc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530871"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>Panoramica delle cassette postali inattive in Office 365

L'organizzazione potrebbe essere necessario mantenere posta elettronica ex dipendenti una volta terminata l'organizzazione. A seconda dei requisiti di conservazione dell'organizzazione, potrebbe essere necessario conservare il contenuto delle cassette postali per alcuni mesi o anni termine occupazione o si potrebbe essere necessario conservare il contenuto delle cassette postali per un tempo indefinito. Indipendentemente dal fatto quanto tempo è necessario mantenere posta elettronica, è possibile creare cassette postali inattive in Office 365 per mantenere la cassetta postale di dipendenti precedente. 
  
## <a name="what-are-inactive-mailboxes"></a>Cosa sono le cassette postali inattive?

Quando un dipendente lascia l'organizzazione (o viene inserito in una prolungata assenza), è possibile rimuovere il proprio account di Office 365. Dati delle cassette postali del dipendente viene mantenuti per 30 giorni dopo che l'account è stato rimosso. Durante questo periodo, è comunque possibile ripristinare i dati delle cassette postali per l'account di annullamento dell'eliminazione. Dopo 30 giorni, i dati vengono rimossi definitivamente.
  
Se l'organizzazione deve mantenere il contenuto delle cassette postali per i dipendenti precedenti, è anche possibile attivare la cassetta postale in una cassetta postale inattiva posizionando la cassetta postale di conservazione per controversia legale o applicare un criterio di conservazione di Office 365 per la cassetta postale in Office 365 Security &amp; Centro conformità e quindi rimuovere l'account di Office 365 corrispondente. Il contenuto di una cassetta postale inattiva viene mantenuto per la durata della conservazione per controversia legale effettuata nella cassetta postale o il periodo di conservazione dei criteri di conservazione di Office 365 applicato prima che la cassetta postale è stata eliminata. È comunque possibile ripristinare l'account utente corrispondente per un periodo di 30 giorni. Tuttavia, dopo 30 giorni, cassette postali inattive viene mantenuta in Office 365 fino a quando non viene rimosso il criterio di conservazione o conservazione. 
  
**Importante:** È stata posticipata la scadenza del 1 ° luglio 2017 per la creazione di nuove archiviazioni sul posto per rendere inattiva una cassetta postale. Ma più avanti in questo anno o un anno successivo anticipati, non sarà in grado di creare nuove archiviazioni sul posto di Exchange Online. A quel punto, solo i criteri di conservazione contiene controversie legali e Office 365 possono essere utilizzati per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti presenti In-Place Hold continueranno a essere supportate ed è possibile continuare a gestire In-Place Holds sulle cassette postali inattive. Sono incluse cambiare la durata di an In-Place Hold e in modo permanente l'eliminazione di una cassetta postale inattiva rimuovendo l'archiviazione sul posto. 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>Le cassette postali inattive e i criteri di conservazione di Office 365

Oltre a conservazione per controversia legale, utilizzando la nuova funzionalità di criteri di conservazione Office 365 nella protezione &amp; centro conformità è un altro modo per rendere inattiva una cassetta postale. Per utilizzare un criterio di conservazione per effettuare una cassetta postale inattiva: 
  
- Deve essere applicato alle cassette postali di Exchange o a percorsi di Skype for Business (perché i contenuti correlati di Skype vengono archiviati nella cassetta postale dell'utente). 
    
- Deve essere configurato per conservare i contenuti o conservare e poi eliminare i contenuti. Se il criterio di conservazione è configurato solo per eliminare i contenuti, una cassetta postale alla quale viene applicato il criterio non diventerà inattiva quando la cassetta postale viene eliminata.
    
- Può essere basato su query affinché conservi quindi solo elementi corrispondenti a una query di ricerca. 
    
Per ulteriori informazioni sulla configurazione dei criteri di conservazione di Office 365, vedere [Panoramica dei criteri di conservazione in Office 365](retention-policies.md).
  
Se si usa un criterio di conservazione di Office 365 per rendere inattiva una cassetta postale, Office 365 continuerà a elaborare il criterio di conservazione nella cassetta postale inattiva. Questo significa che se i criteri di conservazione sono configurato per mantenere ed eliminare contenuto, gli elementi verranno spostati nella cartella Elementi ripristinabili alla scadenza del periodo di conservazione e verranno alla fine eliminati dalla cassetta postale inattiva. Se il criterio di conservazione Office 365 non è configurato per la posta eliminata, allora gli elementi che non vengano eliminati definitivamente dall'utente (prima che la cassetta postale è stata resa inattiva) non verranno spostati nella cartella Elementi ripristinabili e verranno conservati indefinitamente dopo la disattivazione della cassetta postale. 
  
È consigliabile creare un criterio di conservazione Office 365 specifico per le cassette postali inattive. Vengono elencati di seguito alcuni motivi di tale operazione e considerazioni importanti da valutare:
  
- È possibile configurare i criteri di conservazione per conservare il contenuto della cassetta postale solo purché necessari per soddisfare i requisiti dell'organizzazione per ex dipendenti.
    
- È un modo semplice per identificare le cassette postali inattive in quanto il criterio di conservazione verrà applicato solo alle cassette postali inattive.
    
- Sarà in grado di identificare facilmente il criterio di conservazione viene assegnato a cassette postali inattive all'interno dell'organizzazione. Ciò consentirà più semplice modificare le impostazioni di conservazione (o eliminazione), se necessario. Inoltre faciliterà eliminare definitivamente una cassetta postale inattiva dal momento che è appena possibile rimuoverlo dal criterio utilizzando la protezione &amp; centro conformità. In caso contrario, è necessario utilizzare Exchange Online PowerShell per rimuovere una conservazione per controversia legale di una cassetta postale inattiva o utilizzare la protezione &amp; PowerShell centro conformità per escludere una cassetta postale inattiva da un criterio di conservazione a livello di organizzazione Office 365.
    
- Se si crea un criterio di conservazione Office 365 specifico per le cassette postali inattive, è possibile aggiungere un massimo di 1.000 cassette postali al criterio. Se si è un'organizzazione di dimensioni molto grandi, potrebbe essere necessario creare più criteri di conservazione Office 365 da utilizzare per le cassette postali inattive.
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Le cassette postali inattive e i blocchi dei casi di eDiscovery

Se un'esenzione associata a un caso eDiscovery in sicurezza &amp; centro conformità viene messa in una cassetta postale e quindi la cassetta postale o viene eliminato l'account dell'utente Office 365, la cassetta postale diventeranno una cassetta postale inattiva. Tuttavia, si consiglia di non utilizzo caso di eDiscovery contiene per rendere inattiva una cassetta postale. Ciò avviene perché casi di eDiscovery sono destinati ai casi specifici di specifici relativi a un problema legale. Un certo punto, una controversia legale probabilmente verrà terminata e vengono rimosse le conservazioni associate al caso e il caso di eDiscovery verrà chiuso. In effetti, se un'esenzione che viene inserita in una cassetta postale inattiva associato a un caso eDiscovery e quindi Rilascia esenzione o eDiscovery case viene chiuso (o eliminata), verrà eliminata definitivamente la cassetta postale inattiva. È inoltre possibile creare un'esenzione di eDiscovery basate sul tempo. Ciò è indica che il contenuto in una cassetta postale inattiva verrà mantenuto per sempre o fino a quando non viene rimossa la sospensione e viene eliminata la cassetta postale inattiva. Di conseguenza, è consigliabile utilizzare conservazione per controversia legale o un criterio di conservazione di Office 365 per le cassette postali inattive.
  
Per ulteriori informazioni sui casi di eDiscovery e archiviazione, vedere [casi di eDiscovery in Office 365 Security &amp; centro conformità](ediscovery-cases.md).
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>Le cassette postali inattive e le etichette di Office 365

Le etichette in Office 365 consentono di classificare i dati della posta elettronica nell'organizzazione per governance e di applicare le regole di conservazione in base a tale classificazione. Un'etichetta può essere applicata a un elemento di posta elettronica manualmente dagli utenti o automaticamente dagli amministratori e a un elemento di posta elettronica può essere assegnata una sola etichetta. Se a un singolo elemento di posta in una cassetta postale utente è stata assegnata un'etichetta e la cassetta postale o l'account utente di Office 365 viene eliminato, la cassetta postale diventerà una cassetta postale inattiva. Come per i blocchi dei casi di eDiscovery, non è consigliabile utilizzare le etichette per rendere inattiva una cassetta postale. Pertanto, è consigliabile usare il blocco per controversia legale o un criterio di conservazione di Office 365. Tenere presente che in caso di etichette, si potrebbe non rendersi conto che un'etichetta è stata applicata a un elemento di posta elettronica e quindi si potrebbe inavvertitamente rendere una cassetta postale inattiva quando si elimina l'account dell'utente. 
  
Per ulteriori informazioni, vedere [Panoramica delle etichette in Office 365](labels.md).
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Le cassette postali inattive e i criteri di conservazione di Exchange MRM

Se un criterio di conservazione di Exchange (funzionalità Gestione record di messaggistica o MRM, in Exchange Online) sono stato applicato alla cassetta postale quando è stata effettuata inattiva, tutti i criteri di eliminazione, che sono configurati con un'azione di conservazione **eliminare** i tag di conservazione, verrà continuano a essere elaborati sulla cassetta postale inattiva. Ciò significa che verranno spostati gli elementi contrassegnati con un criterio di eliminazione per la cartella elementi ripristinabili quando scade il periodo di conservazione. Questi elementi vengono eliminati dalla cassetta postale inattiva quando scade la durata dell'attesa. Se non viene specificato un intervallo di tempo di attesa per la cassetta postale inattiva, elementi nella cartella Recupera elementi verranno mantenuti indefinitamente. 
  
Al contrario, qualsiasi criterio di archiviazione (vale a dire tag di configurazione configurati con un'azione conservazione **MoveToArchive**) incluso in un criterio di conservazione assegnato a una cassetta postale inattiva viene ignorato. Questo significa che gli elementi in una cassetta postale inattiva contrassegnati con un criterio di archiviazione rimarranno nella cassetta postale principale quando scade il periodo di conservazione. Non vengono spostati nella cassetta postale di archiviazione o nella cartella Elementi ripristinabili nella cassetta postale di archiviazione. Verranno conservati a tempo indeterminato. 
  
## <a name="creating-an-inactive-mailbox"></a>Creazione di una cassetta postale inattiva

Per rendere inattiva una cassetta postale, è necessario assegnare una licenza di Exchange Online (piano 2) in modo che un criterio di conservazione conservazione per controversia legale o Office 365 può essere applicato alla cassetta postale prima che venga eliminato. Dopo che la cassetta postale eliminata, la licenza di Exchange Online che è stata associata sarà disponibile per assegnare a un nuovo utente. Cassette postali inattive non richiedono le licenze in corso.
  
Nella tabella seguente viene riepilogato il processo di esecuzione di una cassetta postale inattiva per gli scenari di conservazione diversi. Per ulteriori informazioni, vedere [gestire cassette postali inattive in Office 365](create-and-manage-inactive-mailboxes.md).
  
|**Per...**|**Eseguire questa operazione...**|**Risultato**|
|:-----|:-----|:-----|
|Conservare il contenuto della cassetta postale a tempo indeterminato dopo che un impiegato lascia l'organizzazione  <br/> | Attivare il blocco per controversia legale in una cassetta postale o applicare un criterio di conservazione di Office 365 alla cassetta postale.  <br/>  Non specificare la durata di un blocco per il blocco per controversia legale oppure non configurare Office 365 criterio di conservazione per eliminare gli elementi; in alternativa è possibile utilizzare un criterio di conservazione che conserva gli elementi per sempre.  <br/>  Rimuovere l'account utente di Office 365.  <br/> |Tutto il contenuto della cassetta postale inattiva, inclusi gli elementi nella cartella elementi recuperabili viene conservato per un tempo indefinito.  <br/> |
|Conservare il contenuto della cassetta postale per un periodo specifico dopo che un impiegato lascia l'organizzazione e quindi eliminarlo  <br/> | Applicare un criterio di conservazione di Office 365 per la cassetta postale.  <br/>  Configurare il criterio di conservazione per mantenere ed eliminare elementi quando scade il periodo di conservazione.  <br/>  Rimuovere l'account utente di Office 365.  <br/> |Quando scade il periodo di conservazione per un elemento della cassetta postale, l'elemento viene spostato nella cartella elementi recuperabili e quindi che viene eliminato definitivamente (cancellati) dalla cassetta postale inattiva allo scadere del periodo di mantenimento elementi eliminati (cassette postali di Exchange). Il periodo di conservazione dei criteri di conservazione Office 365 può essere configurato in base alla data originale è stato ricevuto o creato una cassetta postale o dell'ultima modifica.  <br/> |
   
**Nota:** Se una conservazione per controversia legale è già posizionato in una cassetta postale o un criterio di conservazione di Office 365 è già stato applicato, sarà sufficiente è eliminare l'account utente di Office 365 corrispondente per creare una cassetta postale inattiva. 
  
## <a name="managing-inactive-mailboxes"></a>Gestione di una cassetta postale inattiva

Dopo aver reso inattiva una cassetta postale, è possibile eseguire varie attività di gestione nelle cassette postali inattive.
  
- **Modifica la durata della conservazione per una cassetta postale inattiva** Dopo aver effettuata una cassetta postale inattiva, è possibile modificare la durata di attesa di conservazione per controversia legale o Office 365 dei criteri di conservazione applicato a cassette postali inattive. Per le procedure dettagliate, vedere [modificare la durata della conservazione per una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
    
- **Ripristinare una cassetta postale inattiva** Se un dipendente precedente (o un dipendente in congedo di) restituisce all'organizzazione o un nuovo dipendente è stato assunto deve essere eseguita su professionali del dipendente precedente, è possibile ripristinare il contenuto delle cassette postali inattive. Quando si ripristina una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, vengono mantenuti il contenuto e struttura di cartelle delle cassette postali inattive e la cassetta postale è collegata a un nuovo account utente. Dopo avere recuperato, cassette postali inattive non esiste più. Per informazioni su cosa succede quando si ripristina una cassetta postale inattiva e procedure dettagliate, vedere [ripristino di una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- **Ripristinare una cassetta postale inattiva** Se l'altro impiegato assume la responsabilità di un dipendente precedente o un'altra persona deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva per una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. Cassette postali inattive viene mantenuta e manterrà una cassetta postale inattiva. Cassette postali inattive possono essere ricercate ancora utilizzando gli strumenti di eDiscovery, è possibile ripristinare il contenuto a un'altra cassetta postale e possono essere ripristinato o eliminato in un secondo momento. Per le procedure dettagliate, vedere [ripristino di una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
    
- **Eliminare una cassetta postale inattiva** Quando non più necessaria mantenere il contenuto di una cassetta postale inattiva, è possibile eliminare definitivamente Elimina tutte le esenzioni o Office 365 i criteri di conservazione applicati a cassette postali inattive. Se una cassetta postale è stata effettuata inattiva negli ultimi 30 giorni fa, verrà contrassegnato per l'eliminazione definitiva dopo la rimozione dell'esenzione. Se la cassetta postale è stata effettuata inattiva negli ultimi 30 giorni, si può rendere attiva nuovamente dopo aver rimosso il criterio di conservazione o conservazione. Per le procedure dettagliate, vedere [eliminazione di una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md).