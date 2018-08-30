---
title: Utilizzare la ricerca del contenuto per cercare i dati di terze parti che è stati importati a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Utilizzare lo strumento di eDiscovery di ricerca del contenuto per cercare gli elementi che sono stati importati alle cassette postali in Office 365 da un'origine dati di terze parti. È possibile creare una query per cercare tutti gli elementi importati o creare una query di ricerca di tipi di dati specifici di terze parti. In questo articolo sono elencati i valori che utilizzabili in una query con parole chiave ricerca i tipi di dati di terze parti che possono essere importati a Office 365.
ms.openlocfilehash: 90d9dc52dcd9dba9bc273dfcf1c5f22e3913d6ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531048"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a>Utilizzare la ricerca del contenuto per cercare i dati di terze parti che è stati importati a Office 365

È possibile utilizzare lo [strumento di ricerca di contenuto eDiscovery](content-search.md) in Office 365 Security &amp; centro conformità per cercare gli elementi che sono stati importati alle cassette postali in Office 365 da un'origine dati di terze parti. È possibile creare una query per eseguire la ricerca importati tutti gli elementi di dati di terze parti oppure è possibile creare una query di ricerca solo gli elementi di dati specifici di terze parti. Inoltre, è inoltre possibile creare un criterio di conservazione basata su query o un eDiscovery basata su query legale per conservare i dati di terze parti in Office 365. 
  
Per ulteriori informazioni sull'importazione di dati di terze parti e un elenco dei tipi di dati di terze parti che possono essere importati a Office 365, vedere [archiviazione dei dati di terze parti in Office 365](archiving-third-party-data.md). 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Creazione di una query per cercare tutti i dati di terze parti

Al servizio di ricerca (o messa in attesa) qualsiasi tipo di dati di terze parti che è stato importato a Office 365, si può essere possibile utilizzare il `kind:externaldata` coppia di messaggi valore della proprietà nella casella parole chiave per la ricerca di contenuto o durante la creazione di un'esenzione basata su query. Per cercare gli elementi che sono stati importati da qualsiasi origine dati di terze parti e contengono la parola "contoso" nella proprietà Subject dell'elemento importato, ad esempio, si utilizzerà la query seguente: 
  
```
kind:externaldata AND subject:contoso
```

Nell'esempio precedente viene query di parola chiave include la proprietà subject. Per un elenco delle altre proprietà per i dati di terze parti gli elementi che possono essere inclusi in una query con parole chiave, vedere la sezione "Informazioni" [archiviazione](archiving-third-party-data.md#more-information)dei dati di terze parti in Office 365.
  
Durante la creazione di query per ricercare e conservare dati di terze parti, è inoltre possibile utilizzare le condizioni per limitare i risultati di ricerca. Per ulteriori informazioni sulla creazione di query di ricerca del contenuto, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md).
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Creazione di una query per eseguire la ricerca di specifici tipi di dati di terze parti

Invece di cercare tutti i tipi di dati di terze parti, è possibile creare query che la ricerca sola per un tipo di impostazione dei dati di terze parti con la seguente coppia valore della proprietà messaggio nella casella parole chiave per una ricerca di contenuto:
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

Per cercare solo i dati di Facebook che contiene la parola "contoso" nella proprietà Subject, ad esempio, si utilizzerà la query seguente:
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

Nella tabella seguente sono elencati i tipi di dati di terze parti che è possibile eseguire la ricerca e il valore da utilizzare per il `itemclass:` message, proprietà di ricerca in modo specifico per il tipo di dati di terze parti. Si noti che la sintassi di query non viene fatta distinzione tra maiuscole e minuscole. 
  
|**Tipo di dati di terze parti**|**Il valore di `itemclass:` proprietà**|
|:-----|:-----|
|OBIETTIVO  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL con Pivot Client   <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Segnaposto Axs  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|BearShare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|BlackBerry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|Registri chiamate blackBerry  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Posta Bloomberg
  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Bloomberg messaggistica  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box
  <br/> | `ipm.externaldata.Box*` <br/> |
|Messaggistica Istantanea Cisco &amp; Server presenze  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud per Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Connessione diretta  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr
  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+
  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|Connessioni IBM  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|Chat ghiaccio  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|Indii Messenger
  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram
  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg
  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive
  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Comunicazioni unificate Microsoft  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Allinea presente  <br/> | `ipm.externaldata.MindAlign*` <br/> |
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
|
Squawker
  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony
  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger
  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|Chat UBS
  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
