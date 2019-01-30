---
title: Gestione di un evento imprevisto perdita di dati in Microsoft 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritto come nuovo dati indagini (Preview) in strumento di sicurezza di Office 365 & centro conformità per gestire un evento imprevisto perdita di dati.
ms.openlocfilehash: d863d87cc667b9695f9bf619c35575715dfa144e
ms.sourcegitcommit: 98ec28932ae20e848f9f489c3c78e4a7edab6d18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "29636626"
---
# <a name="managing-a-data-spillage-incident-in-microsoft-365"></a>Gestione di un evento imprevisto perdita di dati in Microsoft 365 

Perdita di dati è rilascio di un documento riservato in un ambiente non attendibile. Quando viene rilevato un problema di perdita di dati, è importante valutare rapidamente le dimensioni e le posizioni della perdita, esaminare le attività dell'utente attorno ad esso e quindi eliminare definitivamente i dati espanso dal sistema.

## <a name="scope-of-this-article"></a>Ambito di questo articolo

In questo articolo fornisce un elenco di istruzioni su come rimuovere definitivamente gli elementi dalle cassette postali di Office 365 in modo che non sono più accessibile o recuperabili dagli utenti o gli amministratori. 

> [!NOTE]
> Quando si eliminano gli elementi disponibili in un SharePoint o OneDrive per sito aziendale, vengono mantenuti per 93 giorni dal momento in cui che sono state eliminate dalla posizione originale.

## <a name="scenario"></a>Scenario

L'utente viene informato di un evento imprevisto perdita di dati in un dipendente condivisa involontariamente un documento altamente riservati con più persone tramite posta elettronica. Si desidera valutare rapidamente che ha ricevuto questo documento sia interni che esterni all'organizzazione. Dopo che è stato provare a utilizzare l'evento imprevisto, si intende condividere le proprie scoperte con altri ricercatori per esaminare e quindi rimuovere in modo permanente i dati espanso da Office 365. Dopo aver completata le indagini, si desidera rimuovere tutte le prove. 

## <a name="workflow"></a>Flusso di lavoro

Ecco il flusso di lavoro per l'utilizzo di dati indagini (Preview) per gestire un evento imprevisto perdita di dati:

1.  Creare un'analisi dei dati.

2.  Cercare i dati espanso.

3.  Esaminare e provare a utilizzare l'evento imprevisto.

4.  Consente di eliminare definitivamente i dati espanso.

5.  Chiudere o eliminare le indagini.


## <a name="before-you-begin"></a>Informazioni preliminari

- Si verrà utilizzare lo strumento dati indagini (Preview) in & la protezione di Office 365 centro conformità per creare un'analisi, cercare i dati espanso, esaminare e analizzarli. Utilizzerà quindi sicurezza & PowerShell centro conformità per eliminare definitivamente i dati espanso da Office 365. 

- Per creare un'analisi, è necessario essere membri del gruppo di ruoli amministratore di conformità in & la sicurezza centro conformità.

- Per eliminare i messaggi, è necessario essere membri del gruppo di ruoli Gestione organizzazione in & la sicurezza centro conformità o essere assegnato il ruolo di ricerca ed eliminazione. Per informazioni sull'aggiunta di utenti a un gruppo di ruoli, vedere [fornire l'accesso degli utenti per la protezione & centro conformità](../grant-access-to-the-security-and-compliance-center.md). 

- Per controllare quali cassette postali degli utenti e account OneDrive un si possono eseguire ricerche, l'organizzazione è possibile impostare una separazione di conformità. Per ulteriori informazioni, [impostare i limiti di conformità per eDiscovery indagini](../set-up-compliance-boundaries.md). 

## <a name="step-1-create-a-data-investigation"></a>Passaggio 1: Creare un'analisi dati

Per creare un'analisi dei dati:

1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. In sicurezza & centro conformità, fare clic su **Dati indagini**.
 
4. Nella pagina **Dati indagini (anteprima)** , fare clic su **Crea una nuova analisi**.
    
5. Nella pagina **Nuovo indagini dati** comparsa assegnare un nome (obbligatorio) le indagini e quindi digitare un numero indagini facoltativo e una descrizione. Si noti che il nome deve essere univoco all'interno dell'organizzazione.

