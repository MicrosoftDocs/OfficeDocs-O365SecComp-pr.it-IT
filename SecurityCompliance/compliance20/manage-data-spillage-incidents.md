---
title: Gestire un problema di fuoriuscita dei dati in Microsoft 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritto come utilizzare lo strumento nuovo data Investigation (Preview) nel centro conformità di Office 365 Security & per gestire un problema di fuoriuscita dei dati.
ms.openlocfilehash: d130983bc87ae5cbb962f9271d8b4b505db0e6f1
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295809"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>Gestire un problema di fuoriuscita dei dati in Microsoft 365 

La fuoriuscita dei dati avviene quando un documento riservato viene rilasciato in un ambiente non attendibile. Quando viene rilevato un problema di fuoriuscita dei dati, è importante valutare rapidamente le dimensioni e le posizioni del versamento, esaminare le attività degli utenti che lo circondano e quindi eliminare definitivamente i dati versati dal sistema.

## <a name="scope-of-this-article"></a>Ambito di questo articolo

In questo articolo viene fornito un elenco di istruzioni su come rimuovere definitivamente gli elementi dalle cassette postali di Office 365, in modo che non siano più accessibili o recuperabili dagli utenti o dagli amministratori. 

> [!NOTE]
> Quando si eliminano gli elementi che si trovano in un sito di SharePoint o OneDrive for business, vengono conservati per 93 giorni dal momento in cui vengono eliminati dal percorso originale.

## <a name="scenario"></a>Scenario

Si è informati di un problema di fuoriuscita dei dati in cui un dipendente ha condiviso inconsapevolmente un documento estremamente riservato con più persone tramite posta elettronica. Si desidera valutare rapidamente chi ha ricevuto il documento, sia all'interno che all'esterno dell'organizzazione. Dopo aver indagato sull'incidente, si prevede di condividere i risultati con altri ricercatori per esaminare e quindi rimuovere definitivamente i dati di cui è stato eseguito il versamento da Office 365. Al termine dell'analisi, si desidera rimuovere tutte le prove. 

## <a name="workflow"></a>Flusso di lavoro

Di seguito è indicato il flusso di lavoro per l'utilizzo delle indagini sui dati (Preview) per gestire un problema di fuoriuscita dei dati:

1.  Creare un'analisi dei dati.

2.  Cercare i dati rovesciati.

3.  Esaminare ed esaminare l'evento Incident.

4.  Elimina definitivamente i dati versati.

5.  Chiudere o eliminare l'indagine.


## <a name="before-you-begin"></a>Informazioni preliminari

- È possibile utilizzare lo strumento analisi dati (Preview) nel centro conformità di Office 365 Security & per creare un'indagine, cercare i dati rovesciati e analizzarla e esaminarla. Sarà quindi possibile utilizzare PowerShell per il centro conformità di sicurezza & per eliminare definitivamente i dati versati da Office 365. 

- Per creare un'indagine, è necessario essere membri del gruppo di ruoli amministratore conformità nel centro sicurezza & Compliance.

- Per eliminare i messaggi, è necessario essere membri del gruppo di ruoli Gestione organizzazione nel centro conformità & sicurezza o essere assegnati al ruolo di ricerca ed eliminazione. Per informazioni sull'aggiunta di utenti a un gruppo di ruoli, vedere [Give users access to the Security _AMP_ Compliance Center](../grant-access-to-the-security-and-compliance-center.md). 

- Per controllare le cassette postali degli utenti e gli account di OneDrive che un ricercatore può cercare, l'organizzazione può impostare i limiti di conformità. Per ulteriori informazioni, [impostare i limiti di conformità per le indagini di eDiscovery](../set-up-compliance-boundaries.md). 

## <a name="step-1-create-a-data-investigation"></a>Passaggio 1: creare un'analisi dei dati

Per creare un'analisi dei dati:

1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel centro sicurezza & Compliance fare clic su **indagini sui dati**.
 
4. Nella pagina **indagini dati (anteprima)** fare clic su **Crea una nuova indagine**.
    
5. Nella pagina nuovo riquadro a comparsa **dei dati** , assegnare un nome all'indagine (obbligatorio) e quindi digitare un numero di ricerca facoltativo e una descrizione. Si noti che il nome deve essere univoco nell'organizzazione.

