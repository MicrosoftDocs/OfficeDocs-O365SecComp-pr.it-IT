---
title: Impostare i limiti di conformità per le indagini eDiscovery in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Per creare i confini logici all'interno dell'organizzazione Office 365 che controllano l'utente i percorsi di contenuti che può eseguire ricerche in un gestore di eDiscovery, utilizzare i limiti di conformità. Limiti di conformità utilizzano autorizzazioni ricerca filtro (anche denominato conformità sicurezza filtri) per controllare quali cassette postali, i siti di SharePoint e gli account OneDrive possono essere ricercati da utenti specifici.
ms.openlocfilehash: 822d228d64d2fd5432db327db98e8d7329c7d939
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258634"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>Impostare i limiti di conformità per le indagini eDiscovery in Office 365

Limiti di conformità creare confini logici all'interno dell'organizzazione Office 365 che controllano i percorsi di contenuto utente (ad esempio le cassette postali, i siti di SharePoint e gli account OneDrive) che possono eseguire ricerche eDiscovery Manager. Inoltre, conformità limiti controllano l'accesso dei casi eDiscovery consentono di gestire l'ufficio legale, risorse umane o altre indagini all'interno dell'organizzazione. La necessità di limiti di conformità è spesso necessaria per le aziende delle Nazioni a più che devono rispettare normative e gli assalti dati geografici e negli enti pubblici, spesso suddivisa in diverse enti regionali. In Office 365, della Guida dei limiti di conformità vengano soddisfatti questi requisiti durante l'esecuzione di contenuto managing indagini con casi di eDiscovery e le ricerche.
  
L'esempio che verrà utilizzata nell'illustrazione seguente per illustrare il funzionamento dei limiti di conformità.
  