6. In **si desidera configurare impostazioni aggiuntive dopo la creazione di questo indagini?**, effettuare una delle operazioni seguenti:

    - Fare clic su **Sì** per creare le indagini e visualizzare la pagina **Impostazioni** nel caso di nuovo. In questo modo è possibile aggiungere membri per le indagini.
    
    - Fare clic su **No** per creare le indagini solo da visualizzare nell'elenco dei casi nella pagina **Dati indagini (Preview)** . Se si sceglie questa opzione, verrà aggiunto come unico membro delle indagini e le impostazioni di ricerca e analitica predefinita verrà utilizzato. È possibile aggiungere membri o cambiare le impostazioni in qualsiasi momento dopo aver creata le indagini.

7. Fare clic su **Salva** per creare le indagini.

    Le nuove indagini viene visualizzata nell'elenco nella pagina **Dati indagini (Preview)** . 

8. Per aprire un'analisi, fare clic sul nome delle indagini. 

    Viene visualizzata la scheda **Home** per le indagini. 

> [!TIP]
> È consigliabile definire una convenzione di denominazione per indagini e vengono fornite le informazioni presenti è il nome e descrizione così da poter individuare e consultare in futuro, se necessario.
 
## <a name="step-2-search-for-the-spilled-data"></a>Passaggio 2: Ricerca per i dati espanso 
 
Se si conoscono gli utenti che si desidera eseguire la ricerca per i dati espanso, è possibile aggiungere come utenti di interesse per eseguire il mapping alle origini dati per le indagini e cercare la cassetta postale e l'account OneDrive. Per aggiungere persone di interesse per le indagini, fare clic su **persone di interesse**e quindi fare clic su **Aggiungi utenti di interesse**. 

