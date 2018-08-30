---
title: Eseguire la ricerca di cassette postali basate sul cloud per gli utenti locali in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Utilizzare lo strumento di ricerca del contenuto in Office 365 Security &amp; centro conformità per cercare ed esportare i dati di chat MicrosoftTeams (denominati 1xN chat) per gli utenti locali in una distribuzione ibrida di Exchange.
ms.openlocfilehash: a504dfcf4c82bec036137b90312c01a0b2326ccc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530609"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>Eseguire la ricerca di cassette postali basate sul cloud per gli utenti locali in Office 365

Se l'organizzazione dispone di una distribuzione ibrida di Exchange e è state attivate Teams Microsoft, gli utenti possono utilizzare l'applicazione di chat team per la messaggistica immediata. Per l'utente basata su cloud, vengono salvati i dati di chat team (denominati anche le chat 1xN) alle cassette postali basate su cloud principale. Quando un utente locale utilizza l'applicazione di chat di Team, cassetta postale principale è disponibile in locale. Per ovviare a questo limite, Microsoft ha rilasciato una nuova caratteristica in cui viene creata un'area di archiviazione basata sul cloud (noti come una cassetta postale basata sul cloud per gli utenti locali) per memorizzare i dati di chat team per gli utenti locali. È possibile utilizzare lo strumento di ricerca del contenuto in Office 365 Security &amp; centro conformità per cercare ed esportare dati di chat per gli utenti locali dei team. 
  
Di seguito sono indicati i requisiti e limitazione per la configurazione e di impostare e ricerca cassette postali basate sul cloud per gli utenti locali:
  
- È necessario sincronizzare gli account utente nel servizio directory locale (ad esempio Active Directory) con Azure Active Directory, il servizio di directory in Office 365. Ciò significa che un account utente di posta elettronica viene creato in Office 365 ed è associato a un utente la cui cassetta postale principale si trova nell'organizzazione locale.
    
- La cassetta postale basata sul cloud per gli utenti locali è utilizzato solo archivio dati della chat team. Un utente locale non può accedere alla cassetta postale basata sul cloud o accedere in alcun modo. Non può essere utilizzato per inviare o ricevere messaggi di posta elettronica. 
    
