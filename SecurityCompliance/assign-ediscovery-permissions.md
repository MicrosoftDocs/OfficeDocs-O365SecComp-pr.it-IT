---
title: Assegnare le autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Assegnare le autorizzazioni necessarie per eseguire attività correlate alla eDiscovery utilizzando la sicurezza &amp; centro conformità.
ms.openlocfilehash: 95f0ed171c37ec84ca8bb8f00e69ab0318cd31cd
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29741159"
---
# <a name="assign-ediscovery-permissions-in-the-office-365-security-amp-compliance-center"></a>Assegnare le autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità

Se si desidera che gli utenti utilizzino uno qualsiasi degli strumenti di eDiscovery in Office 365 Security &amp; centro conformità, è necessario assegnare loro le autorizzazioni appropriate. Il modo più semplice per ottenere questo risultato consiste nell'aggiungere la persona al gruppo di ruolo appropriato nella pagina **autorizzazioni** in Office 365 Security &amp; centro conformità. In questo argomento vengono descritte le autorizzazioni necessarie per eseguire attività correlate alla eDiscovery utilizzando la sicurezza &amp; centro conformità. 
  
Il gruppo di ruoli correlati eDiscovery principale in sicurezza &amp; centro conformità viene chiamato **eDiscovery Manager**. Esistono due sottogruppi all'interno di questo gruppo di ruoli. 
  
- **eDiscovery Manager** - una ricerca eDiscovery Manager possibile utilizzare lo strumento di ricerca di contenuto per la protezione &amp; centro conformità di cercare i percorsi di contenuti nell'organizzazione ed eseguire varie operazioni correlati alla ricerca, ad esempio preview ed esportare ricerca risultati. Membri possono inoltre creare e gestire casi di eDiscovery, aggiungere e rimuovere membri a un caso, creazione di esenzioni maiuscole ed eseguire ricerche del contenuto associato a un caso e accedere ai dati casi di eDiscovery avanzate di Office 365.  Una ricerca eDiscovery Manager possono accedere solo ai e gestire le modalità di creazione. Non possono accedere o gestione dei casi dagli altri responsabili di eDiscovery. 
    
- **eDiscovery amministratori** - un'amministratore di eDiscovery è un membro del gruppo di ruoli di gestione di eDiscovery e può eseguire le stesse ricerca contenuto sociale correlate alla gestione attività e che può eseguire una ricerca eDiscovery Manager. Inoltre, un'amministratore di eDiscovery può: 
    
  - Accedere a tutti i casi elencate nella pagina **casi di eDiscovery** in sicurezza &amp; centro conformità. 

  - Accedere ai dati casi di eDiscovery avanzate per qualsiasi caso nell'organizzazione.
    
  - Gestire i casi di eDiscovery dopo essersi aggiunto come membro del caso.
  
  Per motivi per cui si decide eDiscovery amministratori dell'organizzazione, vedere la sezione [informazioni](#more-information) . 

> [!NOTE]
> Per analizzare i dati dell'utente tramite eDiscovery avanzate, l'utente (depositaria dei dati) deve essere assegnato una licenza di Office 365 E5. In alternativa, gli utenti con una licenza di Office 365 E1 o E3 è possibile assegnare una licenza autonoma eDiscovery avanzate. Gli amministratori e responsabili della conformità assegnati ai casi e utilizzare eDiscovery avanzate per analizzare i dati non è necessario una licenza E5.  
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario essere membri del gruppo di ruoli Gestione organizzazione (o essere assegnato il ruolo di gestione dei ruoli) per assegnare le autorizzazioni di eDiscovery in sicurezza &amp; centro conformità.
    