Nella scheda **ricerche** , è possibile creare le ricerche per individuare i dati espanso. Utilizzare la stessa query di ricerca utilizzato per individuare i dati espanso da eliminare questi stessi messaggi nel [passaggio 4](##step-4:-permanently-delete-the-spilled-data). Per ulteriori informazioni sulla creazione di ricerche, vedere [creare una ricerca per raccogliere i dati](create-search-to-collect-data.md).

Dopo aver eseguito la ricerca, è possibile visualizzare un'anteprima esempi di risultati di ricerca e visualizzare le statistiche di ricerca per valutare l'efficacia delle query di ricerca. Dopo aver identificato gli elementi che si desidera eliminare da Office 365, è possibile fare clic sulla scheda **risolte** e quindi creare un evento imprevisto e aggiungere i risultati di ricerca che contiene gli elementi. 

A tale scopo, fare clic su ricerca che si desidera analizzare. Nella pagina tendina fare clic su **Aggiungi risultati a incidente** e seguire le istruzioni visualizzate. Quindi incidente, è possibile controllare i singoli documenti, indagare che hanno accesso ai documenti ed esportare i documenti. Per eliminare semplicemente i documenti anziché li esaminano, andare al [passaggio 4](##step-4:-permanently-delete-the-spilled-data). 

> [!IMPORTANT]
> Le parole chiave utilizzati nella query di ricerca possono contenere i dati effettivi espanso che si sta cercando. Se, ad esempio, per la ricerca di documenti che contengono un numero di previdenza sociale e utilizzarlo come parola chiave nella query di ricerca, è necessario eliminare la query in un secondo momento per evitare ulteriori perdita. È possibile eliminare ricerca o l'intera indagini nel [passaggio 5](##step-5:-close-or-delete-investigation). 

## <a name="step-3-review-and-investigate"></a>Passaggio 3: Rivedere e analizzare 

In indagini, passare alla scheda **risolte** e fare clic su evento imprevisto creata nel passaggio precedente. Dopo aver completato il processo di elaborazione e vengono aggiunti i risultati della ricerca per l'evento imprevisto, è possibile esaminare i singoli documenti in formato nativo, formato di testo o un formato nativo più vicina. È possibile creare query aggiuntive per limitare ulteriormente l'elenco di documenti e contrassegnare i documenti per indicare le conclusioni l'analisi.

Per raggruppare i documenti e ottenere ulteriore assistenza per la revisione, fare clic su **Gestisci incidente**. Nella porzione **Analitica** , fare clic su **Analyze**. Verrà eseguito analitica avanzate, ad esempio il rilevamento duplicati, posta elettronica threading e analisi di tema. Per ulteriori informazioni, vedere:

- [Quasi duplicati](near-duplicates.md)
- [Messaggio di posta elettronica threading](email-threading.md)
- [Temi](themes.md)

Per determinare gli utenti che partecipano alla perdita dei dati, è possibile creare una nuova query in incidente e quindi utilizzare il mittente/autore e le condizioni di destinatari. Si creerà un elenco di tutti i mittenti attendibili, destinatari e autori di dati raccolti che è stato aggiunto per l'evento imprevisto. Assicurarsi di esaminare l'elenco per determinare se vi sono utenti esterni nell'elenco. Per ulteriori informazioni, vedere [criteri di ricerca](../keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-permanently-delete-the-spilled-data"></a>Passaggio 4: Eliminare definitivamente i dati espanso

### <a name="deleting-mailbox-items"></a>Eliminazione di elementi delle cassette postali

Dopo la revisione e convalida i risultati della ricerca contenenti solo i messaggi di posta elettronica che devono essere eliminati, è possibile eliminare definitivamente li eseguendo il **ComplianceSearchAction New-eliminare - PurgeType HardDelete** command in sicurezza & conformità Centro PowerShell. Per ulteriori informazioni, vedere [cercare ed eliminare i messaggi di posta elettronica](../search-for-and-delete-messages-in-your-organization.md). 

Si noti che se il ripristino di singoli elementi è abilitato per le cassette postali nell'organizzazione, degli elementi eliminati in modo permanente saranno conservati nella cartella elementi ripristinabili dell'utente (e accessibile dagli amministratori) fino a quando non le estremità periodo di mantenimento elementi eliminati (valore predefinito è 14 giorni). Inoltre, se una delle cassette postali che contengono dati espanso un giudiziari o assegnati a un criterio di conservazione, messaggi eliminati verranno mantenuto nella cartella elementi ripristinabili fino alla rimozione o la cassetta postale è escluso da criteri di conservazione. Per i messaggi di eliminazione permanente immediatamente, è necessario eseguire attività di aggiunta. Per ulteriori informazioni, vedere [eliminazione di elementi nella cartella delle cassette postali basate su cloud in attesa agli elementi ripristinabili ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).  

> [!IMPORTANT]
> Verificare con la gestione dei record o reparti legali prima di rimuovere un criterio di conservazione o conservazione. L'organizzazione può disporre di un criterio che definisce se una cassetta postale in attesa o un problema di perdita dei dati ha la priorità. 

### <a name="deleting-site-items"></a>Eliminazione di elementi di siti

Per eliminare definitivamente un documento da un sito di SharePoint o OneDrive per conto di Business, è necessario eliminare e quindi è necessario eliminare dal sito e quindi eliminarla dal Cestino della raccolta siti. Per ulteriori informazioni, vedere [eliminazione documenti in SharePoint e OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).

In alternativa, è possibile eliminare un'intera raccolta siti che potrebbero contenuti dati espanso. Per ulteriori informazioni, vedere [eliminare una raccolta siti](https://docs.microsoft.com/sharepoint/delete-site-collection).

## <a name="step-5-close-or-delete-the-investigation"></a>Passaggio 5: Chiudere o eliminare le indagini

Dopo l'eliminazione di documenti nei percorsi di contenuto di origine (siti o cassette postali), sarà comunque necessario copie di tali documenti aggiunte al risolte nell'ambito della ricerca. Per evitare ulteriormente perdita di dati, è consigliabile eliminare le indagini.

Per eliminare un'analisi:

1. Nella scheda **Impostazioni** , fare clic su **informazioni di indagini**.
2. Fare clic su **Elimina case**. 

Se non è necessario eliminare le indagini o se si desidera salvare le informazioni raccolte durante le indagini, è possibile fare clic su **chiudere un caso**. In un secondo momento, è possibile aprire nuovamente indagini chiuse.