---
title: Domande frequenti sulla crittografia del servizio con Customer Key per Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: Oltre a linea di base, la crittografia a livello di volume che è stata abilitata tramite BitLocker e distribuita chiave Manager (DKM), Office 365 offre un ulteriore livello di crittografia a livello di applicazione per il contenuto dei clienti in Office 365, ad esempio dati di Exchange In linea, Skype per Business, SharePoint Online e OneDrive for Business. Si tratta la crittografia del servizio.
ms.openlocfilehash: ceba35233872bb65b7706ed4e11a263057adc6c1
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575330"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Domande frequenti sulla crittografia del servizio con Customer Key per Office 365

Oltre a linea di base, la crittografia a livello di volume che è stata abilitata tramite BitLocker e distribuita chiave Manager (DKM), Office 365 offre un ulteriore livello di crittografia a livello di applicazione per il contenuto dei clienti in Office 365, ad esempio dati di Exchange In linea, Skype per Business, SharePoint Online e OneDrive for Business. Si tratta la crittografia del servizio.
  
Chiave cliente si basa sulla crittografia del servizio e attiva l'immissione e le chiavi di controllo utilizzati per crittografare i dati statici in Office 365, come descritto in [Termini di servizi in linea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx). Chiave cliente consente di far fronte agli obblighi di conformità dal momento che è possibile controllare le chiavi di crittografia utilizzati da Office 365 per decrittografare i dati.
  
Per inviare commenti e suggerimenti sulla chiave dei clienti, inclusa la documentazione, inviare idee, suggerimenti e prospettive a customerkeyfeedback@microsoft.com.
  
## <a name="what-is-service-encryption-with-customer-key"></a>Che cos'è la crittografia del servizio con chiave di clienti?

Chiave cliente aumenta la capacità dell'organizzazione per soddisfare le esigenze dei requisiti di conformità che specificano chiave accordi con il provider di servizi cloud. Con la chiave di clienti, fornire e controllare le chiavi di crittografia per l'Office 365 dati al-rest a livello di applicazione. Di conseguenza, è possibile esercitare un controllo e revocare le chiavi della propria organizzazione, se si decide di chiudere il servizio. Per revocare le chiavi, i dati sono illeggibili al servizio. Revoca chiave è il primo passaggio sul percorso per raggiungere l'eliminazione dei dati.

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>I dati di Office 365 statici sono occupati da chiave cliente?
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

Contenuto del sito SharePoint Online e i file archiviati in tale sito e i file caricati OneDrive for Business sono trattati. Viene descritto il contenuto delle cassette postali Exchange Online (corpo del messaggio di posta elettronica, le voci di calendario e il contenuto degli allegati di posta elettronica). Conversazioni di testo da Skype per le aziende sono trattate, ma non viene trattati le registrazioni Skype riunione trasmissione e caricamento di contenuto riunione Skype. Skype riunione trasmissione e Skype riunione il caricamento di contenuto viene crittografato con tutti gli altri contenuti in Office 365, ma attualmente non offriamo controllo customer delle chiavi di crittografia.
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>Che cos'è la differenza tra chiave cliente e inserire il proprio chiave (BYOK) con Azure Information Protection per Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Entrambe le opzioni consentono di fornire e controllare il proprio chiavi di crittografia; Tuttavia, servizio con clienti chiave vengono crittografati i dati statici, che risiede in Office 365 server al-rest, mentre BYOK con Azure Information Protection per Exchange Online consente di crittografare i dati in transito e fornisce persistent online e offline protezione per messaggi di posta elettronica e allegati di Office 365. Chiave cliente e BYOK con Azure Information Protection per Exchange Online sono complementari e se si sceglie di utilizzare chiavi di Microsoft Management service o il proprio chiavi, crittografare i dati in rest e in transito può fornire una protezione sono stati aggiunta da attacchi dannosi.
  