![Limiti di conformità sono costituiti filtri di ricerca per le autorizzazioni di controllo dell'accesso alle agenzie e ruoli di amministratore gruppi che controllano l'accesso ai casi eDisocovery](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
In questo esempio, Contoso LTD è un'organizzazione di Office 365 costituita da due filiali, Fourth Coffee e Coho Winery. L'azienda richiede che ricercatori e strumenti di gestione di eDiscovery possono effettuare la ricerca solo le cassette postali di Exchange, gli account di OneDrive e siti di SharePoint nel loro Agenzia. Inoltre, i responsabili di eDiscovery e ricercatori viene visualizzato solo casi di eDiscovery nel nella loro agenzia e possono accedere solo i casi è un membro del. Ecco come dei limiti di conformità soddisfano questi requisiti.
  
- Le autorizzazioni di ricerca filtro funzionalità di ricerca di contenuti controlli i percorsi di contenuti che possono eseguire ricerche ricercatori e i responsabili di eDiscovery. Di conseguenza, i responsabili di eDiscovery e ricercatori in agenzia Fourth Coffee ricerca è possono solo i percorsi di contenuti in filiale Fourth Coffee. La stessa restrizione si applica a quelle della filiale Coho Winery.
    
    Gruppi di ruolo controllare quali utenti può visualizzare i casi di eDiscovery in Office 365 Security &amp; centro conformità. Ciò significa che ricercatori ed eDiscovery Manager possono visualizzare solo i casi di eDiscovery in loro Agenzia.
    
- Gruppi di ruoli controllano che possono assegnare i membri a un caso eDiscovery. Ciò significa ricercatori e i responsabili di eDiscovery possono assegnare solo i membri per i casi in cui vengono anch ' essi essere membri del.
    
Di seguito è il processo per la configurazione dei limiti di conformità:
  
[Passaggio 1: Identificare un attributo utente per definire le enti governativi](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Passaggio 2: File di una richiesta con il supporto Microsoft per sincronizzare l'attributo utente per l'account OneDrive](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Passaggio 3: Creare un gruppo di ruoli per ogni agenzia](#step-3-create-a-role-group-for-each-agency)

[Passaggio 4: Creare un filtro di autorizzazioni di ricerca per applicare il limite di conformità](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Passaggio 5: Creare un caso eDiscovery per indagini una stretta tra le](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Passaggio 1: Identificare un attributo utente per definire le enti governativi

Il primo passaggio consiste per scegliere un attributo di Azure Active Directory da utilizzare che definirà le agenzie. Questo attributo viene utilizzato per creare il filtro di autorizzazioni di ricerca che consente di limitare una ricerca eDiscovery responsabile per la ricerca solo le posizioni del contenuto di utenti vengono assegnati un valore specifico per questo attributo. Ad esempio, si supponga che Contoso decide di usare l'attributo **reparto** . È il valore per questo attributo per gli utenti in filiale Fourth Coffee `FourthCoffee` e il valore per gli utenti in filiale Coho Winery sarà `CohoWinery`. Nel passaggio 4, si utilizzerà questo `attribute:value` percorsi eseguire una ricerca eDiscovery Manager del contenuto coppia (ad esempio, *Reparto: FourthCoffee* ) per limitare l'utente. 
  
Ecco un elenco di attributi utente Azure Active Directory che è possibile utilizzare per i limiti di conformità:
  
- Company
    
- CountryCode
    
- CustomAttribute1 - CustomAttribute15
    
- Reparto
    
- Ufficio
    
Sebbene ulteriori attributi utente siano disponibili, in particolare per cassette postali di Exchange, gli attributi sopra elencati sono le uniche è attualmente supportate da OneDrive.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Passaggio 2: File di una richiesta con il supporto Microsoft per sincronizzare l'attributo utente per l'account OneDrive

Il passaggio successivo consiste nel file di una richiesta con il supporto Microsoft per sincronizzare l'attributo di Azure Active Directory che si è scelto nel passaggio 1 di tutti gli account OneDrive nell'organizzazione. Dopo l'esecuzione della sincronizzazione, l'attributo (e il relativo valore) è selezionato nel passaggio 1 verrà mappato a una proprietà gestita nascosta in SharePoint denominato `ComplianceAttribute`. Utilizzare questo attributo per creare il filtro di autorizzazioni di ricerca di OneDrive nel passaggio 4.
  
Quando si invia la richiesta al supporto tecnico Microsoft, sono incluse le informazioni seguenti:
  
- Il nome di dominio predefinito dell'organizzazione Office 365
    
- Il nome dell'attributo Azure Active Directory (dal passaggio 1)
    
- Il titolo o la descrizione dello scopo della richiesta di supporto seguenti: "Abilitare OneDrive per Business sincronizzazione con Azure Active Directory per la conformità filtri di protezione". Ciò consente di instradare la richiesta a Office 365 eDiscovery team di progettazione che verrà implementata la richiesta.
    
Dopo aver apportato la modifica di progettazione e l'attributo viene sincronizzato con OneDrive, supporto Microsoft verrà inviato è il numero di build è stata effettuata la modifica in e una data di distribuzione stimate. Si noti che il processo di distribuzione richiede in genere 4-6 settimane dopo avere inviato la richiesta di supporto.
  
 **Importante:** È possibile completare il passaggio 3 a 5 passaggio prima che la modifica viene distribuita. Ma che eseguono ricerche di contenuto non restituirà documenti dai siti OneDrive specificati nel filtro autorizzazioni ricerca fino a dopo la modifica viene distribuita. 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Passaggio 3: Creare un gruppo di ruoli per ogni agenzia

Il passaggio successivo consiste nel creare i gruppi di ruoli in Office 365 Security &amp; centro conformità che verrà allineato con l'enti regionali. È consigliabile creare un nuovo gruppo di ruoli copiando il gruppo Manager eDiscovery incorporati, aggiungere i membri appropriati e la rimozione dei ruoli che potrebbero non essere applicabili alle proprie esigenze. Per ulteriori informazioni sui ruoli di eDiscovery, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
  
Per creare i gruppi di ruoli, passare alla pagina **autorizzazioni** di sicurezza &amp; centro conformità e creare un gruppo di ruoli per ogni team in ogni agenzia che utilizzerà i limiti di conformità e casi di eDiscovery per gestire indagini. 
  
Utilizza lo scenario di limiti di conformità di Contoso, è necessario creare quattro gruppi di ruoli e i membri appropriati aggiunto a ciascuno di essi.
  
- Fourth Coffee eDiscovery Manager
    
- Fourth Coffee ricercatori
    
- Coho Winery eDiscovery Manager
    
- Coho Winery ricercatori
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Passaggio 4: Creare un filtro di autorizzazioni di ricerca per applicare il limite di conformità
<a name="step4"> </a>

Dopo aver creato i gruppi di ruoli per ogni agenzia, il passaggio successivo consiste nel creare i filtri di autorizzazioni ricerca associare ogni gruppo di ruolo per il relativo agenzia specifico e definisce il limite di conformità. È necessario creare un filtro di autorizzazioni di ricerca per ogni agenzia. Per ulteriori informazioni sulla creazione di filtri di autorizzazioni di sicurezza, vedere [configurare autorizzazioni di filtro per la ricerca del contenuto](permissions-filtering-for-content-search.md).
  
Di seguito è riportata la sintassi utilizzata per creare un filtro di autorizzazioni di ricerca utilizzato per i limiti di conformità.

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
Ecco una descrizione di ciascun parametro nel comando:
  
-  `FilterName`-Specifica il nome del filtro. Utilizzare un nome che descrive o identifica l'agenzia che filtrano verrà utilizzato. 
    
-  `Users`-Consente di specificare gli utenti o gruppi di cui ottenere il filtro applicato per le azioni di ricerca del contenuto che eseguono. Per i limiti di conformità, questo parametro consente di specificare i gruppi di ruoli (creato nel passaggio 3) ente che si desidera creare il filtro per. Si che tratta di un parametro multivalore in modo che è possibile includere uno o più gruppi di ruoli, separati da virgole. 
    
-  `Filters`-Consente di specificare i criteri di ricerca per il filtro. Per i bordi della conformità, definire i filtri seguenti. Ognuno di essi si applica a un percorso di contenuto utente. 
    
  -  `Mailbox`-Consente di specificare le cassette postali che i gruppi di ruoli definiti nel `Users` parametro può eseguire ricerche. Per i limiti di conformità, *ComplianceAttribute* è lo stesso attributo identificato nel passaggio 1 e *AttributeValue* consente di specificare l'Agenzia. Questo filtro consente ai membri del gruppo di ruoli per effettuare la ricerca solo le cassette postali in un ente specifico; ad esempio `"Mailbox_Department -eq 'FourthCoffee'"` . 
    
  -  `Site`-Consente di specificare gli account OneDrive i gruppi di ruoli definiti nel `Users` parametro può eseguire ricerche. Per il filtro di OneDrive, utilizzare la stringa effettiva `ComplianceAttribute`; questo verrà eseguito il mapping allo stesso attributo identificato nel passaggio 1 e che viene sincronizzato con account OneDrive a causa della richiesta di supporto che inviato nel passaggio 2;  *AttributeValue* consente di specificare l'Agenzia. Questo filtro consente ai membri del gruppo di ruoli in cui cercare solo gli account OneDrive agenzia specifica; ad esempio `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.
    
  -  `Site_Path`-Consente di specificare i siti di SharePoint che i gruppi di ruoli definiti nel `Users` parametro può eseguire ricerche. *SharePointURL* consente di specificare i siti ente membri del gruppo di ruolo possono eseguire ricerche; Per esempio`Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`
    
-  `Action`-Specifica il tipo di azione Compliance ricerca che il filtro viene applicato a. Ad esempio `-Action Search` il filtro si applica solo quando i membri dei gruppi di ruolo definito nel `Users` parametro consente di eseguire una ricerca di contenuto. In questo caso, non sarebbe applicato il filtro per l'esportazione dei risultati della ricerca. Per i bordi della conformità, utilizzare `-Action All` in modo che il filtro viene applicato a tutte le azioni di ricerca. 
    
    Per un elenco delle azioni di ricerca del contenuto, vedere la sezione "New-ComplianceSecurityFilter" [configurare autorizzazioni di filtro per la ricerca del contenuto](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).
    
Di seguito sono riportati esempi dei filtri autorizzazioni due ricerca creati per supportare lo scenario dei limiti di conformità Contoso.
  
 **Fourth Coffee**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **Coho Winery**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a>Passaggio 5: Creare un caso eDiscovery per indagini una stretta tra le

Il passaggio finale consiste nel creare un nuovo caso nella protezione &amp; centro conformità e quindi aggiungere il gruppo di ruoli, ovvero creato nel passaggio 3: come membro del case. Di conseguenza, due importanti caratteristiche di utilizzo dei limiti di conformità:
  
- Solo i membri del gruppo di ruoli aggiunti al caso sarà in grado di visualizzare e accedere il caso di sicurezza &amp; centro conformità. Se il gruppo di ruoli Fourth Coffee ricercatori è l'unico membro di un caso, ad esempio, i membri del gruppo di ruolo Manager eDiscovery Fourth Coffee (o membri di qualsiasi altro gruppo) non saranno in grado di visualizzare o accedere il caso.
    
- Quando un membro del gruppo di ruoli assegnato a un caso viene eseguita una ricerca associata al caso, sono solo saranno in grado di cercare i percorsi contenuti all'interno di loro agency (che è definita dal filtro autorizzazioni ricerca creato nel passaggio 4.)


Per creare un nuovo caso e assegnare i membri:
    
1. Andare alla pagina di **eDiscovery** in sicurezza &amp; centro conformità e creare un nuovo caso. 
    
2. Nell'elenco dei casi di eDiscovery, fare clic sul nome del caso che appena creato.
    
3. Nella pagina comparsa **Gestisci in questo caso** , in **gruppi di ruoli Gestisci**, fare clic su ![sull'icona Aggiungi](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.
    
    ![Aggiungere un gruppo di ruoli come membro di un caso eDiscovery](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. Nell'elenco dei gruppi di ruoli, selezionare uno dei gruppi di ruolo creato nel passaggio 3 e fare clic su **Aggiungi**.
    
5. Fare clic su **Salva** in comparsa **Gestisci questo case** per salvare le modifiche. 

## <a name="compliance-boundary-limitations"></a>Limitazioni di limite di conformità

Durante la gestione dei casi di eDiscovery e indagini che utilizzano dei confini di conformità, tenere presenti le limitazioni seguenti.
  
- Durante la creazione e l'esecuzione di una ricerca di contenuto, è possibile selezionare i percorsi di contenuti che si trovano all'esterno l'Agenzia. A causa del filtro di autorizzazioni di ricerca il contenuto da tali posizioni non saranno incluse nei risultati della ricerca.
    
- Limiti di conformità non si applicano a esenzioni in casi di eDiscovery. Ciò significa che un gestore di eDiscovery in un ente possibile inserire un utente in un ente diverso in attesa. Tuttavia, verrà applicato al limite di conformità se il gestore di eDiscovery cerca i percorsi di contenuti dell'utente che è stato messo in attesa. Pertanto, gestione di eDiscovery non sarà possibile ricerca in grado i percorsi di contenuti dell'utente, anche se fossero in grado di effettuare l'utente in attesa.
    
    Tenere inoltre statistiche verranno applicata solo ai percorsi di contenuti nell'ente.
    
- Filtri di ricerca per le autorizzazioni non vengono applicati alle cartelle pubbliche di Exchange.

## <a name="searching-and-exporting-sharepoint-content-in-multi-geo-environments"></a>Ricerca e l'esportazione del contenuto di SharePoint negli ambienti Multi-Geo

Filtri di ricerca per le autorizzazioni consentono inoltre di controllare in cui il contenuto viene instradato per l'esportazione e i centri dati possono essere eseguita la ricerca OneDrive account e i siti di SharePoint in un [ambiente Multi-Geo SharePoint](https://go.microsoft.com/fwlink/?linkid=860840):
  
- Esportare i risultati della ricerca da un centro dati specifici. Ciò significa che è possibile specificare che i dati al centro posizione che i risultati verranno esportati dalla ricerca.
    
- Instradare la ricerca di OneDrive account e i siti di SharePoint a un centro dati satellitari. Ciò significa che è possibile specificare l'ubicazione del centro dati in cui verranno eseguite ricerche.
    
Utilizzare il parametro **Region** per i cmdlet **New-ComplianceSecurityFilter** o **Set-ComplianceSecurityFilter** per creare o modificare i Data Center sarà instradato attraverso l'esportazione.
  
|**Valore del parametro**|**Ubicazione del centro dati**|
|:-----|:-----|
|NAM  <br/> |Nord America (dati effettivi Center sono negli Stati Uniti)  <br/> |
|EUR  <br/> |Europa  <br/> |
|APC  <br/> |Asia Pacifico  <br/> |
|CAN <br/> |Canada
   
Analogamente, è possibile utilizzare i seguenti valori per i valori dei parametri **area** per controllare i data center in ricerche di contenuto verranno eseguiti nel durante la ricerca dei percorsi di SharePoint e OneDrive. Si noti che nella tabella seguente vengono inoltre i data center di esportazioni saranno instradate attraverso. 
  
|**Valore del parametro**|**Percorsi di routing per l'esportazione del centro dati**|
|:-----|:-----|
|NAM  <br/> |IT  <br/> |
|EUR  <br/> |Europa  <br/> |
|APC  <br/> |Asia Pacifico  <br/> |
|CAN  <br/> |IT  <br/> |
|AUS  <br/> |Asia Pacifico  <br/> |
|KOR  <br/> |Centro dati predefinito dell'organizzazione  <br/> |
|GBR  <br/> |Europa  <br/> |
|JPN  <br/> |Asia Pacifico  <br/> |
|RICERCA  <br/> |Asia Pacifico  <br/> |
|LAM  <br/> |IT  <br/> |
   
 **Nota:** Se non si specifica il parametro Region per un filtro di autorizzazioni di ricerca, vengono esportati i risultati della ricerca dal centro dati più vicino. 
  
Di seguito sono riportati esempi dell'utilizzo di **-area** parametro durante la creazione di filtri di autorizzazione di ricerca per i limiti di conformità. Si presuppone che la filiale Fourth Coffee si trova in Nord America e che Coho Winery in Europa. 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
Tenere presenti durante la ricerca e l'esportazione di SharePoint e OneDrive i seguenti aspetti contenuto in ambienti multi-geo.
  
- Il parametro **Region** non controllare le ricerche delle cassette postali di Exchange; tutti i data Center verrà eseguita la ricerca quando si esegue la ricerca delle cassette postali. Per limitare l'ambito di Exchange che è possono eseguire la ricerca di cassette postali, utilizzare il parametro **filtri** quando si crea o modifica di un filtro di autorizzazioni di ricerca. 
    
- Se è necessario che una ricerca eDiscovery Manager eseguire ricerche in più aree di SharePoint, è necessario creare un account utente diverso per tale eDiscovery manager che può essere utilizzato nel filtro delle autorizzazioni di ricerca per specificare l'area alternativo qualora la Siti di SharePoint o gli account OneDrive si trovano.
    
- Durante la ricerca di contenuto in SharePoint e OneDrive, il parametro **Region** indirizza le ricerche per principale o satellitare posizioni in manager eDiscovery eseguirà indagini eDiscovery. Se un gestore di eDiscovery eseguita la ricerca dei siti di SharePoint e OneDrive di fuori l'area specificata nel filtro delle autorizzazioni di ricerca, non verrà restituito alcun risultato di ricerca. 
    
- Per l'esportazione dei risultati della ricerca, il contenuto da tutti i percorsi di contenuti, inclusi Exchange, Skype per Business, SharePoint, OneDrive e altri servizi in Office 365 è possibile eseguire la ricerca utilizzando lo strumento di ricerca di contenuto, verrà caricato nel percorso di archiviazione Azure nel centro dati specificato dal parametro **Region** . Consente alle organizzazioni di mantenere in conformità non consentendo contenuto tra i bordi controllati da esportare. Se nessuna regione è specificata nel filtro delle autorizzazioni di ricerca, il contenuto caricato all'area predefinita dell'organizzazione. 
    
- È possibile modificare un filtro di autorizzazioni di ricerca esistente per aggiungere o modificare l'area eseguendo il comando seguente:

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>Domande frequenti

 **Chi può creare e gestire i filtri di ricerca autorizzazioni (utilizzando New-ComplianceSecurityFilter e i cmdlet Set-ComplianceSecurityFilter)?**
  
Per creare, visualizzare e modificare i filtri di ricerca per le autorizzazioni, è necessario essere membri del gruppo di ruoli Gestione organizzazione in sicurezza &amp; centro conformità.
  
 **Se un gestore di eDiscovery è assegnato a più di un gruppo di ruolo che si espande su più enti regionali, come cui cercare il contenuto di un ente o l'altro?**
  
Gestione di eDiscovery può aggiungere parametri per le query di ricerca che verrà limitare la ricerca a un ente specifico. Ad esempio, se un'organizzazione ha specificato la proprietà **CustomAttribute10** per distinguere enti, può aggiungere le seguenti per le query di ricerca OneDrive account e le cassette postali in un ente specifici: `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.
  
 **Cosa succede se si modifica il valore dell'attributo in cui viene utilizzata come l'attributo di conformità in un filtro di autorizzazioni di ricerca?**
  
Sono necessari fino a 3 giorni per un filtro di ricerca delle autorizzazioni applicare il limite di conformità, se si modifica il valore dell'attributo viene utilizzato nel filtro. Ad esempio, nello scenario di Contoso si supponga che un utente in agenzia Fourth Coffee viene trasferito al ente Coho Winery. Di conseguenza, il valore dell'attributo **reparto** sull'oggetto utente viene modificato da *FourthCoffee* a *CohoWinery* . In questo caso, investitori e Fourth Coffee eDiscovery verranno visualizzati i risultati della ricerca per tale utente per backup 3 giorni dopo la modifica dell'attributo. Analogamente, richiede fino a 3 giorni prima di responsabili di eDiscovery Coho Winery e ricercatori verranno visualizzati i risultati della ricerca per l'utente. 
  
 **Un manager di eDiscovery possono visualizzare il contenuto da due limiti di conformità separato.**
  
Sì. Possono essere eseguita aggiungendo l'utente ai gruppi di ruolo che sono visibili agli enti governativi entrambi.
  
 **La ricerca funzioni filtri autorizzazioni esenzioni casi di eDiscovery, i criteri di conservazione Office 365 o DLP?**
  
No, non ora
  
 **Se specifica un'area di controllo in cui il contenuto viene esportato, ma non è un'organizzazione di SharePoint in tale area, è comunque di ricerca SharePoint?**
  
Se l'area specificata nel filtro delle autorizzazioni di ricerca non esiste nell'organizzazione, verrà eseguita la ricerca nell'area predefinita.
  
 **Che cos'è il numero massimo di filtri di ricerca per le autorizzazioni che possono essere creati in un'organizzazione?**
  
Non esiste alcun limite al numero di filtri di ricerca per le autorizzazioni che possono essere creati in un'organizzazione. Tuttavia, le prestazioni della ricerca inciderà quando sono presenti più di 100 filtri di ricerca per le autorizzazioni. Per mantenere al minimo il numero di filtri di ricerca per le autorizzazioni nell'organizzazione, creare filtri di combinano le regole di Exchange, SharePoint e OneDrive in un filtro di autorizzazioni singola ricerca quando possibile.
