---
title: Utilizzo della condivisione controllo nel Registro di controllo di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: "La condivisione è un'attività chiave in SharePoint Online e OneDrive for Business. Gli amministratori ora possono utilizzare Condivisione controllo nel Registro di controllo di Office 365 per determinare la modalità di condivisione utilizzata all'interno dell'organizzazione. "
ms.openlocfilehash: 511f8b0e61d450659d78177d5b87fac9ee636cd4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530910"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>Utilizzo della condivisione controllo nel Registro di controllo di Office 365

La condivisione è un'attività chiave in SharePoint Online e OneDrive for Business e viene ampiamente utilizzata nelle organizzazioni di Office 365. Gli amministratori ora possono utilizzare Condivisione controllo nel Registro di controllo di Office 365 per determinare la modalità di condivisione utilizzata all'interno dell'organizzazione. 
  
## <a name="the-sharepoint-sharing-schema"></a>Lo schema di condivisione di SharePoint

Condivisione (escluso condivisione dei criteri e collegare gli eventi) sono diversi da eventi relativi a file e cartelle in un modo principale: un utente richiede un'azione che ha alcune effetto su un altro utente. Ad esempio, l'utente consente l'accesso utente B in un file. In questo esempio, l'utente è *che agiscono utente* e utente B è l' *utente di destinazione*. Nello schema di File di SharePoint, azione dell'utente operativo interessa solo il file stesso. Quando l'utente apre un file, l'unica informazione necessaria nell'evento **FileAccessed** è l'utente operativo. Per risolvere questo differenza, c'è uno schema separato, denominato *SharePoint condivisione dello schema*, per l'acquisizione di ulteriori informazioni sulla condivisione degli eventi. In questo modo che gli amministratori dispongono di un'analisi più approfondita in cui una risorsa condivisa e l'utente la risorsa deve essere stato condiviso con. 
  
Lo schema di condivisione sono disponibili due campi aggiuntivi nel Registro di controllo relative alla condivisione degli eventi: 
  
