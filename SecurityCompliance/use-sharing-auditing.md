---
title: Controllare la condivisione per identificare risorse condivise con utenti esterni
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: "La condivisione è un'attività chiave in SharePoint Online e OneDrive for business. Gli amministratori possono ora utilizzare il controllo di condivisione nel log di controllo di Office 365 per determinare la modalità di utilizzo della condivisione nell'organizzazione. "
ms.openlocfilehash: 08b511acdf74edac5b2d595d1b60bdd84d630918
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263404"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>Controllare la condivisione per identificare risorse condivise con utenti esterni

La condivisione è un'attività chiave in SharePoint Online e OneDrive for business ed è ampiamente utilizzata nelle organizzazioni di Office 365. Gli amministratori possono ora utilizzare il controllo di condivisione nel log di controllo di Office 365 per determinare la modalità di utilizzo della condivisione nell'organizzazione. 
  
## <a name="the-sharepoint-sharing-schema"></a>Lo schema di condivisione di SharePoint

La condivisione di eventi (esclusi i criteri di condivisione e gli eventi di collegamento di condivisione) è diversa dagli eventi relativi a file e cartelle in un unico modo principale: un utente esegue un'azione che ha effetti su un altro utente. Ad esempio, l'utente A consente all'utente B di accedere a un file. In questo esempio, l'utente A rappresenta l'utente che *agisce* e l'utente B è l' *utente di destinazione*. Nello schema dei file di SharePoint, l'azione dell'utente che agisce ha effetto solo sul file stesso. Quando un utente apre un file, le uniche informazioni necessarie per l' **** evento fileaccessed sono gli utenti che agiscono. Per risolvere questa differenza, è disponibile uno schema distinto, denominato *schema di condivisione di SharePoint*, che acquisisce ulteriori informazioni sulla condivisione degli eventi. In questo modo gli amministratori avranno maggiori informazioni su chi ha condiviso una risorsa e l'utente con cui è stata condivisa la risorsa. 
  
Nello schema di condivisione sono disponibili due campi aggiuntivi nel log di controllo relativi agli eventi di condivisione: 
  
