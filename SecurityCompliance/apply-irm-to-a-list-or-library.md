---
title: Applicare Information Rights Management (IRM) per un elenco o raccolta
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
description: È possibile utilizzare Information Rights Management (IRM) per controllare e proteggere i file scaricati da raccolte o elenchi.
ms.openlocfilehash: 5a48abf13841716d4dba34311d69ca2e6a5ea422
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530730"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Applicare Information Rights Management (IRM) per un elenco o raccolta

È possibile utilizzare Information Rights Management (IRM) per controllare e proteggere i file scaricati da raccolte o elenchi.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Il servizio di Azure Rights Management (Azure RMS) da Azure Information Protection and equivalente in locale, Active Directory Rights Management Services (AD RMS) supportano Information Rights Management per i siti. Nessun installazioni separate o aggiuntive sono necessari.
    
- Prima di applicare IRM per un elenco o raccolta che deve innanzitutto essere abilitato dall'amministratore per il sito.
    
- Per applicare la protezione IRM per un elenco o raccolta, è necessario disporre delle autorizzazioni di amministratore in tale elenco o raccolta.
    
- Se si utilizza SharePoint Online, gli utenti potrebbero verificarsi timeout durante il download dei file di dimensioni maggiori protetti tramite IRM. In questo caso, quindi applicare la protezione IRM mediante le applicazioni di Office e archiviare i file di grandi dimensioni in una raccolta di SharePoint che non utilizza IRM.
    
> [!NOTE]
> Se si utilizza SharePoint Server 2013, un amministratore deve installare programmi di protezione in tutti i server Web front-end per ogni tipo di file che gli utenti nell'organizzazione desiderano proteggere tramite IRM. 
  
## <a name="apply-irm-to-a-list-or-library"></a>Applicare la protezione IRM per un elenco o raccolta
<a name="__toc256598179"> </a>