- È necessario inviare una richiesta di supporto Microsoft per consentire all'organizzazione di dati di ricerca per i team chat nelle cassette postali basate su cloud per gli utenti locali. Vedere [archiviazione una richiesta con il supporto Microsoft per attivare questa funzionalità per la protezione &amp; centro conformità](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center) in questo articolo. 
    
 **Nota:** Conversazioni del canale team vengono sempre memorizzate nella cassetta postale basata sul cloud associato al Team. Ciò significa che è possibile utilizzare ricerca contenuto a canale ricerca conversazioni senza devono una richiesta di supporto dei file. Per ulteriori informazioni sulla ricerca team channel conversazioni, vedere [Office 365 gruppi e team Microsoft che la ricerca](content-search.md#searching-microsoft-teams-and-office-365-groups).
  
## <a name="how-it-works"></a>Funzionamento

Se un utente abilitati per i team di Microsoft dispone di una cassetta postale locale e la propria identità o un account utente sono stati sincronizzati nel cloud, Microsoft consente di creare una cassetta postale basata sul cloud per l'archiviazione dei dati della chat 1xN team. Dopo che il team chat vengono memorizzati nella cassetta postale basata sul cloud, è indicizzato per la ricerca. Ciò consente di utilizzare la ricerca del contenuto (e ricerche associate ai casi di eDiscovery) per eseguire la ricerca, visualizzare in anteprima ed esportare dati della chat team per gli utenti locali. È inoltre possibile utilizzare ** \*ComplianceSearch** i cmdlet di Office 365 Security &amp; PowerShell centro conformità per la ricerca per i team di dati della chat per gli utenti locali. 
  
Nella figura seguente viene illustrato il flusso di lavoro di come team chat dati per gli utenti locali è disponibile per la ricerca, visualizzare in anteprima ed esportare.
  
![Archiviazione basata su cloud per gli utenti locali all'interno di Microsoft Teams](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
Oltre a questa nuova funzionalità, è possibile utilizzare ancora ricerca il contenuto di ricerca, visualizzare in anteprima ed esportare il contenuto nel sito di SharePoint basate su cloud e cassetta postale di Exchange associato a ogni Team di Microsoft e team 1xN dati della chat nella cassetta postale di Exchange Online per Team utenti basata su cloud.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center"></a>Archiviazione di una richiesta con il supporto Microsoft per attivare questa funzionalità per la protezione &amp; centro conformità

Una richiesta con il supporto Microsoft per consentire all'organizzazione di utilizzare l'interfaccia utente grafica nella protezione deve di &amp; centro conformità per la ricerca per i team di dati della chat nelle cassette postali basate su cloud per gli utenti locali. Si noti che questa funzionalità è disponibile in Office 365 Security &amp; PowerShell centro conformità. Non è necessario inviare una richiesta di supporto da utilizzare PowerShell per cercare i dati di chat team per gli utenti locali. 
  
Quando si invia la richiesta di supporto Microsoft, sono incluse le informazioni seguenti:
  
- Nome di dominio predefinito dell'organizzazione Office 365.
    
- Il nome del tenant e l'ID tenant dell'organizzazione Office 365. È possibile trovare queste nel portale di Azure Active Directory ( **Gestione** \> **proprietà**). Vedere [trovare l'ID tenant Office 365](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).
    
- Il titolo o la descrizione dello scopo della richiesta di supporto seguenti: "Abilita le applicazioni di ricerca del contenuto per gli utenti locali". Ciò consente di instradare la richiesta a Office 365 eDiscovery team di progettazione che verrà implementata la richiesta. 
    
Dopo aver effettuata le modifiche engineering, supporto Microsoft inviare una data di distribuzione stimate. Si noti che il processo di distribuzione richiede in genere 2-3 settimane dopo avere inviato la richiesta di supporto. 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>Che cosa accade dopo aver abilitata questa funzionalità?

Dopo che questa funzionalità è distribuita nell'organizzazione Office 365, le modifiche seguenti vengono eseguite nella ricerca contenuto nelle ricerche associate a una ricerca eDiscovery e maiuscole e minuscole per la protezione &amp; centro conformità:
  
- La casella di controllo **contenuto di Office aggiungere app per gli utenti locali** è stato aggiunto in **percorsi** della funzionalità di ricerca di contenuto. 
    
    ![La casella di controllo "Aggiungere contenuti di applicazioni di Office per gli utenti locali" viene aggiunto all'interfaccia utente di ricerca di contenuto](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Gli utenti locali vengono visualizzati in selezione i percorsi di contenuti che consente di selezionare le cassette postali utente per la ricerca. 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>Cercare chat team contenuto nelle cassette postali basate su cloud per gli utenti locali

Dopo la funzionalità è stata abilitata, è possibile utilizzare ricerca contenuto nella protezione &amp; centro conformità per la ricerca per i team di dati della chat nelle cassette postali basate su cloud per gli utenti locali. 
  
1. In sicurezza &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca contenuto**
    
2. Nella pagina **ricerca** fare clic su ![sull'icona Aggiungi](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nuova ricerca**.
    
    Come indicato in precedenza, viene visualizzata la casella di controllo **contenuto di Office aggiungere app per gli utenti locali** in **percorsi**. Si noti che sia selezionata per impostazione predefinita.
    
3. Creare la query con parole chiave e aggiungere le condizioni di query di ricerca, se necessario. Per cercare del Team solo alle chat di dati, è possibile aggiungere la query seguente nella casella **parole chiave** : 
    
    ```
    kind:im
    ``` 

4. A questo punto è possibile scegliere una delle opzioni seguenti in **posizioni**:
    
    - **Tutti i percorsi** : selezionare questa opzione per la ricerca di cassette postali di tutti gli utenti nell'organizzazione. Se la casella di controllo è selezionata, tutte le cassette postali basate su cloud per gli utenti locali è anche possibile ricercare. 
    
    - **Percorsi specifici** : selezionare questa opzione e quindi fare clic su **Modifica** \> scegliere utenti, gruppi o team per la ricerca di cassette postali specifiche. Come indicato in precedenza, la selezione di posizioni sarà possibile cercare gli utenti locali. 
    
5. Salvare ed eseguire la ricerca. Da visualizzare in anteprima alcun risultato di ricerca dalle cassette postali basate su cloud per gli utenti locali come qualsiasi altro risultato di ricerca. È inoltre possibile è possibile esportare i risultati della ricerca (inclusi i dati di chat team) in un file PST. Per ulteriori informazioni, vedere: 
    
    - [Creare una nuova ricerca](content-search.md#create-a-new-search)
    
    - [Anteprima dei risultati della ricerca](content-search.md#preview-search-results)
    
    - [Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>Utilizzo di PowerShell per cercare i team dati della chat nelle cassette postali basate su cloud per gli utenti locali

È possibile utilizzare i cmdlet **New-ComplianceSearch** e **Set-ComplianceSearch** in Office 365 Security &amp; PowerShell centro conformità per la ricerca nella cassetta postale basata su cloud per gli utenti locali. Come indicato in precedenza, non è necessario inviare una richiesta di supporto da utilizzare PowerShell per cercare i dati di chat team per gli utenti locali. 
  
1. [Connettersi a Office 365 protezione &amp; PowerShell centro conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
    
2. Esecuzione di PowerShell seguente comando per creare un nuovo contenuto ricerca le cassette postali basate su cloud degli utenti locali.
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    Il parametro *IncludeUserAppContent* viene utilizzato per specificare la cassetta postale basata sul cloud per l'utente o gli utenti specificati dal parametro *ExchangeLocation* . *AllowNotFoundExchangeLocationsEnabled* consente cassette postali basate sul cloud per gli utenti locali. Quando si utilizza il `$true` valore per questo parametro, la ricerca non tenta di convalidare l'esistenza della cassetta postale prima dell'esecuzione. Ciò è necessario eseguire le ricerche nelle cassette postali basate su cloud per gli utenti locali perché questi tipi di cassette postali non è possibile risolvere come cassette postali regolari. 
    
    Nell'esempio seguente viene eseguita la ricerca dei team di chat, che sono messaggi immediati, contenenti parole chiave "redstone" nella cassetta postale basata sul cloud di Sara Davis, che è un utente locale nell'organizzazione Contoso.
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Dopo aver creato una nuova ricerca, è necessario utilizzare il cmdlet **Start-ComplianceSearch** per eseguire la ricerca. 
  
Per ulteriori informazioni sull'utilizzo di questi cmdlet, vedere:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>Problemi noti

- Attualmente, è possibile solo ricerca, anteprima ed esportazione contenuto nelle cassette postali basate su cloud per locale agli utenti. Inserire una cassetta postale basata sul cloud per un utente locale di un'esenzione associata a una ricerca eDiscovery case o l'assegnazione a un criterio di conservazione di Office 365 non è supportato. 
    
- Selezione percorso di contenuto eDiscovery contiene consente di visualizzare gli utenti locali e sarà possibile selezionarla. Tuttavia, descritto in precedenza che esenzione non verranno applicata all'utente locale.
    
## <a name="frequently-asked-questions"></a>Domande frequenti

 **Posizione delle cassette postali basate sul cloud per gli utenti locali**
  
Cassette postali basate sul cloud vengono create e memorizzate nello stesso datacenter organizzazione Office 365. 
  
 **Esistono altri requisiti diversi da inviare una richiesta di supporto.**
  
 Come indicato in precedenza, è necessario sincronizzare le identità degli utenti con cassette postali nel % di beni nell'organizzazione basata su cloud in modo che venga creato un account utente di posta elettronica corrispondente per ogni account utente locale in Office 365. Inoltre, l'organizzazione deve disporre di una sottoscrizione a Office 365 enterprise, ad esempio una sottoscrizione a Office 365 Enterprise E1, E3 o E5. 
  
 **Esiste un rischio di perdita di dati della chat team se viene eseguita la migrazione delle cassette postali locali dell'utente nel cloud?**
  
No. Quando si esegue la migrazione la cassetta postale principale di un utente locale al cloud, i dati di chat team per tale utente verranno migrati le nuove basate su cloud cassetta postale principale.
  
 **È possibile applicare un'esenzione di eDiscovery o criteri di conservazione di Office 365 per gli utenti locali.**
  
No.
  
 **Possibile Trova ricerca contenuto Team meno recente di chat per gli utenti locali prima dell'ora organizzazione ha inviato la richiesta per attivare questa funzionalità?**
  
Microsoft avviato l'archiviazione dei dati di chat team per gli utenti locali in 31 gennaio 2018. Pertanto, se l'identità di un utente di team locale è stato sincronizzato tra Active Directory e Azure Active Directory dopo tale data, quindi i dati di chat team verranno archiviati in una cassetta postale basata sul cloud e saranno disponibile per la ricerca tramite ricerca del contenuto. Microsoft è impegnata anche sulla memorizzazione di dati di chat team dalla prima del 31 gennaio 2018 nelle cassette postali basate su cloud per gli utenti locali. Ulteriori informazioni su questa saranno resi disponibili.
