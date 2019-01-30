---
title: Gestisci archiviazioni di eDiscovery avanzate (Preview)
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
description: ''
ms.openlocfilehash: 75ddbcfb401d285dfb7a4b610e3f0709e21946f2
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607914"
---
# <a name="rename-this-page-and-md-file-to-managing-holds"></a>Rinominare questa pagina e File MD "Gestione dell'archiviazione"

# <a name="holds-in-advanced-ediscovery-preview"></a>Esenzioni di eDiscovery avanzate (Preview)
È possibile utilizzare un caso eDiscovery avanzate (Preview) per creare esenzioni per conservare il contenuto che potrebbe essere rilevante al caso. Utilizzo di eDiscovery avanzate (Preview) tenere funzionalità, è possibile effettuare esenzioni depositari e le relative origini dati. Inoltre, è possibile inserire un'esenzione non detentive nelle cassette postali e OneDrive per i siti. Si può inoltre effettuare un'esenzione cassetta postale di gruppo, siti di SharePoint e OneDrive per sito Business per un gruppo di Office 365. Analogamente, è possibile inserire un'esenzione nella cassetta postale e sito in cui sono associati a Microsoft Teams. Quando si effettua i percorsi di contenuti in attesa, il contenuto viene mantenuto finché non si rilascia il depositaria, rimuovere un percorso di dati specifici o eliminare completamente il criterio di conservazione.

## <a name="manage-custodian-based-holds"></a>Gestire depositaria basato su esenzioni

In alcuni casi, potrebbe essere un insieme di depositari dati che sono stati identificati e scelto devono essere mantenuti. In eDiscovery avanzate (anteprima), quando questi depositari vengono inseriti nel thold, l'utente e i dati selezionati origini vengono aggiunte automaticamente a un depositaria attesa criteri. 

Per visualizzare il criterio di conservazione depositaria:

1. In **sicurezza & centro conformità**, fare clic su **eDiscovery gt _ avanzate eDiscovery (Preview)** per visualizzare l'elenco dei casi nell'organizzazione.
   
2. Passare alla scheda **depositari** aggiungere depositari all'interno del case. Per informazioni su come è possibile aggiungere e depositari posto in attesa all'interno di un caso eDiscovery avanzate (anteprima), visitare la sezione relativa **Gestione depositari all'interno di un caso** . Se si dispone già aggiunti depositari e li messa in attesa, spostare il passaggio 3.
   
3. Passare alla scheda **contiene** e selezionare il criterio di depositaria' '.
   
4. Nel riquadro a comparsa di ulteriori informazioni, è possibile visualizzare le statistiche per il criterio di conservazione. È inoltre possibile eseguire azioni come applicare una query per l'archiviazione depositaria. Per ulteriori informazioni sulla creazione di una query di attesa e l'utilizzo di condizioni, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions )
 
## <a name="manage-non-custodial-holds"></a>Gestisci archiviazioni Non detentive
Quando si crea un'esenzione, sono disponibili le opzioni seguenti per definire l'ambito del contenuto viene mantenuto nei percorsi di contenuto specificati:
  - Creare un'attesa infinita in tutto il contenuto viene messa in attesa. In alternativa, è possibile creare un'esenzione basata su query dove solo il contenuto che corrisponde a una query di ricerca viene messa in attesa.
  - È possibile specificare un intervallo di date per includere solo il contenuto che è stato inviato, ricevuto o creato all'interno di tale intervallo di date. In alternativa, è possibile tenere tutto il contenuto indipendentemente dal fatto se è stato inviato, ricevuto o creato.

