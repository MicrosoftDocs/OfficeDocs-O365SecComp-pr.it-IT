---
title: Controllare la condivisione per identificare risorse condivise con utenti esterni
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
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
ms.openlocfilehash: e2865d35e988d8c0e42a6c51f78507db8b170d4c
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "35435241"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>Controllare la condivisione per identificare risorse condivise con utenti esterni

La condivisione è un'attività chiave in SharePoint Online e OneDrive for business ed è ampiamente utilizzata nelle organizzazioni di Office 365. Gli amministratori possono ora utilizzare il controllo di condivisione nel log di controllo di Office 365 per determinare la modalità di utilizzo della condivisione nell'organizzazione. 
  
## <a name="the-sharepoint-sharing-schema"></a>Lo schema di condivisione di SharePoint

La condivisione di eventi (esclusi i criteri di condivisione e gli eventi di collegamento di condivisione) è diversa dagli eventi relativi a file e cartelle in un unico modo principale: un utente esegue un'azione che ha effetti su un altro utente. Ad esempio, l'utente A consente all'utente B di accedere a un file. In questo esempio, l'utente A rappresenta l'utente che *agisce* e l'utente B è l' *utente di destinazione*. Nello schema dei file di SharePoint, l'azione dell'utente che agisce ha effetto solo sul file stesso. Quando un utente apre un file, le uniche informazioni necessarie per l' **** evento fileaccessed sono gli utenti che agiscono. Per risolvere questa differenza, è disponibile uno schema distinto, denominato *schema di condivisione di SharePoint*, che acquisisce ulteriori informazioni sulla condivisione degli eventi. In questo modo gli amministratori avranno maggiori informazioni su chi ha condiviso una risorsa e l'utente con cui è stata condivisa la risorsa. 
  
Nello schema di condivisione sono disponibili due campi aggiuntivi nel log di controllo relativi agli eventi di condivisione: 
  
- **TargetUserOrGroupName** – archivia l'UPN o il nome dell'utente o del gruppo di destinazione a cui è stata condivisa una risorsa (utente B nell'esempio precedente). 
    
- **TargetUserOrGroupType** – identifica se l'utente o il gruppo di destinazione è un membro, un ospite, un gruppo o un partner. 
    
Questi due campi, oltre ad altre proprietà dallo schema del registro di controllo di Office 365, ad esempio l'utente, l'operazione e la data, possono ** raccontare la storia ** completa dell'utente che ha condiviso la risorsa con *chi* e *quando*. 
  
È presente un'altra proprietà dello schema che è importante per la storia della condivisione. La proprietà **EventData** archivia ulteriori informazioni sulla condivisione di eventi. Ad esempio, quando un utente condivide un sito con un altro utente, questo viene ottenuto aggiungendo l'utente di destinazione a un gruppo di SharePoint. La proprietà **EventData** acquisisce queste informazioni aggiuntive per fornire il contesto per gli amministratori. 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>Il modello di condivisione di SharePoint e gli eventi di condivisione

La condivisione è definita da tre eventi distinti: **SharingSet**, **SharingInvitationCreated**e **SharingInvitaitonAccepted**. Di seguito viene illustrato il flusso di lavoro per la modalità di registrazione degli eventi di condivisione nel registro di controllo di Office 365. 
  
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

Il primo passaggio consiste nell'eseguire una ricerca nel registro di controllo di Office 365 per la condivisione degli eventi. Per ulteriori informazioni (incluse le autorizzazioni necessarie) per la ricerca nel registro di controllo, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro del Centro sicurezza & conformità fare clic su ricerca ****  > **log di controllo**di ricerca.
    
    Viene visualizzata la pagina di **ricerca del registro di controllo** . 
    
4. In **attività**fare clic su **condivisione e accesso alle attività richieste** per cercare gli eventi relativi alla condivisione. 
    
    ![In attività selezionare condivisione e accesso alle attività richieste](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Selezionare un intervallo di data e ora per individuare gli eventi di condivisione che si sono verificati entro quel periodo. 
    
6. Fare clic su **Cerca** per eseguire la ricerca. 
    
7. Al termine dell'esecuzione della ricerca e i risultati vengono visualizzati, fare clic su **Esporta risultati** \> **scaricare tutti i risultati**.
    
    Dopo aver selezionato l'opzione di esportazione, viene visualizzato un messaggio nella parte inferiore della finestra in cui viene richiesto di aprire o salvare il file CSV.
    
8. Fare clic su **Salva** \> con **nome** e salvare il file CSV in una cartella del computer locale. 

### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>Passaggio 2: filtrare il file CSV per le risorse condivise con gli utenti esterni

Il passaggio successivo consiste nel filtrare il CSV per gli eventi **SharingSet** e **SharingInvitationCreated** e per visualizzare gli eventi in cui la proprietà **TargetUserOrGroupType** è **Guest**. Per eseguire questa operazione, è possibile utilizzare lo strumento Power query editor in Excel. Per istruzioni dettagliate, vedere [esportazione, configurazione e visualizzazione dei record del registro di controllo](export-view-audit-log-records.md). 

Dopo aver seguito le istruzioni riportate nell'argomento precedente per preparare il file CSV, eseguire le operazioni seguenti:
    
1. Aprire il file CSV preparato con l'editor di query di alimentazione. 

2. Nella scheda **Home** fare clic su **Ordina & filtro**, quindi fare clic su **filtro**.
    
3. Nell'elenco a discesa **ordina & filtro** nella colonna **operazioni** deselezionare tutte le selezioni, quindi selezionare **SharingSet** e **SharingInvitationCreated**e quindi fare clic su **OK**.
    
    Excel Visualizza le righe per gli eventi **SharingSet** e **SharingInvitationCreated** . 
    
4. Passare alla colonna denominata **TargetUserOrGroupType** e selezionarla. 
    
5. Nell'elenco a discesa **ordina & filtro** , deselezionare tutte le selezioni, quindi selezionare **TargetUserOrGroupType: Guest**e fare clic su **OK**.
    
    Ora Excel Visualizza le righe per gli eventi **SharingInvitationCreated** e **SharingSet** e in cui l'utente di destinazione si trova all'esterno dell'organizzazione, perché gli utenti esterni sono identificati dal valore **TargetUserOrGroupType: Guest**. 
    
Nella tabella seguente vengono illustrati tutti gli utenti dell'organizzazione che hanno condiviso le risorse con un utente Guest all'interno di un intervallo di date specificato.
  
![Condivisione di eventi nel registro di controllo di Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
Anche se non è incluso nella tabella precedente, la proprietà **ObjectID** identifica la risorsa condivisa con l'utente di destinazione. ad esempio `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
  
> [!TIP]
> Se si desidera identificare quando un utente ospite è stato effettivamente assegnato le autorizzazioni per l'accesso a una risorsa (anziché solo le risorse che condividono con essi), ripetere i passaggi 2, 3 e 4 e filtrare su **SharingInvitationAccepted** e **SharingSet** eventi nel passaggio 5. 
