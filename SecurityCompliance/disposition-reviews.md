---
title: Panoramica delle recensioni sulla disposizione
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Quando si crea un'etichetta che conserva il contenuto di Office 365, è possibile scegliere di attivare una revisione della disposizione alla fine del periodo di conservazione.
ms.openlocfilehash: 5dac91368ff2aff6ca7e1a2c3591b50466b869ac
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455038"
---
# <a name="overview-of-disposition-reviews"></a>Panoramica delle recensioni sulla disposizione

Quando il contenuto raggiunge la fine del periodo di conservazione, è possibile che si desideri rivedere il contenuto per decidere se può essere eliminato in modo sicuro ("Disposed"). Ad esempio, potrebbe essere necessario:
  
- Sospendere l'eliminazione ("Disposition") del contenuto pertinente in caso di controversia legale o di controllo.
    
- Rimuovere il contenuto dall'elenco di disposizione per archiviarlo in un archivio, se il contenuto ha una ricerca o un valore cronologico.
    
- Assegnare un periodo di conservazione diverso al contenuto, se il criterio originale era una soluzione temporanea o provvisoria.
    
- Restituire il contenuto ai client o trasferirlo in un'altra organizzazione.
    
Quando si crea un'etichetta che conserva il contenuto di Office 365, è possibile scegliere di attivare una revisione della disposizione alla fine del periodo di conservazione. In una recensione di disposizione:
  
- Gli utenti che scelgono ricevono una notifica tramite posta elettronica che dispongono di contenuto da esaminare. Questi revisori possono essere singoli utenti, gruppi di distribuzione o di sicurezza o gruppi di Office 365. Si noti che le notifiche vengono inviate su base settimanale.
    
- I revisori passano alla pagina **disposizione** nel centro sicurezza &amp; e conformità per esaminare il contenuto. 
    
- Per ogni documento, il revisore può:
    
  - Applicare un'etichetta diversa.
    
  - Estendere il periodo di conservazione.
    
  - Eliminarlo definitivamente.
    
- I revisori possono visualizzare le disposizioni in sospeso o cronologiche ed esportare tale elenco come file. csv.
    
Si noti che le recensioni sulla disposizione richiedono un abbonamento a Office 365 Enterprise E5.
  
Una recensione di disposizione può includere il contenuto nelle cassette postali di Exchange, siti di SharePoint, account di OneDrive e gruppi di Office 365. Il contenuto in attesa di una revisione della disposizione in tali posizioni viene eliminato solo dopo che un revisore sceglie di eliminare definitivamente il contenuto.
  
