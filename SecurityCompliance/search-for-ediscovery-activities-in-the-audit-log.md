---
title: Ricerca di eDiscovery attività nel Registro di controllo di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Informazioni su come cercare il Registro di controllo di Office 365 per gli eventi registrati quando gli amministratori di conformità eseguono operazioni maiuscole ricerca contenuto ed eDiscovery in sicurezza &amp; centro conformità.
ms.openlocfilehash: a4cc3a6b5030a6412d739236e4c534f36948d57f
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038349"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>Ricerca di eDiscovery attività nel Registro di controllo di Office 365

Ricerca e attività correlate ai eDiscovery che vengono eseguite in Office 365 protezione del contenuto &amp; centro conformità o eseguendo il corrispondente di Windows PowerShell cmdlet registrati nel Registro di controllo di Office 365. Vengono registrati gli eventi quando gli amministratori o gli amministratori di conformità (o qualsiasi utente che rappresenta le autorizzazioni assegnate eDiscovery) eseguita la ricerca di contenuto seguenti e attività correlate alla eDiscovery in Office 365 Security &amp; centro conformità:
  
- Creazione e gestione dei casi eDiscovery
    
- Creazione, avvio e modifica di ricerche di contenuto
    
- Esecuzione di azioni di ricerca del contenuto, ad esempio l'anteprima, esportazione e l'eliminazione di una ricerca
    
- Configurazione delle autorizzazioni di filtro per la ricerca del contenuto
    
- Gestire il ruolo di amministratore di eDiscovery
    
> [!IMPORTANT]
> Le attività descritte in questo articolo sono solo il risultato delle operazioni di eDiscovery eseguite utilizzando la protezione &amp; centro conformità. attività di eDiscovery che sono state eseguite mediante lo strumento di eDiscovery In locale in Exchange Online o il centro eDiscovery in SharePoint Online non sono incluse. 
  
Per ulteriori informazioni sulla ricerca nel Registro di controllo di Office 365, le autorizzazioni che sono necessari ed esportazione dei risultati di ricerca, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Come cercare e visualizza le attività di eDiscovery

Attualmente, è necessario eseguire alcune operazioni specifiche per visualizzare le attività di eDiscovery nel Registro di controllo di Office 365. Ecco come.
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. Nel riquadro sinistro fare clic su **ricerca &amp; indagini**e quindi fare clic su **ricerca dei registri di controllo**.
    
4. Nell'elenco a discesa **delle attività** , **le attività di eDiscovery**, fare clic su una o più attività da cercare. In alternativa, è possibile scegliere **le attività di eDiscovery** per la ricerca per tutte le attività correlate eDiscovery. 
    
    > [!NOTE]
    > L'elenco a discesa attività include inoltre un gruppo di attività denominato **eDiscovery cmdlet attività** che verranno restituiti i record dal Registro di controllo cmdlet. 
  
5.  Selezionare un intervallo di data e ora per visualizzare gli eventi di eDiscovery che si sono verificati durante questo periodo. 
    
6. Nella casella **utenti** , selezionare uno o più utenti da visualizzare i risultati della ricerca. Lasciare vuoto questo per restituire le voci per tutti gli utenti. 
    
7. Fare clic su **ricerca** per eseguire la ricerca utilizzando i criteri di ricerca. 
    
8. Dopo che vengono visualizzati i risultati della ricerca, è possibile fare clic su **risultati filtrati** per filtrare oppure ordinare i record risultanti attività. Purtroppo, è possibile utilizzare filtri in modo esplicito escludere alcune attività. 
    
