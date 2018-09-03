---
title: Query delle parole chiave e condizioni di ricerca per ricerca contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: 'Informazioni sulle proprietà di posta elettronica e file che è possibile cercare nelle cassette postali di Exchange Online e in SharePoint o OneDrive per i siti di Business utilizzando lo strumento di ricerca del contenuto in Office 365 Security &amp; centro conformità.  '
ms.openlocfilehash: 8501743d38425cb980088d65e1dd6bd0bd45cc08
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782103"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>Query delle parole chiave e condizioni di ricerca per ricerca contenuto

In questo argomento vengono descritte le proprietà di posta elettronica e documenti che è possibile cercare negli elementi di posta elettronica in Exchange Online e documenti archiviati in SharePoint e OneDrive for Business siti utilizzando la funzionalità di ricerca del contenuto in Office 365 Security &amp; conformità Al centro. È inoltre possibile utilizzare il ** \*- ComplianceSearch** i cmdlet di sicurezza &amp; PowerShell centro conformità effettuare una ricerca queste proprietà. Descrive inoltre l'argomento: 
  
- Utilizzo di operatori booleani ricerca, le condizioni di ricerca e altre tecniche di query di ricerca per restringere i risultati della ricerca.
    
- La ricerca per i tipi di dati riservati e tipi di dati riservati personalizzati in SharePoint e OneDrive for Business.
    
- Ricerca di contenuto del sito è condivisa con utenti esterni all'organizzazione
    