Per creare un'esenzione per un caso eDiscovery:
  1. In **sicurezza & centro conformità**, fare clic su **eDiscovery gt _ avanzate eDiscovery (Preview)** per visualizzare l'elenco dei casi nell'organizzazione.
  
  2. Accanto al caso in cui si desidera creare l'archiviazione in, fare clic su Apri.
  
  3. Nella scheda**Home** per il case, fare clic sulla scheda **contiene** .
  
  4. Nella scheda **archiviazione** fare clic su **Crea**.
  
  5. Sul nome della pagina di attesa, assegnare un nome dell'esenzione. Il nome dell'esenzione deve essere univoco all'interno dell'organizzazione.
 
  6. (Facoltativo) Nella casella Descrizione aggiungere una descrizione dell'esenzione.
  
  7. Fare clic su **Avanti**.
  
  8. Scegliere i percorsi di contenuti che si desidera mettere in attesa. È possibile effettuare le cassette postali, i siti e le cartelle pubbliche in attesa. r. **posta elettronica di Exchange** , fare clic su **Scegli utenti, gruppi o team** e fare clic su **Scegli utenti, gruppi o team** nuovamente. Per specificare le cassette postali per mettere in attesa. Utilizzare la casella di ricerca per trovare cassette postali degli utenti e gruppi di distribuzione (per effettuare un'esenzione per le cassette postali dei membri del gruppo) per mettere in attesa. Può inoltre effettuare un'esenzione nella cassetta postale associata per un Team di Microsoft o un gruppo di Office 365. Selezionare la casella di controllo team utente, gruppo, fare clic su **Scegli**e quindi fare clic su **Fine**.
 
    [!NOTE]
    Quando si fa clic su **Scegli utenti, gruppi o team** per specificare le cassette postali per mettere in attesa, la selezione delle cassette postali che viene visualizzata sia vuota. Questo è per impostazione predefinita per migliorare le prestazioni. Per aggiungere persone all'elenco, digitare un nome (almeno 3 caratteri) nella casella di ricerca.


    **Siti di SharePoint** - b. fare clic su **Scegli siti** e quindi **Scegliere siti** nuovamente per specificare SharePoint e OneDrive per i siti per mettere in attesa. Digitare l'URL per ogni sito che si desidera mettere in attesa. È inoltre possibile aggiungere l'URL del sito di SharePoint per un Team di Microsoft o un gruppo di Office 365. Fare clic su **Scegli**e quindi fare clic su **Fine**.
    
     Vedere la sezione **domande frequenti** per suggerimenti per inserire i gruppi di Office 365 e Microsoft Teams in attesa.

    [!NOTE]
    Nel caso in cui è stato modificato nome entità utente dell'utente (UPN), l'URL per il proprio account OneDrive verrà modificata anche per incorporare l'UPN di nuovo. In questo caso, sarà necessario modificare la conservazione nuovo OneDrive URL dell'utente di aggiungendo e rimuovendo il vecchio.

     **cartelle pubbliche di Exchange** - c. spostare l'opzione Mostra/Nascondi nella posizione tutti per inserire tutte le cartelle pubbliche nei Exchange Online organizzazione su conservazione. Si noti che non è possibile scegliere specifiche cartelle pubbliche per mettere in attesa. Lasciare l'opzione Mostra/Nascondi impostata su **Nessuno** se non si desidera creare un'esenzione per le cartelle pubbliche.

  9. Al termine i percorsi di contenuti aggiunta all'esenzione, fare clic su **Avanti**.
  
  10. Per creare un'esenzione basata su query con condizioni, eseguire le operazioni seguenti. In caso contrario, fare clic su **Avanti**. 1.1 nella casella parole chiave, tipo di una query di ricerca nella casella in modo che solo il contenuto che soddisfa i criteri di ricerca viene messa in attesa. È possibile specificare le parole chiave, le proprietà del messaggio o proprietà del documento, ad esempio i nomi di file. È inoltre possibile utilizzare query più complesse che utilizzano un operatore booleano, ad esempio AND, OR o non. Se si lascia la casella di parola chiave vuota, tutto il contenuto disponibile nei percorsi specificati contenuti verrà messa in attesa.

    1.2 fare clic su **Aggiungi** condizioni per aggiungere una o più condizioni per limitare la query di ricerca per l'attesa. Ogni condizione aggiunge una clausola di query di ricerca KQL che viene creata ed eseguita quando si crea l'attesa. Ad esempio è possibile specificare un intervallo di date in modo che i documenti di posta elettronica o di un sito che sono stati creati all'interno della data intervallo vengono inseriti in attesa. Una condizione è connesso logicamente per le query con parole chiave (specificata nella casella parole chiave) per l'operatore AND. Ciò significa che gli elementi devono soddisfare entrambe le query con parole chiave e la condizione di essere posizionate in attesa.

     Per ulteriori informazioni sulla creazione di una query di ricerca e utilizzo delle condizioni, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions).

  11. Dopo aver configurato un basata su query attesa, fare clic su **Avanti**.
 
  12. Controllare le impostazioni e quindi fare clic su **Crea esenzione**.


