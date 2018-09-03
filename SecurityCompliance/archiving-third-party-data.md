---
title: Archiviazione dei dati di terze parti in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Gli amministratori possono importare dati di terze parti da piattaforme di social networking, piattaforme di messaggistica immediate e le piattaforme di collaborazione documento alle cassette postali nell'organizzazione Office 365. Consente di archiviare dati provenienti da origini dati, Twitter e Facebook in Office 365. È possibile appply funzionalità di conformità di Office 365 (ad esempio, conservazione a fini giudiziari, ricerca contenuto e i criteri di conservazione) ai dati di terze parti.
ms.openlocfilehash: f5590d170986b8ae69458e69cedeb8a0ef137ef4
ms.sourcegitcommit: 81c2fd5cd940c51bc43ac7858c7bdfa207ce401a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "23809711"
---
# <a name="archiving-third-party-data-in-office-365"></a>Archiviazione dei dati di terze parti in Office 365

Consente di Office 365 gli amministratori di importare e archiviazione dei dati di terze parti da piattaforme di social networking, messaggistica immediata piattaforme e piattaforme di collaborazione documento, alle cassette postali nell'organizzazione Office 365. Esempi di origini dati di terze parti che è possibile importare in Office 365 includono: 
  
- **Social** - Twitter, Facebook, Yammer e LinkedIn 
    
- **Messaggistica istantanea** - Yahoo Messenger, GoogleTalk e Cisco Jabber 
    
- **Collaborazione sui documenti** - casella e dell'area di sincronizzazione 
    
- **Settori verticali** - gestione delle relazioni dei clienti (ad esempio traffico correlato forza vendita) e Financials (ad esempio Thomson Reuters e Bloomberg) 
    
