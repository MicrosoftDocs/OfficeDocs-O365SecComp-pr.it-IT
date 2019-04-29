---
title: Utilizzare la ricerca contenuto per cercare i dati di terze parti che sono stati importati in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Utilizzare lo strumento eDiscovery ricerca contenuto per cercare gli elementi importati nelle cassette postali di Office 365 da un'origine dati di terze parti. È possibile creare una query per cercare tutti gli elementi importati o creare una query per la ricerca di tipi di dati specifici di terze parti. In questo articolo vengono elencati i valori che è possibile utilizzare in una query di parole chiave per cercare i tipi di dati di terze parti che possono essere importati in Office 365.
ms.openlocfilehash: c71472b5e6d9b992196780aba55e3775823447ab
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402904"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a>Utilizzare la ricerca contenuto per cercare i dati di terze parti che sono stati importati in Office 365

È possibile utilizzare lo [strumento eDiscovery ricerca contenuto](content-search.md) nel centro sicurezza & Compliance per cercare gli elementi importati nelle cassette postAli di Office 365 da un'origine dati di terze parti. È possibile creare una query per eseguire una ricerca in tutti gli elementi di dati di terze parti importati oppure creare una query per cercare solo elementi di dati di terze parti specifici. Inoltre, è anche possibile creare un criterio di conservazione basato su query o un blocco di eDiscovery basato su query per conservare i dati di terze parti in Office 365. 
  
Per ulteriori informazioni sull'importazione di dati di terze parti e un elenco dei tipi di dati di terze parti che possono essere importati in Office 365, vedere [collaborare con un partner per archiviare i dati di terze parti in office 365](work-with-partner-to-archive-third-party-data.md). 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Creazione di una query per la ricerca di tutti i dati di terze parti

Per cercare (o inserire un blocco) qualsiasi tipo di dati di terze parti importati in Office 365, è possibile utilizzare la `kind:externaldata` coppia proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto o durante la creazione di un blocco basato su query. Ad esempio, per cercare gli elementi importati da un'origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query seguente: 
  
```
kind:externaldata AND subject:contoso
```

Nell'esempio di query con parole chiave precedenti è inclusa la proprietà Subject. Per un elenco di altre proprietà per gli elementi di dati di terze parti che possono essere inclusi in una query di parole chiave, vedere la sezione "ulteriori informazioni" in [collaborazione con un partner per archiviare i dati di terze parti in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).
  
Quando si creano query per la ricerca e la conservazione dei dati di terze parti, è anche possibile utilizzare le condizioni per limitare i risultati della ricerca. Per ulteriori informazioni sulla creazione di query di ricerca del contenuto, vedere [keyword query and Search Conditions for content search](keyword-queries-and-search-conditions.md).
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Creazione di una query per la ricerca di tipi specifici di dati di terze parti

Invece di cercare tutti i tipi di dati di terze parti, è possibile creare query che consentono di cercare solo un tipo di dati di terze parti utilizzando la seguente coppia proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto:
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

Ad esempio, per cercare solo i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query seguente:
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

Nella tabella seguente sono elencati i tipi di dati di terze parti di cui è possibile eseguire la ricerca e il `itemclass:` valore da utilizzare per la proprietà Message per cercare in modo specifico il tipo di dati di terze parti. La sintassi della query non è distinzione tra maiuscole e minuscole. 
  
|**Tipo di dati di terze parti**|**Valore della `itemclass:` proprietà**|
|:-----|:-----|
|OBIETTIVO  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL con Pivot Client   <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Segnaposto AXS  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|BearShare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|BlackBerry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|Registri chiamate BlackBerry  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|PIN BlackBerry  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|SMS BlackBerry  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Posta Bloomberg  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Messaggistica Bloomberg  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Server di &amp; presenza di messaggistica istantanea Cisco  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud per Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Connessione diretta  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google +  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|Connessioni IBM  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|Chat di ghiaccio  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Allinea mente  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype for Business  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Sinfonia  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|Chat UBS  <br/> | `ipm.externaldata.UBS*` <br/> |
|Officemix  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
