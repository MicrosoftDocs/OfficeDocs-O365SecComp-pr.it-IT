---
title: Archiviazione dei dati di terze parti in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Gli amministratori possono importare i dati di terze parti dalle piattaforme di social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti alle cassette postali nell'organizzazione di Office 365. In questo modo è possibile archiviare i dati da Facebook, Twitter e origini dati in Office 365. È quindi possibile applicare le funzionalità di conformità di Office 365 (come la conservazione legale, la ricerca del contenuto e i criteri di ritenzione) ai dati di terze parti.
ms.openlocfilehash: 6e5f40328c54a6f2c97cb6cfe14a1bc5727ae087
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32249608"
---
# <a name="archiving-third-party-data-in-office-365"></a>Archiviazione di dati di terze parti in Office 365

Office 365 consente agli amministratori di importare e archiviare i dati di terze parti dalle piattaforme per i social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti, alle cassette postali dell'organizzazione di Office 365. Di seguito sono riportati alcuni esempi di origini dati di terze parti che è possibile importare in Office 365: 
  
- **Social** -Twitter, Facebook, Yammer e LinkedIn 
    
- **Messaggistica istantanea** -Yahoo Messenger, GoogleTalk e Cisco Jabber 
    
- **Collaborazione di documenti** -box e Dropbox 
    
- **Industrie verticali** -gestione delle relazioni con i clienti (come Salesforce Chatter) e servizi finanziari (come Thomson Reuters e Bloomberg) 
    
- **SMS/Text Messaging** -BlackBerry 
    
Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo e i criteri di conservazione di Office 365, a tali dati. Ad esempio, quando per una cassetta postale si attiva il blocco a causa di controversie legali, i dati di terze parti verranno mantenuti. È possibile eseguire la ricerca di dati di terze parti utilizzando la ricerca contenuto. In alternativa, è possibile applicare i criteri di archiviazione e conservazione ai dati di terze parti esattamente come per i dati di Microsoft. In breve, l'archiviazione dei dati di terze parti in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.
  
