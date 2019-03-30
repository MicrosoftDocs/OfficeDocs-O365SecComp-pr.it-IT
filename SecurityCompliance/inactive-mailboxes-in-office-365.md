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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: Informazioni su come conservare il contenuto delle cassette postali per gli ex dipendenti trasformando la cassetta postale in una cassetta postale inattiva. A tale scopo, inserire la cassetta postale sul blocco per controversia legale o applicare un criterio di conservazione di Office 365 alla cassetta postale e quindi rimuovere l'account di Office 365 corrispondente.
ms.openlocfilehash: 12688cb1c0f1d165c21736ce5a6130245db36a06
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000799"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>Panoramica delle cassette postali inattive in Office 365

L'organizzazione potrebbe dover conservare l'indirizzo di posta elettronica di dipendenti precedenti dopo che lasciano l'organizzazione. In base ai requisiti di conservazione dell'organizzazione, potrebbe essere necessario conservare il contenuto della cassetta postale per pochi mesi o anni dopo il termine dell'impiego oppure potrebbe essere necessario conservare il contenuto della cassetta postale all'infinito. Indipendentemente dal tempo necessario per mantenere la posta elettronica, è possibile creare cassette postali inattive in Office 365 per mantenere la cassetta postale di ex dipendenti. 
  
## <a name="what-are-inactive-mailboxes"></a>Cosa sono le cassette postali inattive?

Quando un dipendente lascia l'organizzazione (o prosegue un congedo prolungato), è possibile rimuovere il proprio account di Office 365. I dati della cassetta postale del dipendente vengono conservati per 30 giorni dopo che l'account è stato rimosso. Durante questo periodo, è comunque possibile ripristinare i dati della cassetta postale eliminando l'account. Dopo 30 giorni, i dati vengono rimossi definitivamente.
  
Tuttavia, se l'organizzazione deve conservare il contenuto delle cassette postali per gli ex dipendenti, è possibile trasformare la cassetta postale in una cassetta postale inattiva posizionando la cassetta postale sul blocco per controversia legale o applicando un criterio di conservazione di Office 365 alla cassetta postale nel centro sicurezza & Compliance. e quindi rimuovendo l'account Office 365 corrispondente. The contents of an inactive mailbox are retained for the duration of the Litigation Hold placed on the mailbox or the retention period of the Office 365 retention policy applied to it before the mailbox was deleted. You can still recover the corresponding user account for a 30-day period. Tuttavia, dopo 30 giorni, la cassetta postale inattiva viene conservata in Office 365 fino a quando non viene rimosso il blocco o il criterio di conservazione. 
  
**Importante:** La data di scadenza del 1 ° luglio 2017 è stata posticipata per la creazione di nuove esenzioni sul posto per rendere inattiva una cassetta postale. Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. Da quel momento, sarà possibile utilizzare soltanto blocchi per controversia legale e criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti disponibili nel blocco sul posto continueranno a essere supportate ed è possibile continuare a gestire i blocchi per controversia legale sulle cassette postali inattive. Ciò include le operazioni di modifica della durata di un blocco sul posto e di eliminazione definitiva di una cassetta postale inattiva mediante la rimozione del blocco sul posto. 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>Le cassette postali inattive e i criteri di conservazione di Office 365

Oltre alla conservazione per controversia legale, l'utilizzo della nuova caratteristica criteri di ritenzione di Office 365 nel centro sicurezza & Compliance è un altro modo per rendere inattiva una cassetta postale. To use a retention policy to make an inactive mailbox: 
  
