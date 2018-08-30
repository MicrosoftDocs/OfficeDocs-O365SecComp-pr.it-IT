---
title: Panoramica dei criteri di conservazione
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 4/3/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 9c3b1d52-40ce-4ba3-a520-9ae0be15538a
description: Per rispettare normative settore o ai criteri interni, le organizzazioni desiderano mantenere il contenuto per un determinato periodo di tempo. Con un criterio di conservazione in Office 365, è possibile mantenere il contenuto nei siti, le cassette postali e cartelle pubbliche tempo indeterminato o per un determinato periodo di tempo. È inoltre possibile filtrare il contenuto che verrà mantenuto fornendo le parole chiave o un intervallo di date per limitare i risultati.
ms.openlocfilehash: a26b85a563dd0e6f9ed8a70bfe9a310fc89a50f2
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272461"
---
# <a name="overview-of-preservation-policies"></a>Panoramica dei criteri di conservazione

> [!IMPORTANT]
> Se si sta utilizzando un criterio di conservazione, tale criterio è stato convertito automaticamente in un criterio di conservazione, che corrisponde a una nuova funzionalità che funzionalità offerte un criterio di conservazione e altro ancora. Il criterio di conservazione continuerà a funzionare e conservare il contenuto senza richiedere alcuna modifica dall'utente. Questi criteri sono disponibili nella pagina **conservazione** nel titolo &amp; centro conformità. Per ulteriori informazioni, vedere [Dov'ai criteri di conservazione?](retention-policies.md#what-happened-to-preservation-policies)
  
Per rispettare normative settore o ai criteri interni, le organizzazioni desiderano mantenere il contenuto per un determinato periodo di tempo. Con un criterio di conservazione in Office 365, è possibile mantenere il contenuto nei siti, le cassette postali e cartelle pubbliche tempo indeterminato o per un determinato periodo di tempo. È inoltre possibile filtrare il contenuto che verrà mantenuto fornendo le parole chiave o un intervallo di date per limitare i risultati.
  
Ad esempio, è possibile mantenere il contenuto in siti che appartengono al reparto vendite per sette anni e cassette postali specifiche e restringere ulteriormente l'ambito del criterio che indica che si desidera mantenere solo contenuto del ultimi due anni che contiene un oggetto specifico nome del client.
  
Quando il contenuto è soggetta a un criterio di conservazione, gli utenti possono continuare a modificare e lavorare con il contenuto come se non vengono apportate modifiche perché i contenuti conservati sul posto nella posizione originale. Ma se un utente modifica o Elimina il contenuto soggetti al criterio, in una posizione sicura dove viene conservata mentre è attivo il criterio viene salvata una copia.
  
Infine, alcune organizzazioni potrebbe essere necessario rispettare regole definite da organismi normativi, ad esempio Securities and Exchange Commission (SEC) regola 17 bis-4, che richiede che dopo un criterio di conservazione è attivato, non possono essere disattivata o rese meno restrittiva. Per soddisfare questo requisito, è possibile utilizzare il blocco di conservazione. Dopo che un criterio di blocco, nessuno, tra cui l'amministratore, ovvero possibile disattivare il criterio o meno restrittive.
  
Creare e gestire i criteri di conservazione nella pagina conservazione in Office 365 Security &amp; centro conformità.
  
![Pagina conservazione in Office 365 Security &amp; centro conformità](media/edb2e228-efff-4619-89d1-8665b5f38639.png)
  
> [!NOTE]
> Per includere una cassetta postale di Exchange Online in un criterio di conservazione, la cassetta postale deve essere assegnata una licenza di Exchange Online piano 2. Se una cassetta postale viene assegnata una licenza di Exchange Online piano 1, è necessario assegnare una licenza separata archiviazione Exchange Online da includere in un criterio di conservazione. 
  
## <a name="how-a-preservation-policy-works-with-content-in-place"></a>Funzionamento dei criteri di conservazione con contenuti in locale

Quando si include un sito, delle cassette postali o cartelle pubbliche in un criterio di conservazione, il contenuto rimane nella posizione originale. Gli utenti possono continuare a lavorare con i documenti o posta, ma una copia del contenuto come viene trovata quando è stata avviata il criterio viene mantenuta. Per i siti, contenuto mantenuto nella libreria di attesa di conservazione. per le cassette postali e cartelle pubbliche, contenuto mantenuto nella cartella elementi ripristinabili. Queste posizioni protette e il contenuto archiviato non sono visibili a molte persone. Con un criterio di conservazione, le persone non sono necessario anche sapere che il contenuto è soggetti al criterio.
  
![Diagramma che mostra il funzionamento dei criteri di conservazione](media/2c1dd82b-84e0-49e0-ab46-d017df297040.png)
  
### <a name="site-content"></a>Contenuti del sito

Un criterio di conservazione viene applicato a livello di un sito. Quando si include un sito in un criterio di conservazione, viene creata una raccolta di attesa di conservazione, se non esiste già. La maggior parte degli utenti non possono visualizzare la raccolta di attesa di conservazione perché è visibile solo ai proprietari della raccolta siti.
  
Se un utente tenta di modificare o eliminare contenuto in un sito in cui è soggetto a un criterio di conservazione, i criteri di verifica innanzitutto se il contenuto del stato modificato in quanto è stato applicato il criterio. Se si tratta della prima modifica poiché è stato applicato il criterio di conservazione, i criteri di copia il contenuto nella raccolta di attesa di conservazione e quindi consentono all'utente di modificare o eliminare il contenuto originale. Si noti che il contenuto del sito può essere copiato nella raccolta di attesa di conservazione, anche se il contenuto non corrisponde al filtro della query utilizzata per il criterio di conservazione.
  
Quindi, un processo timer pulisce la raccolta di archiviazione. Il processo timer viene eseguito periodicamente e confronta tutti i contenuti della raccolta di archiviazione con i filtri utilizzati dai criteri di archiviazione nel sito. A meno che i contenuti non corrispondano ad almeno uno dei filtri, il processo timer elimina definitivamente i contenuti dalla raccolta di archiviazione.
  
Il precedente si applica al contenuto esistente quando viene applicato il criterio di conservazione. Inoltre, qualsiasi nuovo contenuto che ha creato o aggiunti al sito dopo che è stato incluso nel criterio verrà mantenuto dopo l'eliminazione. Nuovo contenuto, tuttavia, non vengono copiato fino al momento della libreria del primo attesa di conservazione che viene modificato, solo quando viene eliminato. Per mantenere le versioni per tutti i file, è necessario attivare il controllo delle versioni, vedere la sezione successiva al controllo delle versioni.
  
### <a name="mailbox-and-public-folder-content"></a>Contenuti delle cassette postali e di cartelle pubbliche

Per quanto riguarda la posta e altri elementi di un utente, i criteri di conservazione vengono applicati a livello di cassetta postale. Per quanto riguarda una cartella pubblica, i criteri di conservazione vengono applicati a livello di cartella, non a livello di cassetta postale. Una cassetta postale e una cartella pubblica utilizzano la cartella Elementi ripristinabili per conservare gli elementi. Solo gli utenti che dispongono delle autorizzazioni di eDiscovery possono visualizzare la cartella Elementi ripristinabili di un altro utente.  
  
Per impostazione predefinita, quando un utente elimina un messaggio da una cartella diversa dalla cartella Posta eliminata, il messaggio viene spostato nella cartella Posta eliminata. Quando una persona Elimina un elemento dalla cartella Posta eliminata, il messaggio viene spostato nella cartella elementi recuperabili e scomparirà dalla visualizzazione dell'utente. Inoltre, una persona soft possibile eliminare un elemento (MAIUSC + CANC) in qualsiasi cartella, che consente di ignorare la cartella Posta eliminata e inserisce l'elemento direttamente nella cartella elementi ripristinabili.
  
Quando una cassetta postale viene inclusa nei criteri di conservazione, gli elementi eliminati vengono spostati nella cartella DiscoveryHold presente all'interno della cartella Elementi ripristinabili. Quando l'assistente della cassetta postale elabora periodicamente la cassetta postale, valuta i messaggi in questa cartella. A meno che i contenuti corrispondano ad almeno uno dei filtri utilizzati dai criteri di conservazione, l'assistente cassette postali elimina definitivamente i contenuti dalla cartella Elementi ripristinabili.
  
La cartella elementi ripristinabili contiene anche una cartella di versioni. Quando un utente tenta di modificare alcune proprietà di un elemento della cassetta postale, ad esempio l'oggetto body, allegati, mittenti e destinatari o data inviato o ricevuto per un messaggio, ovvero una copia dell'elemento originale viene salvata la cartella delle versioni prima del commit della modifica. Ciò si verifica per ogni modifica successiva. Dopo avere rimosso il criterio di conservazione, le copie nella cartella di versioni vengono rimossi dall'Assistente delle cassette postali.
  
### <a name="where-a-preservation-policy-is-stored"></a>Luogo di archiviazione dei criteri di conservazione

Quando si crea un criterio di conservazione, vengono archiviata centralmente in sicurezza &amp; centro conformità e quindi distribuiti per le diverse origini di contenuto che include il criterio, ad esempio siti, le cassette postali e cartelle pubbliche.
  
Dopo aver distribuito i criteri di conservazione per le origini dei contenuti, i criteri funzionano esattamente come un'archiviazione sul posto di eDiscovery. Per ulteriori informazioni relative alle archiviazioni sul posto, vedi:
  
- [Panoramica di eDiscovery e in-place dell'archiviazione](https://go.microsoft.com/fwlink/p/?LinkID=404352) (SharePoint Online) 
    
- [Sul posto archiviazione e conservazione per controversia legale](https://go.microsoft.com/fwlink/p/?LinkID=404353) (Exchange Online) 
    
- [Cartella elementi ripristinabili](https://go.microsoft.com/fwlink/p/?LinkID=404354) (Exchange Online) 
    
### <a name="preservation-policy-vs-ediscovery-hold"></a>Criteri di conservazione e archiviazione di eDiscovery

Anche se queste funzionalità conservare contenuto, queste funzionalità non devono essere confuso dal momento che per scopi diversi:
  
- **Se si desidera mantenere il contenuto come parte di un requisito di conservazione, utilizzare un criterio di conservazione.** Ad esempio, se si desidera mantenere il contenuto da sette anni come parte del piano di conservazione, utilizzare un criterio di conservazione. Un criterio di conservazione può mantenere il contenuto per un periodo di tempo specifico e alla fine del periodo di tempo specificato, il contenuto automaticamente rilasciati dal criterio. I criteri possono anche essere bloccati in modo che non consente di disattivare il criterio o meno restrittive. Un'esenzione di eDiscovery non può essere bloccato o specificare un periodo di tempo. Inoltre, un criterio di conservazione comunemente ha una durata di anni, mentre un'esenzione di eDiscovery è temporanea e comunemente dura solo la durata di una controversia legale. 
    
    È inoltre possibile creare un criterio di conservazione senza i passaggi aggiuntivi che potrebbero richiedere eDiscovery, ad esempio la creazione dei casi, aggiunta di membri, oppure eseguire contenuto eseguita una ricerca.
    
- **Se conservare contenuto come parte di un requisito legale o eDiscovery, è necessario utilizzare un'esenzione di eDiscovery.** Ad esempio, se è necessario conservare contenuto in posizioni specifiche come parte di una richiesta legale, utilizzare un'esenzione di eDiscovery. Di eDiscovery, il contenuto pertinente a un caso è in genere riservato o privilegiati, in modo diversi casi possono essere limitati ai diversi membri. Inoltre, eDiscovery supporta ricerche del contenuto salvate, visualizzato in anteprima, analizzate con eDiscovery avanzate o sono esportati i risultati. 
    
    A differenza di un criterio di conservazione, un'esenzione di eDiscovery è possibile specificare un periodo di tempo: un'esenzione di eDiscovery è attiva fino a quando non si disattivarlo o eliminarlo. Inoltre, non è bloccato un'esenzione di eDiscovery.
    
## <a name="how-a-preservation-policy-works-with-document-versions-in-a-site"></a>Funzionamento dei criteri di conservazione con le versioni del documento in un sito

Un criterio di conservazione non mantiene automaticamente tutte le versioni di un documento in un sito. A tale scopo, è necessario attivare il controllo delle versioni per le raccolte documenti nel sito. Per ulteriori informazioni, vedere [abilitare e configurare il controllo delle versioni per un elenco o raccolta](https://go.microsoft.com/fwlink/p/?LinkID=404350).
  
Se un documento viene eliminato da un sito vengono conservati e controllo delle versioni è attivato per la raccolta, tutte le versioni del documento eliminato vengono conservate. 
  
Se non viene attivato il controllo delle versioni di documenti e un elemento è soggetto a criteri di conservazione diversi, la versione viene mantenuta è quello corrente per ogni criterio di conservazione ha effetto. Ad esempio, se più recente quando il sito viene mantenuto la prima volta e versione 51 è l'ultima versione 27 di un elemento quando il sito viene mantenuto la seconda volta, versioni 27 e 51 vengono conservate.
  
## <a name="filtering-a-preservation-policy"></a>Filtraggio dei criteri di conservazione

È possibile restringere i contenuti soggetti a criteri di conservazione aggiungendo parole chiave o un intervallo di date a criteri. 
  
![Utilizzo di parole chiave e intervalli di date come filtri durante la creazione di un criterio di conservazione](media/603cef40-8f7c-4140-956f-28c092273582.png)
  
### <a name="filter-by-using-keywords"></a>Filtrare utilizzando parole chiave

Un criterio di conservazione supporta Keyword Query Language (KQL). Ad esempio, è possibile utilizzare operatori di base like AND e OR ed è possibile eseguire una ricerca in "marketing NEAR(30) wingtip" identifica i risultati in cui è "wingtip" all'interno di 30 caratteri di "marketing". Una query con parole chiave consente di identificare e mantenere solo il contenuto pertinente.
  
### <a name="filter-by-using-a-date-range"></a>Filtrare utilizzando un intervallo di date

È possibile filtrare i criteri di conservazione in modo che preservino soltanto i contenuti compresi all'interno di un determinato intervallo di date. Per quanto riguarda i messaggi, la data si riferisce a quella di ricezione, mentre per quanto riguarda i documenti e i siti, la data si riferisce a quella di modifica. Ciò significa che puoi conservare i contenuti che includono la posta ricevuta e i documenti modificati all'interno di un determinato intervallo di date oppure prima o dopo la sua data di inizio o di fine.
  
## <a name="preserving-content-for-a-specific-period-of-time"></a>Conservare i contenuti per un determinato periodo di tempo

Grazie ai criteri di conservazione, è possibile conservare i contenuti per un tempo indeterminato o per un numero di giorni, mesi o anni specifico. Considerare che la durata relativa alla conservazione dei contenuti viene calcolata in base alla durata dei contenuti, non dal momento di creazione del criterio di conservazione. 
  
Ad esempio, se si desidera mantenere il contenuto in un sito da sette anni e un documento in tale sito non è stato modificato in sei anni, il documento verrà mantenuto per anno diversa solo se non è stato modificato. Se il documento viene modificato nuovamente, la validità del documento viene calcolata dalla nuova data ultima modifica e verrà mantenuta per altri sette anni.
  
In modo analogo, se vuoi conservare contenuti in una cassetta postale per sette anni e un messaggio è stato inviato sei anni fa, il messaggio verrà conservato soltanto per un anno a meno che la data di ricezione viene modificata. In questo caso, viene conservata una nuova versione del messaggio originale nella cartella Elementi ripristinabili e la durata del messaggio viene calcolata dalla nuova data di ricezione e verrà conservato per altri sette anni.
  
![Impostazione della durata per un nuovo criterio di conservazione](media/455aac78-4c29-4dbb-93a2-b431b99002d9.png)
  
## <a name="locking-a-preservation-policy"></a>Blocco dei criteri di conservazione

Alcune organizzazioni potrebbero essere necessario rispettare regole definite da organismi normativi, ad esempio Securities and Exchange Commission (SEC) regola 17 bis-4, che richiede che dopo un criterio di conservazione è attivato, non possono essere disattivata o rese meno restrittiva. Con il blocco di archiviazione, è possibile bloccare i criteri in modo che nessun, tra cui l'amministratore, ovvero possibile disattivare il criterio o meno restrittive.
  
Dopo che un criterio di blocco, nessuno disattivarlo o rimuovere contenuto dal criterio. E non è possibile modificare o eliminare il contenuto soggetti al criterio durante il periodo di conservazione. Dopo il criterio di stato bloccato, gli unici modi è possibile modificare il criterio di conservazione sono dall'aggiunta di contenuto o l'estensione della durata. Un criterio di blocco può essere aumentato o estese, ma non può essere ridotto o disattivato.
  
Prima di bloccare un criterio di conservazione, è essenziale di comprendere i requisiti di conformità dell'organizzazione e non bloccare un criterio finché non si è certi che è necessario.
  
![Opzione per attivare la protezione dell’archiviazione](media/cf9cc070-ddfb-469c-a47e-f88005a82fe4.png)
  
## <a name="turning-off-a-preservation-policy"></a>La disattivazione di un criterio di conservazione

Se non si desidera bloccare il criterio di conservazione, è possibile rilasciare in qualsiasi momento, anche prima del termine del periodo di tempo specificato dal criterio. A tale scopo, solo consente di disattivare il criterio.
  
![Opzione per la disattivazione di un criterio di conservazione nella pagina conservazione del titolo &amp; centro conformità](media/fdb44455-da01-4480-8fa6-0e3b29b1f535.png)
  
Tuttavia, è possibile eliminare un criterio di conservazione mentre ancora attivo del criterio. Per eliminare un criterio di conservazione, disattivare e quindi eliminare il criterio.
  
Dopo la disattivazione di un criterio di conservazione, tutti gli elementi soggetti a quei criteri in attesa di conservazione raccolta o cartella elementi recuperabili sono quindi idonei per il processo di pulizia standard descritto in precedenza. Si noti che questo significa che gli elementi rilasciati da un criterio non vengono eliminati immediatamente, al contrario, rimangono in attesa di conservazione raccolta o cartella elementi ripristinabili fino a quando non rimuove periodicamente il processo di raccolta o cartella.
  
## <a name="using-preservation-policies-with-retention-policies-and-document-deletion-policies"></a>Utilizzo dei criteri di conservazione con criteri di gestione e criteri di eliminazione dei documenti

I criteri di conservazione assicurano che i contenuti siano mantenuti per un periodo indeterminato o per un periodo specifico, mentre i criteri di gestione per una cassetta postale e i criteri di eliminazione dei documenti per un sito assicurano che i contenuti siano eliminati dopo un determinato periodo di tempo. Se devi conservare contenuti per un certo periodo di tempo, puoi usare i criteri di conservazione insieme ai criteri di gestione o di eliminazione. 
  
### <a name="site-content"></a>Contenuti del sito

Per un sito, puoi usare i criteri di conservazione insieme ai criteri di eliminazione dei documenti. Ad esempio, puoi conservare i documenti per i 5 anni successivi a una modifica, quindi impostare i criteri di eliminazione per cancellare i documenti dopo 5 anni dalla data di modifica.
  
Se un criterio di eliminazione del documento consente di eliminare il contenuto è soggetta a un criterio di conservazione, verrà mantenuto ancora il contenuto nella raccolta di attesa di conservazione. Ad esempio, se un criterio di conservazione consente di mantenere il contenuto per due anni, ma un criterio di eliminazione del documento consente di eliminare il contenuto dopo un anno, qualsiasi contenuto che viene eliminato verrà comunque mantenuto. Per ulteriori informazioni, vedere [Panoramica di criteri di eliminazione dei documenti](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5).
  
### <a name="mailbox-content"></a>Contenuto delle cassette postali

Per una cassetta postale, è possibile combinare un criterio di conservazione con un criterio di conservazione con un tag dei criteri predefiniti singolo. Ad esempio, potrebbe conservare gli elementi della cassetta postale da sette anni e quindi configurare un criterio di conservazione per eliminarli sette anni dopo che sono stati ricevuti (per i messaggi) o create (per gli elementi che non vengono inviati, ad esempio le note). Il criterio di conservazione per accertarsi che gli elementi ottenere eliminati vengono mantenuti per almeno durata specificata, mentre il criterio di conservazione garantisce che gli elementi della cassetta postale vengono eliminati alla fine di tale periodo. Per ulteriori informazioni, vedere [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkID=404351).
  
## <a name="permissions"></a>Autorizzazioni

Membri del team di conformità che utilizzeranno la sicurezza &amp; centro conformità per creare criteri di conservazione necessarie autorizzazioni per il:
  
-  Protezione di Office 365 &amp; centro conformità 
    
- Siti con contenuti da mantenere
    
- Cassette postali con contenuti da mantenere
    
### <a name="office-365-security-amp-compliance-center"></a>Protezione di Office 365 &amp; centro conformità

Come amministratore tenant, che si desidera fornire accesso altre persone e responsabili della conformità per la protezione &amp; centro conformità, senza fornire tutte le autorizzazioni di un amministratore tenant. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).
  
### <a name="sites"></a>Siti

I membri del team di conformità che creano i criteri di conservazione necessitano delle autorizzazioni per le raccolte di siti alle quali verranno applicati i criteri. Inoltre, se i responsabili della conformità creano anche i criteri di eliminazione dei documenti, necessitano delle autorizzazioni per la raccolta siti del Centro criteri di conformità dove vengono creati e archiviati i criteri di eliminazione dei documenti. È consigliabile:
  
1. Creare un gruppo di sicurezza contenente tutti gli utenti del centro di criteri di conformità, è molto probabile che il team di gestione criteri di conformità. Per ulteriori informazioni, vedere [Gruppi di sicurezza Manage Mail-Enabled](https://go.microsoft.com/fwlink/p/?LinkID=404345) . 
    
2. Nell'interfaccia di criteri di conformità, aggiungere il gruppo di protezione al gruppo di proprietari della raccolta siti. Per ulteriori informazioni, vedere [le autorizzazioni per gli amministratori della raccolta siti](https://go.microsoft.com/fwlink/p/?LinkID=404346) . 
    
3. In ogni raccolta siti a cui è necessario assegnare i criteri di conservazione, aggiungere il gruppo di sicurezza al gruppo di visitatori della raccolta siti (autorizzazioni di lettura).
    
### <a name="mailboxes-and-public-folders"></a>Cartelle pubbliche e cassette postali

Per applicare un criterio di conservazione a una cassetta postale, i responsabili della conformità devono almeno disporre delle autorizzazioni di lettura per la cassetta postale. 
  
Per applicare un criterio di conservazione a una cartella pubblica, i responsabili della conformità devono almeno disporre delle autorizzazioni di lettura per tutte le cartelle pubbliche.
  