Di seguito è riportata una panoramica del processo e i passaggi necessari per importare i dati di terze parti in Office 365.

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Step 2: Create and configure a third-party data mailbox in Office 365](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[Passaggio 4: fornire informazioni al partner](#step-4-provide-your-partner-with-information)

[Passaggio 5: registrare il connettore di dati di terze parti in Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>Processo di importazione di dati di terze parti

Nella figura e nella descrizione seguenti viene illustrato il processo di importazione di dati di terze parti.
  
![Funzionamento del processo di importazione dei dati di terze parti](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. Il cliente lavora con il proprio partner preferito per configurare un connettore che estrae gli elementi dall'origine dati di terze parti e quindi importa tali elementi in Office 365.
    
2. Il connettore partner si connette a origini dati di terze parti tramite un'API di terze parti (su base pianificata o configurata) ed estrae gli elementi dall'origine dati. Il connettore partner converte il contenuto di un elemento in un formato di messaggio di posta elettronica. Vedere la sezione [More information](#more-information) per una descrizione dello schema del formato del messaggio. 
    
3. Il connettore partner si connette al servizio di Azure in Office 365 utilizzando il servizio Web Exchange (EWS) tramite un punto finale noto.
    
4. Gli elementi vengono importati nella cassetta postale di un utente specifico oppure in una cassetta postale generale di dati di terze parti. Il fatto che un elemento sia importato nella cassetta postale di un utente specifico o nella cassetta postale di dati di terze parti dipende dai seguenti criteri:
    
    un. **Elementi che dispongono di un ID utente corrispondente a un account utente di office 365** : se il connettore del partner può eseguire il mapping dell'ID utente dell'elemento nell'origine dati di terze parti a un ID utente specifico in Office 365, l'elemento viene **** copiato nella cartella Ripuliture del REC dell'utente. cartella elementi overable. Gli utenti non possono accedere agli elementi nella cartella Ripuliture. Tuttavia, è possibile utilizzare gli strumenti di Office 365 eDiscovery per cercare gli elementi nella cartella Purges.
    
    b. **Elementi che non dispongono di un ID utente corrispondente a un account utente di office 365** -se il connettore partner non è in grado di mappare l'ID utente di un elemento a un ID utente specifico in Office 365, l'elemento viene copiato nella cartella **posta in arrivo** della cassetta postale di dati di terze parti. L'importazione di elementi nella posta in arrivo consente a un utente dell'organizzazione di accedere alla cassetta postale di terze parti per visualizzare e gestire questi elementi e vedere se è necessario prevedere modifiche nella configurazione del connettore partner.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Passaggio 1: trovare un partner di dati di terze parti

Un componente chiave per l'archiviazione dei dati di terze parti in Office 365 è l'individuazione e l'utilizzo di un partner Microsoft specializzato nell'acquisizione dei dati da un'origine dati di terze parti e nell'importarlo in Office 365. Dopo aver importato i dati, è possibile archiviarli e conservarli insieme agli altri dati di Microsoft dell'organizzazione, ad esempio la posta elettronica da Exchange e i documenti di SharePoint e OneDrive for business. Un partner crea un connettore che estrae i dati dalle origini dati di terze parti dell'organizzazione (ad esempio, BlackBerry, Facebook, Google +, Thomson Reuters, Twitter e YouTube) e passa tali dati a un'API di Office 365 che importa gli elementi nelle cassette postali di Exchange come messaggi di posta elettronica. 
  
Nelle sezioni seguenti vengono elencati i partner Microsoft e le origini dati di terze parti che supportano, che partecipano al programma per l'archiviazione dei dati di terze parti in Office 365.

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
    
- Factt
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- Flussi di dati MessageLabs
    
- OpenText
    
- Guida "click-to-call" di Oracle/ATG
    
- Pivot IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype for Business (Lync/OCS)
    
- Skype for Business Online (Lync Online)
    
- Database SQL
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  
### <a name="actiance"></a>Actiance

[Actiance](https://www.actiance.com) supporta le origini dati di terze parti seguenti: 
  
- OBIETTIVO
    
- American Idol
    
- Apple Juice
    
- AOL con client Pivot
    
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
    
- Chiacchiere
    
- Server di &amp; presenza di messaggistica istantanea Cisco (v 9.0.1, v 9.1, v 9.1.1 su1, V10, v 10.5.1 su1)
    
- Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
    
- Importazione collaborazione
    
- Registrazione di collaborazione in tempo reale
    
- Connessione diretta
    
- Facebook
    
- Factt
    
- FastTrack
    
- Gnutella
    
- Google +
    
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
    
- Microsoft Lync (2010, 2013)
    
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
    
- Sinfonia
    
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

[ArchiveSocial](https://www.archivesocial.com) supporta le origini dati di terze parti seguenti: 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Officemix
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com) supporta le origini dati di terze parti seguenti: 
  
- AOL con Pivot Client  
    
- Registri chiamate BlackBerry (v5, v10, v12)
    
- Messenger BlackBerry (v5, v10, v12)
    
- PIN BlackBerry (v5, v10, v12)
    
- SMS BlackBerry (v5, v10, v12)
    
- Chat Bloomber
    
- Posta Bloomberg
    
- Box
    
- CipherCloud per Salesforce Chatter
    
- Server di &amp; presenza di messaggistica istantanea Cisco (V10, v 10.5.1 su1, v 11.0, v 11,5 SU2)

- Team Cisco WebEx

- ShareFile di &amp; area di lavoro Citrix

- CrowdCompass

- File di testo delimitati personalizzati
    
- File XML personalizzati
    
- Facebook (pagine)
    
- Factt
    
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
    
- Sinfonia
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000/FX Trading
    
- Twitter
    
- Chat UBS
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supporta le origini dati di terze parti seguenti: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="verba"></a>Verba

[Verba](https://www.verba.com) supporta le origini dati di terze parti seguenti: 
  
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
    
- Video su Cisco UCCX/UCCE
    
- Cisco UCCX/UCCE Voice
    
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

Di seguito sono riportati i passaggi per la creazione e la configurazione di una cassetta postale di dati di terze parti per l'importazione di dati in Office 365. Come spiegato in precedenza, gli elementi vengono importati nella cassetta postale se il connettore partner non è in grado di mappare l'ID utente dell'elemento a un account utente di Office 365.
  
 **Completare queste attività nell'interfaccia di amministrazione di Microsoft 365**
  
1. Creare un nuovo account utente in Office 365 e assegnargli una licenza di Exchange Online piano 2; vedere [aggiungere utenti a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). È necessaria una licenza di piano 2 per attivare il blocco per controversia legale o abilitare una cassetta postale di archiviazione con una quota illimitata.
    
2. Aggiungere l'account utente per la cassetta postale dei dati di terze parti al ruolo **amministratore di Exchange** in Office 365; Per ulteriori informazioni, vedere [assegnare ruoli di amministratore in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).
    
    > [!TIP]
    > Annotare le credenziali per l'account utente. È necessario fornirle al partner, come descritto nel passaggio 4. 
  
 **Completare queste attività nell'interfaccia di amministrazione di Exchange**
  
1. Nascondere la cassetta postale dei dati di terze parti nella rubrica e negli altri elenchi di indirizzi dell'organizzazione. vedere [gestire le cassette postali degli utenti](https://go.microsoft.com/fwlink/p/?LinkId=616058). In alternativa, è possibile eseguire il comando di PowerShell seguente:
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Assegnare l'autorizzazione **FullAccess** alla cassetta postale dei dati di terze parti in modo che gli amministratori o i responsabili della conformità possano aprire la cassetta postale dei dati di terze parti nel client desktop di Outlook. vedere [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).
    
3. Abilitare le seguenti funzionalità di Office 365 correlate alla conformità per la cassetta postale dei dati di terze parti:
    
    - Abilitare la cassetta postale di archiviazione; vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata](enable-unlimited-archiving.md). In questo modo sarà possibile liberare lo spazio di archiviazione nella cassetta postale principale impostando un criterio di archiviazione che consente di spostare gli elementi di dati di terze parti nella cassetta postale di archiviazione. In questo modo si otterrà uno spazio di archiviazione illimitato per i dati di terze parti.
    
    - Abilitare il blocco per controversia legale nella cassetta postale di dati di terze parti. È anche possibile applicare un criterio di conservazione di Office 365 nel centro sicurezza e conformità. Se si inserisce questa cassetta postale in attesa, verranno mantenuti gli elementi di dati di terze parti (a tempo indeterminato o per una durata specificata) e impedire che vengano eliminati dalla cassetta postale. Vedere uno dei seguenti argomenti:
    
      - [Creare un blocco per controversia legale](create-a-litigation-hold.md)
    
      - [Panoramica dei criteri di conservazione in Office 365](retention-policies.md)
    
       
    
    - Abilitare la registrazione di controllo della cassetta postale per l'accesso del proprietario, di un delegato e dell'amministratore alla cassetta postale dei dati di terze parti; vedere [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). In questo modo è possibile controllare tutte le attività eseguite da qualsiasi utente che abbia accesso alla cassetta postale di dati di terze parti.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti

Il passaggio successivo consiste nel configurare cassette postali degli utenti per supportare i dati di terze parti. Completare queste attività utilizzando l'interfaccia di amministrazione di Exchange o utilizzando i cmdlet di Windows PowerShell corrispondenti.
  
1. Abilitare la cassetta postale di archiviazione per ogni utente; vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata](enable-unlimited-archiving.md).
    
2. Inserire le cassette postali degli utenti sul blocco per controversia legale o applicare un criterio di conservazione di Office 365; vedere uno dei seguenti argomenti: 
    
    - [Creare un blocco per controversia legale](create-a-litigation-hold.md)
    
    - [Panoramica dei criteri di conservazione in Office 365](retention-policies.md)
    
    Come precedentemente illustrato, quando si abilita un blocco delle cassette postali, è possibile impostare una durata per definire quanto tempo devono essere conservati gli elementi dell'origine dati di terze parti oppure è possibile scegliere di conservare gli elementi per un periodo di tempo indeterminato.

## <a name="step-4-provide-your-partner-with-information"></a>Passaggio 4: fornire informazioni al partner

Il passaggio finale consiste nel fornire al partner le informazioni seguenti affinché sia in grado di configurare il connettore per connettersi all'organizzazione di Office 365 e importare i dati nelle cassette postali degli utenti e nella cassetta postale dei dati di terze parti. 
  
- Endpoint utilizzato per la connessione al servizio di Azure in Office 365:

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- Credenziali di accesso (ID utente e password di Office 365) della cassetta postale di dati di terze parti creata al passaggio 2. Queste credenziali sono necessarie affinché il connettore partner possa accedere e importare gli elementi nelle cassette postali degli utenti e nella cassetta postale di dati di terze parti.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Passaggio 5: registrare il connettore di dati di terze parti in Azure Active Directory

A partire da settembre 30, 2018, il servizio di Azure in Office 365 inizierà a utilizzare l'autenticazione moderna in Exchange Online per autenticare i connettori di dati di terze parti che tentano di connettersi all'organizzazione di Office 365 per importare i dati. La causa di questa modifica consiste nel fatto che l'autenticazione moderna fornisce maggiore sicurezza rispetto al metodo corrente, basato sulla whitelist di connettori di terze parti che utilizzano l'endpoint descritto in precedenza per la connessione al servizio Azure.

Per abilitare un connettore di dati di terze parti per la connessione a Office 365 utilizzando il nuovo metodo di autenticazione moderno, un amministratore dell'organizzazione di Office 365 deve acconsentire a registrare il connettore come applicazione di servizio attendibile in Azure Active Directory. Per eseguire questa operazione, è necessario accettare una richiesta di autorizzazione per consentire al connettore di accedere ai dati dell'organizzazione in Azure Active Directory. Dopo aver accettato la richiesta, il connettore di dati di terze parti viene aggiunto come applicazione Enterprise ad Azure Active Directory e rappresentato come entità di servizio. Per ulteriori informazioni sul processo di consenso, vedere [tenant admin consenso](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).

Di seguito sono riportati i passaggi per accedere e accettare la richiesta di registrazione del connettore:

1. Accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di un amministratore globale di Office 365.<br/><br/>Verrà visualizzata la finestra di dialogo seguente. È possibile espandere le carriere per esaminare le autorizzazioni che verranno assegnate al connettore.<br/><br/>![Viene visualizzata la finestra di dialogo delle richieste di autorizzazione](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. Fare clic su **Accetta**.

Dopo aver accettato la richiesta, viene visualizzato il [portale di Azure](https://portal.azure.com) . Per visualizzare l'elenco delle applicazioni per l'organizzazione, fare clic su applicazioni di **Azure Active Directory** > **Enterprise**. Il connettore di dati di terze parti di Office 365 è elencato nel Blade **applicazioni Enterprise** .

> [!IMPORTANT]
> Dopo il 30 settembre 2018, i dati di terze parti non verranno più importati nelle cassette postali dell'organizzazione se non si registra un connettore di dati di terze parti in Azure Active Directory. Nota i connettori di dati di terze parti esistenti (quelli creati prima del 30 settembre 2018) devono essere registrati anche in Azure Active Directory attenendosi alla procedura descritta nel passaggio 5.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Revoca del consenso per un connettore di dati di terze parti

Dopo che l'organizzazione ha acconsentito alla richiesta di autorizzazione per la registrazione di un connettore di dati di terze parti in Azure Active Directory, l'organizzazione può revocare il consenso in qualsiasi momento. Tuttavia, la revoca del consenso per un connettore significherà che i dati provenienti dall'origine dati di terze parti non verranno più importati in Office 365.

Per revocare il consenso per un connettore di dati di terze parti, è possibile eliminare l'applicazione (eliminando l'entità servizio corrispondente) da Azure Active Directory utilizzando il Blade **applicazioni Enterprise** nel portale di Azure o utilizzando il [ Remove-MsolServicePrincipal viene](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell. È inoltre possibile utilizzare il cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell.
  
## <a name="more-information"></a>Altre informazioni

- Come illustrato in precedenza, gli elementi provenienti da origini dati di terze parti vengono importati nelle cassette postali di Exchange come messaggi di posta elettronica. Il connettore partner importa l'elemento utilizzando uno schema richiesto dall'API di Office 365. Nella tabella seguente vengono descritte le proprietà del messaggio di un elemento di un'origine dati di terze parti dopo che è stato importato in una cassetta postale di Exchange come messaggio di posta elettronica. Nella tabella viene indicato anche se la proprietà del messaggio è obbligatoria. È necessario popolare le proprietà obbligatorie. Se un elemento è mancante di una proprietà obbligatoria, non verrà importato in Office 365. Il processo di importazione restituirà un messaggio di errore che spiega perché un elemento non è stato importato e la proprietà non è disponibile.
    
    |**Proprietà del messaggio**|**Obbligatorio?**|**Descrizione**|**Valore di esempio**|
    |:-----|:-----|:-----|:-----|
    |**Da** <br/> |Sì  <br/> |L'utente che ha originariamente creato o inviato l'elemento nell'origine dati di terze parti. Il connettore partner tenterà di mappare l'ID utente dall'elemento di origine (ad esempio un handle Twitter) a un account utente di Office 365 per tutti i partecipanti (utenti nei campi da e a). Verrà importata una copia del messaggio nella cassetta postale di ogni partecipante. Se non è possibile eseguire il mapping di nessuno dei partecipanti dall'elemento a un account utente di Office 365, l'elemento verrà importato nella cassetta postale di archiviazione di terze parti in Office 365.  <br/> <br/> Il partecipante identificato come mittente dell'elemento deve disporre di una cassetta postale attiva nell'organizzazione di Office 365 in cui l'elemento viene importato. In caso contrario, viene restituito l'errore seguente:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**A** <br/> |Sì  <br/> |L'utente che ha ricevuto un elemento, se applicabile per un elemento nell'origine dati.  <br/> | `bob@contoso.com` <br/> |
    |**Oggetto** <br/> |No  <br/> |L'oggetto dell'elemento di origine.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**Data** <br/> |Sì  <br/> |La data in cui l'elemento è stato originariamente creato o inserito nell'origine dati del cliente; ad esempio, la data in cui è stato twittato un messaggio di Twitter.  <br/> | `01 NOV 2015` <br/> |
    |**CORPO** <br/> |No  <br/> |Il contenuto del messaggio o del post. Per alcune origini dati, il contenuto di questa proprietà può corrispondere al contenuto della proprietà **SUBJECT**. Durante il processo di importazione, il connettore partner tenterà di mantenere la massima fedeltà possibile rispetto all'origine del contenuto. Se possibile, i file, gli elementi grafici o altri contenuti del corpo dell'elemento di origine sono inclusi in questa proprietà. In caso contrario, il contenuto dell'elemento di origine è incluso nella proprietà **ATTACHMENT**. Il contenuto di questa proprietà dipenderà dal connettore del partner e dalla funzionalità della piattaforma di origine.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ALLEGATO** <br/> |No  <br/> |Se un elemento nell'origine dati, ad esempio un tweet in Twitter o una conversazione di messaggistica istantanea, ha un file allegato o include immagini, la connessione del partner tenterà innanzitutto di includere gli allegati nella proprietà **Body** . Se non è possibile, allora viene aggiunto alla proprietà * * ATTACHMENT * *. Altri esempi di allegati sono i Like su Facebook, i metadati dell'origine del contenuto e le risposte a un messaggio o a un post.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Sì  <br/> | Si tratta di una proprietà multivalore, che viene creata e compilata dal connettore partner. Il formato di questa proprietà è `IPM.NOTE.Source.Event`. (Questa proprietà deve iniziare con `IPM.NOTE`; questo formato è simile a quello della classe `IPM.NOTE.X` Message). Questa proprietà include le informazioni seguenti:  <br/><br/>`Source`-Indica l'origine dati di terze parti; ad esempio, Twitter, Facebook o BlackBerry.  <br/> <br/>  `Event`-Indica il tipo di attività eseguita nell'origine dati di terze parti che ha prodotto gli elementi; ad esempio, un tweet in Twitter o un post in Facebook. Gli eventi sono specifici per l'origine dati.  <br/> <br/>  Uno scopo di questa proprietà risiede nel filtrare gli elementi specifici in base all'origine dati in cui un elemento ha avuto origine o in base al tipo di evento. In una ricerca eDiscovery, ad esempio, è possibile creare una query di ricerca per trovare tutti i tweet pubblicati da un utente specifico.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Quando gli elementi vengono importati correttamente nelle cassette postali di Office 365, viene restituito un identificatore univoco al chiamante come parte della risposta HTTP. Questo identificatore, denominato `x-IngestionCorrelationID`, può essere utilizzato per la risoluzione dei problemi successivi da parte di partner per il monitoraggio end-to-end degli elementi. Si consiglia di raccogliere queste informazioni e registrarle nel modo più appropriato. Di seguito è riportato un esempio di una risposta HTTP che mostra l'identificatore:

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- È possibile utilizzare lo strumento di ricerca contenuto nel centro sicurezza e conformità per cercare gli elementi importati nelle cassette postali di Office 365 da un'origine dati di terze parti. Per eseguire la ricerca in modo specifico per questi elementi importati, è possibile utilizzare le seguenti coppie proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto.
    
  - **`kind:externaldata`**-Utilizzare questa coppia proprietà-valore per eseguire la ricerca in tutti i tipi di dati di terze parti. Ad esempio, per cercare gli elementi importati da un'origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query `kind:externaldata AND subject:contoso`di parole chiave.
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**-Utilizzare questa coppia proprietà-valore per cercare solo un tipo di dati di terze parti. Ad esempio, per cercare solo i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query `itemclass:ipm.externaldata.Facebook* AND subject:contoso`di parole chiave. 

  Per un elenco completo dei valori da utilizzare per i tipi di dati di terze `itemclass` parti per la proprietà, vedere [utilizzare la ricerca contenuto per cercare i dati di terze parti che sono stati importati in Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   Per ulteriori informazioni sull'utilizzo di Ricerca contenuto e sulla creazione di query di ricerca con parole chiave, vedere:
    
  - [Ricerca contenuto in Office 365](content-search.md)
    
  - [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
 