- Deve essere applicato alle cassette postali di Exchange o a percorsi di Skype for Business (perché i contenuti correlati di Skype vengono archiviati nella cassetta postale dell'utente). 
    
- Deve essere configurato per conservare i contenuti o conservare e poi eliminare i contenuti. Se il criterio di conservazione è configurato solo per eliminare i contenuti, una cassetta postale alla quale viene applicato il criterio non diventerà inattiva quando la cassetta postale viene eliminata.
    
- Può essere basato su query affinché conservi quindi solo elementi corrispondenti a una query di ricerca. 
    
Per ulteriori informazioni sulla configurazione dei criteri di conservazione di Office 365, vedere [Panoramica dei criteri di conservazione in Office 365](retention-policies.md).
  
Se si usa un criterio di conservazione di Office 365 per rendere inattiva una cassetta postale, Office 365 continuerà a elaborare il criterio di conservazione nella cassetta postale inattiva. Questo significa che se i criteri di conservazione sono configurato per mantenere ed eliminare contenuto, gli elementi verranno spostati nella cartella Elementi ripristinabili alla scadenza del periodo di conservazione e verranno alla fine eliminati dalla cassetta postale inattiva. Se il criterio di conservazione Office 365 non è configurato per la posta eliminata, allora gli elementi che non vengano eliminati definitivamente dall'utente (prima che la cassetta postale è stata resa inattiva) non verranno spostati nella cartella Elementi ripristinabili e verranno conservati indefinitamente dopo la disattivazione della cassetta postale. 
  
È consigliabile creare un criterio di conservazione Office 365 specifico per le cassette postali inattive. Vengono elencati di seguito alcuni motivi di tale operazione e considerazioni importanti da valutare:
  
- È possibile configurare i criteri di conservazione per conservare il contenuto della cassetta postale solo purché necessari per soddisfare i requisiti dell'organizzazione per ex dipendenti.
    
- Si tratta di un modo semplice per identificare le cassette postali inattive perché il criterio di conservazione viene applicato solo alle cassette postali inattive.
    
- You'll be able to easily identify the retention policy that's assigned to inactive mailboxes in your organization. This will make it easier to change the retention (or deletion) settings if necessary. Sarà inoltre più facile eliminare definitivamente una cassetta postale inattiva perché è possibile rimuoverla solo dal criterio utilizzando il Centro sicurezza & Compliance. In caso contrario, è necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva o utilizzare PowerShell di & Compliance Center di sicurezza per escludere una cassetta postale inattiva da un criterio di conservazione di Office 365 a livello di organizzazione.
    
- Se si crea un criterio di conservazione Office 365 specifico per le cassette postali inattive, è possibile aggiungere un massimo di 1.000 cassette postali al criterio. Se si è un'organizzazione di dimensioni molto grandi, potrebbe essere necessario creare più criteri di conservazione Office 365 da utilizzare per le cassette postali inattive.
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Le cassette postali inattive e i blocchi dei casi di eDiscovery

Se una conservazione associata a un caso di eDiscovery nel centro conformità di sicurezza & è impostata su una cassetta postale e quindi viene eliminata la cassetta postale o l'account Office 365 dell'utente, la cassetta postale diventerà una cassetta postale inattiva. However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Additionally, you can't create a time-based eDiscovery hold. That's means content in an inactive mailbox will be retained forever or until the hold is removed and the inactive mailbox is deleted. Therefore, we recommend using a Litigation Hold or an Office 365 retention policy for inactive mailboxes.
  
Per ulteriori informazioni sui casi di eDiscovery e sulle esenzioni, vedere [eDiscovery Cases](ediscovery-cases.md).
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>Le cassette postali inattive e le etichette di Office 365

Le etichette in Office 365 consentono di classificare i dati della posta elettronica nell'organizzazione per governance e di applicare le regole di conservazione in base a tale classificazione. Un'etichetta può essere applicata a un elemento di posta elettronica manualmente dagli utenti o automaticamente dagli amministratori e a un elemento di posta elettronica può essere assegnata una sola etichetta. Se a un singolo elemento di posta in una cassetta postale utente è stata assegnata un'etichetta e la cassetta postale o l'account utente di Office 365 viene eliminato, la cassetta postale diventerà una cassetta postale inattiva. Come per i blocchi dei casi di eDiscovery, non è consigliabile utilizzare le etichette per rendere inattiva una cassetta postale. Pertanto, è consigliabile usare il blocco per controversia legale o un criterio di conservazione di Office 365. Tenere presente che in caso di etichette, si potrebbe non rendersi conto che un'etichetta è stata applicata a un elemento di posta elettronica e quindi si potrebbe inavvertitamente rendere una cassetta postale inattiva quando si elimina l'account dell'utente. 
  
Per ulteriori informazioni, vedere [Panoramica delle etichette in Office 365](labels.md).
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Le cassette postali inattive e i criteri di conservazione di Exchange MRM

Se un criterio di conservazione di Exchange (la funzionalità di gestione dei record di messaggistica, o di messaggistica istantanea in Exchange Online) è stato applicato alla cassetta postale quando è stato reso inattivo, tutti i criteri di eliminazione (ovvero i tag di conservazione configurati con un'azione di conservazione **Delete** ) verranno continuare a essere elaborati nella cassetta postale inattiva. Questo significa che gli elementi che sono contrassegnati con un criterio di eliminazione verranno spostati nella cartella Elementi ripristinabili quando scade il periodo di conservazione. Questi elementi vengono eliminati dalla cassetta postale inattiva quando scade la durata di attesa. Se la durata di attesa non è specificata per la cassetta postale inattiva, gli elementi della cartella Recupera elementi verranno conservati all'infinito. 
  
Al contrario, qualsiasi criterio di archiviazione (vale a dire tag di configurazione configurati con un'azione conservazione **MoveToArchive**) incluso in un criterio di conservazione assegnato a una cassetta postale inattiva viene ignorato. Questo significa che gli elementi in una cassetta postale inattiva contrassegnati con un criterio di archiviazione rimarranno nella cassetta postale principale quando scade il periodo di conservazione. Non vengono spostati nella cassetta postale di archiviazione o nella cartella Elementi ripristinabili nella cassetta postale di archiviazione. Verranno conservati a tempo indeterminato. 
  
## <a name="creating-an-inactive-mailbox"></a>Creazione di una cassetta postale inattiva

Per rendere inattiva una cassetta postale, è necessario assegnarle una licenza Exchange Online (Piano 2) in modo da poter applicare il blocco per controversia legale o il criterio di conservazione di Office 365 prima di eliminarla. Dopo che la cassetta postale è stata eliminata, la licenza di Exchange Online associata sarà disponibile per l'assegnazione a un nuovo utente. Le cassette postali inattive non richiedono licenze attive.
  
Nella tabella seguente viene riepilogato il processo di creazione di una cassetta postale inattiva per diversi scenari di conservazione. Per ulteriori informazioni, vedere [gestire le cassette postali inattive in Office 365](create-and-manage-inactive-mailboxes.md).
  
|**Per...**|**Eseguire questa operazione...**|**Risultato**|
|:-----|:-----|:-----|
|Conservare il contenuto della cassetta postale a tempo indeterminato dopo che un impiegato lascia l'organizzazione  <br/> | Attivare il blocco per controversia legale in una cassetta postale o applicare un criterio di conservazione di Office 365 alla cassetta postale.  <br/>  Non specificare la durata di un blocco per il blocco per controversia legale oppure non configurare Office 365 criterio di conservazione per eliminare gli elementi; in alternativa è possibile utilizzare un criterio di conservazione che conserva gli elementi per sempre.  <br/>  Rimuovere l'account utente di Office 365.  <br/> |Tutto il contenuto della cassetta postale inattiva, inclusi gli elementi nella cartella elementi ripristinabili, viene mantenuto a tempo indeterminato.  <br/> |
|Conservare il contenuto della cassetta postale per un periodo specifico dopo che un impiegato lascia l'organizzazione e quindi eliminarlo  <br/> | Applicare un criterio di conservazione di Office 365 alla cassetta postale.  <br/>  Configurare il criterio di conservazione per mantenere e quindi eliminare gli elementi al termine della scadenza del periodo di conservazione.  <br/>  Rimuovere l'account utente di Office 365.  <br/> |Quando il periodo di conservazione per un elemento della cassetta postale scade, l'elemento viene spostato nella cartella elementi ripristinabili e quindi viene eliminato definitivamente (eliminato) dalla cassetta postale inattiva quando scade il periodo di conservazione degli elementi eliminati (per le cassette postali di Exchange). Il periodo di conservazione dei criteri di conservazione di Office 365 può essere configurato in base alla data originale di ricezione o creazione di un elemento della cassetta postale o al momento dell'Ultima modifica.  <br/> |
   
**Nota:** Se un blocco per controversia legale è già stato inserito in una cassetta postale o se è già stato applicato un criterio di conservazione di Office 365, è necessario eliminare l'account utente di Office 365 corrispondente per creare una cassetta postale inattiva. 
  
## <a name="managing-inactive-mailboxes"></a>Gestione di una cassetta postale inattiva

Dopo aver reso inattiva una cassetta postale, è possibile eseguire varie attività di gestione nelle cassette postali inattive.
  
- **Modificare la durata del blocco per una cassetta postale inattiva** Dopo aver reso inattiva una cassetta postale, è possibile modificare la durata del blocco per controversia legale o del criterio di conservazione di Office 365 applicato alla cassetta postale inattiva. Per le procedure dettagliate, vedere [modificare la durata del blocco per una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
    
- **Recuperare una cassetta postale inattiva** Se un ex dipendente (o un dipendente in congedo) torna nell'organizzazione oppure se un nuovo dipendente viene assunto per ricoprire il ruolo del precedente dipendente, è possibile recuperare i contenuti della cassetta postale inattiva. Quando si recupera una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, il contenuto e la struttura della cassetta postale vengono conservati e la cassetta postale viene collegata a un nuovo account utente. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Per le procedure dettagliate e le informazioni su ciò che accade quando si recupera una cassetta postale inattiva, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- **Ripristinare una cassetta postale inattiva** Se un altro dipendente assume le responsabilità di un ex dipendente o se un'altra persona deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando gli strumenti di eDiscovery, i suoi contenuti possono essere ripristinati in un'altra cassetta postale e può essere recuperata o eliminata in un secondo momento. Per le procedure dettagliate, vedere [ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
    
- **Eliminare una cassetta posta inattiva** Se non è più necessario conservare il contenuto di una cassetta postale inattiva, è possibile eliminarla definitivamente rimuovendo tutti i blocchi o i criteri di conservazione di Office 365 a essa applicati. Se una cassetta postale è stata resa inattiva da più di 30 giorni, verrà contrassegnata per l'eliminazione definitiva dopo aver rimosso il blocco. Se la cassetta postale è stata resa inattiva negli ultimi 30 giorni, è possibile attivarla di nuovo dopo aver rimosso il blocco o il criterio di conservazione. Per le procedure dettagliate, vedere [eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md).