![Pagina disposizione](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a>Configurazione della revisione della disposizione mediante la creazione di un'etichetta

Si tratta del flusso di lavoro di base per l'impostazione di una revisione di disposizione. Si noti che questo flusso Visualizza un'etichetta da pubblicare e quindi applicata manualmente da un utente. in alternativa, un'etichetta che attiva una revisione della disposizione può essere applicata automaticamente al contenuto.
  
![Grafico che mostra il flusso di come funziona la disposizione](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Una recensione di disposizione è un'opzione quando si crea un'etichetta in Office 365. Si noti che questa opzione non è disponibile in un criterio di conservazione ma solo in un'etichetta con le impostazioni di conservazione.
  
Per ulteriori informazioni sulle etichette, vedere [Panoramica delle etichette](labels.md).
  
![Impostazioni di conservazione per un'etichetta](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>Eliminazione del contenuto

Quando un revisore riceve una notifica tramite posta elettronica che il contenuto è pronto per la revisione, può accedere alla pagina **disposizione** nel &amp; centro conformità sicurezza e selezionare uno o più elementi. Il revisore può quindi: 
  
- Applicare un'etichetta diversa.
    
- Estendere il periodo di conservazione.
    
- Elimina definitivamente l'elemento.
    
Un revisore può utilizzare il collegamento per visualizzare il documento nel percorso originale, se il revisore dispone delle autorizzazioni per tale percorso. Durante una revisione della disposizione, il contenuto non si sposta mai dal percorso originale e non viene mai eliminato fino a quando il revisore non lo sceglie.
  
Si noti che le notifiche di posta elettronica vengono inviate automaticamente ai revisori su base settimanale. Pertanto, quando il contenuto raggiunge la fine del periodo di conservazione, potrebbero essere necessari fino a sette giorni affinché i revisori ricevano la notifica di posta elettronica che il contenuto è in attesa di disposizione.
  
Si noti inoltre che tutte le azioni di disposizione vengono controllate. Per garantire questo, è necessario abilitare il controllo almeno un giorno prima della prima azione di disposizione-per ulteriori informazioni, vedere [Search the audit log in the Office 365 &amp; Security Compliance Center](search-the-audit-log-in-security-and-compliance.md). 
  
![Opzioni di disposizione per un documento](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a>Autorizzazioni per la disposizione

Per accedere alla pagina **disposizione** , i revisori devono essere membri del ruolo **gestione disposizione** e del ruolo di **controllo di sola visualizzazione** . È consigliabile creare un nuovo gruppo di ruoli denominato reviewers Disposition, aggiungendo questi due ruoli a quel gruppo di ruoli e quindi aggiungendo membri al gruppo di ruoli. 
  
Per ulteriori informazioni, vedere [fornire agli utenti l'accesso al centro sicurezza &amp; e conformità di Office 365](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Durata dell'eliminazione definitiva del contenuto eliminato

Il contenuto in attesa di una revisione della disposizione viene eliminato solo dopo che un revisore sceglie di eliminare definitivamente il contenuto. Quando il revisore sceglie questa opzione, il contenuto del sito di SharePoint o dell'account OneDrive diventa idoneo per il processo di pulizia standard descritto in questa sezione: [modalità di funzionamento dei criteri di conservazione con il contenuto sul posto](retention-policies.md#how-a-retention-policy-works-with-content-in-place).
  
Questo significa che:
  
- Il contenuto di una raccolta documenti verrà spostato nel cestino del primo passaggio **entro 7 giorni** dalla disposizione e quindi definitivamente eliminato **93 giorni** . Il cestino non è indicizzato dalla ricerca e pertanto il relativo contenuto non è disponibile per un blocco di eDiscovery. 
    
- Il contenuto della raccolta di conservazione rimarrà definitivamente eliminato **entro 7 giorni** dalla disposizione. 
    
## <a name="view-pending-and-completed-dispositions"></a>Visualizza disposizioni in sospeso e completate

Nella pagina **disposizione** del Centro sicurezza &amp; e conformità, è possibile visualizzare le disposizioni in sospeso e completate: 
  
- Le disposizioni **in sospeso** hanno raggiunto la fine del periodo di conservazione e richiedono una revisione della disposizione. Dopo aver esaminato ogni elemento, decidere se si desidera applicare un'etichetta diversa, estenderne il periodo di conservazione o eliminarla definitivamente. 
    
- Le disposizioni **complete** sono state approvate per l'eliminazione durante una revisione della disposizione e sono ora in fase di eliminazione definitiva. Gli elementi a cui è stata applicata un'etichetta diversa o il periodo di conservazione esteso nell'ambito di una revisione non verranno visualizzati in questa posizione. 
    
### <a name="filter-the-disposition-views"></a>Filtrare le visualizzazioni di disposizione

È possibile filtrare queste visualizzazioni in base all'etichetta o all'intervallo di tempo. Per le disposizioni in sospeso, l'intervallo di tempo si basa sulla data di scadenza. Per le disposizioni storiche, l'intervallo di tempo è basato sulla data di eliminazione.
  
![Opzioni di filtro nella pagina disposizione](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a>Esportare gli elementi di disposizione

È inoltre possibile esportare gli elementi in una visualizzazione come un file. csv che è possibile aprire in Excel.
  
![Dati di disposizione esPortati in Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