## <a name="view-hold-statistics"></a>Visualizzare le statistiche di attesa
In un secondo momento, informazioni sulla nuova esenzione viene visualizzate nel riquadro dei dettagli della scheda **contiene** dell'esenzione selezionata. Queste informazioni includono il numero di cassette postali e siti in attesa e le statistiche relative al contenuto che è stato messo in attesa, ad esempio il numero totale e le dimensioni degli elementi messa in attesa e l'ultima ora in attesa sono state calcolate le statistiche. Queste attesa consentono di statistiche identificare la quantità di contenuto correlato al caso di eDiscovery è correntemente.

Tenere presenti sulle statistiche di attesa i seguenti aspetti:

  - Il numero totale di elementi in attesa indica il numero di elementi da tutte le origini di contenuto che restano in attesa. Se sono state create una basata su query attesa, questo indica il numero di elementi che corrispondono alla query.
  - Il numero di elementi in attesa include anche gli elementi non indicizzati presenti nei percorsi contenuti. Si noti che se si crea una conservazione basata su query, tutti gli elementi non indicizzati nelle posizioni del contenuto sono messi in attesa. Sono inclusi gli elementi non indicizzati che non soddisfano i criteri di ricerca di un'esenzione basata su query e non indicizzate che potrebbe essere si trovano all'esterno di una condizione di intervallo di date. Questa è diversa da cosa succede quando si esegue una ricerca di contenuto, in cui gli elementi non indicizzati che non corrispondono alla query di ricerca o esclusi da una condizione di intervallo di date non vengono inclusi nei risultati della ricerca. Per ulteriori informazioni sugli elementi non indicizzate, vedere [elementi indicizzati parzialmente in ricerca contenuto in Office 365] (https://docs.microsoft.com/en-us/office365/SecurityCompliance/partially-indexed-items-in-content-search). 
  - È possibile ottenere le statistiche di conservazione più recente facendo clic su aggiornamento delle statistiche per rieseguire una stima di ricerca che calcola il numero corrente di elementi in attesa.
  - Se necessario, fare clic su Aggiorna sulla barra degli strumenti per aggiornare le statistiche di conservazione nel riquadro dei dettagli.
  - La normale per il numero di elementi in attesa per aumentare il tempo perché agli utenti la cui cassetta postale o del sito sono in attesa sono in genere l'invio o ricezione nuovo messaggio di posta elettronica e la creazione di nuovi SharePoint e OneDrive per i documenti aziendali.

[!NOTE]
Se un sito di SharePoint o un account OneDrive viene spostato in una regione diversa in un ambiente multi-geo, le statistiche per il sito non inclusi nelle statistiche di attesa. Tuttavia, il contenuto del sito saranno ancora in attesa. Inoltre, se un sito viene spostato in una regione diversa l'URL che viene visualizzato nell'esenzione non verrà aggiornato. È necessario modificare la conservazione e aggiornare l'URL.

## <a name="faq"></a>Domande frequenti
- **Come mappare un sito di Office 365 gruppi o Microsoft Teams aggiuntivo a un depositaria? E per quanto riguarda effettuare un non detentive conservazione in gruppi di Office 365 e Microsoft Teams?** Microsoft Teams si basano sui gruppi di Office 365. Pertanto, in cui vengono posizionati in attesa di un caso eDiscovery è molto simile. Tenere presenti i seguenti aspetti quando posizionamento gruppi di Office 365 e Microsoft Teams in attesa.
  - Per mettere il contenuto disponibile in Office 365 gruppi e Microsoft Teams in attesa, è necessario specificare la cassetta postale e del sito che associate a un gruppo o un team di SharePoint.
  
  - Eseguire il cmdlet **Get-UnifiedGroup** in Exchange Online per visualizzare le proprietà per un Team di Microsoft o un gruppo di Office 365. Si tratta di un modo efficace per ottenere l'URL per il sito di cui è associato un Team di Microsoft o un gruppo di Office 365. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Office 365 denominato Team leader Senior:

' ' powershell

    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    '''

 [!NOTE]
 Per eseguire il cmdlet Get-UnifiedGroup, è necessario essere assegnato il ruolo di amministratore destinatari di Exchange Online o essere un membro del gruppo di ruoli che è assegnato il ruolo destinatari di sola visualizzazione.

 - Quando viene eseguita la ricerca cassetta postale dell'utente, qualsiasi gruppo di Office 365 o Team Microsoft che l'utente è membro di non eseguire la ricerca. Analogamente, quando si effettua un gruppo di Office 365 o al Team di Microsoft di attesa, solo la cassetta postale di gruppo e i siti gruppo vengono inseriti nel attesa; le cassette postali e OneDrive per i siti dei membri del gruppo non sono messa in attesa, a meno che non è in modo esplicito aggiungerle come depositari o effettuare attesa le origini dati. Pertanto, se è la necessità di inserire un gruppo di Office 365 o un Team di Microsoft in attesa per un depositaria specifico, si consiglia di mapping del gruppo sito e delle cassette postali di gruppo per depositaria (vedere Gestione depositari di eDiscovery avanzate (Preview)). Se il gruppo di Office 365 o un Team di Microsoft sia attribuito a un singolo depositaria, è possibile aggiungere l'origine di un non detentive attesa. 
 
 - Per ottenere un elenco dei membri di un gruppo di Office 365 o un Team di Microsoft, è possibile visualizzare le proprietà della pagina iniziale gt _ gruppi nell'interfaccia di amministrazione di Office 365. In alternativa, è possibile eseguire il seguente comando in Exchange Online PowerShell:

    ' ' powershell
    
        Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
        '''

[!NOTE]
Per eseguire il cmdlet Get-UnifiedGroupLinks, è necessario essere assegnato il ruolo di amministratore destinatari di Exchange Online o essere un membro del gruppo di ruoli che è assegnato il ruolo destinatari di sola visualizzazione.

- Conversazioni del canale che fanno parte di un canale Teams Microsoft sono archiviate nella cassetta postale associata al Team. Analogamente, i file che i membri del team di condividere un canale vengono archiviati nel sito di SharePoint del team. Di conseguenza, è necessario inserire la cassetta postale del Team di Microsoft e siti di SharePoint in attesa per mantenere le conversazioni e i file in un canale.
  
- In alternativa, le conversazioni che fanno parte dell'elenco di Chat di Microsoft Teams sono archiviate nella cassetta postale dell'utente che partecipano alla chat.  I file che un utente condivide conversazioni Chat vengono archiviati in OneDrive per sito aziendale dell'utente che condivide il file. Di conseguenza, è necessario inserire le cassette postali degli utenti singoli e OneDrive per i siti di Business in attesa per mantenere le conversazioni e i file nell'elenco Chat. 
  
- Ogni canale Team di Microsoft o un team contiene un Wiki per la collaborazione e gestione delle note. Il contenuto Wiki viene automaticamente salvato in un file in formato con estensione mht. In questo file è archiviato nella raccolta documenti di team Wiki dati nel sito di SharePoint del team. È possibile inserire il contenuto nel Wiki in attesa inserendo il sito di SharePoint del team in attesa.

[!Note]
La possibilità di conservare contenuto Wiki per un Team di Microsoft o un team di canale (quando si effettua il sito di SharePoint del team in sospeso) è stata rilasciata il 22 giugno 2017. Se un sito del team è in attesa, Wiki contenuto verrà mantenuto partire da tale data. Tuttavia, se un sito del team è in attesa e il contenuto Wiki è stato eliminato prima del 22 giugno 2017, il contenuto Wiki non è stato mantenuto.
   