![Information Rights Management impostazioni](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Passare all'elenco o alla raccolta per cui si desidera configurare IRM.
    
2. Sulla barra multifunzione fare clic sulla scheda **raccolta** e quindi fare clic su **Impostazioni raccolta**. (Se utilizza un elenco, fare clic sulla scheda **elenco** e quindi fare clic su **Impostazioni elenco**).
    
    ![Pulsanti della barra multifunzione impostazioni raccolta SharePoint](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. In **autorizzazioni e gestione**fare clic su **Information Rights Management**. Se il collegamento di Information Rights Management non è presente, potrebbe non essere abilitato IRM per il sito. Rivolgersi all'amministratore di server per verificare se è possibile abilitare IRM per il sito. Il collegamento di Information Rights Management non è visualizzato per le raccolte immagini.
    
4. Nella pagina **Impostazioni di Information Rights Management** selezionare la casella di controllo **Limita le autorizzazioni per i documenti al momento del download della raccolta** da applicare autorizzazioni limitate ai documenti che sono possibile scaricare da questo elenco o raccolta. 
    
5. Nella casella **Crea un titolo di criteri di autorizzazione** digitare un nome descrittivo per il criterio che è possibile utilizzare più avanti per distinguere questo criterio dagli altri criteri. Ad esempio, è possibile digitare **Informazioni aziendali riservate** se si applica autorizzazioni limitate per un elenco o raccolta che conterrà i documenti company confidential. 
    
6. Nella casella **Aggiungi una descrizione dei criteri di autorizzazione** digitare una descrizione che verrà visualizzato agli utenti che utilizzano l'elenco o raccolta che spiega come dovrà gestire documenti presenti nell'elenco o raccolta. Ad esempio, è possibile digitare **discutere il contenuto di questo documento solo con altri dipendenti** se si desidera limitare l'accesso alle informazioni contenute in questi documenti per i dipendenti interni. 
    
7. Per applicare restrizioni aggiuntive per i documenti in questo elenco o raccolta, fare clic su **Mostra opzioni**ed eseguire una delle operazioni seguenti:
    
|**Per eseguire l'operazione:**|**Procedere come segue:**|
|:-----|:-----|
|Consentire agli utenti di stampare documenti dall'elenco o raccolta  <br/> |Selezionare la casella di controllo **Consenti visualizzatori da stampare** .  <br/> |
|Consentire agli utenti che dispongono almeno dell'autorizzazione Visualizza elementi per l'esecuzione di macro o codice incorporato in un documento.  <br/> |Selezionare la casella di controllo **Consenti visualizzatori per l'esecuzione di script e schermo lettore alla funzione in documenti scaricati** .  <br/> Se si seleziona questa opzione, gli utenti potrebbero eseguire codice per estrarre il contenuto di un documento.           |
|Richiedere agli utenti di verificare le credenziali a intervalli specifici.  <br/> Selezionare questa opzione se si desidera limitare l'accesso al contenuto per un periodo di tempo specificato. Se si seleziona questa opzione, licenze di pubblicazione le per accedere al contenuto scadranno dopo il numero specificato di giorni e persone deve restituire al server per verificare le credenziali e scaricare una nuova copia.  <br/> |Selezionare il **gli utenti devono verificare le proprie credenziali utilizzando questo intervallo di (giorni)** casella di controllo e quindi specificare il numero di giorni per cui si desidera documento possa essere visualizzato.  <br/> |
| Impedire il caricamento di documenti che non supportano IRM all'elenco o raccolta.  <br/>  Se si seleziona questa opzione, gli utenti non saranno in grado di caricare uno dei seguenti tipi di file:  <br/>  Tipi di file non è installati in tutti i server Web front-end corrispondente programmi di protezione IRM.  <br/>  Tipi di file che non possono decrittografare SharePoint Server 2010.  <br/>  Tipi di file sono protetti tramite IRM in un altro programma  <br/> |Selezionare la casella di controllo **non consentire agli utenti di caricare documenti che non supportano IRM** .  <br/> |
|Rimuovere le autorizzazioni limitate da questo elenco o raccolta in una data specifica.  <br/> |Selezionare la casella di controllo **Interrompi limitazione dell'accesso alla raccolta a** e quindi selezionare la data in cui si desidera.  <br/> |
|Controllo dell'intervallo che vengono memorizzati nella cache le credenziali per il software viene concesso in licenza per aprire il documento.  <br/> |**Impostare la protezione di gruppo e l'intervallo delle credenziali**, immettere theinterval per la memorizzazione nella cache le credenziali del numero di giorni.  <br/> |
|Consentire la protezione di gruppo in modo che gli utenti possono condividere con i membri del gruppo stesso.  <br/> |Selezionare **Consenti la protezione di gruppo**e immettere il nome del gruppo per la condivisione.  <br/> |
   
8. Dopo aver selezionato le opzioni desiderate, fare clic su **OK**.
  
## <a name="what-is-information-rights-management"></a>Che cos'è Information Rights Management?
<a name="__toc256598175"> </a>

Information Rights Management (IRM) consente di limitare le azioni che gli utenti possono eseguire sui file che sono stati scaricati da elenchi o raccolte. IRM consente di crittografare i file scaricati e limita il set di utenti e programmi consentiti per decrittografare tali file. IRM è inoltre possibile limitare i diritti di utenti sono consentiti leggere i file, in modo che non possono eseguire azioni, ad esempio stampare copie dei file o copiare il testo da essi.
  
È possibile utilizzare IRM in elenchi o raccolte per limitare la diffusione dei contenuti sensibili. Ad esempio, se si crea una raccolta documenti per condividere le informazioni sui prodotti prossimi con determinati responsabili marketing, è possibile utilizzare IRM per impedire a tali utenti di condividere il contenuto con altri dipendenti della società.
  
In un sito, IRM viene applicato a un intero elenco o raccolta, anziché in singoli file. In questo modo più semplice garantire un livello di protezione per un intero set di documenti o file coerenza. IRM consente pertanto all'organizzazione di applicare i criteri aziendali che regolano l'utilizzo e la diffusione di informazioni riservate o proprietarie.
  
> [!NOTE]
> Le informazioni in questa pagina relative ai Information Rights Management sostituisce i termini che fanno riferimento "Information Rights Management" in qualsiasi contratti di termini di licenza Microsoft SharePoint Server 2013 e SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Come IRM consente di proteggere il contenuto
<a name="__toc256598176"> </a>

IRM consente di proteggere il contenuto con restrizioni nei modi seguenti:
  
- Consente di impedire a un utente autorizzato alla visualizzazione dalla copia, modificare, stampare, fax, o copiare e incollare il contenuto per l'utilizzo non autorizzato
    
- Consente di impedire a un utente autorizzato alla visualizzazione di copiare il contenuto utilizzando la caratteristica STAMP in Microsoft Windows
    
- Impedire a un utente autorizzato di visualizzazione del contenuto se viene inviato tramite posta elettronica dopo essere stato scaricato dal server
    
- Limita l'accesso al contenuto per un determinato periodo di tempo trascorso il quale gli utenti devono verificare le proprie credenziali e scaricare il contenuto nuovo
    
- Consente di applicare i criteri aziendali che regolano l'utilizzo e la distribuzione del contenuto all'interno dell'organizzazione
    
### <a name="how-irm-cannot-help-protect-content"></a>Come IRM non può proteggere il contenuto
<a name="__toc256598177"> </a>

IRM non può proteggere il contenuto con restrizioni nei casi seguenti:
  
- Cancellazione, furto, acquisizione o trasmissione tramite programmi dannosi, ad esempio cavalli, di battute e alcuni tipi di spyware
    
- Perdita o danni a causa di virus
    
- Copia manuale o ridigitare del contenuto dalla visualizzazione su schermo
    
- Digitale o su pellicola fotografia del contenuto che viene visualizzato sullo schermo
    
- Copia tramite l'utilizzo di applicazioni di acquisizione schermo di terze parti
    
- La copia dei metadati del contenuto (i valori delle colonne) tramite l'utilizzo di applicazioni di acquisizione schermo di terze parti o azione copia e Incolla
    
[Applicare Information Rights Management a un elenco o a una raccolta](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Funzionamento di IRM per elenchi e raccolte
<a name="__toc256598178"> </a>

La protezione IRM viene applicata ai file a livello di elenco o raccolta. Se IRM è abilitato per una raccolta, gestione dei diritti si applica a tutti i file in tale raccolta. Se IRM è abilitato per un elenco, gestione dei diritti si applica solo ai file associati alle voci di elenco, non le voci dell'elenco effettivo.
  
Al momento del download di file in un elenco abilitato IRM o la raccolta, i file sono crittografati in modo che solo gli utenti autorizzati possono visualizzarli. Ogni file protetto contiene inoltre una licenza di pubblicazione che impone restrizioni sugli utenti che visualizzano il file. Le restrizioni includono in esecuzione un file di sola lettura, la disattivazione della copia del testo, impedendo agli utenti di salvare una copia locale e impedire la stampa del file di persone. Programmi client in grado di leggere i tipi di file supportati IRM utilizzano la licenza di pubblicazione all'interno del file protetto per applicare queste restrizioni. È come un file protetto mantiene la protezione anche dopo essere stato scaricato dal server.
  
I tipi di restrizioni applicate a un file quando viene scaricato da un elenco o raccolta dipendono dalle autorizzazioni del singolo utente nel sito che contiene il file. Nella tabella seguente vengono illustrate le corrispondenze tra le autorizzazioni per i siti e le autorizzazioni IRM.
  
|**Autorizzazioni**|**Autorizzazioni IRM**|
|:-----|:-----|
|Gestire le autorizzazioni, Gestione sito Web  <br/> |**Controllo completo** (come definita dal programma client): questa autorizzazione consente in genere di un utente di leggere, modificare, copiare, salvare e modificare le autorizzazioni del contenuto protetto.  <br/> |
|Modifica elementi, Gestione elenchi, aggiunta e personalizzazione pagine  <br/> |**Modifica**, **Copia**e **salvataggio**: un utente può stampare un file solo se è selezionata la casella di controllo **Consenti agli utenti per la stampa** della pagina Impostazioni di Information Rights Management per l'elenco o raccolta.  <br/> |
|Visualizzazione elementi  <br/> |**Lettura**: un utente può leggere il documento, ma non può copiare o modificare il relativo contenuto. Un utente può stampare solo se è selezionata la casella di controllo **Consenti agli utenti per la stampa** della pagina Impostazioni di Information Rights Management per l'elenco o raccolta.<br/> |
|Altro  <br/> |Nessun'altra autorizzazione corrisponde direttamente alle autorizzazioni IRM.  <br/> |
   
Quando si attiva IRM per un elenco o una raccolta in SharePoint Server 2013, è possibile proteggere solo tipi di file in tale elenco o raccolta per cui è installato un programma di protezione in tutti i server Web front-end. Un programma di protezione è un programma che controlla la crittografia e decrittografia dei file protetti di un formato di file specifici. SharePoint include programmi di protezione per i tipi di file seguenti:
  
- Microsoft Office InfoPath forms
    
- I formati di file 97-2003 per i programmi di Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Formati Office Open XML per i programmi di Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Il formato XML Paper Specification (XPS)
    
Se l'organizzazione prevede di utilizzare IRM per proteggere eventuali altri tipi di file oltre a quelli sopra elencati, l'amministratore del server deve installare programmi di protezione per questi formati di file aggiuntivo.
  

