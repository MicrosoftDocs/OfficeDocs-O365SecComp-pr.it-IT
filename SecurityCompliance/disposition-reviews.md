---
title: Panoramica delle revisioni per l'eliminazione
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: Quando si crea un'etichetta che consente di conservare il contenuto in Office 365, è possibile scegliere di attivare la revisione eliminazione alla fine del periodo di conservazione.
ms.openlocfilehash: c0a2933f597c9b314ac4ce2e72de9619fac90082
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013720"
---
# <a name="overview-of-disposition-reviews"></a>Panoramica delle revisioni per l'eliminazione

Quando è stata raggiunta la fine del periodo di conservazione, sono diversi i motivi per cui è necessario verificare che il contenuto di decidere se che può essere eliminato ("eliminati"). Ad esempio, potrebbe essere necessario:
  
- Sospendere l'eliminazione ("eliminazione") di contenuto pertinente in caso di controversia legale o un controllo.
    
- Rimuovere contenuto nell'elenco di eliminazione per l'archiviazione in un archivio, se tale contenuto dispone di ricerca o cronologiche valore.
    
- Assegnare un periodo di conservazione diversi per il contenuto, se il criterio originale non è una soluzione temporanea o provvisoria.
    
- Restituire il contenuto per i client o trasferire a un'altra organizzazione.
    
Quando si crea un'etichetta che consente di conservare il contenuto in Office 365, è possibile scegliere di attivare la revisione eliminazione alla fine del periodo di conservazione. In una revisione eliminazione:
  
- Le persone che si sceglie ricevano una notifica di posta elettronica che dispongono di contenuto per la revisione. Questi revisori possono essere singoli utenti, la distribuzione o gruppi di sicurezza o gruppi di Office 365. Si noti che le notifiche vengano inviate in una frequenza settimanale.
    
- I revisori passare alla pagina **eliminazione** della protezione &amp; centro conformità per controllare il contenuto. 
    
- Per ogni documento il revisore può:
    
  - Applica un'etichetta diversa.
    
  - Estendere il periodo di conservazione.
    
  - Elimina permanentemente.
    
- I revisori possono visualizzare in sospeso o cronologiche disposizioni ed esportare lista di come file CSV.
    
Si noti che la disposizione valutazioni richiedono una sottoscrizione a Office 365 Enterprise E5.
  
Un'analisi di eliminazione può includere contenuto cassette postali di Exchange, siti di SharePoint, OneDrive account e gruppi di Office 365. In attesa di una revisione eliminazione in tali percorsi il contenuto viene eliminato solo dopo che il revisore decide di eliminare definitivamente il contenuto.
  