BYOK con Azure Information Protection per Exchange Online è disponibile la funzionalità di Office 365 Message Encryption.
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>La crittografia dei messaggi di Office 365 e portare in primo piano del proprio chiave con Azure Information Protection ogni volta approccio di Microsoft per le richieste di dati di terze parti, ad esempio citazioni?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Crittografia dei messaggi di Office 365 e l'opzione per offrire e controllare il proprio chiavi di crittografia con portare in primo piano del proprio chiave (BYOK) per Azure Information Protection (AIP) non sono stati progettati per rispondere a citazioni applicazione della legge. Crittografia dei messaggi di Office 365 con BYOK per AIP è stata progettata per i clienti di conformità sono disponibili che è necessario soddisfare i propri obblighi di conformità interni o esterni. Microsoft ha molto prendere in seria le richieste di terze parti per i dati dei clienti. Come provider di servizi cloud, è sempre sostenere la privacy dei dati dei clienti. Nel caso in cui è possibile ottenere un mandato di comparizione, sempre eseguito un tentativo di reindirizzare la terza parte per il cliente per ottenere le informazioni. (Leggere il blog Brad Smith: [dati relativi ai clienti Protecting da government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Si pubblicano periodicamente informazioni dettagliate di richiesta è visualizzato [di seguito](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data).
  