Per istruzioni dettagliate su come creare una ricerca di contenuto, vedere [Ricerca contenuto in Office 365](content-search.md). |

  
> [!NOTE]
> Ricerca per la protezione del contenuto &amp; centro conformità e i corrispondenti ** \*- ComplianceSearch** i cmdlet di sicurezza &amp; PowerShell centro conformità utilizzare Keyword Query Language (KQL). Per ulteriori informazioni, vedere [riferimento sintassi Keyword Query Language](https://go.microsoft.com/fwlink/?LinkId=269603). 
  
## <a name="searchable-email-properties"></a>Proprietà di posta elettronica disponibili per la ricerca

Nella tabella seguente sono elencati proprietà dei messaggi di posta elettronica che possono essere ricercate utilizzando la funzionalità di ricerca del contenuto per la protezione &amp; centro conformità o utilizzando **New-ComplianceSearch** o il cmdlet **Set-ComplianceSearch** . La tabella include un esempio di sintassi _: valore della proprietà_ per ogni proprietà e una descrizione dei risultati della ricerca restituiti per gli esempi. È possibile digitare queste `property:value` casella alle coppie di parole chiave per la ricerca del contenuto. 
  
|**Proprietà**|**Descrizione proprietà**|**Esempi**|**Risultati di ricerca restituiti dagli esempi**|
|:-----|:-----|:-----|:-----|
|AttachmentNames  <br/> |I nomi dei file allegati a un messaggio di posta elettronica.  <br/> |`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual\*`  <br/> |Messaggi che contengono un file allegato denominato annualreport.ppt. Nel secondo esempio, utilizzando il carattere jolly si ottengono dei messaggi contenenti la parola "annual" nel nome file di un allegato.  <br/> |
|Bcc  <br/> |Il campo BCC (Ccn) di un messaggio di posta elettronica.<sup>1</sup> <br/> |`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`  <br/> |Tutti gli esempi restituiscono messaggi contenenti Pilar Pinilla nel campo Bcc (Ccn).  <br/> |
|Category  <br/> | Le categorie da cercare. Le categorie possono essere definite dagli utenti tramite Outlook o Outlook Web App. I valori possibili sono i seguenti:  <br/><br/>  blue (blu)  <br/>  green (verde)  <br/>  orange (arancione)  <br/>  purple (viola)  <br/>  red (rosso)  <br/>  yellow (giallo)  <br/> |`category:"Red Category"`  <br/> |I messaggi ai quali è stata assegnata la categoria di colore rosso nelle cassette postali di origine.   <br/> |
|Cc  <br/> |Il campo CC (Cc) di un messaggio di posta elettronica.<sup>1</sup> <br/> |`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`  <br/> |In entrambi gli esempi, vengono restituiti i messaggi contenenti Pilar Pinilla specificati nel campo Cc.  <br/> |
|Folderid  <br/> |La cartella ID (GUID) di una cartella di cassetta postale specifica. Se si utilizza questa proprietà, è necessario cercare la cassetta postale che si trova nella cartella specificata. Si noti che verrà cercata solo la cartella specificata. Le sottocartelle della cartella non viene eseguita la ricerca. Per eseguire la ricerca sottocartelle, è necessario utilizzare la proprietà ID cartella per la cartella secondaria da cercare.<br/> Per ulteriori informazioni sulla ricerca per la proprietà ID cartella e l'utilizzo di uno script per ottenere l'ID di cartella per una cassetta postale specifica, vedere [Utilizzare la ricerca del contenuto in Office 365 per le raccolte di destinazione](use-content-search-for-targeted-collections.md).  <br/> |`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`  <br/> |Nel primo esempio restituisce tutti gli elementi nella cartella della cassetta postale specificata. Nel secondo esempio restituisce tutti gli elementi nella cartella della cassetta postale specificata che sono stati inviati o ricevuti da garthf@contoso.com.  <br/> |
|From  <br/> |Il mittente di un messaggio di posta elettronica.<sup>1</sup> <br/> |`from:pilarp@contoso.com`  <br/> `from:contoso.com`  <br/> |I messaggi inviati dall'utente specificato o da un dominio specificato.  <br/> |
|HasAttachment  <br/> |Indica se un messaggio ha un allegato. Utilizzare il valore **true** o **false**.<br/> |`from:pilar@contoso.com AND hasattachment:true`  <br/> |Messaggi inviati dall'utente specificato che contengono allegati.  <br/> |
|Importance  <br/> |La priorità di un messaggio di posta elettronica, che può essere specificata dall'utente al momento dell'invio di un messaggio. Per impostazione predefinita, i messaggi vengono inviati con una priorità normale, a meno che il mittente non imposti la priorità **high** (alta) o **low** (bassa).<br/> |`importance:high`  <br/> `importance:medium`  <br/> `importance:low`  <br/> |I messaggi contrassegnati con priorità alta, media o bassa.  <br/> |
|IsRead  <br/> |Indica se i messaggi letti. Utilizzare il valore **true** o **false**.<br/> |`isread:true`  <br/> `isread:false`  <br/> |Nel primo esempio restituisce i messaggi con la proprietà IsRead impostata su **True**. Nel secondo esempio restituisce i messaggi con la proprietà IsRead impostata su **False**.<br/> |
|ItemClass  <br/> |Utilizzare questa proprietà per cercare i tipi di dati specifici di terze parti che l'organizzazione importato a Office 365. Per questa proprietà, utilizzare la sintassi seguente:`itemclass:ipm.externaldata.<third-party data type>*` <br/> |`itemclass:ipm.externaldata.Facebook\* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter\* AND from:"Ann Beebe" AND "Northwind Traders"`  <br/> |Nel primo esempio restituisce gli elementi di Facebook che contengono la parola "contoso" la proprietà Subject. Nel secondo esempio restituisce Twitter gli elementi che sono stati registrati da Ann Beebe e che contengono la frase parola chiave "Northwind Traders".<br/> Per un elenco completo dei valori da utilizzare per i tipi di dati di terze parti per la proprietà ItemClass, vedere [Utilizzo di ricerca del contenuto per cercare i dati di terze parti che è stati importati a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).  <br/> |
|Kind  <br/> | Il tipo di messaggio di posta elettronica da cercare. Valori possibili:  <br/>  contacts (contatti)  <br/>  docs (documenti)  <br/>  email (posta elettronica)  <br/>  externaldata  <br/>  faxes (fax)  <br/>  im (IM)  <br/>  journals (journal)  <br/>  meetings (riunioni)  <br/>  microsoftteams (restituisce gli elementi di chat, riunioni e le chiamate in Teams Microsoft)  <br/>  notes (note)  <br/>  post (inserimenti)  <br/>  rssfeeds (feed RSS)  <br/>  tasks (attività)  <br/>  Segreteria telefonica  <br/> |`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`  <br/> |Nel primo esempio restituisce i messaggi di posta elettronica che soddisfano i criteri di ricerca. Nel secondo esempio restituisce messaggi di posta elettronica, conversazioni di messaggistica immediata e messaggi vocali che soddisfano i criteri di ricerca. Nel terzo esempio restituisce gli elementi che sono stati importati alle cassette postali in Office 365 da origini dati di terze parti, ad esempio Twitter, Facebook e Jabber Cisco, che soddisfano i criteri di ricerca. Per ulteriori informazioni, vedere [archiviazione dei dati di terze parti in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).<br/> |
|Participants  <br/> |Tutti i campi degli utenti in un messaggio di posta elettronica; questi campi sono From (Da), To (A), CC (Cc) e BCC (Ccn).<sup>1</sup> <br/> |`participants:garthf@contoso.com`  <br/> `participants:contoso.com`  <br/> |I messaggi inviati da o a garthf@contoso.com. Il secondo esempio restituisce tutti i messaggi inviati da o a un utente nel dominio contoso.com.  <br/> |
|Received  <br/> |La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario.  <br/> |`received:04/15/2016`  <br/> `received\>=01/01/2016 AND received\<=03/31/2016`  <br/> |Messaggi ricevuti in 15 aprile 2016. Nel secondo esempio restituisce tutti i messaggi ricevuti tra il 1 ° gennaio 2016 e il 31 marzo 2016.  <br/> |
|Destinatari  <br/> |Tutti i campi dei destinatari in un messaggio di posta elettronica; questi campi sono To (A), CC (Cc) e BCC (Ccn).<sup>1</sup> <br/> |`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`  <br/> |I messaggi inviati a garthf@contoso.com. Il secondo esempio restituisce i messaggi inviati ai destinatari nel dominio contoso.com.  <br/> |
|Sent  <br/> |La data in cui un messaggio di posta elettronica viene inviato dal mittente.  <br/> |`sent:07/01/2016`  <br/> `sent\>=06/01/2016 AND sent\<=07/01/2016`  <br/> |I messaggi inviati in una data specifica o entro l'intervallo di date specificato.  <br/> |
|Size  <br/> |Le dimensioni di un elemento, in byte.  <br/> |`size\>26214400`  <br/> `size:1..1048567`  <br/> |Messaggi di dimensioni superiori a 25?? MB. Nel secondo esempio restituisce i messaggi tra 1 e 1,048,567 byte (1 MB).  <br/> |
|Subject  <br/> |Il testo nella riga dell'oggetto di un messaggio di posta elettronica.  <br/> **Nota:** Quando si utilizza la proprietà Subject in una query, la ricerca ???the restituisce tutti i messaggi in cui la riga dell'oggetto contiene il testo da cercare. In altre parole, la query non restituisce solo i messaggi contenenti una corrispondenza esatta. Ad esempio, se si cerca `subject:"Quarterly Financials"`, i risultati includeranno i messaggi con l'oggetto "Trimestrali 2018 Financials".<br/> |`subject:"Quarterly Financials"`  <br/> `subject:northwind`  <br/> |Messaggi che contengono la frase "Quarterly Financials" in qualsiasi punto nel testo della riga dell'oggetto. Nel secondo esempio restituisce tutti i messaggi che contengono la parola northwind nella riga dell'oggetto.  <br/> |
|Per  <br/> |Il campo To (A) di un messaggio di posta elettronica.<sup>1</sup> <br/> |`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`  <br/> |Tutti gli esempi restituiscono i messaggi in cui è specificato l'utente Ann Beebe nella riga To: (A:).  <br/> |
   
> [!NOTE]
> <sup>1</sup> per il valore di una proprietà del destinatario, è possibile utilizzare l'indirizzo di posta elettronica (anche denominato *nome dell'entità utente* o UPN), nome visualizzato o l'alias per specificare un utente. Ad esempio, è possibile utilizzare annb@contoso.com, annb o "Ann Beebe" per specificare l'utente di Ann Beebe.<br/><br/>Durante la ricerca di una proprietà del destinatario (From, To, Cc, Ccn, i partecipanti e destinatari), Office 365 tenta di espandere l'identità di ogni utente cercando averne di Azure Active Directory.  Se l'utente viene trovato in Azure Active Directory, la query viene espanso per includere alias dell'utente e-mail address (o UPN), nome visualizzato e LegacyExchangeDN.<br/><br/>Ad esempio, una query, ad esempio `participants:ronnie@contoso.com` si estende fino a `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`.

## <a name="searchable-site-properties"></a>Proprietà dei siti disponibili per la ricerca

Nella tabella seguente sono elencati alcuni SharePoint e OneDrive per la proprietà aziendali che possono essere ricercate utilizzando la funzionalità di ricerca del contenuto per la protezione &amp; centro conformità o utilizzando **New-ComplianceSearch** o il ** Set-ComplianceSearch** cmdlet. La tabella include un esempio di sintassi _: valore della proprietà_ per ogni proprietà e una descrizione dei risultati della ricerca restituiti per gli esempi. 
  