- **TargetUserOrGroupName** -archivia l'UPN o il nome dell'utente o del gruppo di destinazione a cui è stata condivisa una risorsa (utente B nell'esempio precedente). 
    
- **TargetUserOrGroupType** -identifica se l'utente o il gruppo di destinazione è un membro, un ospite, un gruppo o un partner. 
    
Questi due campi, oltre ad altre proprietà dallo schema del registro di controllo di Office 365, ad esempio l'utente, l'operazione e la data, possono ** raccontare la storia ** completa dell'utente che ha condiviso la risorsa con *chi* e *quando*. 
  
È presente un'altra proprietà dello schema che è importante per la storia della condivisione. La proprietà **EventData** archivia ulteriori informazioni sulla condivisione di eventi. Ad esempio, quando un utente condivide un sito con un altro utente, questo viene ottenuto aggiungendo l'utente di destinazione a un gruppo di SharePoint. La proprietà **EventData** acquisisce queste informazioni aggiuntive per fornire il contesto per gli amministratori. 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>Il modello di condivisione di SharePoint e gli eventi di condivisione

La condivisione è in realtà definita da tre eventi distinti: **SharingSet**, **SharingInvitationCreated**e **SharingInvitaitonAccepted**. Di seguito viene illustrato il flusso di lavoro per la modalità di registrazione degli eventi di condivisione nel registro di controllo di Office 365. 
  
![Diagramma di flusso di come funziona la condivisione del controllo](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
Quando un utente (l'utente che agisce) desidera condividere una risorsa con un altro utente (l'utente di destinazione), SharePoint (o OneDrive for business) prima verifica se l'indirizzo di posta elettronica dell'utente di destinazione è già associato a un account utente nella directory dell'organizzazione. Se l'utente di destinazione si trova nella directory dell'organizzazione, SharePoint esegue le operazioni seguenti:
  
-  Assegna immediatamente le autorizzazioni utente di destinazione per l'accesso alla risorsa. 
    
- Invia una notifica di condivisione all'indirizzo di posta elettronica dell'utente di destinazione.
    
- Registra un evento **SharingSet** . 
    
 Se un account utente per l'utente di destinazione non si trova nella directory dell'organizzazione, SharePoint esegue le operazioni seguenti: 
  
- Crea un invito alla condivisione e lo invia all'indirizzo di posta elettronica dell'utente di destinazione.
    
- Registra un evento **SharingInvitationCreated** . 
    
    > [!NOTE]
    > L'evento **SharingInvitationCreated** è sempre associato alla condivisione esterna o Guest quando l'utente di destinazione non ha accesso alla risorsa condivisa. 
  
Quando l'utente di destinazione accetta l'invito di condivisione inviato a tali utenti (facendo clic sul collegamento nell'invito), SharePoint registra un evento **SharingInvitationAccepted** e assegna le autorizzazioni utente di destinazione per l'accesso alla risorsa. Vengono inoltre registrate informazioni aggiuntive sull'utente di destinazione, ad esempio l'identità dell'utente a cui è stato inviato l'invito e l'utente che ha effettivamente accettato l'invito. In alcuni casi, questi utenti (o indirizzi di posta elettronica) potrebbero essere diversi. 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a>Come identificare le risorse condivise con gli utenti esterni

Un requisito comune per gli amministratori consiste nella creazione di un elenco di tutte le risorse condivise con utenti esterni all'organizzazione. Utilizzando la condivisione del controllo in Office 365, gli amministratori possono ora generare questo elenco. Ecco come fare.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Passaggio 1: cercare gli eventi di condivisione ed esportare i risultati in un file CSV

Il primo passaggio consiste nell'eseguire una ricerca nel registro di controllo di Office 365 per la condivisione degli eventi. Per ulteriori informazioni (incluse le autorizzazioni necessarie) sulla ricerca nel registro di controllo, vedere [Search the audit log in the Security _AMP_ Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro del Centro sicurezza & Compliance fare clic su ricerca**log di controllo**di **ricerca**  > .
    
    Viene visualizzata la pagina di **ricerca del registro di controllo** . 
    
4. In **attività**fare clic su **Condivisione attività** per eseguire la ricerca solo per la condivisione di eventi. 
    
    ![In attività selezionare Condivisione attività](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Selezionare un intervallo di data e ora per individuare gli eventi di condivisione che si sono verificati entro quel periodo. 
    
6. Fare clic su **Cerca** per eseguire la ricerca. 
    
7. Al termine dell'esecuzione della ricerca e i risultati vengono visualizzati, fare clic su **Esporta risultati** \> **scaricare tutti i risultati**.
    
    Dopo aver selezionato l'opzione di esportazione, viene visualizzato un messaggio nella parte inferiore della finestra in cui viene richiesto di aprire o salvare il file CSV.
    
8. Fare clic su **Salva** \> con **nome** e salvare il file CSV in una cartella del computer locale. 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>Passaggio 2: filtrare il file CSV per le risorse condivise con gli utenti esterni

Il passaggio successivo consiste nel filtrare il CSV per gli eventi **SharingSet** e **SharingInvitationCreated** e per visualizzare gli eventi in cui la proprietà **TargetUserOrGroupType** è **Guest**. Per eseguire questa operazione, è possibile utilizzare la funzionalità Power query in Excel. In Excel 2016 viene eseguita la procedura seguente. 
  
1. In Excel 2016 aprire una cartella di lavoro vuota.
    
2. Fare clic sulla scheda **dati** . 
    
3. Fare clic su **nuova query** \> **da file** \> **da CSV**.
    
    ![Nella scheda dati selezionare nuova query, selezionare da file e quindi fare clic su da CSV.](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. Aprire il file CSV scaricato nel passaggio 1.
    
    Il file CSV viene aperto nell'editor di query. Si noti che sono presenti quattro colonne: **ora**, **utente**, **azione**e **dettaglio**. La colonna **dettaglio** è un campo con più proprietà. Il passaggio successivo consiste nel creare una nuova colonna per ognuna delle proprietà nella colonna **dettaglio** . 
    
5. Selezionare la colonna **dettaglio** e quindi nella scheda **Home** fare clic su **Suddividi colonna** \> **per**delimitatore.
    
    ![Nella scheda Home fare clic su Suddividi colonna e quindi su delimitatore](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. Nella finestra **Suddividi in base** al delimitatore eseguire le operazioni seguenti: 
    
      - In **Seleziona o immetti**delimitatore, **** seleziona virgola.
    
      - In **Split**selezionare **a ogni occorrenza del**delimitatore.
    
7. Fare clic su **OK**.
    
    La colonna **dettaglio** è suddivisa in più colonne. Ogni nuova colonna è denominata **dettaglio. 1**, **dettaglio. 2**, **dettaglio. 3**e così via. Si noterà che i valori di ogni cella nelle colonne **detail. n** sono preceduti dal nome della proprietà. ad esempio, **Operation: SharingSet**, **Operation: SharingInvitationAccepted**e **Operation: SharingInvitationCreated**.
    
    ![La colonna dettaglio è suddivisa in più colonne, una per ogni proprietà](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. Nella scheda **file** fare clic su **Chiudi &amp; caricamento** per chiudere l'editor di query e aprire il file in una cartella di lavoro di Excel. 
    
    Il passaggio successivo consiste nel filtrare il file in modo da visualizzare solo gli eventi **SharingSet** e **SharingInvitationCreated** . 
    
9. Passare alla scheda **Home** e quindi selezionare la colonna **azione** . 
    
10. Nell'elenco a discesa ** &amp; Ordina filtro** deselezionare tutte le selezioni, quindi selezionare **SharingSet** e **SharingInvitationCreated**e quindi fare clic su **OK**.
    
    Excel Visualizza le righe per gli eventi **SharingSet** e **SharingInvitationCreated** . 
    
11. Passare alla colonna denominata **detail. 17** (o qualsiasi colonna contenente la proprietà **TargetUserOrGroupType** ) e selezionarla. 
    
12. Nell'elenco a discesa **Ordina &amp; filtro** deselezionare tutte le selezioni, quindi selezionare **TargetUserOrGroupType: Guest**e quindi fare clic su **OK**.
    
    Ora Excel Visualizza le righe per gli eventi **SharingInvitationCreated** e **SharingSet** e in cui l'utente di destinazione si trova all'esterno dell'organizzazione, perché gli utenti esterni sono identificati dal valore **TargetUserOrGroupType: Guest**. 
    
Nella tabella seguente vengono illustrati tutti gli utenti dell'organizzazione che hanno condiviso le risorse con un utente Guest all'interno di un intervallo di date specificato.
  
![Condivisione di eventi nel registro di controllo di Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
Anche se non è incluso nella tabella precedente, la colonna **detail. 10** (o qualsiasi colonna contiene la proprietà **ObjectID** ) identifica la risorsa condivisa con l'utente di destinazione. ad esempio `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
  
> [!TIP]
> Se si desidera identificare quando un utente ospite è stato effettivamente assegnato le autorizzazioni per l'accesso a una risorsa (anziché solo le risorse che condividono con essi), ripetere i passaggi 10, 11 e 12 e filtrare su **SharingInvitationAccepted** e **SharingSet **eventi nel passaggio 10. 
