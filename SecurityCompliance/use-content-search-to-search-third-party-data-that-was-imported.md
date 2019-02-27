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
ms.openlocfilehash: f1ab3cfc8dd866aa0d70014b22a301de2a65f3c5
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296039"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a><span data-ttu-id="376d9-105">Utilizzare la ricerca contenuto per cercare i dati di terze parti che sono stati importati in Office 365</span><span class="sxs-lookup"><span data-stu-id="376d9-105">Use Content Search to search third-party data that was imported to Office 365</span></span>

<span data-ttu-id="376d9-p102">È possibile utilizzare lo [strumento eDiscovery ricerca contenuto](content-search.md) nel centro sicurezza &amp; e conformità di Office 365 per cercare gli elementi importati nelle cassette postali di Office 365 da un'origine dati di terze parti. È possibile creare una query per eseguire una ricerca in tutti gli elementi di dati di terze parti importati oppure creare una query per cercare solo elementi di dati di terze parti specifici. Inoltre, è anche possibile creare un criterio di conservazione basato su query o un blocco di eDiscovery basato su query per conservare i dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="376d9-p102">You can use the [Content Search eDiscovery tool](content-search.md) in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. You can create a query to search all imported third-party data items or you can create a query to only search specific third-party data items. Additionally, you can also create a query-based Preservation Policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="376d9-109">Per ulteriori informazioni sull'importazione di dati di terze parti e un elenco dei tipi di dati di terze parti che possono essere importati in Office 365, vedere [archiviazione dei dati di terze parti in office 365](archiving-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="376d9-109">For more information about importing third-party data and a list of the third-party data types that can be imported to Office 365, see [Archiving third-party data in Office 365](archiving-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="376d9-110">Creazione di una query per la ricerca di tutti i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="376d9-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="376d9-p103">Per cercare (o inserire un blocco) qualsiasi tipo di dati di terze parti importati in Office 365, è possibile utilizzare la `kind:externaldata` coppia proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto o durante la creazione di un blocco basato su query. Ad esempio, per cercare gli elementi importati da un'origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="376d9-p103">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold. For example, to search for items that were imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="376d9-p104">Nell'esempio di query con parole chiave precedenti è inclusa la proprietà Subject. Per un elenco di altre proprietà per gli elementi di dati di terze parti che possono essere inclusi in una query di parole chiave, vedere la sezione "ulteriori informazioni" nell' [archiviazione dei dati di terze parti in Office 365](archiving-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="376d9-p104">The previous keyword query example includes the subject property. For a list of other properties for third-party data items that can included in a keyword query, see the "More information" section in [Archiving third-party data in Office 365](archiving-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="376d9-p105">Quando si creano query per la ricerca e la conservazione dei dati di terze parti, è anche possibile utilizzare le condizioni per limitare i risultati della ricerca. Per ulteriori informazioni sulla creazione di query di ricerca del contenuto, vedere [keyword query and Search Conditions for content search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="376d9-p105">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results. For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="376d9-117">Creazione di una query per la ricerca di tipi specifici di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="376d9-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="376d9-118">Invece di cercare tutti i tipi di dati di terze parti, è possibile creare query che consentono di cercare solo un tipo di dati di terze parti utilizzando la seguente coppia proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto:</span><span class="sxs-lookup"><span data-stu-id="376d9-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message property-value pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="376d9-119">Ad esempio, per cercare solo i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="376d9-119">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="376d9-p106">Nella tabella seguente sono elencati i tipi di dati di terze parti di cui è possibile eseguire la ricerca e il `itemclass:` valore da utilizzare per la proprietà Message per cercare in modo specifico il tipo di dati di terze parti. La sintassi della query non è distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="376d9-p106">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data. Note that the query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="376d9-122">**Tipo di dati di terze parti**</span><span class="sxs-lookup"><span data-stu-id="376d9-122">**Third-party data type**</span></span>|<span data-ttu-id="376d9-123">**Valore della `itemclass:` proprietà**</span><span class="sxs-lookup"><span data-stu-id="376d9-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="376d9-124">OBIETTIVO</span><span class="sxs-lookup"><span data-stu-id="376d9-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="376d9-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="376d9-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="376d9-126">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="376d9-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="376d9-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="376d9-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="376d9-128">Ares</span><span class="sxs-lookup"><span data-stu-id="376d9-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="376d9-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="376d9-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="376d9-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="376d9-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="376d9-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="376d9-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="376d9-132">Segnaposto AXS</span><span class="sxs-lookup"><span data-stu-id="376d9-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="376d9-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="376d9-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="376d9-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="376d9-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="376d9-135">BearShare</span><span class="sxs-lookup"><span data-stu-id="376d9-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="376d9-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="376d9-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="376d9-137">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="376d9-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="376d9-138">Registri chiamate BlackBerry</span><span class="sxs-lookup"><span data-stu-id="376d9-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="376d9-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="376d9-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="376d9-140">PIN BlackBerry</span><span class="sxs-lookup"><span data-stu-id="376d9-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="376d9-141">SMS BlackBerry</span><span class="sxs-lookup"><span data-stu-id="376d9-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="376d9-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="376d9-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="376d9-143">Posta Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="376d9-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="376d9-144">Messaggistica Bloomberg</span><span class="sxs-lookup"><span data-stu-id="376d9-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="376d9-145">Box</span><span class="sxs-lookup"><span data-stu-id="376d9-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="376d9-146">Server di &amp; presenza di messaggistica istantanea Cisco</span><span class="sxs-lookup"><span data-stu-id="376d9-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="376d9-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="376d9-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="376d9-148">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="376d9-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="376d9-149">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="376d9-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="376d9-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="376d9-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="376d9-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="376d9-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="376d9-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="376d9-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="376d9-153">Flickr
</span><span class="sxs-lookup"><span data-stu-id="376d9-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="376d9-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="376d9-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="376d9-155">Google+
</span><span class="sxs-lookup"><span data-stu-id="376d9-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="376d9-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="376d9-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="376d9-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="376d9-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="376d9-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="376d9-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="376d9-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="376d9-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="376d9-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="376d9-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="376d9-161">Connessioni IBM</span><span class="sxs-lookup"><span data-stu-id="376d9-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="376d9-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="376d9-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="376d9-163">Chat di ghiaccio</span><span class="sxs-lookup"><span data-stu-id="376d9-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="376d9-164">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="376d9-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="376d9-165">Instagram
</span><span class="sxs-lookup"><span data-stu-id="376d9-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="376d9-166">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="376d9-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="376d9-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="376d9-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="376d9-168">IRC</span><span class="sxs-lookup"><span data-stu-id="376d9-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="376d9-169">Jive
</span><span class="sxs-lookup"><span data-stu-id="376d9-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="376d9-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="376d9-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="376d9-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="376d9-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="376d9-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="376d9-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="376d9-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="376d9-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="376d9-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="376d9-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="376d9-175">Allinea mente</span><span class="sxs-lookup"><span data-stu-id="376d9-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="376d9-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="376d9-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="376d9-177">MSN</span><span class="sxs-lookup"><span data-stu-id="376d9-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="376d9-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="376d9-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="376d9-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="376d9-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="376d9-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="376d9-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="376d9-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="376d9-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="376d9-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="376d9-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="376d9-183">QQ</span><span class="sxs-lookup"><span data-stu-id="376d9-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="376d9-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="376d9-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="376d9-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="376d9-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="376d9-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="376d9-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="376d9-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="376d9-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="376d9-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="376d9-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="376d9-189">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="376d9-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="376d9-190">Symphony
</span><span class="sxs-lookup"><span data-stu-id="376d9-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="376d9-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="376d9-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="376d9-192">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="376d9-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="376d9-193">Tor</span><span class="sxs-lookup"><span data-stu-id="376d9-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="376d9-194">TTT</span><span class="sxs-lookup"><span data-stu-id="376d9-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="376d9-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="376d9-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="376d9-196">Chat UBS
</span><span class="sxs-lookup"><span data-stu-id="376d9-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="376d9-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="376d9-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="376d9-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="376d9-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="376d9-199">Winny</span><span class="sxs-lookup"><span data-stu-id="376d9-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="376d9-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="376d9-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="376d9-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="376d9-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="376d9-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="376d9-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="376d9-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="376d9-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