6. In **se si desidera configurare altre impostazioni dopo aver creato l'indagine**, eseguire una delle operazioni seguenti:

    - Fare clic su **Sì** per creare l'analisi e visualizzare la pagina **Impostazioni** nel nuovo caso. In questo modo è possibile aggiungere membri all'indagine.
    
    - Fare clic su **No** per creare solo l'analisi e visualizzarla nell'elenco dei casi della pagina **indagini dati (anteprima)** . Se si sceglie questa opzione, verrà aggiunto come unico membro dell'indagine e verranno utilizzate le impostazioni di ricerca e analisi predefinite. È possibile aggiungere membri o modificare le impostazioni in qualsiasi momento dopo la creazione dell'indagine.

7. Fare clic su **Salva** per creare l'indagine.

    La nuova analisi viene visualizzata nell'elenco nella pagina **indagini dati (anteprima)** . 

8. Per aprire un'indagine, fare clic sul nome dell'indagine. 

    Viene visualizzata la scheda **Home** per l'indagine. 

> [!TIP]
> Valutare la possibilità di stabilire una convenzione di denominazione per le indagini e fornire quante più informazioni possibile nel nome e nella descrizione, in modo da poter individuare e fare riferimento in futuro, se necessario.
 
## <a name="step-2-search-for-the-spilled-data"></a>Passaggio 2: ricerca dei dati versati 
 
Se si conoscono gli utenti di cui si desidera eseguire la ricerca per i dati riversati, è possibile aggiungerli come persone di interesse per mappare le origini dati all'analisi e cercare rapidamente la propria cassetta postale e l'account OneDrive. Per aggiungere persone di interesse all'indagine, fare clic su **persone di interesse**, quindi fare clic su **Aggiungi persone di interesse**. 