Vedere il [Centro protezione di Microsoft](https://www.microsoft.com/en-us/trustcenter/default.aspx) sulle richieste di dati di terze parti e "Divulgazione di dati dei clienti" in [Termini di servizi in linea (OST) ](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)per ulteriori informazioni.
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>La crittografia del servizio con clienti chiave cambiano approccio di Microsoft per le richieste di dati di terze parti, ad esempio citazioni?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Chiave cliente non è stato progettato per rispondere a citazioni applicazione della legge. È stata progettata per i clienti regolamentati soddisfare gli obblighi di conformità interni o esterni. Microsoft ha molto prendere in seria le richieste di terze parti per i dati dei clienti. Come provider di servizi cloud, è sempre sostenere la privacy dei dati dei clienti. Nel caso in cui è possibile ottenere un mandato di comparizione, sempre eseguito un tentativo di reindirizzare la terza parte per il cliente per ottenere le informazioni. (Leggere il blog Brad Smith: [dati relativi ai clienti Protecting da government snooping](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Si pubblicano periodicamente informazioni dettagliate di richiesta è visualizzato [di seguito](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data).
  
Vedere il [Centro protezione di Microsoft](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data) sulle richieste di dati di terze parti e "Divulgazione di dati dei clienti" in [Termini di servizi in linea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx) per ulteriori informazioni. 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>È disponibile per l'implementazione della chiave cliente FastTrack supporto?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. FastTrack viene utilizzata solo per la raccolta di tenant del servizio le informazioni sulla configurazione che è necessari effettuare la registrazione per clienti chiave. Il tasto cliente offre vengono pubblicati da FastTrack in modo che è utile per clienti e partner inviare queste informazioni necessarie utilizzando lo stesso metodo e facilità di dati che consentono ai clienti l'offerta di archiviazione.
  
Se è necessario per il supporto aggiuntivo oltre la documentazione, contattare Microsoft Consulting Services (MCS), Premier campo Engineering (PFE) o un partner di Microsoft per assistenza.
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>Se vengono eliminati i tasti, com'è possibile recuperare?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La chiave di disponibilità viene fornita con la possibilità di ripristinare dalla perdita imprevista di chiavi principali da gestire. Se si perdono le chiavi di primo livello, contatti e supporto Microsoft per Microsoft consentirà passaggi del processo di attivazione della chiave di disponibilità. Utilizzare il tasto di disponibilità per la migrazione a un nuovo criterio di crittografia dei dati con i tasti di nuovi il provisioning dall'utente. 
  
## <a name="what-is-the-availability-key"></a>Che cos'è la chiave di disponibilità?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La chiave di disponibilità è una chiave principale che viene eseguito il provisioning quando si crea un criterio di crittografia dei dati. La chiave di disponibilità viene archiviata e protetta in Office 365 e a livello funzionale equivale alla pressione dei tasti due radice in cui vengono inseriti dall'utente per l'utilizzo con la crittografia del servizio clienti chiave. A differenza di tasti che forniscono e gestione di Azure chiave cassaforte, è possibile accedere direttamente la chiave di disponibilità. Archiviazione e il controllo della chiave disponibilità sono intenzionalmente diverse da Azure chiave cassaforte per tre motivi: innanzitutto la chiave di disponibilità fornisce una funzionalità di disponibilità elevata in caso di servizi di Office 365 sono in grado di raggiungere chiavi ospitate nella chiave Azure Cassaforte; in secondo luogo, la chiave di disponibilità fornisce una funzionalità "interruzione di ingrandimento" nel caso in cui entrambe le chiavi Azure chiave cassaforte vanno perse. e la terza la separazione dei controlli logici sono disponibili in difesa e la protegge da punto di errore o la perdita di tutte le chiavi da un singolo attacco. Condivisione di competenza per proteggere i tasti mentre si utilizza una vasta gamma di protezioni e i processi per la gestione delle chiavi, in ultima analisi riduce il rischio che tutte le chiavi (e pertanto i dati) verranno perso o eliminati. Microsoft fornisce con autorità unicamente tramite l'eliminazione della chiave di disponibilità. Per impostazione predefinita, nessun presso Microsoft può accedere alla chiave disponibilità: è accessibile solo dal codice del servizio Office 365.
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>Quanti criteri di crittografia dei dati (DEPs) è possibile creare?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype per le aziende:** È possibile creare fino a 50 DEPs. 
  
 **SharePoint Online e OneDrive for Business:** Una protezione esecuzione programmi si applica ai dati in un'unica posizione geografica, denominato anche un livello geografico. Se si utilizza la funzionalità multi-geo di Office 365, è possibile creare una protezione esecuzione programmi per ogni livello geografico. Se non si utilizza multi-geo, è possibile creare una protezione esecuzione programmi.
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>È possibile assegnare un criterio di crittografia dei dati prima della migrazione di una cassetta postale nel cloud?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Sì. È possibile utilizzare il cmdlet di Windows PowerShell Set-MailUser per assegnare un criterio di crittografia dei dati (DEP) all'utente prima della migrazione della cassetta postale a Office 365. A tale scopo, il contenuto della cassetta postale verrà crittografato tramite programmi assegnato come la migrazione di contenuto. Può essere più efficiente rispetto all'assegnazione di una protezione esecuzione programmi dopo che la cassetta postale è già stata eseguita la migrazione. e quindi in attesa per la crittografia venga eseguita, può richiedere ore o eventualmente diversi giorni. 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>Come verificare che viene attivata la crittografia con chiave cliente e Office 365 ha terminato la crittografia con chiave di clienti?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype per le aziende:** È possibile [connettersi a Exchange Online tramite remote PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) e quindi utilizzare il cmdlet **[Get-MailboxStatistics]** per ciascuna cassetta postale che si desidera controllare. Nell'output del cmdlet Get-MailboxStatistics, la proprietà _IsEncrypted_ restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** in caso contrario. Se la cassetta postale è crittografata, il valore restituito per la proprietà _DataEncryptionPolicyID_ è il GUID della protezione esecuzione programmi con cui verrà crittografata alla cassetta postale. Per ulteriori informazioni sull'esecuzione di questo cmdlet, vedere [Get-MailboxStatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx) e l'utilizzo di PowerShell con Exchange Online. 
  
Se le cassette postali non sono crittografate dopo aver atteso 72 ore dal momento in cui è assegnato i programmi, avviare uno spostamento delle cassette postali. Per ottenere questo risultato, [connessione a Exchange Online tramite remote PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) , utilizzare il cmdlet New-MoveRequest e specificare l'alias della cassetta postale nel modo seguente: 
  
```
New-MoveRequest <alias>
```

 **SharePoint Online e OneDrive for Business:** È possibile [connettersi a PowerShell per SharePoint Online](https://technet.microsoft.com/en-us/library/fp161372.aspx)e quindi utilizzare il cmdlet **[Get-SPODataEncryptionPolicy]** per verificare lo stato del tenant. Il * * _stato_* * restituirà un valore pari **registrato** se è attivata la crittografia chiave cliente e tutti i file in tutti i siti sono stati crittografati. Se la crittografia è ancora in corso, questo cmdlet fornisce informazioni su quale percentuale di siti è stata completata. 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>Se desidera passare a un diverso set di chiavi, quanto tempo è necessario per il nuovo set di chiavi per proteggere i dati?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype per le aziende:** È possibile richiedere fino a 72 ore per la protezione di una cassetta postale in base a una nuova crittografia criteri (DEP, Data) dal momento in cui che la nuova Protezione esecuzione programmi viene assegnato alla cassetta postale. 
  
 **SharePoint Online e OneDrive for Business:** È possibile richiedere fino a quattro ore per ricrittografare il tenant intero dopo che è stata assegnata una nuova chiave. 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>I dati esistenti memorizzati senza crittografia in qualsiasi momento durante la decrittografia o crittografata con chiave clienti?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. I dati vengono crittografati sempre statici nel servizio di Office 365 con BitLocker e DKM. Per ulteriori informazioni, vedere "protezione, Privacy e informazioni sulla conformità per Office 365" e [come Exchange Online viene protetto tramite segreti il messaggio di posta elettronica](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376).
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>Se non desidera non è più utilizzare chiavi di crittografia gestite cliente, è possibile passare alle chiavi gestito Microsoft?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype per le aziende:** Non ancora. Questo sarà supportato dopo la crittografia del servizio in Office 365 con i tasti gestiti Microsoft che è stata implementata in generale. Si prevede di distribuire questo nel servizio dopo aver è rilasciare la crittografia del servizio con clienti chiave. 
  
 **SharePoint Online e OneDrive for Business:** Sì. È possibile scegliere di tornare a utilizzare chiavi di Microsoft Management separatamente per ogni livello geografico (se si utilizza la funzionalità multi-geo) o per tutti i dati in caso di un singolo livello geografico. 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>Se perdono i tasti, quanto tempo è necessario ripristinare la disponibilità dei servizi con la chiave di ripristino?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype per le aziende:** Dopo aver chiamato utilizzare il tasto di disponibilità, le cassette postali è accessibile in pochi minuti. 
  
 **SharePoint Online e OneDrive for Business:** Questa operazione è proporzionale al numero di siti che presenti. Dopo aver chiamato Microsoft per l'utilizzo della chiave di disponibilità, sarà completamente online all'interno di circa quattro ore. 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>Come viene utilizzata la chiave di disponibilità con Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Esistono tre modi che viene utilizzata la chiave di disponibilità con Exchange Online:
  
- Servizio disponibilità - nel caso in cui le chiavi Azure chiave cassaforte non sono raggiungibili.
    
- Operazioni avviate dal codice del servizio Office 365, ad esempio la creazione dell'indice di ricerca o spostamenti delle cassette postali.
    
- Ripristinare da perdita chiave -, ad esempio la perdita di entrambe le chiavi Azure chiave cassaforte associate a un singolo Protezione esecuzione programmi.
    
 **Con la chiave di disponibilità per la disponibilità dei servizi in caso di chiavi Azure chiave cassaforte non raggiungibile.**
  
Office 365 utilizza la chiave di disponibilità sia la disponibilità del servizio e il ripristino da uno stato di chiave cliente per Exchange Online. Esiste una gerarchia di chiavi utilizzate dalla chiave cliente. Nella figura seguente è illustrata la gerarchia.
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Se entrambe le chiavi Azure chiave cassaforte di un singolo crittografia criteri (DEP, Data) non sono disponibili, Office 365 è possibile utilizzare la disponibilità tasto per passare a un nuovo programmi Office 365 determina se utilizzare la chiave di disponibilità per la disponibilità del servizio in modo diverso a seconda se un attività dall'utente, ad esempio, quando un utente scarica posta elettronica per il client di Outlook o un'attività ha avviato sistema, ad esempio l'indicizzazione del contenuto delle cassette postali o per le ricerche di eDiscovery, attivato il processo.
  
Office 365 segue questo processo in risposta alle azioni dall'utente per determinare se utilizzare la chiave di disponibilità per cassette postali degli utenti:
  
1. Office 365 legge la protezione esecuzione programmi a cui è assegnata alla cassetta postale per determinare la posizione delle chiavi del due cliente cassaforte chiave Azure.
    
2. Office 365 in modo casuale uno dei tasti di due analisi sceglie tra la protezione esecuzione programmi e invia una richiesta a Azure chiave Vault per annullare la chiave di protezione esecuzione programmi utilizzando la chiave di clienti.
    
3. Se la richiesta per annullare la protezione esecuzione programmi della chiave tramite la chiave cliente ha esito negativo e restituirà un errore, Office 365 invia una seconda richiesta di Azure chiave cassaforte, questa volta per indicare l'utilizzo di alternativo chiave cliente (secondo).
    
4. Se la seconda richiesta per annullare la chiave di protezione esecuzione programmi utilizzando il cliente chiave si verifica un errore e restituisce un errore, Office 365 esamina i risultati di entrambe le richieste:
    
  - Se l'esame determina che gli errori non riflettono un'azione esplicita per un'identità di clienti, Office 365 utilizza la chiave di disponibilità per decrittografare la chiave di protezione esecuzione programmi. La chiave di protezione esecuzione programmi viene quindi utilizzata per decrittografare la chiave della cassetta postale e completare la richiesta dell'utente.
    
    In questo caso, cassaforte chiave Azure è non è possibile rispondere o non raggiungibile per qualunque motivo. Office 365 non avendo la possibilità di determinare se i clienti sono intenzionalmente revocato accesso alle chiavi.
    
  - Se l'esame indica azione intenzionale è stato escluso il rendering cliente chiavi non è disponibile, quindi non verrà utilizzata la chiave di disponibilità, la richiesta dell'utente ha esito negativo e l'utente riceve un messaggio di errore, ad esempio errori di accesso.
    
    In questo caso, il cliente è a conoscenza che è interessato service e la condizione della chiave di analisi non è integro. Ad esempio, se un cliente utilizza un singolo Protezione esecuzione programmi per tutte le cassette postali nell'organizzazione, il cliente può registrano un errore diffuso dove gli utenti non possono accedere alle cassette postali. In questo modo che quando entrambe le chiavi dei clienti sono integro, il cliente viene informato della necessità di risolvere il problema e ripristinare il servizio in uno stato integro.
    
 **Con la chiave di disponibilità per le azioni avviate dal codice del servizio Office 365.**
  
Codice di Office 365 service sempre dispone di un token di accesso valido e non è bloccato. Pertanto, fino a quando non è stata eliminata la chiave di disponibilità, può essere utilizzato per le azioni avviate da, o interna al codice del servizio Office 365, ad esempio la creazione dell'indice di ricerca o lo spostamento delle cassette postali.
  
 **Con la chiave di disponibilità per recuperare da perdita di chiave.**
  
È possibile utilizzare il tasto di disponibilità per recuperare dalla perdita di entrambe le chiavi Azure chiave cassaforte associati DEP stesso, come descritto in risposta alla voce di domande frequenti "se vengono eliminati i tasti, com'è possibile recuperare?".
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>Il tasto disponibilità utilizzo con SharePoint Online e OneDrive for Business?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

SharePoint Online e OneDrive per l'architettura di Business e l'implementazione chiave chiave cliente e disponibilità sono diversi da Exchange Online e Skype per le aziende.
  
Quando si sposta un cliente alle chiavi gestiti clienti, Office 365 crea una chiave di livello intermedia specifiche del tenant (TIK). Office 365 consente di crittografare i TIK due volte, una volta a ciascuno dei tasti dei clienti e li archivia le due versioni crittografate il TIK. Vengono archiviate solo le versioni della TIK crittografate e un TIK possono essere decrittografati solo con i tasti dei clienti. Il TIK viene quindi utilizzato per crittografare le chiavi del sito, che vengono quindi utilizzate per crittografare le chiavi blob. Gli oggetti BLOB se stessi vengono crittografate e archiviate nel servizio di archiviazione Blob di Microsoft Azure.
  
Office 365 segue questo processo per accedere a un oggetto blob con i dati dei clienti file:
  
1. Decrittografare TIK con la chiave di clienti.
    
2. Utilizzare TIK crittografato per decrittografare una chiave del sito.
    
3. Utilizzare il tasto sito crittografato per decrittografare una chiave blob.
    
4. Utilizzare il tasto blob crittografato per decrittografare il blob.
    
Durante la decrittografia di un TIK, Office 365 rilascia due richieste decrittografia Azure chiave cassaforte con un offset leggero. La prima occorrenza per terminare la offre un sistema di risultati, annullando la richiesta di altre.
  
Nel caso in cui il cliente perde l'accesso alle chiavi clienti, Office 365 crittografa il TIK con una chiave di disponibilità e questa tabella sono archiviate e TIKs crittografati con ogni codice cliente. TIK crittografati con la chiave di disponibilità viene utilizzato solo quando il cliente chiama Microsoft per integrare il percorso di recupero quando si è più possibile accedere alle relative chiavi o accidentalmente.
  
Per motivi di scalabilità e disponibilità, TIKs decrittografati vengono memorizzati nella cache in una cache di memoria di durata limitata. Due ore prima di una cache TIK è impostata per scadere, Office 365 tenta di decrittografare ogni TIK. Decrittografia il TIKs estende la durata della cache. Se la decrittografia TIK ha esito negativo per una grande quantità di tempo, Office 365 genera un avviso per notificare engineering prima della scadenza della cache. Solo se il cliente chiama Microsoft Office 365 verrà avviata l'operazione di ripristino, che comporta la decrittografia di che TIK con la chiave di disponibilità archiviate in Microsoft archivio segreto e on-boarding tenant usando ancora decrittografato TIK e un nuovo set tasti di Azure chiave cassaforte fornito dal cliente.
  
A partire da oggi, la catena di crittografia e decrittografia di SharePoint Online dati archiviati in dell'archivio blob Azure, ma non elementi di elenchi di SharePoint Online o dei metadati archiviate nel database di SQL file interessato chiave cliente. Office 365 non utilizza la disponibilità chiave per SharePoint Online o OneDrive for Business diverso da quello descritto in precedenza, ovvero cliente ha avviato. Risorse umana accesso ai dati dei clienti è protetto da archivio protetto cliente.
  
## <a name="how-is-customer-key-licensed"></a>Come chiave cliente dispone di una licenza?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Chiave cliente è disponibile in Office 365 Enterprise Suite, "E5" e SKU di conformità avanzate. Inoltre, clienti devono inoltre acquistare licenze appropriato per l'utilizzo di Azure chiave cassaforte.
  
Ogni utente beneficiano chiave cliente deve essere concesso in licenza se desiderano chiave cliente.
  
SharePoint Online, l'amministratore di Office 365 che configura chiave cliente deve inoltre essere concessi in licenza, per eseguire la procedura di installazione. Inoltre, gli utenti che sono beneficiano la caratteristica devono essere concessi in licenza: include il proprietario del sito e agli utenti di accedere a file in uno o più siti che vengono crittografati utilizzando la chiave cliente. Gli utenti esterni non sono necessario disporre della licenza per accedere ai file di uno o più siti che vengono crittografati utilizzando la chiave cliente.
  
Per Exchange Online, le cassette postali "user" e "utente di posta elettronica" cassette postali deve essere concesso in licenza. Non tutti gli altri, ad esempio le cassette postali condivise, è necessario disporre di una licenza per clienti chiave. Per verificare che la cassetta postale di Exchange Online viene concesso in licenza correttamente, eseguire il cmdlet seguente:
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

Se la stringa BPOS_S_EquivioAnalytics esiste, la cassetta postale viene concesso in licenza in modo corretto. In caso contrario, è necessario applicare la licenza appropriata per utilizzare la funzionalità chiave cliente per questa cassetta postale.
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>È possibile attivare chiave dei clienti per una sottoscrizione di prova?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Per definizione, sottoscrizioni di valutazione sono a breve termine. Le chiavi di crittografia che sono ospitate in sottoscrizioni di valutazione possono andare perdute alla fine della durata di prova. Poiché Microsoft non è e non impedisce ai clienti di inserire i dati dei clienti importanti di sottoscrizioni di valutazione, è vietato l'utilizzo di chiave cliente con sottoscrizioni di valutazione.
  
## <a name="how-much-will-using-customer-key-cost"></a>La quantità verrà utilizzando costo chiave cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Oltre alle licenze necessarie per la chiave cliente, i clienti comporta un costo per l'utilizzo del tasto cassaforte. [Ulteriori informazioni sui prezzi di Azure chiave cassaforte](https://azure.microsoft.com/en-us/pricing/details/key-vault/) viene descritto il modello di costo e assistere stima. Non è possibile prevedere il costo esatto che causeranno ai clienti perché i modelli di utilizzo variano. Esperienza dimostra che il costo è molto ridotto e in genere si trova all'interno dell'intervallo di $0,002 a $0,005 per utente al mese e il costo dei tasti eseguito il modulo di sicurezza hardware. Il costo varia in base alla configurazione di registrazione scelta dal cliente e la quantità di spazio di archiviazione Azure utilizzato per i registri di Azure chiave cassaforte. 
  
## <a name="for-more-information"></a>Per altre informazioni
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Per iniziare con clienti chiave, vedere [il controllo dei dati in Office 365 con chiave cliente](controlling-your-data-using-customer-key.md).
  