Per un elenco completo delle proprietà di SharePoint che può essere eseguita la ricerca, vedere [Overview of a ricerca per indicizzazione e proprietà gestite nello SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Proprietà contrassegnate con **Sì** nella colonna **impostazione sottoponibile a query** possono essere ricercate. 
  
|**Proprietà**|**Descrizione proprietà**|**Esempio**|**Risultati di ricerca restituiti dagli esempi**|
|:-----|:-----|:-----|:-----|
|Autore  <br/> |Nel campo autore da documenti di Office, che rimane permanente se un documento viene copiato. Ad esempio, se un utente crea un documento e i messaggi di posta elettronica a una persona quindi carica in SharePoint, il documento ancora manterrà autore originale. Assicurarsi di utilizzare il nome visualizzato dell'utente per questa proprietà.  <br/> |`author:"Garth Fort"`  <br/> |Tutti i documenti creati da Garth Fort.  <br/> |
|ContentType  <br/> |Tipo di contenuto di SharePoint di un elemento, ad esempio elementi, documenti o Video.  <br/> |`contenttype:document`  <br/> |Vengono restituiti tutti i documenti.  <br/> |
|Created  <br/> |La data di creazione di un elemento.  <br/> |`created\>=06/01/2016`  <br/> |Tutti gli elementi creati o dopo 1 giugno 2016.  <br/> |
|CreatedBy  <br/> |La persona che crea o si scarica un elemento. Assicurarsi di utilizzare il nome visualizzato dell'utente per questa proprietà.  <br/> |`createdby:"Garth Fort"`  <br/> |Tutti gli elementi creati o caricati da Garth Fort.  <br/> |
|DetectedLanguage  <br/> |La lingua di un elemento.  <br/> |`detectedlanguage:english`  <br/> |Tutti gli elementi in lingua inglese.  <br/> |
|FileExtension  <br/> |L'estensione di file. ad esempio, docx, uno, pptx o xlsx.  <br/> |`fileextension:xlsx`  <br/> |Tutti i file di Excel (Excel 2007 e versioni successive)  <br/> |
|FileName  <br/> |Il nome di un file.  <br/> |`filename:"marketing plan"`  <br/> `filename:estimate`  <br/> |Il primo esempio restituisce i file con la frase esatta "marketing plan" nel titolo. Il secondo esempio restituisce i file con la parola "estimate" nel nome file.  <br/> |
|LastModifiedTime  <br/> |La data dell'ultima modifica di un elemento.  <br/> |`lastmodifiedtime\>=05/01/2016`  <br/> `lastmodifiedtime\>=05/10/2016 AND lastmodifiedtime\<=06/1/2016`  <br/> |Nel primo esempio restituisce gli elementi che sono stati modificati o dopo 1 maggio 2016. Nel secondo esempio restituisce gli elementi modificati tra il 1 maggio 2016 e 1 giugno 2016.  <br/> |
|ModifiedBy  <br/> |La persona che ha modificato un elemento. Assicurarsi di utilizzare il nome visualizzato dell'utente per questa proprietà.  <br/> |`modifiedby:"Garth Fort"`  <br/> |Tutti gli elementi in cui l’ultima modifica è stata apportata da Garth Fort.  <br/> |
|Percorso  <br/> |Percorso (URL) di una cartella specifica in un SharePoint o OneDrive per sito aziendale. Se si utilizza questa proprietà, assicurarsi di ricerca nel sito che si trova nella cartella specificata.<br/> Per restituire elementi disponibili nelle sottocartelle nella cartella specificata per la proprietà path, è necessario aggiungere /\* all'URL della cartella specificata. ad esempio `path: https://contoso.sharepoint.com/Shared Documents/*`.  <br/> <br/> **Nota:** Utilizzo di `Path` proprietà per la ricerca di OneDrive percorsi non restituiscono i file multimediali, ad esempio file PNG, TIFF o con estensione wav, nei risultati della ricerca. Utilizzare una proprietà del sito diverso nella query di ricerca per cercare i file multimediali nelle cartelle OneDrive.<br/> <br/> Per ulteriori informazioni sulla ricerca per la proprietà Path e l'utilizzo di uno script per ottenere il percorso URL per le cartelle in un sito specifico, vedere [Utilizzare la ricerca del contenuto in Office 365 per le raccolte di destinazione](use-content-search-for-targeted-collections.md).  <br/> |`path:https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/\*" AND filename:confidential`  <br/> |Nel primo esempio restituisce tutti gli elementi in OneDrive specificato per la cartella di Business. Nel secondo esempio restituirà documenti che contengono la parola "confidential" nel nome del file nella cartella di sito specificata (e tutte le sottocartelle).  <br/> |
|SharedWithUsersOWSUser  <br/> |Documenti che sono state condivisi con l'utente specificato e visualizzati nella pagina **condiviso con me** in OneDrive dell'utente per sito aziendale. Questi sono i documenti in modo esplicito condivise con l'utente specificato da altre persone nell'organizzazione. Quando si esportano i documenti che corrispondono a una query di ricerca che utilizza la proprietà SharedWithUsersOWSUser, i documenti vengono esportati dal percorso originale del contenuto della persona condivisa del documento con l'utente specificato. Per ulteriori informazioni, vedere [ricerca di contenuto del sito condivise all'interno dell'organizzazione](keyword-queries-and-search-conditions.md#internal).<br/> |`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`  <br/> |Entrambi gli esempi di restituire tutti i documenti interni che sono state condivise in modo esplicito con Garth Fort e che vengono visualizzati nella pagina **condiviso con me** Garth Fort OneDrive for Business account.  <br/> |
|Site  <br/> |L'URL di un sito o di un gruppo di siti nell'organizzazione.  <br/> |`site:https://contoso-my.sharepoint.com`  <br/> `site:https://contoso.sharepoint.com/sites/teams`  <br/> |Nel primo esempio restituisce gli elementi di OneDrive per i siti per tutti gli utenti nell'organizzazione. Nel secondo esempio restituisce gli elementi da tutti i siti del team.  <br/> |
|Size  <br/> |Le dimensioni di un elemento, in byte.  <br/> |`size\>=1`  <br/> `size:1..10000`  <br/> |Il primo esempio restituisce gli elementi di dimensioni maggiori di 1 byte. Il secondo esempio restituisce gli elementi di dimensioni comprese tra 1 e 10.000 byte.  <br/> |
|Title  <br/> |Il titolo del documento. La proprietà Title è metadati specificata in documenti di Microsoft Office. È diverso dal nome del file del documento.  <br/> |`title:"communication plan"`  <br/> |Qualsiasi documento contenente la frase "communication plan" nella proprietà di metadati Title di un documento di Office.  <br/> |
   
## <a name="searchable-contact-properties"></a>Proprietà del contatto disponibile per la ricerca

Nella tabella seguente sono elencate le proprietà del contatto che vengono indicizzati e che è possibile cercare per l'utilizzo di ricerca del contenuto. Queste sono le proprietà che sono disponibili agli utenti di configurare per i contatti, denominati anche contatti personali dell'utente, che si trovano nella Rubrica personale della cassetta postale dell'utente. Per cercare contatti, è possibile selezionare le cassette postali di ricerca e quindi utilizzare le proprietà di uno o più contatti nella query di parola chiave.
  
> [!TIP]
> Per cercare valori che contengono spazi, utilizzare le virgolette doppie ("??") per contengono la frase; ad esempio `businessaddress:"123 Main Street"`. 
  
|**Proprietà**|**Descrizione proprietà**|
|:-----|:-----|
|BusinessAddress  <br/> |L'indirizzo nella proprietà **Indirizzo dell'ufficio** . La proprietà è l'acronimo l'indirizzo **dell'ufficio** nella pagina proprietà del contatto.<br/> |
|BusinessPhone  <br/> |Il numero di telefono in qualsiasi **Telefono ufficio** dei numeri di proprietà.  <br/> |
|CompanyName  <br/> |Il nome della proprietà **Company** .  <br/> |
|Reparto  <br/> |Il nome nella proprietà **reparto** .  <br/> |
|DisplayName  <br/> |Il nome visualizzato del contatto. Questo è il nome nella proprietà **Nome e cognome** del contatto.<br/> |
|EmailAddress  <br/> |L'indirizzo per qualsiasi proprietà di indirizzo di posta elettronica del contatto. Si noti che gli utenti possono aggiungere più indirizzi di posta elettronica di un contatto. Utilizzo di questa proprietà restituisce i contatti che soddisfano uno qualsiasi degli indirizzi di posta elettronica del contatto.  <br/> |
|FileAs  <br/> |La proprietà **come File** . Questa proprietà viene utilizzata per specificare come il contatto è incluso nell'elenco contatti dell'utente. Un contatto, ad esempio, potrebbe essere elencato come *FirstName, LastName* o *Cognome, nome* .<br/> |
|GivenName  <br/> |Il nome nella proprietà **nome** .  <br/> |
|HomeAddress  <br/> |L'indirizzo in qualsiasi proprietà indirizzo **Home** .  <br/> |
|HomePhone  <br/> |Il numero di telefono in qualsiasi telefono **abitazione** dei numeri di proprietà.  <br/> |
|IMAddress  <br/> |Proprietà indirizzo messaggistica immediata, in genere è un indirizzo di posta elettronica utilizzato per la messaggistica immediata.  <br/> |
|MiddleName  <br/> |Il nome della proprietà name **intermedio** .  <br/> |
|MobilePhone  <br/> |Proprietà number il numero di telefono **cellulare** .  <br/> |
|Nickname  <br/> |Il nome nella proprietà **nome alternativo** .  <br/> |
|OfficeLocation  <br/> |Il valore della proprietà **Office** o **l'ubicazione dell'ufficio** .  <br/> |
|OtherAddress  <br/> |Il valore della **proprietà address** .  <br/> |
|Surname  <br/> |Il nome della proprietà name **ultimo** .  <br/> |
|Titolo  <br/> |Il titolo nella proprietà **titolo professionale** .  <br/> |
   

## <a name="searchable-sensitive-data-types"></a>Tipi di dati sensibili disponibili per la ricerca

È possibile utilizzare la funzionalità di ricerca del contenuto per la protezione &amp; centro conformità per cercare i dati riservati, ad esempio numeri di carta di credito o previdenza sociale, archiviati nei documenti di SharePoint e OneDrive per i siti. Tale scopo, è possibile utilizzare il `SensitiveType` proprietà e il nome di un informazioni riservate digitare in una query con parole chiave. Ad esempio, la query `SensitiveType:"Credit Card Number"` restituirà documenti che contengono un numero di carta di credito. La query `SensitiveType:"U.S. Social Security Number (SSN)"` restituirà documenti che contiene un numero di previdenza sociale negli Stati Uniti. Per visualizzare un elenco dei tipi di dati riservati che è possibile cercare, passare a **classificazioni** \> **tipi di informazioni riservate** in sicurezza &amp; centro conformità. Oppure è possibile utilizzare il cmdlet **Get-DlpSensitiveInformationType** nella protezione &amp; PowerShell centro conformità per visualizzare un elenco di tipi di informazioni riservate. 
  
È inoltre possibile utilizzare il `SensitiveType` proprietà per la ricerca per il nome di un tipo di informazioni riservate personalizzate dall'utente (o un altro amministratore) creato per l'organizzazione. Si noti che è possibile utilizzare la colonna **Publisher** nella pagina **tipi di informazioni riservate** in sicurezza &amp; centro conformità (o la proprietà **Publisher** in PowerShell) per distinguere tra riservati predefinite e personalizzate tipi di informazioni. Per ulteriori informazioni, vedere [creare un tipo di informazioni riservate personalizzate](create-a-custom-sensitive-information-type.md).
  
Per ulteriori informazioni sulla creazione di query che utilizzano il `SensitiveType` proprietà, vedere [Form una query per la ricerca dei dati riservati archiviati nei siti](form-a-query-to-find-sensitive-data-stored-on-sites.md).
  
## <a name="search-operators"></a>Operatori di ricerca

Operatori booleani ricerca, ad esempio **AND**, **OR**e **non**, consentono di definire ricerche più precise, è necessario includere o escludere parole specifiche nella query di ricerca. Altre tecniche, quali l'utilizzo di operatori di proprietà (ad esempio \>= o..), racchiuso tra virgolette, parentesi e i caratteri jolly, consentono di ottimizzare una query di ricerca. Nella tabella seguente sono elencati gli operatori che è possibile utilizzare per ridurre o ampliare risultati della ricerca. 
  
|**Operatore**|**Usage**|**Descrizione**|
|:-----|:-----|:-----|
|AND  <br/> |keyword1 AND keyword2  <br/> |Restituisce gli elementi che includono tutte le parole chiave specificate o `property:value` espressioni. Ad esempio `from:"Ann Beebe" AND subject:northwind` restituirebbe tutti i messaggi inviati da Ann Beebe contenente northwind word nella riga dell'oggetto. <sup>2</sup> <br/> |
|+  <br/> |parola chiave1 + parola chiave2 + keyword3  <br/> |Restituisce gli elementi che contengono *sia* `keyword2` o `keyword3` *e* anche contenenti `keyword1`. Pertanto, in questo esempio è equivalente alla query `(keyword2 OR keyword3) AND keyword1`.  <br/> Si noti che la query `keyword1 + keyword2` (con uno spazio dopo il **+** simbolo) non equivale a utilizzare il * * AND * * operatore. Questa query è equivalente a `"keyword1 + keyword2"` e restituisce gli elementi con la fase esatta `"keyword1 + keyword2"`.<br/> |
|OR  <br/> |keyword1 OR keyword2  <br/> |Restituisce gli elementi che includono una o più delle parole chiave specificate o `property:value` espressioni. <sup>2</sup> <br/> |
|NOT  <br/> |keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> Tipo: messaggistica istantanea  <br/> |Consente di escludere elementi specificati da una parola chiave o un `property:value` espressione. Nel secondo esempio vengono esclusi i messaggi inviati da Ann Beebe. Nel terzo esempio esclude le conversazioni di messaggistica immediata, ad esempio Skype per le conversazioni aziendali che vengono salvati nella cartella delle cassette postali Cronologia conversazioni. <sup>2</sup> <br/> |
|-  <br/> |keyword1 -keyword2  <br/> |Lo stesso come operatore **non** . In modo che la query restituisce gli elementi che contengono `keyword1` e di escludere gli elementi che contengono `keyword2`.<br/> |
|NEAR  <br/> |keyword1 NEAR(n) keyword2  <br/> |Restituisce gli elementi con le parole scritte vicini, dove n è uguale al numero di parole distinto. Ad esempio `best NEAR(5) worst` restituisce qualsiasi elemento in cui la parola "peggiore" è all'interno di cinque parole di "best". Se viene specificato alcun numero, la distanza predefinita è otto parole. <sup>2</sup> <br/> |
|ONEAR  <br/> |keyword1 ONEAR(n) keyword2  <br/> |Allo stesso **quasi**, ma restituisce gli elementi con le parole scritte vicini nell'ordine specificato. Ad esempio `best ONEAR(5) worst` restituisce qualsiasi elemento in cui la parola "ottimale" si verifica prima della parola "peggiore" e le parole sono all'interno di cinque parole tra loro. Se viene specificato alcun numero, la distanza predefinita è otto parole. <sup>2</sup> <br/> > [!NOTE]> L'operatore **ONEAR** non è supportata per la ricerca di cassette postali; funziona solo per la ricerca di SharePoint e OneDrive i siti. Se si esegue la ricerca cassette postali e i siti nella stessa ricerca e la query che include l'operatore **ONEAR** , la ricerca verrà restituiti gli elementi della cassetta postale come se si utilizza l'operatore **NEAR** . In altre parole, la ricerca restituisce gli elementi in cui le parole specificate sono vicini indipendentemente dall'ordine in cui vengono eseguite le parole.           |
|:  <br/> |property:value  <br/> |I due punti (:) nel `property:value` sintassi specifica che il valore della proprietà da ricercare contiene il valore specificato. Ad esempio `recipients:garthf@contoso.com` restituisce tutti i messaggi inviati a garthf@contoso.com.<br/> |
|=  <br/> |property=value  <br/> |Identico operatore **:** .  <br/> |
|\<  <br/> |proprietà\<valore  <br/> |Indica che la proprietà da cercare è inferiore al valore specificato. <sup>1</sup> <br/> |
|\>  <br/> |proprietà\>valore  <br/> |Indica che la proprietà da cercare è superiore al valore specificato.<sup>1</sup> <br/> |
|\<=  <br/> |proprietà\<= valore  <br/> |Indica che la proprietà da cercare è inferiore o uguale al valore specifico.<sup>1</sup> <br/> |
|\>=  <br/> |proprietà\>= valore  <br/> |Indica che la proprietà da cercare è superiore o uguale al valore specifico.<sup>1</sup> <br/> |
|..  <br/> |proprietà: valore1.. valore2  <br/> |Indica che la proprietà da cercare è superiore o uguale al valore 1 e inferiore o uguale al valore 2.<sup>1</sup> <br/> |
|"  "  <br/> |"fair value"  <br/> subject:"Quarterly Financials"  <br/> |Utilizzare le virgolette doppie ("") per cercare una frase esatta o termine di parola chiave e `property:value` query di ricerca.  <br/> |
|\*  <br/> |risultati\*  <br/> oggetto: set\*  <br/> |Ricerche con caratteri jolly prefisso (dove l'asterisco è posizionato alla fine di una parola) corrispondono per i caratteri zero o più parole chiave o `property:value` delle query. Ad esempio `title:set*` restituirà documenti che contengono il set di word, il programma di installazione e impostazione (e altre parole che iniziano con"") il titolo del documento.<br/><br/> **Nota:** È possibile utilizzare solo le ricerche con caratteri jolly prefisso; ad esempio **cat\* ** o **impostare\***. Suffisso ricerche ( ** \*cat** ), infisso ricerche ( **c\*t** ) e le ricerche delle sottostringhe ( ** \*cat\* ** ) non sono supportati.           |
|(  )  <br/> | (fair OR free) AND (from:contoso.com)  <br/>  (IPO OR initial) AND (stock OR shares)  <br/>  (quarterly financials)  <br/> |Parentesi raggruppano Boolean frasi, `property:value` elementi e le parole chiave. Ad esempio `(quarterly financials)` restituisce gli elementi che contengono le parole trimestrali e financials.<br/> |
   
> [!NOTE]
> <sup>1</sup> utilizzare questo operatore per le proprietà che sono valori numerici o Data.<br/> <sup>2</sup> gli operatori booleani ricerca devono essere scritte in maiuscolo; ad esempio, **AND**. Se si utilizza un operatore minuscolo, ad esempio **e**verrà considerata una parola chiave nella query di ricerca. 
  
## <a name="search-conditions"></a>Condizioni di ricerca

È possibile aggiungere le condizioni di una query di ricerca per restringere la ricerca e restituire un set di risultati più dettagliato. Ogni condizione aggiunge una clausola di query di ricerca KQL che viene creata ed eseguita quando si avvia la ricerca.
  
[Condizioni per le proprietà comuni ](#conditions-for-common-properties)

[Condizioni per le proprietà della posta](#conditions-for-mail-properties)

[Condizioni per le proprietà dei documenti](#conditions-for-document-properties)

[Operatori utilizzati con condizioni](#operators-used-with-conditions)

[Linee guida per l'uso di condizioni](#guidelines-for-using-conditions)

[Esempi](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>Condizioni per le proprietà comuni 

Creare una condizione utilizzando le proprietà comuni durante la ricerca di cassette postali e i siti della ricerca stessa. Nella tabella seguente sono elencate le opzioni disponibili da utilizzare quando si aggiunge una condizione.
  
|**Condizione**|**Descrizione**|
|:-----|:-----|
|Data  <br/> |Per la posta elettronica, la data di un messaggio è stata ricevuta da un destinatario o inviata dal mittente. Per i documenti, la data che dell'ultima modifica di un documento.  <br/> |
|Sender/Author  <br/> |Per la posta elettronica, la persona che ha inviato un messaggio. Per i documenti, la persona citata nel campo autore da documenti di Office. È possibile digitare più nomi, separati da virgole. Due o più valori in modo logico sono connessi tramite l'operatore **OR** .<br/> |
|Dimensioni (in byte)  <br/> |Per la posta elettronica e i documenti, la dimensione dell'elemento (in byte).  <br/> |
|Subject/Title  <br/> |Per la posta elettronica, il testo nella riga dell'oggetto del messaggio. Per i documenti, il titolo del documento. Come indicato in precedenza, la proprietà Title è metadati specificati nei documenti di Microsoft Office. È possibile digitare il nome del soggetto più/titolo, separato da virgole. Due o più valori in modo logico sono connessi tramite l'operatore **OR** .<br/> |
|Tag di conformità  <br/> |Per la posta elettronica e documenti, le etichette che sono state assegnate ai documenti e messaggi automaticamente i criteri di etichetta o etichette che sono state assegnate manualmente dagli utenti. Le etichette vengono utilizzate per classificare i documenti per la governance di dati e posta elettronica e applicare le regole di conservazione in base alla classificazione definita per l'etichetta. È possibile digitare una parte del nome di etichetta e utilizzare un carattere jolly o digitare il nome dell'etichetta completa. Per ulteriori informazioni, vedere [Overview of etichette in Office 365](labels.md).<br/> |
  
### <a name="conditions-for-mail-properties"></a>Condizioni per le proprietà della posta

Creare una condizione utilizzando le proprietà della posta quando si effettuano ricerche in cassette postali o cartelle pubbliche. Nella tabella seguente vengono elencate le proprietà della posta elettronica che è possibile utilizzare per una condizione. Tenere presente che tali proprietà sono un sottoinsieme delle proprietà della posta elettronica descritte in precedenza; tali descrizioni sono ripetute per motivi pratici.
  
|**Condizione**|**Descrizione**|
|:-----|:-----|
|Tipo di messaggio  <br/> | Il tipo di messaggio per la ricerca. Questa è la stessa proprietà la proprietà Kind posta elettronica. Valori possibili:  <br/><br/>  contacts (contatti)  <br/>  docs (documenti)  <br/>  email (posta elettronica)  <br/>  externaldata  <br/>  faxes (fax)  <br/>  im (IM)  <br/>  journals (journal)  <br/>  meetings (riunioni)  <br/>  microsoftteams  <br/>  notes (note)  <br/>  post (inserimenti)  <br/>  rssfeeds (feed RSS)  <br/>  tasks (attività)  <br/>  Segreteria telefonica  <br/> |
|Participants  <br/> |Tutti i campi degli utenti in un messaggio di posta elettronica; questi campi sono From (Da), To (A), CC (Cc) e BCC (Ccn).  <br/> |
|Tipo  <br/> |Proprietà della classe messaggio per un elemento di posta elettronica. Questa è la stessa proprietà la proprietà di posta elettronica ItemClass. È inoltre una condizione multivalore. In modo per selezionare più classi messaggio, tenere premuto il tasto **CTRL** e quindi fare clic su due o più classi messaggio nell'elenco a discesa che si desidera aggiungere la condizione. Ogni classe messaggio selezionato nell'elenco verrà connessi logicamente dall'operatore di telefonia **o** nella query di ricerca corrispondente.<br/> Per un elenco delle classi messaggio (e l'ID di classe messaggio corrispondente) che vengono utilizzati da Exchange e che è possibile selezionare nell'elenco delle **classi messaggio** , vedere [tipi di elementi e classi messaggio](https://go.microsoft.com/fwlink/?linkid=848143).  <br/> |
|Received  <br/> |La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. Corrisponde alla proprietà della posta elettronica Received (Ricevuto).  <br/> |
|Destinatari  <br/> |È stata inviata il messaggio di posta elettronica della persona a. Questa è la stessa proprietà la proprietà di posta elettronica a.  <br/> |
|Sender  <br/> |Il mittente di un messaggio di posta elettronica.  <br/> |
|Sent  <br/> |Data di un messaggio di posta elettronica è stato inviato dal mittente. Questa è la stessa proprietà la proprietà di posta elettronica inviato.  <br/> |
|Subject  <br/> |Il testo nella riga dell'oggetto di un messaggio di posta elettronica.  <br/> |
|Per  <br/> |Il destinatario del messaggio di posta elettronica.  <br/> |
  
### <a name="conditions-for-document-properties"></a>Condizioni per le proprietà dei documenti

Creare una condizione utilizzando le proprietà del documento durante la ricerca di documenti in SharePoint e OneDrive per i siti. Nella tabella seguente sono elencate le proprietà del documento che è possibile utilizzare per una condizione. Si noti che le proprietà sono un sottoinsieme delle proprietà del sito che sono stati descritto in precedenza; le descrizioni vengono ripetute presentazione.
  
|**Condizione**|**Descrizione**|
|:-----|:-----|
|Autore  <br/> |Nel campo autore da documenti di Office, che rimane permanente se un documento viene copiato. Ad esempio, se un utente crea un documento e i messaggi di posta elettronica a una persona quindi carica in SharePoint, il documento ancora manterrà autore originale.  <br/> |
|Titolo  <br/> |Il titolo del documento. La proprietà Title è metadati specificata in documenti di Office. È diverso dal nome di file del documento.  <br/> |
|Created  <br/> |La data di creazione di un documento.  <br/> |
|Ultima modifica  <br/> |La data dell'ultima modifica di un documento.  <br/> |
|Tipo file  <br/> |L'estensione di file. ad esempio, docx, uno, pptx o xlsx. Questa è la stessa proprietà la proprietà site FileExtension.  <br/> |
  
### <a name="operators-used-with-conditions"></a>Operatori utilizzati con condizioni

Quando si aggiunge una condizione, è possibile selezionare un operatore pertinente al tipo di proprietà per la condizione. Nella tabella seguente vengono descritti gli operatori utilizzati con condizioni e ne vengono elencati gli equivalenti utilizzati nella query di ricerca.
  
|**Operatore**|**Equivalente nella query**|**Descrizione**|
|:-----|:-----|:-----|
|After  <br/> |`property\>date`  <br/> |Utilizzato con condizioni relative alla data. Restituisce gli elementi che sono stati inviati, ricevuti o modificati dopo la data specificata.   <br/> |
|Before  <br/> |`property\<date`  <br/> |Utilizzato con condizioni relative alla data. Restituisce gli elementi che sono stati inviati, ricevuti o modificati prima della data specificata.  <br/> |
|Between  <br/> |`date..date`  <br/> |Utilizzare con le condizioni di data e la dimensione. Se utilizzato con una condizione di data, restituisce gli elementi non vi sono stati inviati, ricevuti o modificati all'interno dell'intervallo di date specificato. Se utilizzato con una condizione di dimensioni, restituisce gli elementi la cui dimensione è compreso nell'intervallo specificato.  <br/> |
|Contains any of  <br/> |`(property:value) OR (property:value)`  <br/> |Utilizzata con le condizioni per le proprietà che specificano un valore stringa. Restituisce gli elementi contenenti qualsiasi parte di uno o più valori stringa specificata.  <br/> |
|Doesn't contain any of  <br/> |`-property:value`  <br/> `NOT property:value`  <br/> |Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono parti del valore di stringa specificato.  <br/> |
|Doesn't equal any of
  <br/> |`-property=value`  <br/> `NOT property=value`  <br/> |Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono la stringa specificata.  <br/> |
|Equals  <br/> |`size=value`  <br/> |Restituisce gli elementi equivalenti alla dimensione specificata.<sup>1</sup> <br/> |
|Equals any of  <br/> |`(property=value) OR (property=value)`  <br/> |Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che corrispondono esattamente a uno o più valori di stringa specificati.  <br/> |
|Greater  <br/> |`size>value`  <br/> |Restituisce gli elementi dove la proprietà specificata è maggiore del valore indicato.<sup>1</sup> <br/> |
|Greater or equal  <br/> |`size>=value`  <br/> |Restituisce gli elementi dove la proprietà specificata è maggiore o uguale al valore indicato.<sup>1</sup> <br/> |
|Less  <br/> |`size<value`  <br/> |Restituisce gli elementi che sono maggiori o uguali al valore specificato.<sup>1</sup> <br/> |
|Less or equal  <br/> |`size<=value`  <br/> |Restituisce gli elementi che sono maggiori o uguali al valore specificato.<sup>1</sup> <br/> |
|Not equal  <br/> |`size<>value`  <br/> | Restituisce gli elementi che non sono equivalenti alla dimensione specificata.<sup>1</sup> <br/> |
   
> [!NOTE]
> È disponibile solo per le condizioni di utilizzano la proprietà Size <sup>1</sup> questo operatore. 
  
### <a name="guidelines-for-using-conditions"></a>Linee guida per l'uso di condizioni

Tenere presente quanto segue quando si utilizzano le condizioni di ricerca.
  
- Una condizione è connesso logicamente per le query con parole chiave (specificata nella casella parole chiave) dall'operatore di telefonia **e** . Ciò significa che gli elementi devono soddisfare entrambe le query con parole chiave e la condizione da includere nei risultati della. Si tratta come condizioni consentono di limitare i risultati. 
    
- Se si aggiungono due o più condizioni univoche per una query di ricerca (condizioni che specificano proprietà diverse), le condizioni logicamente sono connessi tramite l'operatore **AND** . Pertanto, vengono restituiti solo gli elementi che soddisfano tutte le condizioni (oltre a eventuali query con parole chiave). 
    
- Se si aggiunta più di una condizione per la stessa proprietà, queste condizioni sono connessi logicamente tramite l'operatore **OR** . Pertanto, vengono restituiti gli elementi che soddisfano la query con parole chiave e una qualsiasi delle condizioni. Gruppi di stesse condizioni sono correlati al tra loro dall'operatore di telefonia **o** e quindi set univoco condizioni sono connessi tramite l'operatore **AND** . 
    
- Se si aggiungono più valori, separati da virgole o punti e virgola, di una singola condizione, questi valori sono connessi tramite l'operatore **OR** . Ciò significa che vengono restituiti gli elementi che contengono uno dei valori specificati per la proprietà nella condizione. 
    
- Query di ricerca che viene creata utilizzando la casella parole chiave e condizioni viene visualizzata nella pagina **ricerca** nel riquadro dei dettagli per la ricerca selezionata. In una query, tutto il contenuto a destra della notazione `(c:c)` indica le condizioni che vengono aggiunti alla query. 
    
- Condizioni aggiungere solo le proprietà per la query di ricerca. il non aggiungere operatori. Questo è il motivo per non visualizzare la query visualizzata nel riquadro dei dettagli a destra del `(c:c)` notazione. KQL aggiunge gli operatori logici (in base alle regole indicate in precedenza) quando l'esecuzione della query. 
    
- È possibile utilizzare l'operazione di trascinamento e rilasciare controllo per modificare la sequenza l'ordine delle condizioni. Fare clic sul controllo per una condizione e spostarlo verso l'alto o verso il basso.
    
- Come indicato in precedenza, alcune proprietà condizione può digitare più valori. Ogni valore logicamente è connesso per l'operatore **OR** . Di conseguenza la stessa logica con più istanze della stessa condizione, in ogni ha un valore singolo. Le figure seguenti viene illustrato un esempio di una singola condizione con più valori e un esempio di più condizioni (per la stessa proprietà) con un valore singolo. Entrambi gli esempi di risultati nella stessa query:`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![Una condizione con più valori](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![Più condizioni di ricerca per la stessa proprietà](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> Se una condizione accetta più valori, è consigliabile utilizzare una singola condizione e specificare più valori (separati da virgole o punti e virgola). Ciò garantisce che la logica di query che viene applicata corrisponda a quella desiderata. 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>Esempi

Nell'esempio seguente mostra la versione basata su interfaccia grafica di una query di ricerca con condizioni, la sintassi di query di ricerca che viene visualizzata nel riquadro dei dettagli della ricerca selezionata (che viene inoltre restituito dal cmdlet **Get-ComplianceSearch** ) e la logica del query KQL corrispondente. 
  
#### <a name="example-1"></a>Esempio 1

Questo esempio viene restituito documenti di SharePoint e OneDrive per i siti contenenti un numero di carta di credito e dell'ultima modifica apportata prima del 1 ° gennaio 2016.
  
 **GUI**
  
![Primo esempio relativo alle condizioni di ricerca](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **Sintassi della query di ricerca**
  
 `SensitiveType:"Credit Card Number(c:c)(lastmodifiedtime<2016-01-01)`
  
 **Logica della query di ricerca**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>Esempio 2

In questo esempio vengono restituiti i documenti o gli elementi della posta elettronica che contengono la parola chiave "report", che sono stati inviati o creati prima del 1° aprile 2015 e che contengono la parola "northwind" nel campo dell'oggetto dei messaggi di posta elettronica o nella proprietà del titolo dei documenti. La query esclude le pagine Web che soddisfano gli altri criteri della ricerca. 
  
 **GUI**
  
![Secondo esempio relativo alle condizioni di ricerca](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **Sintassi della query di ricerca**
  
 `report???(c:c)??????(date<2016-04-01)??????(subjecttitle:"northwind")??????(-filetype="aspx")???`
  
 **Logica della query di ricerca**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>Esempio 3
<a name="conditionexamples"> </a>

In questo esempio restituisce messaggi di posta elettronica o calendario riunioni che sono stati inviati tra 1/12/2016 e 30/11/2016 e che contengono le parole che iniziano con "telefono" o "smartphone".
  
 **GUI**
  
![Terzo esempio relativo alle condizioni di ricerca](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **Sintassi della query di ricerca**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **Logica della query di ricerca**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>Ricerca di contenuti dei siti condivisi con utenti esterni

È inoltre possibile utilizzare la funzionalità di ricerca del contenuto per la protezione &amp; centro conformità per cercare documenti archiviati in SharePoint e OneDrive per i siti che sono state condivise con persone esterne all'organizzazione. Ciò può aiutare a identificare le informazioni sensibili o proprietari condivise all'esterno dell'organizzazione. Tale scopo, è possibile utilizzare il `ViewableByExternalUsers` proprietà in una query con parole chiave. Questa proprietà restituirà documenti o siti che sono state condivise con utenti esterni tramite uno dei seguenti metodi di condivisione: 
  
- Un invito alla condivisione che richiede agli utenti di accedere all'organizzazione come utente autenticato.
    
- Un collegamento guest anonimi, che consente a chiunque di questo collegamento per accedere alla risorsa senza dover eseguire l'autenticazione.
    
Ecco alcuni esempi:
  
- La query `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` restituirà tutti gli elementi che sono state condivise con utenti esterni all'organizzazione e contengono un numero di carta di credito. 
    
- La query `ViewableByExternalUsers:true AND ContentType:document AND Site:https://contoso.sharepoint.com/Sites/Teams` restituirà un elenco di documenti in tutti i siti del team nell'organizzazione che sono state condivise con utenti esterni. 
    
> [!TIP]
> Una query di ricerca, ad esempio `ViewableByExternalUsers:true AND ContentType:document` potrebbe restituire una quantità elevata di file con estensione aspx nei risultati della ricerca. Per eliminare questi o altri tipi di file, è possibile utilizzare il `FileExtension` escludere tipi di file specifici, proprietà ad esempio `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`. 
  
Che cos'è considerato contenuto condiviso con persone esterne all'organizzazione? Documenti in SharePoint dell'organizzazione e OneDrive per i siti che vengono condivisi nei percorsi pubblici e che vengono condivisi mediante l'invio di inviti di condivisione. Ad esempio, le seguenti attività utente comportare il contenuto visualizzabile dagli utenti esterni:
  
- Un utente condivide un file o una cartella con una persona esterna all'organizzazione.

    
- Un utente creato e inviato un collegamento a un file condiviso a una persona esterna all'organizzazione. Questo collegamento consente all'utente esterno visualizzare il file (o modifica).
    
- Un utente invia un invito alla condivisione o un collegamento guest a una persona esterna all'organizzazione per visualizzare (o modificare) un file condiviso.
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>Problemi tramite la proprietà ViewableByExternalUsers

Mentre il `ViewableByExternalUsers` proprietà rappresenta lo stato dei se un documento o un sito è condivisa con utenti esterni, esistono alcuni aspetti da questa proprietà non e doesn???t riflettere. Negli scenari seguenti, il valore del `ViewableByExternalUsers` proprietà non vengono aggiornati e potrebbero non essere precisi i risultati di una query di ricerca del contenuto che utilizza questa proprietà. 
  
- Modifiche apportate al criterio, ad esempio la disattivazione di condivisione esterna per un sito o per l'organizzazione di condivisione. La proprietà viene comunque documenti condivisi in precedenza come accessibile dall'esterno anche se l'accesso esterno potrebbe essere stato revocato.
    
- Modifiche apportate all'appartenenza al gruppo, ad esempio aggiungendo o rimuovendo gli utenti esterni a gruppi di sicurezza di Office 365 gruppi o Office 365. La proprietà non vengono aggiornata automaticamente per il gruppo dispone dell'accesso per gli elementi.
    
- Invio gli inviti alla condivisione per gli utenti esterni dove il destinatario non ha ancora accettato l'invito e pertanto non ancora hanno accesso al contenuto.
    
In questi scenari, le `ViewableByExternalUsers` proprietà non riflette lo stato di condivisione corrente fino al sito o raccolta documenti è nuovamente a ricerca per indicizzazione e reindicizzazione. 

## <a name="searching-for-site-content-shared-within-your-organization"></a>Ricerca di contenuto del sito condiviso all'interno dell'organizzazione

Come indicato in precedenza, è possibile utilizzare il `SharedWithUsersOWSUser` proprietà in modo la ricerca dei documenti condivisi tra gli utenti dell'organizzazione. Quando un utente condivide un file (o una cartella) con un altro utente all'interno dell'organizzazione, viene visualizzato un collegamento al file condiviso nella pagina **condiviso con me** OneDrive per account aziendale dell'utente che il file è stato condiviso con. Per eseguire la ricerca per i documenti condivisi con Sara Davis, ad esempio, è possibile utilizzare la query `SharedWithUsersOWSUser:"sarad@contoso.com"`. Se si esportano i risultati della ricerca, verranno scaricati i documenti originali (si trova nel percorso del contenuto della persona che ha condiviso i documenti con Luisa).
  
Si noti che i documenti devono essere condivisi in modo esplicito a un utente specifico da restituire nei risultati della ricerca quando si utilizza il `SharedWithUsersOWSUser` proprietà. Ad esempio, quando un utente condivide un documento nel proprio account OneDrive, hanno la possibilità di condividere con altre persone (all'interno o all'esterno dell'organizzazione), condividere solo con le persone all'interno dell'organizzazione o condividere con una persona specifica. Di seguito viene cattura di schermata della finestra di **condivisione** in OneDrive che mostra le tre opzioni di condivisione. 
  
![Verranno restituiti solo i file condivisi con utenti specifici da una query searcj che utilizza la proprietà SharedWithUsersOWSUser](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
Verranno restituiti solo i documenti condivisi utilizzando la terza opzione (condivisa con **utenti specifici**) da una query di ricerca che utilizza il `SharedWithUsersOWSUser` proprietà. 

## <a name="search-tips-and-tricks"></a>Suggerimenti pratici per la ricerca

- Le ricerche per parole chiave non rilevano la distinzione tra maiuscole e minuscole. Ad esempio, **cat** e **CAT** restituiscono gli stessi risultati.  
    
- Operatori booleani **AND**, **OR**, **non**, **NEAR**e **ONEAR** devono essere maiuscoli. 
    
- Uno spazio tra due parole chiave o due `property:value` espressioni equivale all'utilizzo **AND**. Ad esempio `from:"Sara Davis" subject:reorganization` restituisce tutti i messaggi inviati da Sara Davis contenenti riorganizzazione word nella riga dell'oggetto. 
    
- Utilizzare la sintassi che genera una corrispondenza per i `property:value` formato. Valori non fanno distinzione maiuscole/minuscole e non può avere uno spazio dopo l'operatore. Se vi sia uno spazio, il valore previsto sarà semplicemente una ricerca full-text. Ad esempio `to: pilarp` le ricerche per "pilarp" come parola chiave, anziché per i messaggi inviati a pilarp. 
    
- Quando si cerca una proprietà relativa al destinatario, come To (A), From (Da), Cc (Cc) o Recipients (Destinatari), è possibile utilizzare un indirizzo SMTP, un alias o un nome visualizzato per denotare un destinatario. Ad esempio, è possibile utilizzare pilarp@contoso.com, pilarp o "Pilar Pinilla".
    
- È possibile utilizzare solo le ricerche con caratteri jolly prefisso; ad esempio **cat\* ** o **impostare\***. Suffisso ricerche ( ** \*cat** ), infisso ricerche ( **c\*t** ) e le ricerche delle sottostringhe ( ** \*cat\* ** ) non sono supportati. 
    
- Durante la ricerca di una proprietà, utilizzare le virgolette doppie ("") se il valore è costituita da più parole. Ad esempio `subject:budget Q1` restituisce i messaggi che contengono **budget** nella riga dell'oggetto e che contengono **T1** in un punto qualsiasi del messaggio o in una delle proprietà dei messaggi. Utilizzo di `subject:"budget Q1"` restituisce tutti i messaggi che contengono **budget T1** qualsiasi posizione nella riga dell'oggetto. 
    
- Per escludere il contenuto contrassegnato con un determinato valore della proprietà dai risultati della ricerca, inserire un segno meno (-) prima del nome della proprietà. Ad esempio `-from:"Sara Davis"` escluderà i messaggi inviati da Sara Davis. 
