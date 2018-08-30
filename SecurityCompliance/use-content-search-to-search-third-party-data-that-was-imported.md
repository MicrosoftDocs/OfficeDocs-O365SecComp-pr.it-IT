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
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a><span data-ttu-id="05950-105">Utilizzare la ricerca del contenuto per cercare i dati di terze parti che è stati importati a Office 365</span><span class="sxs-lookup"><span data-stu-id="05950-105">Use Content Search to search third-party data that was imported to Office 365</span></span>

<span data-ttu-id="05950-p102">È possibile utilizzare lo [strumento di ricerca di contenuto eDiscovery](content-search.md) in Office 365 Security &amp; centro conformità per cercare gli elementi che sono stati importati alle cassette postali in Office 365 da un'origine dati di terze parti. È possibile creare una query per eseguire la ricerca importati tutti gli elementi di dati di terze parti oppure è possibile creare una query di ricerca solo gli elementi di dati specifici di terze parti. Inoltre, è inoltre possibile creare un criterio di conservazione basata su query o un eDiscovery basata su query legale per conservare i dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="05950-p102">You can use the [Content Search eDiscovery tool](content-search.md) in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. You can create a query to search all imported third-party data items or you can create a query to only search specific third-party data items. Additionally, you can also create a query-based Preservation Policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="05950-109">Per ulteriori informazioni sull'importazione di dati di terze parti e un elenco dei tipi di dati di terze parti che possono essere importati a Office 365, vedere [archiviazione dei dati di terze parti in Office 365](archiving-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="05950-109">For more information about importing third-party data and a list of the third-party data types that can be imported to Office 365, see [Archiving third-party data in Office 365](archiving-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="05950-110">Creazione di una query per cercare tutti i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="05950-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="05950-p103">Al servizio di ricerca (o messa in attesa) qualsiasi tipo di dati di terze parti che è stato importato a Office 365, si può essere possibile utilizzare il `kind:externaldata` coppia di messaggi valore della proprietà nella casella parole chiave per la ricerca di contenuto o durante la creazione di un'esenzione basata su query. Per cercare gli elementi che sono stati importati da qualsiasi origine dati di terze parti e contengono la parola "contoso" nella proprietà Subject dell'elemento importato, ad esempio, si utilizzerà la query seguente:</span><span class="sxs-lookup"><span data-stu-id="05950-p103">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold. For example, to search for items that were imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="05950-p104">Nell'esempio precedente viene query di parola chiave include la proprietà subject. Per un elenco delle altre proprietà per i dati di terze parti gli elementi che possono essere inclusi in una query con parole chiave, vedere la sezione "Informazioni" [archiviazione](archiving-third-party-data.md#more-information)dei dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="05950-p104">The previous keyword query example includes the subject property. For a list of other properties for third-party data items that can included in a keyword query, see the "More information" section in [Archiving third-party data in Office 365](archiving-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="05950-p105">Durante la creazione di query per ricercare e conservare dati di terze parti, è inoltre possibile utilizzare le condizioni per limitare i risultati di ricerca. Per ulteriori informazioni sulla creazione di query di ricerca del contenuto, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="05950-p105">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results. For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="05950-117">Creazione di una query per eseguire la ricerca di specifici tipi di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="05950-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="05950-118">Invece di cercare tutti i tipi di dati di terze parti, è possibile creare query che la ricerca sola per un tipo di impostazione dei dati di terze parti con la seguente coppia valore della proprietà messaggio nella casella parole chiave per una ricerca di contenuto:</span><span class="sxs-lookup"><span data-stu-id="05950-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message property-value pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="05950-119">Per cercare solo i dati di Facebook che contiene la parola "contoso" nella proprietà Subject, ad esempio, si utilizzerà la query seguente:</span><span class="sxs-lookup"><span data-stu-id="05950-119">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="05950-p106">Nella tabella seguente sono elencati i tipi di dati di terze parti che è possibile eseguire la ricerca e il valore da utilizzare per il `itemclass:` message, proprietà di ricerca in modo specifico per il tipo di dati di terze parti. Si noti che la sintassi di query non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="05950-p106">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data. Note that the query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="05950-122">**Tipo di dati di terze parti**</span><span class="sxs-lookup"><span data-stu-id="05950-122">**Third-party data type**</span></span>|<span data-ttu-id="05950-123">**Il valore di `itemclass:` proprietà**</span><span class="sxs-lookup"><span data-stu-id="05950-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="05950-124">OBIETTIVO</span><span class="sxs-lookup"><span data-stu-id="05950-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="05950-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="05950-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="05950-126">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="05950-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="05950-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="05950-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="05950-128">Ares</span><span class="sxs-lookup"><span data-stu-id="05950-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="05950-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="05950-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="05950-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="05950-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="05950-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="05950-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="05950-132">Segnaposto Axs</span><span class="sxs-lookup"><span data-stu-id="05950-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="05950-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="05950-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="05950-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="05950-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="05950-135">BearShare</span><span class="sxs-lookup"><span data-stu-id="05950-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="05950-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="05950-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="05950-137">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="05950-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="05950-138">Registri chiamate blackBerry</span><span class="sxs-lookup"><span data-stu-id="05950-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="05950-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="05950-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="05950-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="05950-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="05950-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="05950-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="05950-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="05950-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="05950-143">Posta Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="05950-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="05950-144">Bloomberg messaggistica</span><span class="sxs-lookup"><span data-stu-id="05950-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="05950-145">Box
</span><span class="sxs-lookup"><span data-stu-id="05950-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="05950-146">Messaggistica Istantanea Cisco &amp; Server presenze</span><span class="sxs-lookup"><span data-stu-id="05950-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="05950-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="05950-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="05950-148">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="05950-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="05950-149">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="05950-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="05950-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="05950-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="05950-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="05950-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="05950-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="05950-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="05950-153">Flickr
</span><span class="sxs-lookup"><span data-stu-id="05950-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="05950-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="05950-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="05950-155">Google+
</span><span class="sxs-lookup"><span data-stu-id="05950-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="05950-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="05950-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="05950-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="05950-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="05950-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="05950-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="05950-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="05950-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="05950-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="05950-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="05950-161">Connessioni IBM</span><span class="sxs-lookup"><span data-stu-id="05950-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="05950-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="05950-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="05950-163">Chat ghiaccio</span><span class="sxs-lookup"><span data-stu-id="05950-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="05950-164">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="05950-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="05950-165">Instagram
</span><span class="sxs-lookup"><span data-stu-id="05950-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="05950-166">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="05950-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="05950-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="05950-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="05950-168">IRC</span><span class="sxs-lookup"><span data-stu-id="05950-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="05950-169">Jive
</span><span class="sxs-lookup"><span data-stu-id="05950-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="05950-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="05950-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="05950-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="05950-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="05950-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="05950-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="05950-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="05950-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="05950-174">Comunicazioni unificate Microsoft</span><span class="sxs-lookup"><span data-stu-id="05950-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="05950-175">Allinea presente</span><span class="sxs-lookup"><span data-stu-id="05950-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="05950-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="05950-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="05950-177">MSN</span><span class="sxs-lookup"><span data-stu-id="05950-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="05950-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="05950-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="05950-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="05950-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="05950-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="05950-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="05950-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="05950-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="05950-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="05950-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="05950-183">QQ</span><span class="sxs-lookup"><span data-stu-id="05950-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="05950-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="05950-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="05950-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="05950-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="05950-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="05950-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="05950-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="05950-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="05950-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="05950-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="05950-189">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="05950-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="05950-190">Symphony
</span><span class="sxs-lookup"><span data-stu-id="05950-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="05950-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="05950-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="05950-192">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="05950-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="05950-193">Tor</span><span class="sxs-lookup"><span data-stu-id="05950-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="05950-194">TTT</span><span class="sxs-lookup"><span data-stu-id="05950-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="05950-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="05950-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="05950-196">Chat UBS
</span><span class="sxs-lookup"><span data-stu-id="05950-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="05950-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="05950-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="05950-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="05950-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="05950-199">Winny</span><span class="sxs-lookup"><span data-stu-id="05950-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="05950-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="05950-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="05950-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="05950-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="05950-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="05950-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="05950-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="05950-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