Nella scheda **ricerche** è possibile creare ricerche per individuare i dati versati. Si utilizzerà la stessa query di ricerca utilizzata per individuare i dati rovesciati per eliminare gli stessi messaggi nel [passaggio 4](##step-4:-permanently-delete-the-spilled-data). Per ulteriori informazioni sulla creazione di ricerche, vedere [creare una ricerca per raccogliere i dati](create-search-to-collect-data.md).

Dopo aver eseguito la ricerca, è possibile visualizzare in anteprima esempi di risultati della ricerca e visualizzarne le statistiche per valutare l'efficacia della query di ricerca. Dopo aver identificato gli elementi che si desidera eliminare da Office 365, è possibile fare clic sulla scheda **eventi** non consentiti e quindi creare un evento imprevisto e aggiungere i risultati della ricerca che contengono tali elementi. 

A tale scopo, fare clic sulla ricerca che si desidera esaminare. Nella pagina riquadro a comparsa fare clic su **Aggiungi risultati in incidente** e seguire le istruzioni. Nell'incidente è quindi possibile esaminare singoli documenti, esaminare gli utenti che hanno accesso ai documenti ed esportare i documenti. Per eliminare semplicemente i documenti anziché esaminarli, passare al [passaggio 4](##step-4:-permanently-delete-the-spilled-data). 

> [!IMPORTANT]
> Le parole chiave utilizzate nella query di ricerca possono contenere i dati di cui è stata eseguita la ricerca. Ad esempio, se si cercano documenti contenenti un numero di previdenza sociale e lo si usa come parola chiave nella query di ricerca, è necessario eliminare la query in seguito per evitare ulteriori fuoriuscite. È possibile eliminare la ricerca o eliminare l'intera analisi nel [passaggio 5](##step-5:-close-or-delete-investigation). 

## <a name="step-3-review-and-investigate"></a>Passaggio 3: Revisione e analisi 

Nell'inchiesta, andare alla scheda **incidenti** e fare clic sull'incidente creato nel passaggio precedente. Una volta completato il processo di elaborazione e i risultati della ricerca vengono aggiunti all'evento Incident, è possibile esaminare singoli documenti nel formato nativo, nel formato di testo o in un formato quasi nativo. È possibile creare query aggiuntive per limitare ulteriormente l'elenco dei documenti e contrassegnare i documenti per indicare i risultati dell'indagine.

Per raggruppare i documenti e ottenere assistenza per la revisione, fare clic su **Gestisci evento**. Nel riquadro **analisi** fare clic su **analizza**. Verrà eseguito l'analisi avanzata, ad esempio il rilevamento duplicato, il threading di posta elettronica e l'analizzatore dei temi. Per ulteriori informazioni, vedere:

- [Rilevamento dei documenti simili](near-duplicates.md)
- [Threading posta elettronica](email-threading.md)
- [Temi](themes.md)

Per determinare gli utenti coinvolti nella fuoriuscita di dati, è possibile creare una nuova query nell'incidente e quindi utilizzare le condizioni mittente/autore e destinatari. In questo modo verrà creato un elenco di tutti i mittenti, i destinatari e gli autori trovati nei dati raccolti che sono stati aggiunti all'evento Incident. Assicurarsi di esaminare l'elenco per determinare se sono presenti utenti esterni nell'elenco. Per ulteriori informazioni, vedere [condizioni di ricerca](../keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-permanently-delete-the-spilled-data"></a>Passaggio 4: eliminare definitivamente i dati versati

### <a name="deleting-mailbox-items"></a>Eliminazione di elementi della cassetta postale

Dopo aver esaminato e convalidato che i risultati della ricerca contengono solo i messaggi di posta elettronica che devono essere eliminati, è possibile eliminarli definitivamente eseguendo il comando **New-ComplianceSearchAction-Purge-PurgeType HardDelete** in sicurezza & Compliance Centro PowerShell. Per istruzioni, vedere [cercare ed eliminare i messaggi di posta elettronica](../search-for-and-delete-messages-in-your-organization.md). 

Tenere presente che se il ripristino di un singolo elemento è abilitato per le cassette postali nell'organizzazione, gli elementi eliminati definitivamente verranno conservati nella cartella elementi ripristinabili dell'utente (e accessibili dagli amministratori) fino alla fine del periodo di conservazione degli elementi eliminati (il valore predefinito è 14 giorni). Inoltre, se una delle cassette postali che contengono dati versati si trova in una conservazione legale o assegnata a un criterio di archiviazione, il messaggio eliminato verrà mantenuto nella cartella elementi ripristinabili finché il blocco non viene rimosso o se la cassetta postale non viene esclusa dai criteri di conservazione. Per eliminare immediatamente i messaggi, è necessario eseguire le attività di addizione. Per istruzioni, vedere [eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).  

> [!IMPORTANT]
> Consultare la gestione dei record o i reparti giuridici prima di rimuovere un blocco o un criterio di conservazione. È possibile che l'organizzazione disponga di un criterio che definisce se una cassetta postale in attesa o un problema di fuoriuscita dei dati è prioritaria. 

### <a name="deleting-site-items"></a>Eliminazione di elementi del sito

Per eliminare definitivamente un documento da un sito di SharePoint o da un account OneDrive for business, è necessario eliminarlo e quindi eliminarlo dal sito e quindi eliminarlo dal cestino della raccolta siti. Per istruzioni, vedere [eliminare documenti in SharePoint e OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).

In alternativa, è possibile eliminare un'intera raccolta siti che potrebbe contenere dati rovesciati. Per istruzioni, vedere [eliminare una raccolta siti](https://docs.microsoft.com/sharepoint/delete-site-collection).

## <a name="step-5-close-or-delete-the-investigation"></a>Passaggio 5: chiudere o eliminare l'analisi

Dopo aver eliminato i documenti nelle posizioni di contenuto di origine (cassette postali o siti), sono ancora presenti copie di questi documenti che sono stati aggiunti agli eventi non consentiti nell'ambito dell'indagine. Per evitare un ulteriore versamento dei dati, è consigliabile eliminare l'indagine.

Per eliminare un'analisi:

1. Nella scheda **Impostazioni** fare clic su **informazioni di analisi**.

2. Fare clic su **Delete case**. 

Se non è necessario eliminare l'analisi o se si desidera salvare le informazioni raccolte durante l'indagine, è possibile fare clic su **Chiudi caso**. In un secondo momento, è possibile riaprire le indagini chiuse.