- **La messaggistica di testo SMS /** - BlackBerry 
    
Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio i criteri di conservazione conservazione per controversia legale, ricerca contenuto, archiviazione sul posto, controllo e Office 365, ovvero a tali dati. Ad esempio, quando una cassetta postale viene messo in attesa di conservazione per controversia, verranno mantenuti i dati di terze parti. È possibile cercare dati di terze parti tramite ricerca del contenuto. Oppure è possibile applicare l'archiviazione e i criteri di conservazione ai dati di terze parti nello stesso modo in cui è possibile utilizzare per i dati di Microsoft. In pratica, l'archiviazione dei dati di terze parti in Office 365 consentono alle organizzazioni garantire la conformità con criteri normativi e pubblico.
  
Ecco una panoramica del processo e i passaggi necessari per importare i dati di terze parti a Office 365.

[Passaggio 1: trovare un partner di dati di terze parti](#step-1-find-a-third-party-data-partner)

[Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti](#step-3-configure-user-mailboxes-for-third-party-data)

[Passaggio 4: fornire informazioni al partner](#step-4-provide-your-partner-with-information)

[Passaggio 5: Registrare il connettore di terze parti dati in Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>Processo di importazione dei dati di terze parti come funziona >

Nella figura e nella descrizione seguenti viene illustrato il processo di importazione di dati di terze parti.
  
![Funzionamento del processo di importazione dei dati di terze parti](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. Clienti può essere utilizzato con i partner della scelta per configurare un connettore che verrà estrarre gli elementi dall'origine dati di terze parti e quindi importato quegli elementi in Office 365.
    
2. Il connettore partner si connette a origini dati di terze parti tramite un'API di terze parti (su base pianificata o come configurati) e vengono estratte elementi dall'origine dati. Il connettore partner converte il contenuto di un elemento in un formato dei messaggi di posta elettronica. Vedere la sezione [informazioni](#more-information) per una descrizione dello schema di formato di messaggio. 
    
3. Connettore partner si connette al servizio Azure in Office 365 tramite servizi Web Exchange (EWS) da un punto finale noto.
    
4. Gli elementi vengono importati nella cassetta postale di un utente specifico oppure in una cassetta postale generale di dati di terze parti. Il fatto che un elemento sia importato nella cassetta postale di un utente specifico o nella cassetta postale di dati di terze parti dipende dai seguenti criteri:
    
    r. **gli elementi che presentano un ID utente che corrisponde a un account utente di Office 365** - se il connettore di partner è possibile mappare l'ID dell'elemento nell'origine dati di terze parti a uno specifico utente che ID in Office 365, l'elemento viene copiato nella cartella **Elimina** l'utente Cartella degli elementi ripristinabili. Gli utenti non possono accedere agli elementi nella cartella Elimina. Tuttavia, è possibile utilizzare gli strumenti di Office 365 eDiscovery per cercare gli elementi nella cartella Elimina.
    
    b. **gli elementi che non dispongono di un ID utente che corrisponde a un account utente di Office 365** : il connettore di partner è possibile connettere l'ID utente di un elemento a un utente specifico che ID in Office 365, l'elemento viene copiato nella cartella **posta in arrivo** della cassetta postale di dati di terze parti. Importazione di elementi di posta in arrivo consente una persona all'interno dell'organizzazione per l'accesso alla cassetta postale di terze parti per visualizzare e gestire tali elementi e verificare se è necessario prevedere nella configurazione del connettore partner eventuali modifiche.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Passaggio 1: trovare un partner di dati di terze parti

Un ruolo fondamentale per l'archiviazione dei dati di terze parti in Office 365 è la ricerca e sull'utilizzo di un partner Microsoft è specializzato in l'acquisizione dei dati da un'origine dati di terze parti e l'importazione in Office 365. Dopo aver importato i dati, possono essere archiviato e mantenuta lungo con l'organizzazione di altri dati di Microsoft, ad esempio documenti di SharePoint e OneDrive for Business e posta elettronica di Exchange. Un partner consente di creare un connettore che estrae dati da origini dati di terze parti dell'organizzazione (ad esempio BlackBerry, Facebook, Google +, Reuters Thomson, Twitter e YouTube) e passa tali dati a un'API di Office 365 che importare gli elementi nelle cassette postali di Exchange come messaggi di posta elettronica. 
  
Nelle sezioni seguenti vengono elencati i partner Microsoft e le origini dati di terze parti che supportano, ovvero che partecipano al programma per l'archiviazione dei dati di terze parti in Office 365.

[17a-4 LLC](#17a-4-llc)
  
[Actiance](#actiance)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

17a-4 LLC supporta le origini dati di terze parti seguenti:
  
- BlackBerry
    
- Flussi di dati di Bloomberg
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- 
Flussi di dati MessageLabs

    
- OpenText
    
- Guida "click-to-call" di Oracle/ATG

    
- Pivot IMTRADER

    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- 
Skype for Business (Lync/OCS)
    
- 
Skype for Business Online (Lync Online)

    
- Database SQL
    
- 
Squawker

    
- Thomson Reuters Eikon Messenger

  
### <a name="actiance"></a>Actiance

[Actiance](https://www.actiance.com) supporta origini dati di terze parti seguenti: 
  
- OBIETTIVO
    
- American Idol
    
- Apple Juice
    
- 
AOL con client Pivot

    
- Ares
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- Registri chiamate BlackBerry (v5, v10, v12)
    
- Messenger BlackBerry (v5, v10, v12)
    
- PIN BlackBerry (v5, v10, v12)
    
- SMS BlackBerry (v5, v10, v12)
    
- Posta Bloomberg

    
- CellTrust
    
- Chat Import

    
- Chat Real Time Logging and Policy

    
- Chatter

    
- Messaggistica Istantanea Cisco &amp; Server presenze (v9.0.1, v 9.1, v9.1.1 SU1, v10, v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)

    
- Importazione collaborazione

    
- Registrazione di collaborazione in tempo reale

    
- Connessione diretta
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google+

    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)

    
- IBM Connections Chat Cloud

    
- IBM Connections Social Cloud

    
- IBM SameTime Advanced 8.5.2 IFR1

    
- IBM SameTime Communicate 9.0

    
- IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)

    
- IBM SameTime Complete 9.0

    
- IBM SameTime Conference 9.0

    
- IBM SameTime Meeting 8.5.2 IFR1

    
- ICE/YellowJacket
    
- IM Import

    
- IM Real Time Logging and Policy

    
- Indii Messenger

    
- Instant Bloomberg

    
- IRC
    
- Jive

    
- Jive 6 Real Time Logging (v6, v7)

    
- Jive Import
    
- JXTA
    
- LinkedIn
    
- 
Microsoft Lync (2010, 2013)

    
- MFTP
    
- Microsoft Lync 2013 Voice

    
- Microsoft SharePoint (2010, 2013)

    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
- Office 365 Lync Dedicated

    
- Messaggistica istantanea condivisa di Office 365

    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphony

    
- Thomson Reuters Eikon

    
- Thomson Reuters Messenger

    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo

    
- Yammer
    
- YouTube
    
  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com) supporta origini dati di terze parti seguenti: 
  
- Facebook
    
- Flickr

    
- Instagram

    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com) supporta origini dati di terze parti seguenti: 
  
- AOL con Pivot Client  
    
- Registri chiamate BlackBerry (v5, v10, v12)
    
- Messenger BlackBerry (v5, v10, v12)
    
- PIN BlackBerry (v5, v10, v12)
    
- SMS BlackBerry (v5, v10, v12)
    
- Chat Bloomber

    
- Posta Bloomberg

    
- Box

    
- CipherCloud per Salesforce Chatter
    
- Messaggistica Istantanea Cisco &amp; Server presenze (v10, SU1 v10.5.1, v11.0, v11.5 SU2)

- Cisco Webex team

- Area di lavoro Citrix &amp; ShareFile

- CrowdCompass

- File di testo delimitati personalizzati

    
- File XML personalizzati

    
- Facebook (pagine)
    
- Factset

    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive

    
- XIP Macgregor


- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer

    
- Mobile Guard
    
- Pivot
    
- Salesforce Chatter

- Skype for Business online
    
- Skype for Business, versioni 2007 R2 - 2016 (locale)

    
- Slack Enterprise Grid
    
- Symphony

    
- Thomson Reuters Eikon

    
- Thomson Reuters Messenger

    
- Thomson Reuters Dealings 3000/FX Trading

    
- Twitter
    
- Chat UBS

    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supporta origini dati di terze parti seguenti: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="verba"></a>Verba

[Verba](https://www.verba.com) supporta origini dati di terze parti seguenti: 
  
- Avaya Aura Video

    
- Avaya Aura Voice

    
- Avtec Radio

    
- Bosch/Telex Radio

    
- BroadSoft Video

    
- BroadSoft Voice

    
- Centile Voice

    
- Messaggistica immediata Cisco Jabber

    
- Cisco UC Video

    
- Cisco UC Voice

    
- Cisco UCCX/UCCE Video
    
- Cisco UCCX/UCCE vocale
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice

    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center per Lync (prairieFyre) 

    
- Oracle / Acme Packet Session Border Controller Video  

    
- Oracle / Acme Packet Session Border Controller Voice

    
- Singtel Mobile Voice

    
- SIPREC Video
    
-  SIPREC Voice 
    
- Messaggistica immediata Skype for Business / Lync

    
- Video Skype for Business / Lync

    
- Chiamate Skype for Business / Lync

    
- Speakerbus Voice

    
- Video SIP/H.323 standard 

    
- Chiamate SIP/H.323 standard 

    
- Truphone Voice

    
- TwistedPair Radio

    
- Schermata di Computer Desktop di Windows 

  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365

Ecco la procedura per la creazione e configurazione di una cassetta postale di dati di terze parti per l'importazione di dati in Office 365. Nel precedente illustrati, vengono importati elementi a questa cassetta postale se il connettore partner non può eseguire il mapping l'ID dell'elemento a un account utente di Office 365.
  
 **Completare queste attività nell'interfaccia di amministrazione di Office 365**
  
1. Creare un nuovo account utente in Office 365 e assegnare una licenza di Exchange Online piano 2; vedere [aggiungere utenti a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Per effettuare la cassetta postale di conservazione per controversia legale o abilitare una cassetta postale di archiviazione con una quota di archiviazione illimitato è necessaria una licenza piano 2.
    
2. Aggiungere l'account utente per la cassetta postale di dati di terze parti per il ruolo di amministratore **di amministrazione di Exchange** in Office 365, vedere [assegnare ruoli di amministratore in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).
    
    > [!TIP]
    > Annotare le credenziali per l'account utente. È necessario fornirle al partner, come descritto nel passaggio 4. 
  
 **Completare queste attività nell'interfaccia di amministrazione di Exchange**
  
1. Nascondere la cassetta postale di terze parti dati dalla Rubrica e altri elenchi di indirizzi nell'organizzazione. vedere [Gestione cassette postali degli utenti](https://go.microsoft.com/fwlink/p/?LinkId=616058). In alternativa, è possibile eseguire il seguente comando PowerShell:
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Assegnare l'autorizzazione **FullAccess** per la cassetta postale di dati di terze parti in modo che gli amministratori o responsabili della conformità aprire la cassetta postale di terze parti dati nel client desktop Outlook; vedere [Manage permissions per i destinatari](https://go.microsoft.com/fwlink/p/?LinkId=692104).
    
3. Abilitare le seguenti funzionalità Office 365 relativi alla conformità per la cassetta postale di dati di terze parti:
    
    - Abilitare la cassetta postale di archivio; vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md). Consente di liberare spazio nella cassetta postale principale mediante l'impostazione di criteri di archiviazione che sposta gli elementi di dati di terze parti per la cassetta postale di archivio. In questo modo sarà con archiviazione illimitata per i dati di terze parti.
    
    - Effettuare la cassetta postale di dati di terze parti controversie legali. È inoltre possibile applicare un criterio di conservazione di Office 365 in Office 365 Security &amp; centro conformità. Esecuzione di questa cassetta postale in attesa verrà conservazione degli elementi di dati di terze parti (tempo indeterminato o per un periodo specificato) e impedire che venga eliminato dalla cassetta postale. Vedere uno degli argomenti seguenti:
    
      - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Panoramica dei criteri di conservazione in Office 365](retention-policies.md)
    
       
    
    - Abilitare la registrazione per l'accesso alla cassetta postale di dati di terze parti, proprietario, delegato e amministrazione di controllo delle cassette postali vedere [abilitare il controllo in Office 365](enable-mailbox-auditing.md). In questo modo è possibile controllare tutte le attività eseguite da qualsiasi utente che ha accesso alla cassetta postale di dati di terze parti.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti

Il passaggio successivo consiste nel configurare cassette postali degli utenti per il supporto dei dati di terze parti. Completare queste attività utilizzando l'interfaccia di amministrazione di Exchange o utilizzando i cmdlet di Windows PowerShell corrispondenti.
  
1. Abilitare la cassetta postale di archiviazione per ogni utente. vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).
    
2. Archiviare le cassette postali utente conservazione per controversia legale o applicare un criterio di conservazione, Office 365 vedere uno degli argomenti seguenti: 
    
    - [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Panoramica dei criteri di conservazione in Office 365](retention-policies.md)
    
    Come precedentemente illustrato, quando si abilita un blocco delle cassette postali, è possibile impostare una durata per definire quanto tempo devono essere conservati gli elementi dell'origine dati di terze parti oppure è possibile scegliere di conservare gli elementi per un periodo di tempo indeterminato.

## <a name="step-4-provide-your-partner-with-information"></a>Passaggio 4: fornire informazioni al partner

Il passaggio finale consiste nel fornire al partner le informazioni seguenti affinché sia in grado di configurare il connettore per connettersi all'organizzazione di Office 365 e importare i dati nelle cassette postali degli utenti e nella cassetta postale dei dati di terze parti. 
  
- L'endpoint utilizzato per la connessione al servizio Azure in Office 365:

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- Accesso in credenziali (ID utente di Office 365 e password) della cassetta postale di dati di terze parti creato nel passaggio 2. Queste credenziali sono necessari in modo che il connettore di partner può accedere e importare gli elementi delle cassette postali utente e la cassetta postale di dati di terze parti.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Passaggio 5: Registrare il connettore di terze parti dati in Azure Active Directory

Avvio 30 settembre 2018, il servizio Azure in Office 365 inizierà con l'autenticazione moderno di Exchange Online per autenticare i connettori di dati di terze parti che tentano di connettersi all'organizzazione di Office 365 per importare i dati. Motivo della modifica è che l'autenticazione moderno offre maggiore protezione rispetto al metodo corrente, è basato su whitelist i connettori di terze parti che utilizzano l'endpoint descritto in precedenza per la connessione al servizio di Azure.

Per abilitare un connettore di dati di terze parti per la connessione a Office 365 utilizzando il nuovo metodo di autenticazione moderno, un amministratore dell'organizzazione Office 365 deve acconsente alla registrazione del connettore come un'applicazione di servizio attendibile in Azure Active Directory. Questa operazione viene eseguita mediante l'accettazione di una richiesta di autorizzazioni per consentire il connettore per accedere ai dati dell'organizzazione in Azure Active Directory. Dopo aver accettato la richiesta, il connettore di terze parti dati aggiunto come un'applicazione enterprise per Azure Active Directory e rappresentato come un'identità di servizio. Per ulteriori informazioni il processo di consenso dell'utente, vedere [Il proprio consenso amministrazione Tenant](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).

Ecco la procedura per accedere e accettare la richiesta per registrare il connettore:

1. Accedere a [questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e accedere utilizzando le credenziali di un amministratore globale di Office 365.<br/><br/>Viene visualizzata la finestra di dialogo seguente. È possibile espandere accenti circonflessi per esaminare le autorizzazioni assegnate al connettore.<br/><br/>![Viene visualizzata la finestra di dialogo di richiesta di autorizzazioni](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. Fare clic su **Accept**.

Dopo aver accettato la richiesta, viene visualizzato il [dashboard portale Azure](https://portal.azure.com) . Per visualizzare l'elenco delle applicazioni per l'organizzazione, fare clic su **Azure Active Directory** > **applicazioni aziendali**. Il connettore di dati di terze parti di Office 365 è elencato nella blade **applicazioni aziendali** .

> [!IMPORTANT]
> Dopo 30 settembre 2018, dati di terze parti non sono più da importare nelle cassette postali nell'organizzazione non registrare un connettore di dati di terze parti in Azure Active Directory. Nota esistenti di connettori di terze parti dati, ovvero creato prima del 30 settembre 2018, deve essere registrata anche in Azure Active Directory tramite la procedura descritta nel passaggio 5.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Revoca dell'autorizzazione per un connettore di dati di terze parti

Dopo che l'organizzazione acconsente alla richiesta di autorizzazioni per la registrazione di un connettore di dati di terze parti in Azure Active Directory, l'organizzazione può revocare il consenso in qualsiasi momento. Tuttavia, revoca dell'autorizzazione per un connettore significa che i dati dall'origine dati di terze parti non è più essere importati in Office 365.

Per revocare il consenso dell'utente per un connettore di dati di terze parti, è possibile eliminare l'applicazione (eliminando l'entità servizio corrispondente) da Azure Active Directory utilizzando blade **applicazioni aziendali** nel portale di Azure o con la [ Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell. È inoltre possibile utilizzare il cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell.
  
## <a name="more-information"></a>Ulteriori informazioni

- Spiegato come precedente, gli elementi alle cassette postali di Exchange come messaggi di posta elettronica vengono importate le origini dati di terze parti. Il connettore partner consente di importare l'elemento utilizzando uno schema necessario per l'API di Office 365. Nella tabella seguente vengono descritte le proprietà del messaggio di un elemento da un'origine dati di terze parti dopo l'importazione di una cassetta postale di Exchange come messaggio di posta elettronica. Nella tabella indica anche se la proprietà message è obbligatoria. Le proprietà obbligatorie devono essere compilate. Se un elemento manca una proprietà obbligatoria, non sarà possibile importare a Office 365. Il processo di importazione restituirà un messaggio di errore che spiega perché un elemento non è stato importato e la proprietà non è disponibile.
    
    |**Proprietà del messaggio**|**Obbligatorio?**|**Descrizione**|**Valore di esempio**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |Sì  <br/> |L'utente che ha creato o l'elemento inviato nell'origine dati di terze parti. Il connettore partner tenterà di mappare l'ID utente dalla voce di origine (ad esempio un handle Twitter) da un account utente di Office 365 per tutti i partecipanti (utenti nei campi FROM e TO). Verrà importata una copia del messaggio alla cassetta postale di tutti gli altri partecipanti. Se nessuno dei partecipanti dall'elemento può essere associata a un account utente di Office 365, l'elemento verrà importata alla cassetta postale di archiviazione di terze parti in Office 365.<br/> <br/> Il partecipante che viene identificato come mittente dell'elemento deve disporre di una cassetta postale attiva nell'organizzazione di Office 365 importato per l'elemento. Se il mittente non dispone di una cassetta postale attiva, viene restituito l'errore seguente:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |Sì  <br/> |L'utente che ha ricevuto un elemento, se applicabile per un elemento nell'origine dati.  <br/> | `bob@contoso.com` <br/> |
    |**SUBJECT** <br/> |No  <br/> |L'oggetto dell'elemento di origine.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATA** <br/> |Sì  <br/> |La data in cui l'elemento è stato originariamente creato o inserito nell'origine dati del cliente; ad esempio, la data in cui è stato twittato un messaggio di Twitter.  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |No  <br/> |Il contenuto del messaggio o post. Per alcune origini dati, il contenuto di questa proprietà può corrispondere a quella come il contenuto per la proprietà **SUBJECT** . Durante il processo di importazione, il connettore partner tenterà di mantenere massima fedeltà dall'origine di contenuto possibile. Se possibile file, grafica o altri contenuti provenienti dal corpo dell'elemento di origine sono incluso nella proprietà. In caso contrario, il contenuto dall'elemento di origine è incluso nella proprietà **allegato** . Il contenuto della proprietà dipenderà sul connettore di partner e alla capacità della piattaforma di origine.<br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |No  <br/> |Se un elemento nell'origine dati (ad esempio, visualizzato in una conversazione di messaggistica immediata o Twitter) è un file allegato o includere le immagini, il partner connettersi will primo tentativo di essere inclusi gli allegati nella proprietà **BODY** . Se ciò non è possibile, quindi viene aggiunta al * * allegato * * proprietà. Altri esempi di allegati sono apprezzamenti in Facebook, metadati di origine di contenuto e le risposte a un messaggio o post.<br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Sì  <br/> | Si tratta di una proprietà multivalore, che viene creata e compilata dal connettore di partner. Il formato di questa proprietà è `IPM.NOTE.Source.Event`. (Questa proprietà deve iniziare con `IPM.NOTE`; in questo formato è simile a quella per la `IPM.NOTE.X` classe messaggio.) Questa proprietà include le informazioni seguenti:<br/><br/>`Source`-Indica l'origine dati di terze parti. ad esempio Twitter, Facebook o BlackBerry.  <br/> <br/>  `Event`-Indica il tipo di attività eseguita nell'origine dati di terze parti che ha generato gli elementi; ad esempio, visualizzato in un post di Facebook o Twitter. Gli eventi sono specifici per l'origine dati.<br/> <br/>  Uno scopo di questa proprietà è per filtrare elementi specifici in base all'origine dati in un elemento ha dato origine o in base al tipo di evento. In una ricerca eDiscovery, ad esempio, è possibile creare una query di ricerca per trovare tutti i tweets che sono stati inviati da un utente specifico.<br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Quando gli elementi vengono importati correttamente le cassette postali in Office 365, viene restituito un identificatore univoco al chiamante come parte della risposta HTTP. Questo identificatore, viene chiamato `x-IngestionCorrelationID`, può essere utilizzata per scopi di risoluzione dei problemi successivi da parte dei partner per tenere traccia end-to-end di elementi. È consigliabile che i partner acquisire informazioni e accedere conseguenza dal lato. Di seguito è riportato un esempio di una risposta HTTP che mostra l'identificatore:

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- È possibile utilizzare lo strumento di ricerca del contenuto in Office 365 Security &amp; centro conformità per cercare gli elementi che sono stati importati alle cassette postali in Office 365 da un'origine dati di terze parti. Per eseguire la ricerca in modo specifico per questi elementi importati, è possibile utilizzare le seguenti coppie di valore della proprietà messaggio nella casella parole chiave per la ricerca del contenuto. . 
    
  - **`kind:externaldata`**-Utilizzare questo coppia valore della proprietà per cercare tutti i tipi di dati di terze parti. Ad esempio, per cercare gli elementi che sono stati importati da un'origine dati di terze parti e contenuto la parola "contoso" nella proprietà Subject dell'elemento importato, utilizzare la query con parole chiave `kind:externaldata AND subject:contoso`.
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-Utilizzare questo coppia valore della proprietà di ricerca solo un tipo di impostazione dei dati di terze parti. Ad esempio, per eseguire la ricerca solo dati Facebook che contiene la parola "contoso" nella proprietà Subject, utilizzare la query con parole chiave `itemclass:ipm.externaldata.Facebook* AND subject:contoso`. 

  Per un elenco completo dei valori da utilizzare per i tipi di dati di terze parti per la `itemclass` proprietà, vedere [Utilizzo della ricerca contenuto per cercare i dati di terze parti che è stati importati a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   Per ulteriori informazioni sull'utilizzo di Ricerca contenuto e sulla creazione di query di ricerca con parole chiave, vedere:
    
  - [Ricerca del contenuto in Office 365](content-search.md)
    
  - [Query delle parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
 
