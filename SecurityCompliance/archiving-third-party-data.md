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
ms.openlocfilehash: 3d51d9f5cb546b33fa636fab0ca319e4d24b1ad4
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23230038"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="181b8-105">Archiviazione dei dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="181b8-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="181b8-p102">Consente di Office 365 gli amministratori di importare e archiviazione dei dati di terze parti da piattaforme di social networking, messaggistica immediata piattaforme e piattaforme di collaborazione documento, alle cassette postali nell'organizzazione Office 365. Esempi di origini dati di terze parti che è possibile importare in Office 365 includono:</span><span class="sxs-lookup"><span data-stu-id="181b8-p102">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="181b8-108">**Social** - Twitter, Facebook, Yammer e LinkedIn</span><span class="sxs-lookup"><span data-stu-id="181b8-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="181b8-109">**Messaggistica istantanea** - Yahoo Messenger, GoogleTalk e Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="181b8-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="181b8-110">**Collaborazione sui documenti** - casella e dell'area di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="181b8-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="181b8-111">**Settori verticali** - gestione delle relazioni dei clienti (ad esempio traffico correlato forza vendita) e Financials (ad esempio Thomson Reuters e Bloomberg)</span><span class="sxs-lookup"><span data-stu-id="181b8-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="181b8-112">**La messaggistica di testo SMS /** - BlackBerry</span><span class="sxs-lookup"><span data-stu-id="181b8-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="181b8-p103">Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio i criteri di conservazione conservazione per controversia legale, ricerca contenuto, archiviazione sul posto, controllo e Office 365, ovvero a tali dati. Ad esempio, quando una cassetta postale viene messo in attesa di conservazione per controversia, verranno mantenuti i dati di terze parti. È possibile cercare dati di terze parti tramite ricerca del contenuto. Oppure è possibile applicare l'archiviazione e i criteri di conservazione ai dati di terze parti nello stesso modo in cui è possibile utilizzare per i dati di Microsoft. In pratica, l'archiviazione dei dati di terze parti in Office 365 consentono alle organizzazioni garantire la conformità con criteri normativi e pubblico.</span><span class="sxs-lookup"><span data-stu-id="181b8-p103">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="181b8-118">Ecco una panoramica del processo e i passaggi necessari per importare i dati di terze parti a Office 365.</span><span class="sxs-lookup"><span data-stu-id="181b8-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="181b8-119">Passaggio 1: trovare un partner di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="181b8-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="181b8-120">Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="181b8-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="181b8-121">Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="181b8-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="181b8-122">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="181b8-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="181b8-123">Processo di importazione dei dati di terze parti come funziona ></span><span class="sxs-lookup"><span data-stu-id="181b8-123">How the third-party data import process works></span></span>

<span data-ttu-id="181b8-124">Nella figura e nella descrizione seguenti viene illustrato il processo di importazione di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="181b8-124">The following illustration and description explain how the third-party data import process works.</span></span>
  
![Funzionamento del processo di importazione dei dati di terze parti](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="181b8-126">Clienti può essere utilizzato con i partner della scelta per configurare un connettore che verrà estrarre gli elementi dall'origine dati di terze parti e quindi importato quegli elementi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="181b8-126">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="181b8-p104">Il connettore partner si connette a origini dati di terze parti tramite un'API di terze parti (su base pianificata o come configurati) e vengono estratte elementi dall'origine dati. Il connettore partner converte il contenuto di un elemento in un formato dei messaggi di posta elettronica. Vedere la sezione [informazioni](#more-information) per una descrizione dello schema di formato di messaggio.</span><span class="sxs-lookup"><span data-stu-id="181b8-p104">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="181b8-130">Connettore partner si connette al servizio Azure in Office 365 tramite servizi Web Exchange (EWS) da un punto finale noto.</span><span class="sxs-lookup"><span data-stu-id="181b8-130">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="181b8-p105">Gli elementi vengono importati nella cassetta postale di un utente specifico oppure in una cassetta postale generale di dati di terze parti. Il fatto che un elemento sia importato nella cassetta postale di un utente specifico o nella cassetta postale di dati di terze parti dipende dai seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="181b8-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="181b8-p106">r. **gli elementi che presentano un ID utente che corrisponde a un account utente di Office 365** - se il connettore di partner è possibile mappare l'ID dell'elemento nell'origine dati di terze parti a uno specifico utente che ID in Office 365, l'elemento viene copiato nella cartella **Elimina** l'utente Cartella degli elementi ripristinabili. Gli utenti non possono accedere agli elementi nella cartella Elimina. Tuttavia, è possibile utilizzare gli strumenti di Office 365 eDiscovery per cercare gli elementi nella cartella Elimina.</span><span class="sxs-lookup"><span data-stu-id="181b8-p106">a. **Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="181b8-p107">b. **gli elementi che non dispongono di un ID utente che corrisponde a un account utente di Office 365** : il connettore di partner è possibile connettere l'ID utente di un elemento a un utente specifico che ID in Office 365, l'elemento viene copiato nella cartella **posta in arrivo** della cassetta postale di dati di terze parti. Importazione di elementi di posta in arrivo consente una persona all'interno dell'organizzazione per l'accesso alla cassetta postale di terze parti per visualizzare e gestire tali elementi e verificare se è necessario prevedere nella configurazione del connettore partner eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="181b8-p107">b. **Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="181b8-140">Passaggio 1: trovare un partner di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="181b8-140">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="181b8-p108">Un ruolo fondamentale per l'archiviazione dei dati di terze parti in Office 365 è la ricerca e sull'utilizzo di un partner Microsoft è specializzato in l'acquisizione dei dati da un'origine dati di terze parti e l'importazione in Office 365. Dopo aver importato i dati, possono essere archiviato e mantenuta lungo con l'organizzazione di altri dati di Microsoft, ad esempio documenti di SharePoint e OneDrive for Business e posta elettronica di Exchange. Un partner consente di creare un connettore che estrae dati da origini dati di terze parti dell'organizzazione (ad esempio BlackBerry, Facebook, Google +, Reuters Thomson, Twitter e YouTube) e passa tali dati a un'API di Office 365 che importare gli elementi nelle cassette postali di Exchange come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="181b8-p108">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="181b8-144">Nelle sezioni seguenti vengono elencati i partner Microsoft e le origini dati di terze parti che supportano, ovvero che partecipano al programma per l'archiviazione dei dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="181b8-144">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="181b8-145">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="181b8-145">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="181b8-146">Actiance</span><span class="sxs-lookup"><span data-stu-id="181b8-146">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="181b8-147">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="181b8-147">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="181b8-148">Globanet</span><span class="sxs-lookup"><span data-stu-id="181b8-148">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="181b8-149">OpenText</span><span class="sxs-lookup"><span data-stu-id="181b8-149">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="181b8-150">Verba</span><span class="sxs-lookup"><span data-stu-id="181b8-150">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="181b8-151">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="181b8-151">17a-4 LLC</span></span>

<span data-ttu-id="181b8-152">17a-4 LLC supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-152">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="181b8-153">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="181b8-153">BlackBerry</span></span>
    
- <span data-ttu-id="181b8-154">Flussi di dati di Bloomberg</span><span class="sxs-lookup"><span data-stu-id="181b8-154">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="181b8-155">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="181b8-155">Cisco Jabber</span></span>
    
- <span data-ttu-id="181b8-156">FactSet</span><span class="sxs-lookup"><span data-stu-id="181b8-156">FactSet</span></span>
    
- <span data-ttu-id="181b8-157">HipChat</span><span class="sxs-lookup"><span data-stu-id="181b8-157">HipChat</span></span>
    
- <span data-ttu-id="181b8-158">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="181b8-158">InvestEdge</span></span>
    
- <span data-ttu-id="181b8-159">LivePerson</span><span class="sxs-lookup"><span data-stu-id="181b8-159">LivePerson</span></span>
    
- <span data-ttu-id="181b8-160">
Flussi di dati MessageLabs
</span><span class="sxs-lookup"><span data-stu-id="181b8-160">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="181b8-161">OpenText</span><span class="sxs-lookup"><span data-stu-id="181b8-161">OpenText</span></span>
    
- <span data-ttu-id="181b8-162">Guida "click-to-call" di Oracle/ATG
</span><span class="sxs-lookup"><span data-stu-id="181b8-162">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="181b8-163">Pivot IMTRADER
</span><span class="sxs-lookup"><span data-stu-id="181b8-163">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="181b8-164">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="181b8-164">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="181b8-165">MindAlign</span><span class="sxs-lookup"><span data-stu-id="181b8-165">MindAlign</span></span>
    
- <span data-ttu-id="181b8-166">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="181b8-166">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="181b8-167">
Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="181b8-167">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="181b8-168">
Skype for Business Online (Lync Online)
</span><span class="sxs-lookup"><span data-stu-id="181b8-168">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="181b8-169">Database SQL</span><span class="sxs-lookup"><span data-stu-id="181b8-169">SQL Databases</span></span>
    
- <span data-ttu-id="181b8-170">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="181b8-170">Squawker</span></span>
    
- <span data-ttu-id="181b8-171">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="181b8-171">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="181b8-172">Actiance</span><span class="sxs-lookup"><span data-stu-id="181b8-172">Actiance</span></span>

<span data-ttu-id="181b8-173">[Actiance](https://www.actiance.com) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-173">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="181b8-174">OBIETTIVO</span><span class="sxs-lookup"><span data-stu-id="181b8-174">AIM</span></span>
    
- <span data-ttu-id="181b8-175">American Idol</span><span class="sxs-lookup"><span data-stu-id="181b8-175">American Idol</span></span>
    
- <span data-ttu-id="181b8-176">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="181b8-176">Apple Juice</span></span>
    
- <span data-ttu-id="181b8-177">
AOL con client Pivot
</span><span class="sxs-lookup"><span data-stu-id="181b8-177">AOL with Pivot client</span></span>
    
- <span data-ttu-id="181b8-178">Ares</span><span class="sxs-lookup"><span data-stu-id="181b8-178">Ares</span></span>
    
- <span data-ttu-id="181b8-179">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="181b8-179">Bazaar Voice</span></span>
    
- <span data-ttu-id="181b8-180">Bear Share</span><span class="sxs-lookup"><span data-stu-id="181b8-180">Bear Share</span></span>
    
- <span data-ttu-id="181b8-181">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="181b8-181">Bit Torrent</span></span>
    
- <span data-ttu-id="181b8-182">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="181b8-182">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="181b8-183">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="181b8-183">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="181b8-184">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="181b8-184">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="181b8-185">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="181b8-185">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="181b8-186">Posta Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="181b8-186">Bloomberg Mail</span></span>
    
- <span data-ttu-id="181b8-187">CellTrust</span><span class="sxs-lookup"><span data-stu-id="181b8-187">CellTrust</span></span>
    
- <span data-ttu-id="181b8-188">Chat Import
</span><span class="sxs-lookup"><span data-stu-id="181b8-188">Chat Import</span></span>
    
- <span data-ttu-id="181b8-189">Chat Real Time Logging and Policy
</span><span class="sxs-lookup"><span data-stu-id="181b8-189">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="181b8-190">Chatter
</span><span class="sxs-lookup"><span data-stu-id="181b8-190">Chatter</span></span>
    
- <span data-ttu-id="181b8-191">Messaggistica Istantanea Cisco &amp; Server presenze (v9.0.1, v 9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="181b8-191">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="181b8-192">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
</span><span class="sxs-lookup"><span data-stu-id="181b8-192">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="181b8-193">Importazione collaborazione
</span><span class="sxs-lookup"><span data-stu-id="181b8-193">Collaboration Import</span></span>
    
- <span data-ttu-id="181b8-194">Registrazione di collaborazione in tempo reale
</span><span class="sxs-lookup"><span data-stu-id="181b8-194">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="181b8-195">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="181b8-195">Direct Connect</span></span>
    
- <span data-ttu-id="181b8-196">Facebook</span><span class="sxs-lookup"><span data-stu-id="181b8-196">Facebook</span></span>
    
- <span data-ttu-id="181b8-197">FactSet</span><span class="sxs-lookup"><span data-stu-id="181b8-197">FactSet</span></span>
    
- <span data-ttu-id="181b8-198">FastTrack</span><span class="sxs-lookup"><span data-stu-id="181b8-198">FastTrack</span></span>
    
- <span data-ttu-id="181b8-199">Gnutella</span><span class="sxs-lookup"><span data-stu-id="181b8-199">Gnutella</span></span>
    
- <span data-ttu-id="181b8-200">Google+
</span><span class="sxs-lookup"><span data-stu-id="181b8-200">Google+</span></span>
    
- <span data-ttu-id="181b8-201">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="181b8-201">GoToMyPC</span></span>
    
- <span data-ttu-id="181b8-202">Hopster</span><span class="sxs-lookup"><span data-stu-id="181b8-202">Hopster</span></span>
    
- <span data-ttu-id="181b8-203">HubConnex</span><span class="sxs-lookup"><span data-stu-id="181b8-203">HubConnex</span></span>
    
- <span data-ttu-id="181b8-204">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
</span><span class="sxs-lookup"><span data-stu-id="181b8-204">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="181b8-205">IBM Connections Chat Cloud
</span><span class="sxs-lookup"><span data-stu-id="181b8-205">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="181b8-206">IBM Connections Social Cloud
</span><span class="sxs-lookup"><span data-stu-id="181b8-206">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="181b8-207">IBM SameTime Advanced 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="181b8-207">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="181b8-208">IBM SameTime Communicate 9.0
</span><span class="sxs-lookup"><span data-stu-id="181b8-208">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="181b8-209">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
</span><span class="sxs-lookup"><span data-stu-id="181b8-209">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="181b8-210">IBM SameTime Complete 9.0
</span><span class="sxs-lookup"><span data-stu-id="181b8-210">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="181b8-211">IBM SameTime Conference 9.0
</span><span class="sxs-lookup"><span data-stu-id="181b8-211">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="181b8-212">IBM SameTime Meeting 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="181b8-212">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="181b8-213">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="181b8-213">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="181b8-214">IM Import
</span><span class="sxs-lookup"><span data-stu-id="181b8-214">IM Import</span></span>
    
- <span data-ttu-id="181b8-215">IM Real Time Logging and Policy
</span><span class="sxs-lookup"><span data-stu-id="181b8-215">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="181b8-216">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="181b8-216">Indii Messenger</span></span>
    
- <span data-ttu-id="181b8-217">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="181b8-217">Instant Bloomberg</span></span>
    
- <span data-ttu-id="181b8-218">IRC</span><span class="sxs-lookup"><span data-stu-id="181b8-218">IRC</span></span>
    
- <span data-ttu-id="181b8-219">Jive
</span><span class="sxs-lookup"><span data-stu-id="181b8-219">Jive</span></span>
    
- <span data-ttu-id="181b8-220">Jive 6 Real Time Logging (v6, v7)
</span><span class="sxs-lookup"><span data-stu-id="181b8-220">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="181b8-221">Jive Import</span><span class="sxs-lookup"><span data-stu-id="181b8-221">Jive Import</span></span>
    
- <span data-ttu-id="181b8-222">JXTA</span><span class="sxs-lookup"><span data-stu-id="181b8-222">JXTA</span></span>
    
- <span data-ttu-id="181b8-223">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="181b8-223">LinkedIn</span></span>
    
- <span data-ttu-id="181b8-224">
Microsoft Lync (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="181b8-224">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="181b8-225">MFTP</span><span class="sxs-lookup"><span data-stu-id="181b8-225">MFTP</span></span>
    
- <span data-ttu-id="181b8-226">Microsoft Lync 2013 Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-226">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="181b8-227">Microsoft SharePoint (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="181b8-227">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="181b8-228">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="181b8-228">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="181b8-229">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="181b8-229">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="181b8-230">MindAlign</span><span class="sxs-lookup"><span data-stu-id="181b8-230">MindAlign</span></span>
    
- <span data-ttu-id="181b8-231">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="181b8-231">Mobile Guard</span></span>
    
- <span data-ttu-id="181b8-232">MSN</span><span class="sxs-lookup"><span data-stu-id="181b8-232">MSN</span></span>
    
- <span data-ttu-id="181b8-233">My Space</span><span class="sxs-lookup"><span data-stu-id="181b8-233">My Space</span></span>
    
- <span data-ttu-id="181b8-234">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="181b8-234">NEONetwork</span></span>
    
- <span data-ttu-id="181b8-235">Office 365 Lync Dedicated
</span><span class="sxs-lookup"><span data-stu-id="181b8-235">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="181b8-236">Messaggistica istantanea condivisa di Office 365
</span><span class="sxs-lookup"><span data-stu-id="181b8-236">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="181b8-237">Pinterest</span><span class="sxs-lookup"><span data-stu-id="181b8-237">Pinterest</span></span>
    
- <span data-ttu-id="181b8-238">Pivot</span><span class="sxs-lookup"><span data-stu-id="181b8-238">Pivot</span></span>
    
- <span data-ttu-id="181b8-239">QQ</span><span class="sxs-lookup"><span data-stu-id="181b8-239">QQ</span></span>
    
- <span data-ttu-id="181b8-240">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="181b8-240">Skype for Business 2015</span></span>
    
- <span data-ttu-id="181b8-241">SoftEther</span><span class="sxs-lookup"><span data-stu-id="181b8-241">SoftEther</span></span>
    
- <span data-ttu-id="181b8-242">Symphony
</span><span class="sxs-lookup"><span data-stu-id="181b8-242">Symphony</span></span>
    
- <span data-ttu-id="181b8-243">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="181b8-243">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="181b8-244">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="181b8-244">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="181b8-245">Tor</span><span class="sxs-lookup"><span data-stu-id="181b8-245">Tor</span></span>
    
- <span data-ttu-id="181b8-246">TTT</span><span class="sxs-lookup"><span data-stu-id="181b8-246">TTT</span></span>
    
- <span data-ttu-id="181b8-247">Twitter</span><span class="sxs-lookup"><span data-stu-id="181b8-247">Twitter</span></span>
    
- <span data-ttu-id="181b8-248">WinMX</span><span class="sxs-lookup"><span data-stu-id="181b8-248">WinMX</span></span>
    
- <span data-ttu-id="181b8-249">Winny</span><span class="sxs-lookup"><span data-stu-id="181b8-249">Winny</span></span>
    
- <span data-ttu-id="181b8-250">Yahoo
</span><span class="sxs-lookup"><span data-stu-id="181b8-250">Yahoo</span></span>
    
- <span data-ttu-id="181b8-251">Yammer</span><span class="sxs-lookup"><span data-stu-id="181b8-251">Yammer</span></span>
    
- <span data-ttu-id="181b8-252">YouTube</span><span class="sxs-lookup"><span data-stu-id="181b8-252">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="181b8-253">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="181b8-253">ArchiveSocial</span></span>

<span data-ttu-id="181b8-254">[ArchiveSocial](https://www.archivesocial.com) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-254">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="181b8-255">Facebook</span><span class="sxs-lookup"><span data-stu-id="181b8-255">Facebook</span></span>
    
- <span data-ttu-id="181b8-256">Flickr
</span><span class="sxs-lookup"><span data-stu-id="181b8-256">Flickr</span></span>
    
- <span data-ttu-id="181b8-257">Instagram
</span><span class="sxs-lookup"><span data-stu-id="181b8-257">Instagram</span></span>
    
- <span data-ttu-id="181b8-258">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="181b8-258">LinkedIn</span></span>
    
- <span data-ttu-id="181b8-259">Pinterest</span><span class="sxs-lookup"><span data-stu-id="181b8-259">Pinterest</span></span>
    
- <span data-ttu-id="181b8-260">Twitter</span><span class="sxs-lookup"><span data-stu-id="181b8-260">Twitter</span></span>
    
- <span data-ttu-id="181b8-261">YouTube</span><span class="sxs-lookup"><span data-stu-id="181b8-261">YouTube</span></span>
    
- <span data-ttu-id="181b8-262">Vimeo</span><span class="sxs-lookup"><span data-stu-id="181b8-262">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="181b8-263">Globanet</span><span class="sxs-lookup"><span data-stu-id="181b8-263">Globanet</span></span>

<span data-ttu-id="181b8-264">[Globanet](https://www.globanet.com) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-264">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="181b8-265">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="181b8-265">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="181b8-266">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="181b8-266">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="181b8-267">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="181b8-267">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="181b8-268">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="181b8-268">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="181b8-269">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="181b8-269">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="181b8-270">Chat Bloomber
</span><span class="sxs-lookup"><span data-stu-id="181b8-270">Bloomberg Chat</span></span>
    
- <span data-ttu-id="181b8-271">Posta Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="181b8-271">Bloomberg Mail</span></span>
    
- <span data-ttu-id="181b8-272">Box
</span><span class="sxs-lookup"><span data-stu-id="181b8-272">Box</span></span>
    
- <span data-ttu-id="181b8-273">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="181b8-273">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="181b8-274">Messaggistica Istantanea Cisco &amp; Server presenze (v10, SU1 v10.5.1, v11.0, v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="181b8-274">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="181b8-275">Cisco Webex team</span><span class="sxs-lookup"><span data-stu-id="181b8-275">Cisco Webex Teams</span></span>

- <span data-ttu-id="181b8-276">Area di lavoro Citrix &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="181b8-276">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="181b8-277">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="181b8-277">CrowdCompass</span></span>

- <span data-ttu-id="181b8-278">File di testo delimitati personalizzati
</span><span class="sxs-lookup"><span data-stu-id="181b8-278">Custom delimited text files</span></span>
    
- <span data-ttu-id="181b8-279">File XML personalizzati
</span><span class="sxs-lookup"><span data-stu-id="181b8-279">Custom XML files</span></span>
    
- <span data-ttu-id="181b8-280">Facebook (pagine)</span><span class="sxs-lookup"><span data-stu-id="181b8-280">Facebook (Pages)</span></span>
    
- <span data-ttu-id="181b8-281">Factset
</span><span class="sxs-lookup"><span data-stu-id="181b8-281">Factset</span></span>
    
- <span data-ttu-id="181b8-282">FXConnect</span><span class="sxs-lookup"><span data-stu-id="181b8-282">FXConnect</span></span>
    
- <span data-ttu-id="181b8-283">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="181b8-283">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="181b8-284">Jive
</span><span class="sxs-lookup"><span data-stu-id="181b8-284">Jive</span></span>
    
- <span data-ttu-id="181b8-285">XIP Macgregor
</span><span class="sxs-lookup"><span data-stu-id="181b8-285">Macgregor XIP</span></span>

- <span data-ttu-id="181b8-286">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="181b8-286">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="181b8-287">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="181b8-287">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="181b8-288">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="181b8-288">Microsoft Teams</span></span>
       
- <span data-ttu-id="181b8-289">Microsoft Yammer
</span><span class="sxs-lookup"><span data-stu-id="181b8-289">Microsoft Yammer</span></span>
    
- <span data-ttu-id="181b8-290">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="181b8-290">Mobile Guard</span></span>
    
- <span data-ttu-id="181b8-291">Pivot</span><span class="sxs-lookup"><span data-stu-id="181b8-291">Pivot</span></span>
    
- <span data-ttu-id="181b8-292">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="181b8-292">Salesforce Chatter</span></span>

- <span data-ttu-id="181b8-293">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="181b8-293">Skype for Business Online</span></span>
    
- <span data-ttu-id="181b8-294">Skype for Business, versioni 2007 R2 - 2016 (locale)
</span><span class="sxs-lookup"><span data-stu-id="181b8-294">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="181b8-295">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="181b8-295">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="181b8-296">Symphony
</span><span class="sxs-lookup"><span data-stu-id="181b8-296">Symphony</span></span>
    
- <span data-ttu-id="181b8-297">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="181b8-297">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="181b8-298">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="181b8-298">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="181b8-299">Thomson Reuters Dealings 3000/FX Trading
</span><span class="sxs-lookup"><span data-stu-id="181b8-299">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="181b8-300">Twitter</span><span class="sxs-lookup"><span data-stu-id="181b8-300">Twitter</span></span>
    
- <span data-ttu-id="181b8-301">Chat UBS
</span><span class="sxs-lookup"><span data-stu-id="181b8-301">UBS Chat</span></span>
    
- <span data-ttu-id="181b8-302">YouTube</span><span class="sxs-lookup"><span data-stu-id="181b8-302">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="181b8-303">OpenText</span><span class="sxs-lookup"><span data-stu-id="181b8-303">OpenText</span></span>

<span data-ttu-id="181b8-304">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-304">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="181b8-305">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="181b8-305">Axs Encrypted</span></span>
    
- <span data-ttu-id="181b8-306">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="181b8-306">Axs Exchange</span></span>
    
- <span data-ttu-id="181b8-307">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="181b8-307">Axs Local Archive</span></span>
    
- <span data-ttu-id="181b8-308">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="181b8-308">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="181b8-309">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="181b8-309">Axs Signed</span></span>
    
- <span data-ttu-id="181b8-310">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="181b8-310">Bloomberg</span></span>
    
- <span data-ttu-id="181b8-311">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="181b8-311">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="181b8-312">Verba</span><span class="sxs-lookup"><span data-stu-id="181b8-312">Verba</span></span>

<span data-ttu-id="181b8-313">[Verba](https://www.verba.com) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-313">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="181b8-314">Avaya Aura Video
</span><span class="sxs-lookup"><span data-stu-id="181b8-314">Avaya Aura Video</span></span>
    
- <span data-ttu-id="181b8-315">Avaya Aura Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-315">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="181b8-316">Avtec Radio
</span><span class="sxs-lookup"><span data-stu-id="181b8-316">Avtec Radio</span></span>
    
- <span data-ttu-id="181b8-317">Bosch/Telex Radio
</span><span class="sxs-lookup"><span data-stu-id="181b8-317">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="181b8-318">BroadSoft Video
</span><span class="sxs-lookup"><span data-stu-id="181b8-318">BroadSoft Video</span></span>
    
- <span data-ttu-id="181b8-319">BroadSoft Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-319">BroadSoft Voice</span></span>
    
- <span data-ttu-id="181b8-320">Centile Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-320">Centile Voice</span></span>
    
- <span data-ttu-id="181b8-321">Messaggistica immediata Cisco Jabber
</span><span class="sxs-lookup"><span data-stu-id="181b8-321">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="181b8-322">Cisco UC Video
</span><span class="sxs-lookup"><span data-stu-id="181b8-322">Cisco UC Video</span></span>
    
- <span data-ttu-id="181b8-323">Cisco UC Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-323">Cisco UC Voice</span></span>
    
- <span data-ttu-id="181b8-324">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="181b8-324">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="181b8-325">Cisco UCCX/UCCE vocale</span><span class="sxs-lookup"><span data-stu-id="181b8-325">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="181b8-326">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="181b8-326">ESChat Radio</span></span>
    
- <span data-ttu-id="181b8-327">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="181b8-327">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="181b8-328">IP Trade Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-328">IP Trade Voice</span></span>
    
- <span data-ttu-id="181b8-329">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="181b8-329">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="181b8-330">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="181b8-330">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="181b8-331">Mitel MiContact Center per Lync (prairieFyre) 
</span><span class="sxs-lookup"><span data-stu-id="181b8-331">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="181b8-332">Oracle / Acme Packet Session Border Controller Video  
</span><span class="sxs-lookup"><span data-stu-id="181b8-332">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="181b8-333">Oracle / Acme Packet Session Border Controller Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-333">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="181b8-334">Singtel Mobile Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-334">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="181b8-335">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="181b8-335">SIPREC Video</span></span>
    
-  <span data-ttu-id="181b8-336">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="181b8-336">SIPREC Voice</span></span> 
    
- <span data-ttu-id="181b8-337">Messaggistica immediata Skype for Business / Lync
</span><span class="sxs-lookup"><span data-stu-id="181b8-337">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="181b8-338">Video Skype for Business / Lync
</span><span class="sxs-lookup"><span data-stu-id="181b8-338">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="181b8-339">Chiamate Skype for Business / Lync
</span><span class="sxs-lookup"><span data-stu-id="181b8-339">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="181b8-340">Speakerbus Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-340">Speakerbus Voice</span></span>
    
- <span data-ttu-id="181b8-341">Video SIP/H.323 standard 
</span><span class="sxs-lookup"><span data-stu-id="181b8-341">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="181b8-342">Chiamate SIP/H.323 standard 
</span><span class="sxs-lookup"><span data-stu-id="181b8-342">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="181b8-343">Truphone Voice
</span><span class="sxs-lookup"><span data-stu-id="181b8-343">Truphone Voice</span></span>
    
- <span data-ttu-id="181b8-344">TwistedPair Radio
</span><span class="sxs-lookup"><span data-stu-id="181b8-344">TwistedPair Radio</span></span>
    
- <span data-ttu-id="181b8-345">Schermata di Computer Desktop di Windows 
</span><span class="sxs-lookup"><span data-stu-id="181b8-345">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="181b8-346">Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="181b8-346">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="181b8-p109">Ecco la procedura per la creazione e configurazione di una cassetta postale di dati di terze parti per l'importazione di dati in Office 365. Nel precedente illustrati, vengono importati elementi a questa cassetta postale se il connettore partner non può eseguire il mapping l'ID dell'elemento a un account utente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="181b8-p109">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="181b8-349">**Completare queste attività nell'interfaccia di amministrazione di Office 365**</span><span class="sxs-lookup"><span data-stu-id="181b8-349">**Complete these tasks in the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="181b8-p110">Creare un nuovo account utente in Office 365 e assegnare una licenza di Exchange Online piano 2; vedere [aggiungere utenti a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Per effettuare la cassetta postale di conservazione per controversia legale o abilitare una cassetta postale di archiviazione con una quota di archiviazione illimitato è necessaria una licenza piano 2.</span><span class="sxs-lookup"><span data-stu-id="181b8-p110">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="181b8-352">Aggiungere l'account utente per la cassetta postale di dati di terze parti per il ruolo di amministratore **di amministrazione di Exchange** in Office 365, vedere [assegnare ruoli di amministratore in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="181b8-352">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="181b8-p111">Annotare le credenziali per l'account utente. È necessario fornirle al partner, come descritto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="181b8-p111">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="181b8-355">**Completare queste attività nell'interfaccia di amministrazione di Exchange**</span><span class="sxs-lookup"><span data-stu-id="181b8-355">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="181b8-p112">Nascondere la cassetta postale di terze parti dati dalla Rubrica e altri elenchi di indirizzi nell'organizzazione. vedere [Gestione cassette postali degli utenti](https://go.microsoft.com/fwlink/p/?LinkId=616058). In alternativa, è possibile eseguire il seguente comando PowerShell:</span><span class="sxs-lookup"><span data-stu-id="181b8-p112">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="181b8-358">Assegnare l'autorizzazione **FullAccess** per la cassetta postale di dati di terze parti in modo che gli amministratori o responsabili della conformità aprire la cassetta postale di terze parti dati nel client desktop Outlook; vedere [Manage permissions per i destinatari](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="181b8-358">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="181b8-359">Abilitare le seguenti funzionalità Office 365 relativi alla conformità per la cassetta postale di dati di terze parti:</span><span class="sxs-lookup"><span data-stu-id="181b8-359">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="181b8-p113">Abilitare la cassetta postale di archivio; vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md). Consente di liberare spazio nella cassetta postale principale mediante l'impostazione di criteri di archiviazione che sposta gli elementi di dati di terze parti per la cassetta postale di archivio. In questo modo sarà con archiviazione illimitata per i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="181b8-p113">Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="181b8-p114">Effettuare la cassetta postale di dati di terze parti controversie legali. È inoltre possibile applicare un criterio di conservazione di Office 365 in Office 365 Security &amp; centro conformità. Esecuzione di questa cassetta postale in attesa verrà conservazione degli elementi di dati di terze parti (tempo indeterminato o per un periodo specificato) e impedire che venga eliminato dalla cassetta postale. Vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-p114">Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. See one of the following topics:</span></span>
    
      - [<span data-ttu-id="181b8-367">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="181b8-367">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="181b8-368">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="181b8-368">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="181b8-p115">Abilitare la registrazione per l'accesso alla cassetta postale di dati di terze parti, proprietario, delegato e amministrazione di controllo delle cassette postali vedere [abilitare il controllo in Office 365](enable-mailbox-auditing.md). In questo modo è possibile controllare tutte le attività eseguite da qualsiasi utente che ha accesso alla cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="181b8-p115">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="181b8-371">Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="181b8-371">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="181b8-p116">Il passaggio successivo consiste nel configurare cassette postali degli utenti per il supporto dei dati di terze parti. Completare queste attività utilizzando l'interfaccia di amministrazione di Exchange o utilizzando i cmdlet di Windows PowerShell corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="181b8-p116">The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="181b8-374">Abilitare la cassetta postale di archiviazione per ogni utente. vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="181b8-374">Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="181b8-375">Archiviare le cassette postali utente conservazione per controversia legale o applicare un criterio di conservazione, Office 365 vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-375">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="181b8-376">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="181b8-376">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="181b8-377">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="181b8-377">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="181b8-378">Come precedentemente illustrato, quando si abilita un blocco delle cassette postali, è possibile impostare una durata per definire quanto tempo devono essere conservati gli elementi dell'origine dati di terze parti oppure è possibile scegliere di conservare gli elementi per un periodo di tempo indeterminato.</span><span class="sxs-lookup"><span data-stu-id="181b8-378">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="181b8-379">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="181b8-379">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="181b8-380">Il passaggio finale consiste nel fornire al partner le informazioni seguenti affinché sia in grado di configurare il connettore per connettersi all'organizzazione di Office 365 e importare i dati nelle cassette postali degli utenti e nella cassetta postale dei dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="181b8-380">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="181b8-381">L'endpoint utilizzato per la connessione al servizio Azure in Office 365:</span><span class="sxs-lookup"><span data-stu-id="181b8-381">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="181b8-p117">Accesso in credenziali (ID utente di Office 365 e password) della cassetta postale di dati di terze parti creato nel passaggio 2. Queste credenziali sono necessari in modo che il connettore di partner può accedere e importare gli elementi delle cassette postali utente e la cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="181b8-p117">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
    

  
## <a name="more-information"></a><span data-ttu-id="181b8-384">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="181b8-384">More information</span></span>

- <span data-ttu-id="181b8-p118">Spiegato come precedente, gli elementi alle cassette postali di Exchange come messaggi di posta elettronica vengono importate le origini dati di terze parti. Il connettore partner consente di importare l'elemento utilizzando uno schema necessario per l'API di Office 365. Nella tabella seguente vengono descritte le proprietà del messaggio di un elemento da un'origine dati di terze parti dopo l'importazione di una cassetta postale di Exchange come messaggio di posta elettronica. Nella tabella indica anche se la proprietà message è obbligatoria. Le proprietà obbligatorie devono essere compilate. Se un elemento manca una proprietà obbligatoria, non sarà possibile importare a Office 365. Il processo di importazione restituirà un messaggio di errore che spiega perché un elemento non è stato importato e la proprietà non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="181b8-p118">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="181b8-392">**Proprietà del messaggio**</span><span class="sxs-lookup"><span data-stu-id="181b8-392">**Message property**</span></span>|<span data-ttu-id="181b8-393">**Obbligatorio?**</span><span class="sxs-lookup"><span data-stu-id="181b8-393">**Mandatory?**</span></span>|<span data-ttu-id="181b8-394">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="181b8-394">**Description**</span></span>|<span data-ttu-id="181b8-395">**Valore di esempio**</span><span class="sxs-lookup"><span data-stu-id="181b8-395">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="181b8-396">**FROM**</span><span class="sxs-lookup"><span data-stu-id="181b8-396">**FROM**</span></span> <br/> |<span data-ttu-id="181b8-397">Sì</span><span class="sxs-lookup"><span data-stu-id="181b8-397">Yes</span></span>  <br/> |<span data-ttu-id="181b8-p119">L'utente che ha creato o l'elemento inviato nell'origine dati di terze parti. Il connettore partner tenterà di mappare l'ID utente dalla voce di origine (ad esempio un handle Twitter) da un account utente di Office 365 per tutti i partecipanti (utenti nei campi FROM e TO). Verrà importata una copia del messaggio alla cassetta postale di tutti gli altri partecipanti. Se nessuno dei partecipanti dall'elemento può essere associata a un account utente di Office 365, l'elemento verrà importata alla cassetta postale di archiviazione di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="181b8-p119">The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  </span></span><br/> <br/> <span data-ttu-id="181b8-p120">Il partecipante che viene identificato come mittente dell'elemento deve disporre di una cassetta postale attiva nell'organizzazione di Office 365 importato per l'elemento. Se il mittente non dispone di una cassetta postale attiva, viene restituito l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="181b8-p120">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="181b8-404">**TO**</span><span class="sxs-lookup"><span data-stu-id="181b8-404">**TO**</span></span> <br/> |<span data-ttu-id="181b8-405">Sì</span><span class="sxs-lookup"><span data-stu-id="181b8-405">Yes</span></span>  <br/> |<span data-ttu-id="181b8-406">L'utente che ha ricevuto un elemento, se applicabile per un elemento nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="181b8-406">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="181b8-407">**SUBJECT**</span><span class="sxs-lookup"><span data-stu-id="181b8-407">**SUBJECT**</span></span> <br/> |<span data-ttu-id="181b8-408">No</span><span class="sxs-lookup"><span data-stu-id="181b8-408">No</span></span>  <br/> |<span data-ttu-id="181b8-409">L'oggetto dell'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="181b8-409">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="181b8-410">**DATA**</span><span class="sxs-lookup"><span data-stu-id="181b8-410">**DATE**</span></span> <br/> |<span data-ttu-id="181b8-411">Sì</span><span class="sxs-lookup"><span data-stu-id="181b8-411">Yes</span></span>  <br/> |<span data-ttu-id="181b8-412">La data in cui l'elemento è stato originariamente creato o inserito nell'origine dati del cliente; ad esempio, la data in cui è stato twittato un messaggio di Twitter.</span><span class="sxs-lookup"><span data-stu-id="181b8-412">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="181b8-413">**BODY**</span><span class="sxs-lookup"><span data-stu-id="181b8-413">**BODY**</span></span> <br/> |<span data-ttu-id="181b8-414">No</span><span class="sxs-lookup"><span data-stu-id="181b8-414">No</span></span>  <br/> |<span data-ttu-id="181b8-p121">Il contenuto del messaggio o post. Per alcune origini dati, il contenuto di questa proprietà può corrispondere a quella come il contenuto per la proprietà **SUBJECT** . Durante il processo di importazione, il connettore partner tenterà di mantenere massima fedeltà dall'origine di contenuto possibile. Se possibile file, grafica o altri contenuti provenienti dal corpo dell'elemento di origine sono incluso nella proprietà. In caso contrario, il contenuto dall'elemento di origine è incluso nella proprietà **allegato** . Il contenuto della proprietà dipenderà sul connettore di partner e alla capacità della piattaforma di origine.</span><span class="sxs-lookup"><span data-stu-id="181b8-p121">The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  </span></span><br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="181b8-421">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="181b8-421">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="181b8-422">No</span><span class="sxs-lookup"><span data-stu-id="181b8-422">No</span></span>  <br/> |<span data-ttu-id="181b8-p122">Se un elemento nell'origine dati (ad esempio, visualizzato in una conversazione di messaggistica immediata o Twitter) è un file allegato o includere le immagini, il partner connettersi will primo tentativo di essere inclusi gli allegati nella proprietà **BODY** . Se ciò non è possibile, quindi viene aggiunta al * * allegato * * proprietà. Altri esempi di allegati sono apprezzamenti in Facebook, metadati di origine di contenuto e le risposte a un messaggio o post.</span><span class="sxs-lookup"><span data-stu-id="181b8-p122">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the ** ATTACHMENT ** property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  </span></span><br/> | `image.gif` <br/> |
    |<span data-ttu-id="181b8-426">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="181b8-426">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="181b8-427">Sì</span><span class="sxs-lookup"><span data-stu-id="181b8-427">Yes</span></span>  <br/> | <span data-ttu-id="181b8-p123">Si tratta di una proprietà multivalore, che viene creata e compilata dal connettore di partner. Il formato di questa proprietà è `IPM.NOTE.Source.Event`. (Questa proprietà deve iniziare con `IPM.NOTE`; in questo formato è simile a quella per la `IPM.NOTE.X` classe messaggio.) Questa proprietà include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="181b8-p123">This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  </span></span><br/><br/><span data-ttu-id="181b8-431">`Source`-Indica l'origine dati di terze parti. ad esempio Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="181b8-431">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="181b8-p124">`Event`-Indica il tipo di attività eseguita nell'origine dati di terze parti che ha generato gli elementi; ad esempio, visualizzato in un post di Facebook o Twitter. Gli eventi sono specifici per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="181b8-p124">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  </span></span><br/> <br/>  <span data-ttu-id="181b8-p125">Uno scopo di questa proprietà è per filtrare elementi specifici in base all'origine dati in un elemento ha dato origine o in base al tipo di evento. In una ricerca eDiscovery, ad esempio, è possibile creare una query di ricerca per trovare tutti i tweets che sono stati inviati da un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="181b8-p125">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  </span></span><br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="181b8-p126">Quando gli elementi vengono importati correttamente le cassette postali in Office 365, viene restituito un identificatore univoco al chiamante come parte della risposta HTTP. Questo identificatore, viene chiamato `x-IngestionCorrelationID`, può essere utilizzata per scopi di risoluzione dei problemi successivi da parte dei partner per tenere traccia end-to-end di elementi. È consigliabile che i partner acquisire informazioni e accedere conseguenza dal lato. Di seguito è riportato un esempio di una risposta HTTP che mostra l'identificatore:</span><span class="sxs-lookup"><span data-stu-id="181b8-p126">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="181b8-p127">È possibile utilizzare lo strumento di ricerca del contenuto in Office 365 Security &amp; centro conformità per cercare gli elementi che sono stati importati alle cassette postali in Office 365 da un'origine dati di terze parti. Per eseguire la ricerca in modo specifico per questi elementi importati, è possibile utilizzare le seguenti coppie di valore della proprietà messaggio nella casella parole chiave per la ricerca del contenuto. .</span><span class="sxs-lookup"><span data-stu-id="181b8-p127">You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. .</span></span> 
    
  - <span data-ttu-id="181b8-p128">**`kind:externaldata`**-Utilizzare questo coppia valore della proprietà per cercare tutti i tipi di dati di terze parti. Ad esempio, per cercare gli elementi che sono stati importati da un'origine dati di terze parti e contenuto la parola "contoso" nella proprietà Subject dell'elemento importato, utilizzare la query con parole chiave `kind:externaldata AND subject:contoso`.</span><span class="sxs-lookup"><span data-stu-id="181b8-p128">**`kind:externaldata`** - Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="181b8-p129">**`itemclass:ipm.externaldata.<third-party data type>`**-Utilizzare questo coppia valore della proprietà di ricerca solo un tipo di impostazione dei dati di terze parti. Ad esempio, per eseguire la ricerca solo dati Facebook che contiene la parola "contoso" nella proprietà Subject, utilizzare la query con parole chiave `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span><span class="sxs-lookup"><span data-stu-id="181b8-p129">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="181b8-447">Per un elenco completo dei valori da utilizzare per i tipi di dati di terze parti per la `itemclass` proprietà, vedere [Utilizzo della ricerca contenuto per cercare i dati di terze parti che è stati importati a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="181b8-447">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="181b8-448">Per ulteriori informazioni sull'utilizzo di Ricerca contenuto e sulla creazione di query di ricerca con parole chiave, vedere:</span><span class="sxs-lookup"><span data-stu-id="181b8-448">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="181b8-449">Ricerca del contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="181b8-449">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="181b8-450">Query delle parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="181b8-450">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
