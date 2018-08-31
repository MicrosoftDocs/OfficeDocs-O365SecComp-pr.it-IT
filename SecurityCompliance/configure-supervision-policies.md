---
title: Configurare i criteri di supervisione per l’organizzazione
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Impostare criteri di supervisione revisione per acquisire le comunicazioni di dipendenti per la revisione.
ms.openlocfilehash: a919d65f5c0967a44ac12b7e02d477dac2113704
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531477"
---
# <a name="configure-supervision-policies-for-your-organization"></a>Configurare i criteri di supervisione per l’organizzazione

Utilizzare criteri di supervisione per acquisire le comunicazioni di dipendenti per un esame dai revisori interni o esterni.
  
> [!NOTE]
> Utilizzo dei criteri di supervisione richiede una sottoscrizione a Office 365 E5 per l'organizzazione. Se non sono dial plan e desidera provare supervisione, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Eseguire la procedura seguente per configurare e utilizzare supervisione nella propria organizzazione Office 365: 
  
- [Impostare i gruppi di supervisione](configure-supervision-policies.md#exampledist)
    
    Prima di iniziare a utilizzare supervisione, determinare che verranno loro comunicazioni rivisto e che verranno eseguite le valutazioni. Se si desidera iniziare a utilizzare solo pochi utenti per verificare il funzionamento di supervisione, è possibile ignorare l'impostazione dei gruppi per il momento.
    
- [Rendere disponibile nell'organizzazione supervisione](configure-supervision-policies.md#SRavailable)
    
    Aggiungersi al gruppo di ruoli supervisione esaminare in modo che è possibile impostare criteri. Chiunque disponga di questo ruolo assegnato può accedere alla pagina di **supervisione** in **Dati di Governance** della protezione &amp; centro conformità. 
    
- [Impostare i criteri di supervisione](configure-supervision-policies.md#setupsuper)
    
    Criteri di supervisione verrà creata nella protezione &amp; centro conformità. Questi criteri definiscono le comunicazioni sono soggetti a revisione all'interno dell'organizzazione e consente di specificare che deve eseguire le revisioni. Comunicazioni includono posta elettronica, nonché communications piattaforma 3rd parti (ad esempio, Facebook, Twitter e così via)
    
- [Utilizzare Outlook web app per controllare le comunicazioni identificate da un criterio di supervisione](configure-supervision-policies.md#UseOutlook)
    
    Il componente aggiuntivo per la supervisione consente revisori accedere alle funzionalità di supervisione adatto all'interno di Outlook web app in modo che possano valutare e classificare ciascun elemento. Supporto per la versione desktop di Outlook è disponibile a breve.
    
- **Eseguire il report di supervisione**
    
    Utilizzare i rapporti di supervisione esaminare l'attività di verifica a livello di criteri e revisore. Per ogni criterio, è inoltre possibile visualizzare le statistiche live sullo stato corrente dell'attività di verifica. Per ulteriori informazioni, vedere [supervisione reports](supervision-reports.md).
    
## <a name="set-up-groups-for-supervision"></a>Impostare i gruppi di supervisione
<a name="exampledist"> </a>

 Quando si crea un criterio di supervisione, se ne determinerà che avranno le proprie comunicazioni esaminate e che verranno eseguite le valutazioni. Nel criterio, si utilizzerà indirizzi di posta elettronica per identificare i singoli utenti o gruppi di utenti. Per semplificare l'installazione, creare gruppi per gli utenti che dovranno le comunicazioni esaminata e per gli utenti che verranno controllare le comunicazioni. Se si sta utilizzando gruppi, potrebbe essere necessario diverse, ad esempio, se si desidera monitorare le comunicazioni tra i due gruppi distinti di persone o se si desidera specificare un gruppo a cui non è continui a essere controllati. Per informazioni dettagliate sul funzionamento, vedere [gruppi di distribuzione di esempio](configure-supervision-policies.md#GroupExample) . 
  
Per controllare le comunicazioni tra o all'interno dei gruppi nell'organizzazione, impostare i gruppi di distribuzione nell'interfaccia di amministrazione di Exchange (accedere a **destinatari** \> **gruppi**). Per ulteriori informazioni sulla configurazione di gruppi di distribuzione, vedere [gestire i gruppi di distribuzione](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> È inoltre possibile utilizzare gruppi di distribuzione dinamici o gruppi di protezione per la supervisione se si preferisce. Per decidere se queste si adattino meglio l'organizzazione deve, vedere [gestire i gruppi di protezione abilitati alla posta elettronica](http://go.microsoft.com/fwlink/?LinkId=627033)e [gestire i gruppi di distribuzione dinamico](http://go.microsoft.com/fwlink/?LinkId=627058). 
  
### <a name="example-distribution-groups"></a>Gruppi di distribuzione di esempio
<a name="GroupExample"> </a>

In questo esempio include un gruppo di distribuzione che è stato impostato per un'organizzazione finanziaria denominata Contoso finanziaria internazionale. 
  
In Contoso Financial International, deve essere supervisionato un campionamento delle comunicazioni tra broker negli Stati Uniti. Tuttavia, i responsabili della conformità all'interno del gruppo non richiedono supervisione. In questo esempio, è possibile creare i seguenti gruppi:
  
|**Configurare il gruppo di distribuzione**|**Indirizzo del gruppo (alias)**|**Descrizione**|
|:-----|:-----|:-----|
|Tutti i broker degli Stati Uniti  <br/> |US_Brokers@contoso.com  <br/> |Questo gruppo include gli indirizzi di posta elettronica di tutti i broker degli Stati Uniti che lavorano per Contoso.  <br/> |
|Tutti i responsabili della conformità degli Stati Uniti  <br/> |US_Compliance@contoso.com  <br/> |Questo gruppo include gli indirizzi di posta elettronica per tutti i responsabili della conformità in Usa che lavorano per Contoso. Poiché questo gruppo è un sottoinsieme di tutte le Broker in USA, è possibile utilizzare l'alias per responsabili della conformità esenti dai criteri di supervisione.  <br/> |
   
Nella sezione [impostare i criteri di supervisione](configure-supervision-policies.md#setupsuper) descritto come utilizzare questi gruppi quando si configurano i criteri. 
  
## <a name="make-supervision-available-in-your-organization"></a>Rendere disponibile nell'organizzazione supervisione
<a name="SRavailable"> </a>

Per rendere disponibile come opzione di menu **supervisione** della protezione &amp; centro conformità, deve essere assegnato il ruolo di amministratore di revisione supervisione. 
  
A tale scopo, è possibile aggiungere familiarità con un account membro del gruppo di ruoli supervisione revisione oppure è possibile creare un nuovo gruppo di ruoli.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Aggiungere membri al gruppo di ruoli supervisione revisione

1. Accedere a [https://protection.office.com](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365. 
    
2. In sicurezza &amp; centro conformità, accedere alle **autorizzazioni**.
    
3. Selezionare il gruppo di ruoli **Revisione autorità di controllo** e quindi fare clic sull'icona Modifica. 
    
4. Nella sezione **membri** , aggiungere gli utenti che si desidera gestire supervisione per l'organizzazione. 
    
### <a name="create-a-new-role-group"></a>Creare un nuovo gruppo di ruoli

1. Accedere a [https://protection.office.com](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365. 
    
2. In sicurezza &amp; centro conformità, accedere alle **autorizzazioni** e quindi fare clic su Aggiungi ( **+**).
    
3. Nella sezione **ruoli** , fare clic su Aggiungi ( **+**) e scorrere verso il basso per **Supervisione amministratore revisione**. Aggiungere questo ruolo al gruppo di ruoli.
    
4. Nella sezione **membri** , aggiungere gli utenti che si desidera gestire supervisione per l'organizzazione. 
    
Per ulteriori informazioni sulle autorizzazioni e gruppi di ruoli, vedere [autorizzazioni in Office 365 Security &amp; centro conformità ](permissions-in-the-security-and-compliance-center.md).
  
## <a name="set-up-a-supervision-policy"></a>Impostare i criteri di supervisione
<a name="setupsuper"> </a>

> [!IMPORTANT]
> Prima di creare criteri di supervisione, è innanzitutto necessario rimuovere tutti i criteri di supervisione revisione esistente. 
  
1. Accedere a [https://protection.office.com](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365. 
    
2. In sicurezza &amp; centro conformità, passare a fare clic su **governance dati** \> **supervisione**.
    
    > [!NOTE]
    > La versione precedente della caratteristica potrebbe visualizzare nel riquadro di spostamento sinistro come **revisione supervisione (ritiro breve)**. Questa versione non appena verrà essere deprecata e rimosso. La nuova versione chiamata **supervisione** avverrà il relativo. 
  
3. Fare clic su **Crea** e quindi seguire la procedura guidata per configurare le pagine seguenti del criterio. 
    
### <a name="policy-name-and-description"></a>Descrizione e nome del criterio

Immettere un nome e una descrizione per il criterio. A scopo di esempio, sarà denominato criterio Broker di Contoso US.
  
### <a name="choose-users-to-supervise"></a>Scegliere gli utenti a controllare

- Nella casella **Supervise questi utenti o gruppi** scegliere gli utenti o gruppi di cui si desidera a controllare il cui communications. Utilizzo di esempio per Broker di Contoso Stati Uniti, verrà scelto il gruppo US_Brokers@Contoso.com qui. 
    
- Se si sceglie un gruppo a controllare, è possibile utilizzare la casella **escludere tali utenti** per scegliere i membri del gruppo che sono esenti dalla supervisione. Con l'esempio, si verrà escludere gruppo US_Compliance@Contoso.com qui. 
    
### <a name="choose-communications-to-review"></a>Scegliere communications per la revisione
<a name="CommsToReview"> </a>

Per impostazione predefinita, la condizione **è direzione** viene visualizzata e non possono essere rimosse. Se si desidera definire l'ambito della revisione ulteriormente (ad esempio solo esame del contenuto che contiene alcune parole o frasi), fare clic su **Aggiungi una condizione**. Se necessario, è possibile specificare più condizioni.
  
Le condizioni che si sceglie verranno applicata alle comunicazioni provenienti da origini di posta elettronica sia 3rd parti all'interno dell'organizzazione (come da Facebook o raccolta). Per ulteriori informazioni sull'importazione di terze parti 3rd communications nella propria organizzazione Office 365, vedere [archiviazione dei dati di terze parti in Office 365](https://technet.microsoft.com/EN-US/library/mt621583.aspx).
  
Nella tabella seguente vengono illustrati più relativi ogni condizione.
  
|**Condizione**|**Come utilizzare la condizione**|
|:-----|:-----|
|Direzione  <br/> |Scegliere **in ingresso** per controllare le comunicazioni che vengono inviate **a** utenti che si è scelto di supervisione delle attività **da** utenti non inclusi nel criterio.  <br/> Scegliere **in uscita** , se si desidera controllare le comunicazioni che vengono inviati **da** utenti che si è scelto di controllare * * a * * utenti non inclusi nel criterio.  <br/> Scegliere **Internal** per esaminare inviate le comunicazioni **tra** persone identificato nel criterio.  <br/> |
|Messaggio contiene una di queste parole  <br/> Messaggio non include alcuna di queste parole  <br/> |Per applicare il criterio quando alcune parole o frasi vengono incluse o escluse in un messaggio, immettere ogni parola o frase su una riga distinta. Verrà applicata separatamente ogni riga di parole si immette (solo uno di questi righe necessario applicare per i criteri da applicare al messaggio). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva [minuscole parole e frasi di messaggi di posta elettronica o gli allegati](configure-supervision-policies.md#Matchwords).<br/> |
|Allegato include una di queste parole  <br/> Allegato non include alcuna di queste parole  <br/> |Per applicare il criterio quando alcune parole o frasi vengono incluse o escluse in un allegato del messaggio (ad esempio, un documento di Word), immettere ogni parola o frase su una riga distinta. Verrà applicata separatamente ogni riga di parole si immette (necessario applicare una sola riga per il criterio da applicare all'allegato). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva [minuscole parole e frasi di messaggi di posta elettronica o gli allegati](configure-supervision-policies.md#Matchwords).<br/> |
|Allegato corrisponde a uno qualsiasi di questi tipi di file  <br/> Gli allegati sono Nessuno di questi tipi di file  <br/> |Per controllare le comunicazioni che includono o escludono tipi specifici di allegati, immettere le estensioni di file (ad esempio .exe o PDF). Se si desidera includere o escludere più estensioni di file, immettere queste informazioni su righe separate. Estensione solo un allegato deve corrispondere per il criterio da applicare.  <br/> |
|La dimensione del messaggio è maggiore di  <br/> Dimensione del messaggio non è più grande  <br/> |Per esaminare i messaggi di base in una determinata dimensione, utilizzare le condizioni per specificare la dimensione massima o minima che può essere un messaggio prima che sia soggetto a revisione. Ad esempio, se si specifica **dimensione dei messaggi è superiori a quelle** \> **MB 1.0**, tutti i messaggi che sono MB 1.01 e che verranno più soggette a revisione. È possibile scegliere byte, kilobyte, megabyte o gigabyte questa condizione.<br/> |
|Allegato è più grande  <br/> Non è più grande allegato  <br/> |Per esaminare i messaggi in base alla dimensione degli allegati, specificare la dimensione massima o minima allegato può essere prima del messaggio e relativi allegati sono soggetti a revisione. Ad esempio, se si specifica **l'allegato è più grande** \> **2.0 MB**, tutti i messaggi con allegati MB 2.01 e failover saranno soggette a revisione. È possibile scegliere byte, kilobyte, megabyte o gigabyte questa condizione.<br/> |
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Corrispondenza di parole e frasi a messaggi di posta elettronica o allegati
<a name="Matchwords"> </a>

Verrà applicata separatamente ogni riga di parole si immette (una sola riga necessario applicare per la condizione dei criteri da applicare alla posta elettronica o allegato). Ad esempio, utilizziamo la condizione, **che messaggio contiene una di queste parole**, con il tipo"parole chiave" e "persona interna negoziazione" su righe separate. Il criterio verrà applicato a tutti i messaggi che includono il parola "un particolare tipo" o la frase "utente interno negoziazione". Solo una di queste parole o frasi deve essere eseguito per questa condizione dei criteri da applicare. Parole nel messaggio o allegato devono corrispondere esattamente quello inserito.
  
#### <a name="entering-multiple-conditions"></a>Immissione di più condizioni
<a name="Matchwords"> </a>

Se si immettono più condizioni, Office 365 utilizza contemporaneamente tutte le condizioni per determinare quando applicare i criteri per gli elementi di comunicazione. Quando si imposta più condizioni, è necessario che vengano soddisfatti tutti per il criterio da applicare, a meno che non si immette un'eccezione. Si supponga, ad esempio, che è necessario creare un criterio che si applicano se un messaggio contiene la parola "commerciali" e maggiore di 2MB. Tuttavia, se anche il messaggio contiene le parole "Approvato da parte di Contoso finanziaria", il criterio non applicare. In questo modo, in questo caso, le tre condizioni sarebbero come indicato di seguito: 
  
- **Messaggio contiene una di queste parole**, con le parole chiave "commerciali"
    
- **Dimensione del messaggio è superiori a quelle**con il valore di 2 MB
    
- Il **messaggio non include alcuna di queste parole**, con le parole chiave "Approvato dal team finanziari Contoso".
    
### <a name="specify-percentage-to-review"></a>Specificare una percentuale per la revisione
<a name="CommsToReview"> </a>

Se si desidera ridurre la quantità di contenuto per la revisione, specificare una percentuale. È in modo casuale verrà selezionare tale quantità di contenuto totale corrispondenti alle condizioni che scelto. Se si desidera che i revisori per esaminare tutti gli elementi, immettere **100%**.
  
### <a name="choose-reviewers"></a>Scegliere i revisori
<a name="CommsToReview"> </a>

Gli utenti e gruppi che è scegliere utilizzerà l'app supervisione in Outlook web app per esaminare le comunicazioni vengono restituite da questo criterio. È possibile includere gli indirizzi di posta elettronica per i revisori interni o esterni. 
  
### <a name="review-your-settings"></a>Controllare le impostazioni
<a name="CommsToReview"> </a>

Dopo aver completato tutte le sezioni dei criteri di supervisione, esaminare le impostazioni e quindi fare clic su **Fine** per salvare il criterio. Potrebbe richiedere alcune ore per i criteri avviare il processo communications. Supervisione offre tutte le comunicazioni per la revisione in una cartella condivisa che possono accedere ai revisori di Outlook web app. 
  
## <a name="use-outlook-web-app-to-review-communications-identified-by-a-supervision-policy"></a>Utilizzare Outlook web app per controllare le comunicazioni identificate da un criterio di supervisione
<a name="UseOutlook"> </a>

I revisori utilizzerà il supervisione componente aggiuntivo per Outlook web app per controllare le comunicazioni. Il componente aggiuntivo viene installato automaticamente in Outlook web app per tutti i revisori specificato nel criterio. Supporto per la versione desktop di Outlook è disponibile a breve.
  
 **Esaminare le comunicazioni in Outlook web app**
  
1. In Outlook web app, espandere il **supervisione - \<nome criterio\> ** cartella. 
    
2. Nella ** \<nome criterio\> ** sottocartella, i revisori vedranno tutte le comunicazioni identificate dal criterio supervisione. 
    
    ![Supervisione componente aggiuntivo di Outlook web app che mostra la sottocartella di criteri di supervisione selezionata](media/eef329bf-2bd0-477e-a715-76ca19b3347f.jpg)
  
3. Aprire un elemento per esaminare e fare clic su componente aggiuntivo per la **supervisione** . 
    
4. Utilizzare il componente aggiuntivo per classificare l'elemento come **conforme**, **Non conforme**, **Questionable** o **risolto**. Dopo che è stato classificato un elemento, verrà spostato nella sottocartella corrispondente sotto il ** \<nome criterio\> ** cartella. 
    