- È possibile utilizzare il cmdlet [Add-RoleGroupMember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) in sicurezza &amp; PowerShell centro conformità per aggiungere un gruppo di protezione abilitati alla posta elettronica come membro del sottogruppo di responsabili di eDiscovery nel gruppo di ruoli di gestione di eDiscovery. Tuttavia, è possibile aggiungere un gruppo di protezione abilitati alla posta elettronica al sottogruppo amministratori eDiscovery. Per ulteriori informazioni, vedere [ulteriori informazioni](#more-information) . 
    
## <a name="assign-ediscovery-permissions-in-the-security-amp-compliance-center"></a>Assegnare le autorizzazioni di eDiscovery in sicurezza &amp; centro conformità

1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **autorizzazioni**e quindi la casella di controllo accanto a **eDiscovery Manager**.
    
4. Nella pagina comparsa **eDiscovery Manager** , effettuare una delle opzioni seguenti in base alle autorizzazioni eDiscovery che si desidera assegnare. 
    
  - **Per effettuare una ricerca eDiscovery Manager un utente** Accanto a **eDiscovery Manager**, fare clic su **Modifica**. In **eDiscovery selezionati Manager**, fare clic su **Modifica**e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **Add**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come un manager di eDiscovery e quindi fare clic su **Aggiungi**. Una volta terminato l'aggiunta di utenti, fare clic su **Chiudi**. Quindi, nella pagina **Modifica scegliere eDiscovery Manager** tendina fare clic su **Salva** per salvare le modifiche alle appartenenze di gestione di eDiscovery. 
    
  - **Per impostare un utente come un'amministratore di eDiscovery** Accanto a **eDiscovery amministratore**, fare clic su **Modifica**. In **eDiscovery selezionati gli amministratori**, fare clic su **Modifica**e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **Add**. Selezionare l'utente (o gli utenti) che si desidera aggiungere come un'amministratore di eDiscovery e quindi fare clic su **Aggiungi**. Una volta terminato l'aggiunta di utenti, fare clic su **Chiudi**. Quindi, nella pagina **Modifica scegliere eDiscovery amministratore** tendina fare clic su **Salva** per salvare le modifiche a eDiscovery l'appartenenza degli amministratori. 
    
> [!NOTE]
> È inoltre possibile utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** per effettuare una ricerca eDiscovery amministratore di un utente. Tuttavia, l'utente deve essere assegnato il ruolo di gestione Case prima di poter utilizzare questo cmdlet in modo da renderli un'amministratore di eDiscovery. Per ulteriori informazioni, vedere [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
Nella pagina **autorizzazioni** di sicurezza &amp; centro conformità, è inoltre possibile assegnare agli utenti le autorizzazioni relative a eDiscovery, aggiungendoli a gruppi di ruoli amministratore di conformità, la gestione dell'organizzazione e revisore. Per una descrizione dei ruoli RBAC correlati eDiscovery assegnati a ognuno di questi gruppi di ruoli, vedere la sezione [ruoli RBAC relative a eDiscovery](#rbac-roles-related-to-ediscovery) . 

## <a name="rbac-roles-related-to-ediscovery"></a>Ruoli RBAC relativi a eDiscovery

Nella tabella seguente sono elencati i ruoli RBAC relative a eDiscovery in & la sicurezza centro conformità e indica i gruppi di ruoli incorporati che ogni ruolo viene assegnato per impostazione predefinita. 
    
|**Ruolo**|**Amministratore di conformità**|**Amministratore gestione & eDiscovery**|**Gestione organizzazione**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Gestione dei casi <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Ricerca di conformità <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Esportazione <br/> | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Archiviazione <br/>  |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Anteprima <br/>  | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Revisione  <br/>  | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|Decrittografia RMS <br/>  ||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Ricerca ed eliminazione <br/> | <br/> | <br/> |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
Nelle sezioni seguenti vengono illustrati i ruoli RBAC correlati eDiscovery elencati nella tabella precedente.

### <a name="case-management"></a>Gestione dei casi

Questo ruolo consente agli utenti di creare, modificare, eliminare e controllare l'accesso ai casi di eDiscovery in & la sicurezza centro conformità. Per ulteriori informazioni, vedere [gestione dei casi di eDiscovery in Office 365 Security &amp; centro conformità](manage-ediscovery-cases.md). Come indicato in precedenza, un utente deve essere assegnato il ruolo di gestione Case prima di poter utilizzare il cmdlet **Add-eDiscoveryCaseAdmin** in modo da renderli un'amministratore di eDiscovery. 

### <a name="compliance-search"></a>Ricerca di conformità

Questo ruolo consente agli utenti di eseguire lo strumento di ricerca del contenuto in & la sicurezza centro conformità per la ricerca di cassette postali e cartelle pubbliche, siti di SharePoint Online, OneDrive per i siti di Business Skype per le conversazioni, gruppi di Office 365 e Teams Microsoft Business. Questo ruolo consente di ottenere una stima dei risultati della ricerca e creazione di report di esportazione, ma ruoli aggiuntivi necessari per avviare le azioni di ricerca del contenuto, ad esempio l'anteprima, esportazione o l'eliminazione dei risultati di ricerca.

Si noti che gli utenti assegnati al ruolo di conformità ricerca ma non è installato il ruolo di anteprima possono visualizzare in anteprima i risultati della ricerca in cui è stata avviata l'azione preview da un utente che ha assegnato il ruolo di anteprima. L'utente senza il ruolo di anteprima è possibile visualizzare un'anteprima dei risultati per fino a due settimane dopo che l'azione iniziale preview è stato creato.

Analogamente, gli utenti assegnati al ruolo di conformità ricerca ma non l'esportazione di ruolo può scaricare i risultati della ricerca in cui è stata avviata l'azione di esportazione da un utente che ha assegnato il ruolo di esportazione. L'utente senza il ruolo di esportazione può scaricare i risultati di ricerca di fino a due settimane dopo che è stato creato l'azione Esporta iniziale. Dopo che non saranno in grado di scaricare i risultati a meno che un utente con il ruolo di esportazione viene riavviato l'esportazione.

Per ulteriori informazioni, vedere [Ricerca contenuto in Office 365](content-search.md). 

### <a name="export"></a>Esportazione

Il ruolo consente agli utenti di esportare i risultati di una ricerca di contenuto in un computer locale. Consente inoltre li preparare i risultati della ricerca per l'analisi di eDiscovery avanzate. 

Per ulteriori informazioni sull'esportazione dei risultati della ricerca, vedere [esportazione risultati della ricerca da & la protezione di Office 365 centro conformità](export-search-results.md).

### <a name="hold"></a>Archiviazione

Questo ruolo consente agli utenti di inserire i contenuti delle cassette postali, le cartelle pubbliche, Skype per le conversazioni aziendali, siti e gruppi di Office 365 in attesa. Quando il contenuto è in attesa, i proprietari dei contenuti saranno ancora in grado di modificare o eliminare il contenuto originale, ma il contenuto verrà mantenuto finché non viene rimossa la conservazione o fino a quando scade la durata dell'attesa. 

Per ulteriori informazioni sulle esenzioni, vedere:

- [casi di eDiscovery in & la protezione di Office 365 centro conformità](ediscovery-cases.md) 
- [Panoramica dei criteri di conservazione](retention-policies.md)

### <a name="preview"></a>Anteprima

Questo ruolo consente agli utenti di visualizzare un elenco di elementi che sono stati restituiti dalla ricerca di contenuto. Essi verranno inoltre in grado di aprire e visualizzare ogni elemento nell'elenco per visualizzarne il contenuto.

### <a name="review"></a>Revisione 

Questo ruolo consente agli utenti di accedere ai dati casi di eDiscovery avanzate di Office 365. Lo scopo principale di questo ruolo deve fornire agli utenti l'accesso a eDiscovery avanzate. Gli utenti assegnati al ruolo possono vedere e aprire l'elenco dei casi nella pagina di eDiscovery in & la sicurezza centro conformità che sono membri di. Dopo che l'utente accede a un caso di & la sicurezza centro conformità, è possibile fare clic su **passa a eDiscovery avanzate** per accedere e analisi dei dati casi di eDiscovery avanzate. Questo ruolo non consentirà all'utente di visualizzare in anteprima i risultati di una ricerca di contenuto che è associato il caso o di eseguire altri ricerca contenuto o l'attività di gestione dei casi.

### <a name="rms-decrypt"></a>Decrittografia RMS

In questo ruolo consente agli utenti decrittografa crittografati RMS messaggi di posta elettronica durante l'esportazione dei risultati della ricerca o la preparazione dei risultati di ricerca per l'analisi di eDiscovery avanzate. Per ulteriori informazioni sulla decrittografia di risultati della ricerca durante l'esportazione, vedere [esportazione risultati della ricerca da & la protezione di Office 365 centro conformità](export-search-results.md).

### <a name="search-and-purge"></a>Ricerca ed eliminazione

Questo ruolo consente agli utenti di eseguire la rimozione di blocco di dati corrispondenti ai criteri di ricerca di contenuto. Per ulteriori informazioni, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione Office 365](search-for-and-delete-messages-in-your-organization.md). 


## <a name="more-information"></a>Ulteriori informazioni

- **Informazioni sulla creazione di un'amministratore di eDiscovery?** Come precedentemente illustrato, una ricerca eDiscovery amministratore è membro del gruppo di ruoli gestione eDiscovery in grado di visualizzare e accedere a tutti i casi di eDiscovery nell'organizzazione. Questa possibilità di accedere a tutti i casi di eDiscovery ha due importanti scopi: 
    
  - Se una persona è l'unico membro di un caso eDiscovery lascia l'organizzazione, inclusi i membri del gruppo di ruoli Gestione organizzazione o un altro membro del gruppo di ruoli di gestione di eDiscovery, per accedere tale caso di eDiscovery poiché non sono membri di un caso. In questo caso, non potrebbe essere possibile in alcun modo per accedere ai dati nel caso. Ma dal momento che un'amministratore di eDiscovery può accedere a tutti i casi di eDiscovery nell'organizzazione, possano visualizzare il caso nella protezione &amp; centro conformità e aggiungere se stessi o un altro eDiscovery manager come membro del case.
    
  - Dal momento che un'amministratore di eDiscovery può visualizzare e accedere a tutti i casi di eDiscovery, può controllare e controllare tutti i casi e associate le ricerche di conformità. Ciò consente di impedire qualsiasi utilizzo non corretto delle ricerche di conformità o casi di eDiscovery. E poiché eDiscovery gli amministratori possono accedere a informazioni riservate nei risultati della ricerca di conformità, è consigliabile limitare il numero di persone che sono amministratori eDiscovery.
    
    EDiscovery, inoltre, gli amministratori nella protezione &amp; centro conformità vengono aggiunte automaticamente come amministratori di eDiscovery avanzate. Pertanto, che è necessario essere un'amministratore di eseguire attività amministrative di eDiscovery avanzate, ad esempio configurazione degli utenti, creare casi e importazione dei dati in un caso eDiscovery.
    
- **È possibile aggiungere un gruppo con un account membro del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità?** Come precedentemente illustrato, è possibile aggiungere un gruppo di protezione abilitati alla posta elettronica come membro del sottogruppo di responsabili di eDiscovery nel gruppo di ruoli di gestione di eDiscovery utilizzando il cmdlet **Add-RoleGroupMember** in sicurezza &amp; PowerShell centro conformità. Ad esempio, è possibile eseguire il comando seguente per aggiungere un gruppo di protezione abilitati alla posta elettronica per il gruppo di ruoli di gestione di eDiscovery. 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Si noti che un gruppo di distribuzione di Exchange o un gruppo di Office 365 non sono supportati. È necessario utilizzare un gruppo di protezione abilitati alla posta elettronica, è possibile creare in Exchange Online PowerShell utilizzando il ` New-DistributionGroup -Type Security ` comando. È inoltre possibile creare un gruppo di protezione abilitati alla posta elettronica (e aggiungere membri) nell'interfaccia di amministrazione di Exchange o nell'interfaccia di amministrazione di Office 365. Si noti che potrebbero richiedere fino a 60 minuti dopo averlo creato per un nuovo di protezione abilitati alla posta elettronica sia disponibile per aggiungere al gruppo di ruoli Manager eDiscovery. 
    
    Anche come affermato in precedenza, non è possibile effettuare una protezione abilitati alla posta elettronica un'amministratore di eDiscovery di gruppo utilizzando il cmdlet **Add-eDiscoveryCaseAdmin** in sicurezza &amp; PowerShell centro conformità. È possibile aggiungere solo i singoli utenti come amministratori di eDiscovery. 
    
    Si noti che è anche possibile aggiungere un gruppo di protezione abilitati alla posta elettronica come membro di un caso.