- **TargetUserOrGroupName** - archivia l'UPN o il nome dell'utente di destinazione o del gruppo che una risorsa è stato condiviso con (utente B nell'esempio precedente). 
    
- **TargetUserOrGroupType** - indica se l'utente di destinazione o il gruppo è un membro, Guest, gruppo o Partner. 
    
Questi due campi, oltre alle altre proprietà di Office 365 schema del Registro di controllo come utente, l'operazione e data poter distinguere brano completo su *quali* condivisi *quali* risorsa utente con *cui* e *quando*. 
  
Non esiste un'altra proprietà dello schema che è importante brano della condivisione. La proprietà **EventData** archivia informazioni aggiuntive sulla condivisione degli eventi. Ad esempio, quando un utente condivide un sito con un altro utente, questa operazione viene eseguita aggiungendo l'utente di destinazione a un gruppo di SharePoint. La proprietà **EventData** acquisisce queste informazioni aggiuntive per fornire un contesto per gli amministratori. 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>Il modello di condivisione e gli eventi di SharePoint

La condivisione viene effettivamente definita da tre eventi distinti: **SharingSet**, **SharingInvitationCreated**e **SharingInvitaitonAccepted**. Ecco il flusso di lavoro per gli eventi come condivisione vengono registrati nel Registro di controllo di Office 365. 
  
![Diagramma di flusso del funzionamento di condivisione controllo](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
Quando un utente (user operativo) può condividere una risorsa con un altro utente (l'utente di destinazione), SharePoint (o OneDrive for Business) innanzitutto verifica se l'indirizzo di posta elettronica dell'utente di destinazione è già associato a un account utente nell'elenco dell'organizzazione. Se l'utente di destinazione nella directory dell'organizzazione, SharePoint esegue le operazioni seguenti:
  
-  Immediatamente consente di assegnare le autorizzazioni utente di destinazione per accedere alla risorsa. 
    
- Invia una notifica di condivisione per l'indirizzo di posta elettronica dell'utente di destinazione.
    
- Registra un evento **SharingSet** . 
    
 Se non è un account utente per l'utente di destinazione nell'elenco dell'organizzazione, SharePoint esegue le operazioni seguenti: 
  
- Crea un invito alla condivisione e invia per l'indirizzo di posta elettronica dell'utente di destinazione.
    
- Registra un evento **SharingInvitationCreated** . 
    
    > [!NOTE]
    > L'evento **SharingInvitationCreated** è sempre più associato esterno o guest condivisione quando l'utente di destinazione non dispone dell'accesso alle risorse che deve essere stato condiviso. 
  
Quando l'utente di destinazione accetta l'invito alla condivisione che ha inviato a tali (facendo clic sul collegamento nell'invito), SharePoint registra un evento **SharingInvitationAccepted** e consente di assegnare le autorizzazioni utente di destinazione per accedere alla risorsa. Viene registrate anche informazioni aggiuntive relative all'utente di destinazione, ad esempio l'identità dell'utente che è stato inviato l'invito e l'utente che ha effettivamente accettato l'invito. In alcuni casi, questi utenti (o gli indirizzi di posta elettronica) potrebbero essere diversi. 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a>Come identificare le risorse condivise con utenti esterni

Un requisito comune per gli amministratori sta creando un elenco di tutte le risorse condivise con gli utenti all'esterno dell'organizzazione. Utilizzando la condivisione controllo in Office 365, gli amministratori possono ora generare questo elenco. Ecco come.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Passaggio 1: Ricerca per la condivisione di eventi ed esportare i risultati in un file CSV

Il primo passaggio consiste nel cercare nel Registro di controllo di Office 365 per gli eventi di condivisione. Per ulteriori informazioni (tra cui le autorizzazioni necessarie) sulla ricerca nel Registro di controllo, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini**e quindi fare clic su **ricerca dei registri di controllo**.
    
    Verrà visualizzata la pagina di **ricerca dei registri di controllo** . 
    
4. In **attività**, fare clic su **attività di condivisione** per la ricerca solo per gli eventi di condivisione. 
    
    ![Tra le attività, selezionare le attività di condivisione](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Selezionare un intervallo di data e ora per individuare gli eventi di condivisione che si sono verificati durante questo periodo. 
    
6. Fare clic su **ricerca** per eseguire la ricerca. 
    
7. Al termine della ricerca in esecuzione e i risultati vengono visualizzati, fare clic su **Esporta risultati** \> **scaricare tutti i risultati**.
    
    Dopo aver selezionato l'opzione di esportazione, viene visualizzato un messaggio nella parte inferiore della finestra in cui viene chiesto se aprire o salvare il file CSV.
    
8. Fare clic su **Salva** \> **Salva** e salvare il file CSV in una cartella nel computer locale. 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>Passaggio 2: Filtrare il file CSV per le risorse condivise con utenti esterni

Il passaggio successivo è per filtrare il file CSV per gli eventi **SharingSet** e **SharingInvitationCreated** e visualizzare gli eventi in cui la proprietà **TargetUserOrGroupType** è **Guest**. Si utilizzerà la funzionalità Power Query in Excel per eseguire questa operazione. La procedura seguente viene eseguita in Excel 2016. 
  
1. In Excel 2016, aprire una cartella di lavoro vuota.
    
2. Fare clic sulla scheda **Dati**. 
    
3. Fare clic su **Nuova Query** \> **dal file** \> **Da CSV**.
    
    ![Nella scheda dati selezionare Nuova Query, selezionare file e quindi selezionare da CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. Aprire il file CSV che è stato scaricato nel passaggio 1.
    
    Il file CSV viene aperto nell'Editor di Query. Si noti che esistono quattro colonne: **ora**, **utente**, **Azioni**e **tutti i dettagli**. Nella colonna **dei dettagli** è un campo a più proprietà. Il passaggio successivo consiste nel creare una nuova colonna per ogni proprietà della colonna di **tutti i dettagli** . 
    
5. Selezionare la colonna di **tutti i dettagli** e quindi nella scheda **Home** fare clic su **Colonna divisa** \> **Da delimitatore**.
    
    ![Nella scheda Home fare clic su colonna divisa e quindi fare clic su da delimitatore](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. Nella finestra della **Colonna divisa da delimitatore** , procedere come segue: 
    
      - In **Selezionare o immettere delimitatore**, selezionare **virgola**.
    
      - In **divisa**, selezionare **ogni occorrenza della delimitatore**.
    
7. Fare clic su **OK**.
    
    Nella colonna **dei dettagli** è suddivisa in più colonne. Ogni nuova colonna è denominato **Detail.1**, **Detail.2**, **Detail.3**e così via. Si noterà che includono il prefisso i valori in ciascuna cella nelle colonne **Detail.n** con il nome della proprietà. ad esempio **Operazione: SharingSet**, **Operazione: SharingInvitationAccepted**e **Operazione: SharingInvitationCreated**.
    
    ![La colonna dettagli viene suddiviso in più colonne, uno per ogni proprietà](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. Nella scheda **File** fare clic su **chiudere &amp; carico** per chiudere l'Editor di Query e aprire il file in una cartella di lavoro di Excel. 
    
    Il passaggio successivo consiste nel filtrare il file da visualizzare solo gli eventi **SharingSet** e **SharingInvitationCreated** . 
    
9. Passare alla scheda **Home** e quindi selezionare nella colonna **azione** . 
    
10. Nella **ordinamento &amp; filtro** elenco a discesa, deselezionare tutte le selezioni effettuate, quindi selezionare **SharingSet** e **SharingInvitationCreated**e fare clic su **OK**.
    
    Verranno visualizzate le righe per gli eventi **SharingSet** e **SharingInvitationCreated** . 
    
11. Passare alla colonna denominata **Detail.17** (o qualsiasi colonna contiene la proprietà **TargetUserOrGroupType** ) e selezionarlo. 
    
12. Nella **ordinamento &amp; filtro** elenco a discesa, deselezionare tutte le selezioni effettuate, quindi selezionare **TargetUserOrGroupType:Guest**e fare clic su **OK**.
    
    Ora Excel vengono visualizzate le righe per gli eventi **SharingInvitationCreated** e **SharingSet** e dove l'utente di destinazione è esterno all'organizzazione, perché gli utenti esterni vengono identificati dal valore **TargetUserOrGroupType:Guest**. 
    
Nella tabella seguente vengono illustrati tutti gli utenti dell'organizzazione che le risorse condivise con un utente guest all'interno di un intervallo di date specificato.
  
![Registro di controllo di condivisione degli eventi in Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
Anche se non è incluso nella tabella precedente, la colonna **Detail.10** (o qualsiasi colonna contiene la proprietà **ObjectId** ) identifica la risorsa che deve essere stato condiviso con l'utente di destinazione. ad esempio `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
  
> [!TIP]
> Se si desidera identificare quando un utente guest è stato assegnato le autorizzazioni per accedere a una risorsa (in contrapposizione a quelli solo le risorse quello in condivise con loro), ripetere i passaggi 10, 11 e 12 e filtrare i **SharingInvitationAccepted** e **SharingSet **eventi nel passaggio 10. 