9. Per visualizzare informazioni dettagliate su un'attività, fare clic sul record attività nell'elenco dei risultati della ricerca. 
    
    Viene visualizzato un volo **Dettagli** pagina che contiene le proprietà dettagliate dal record di eventi. Per visualizzare ulteriori dettagli, fare clic su **ulteriori informazioni**. Per una descrizione di queste proprietà, vedere la sezione [proprietà dettagliate per attività di eDiscovery](#detailed-properties-for-ediscovery-activities) . 

  
## <a name="ediscovery-activities"></a>attività di eDiscovery

Nella tabella seguente vengono descritti i ricerca contenuto e attività correlate ai eDiscovery che vengono registrate quando un amministratore o utente esegue attività relative a eDiscovery utilizzando la protezione &amp; centro conformità oppure eseguendo il cmdlet corrispondente PowerShell remoto connesso alla protezione dell'organizzazione &amp; centro conformità. 
  
> [!NOTE]
> Le attività di eDiscovery descritte in questa sezione vengono fornite informazioni simili alle attività eDiscovery cmdlet descritti nella sezione successiva. È consigliabile utilizzare le attività di eDiscovery descritte in questa sezione verranno visualizzati nei risultati della ricerca audit log entro 30 minuti. 24 ore per eDiscovery necessario cmdlet attività venga visualizzato nei risultati della ricerca di log di controllo. 
  
|**Nome descrittivo**|**Operazione**|**Cmdlet corrispondente**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Membro è stato aggiunto in caso di eDiscovery  <br/> |CaseMemberAdded  <br/> |Aggiungere ComplianceCaseMember  <br/> |Un utente è stato aggiunto come membro di un caso eDiscovery. Come membro di un caso, un utente può eseguire diverse attività riguardanti il caso in base al fatto che sia stato assegnato le autorizzazioni necessarie.  <br/> |
|Ricerca di contenuto modificato  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |È stata modificata una ricerca di contenuto esistente. Aggiunta o rimozione di percorsi di contenuti o modifica di query di ricerca, possono includere le modifiche.  <br/> |
|Appartenenza degli amministratori modificate eDiscovery  <br/> |CaseAdminUpdated  <br/> |Aggiornamento eDiscoveryCaseAdmin  <br/> |L'elenco di eDiscovery agli amministratori dell'organizzazione è stato modificato. Questa attività viene registrata quando l'elenco di eDiscovery agli amministratori viene sostituito con un gruppo di nuovi utenti. Se un singolo utente viene aggiunto o rimosso, viene registrata l'operazione CaseAdminAdded.  <br/> |
|Caso di eDiscovery modificate  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |È stato modificato un caso eDiscovery. Modifiche includono la chiusura di un caso aperto o riaprire un caso chiuso.  <br/> |
|Appartenenza al caso eDiscovery modificate  <br/> |CaseMemberUpdated  <br/> |Aggiornamento ComplianceCaseMember  <br/> |L'elenco dei membri di un caso eDiscovery è stato modificato. Questa attività viene registrata quando tutti i membri sono stati sostituiti con un gruppo di nuovi utenti. Aggiunta o rimozione di un singolo membro, operazione CaseMemberAdded o CaseMemberRemoved viene registrato.  <br/> |
|Modificare il filtro delle autorizzazioni di ricerca  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |È stato modificato un filtro di autorizzazioni di ricerca.  <br/> |
|Query di ricerca modificate per la conservazione casi eDiscovery  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |È stata modificata una conservazione basata su query associata a un caso eDiscovery. Modifiche possibili includono la modifica della query o intervallo di date per una query basata su legale.  <br/> |
|Ricerca contenuto anteprima elemento scaricato  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Un utente scaricato un elemento nel proprio computer locale (facendo clic sul collegamento **Download elemento originale** ) quando l'anteprima dei risultati della ricerca.  <br/> |
|Ricerca contenuto anteprima elemento elencato  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Un utente fa clic su **Anteprima risultati di ricerca** per visualizzare l'anteprima pagina dei risultati ricerca contenente un massimo di 1000 elementi dai risultati di ricerca di contenuto.  <br/> |
|Ricerca contenuto anteprima elemento visualizzato  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Un manager eDiscovery visualizzare un elemento fare clic su Anteprima dei risultati di ricerca.  <br/> |
|Creazione di ricerca del contenuto  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |È stata creata una nuova ricerca del contenuto.  <br/> |
|Amministratore di eDiscovery creata  <br/> |CaseAdminAdded  <br/> |Aggiungere eDiscoveryCaseAdmin  <br/> |Un utente è stato aggiunto come un'amministratore di eDiscovery nell'organizzazione.  <br/> |
|Caso di eDiscovery creata  <br/> |CaseAdded  <br/> |Nuovo ComplianceCase  <br/> |È stato creato un caso eDiscovery. Quando viene creato un caso, è necessario assegnare un nome. Altre operazioni riguardanti il caso, ad esempio l'aggiunta di membri, la creazione di esenzioni e creazione ricerche del contenuto associate al risultato maiuscole in altri eventi registrati.  <br/> |
|Creato il filtro delle autorizzazioni di ricerca  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |È stato creato un filtro di autorizzazioni di ricerca.  <br/> |
|Query di ricerca creata per la conservazione casi eDiscovery  <br/> |HoldCreated  <br/> |Nuovo CaseHoldRule  <br/> |È stata creata un'esenzione basata su query associata a un caso eDiscovery.  <br/> |
|Ricerca di contenuto eliminato  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Una ricerca di contenuto esistente è stata eliminata.  <br/> |
|Amministratore di eDiscovery eliminati  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Un'amministratore di eDiscovery è stata eliminata dall'organizzazione.  <br/> |
|Caso di eDiscovery eliminati  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |È stato eliminato un caso eDiscovery. Si noti che qualsiasi attesa associato al caso deve essere rimosso prima che il caso può essere eliminato.  <br/> |
|Filtro di ricerca eliminati autorizzazioni  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |È stato eliminato un filtro di autorizzazioni di ricerca.  <br/> |
|Query di ricerca eliminati per la conservazione casi eDiscovery  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Una conservazione basata su query associata a un caso eDiscovery è stato eliminato. Rimozione di query dall'esenzione è spesso il risultato dell'eliminazione di un'esenzione. Quando un'esenzione o una query di conservazione vengono eliminate, vengono rilasciati i percorsi di contenuti che era in attesa.  <br/> |
|Esportazione scaricato di ricerca del contenuto  <br/> |SearchResultDownloaded  <br/> |N/D  <br/> |Un utente scaricati i risultati di ricerca di contenuto al proprio computer locale. Si noti che un'attività **avviato l'esportazione di ricerca del contenuto** deve essere avviata prima che i risultati della ricerca possono essere scaricati.<br/> |
|Visualizzati in anteprima i risultati di ricerca del contenuto  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Un utente di visualizzare in anteprima i risultati di ricerca di contenuto.  <br/> |
|Risultati di ricerca del contenuto  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Un utente eliminati i risultati di ricerca del contenuto mediante l'esecuzione di **ComplianceSearchAction New-eliminare** comando.  <br/> |
|Rimosso analisi della ricerca contenuto  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Preparare la ricerca contenuto azione (per preparare i risultati della ricerca eDiscovery avanzate di Office 365) è stato eliminato. Se l'azione durante la preparazione è meno di due settimane, i risultati della ricerca sono stati preparati per eDiscovery avanzate sono stati eliminati dall'area di archiviazione Microsoft Azure. Se l'azione durante la preparazione è stato superato 2 settimane, questo evento indica che è stato eliminato solo l'azione preparazione corrispondente.  <br/> |
|Esportazione rimossa di ricerca del contenuto  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Un'operazione di esportazione di ricerca del contenuto è stata eliminata. Se l'azione Esporta è inferiore a due settimane, sono stati eliminati i risultati della ricerca che sono stati caricati nell'area di archiviazione di Microsoft Azure. Se l'azione Esporta è stato superato 2 settimane, questo evento indica che è stato eliminato solo l'azione di esportazione corrispondente.  <br/> |
|Membri rimossi dal caso di eDiscovery  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Un utente è stato rimosso come membro di un caso eDiscovery.  <br/> |
|Rimuovere l'anteprima dei risultati di ricerca del contenuto  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Un'operazione di anteprima di ricerca del contenuto è stata eliminata.  <br/> |
|Eseguire l'azione Elimina rimosso su ricerca contenuto  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Un'azione di eliminazione di ricerca del contenuto è stata eliminata.  <br/> |
|Rimuovere i report di ricerca  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Una ricerca contenuta esportare report azione è stata eliminata.  <br/> |
|Introduzione analisi della ricerca contenuto  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |I risultati di ricerca del contenuto sono stati preparati per l'analisi di eDiscovery avanzate.  <br/> |
|Avvio ricerca contenuto  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |È stata avviata una ricerca di contenuto. Quando si crea o si modifica una ricerca del contenuto utilizzando la protezione &amp; GUI centro conformità, la ricerca viene avviata automaticamente. Se si crea o modifica di una ricerca utilizzando il **New-ComplianceSearch** o il cmdlet **Set-ComplianceSearch** , è necessario eseguire il cmdlet **Start-ComplianceSearch** per avviare la ricerca.<br/> |
|Esportazione introduttiva di ricerca del contenuto  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Un utente di esportata i risultati di ricerca di contenuto.  <br/> |
|Report di esportazione introduttiva  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Un utente esportato un report di ricerca del contenuto.  <br/> |
|Arrestato ricerca contenuto  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Un utente ha interrotto la ricerca del contenuto.  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>attività del cmdlet eDiscovery

Nella tabella seguente sono elencati i record del Registro di controllo di cmdlet che vengono registrati quando un amministratore o utente esegue attività relative a eDiscovery utilizzando la protezione &amp; centro conformità oppure eseguendo il cmdlet corrispondente in PowerShell remoto del connessi alla protezione dell'organizzazione &amp; centro conformità. Si noti che le informazioni dettagliate in record del Registro di controllo sono diverse per le attività di cmdlet elencate in questa tabella e le attività di eDiscovery descritte nella sezione precedente. 
  
Come descritto in precedenza, necessario 24 ore di eDiscovery cmdlet attività venga visualizzato nei risultati della ricerca di log di controllo.
  
> [!TIP]
> L'argomento della Guida corrispondente nel sito TechNet sono collegati i cmdlet nella colonna **operazione** nella tabella riportata di seguito. Vedere l'argomento della Guida per una descrizione dei parametri disponibili per ciascun cmdlet. Il parametro e il valore del parametro utilizzate con un cmdlet sono inclusi nella voce del Registro di controllo per ogni attività del cmdlet eDiscovery che ha eseguito l'accesso. 
  
|**Nome descrittivo**|**Operazione (cmdlet)**|**Descrizione**|
|:-----|:-----|:-----|
|Attesa creato in caso di eDiscovery  <br/> |[Nuovo CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |Per un caso eDiscovery è stata creata un'esenzione. Con o senza specificare un'origine di contenuto, è possibile creare un'esenzione. Se vengono specificate origini di contenuto, si verrà identificati nella voce del Registro di controllo.  <br/> |
|Attesa eliminata dal caso di eDiscovery  <br/> |[Remove-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |Un'esenzione associato a un caso eDiscovery è stata eliminata. Eliminazione di un'esenzione rilascia tutti i percorsi contenuti dall'esenzione. Eliminazione dell'esenzione anche comporta l'eliminazione di regole attesa maiuscole associate all'esenzione (vedere **Remove-CaseHoldRule** ).<br/> |
|Attesa modificata in caso di eDiscovery  <br/> |[Set-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |È stata modificata un'esenzione associato a una ricerca eDiscovery. Modifiche possibili includono aggiungendo o rimuovendo i percorsi di contenuti o la disattivazione (disattivazione) all'esenzione.  <br/> |
|Query di ricerca creata per la conservazione casi eDiscovery  <br/> |[Nuovo CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |È stata creata un'esenzione basata su query associata a un caso eDiscovery.  <br/> |
|Query di ricerca eliminati per la conservazione casi eDiscovery  <br/> |[Remove-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |Una conservazione basata su query associata a un caso eDiscovery è stato eliminato. Rimozione di query dall'esenzione è spesso il risultato dell'eliminazione di un'esenzione. Quando un'esenzione o una query di conservazione vengono eliminate, vengono rilasciati i percorsi di contenuti che era in attesa.  <br/> |
|Query di ricerca modificate per la conservazione casi eDiscovery  <br/> |[Set-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |È stata modificata una conservazione basata su query associata a un caso eDiscovery. Modifiche possibili includono la modifica della query o intervallo di date per una query basata su legale.  <br/> |
|Caso di eDiscovery creata  <br/> |[Nuovo ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |È stato creato un caso eDiscovery. Quando viene creato un caso, è necessario assegnare un nome. Altre operazioni riguardanti il caso, ad esempio l'aggiunta di membri, la creazione di esenzioni e creazione ricerche del contenuto associate al risultato maiuscole in altri eventi registrati.  <br/> |
|Caso di eDiscovery eliminati  <br/> |[Remove-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |È stato eliminato un caso eDiscovery. Si noti che qualsiasi attesa associato al caso deve essere rimosso prima che il caso può essere eliminato.  <br/> |
|Caso di eDiscovery modificate  <br/> |[Set-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |È stato modificato un caso eDiscovery. Modifiche includono la chiusura di un caso aperto o riaprire un caso chiuso.  <br/> |
|Membro è stato aggiunto in caso di eDiscovery  <br/> |[Aggiungere ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |Un utente è stato aggiunto come membro di un caso eDiscovery. Come membro di un caso, un utente può eseguire diverse attività riguardanti il caso in base al fatto che sia stato assegnato le autorizzazioni necessarie.  <br/> |
|Membri rimossi dal caso di eDiscovery  <br/> |[Remove-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |Un utente è stato rimosso come membro di un caso eDiscovery.  <br/> |
|Appartenenza al caso eDiscovery modificate  <br/> |[Aggiornamento ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |L'elenco dei membri di un caso eDiscovery è stato modificato. Questa attività viene registrata quando tutti i membri sono stati sostituiti con un gruppo di nuovi utenti. Se un singolo elemento viene aggiunto o rimosso, l'operazione **ComplianceCaseMember Aggiungi** o **Rimuovi ComplianceCaseMember** viene registrata.<br/> |
|Creazione di ricerca del contenuto  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |È stata creata una nuova ricerca del contenuto.  <br/> |
|Ricerca di contenuto eliminato  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |Una ricerca di contenuto esistente è stata eliminata.  <br/> |
|Ricerca di contenuto modificato  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |È stata modificata una ricerca di contenuto esistente. Le modifiche possono includere aggiungendo o rimuovendo i percorsi di contenuti che vengono eseguita la ricerca e la modifica di query di ricerca.  <br/> |
|Avvio ricerca contenuto  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |È stata avviata una ricerca di contenuto. Quando si crea o si modifica una ricerca del contenuto utilizzando la protezione &amp; GUI centro conformità, la ricerca viene avviata automaticamente. Se si crea o modifica di una ricerca utilizzando il **New-ComplianceSearch** o il cmdlet **Set-ComplianceSearch** , è necessario eseguire il cmdlet **Start-ComplianceSearch** per avviare la ricerca.<br/> |
|Arrestato ricerca contenuto  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |Una ricerca di contenuto che era in esecuzione è stata arrestata.  <br/> |
|Creazione di azioni di ricerca del contenuto  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |È stata creata un'operazione di ricerca del contenuto. Azioni di ricerca del contenuto includono l'anteprima dei risultati della ricerca, esportazione dei risultati della ricerca, preparazione dei risultati della ricerca per l'analisi di Office 365 avanzate eDiscovery e in modo permanente l'eliminazione di elementi che soddisfano i criteri di ricerca di una ricerca di contenuto.  <br/> |
|Azione di ricerca di contenuto eliminato  <br/> |[Remove-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |Un'operazione di ricerca del contenuto è stata eliminata.  <br/> |
|Creato il filtro delle autorizzazioni di ricerca  <br/> |[New-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |È stato creato un filtro di autorizzazioni di ricerca.  <br/> |
|Filtro di ricerca eliminati autorizzazioni  <br/> |[Remove-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |È stato eliminato un filtro di autorizzazioni di ricerca.  <br/> |
|Modificare il filtro delle autorizzazioni di ricerca  <br/> |[Set-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |È stato modificato un filtro di autorizzazioni di ricerca.  <br/> |
|Amministratore di eDiscovery creata  <br/> |[Aggiungere eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |Un utente è stato aggiunto come un'amministratore di eDiscovery nell'organizzazione.  <br/> |
|Amministratore di eDiscovery eliminati  <br/> |[Remove-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |Un'amministratore di eDiscovery è stata eliminata dall'organizzazione.  <br/> |
|Appartenenza degli amministratori modificate eDiscovery  <br/> |[Aggiornamento eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |L'elenco di eDiscovery agli amministratori dell'organizzazione è stato modificato. Questa attività viene registrata quando l'elenco di eDiscovery agli amministratori viene sostituito con un gruppo di nuovi utenti. Se un singolo utente viene aggiunto o rimosso, l'operazione **eDiscoveryCaseAdmin Aggiungi** o **Rimuovi eDiscoveryCaseAdmin** viene registrata.<br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Proprietà dettagliate per attività di eDiscovery

Nella tabella seguente vengono descritte le proprietà che vengono incluse quando si fa clic su **ulteriori informazioni** sulla pagina dei **Dettagli** per un'attività di eDiscovery elencata nei risultati della ricerca. Queste proprietà sono inclusi nel file CSV anche quando si esportano i risultati di ricerca del log di controllo. Si noti che un record del Registro di controllo per un'attività di eDiscovery non includere tutte le informazioni dettagliate sulla proprietà elencate di seguito. 
  
> [!TIP]
> Quando si esportano i risultati della ricerca, il file CSV contiene una colonna denominata con **tutti i dettagli**, che contiene le proprietà dettagliate descritte nella tabella seguente in una proprietà multivalore. È possibile utilizzare la funzionalità Power Query in Excel divisa questa colonna più colonne in modo che ogni proprietà è relativa colonna. Ciò consente di ordinare e filtrare su uno o più di queste proprietà. Per ulteriori informazioni, vedere la sezione "Esportare i risultati della ricerca in un file" della funzionalità di [ricerca il controllo di accesso nel centro conformità protezione di Office 365 ](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Proprietà**|**Descrizione**|
|:-----|:-----|
|Caso  <br/> |L'identità (GUID) di eDiscovery caso in cui è stato creato, modifica o eliminazione.  <br/> |
|ClientApplication  <br/> |attività del cmdlet eDiscovery hanno un valore di **EMC** per questa proprietà. Indica l'attività è stata eseguita utilizzando la protezione &amp; GUI centro conformità o l'esecuzione del cmdlet di PowerShell.<br/> |
|ClientIP  <br/> |L'indirizzo IP del dispositivo utilizzato quando ha effettuato l'accesso all'attività. L'indirizzo IP viene visualizzato in formato di indirizzo di un indirizzo IPv4 o IPv6.  <br/> |
|ClientRequestId  <br/> | Per le attività di eDiscovery, questa proprietà è in genere vuota.  <br/> |
|CmdletVersion  <br/> |Il numero di build per la versione di sicurezza &amp; centro conformità in esecuzione nell'organizzazione.  <br/> |
|CreationTime  <br/> |Data e ora in ora UTC (Coordinated) quando è stata completata l'attività eDiscovery.  <br/> |
|EffectiveOrganization  <br/> |Il nome della propria organizzazione Office 365.  <br/> |
|ExchangeLocations  <br/> |Le cassette postali di Exchange Online che vengono incluse in una ricerca di contenuto o messa in attesa di un caso eDiscovery.  <br/> |
|Esclusioni  <br/> |Percorsi delle cassette postali o un sito che sono esclusi da una ricerca di contenuto o un'esenzione in un caso eDiscovery.  <br/> |
|ExtendedProperties  <br/> |Proprietà aggiuntive da un contenuto di ricerca, un'azione di ricerca del contenuto o legale in un caso di eDiscovery, ad esempio il GUID dell'oggetto e la corrispondente cmdlet e parametri cmdlet utilizzati quando è stata eseguita l'attività.  <br/> |
|Id  <br/> |ID della voce del report. L'ID identifica in modo univoco la voce del Registro di controllo.  <br/> |
|NonPIIParameters  <br/> |Un elenco dei parametri utilizzati con il cmdlet identificato nella proprietà Operation (senza alcun valore). I parametri elencati in questa proprietà sono uguali a quelle elencate nella proprietà Parameters.  <br/> |
|ObjectId  <br/> |Il GUID o il nome dell'oggetto (ad esempio una ricerca di contenuto o un caso eDiscovery) che è stato creato, modificato o eliminato dall'attività elencate nella proprietà Operation. Questo oggetto viene inoltre identificato nella colonna elemento nei risultati della ricerca di log di controllo.  <br/> |
|ObjectType  <br/> |Il tipo di oggetto di eDiscovery l'utente creato, eliminato o modificato. ad esempio un'operazione di ricerca del contenuto (anteprima, esportazione o eliminazione), un caso eDiscovery o una ricerca di contenuto.  <br/> |
|Operazione  <br/> |Nome dell'operazione che corrisponde all'attività eDiscovery eseguita.  <br/> |
|OrganizationId  <br/> |Il GUID per l'organizzazione Office 365.  <br/> |
|Parametri  <br/> |Il nome e il valore per i parametri utilizzati con il cmdlet corrispondente.  <br/> |
|PublicFolderLocations  <br/> |I percorsi di cartelle pubbliche in Exchange Online che vengono incluse in una ricerca di contenuto o messa in attesa di un caso eDiscovery.  <br/> |
|Query  <br/> |Query di ricerca associata all'attività, ad esempio una ricerca di contenuto o una conservazione basata su query.  <br/> |
|RecordType (ADO)  <br/> |Il tipo di operazione indicato dall'oggetto record. Il valore di **18** indica un evento relativo a un'attività elencata nella sezione [attività del cmdlet eDiscovery](#ediscovery-cmdlet-activities) . Il valore di **24** indica un evento relativo a un'attività elencata nella sezione [come cercare e visualizza le attività di eDiscovery](#how-to-search-for-and-view-ediscovery-activities) .<br/> |
|ResultStatus  <br/> |Indica se l'azione (specificato nella proprietà Operation) è stata eseguita o non.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica che l'attività è un titolo &amp; evento centro conformità. Tutte le attività di eDiscovery dispone di un valore pari a **0** per questa proprietà.<br/> |
|SharepointLocations  <br/> |I siti di SharePoint Online inclusi in una ricerca di contenuto o messa in attesa di un caso eDiscovery.  <br/> |
|StartTime  <br/> |Data e ora in ora UTC (Coordinated) quando è stata avviata l'attività di eDiscovery.  <br/> |
|ID utente  <br/> |Utente che ha eseguito l'attività (specificato nella proprietà Operation) che hanno generato il record registrato. Si noti che i record per l'attività di eDiscovery eseguite per gli account di sistema (ad esempio, il sistema operativo NT) sono inoltre inclusi nel Registro di controllo.  <br/> |
|UserKey specificato  <br/> |Un ID alternativo per l'utente identificato nella proprietà UserId. Per le attività di eDiscovery, il valore di questa proprietà è in genere equivale alla proprietà UserId.  <br/> |
|UserServicePlan  <br/> |La sottoscrizione a Office 365 utilizzata dall'organizzazione. Per le attività di eDiscovery, questa proprietà è in genere vuota.  <br/> |
|UserType  <br/> |Il tipo di utente che ha eseguito l'operazione. I valori seguenti indicano il tipo di utente.  <br/> Utente di normale A 0. 2 un amministratore dell'organizzazione Office 365. 3 un datacenter datacenter o amministratore di sistema account Microsoft. 4 un account di sistema. 5 un'applicazione. 6 un'entità di servizio. |
|Version  <br/> |Indica il numero di versione dell'attività (identificata dalla proprietà Operation) che ha eseguito l'accesso.  <br/> |
|Carico di lavoro  <br/> |Il servizio Office 365 in cui si è verificato l'attività. Per le attività di eDiscovery, il valore è **SecurityComplianceCenter**.<br/> |