![Pagina di eliminazione](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a>Impostazione di revisione della disposizione mediante la creazione di un'etichetta

Questo è il flusso di lavoro di base per la configurazione di un'analisi di eliminazione. Si noti che questo flusso Mostra un'etichetta viene pubblicato e quindi applicata manualmente da un utente. In alternativa, un'etichetta che genera un'analisi di eliminazione può essere applicato automaticamente al contenuto.
  
![Grafico che mostra il flusso del funzionamento di eliminazione](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Un'analisi di eliminazione è un'opzione quando si crea un'etichetta in Office 365. Si noti che questa opzione non è disponibile in un criterio di conservazione ma solo in un'etichetta con le impostazioni di conservazione.
  
Per ulteriori informazioni sulle etichette, vedere [Overview of etichette](labels.md).
  
![Impostazioni di conservazione per un'etichetta](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>Eliminazione del contenuto

Quando un revisore riceve una notifica tramite posta elettronica che il contenuto è pronto per la revisione, consente di passare alla pagina di **eliminazione** per la protezione &amp; centro conformità e selezionare uno o più elementi. Il revisore può quindi: 
  
- Applica un'etichetta diversa.
    
- Estendere il periodo di conservazione.
    
- Consente di eliminare definitivamente l'elemento.
    
Il revisore può utilizzare il collegamento per visualizzare il documento nella posizione originale, se il revisore disponga delle autorizzazioni per tale posizione. Durante un'analisi di eliminazione, il contenuto non viene spostata dalla posizione originale e che non venga eliminato fino a quando il revisore decida di farlo.
  
Si noti che le notifiche tramite posta elettronica vengono inviate automaticamente a revisori su base settimanale. Pertanto, quando è stata raggiunta la fine del periodo di conservazione, potrebbe richiedere fino a sette giorni ai revisori di ricevere la notifica di posta elettronica che il contenuto è in attesa di eliminazione.
  
Si noti inoltre che vengono controllate tutte le azioni di eliminazione. A tale scopo, è necessario attivare il controllo almeno un giorno prima della prima azione di eliminazione: per ulteriori informazioni, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md). 
  
![Opzioni di eliminazione per un documento](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a>Autorizzazioni per la disposizione

Per ottenere l'accesso alla pagina di **eliminazione** , i revisori devono essere membri del ruolo di **Gestione di eliminazione** e il ruolo **Registri di controllo View-Only** . È consigliabile la creazione di un nuovo gruppo di ruolo denominato revisori di eliminazione, aggiunta di questi due ruoli a tale gruppo di ruoli e quindi l'aggiunta di membri al gruppo di ruoli. 
  
Per ulteriori informazioni, vedere [fornire agli utenti di accedere a Office 365 Security &amp; centro conformità](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Quanto tempo fino a quando non viene eliminato definitivamente eliminato il contenuto

Contenuto in attesa di una revisione di eliminazione viene eliminato solo dopo che il revisore decide di eliminare definitivamente il contenuto. Quando il revisore sceglie questa opzione, il contenuto del sito di SharePoint o OneDrive account diventa idoneo per il processo di pulizia standard descritto in questa sezione: [funzionamento di un criterio di conservazione con contenuti in locale](retention-policies.md#how-a-retention-policy-works-with-content-in-place).
  
Ciò significa che:
  
- È contenuto in una raccolta documenti di spostamento per la prima fase Cestino **7 giorni** di eliminazione e quindi eliminati definitivamente **93 giorni** dopo che. Il Cestino non è indicizzato dalla ricerca e quindi il relativo contenuto non è disponibile a un'esenzione di eDiscovery. 
    
- Il contenuto in attesa la conservazione raccolta sarà definitivamente eliminato **7 giorni** di eliminazione. 
    
## <a name="view-pending-and-completed-dispositions"></a>Visualizzazione in sospeso e completate disposizioni

Nella pagina **eliminazione** della sicurezza &amp; centro conformità, è possibile visualizzare in sospeso e completate disposizioni: 
  
- **In sospeso** disposizioni sono raggiunta la fine del loro periodo di conservazione e richiedono un'analisi di eliminazione. Dopo aver verificato ogni elemento, se si desidera applicare un'etichetta diversa, estendere il periodo di conservazione o eliminarla in modo permanente. 
    
- **Completato** disposizioni approvati per l'eliminazione durante un'analisi di eliminazione e sono in corso l'eliminazione definitiva. Elementi con un'altra etichetta applicato o il periodo di conservazione estese come parte di un'analisi non viene visualizzato di seguito. 
    
### <a name="filter-the-disposition-views"></a>Filtrare le visualizzazioni di eliminazione

È possibile filtrare le visualizzazioni dall'intervallo di tempo o etichetta. Per in sospeso disposizioni, l'intervallo di tempo in base alla data di scadenza. Per cronologiche disposizioni, l'intervallo di tempo si basa sulla data di eliminazione.
  
![Opzioni di filtro nella pagina di eliminazione](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a>Esportare gli elementi di eliminazione

È inoltre possibile esportare gli elementi in una visualizzazione come file CSV che è possibile aprire in Excel.
  
![Eliminazione esportato dati in Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

