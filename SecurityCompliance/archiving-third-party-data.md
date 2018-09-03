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
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="e3f2b-105">Archiviazione dei dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="e3f2b-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="e3f2b-p102">Consente di Office 365 gli amministratori di importare e archiviazione dei dati di terze parti da piattaforme di social networking, messaggistica immediata piattaforme e piattaforme di collaborazione documento, alle cassette postali nell'organizzazione Office 365. Esempi di origini dati di terze parti che è possibile importare in Office 365 includono:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p102">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="e3f2b-108">**Social** - Twitter, Facebook, Yammer e LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e3f2b-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="e3f2b-109">**Messaggistica istantanea** - Yahoo Messenger, GoogleTalk e Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="e3f2b-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="e3f2b-110">**Collaborazione sui documenti** - casella e dell'area di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="e3f2b-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="e3f2b-111">**Settori verticali** - gestione delle relazioni dei clienti (ad esempio traffico correlato forza vendita) e Financials (ad esempio Thomson Reuters e Bloomberg)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="e3f2b-112">**La messaggistica di testo SMS /** - BlackBerry</span><span class="sxs-lookup"><span data-stu-id="e3f2b-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="e3f2b-p103">Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio i criteri di conservazione conservazione per controversia legale, ricerca contenuto, archiviazione sul posto, controllo e Office 365, ovvero a tali dati. Ad esempio, quando una cassetta postale viene messo in attesa di conservazione per controversia, verranno mantenuti i dati di terze parti. È possibile cercare dati di terze parti tramite ricerca del contenuto. Oppure è possibile applicare l'archiviazione e i criteri di conservazione ai dati di terze parti nello stesso modo in cui è possibile utilizzare per i dati di Microsoft. In pratica, l'archiviazione dei dati di terze parti in Office 365 consentono alle organizzazioni garantire la conformità con criteri normativi e pubblico.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p103">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="e3f2b-118">Ecco una panoramica del processo e i passaggi necessari per importare i dati di terze parti a Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="e3f2b-119">Passaggio 1: trovare un partner di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e3f2b-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="e3f2b-120">Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="e3f2b-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="e3f2b-121">Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e3f2b-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="e3f2b-122">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="e3f2b-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="e3f2b-123">Passaggio 5: Registrare il connettore di terze parti dati in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e3f2b-123">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="e3f2b-124">Processo di importazione dei dati di terze parti come funziona ></span><span class="sxs-lookup"><span data-stu-id="e3f2b-124">How the third-party data import process works></span></span>

<span data-ttu-id="e3f2b-125">Nella figura e nella descrizione seguenti viene illustrato il processo di importazione di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-125">The following illustration and description explain how the third-party data import process works.</span></span>
  
![Funzionamento del processo di importazione dei dati di terze parti](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="e3f2b-127">Clienti può essere utilizzato con i partner della scelta per configurare un connettore che verrà estrarre gli elementi dall'origine dati di terze parti e quindi importato quegli elementi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-127">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="e3f2b-p104">Il connettore partner si connette a origini dati di terze parti tramite un'API di terze parti (su base pianificata o come configurati) e vengono estratte elementi dall'origine dati. Il connettore partner converte il contenuto di un elemento in un formato dei messaggi di posta elettronica. Vedere la sezione [informazioni](#more-information) per una descrizione dello schema di formato di messaggio.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p104">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="e3f2b-131">Connettore partner si connette al servizio Azure in Office 365 tramite servizi Web Exchange (EWS) da un punto finale noto.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-131">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="e3f2b-p105">Gli elementi vengono importati nella cassetta postale di un utente specifico oppure in una cassetta postale generale di dati di terze parti. Il fatto che un elemento sia importato nella cassetta postale di un utente specifico o nella cassetta postale di dati di terze parti dipende dai seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="e3f2b-p106">r. **gli elementi che presentano un ID utente che corrisponde a un account utente di Office 365** - se il connettore di partner è possibile mappare l'ID dell'elemento nell'origine dati di terze parti a uno specifico utente che ID in Office 365, l'elemento viene copiato nella cartella **Elimina** l'utente Cartella degli elementi ripristinabili. Gli utenti non possono accedere agli elementi nella cartella Elimina. Tuttavia, è possibile utilizzare gli strumenti di Office 365 eDiscovery per cercare gli elementi nella cartella Elimina.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p106">a. **Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="e3f2b-p107">b. **gli elementi che non dispongono di un ID utente che corrisponde a un account utente di Office 365** : il connettore di partner è possibile connettere l'ID utente di un elemento a un utente specifico che ID in Office 365, l'elemento viene copiato nella cartella **posta in arrivo** della cassetta postale di dati di terze parti. Importazione di elementi di posta in arrivo consente una persona all'interno dell'organizzazione per l'accesso alla cassetta postale di terze parti per visualizzare e gestire tali elementi e verificare se è necessario prevedere nella configurazione del connettore partner eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p107">b. **Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="e3f2b-141">Passaggio 1: trovare un partner di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e3f2b-141">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="e3f2b-p108">Un ruolo fondamentale per l'archiviazione dei dati di terze parti in Office 365 è la ricerca e sull'utilizzo di un partner Microsoft è specializzato in l'acquisizione dei dati da un'origine dati di terze parti e l'importazione in Office 365. Dopo aver importato i dati, possono essere archiviato e mantenuta lungo con l'organizzazione di altri dati di Microsoft, ad esempio documenti di SharePoint e OneDrive for Business e posta elettronica di Exchange. Un partner consente di creare un connettore che estrae dati da origini dati di terze parti dell'organizzazione (ad esempio BlackBerry, Facebook, Google +, Reuters Thomson, Twitter e YouTube) e passa tali dati a un'API di Office 365 che importare gli elementi nelle cassette postali di Exchange come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p108">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="e3f2b-145">Nelle sezioni seguenti vengono elencati i partner Microsoft e le origini dati di terze parti che supportano, ovvero che partecipano al programma per l'archiviazione dei dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-145">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="e3f2b-146">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="e3f2b-146">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="e3f2b-147">Actiance</span><span class="sxs-lookup"><span data-stu-id="e3f2b-147">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="e3f2b-148">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="e3f2b-148">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="e3f2b-149">Globanet</span><span class="sxs-lookup"><span data-stu-id="e3f2b-149">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="e3f2b-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="e3f2b-150">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="e3f2b-151">Verba</span><span class="sxs-lookup"><span data-stu-id="e3f2b-151">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="e3f2b-152">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="e3f2b-152">17a-4 LLC</span></span>

<span data-ttu-id="e3f2b-153">17a-4 LLC supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-153">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="e3f2b-154">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="e3f2b-154">BlackBerry</span></span>
    
- <span data-ttu-id="e3f2b-155">Flussi di dati di Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e3f2b-155">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="e3f2b-156">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="e3f2b-156">Cisco Jabber</span></span>
    
- <span data-ttu-id="e3f2b-157">FactSet</span><span class="sxs-lookup"><span data-stu-id="e3f2b-157">FactSet</span></span>
    
- <span data-ttu-id="e3f2b-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="e3f2b-158">HipChat</span></span>
    
- <span data-ttu-id="e3f2b-159">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="e3f2b-159">InvestEdge</span></span>
    
- <span data-ttu-id="e3f2b-160">LivePerson</span><span class="sxs-lookup"><span data-stu-id="e3f2b-160">LivePerson</span></span>
    
- <span data-ttu-id="e3f2b-161">
Flussi di dati MessageLabs
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-161">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="e3f2b-162">OpenText</span><span class="sxs-lookup"><span data-stu-id="e3f2b-162">OpenText</span></span>
    
- <span data-ttu-id="e3f2b-163">Guida "click-to-call" di Oracle/ATG
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-163">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="e3f2b-164">Pivot IMTRADER
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-164">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="e3f2b-165">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="e3f2b-165">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="e3f2b-166">MindAlign</span><span class="sxs-lookup"><span data-stu-id="e3f2b-166">MindAlign</span></span>
    
- <span data-ttu-id="e3f2b-167">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-167">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="e3f2b-168">
Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-168">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="e3f2b-169">
Skype for Business Online (Lync Online)
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-169">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="e3f2b-170">Database SQL</span><span class="sxs-lookup"><span data-stu-id="e3f2b-170">SQL Databases</span></span>
    
- <span data-ttu-id="e3f2b-171">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-171">Squawker</span></span>
    
- <span data-ttu-id="e3f2b-172">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-172">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="e3f2b-173">Actiance</span><span class="sxs-lookup"><span data-stu-id="e3f2b-173">Actiance</span></span>

<span data-ttu-id="e3f2b-174">[Actiance](https://www.actiance.com) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-174">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e3f2b-175">OBIETTIVO</span><span class="sxs-lookup"><span data-stu-id="e3f2b-175">AIM</span></span>
    
- <span data-ttu-id="e3f2b-176">American Idol</span><span class="sxs-lookup"><span data-stu-id="e3f2b-176">American Idol</span></span>
    
- <span data-ttu-id="e3f2b-177">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="e3f2b-177">Apple Juice</span></span>
    
- <span data-ttu-id="e3f2b-178">
AOL con client Pivot
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-178">AOL with Pivot client</span></span>
    
- <span data-ttu-id="e3f2b-179">Ares</span><span class="sxs-lookup"><span data-stu-id="e3f2b-179">Ares</span></span>
    
- <span data-ttu-id="e3f2b-180">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="e3f2b-180">Bazaar Voice</span></span>
    
- <span data-ttu-id="e3f2b-181">Bear Share</span><span class="sxs-lookup"><span data-stu-id="e3f2b-181">Bear Share</span></span>
    
- <span data-ttu-id="e3f2b-182">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="e3f2b-182">Bit Torrent</span></span>
    
- <span data-ttu-id="e3f2b-183">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-183">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e3f2b-184">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-184">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e3f2b-185">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-185">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e3f2b-186">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-186">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e3f2b-187">Posta Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-187">Bloomberg Mail</span></span>
    
- <span data-ttu-id="e3f2b-188">CellTrust</span><span class="sxs-lookup"><span data-stu-id="e3f2b-188">CellTrust</span></span>
    
- <span data-ttu-id="e3f2b-189">Chat Import
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-189">Chat Import</span></span>
    
- <span data-ttu-id="e3f2b-190">Chat Real Time Logging and Policy
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-190">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="e3f2b-191">Chatter
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-191">Chatter</span></span>
    
- <span data-ttu-id="e3f2b-192">Messaggistica Istantanea Cisco &amp; Server presenze (v9.0.1, v 9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-192">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="e3f2b-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="e3f2b-194">Importazione collaborazione
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-194">Collaboration Import</span></span>
    
- <span data-ttu-id="e3f2b-195">Registrazione di collaborazione in tempo reale
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-195">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="e3f2b-196">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="e3f2b-196">Direct Connect</span></span>
    
- <span data-ttu-id="e3f2b-197">Facebook</span><span class="sxs-lookup"><span data-stu-id="e3f2b-197">Facebook</span></span>
    
- <span data-ttu-id="e3f2b-198">FactSet</span><span class="sxs-lookup"><span data-stu-id="e3f2b-198">FactSet</span></span>
    
- <span data-ttu-id="e3f2b-199">FastTrack</span><span class="sxs-lookup"><span data-stu-id="e3f2b-199">FastTrack</span></span>
    
- <span data-ttu-id="e3f2b-200">Gnutella</span><span class="sxs-lookup"><span data-stu-id="e3f2b-200">Gnutella</span></span>
    
- <span data-ttu-id="e3f2b-201">Google+
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-201">Google+</span></span>
    
- <span data-ttu-id="e3f2b-202">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="e3f2b-202">GoToMyPC</span></span>
    
- <span data-ttu-id="e3f2b-203">Hopster</span><span class="sxs-lookup"><span data-stu-id="e3f2b-203">Hopster</span></span>
    
- <span data-ttu-id="e3f2b-204">HubConnex</span><span class="sxs-lookup"><span data-stu-id="e3f2b-204">HubConnex</span></span>
    
- <span data-ttu-id="e3f2b-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="e3f2b-206">IBM Connections Chat Cloud
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-206">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="e3f2b-207">IBM Connections Social Cloud
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-207">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="e3f2b-208">IBM SameTime Advanced 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-208">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="e3f2b-209">IBM SameTime Communicate 9.0
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-209">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="e3f2b-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="e3f2b-211">IBM SameTime Complete 9.0
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-211">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="e3f2b-212">IBM SameTime Conference 9.0
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-212">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="e3f2b-213">IBM SameTime Meeting 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-213">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="e3f2b-214">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e3f2b-214">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="e3f2b-215">IM Import
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-215">IM Import</span></span>
    
- <span data-ttu-id="e3f2b-216">IM Real Time Logging and Policy
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-216">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="e3f2b-217">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-217">Indii Messenger</span></span>
    
- <span data-ttu-id="e3f2b-218">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-218">Instant Bloomberg</span></span>
    
- <span data-ttu-id="e3f2b-219">IRC</span><span class="sxs-lookup"><span data-stu-id="e3f2b-219">IRC</span></span>
    
- <span data-ttu-id="e3f2b-220">Jive
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-220">Jive</span></span>
    
- <span data-ttu-id="e3f2b-221">Jive 6 Real Time Logging (v6, v7)
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-221">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="e3f2b-222">Jive Import</span><span class="sxs-lookup"><span data-stu-id="e3f2b-222">Jive Import</span></span>
    
- <span data-ttu-id="e3f2b-223">JXTA</span><span class="sxs-lookup"><span data-stu-id="e3f2b-223">JXTA</span></span>
    
- <span data-ttu-id="e3f2b-224">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e3f2b-224">LinkedIn</span></span>
    
- <span data-ttu-id="e3f2b-225">
Microsoft Lync (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-225">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="e3f2b-226">MFTP</span><span class="sxs-lookup"><span data-stu-id="e3f2b-226">MFTP</span></span>
    
- <span data-ttu-id="e3f2b-227">Microsoft Lync 2013 Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-227">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="e3f2b-228">Microsoft SharePoint (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-228">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="e3f2b-229">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e3f2b-229">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="e3f2b-230">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-230">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="e3f2b-231">MindAlign</span><span class="sxs-lookup"><span data-stu-id="e3f2b-231">MindAlign</span></span>
    
- <span data-ttu-id="e3f2b-232">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="e3f2b-232">Mobile Guard</span></span>
    
- <span data-ttu-id="e3f2b-233">MSN</span><span class="sxs-lookup"><span data-stu-id="e3f2b-233">MSN</span></span>
    
- <span data-ttu-id="e3f2b-234">My Space</span><span class="sxs-lookup"><span data-stu-id="e3f2b-234">My Space</span></span>
    
- <span data-ttu-id="e3f2b-235">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="e3f2b-235">NEONetwork</span></span>
    
- <span data-ttu-id="e3f2b-236">Office 365 Lync Dedicated
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-236">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="e3f2b-237">Messaggistica istantanea condivisa di Office 365
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-237">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="e3f2b-238">Pinterest</span><span class="sxs-lookup"><span data-stu-id="e3f2b-238">Pinterest</span></span>
    
- <span data-ttu-id="e3f2b-239">Pivot</span><span class="sxs-lookup"><span data-stu-id="e3f2b-239">Pivot</span></span>
    
- <span data-ttu-id="e3f2b-240">QQ</span><span class="sxs-lookup"><span data-stu-id="e3f2b-240">QQ</span></span>
    
- <span data-ttu-id="e3f2b-241">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="e3f2b-241">Skype for Business 2015</span></span>
    
- <span data-ttu-id="e3f2b-242">SoftEther</span><span class="sxs-lookup"><span data-stu-id="e3f2b-242">SoftEther</span></span>
    
- <span data-ttu-id="e3f2b-243">Symphony
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-243">Symphony</span></span>
    
- <span data-ttu-id="e3f2b-244">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-244">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="e3f2b-245">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-245">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="e3f2b-246">Tor</span><span class="sxs-lookup"><span data-stu-id="e3f2b-246">Tor</span></span>
    
- <span data-ttu-id="e3f2b-247">TTT</span><span class="sxs-lookup"><span data-stu-id="e3f2b-247">TTT</span></span>
    
- <span data-ttu-id="e3f2b-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="e3f2b-248">Twitter</span></span>
    
- <span data-ttu-id="e3f2b-249">WinMX</span><span class="sxs-lookup"><span data-stu-id="e3f2b-249">WinMX</span></span>
    
- <span data-ttu-id="e3f2b-250">Winny</span><span class="sxs-lookup"><span data-stu-id="e3f2b-250">Winny</span></span>
    
- <span data-ttu-id="e3f2b-251">Yahoo
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-251">Yahoo</span></span>
    
- <span data-ttu-id="e3f2b-252">Yammer</span><span class="sxs-lookup"><span data-stu-id="e3f2b-252">Yammer</span></span>
    
- <span data-ttu-id="e3f2b-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="e3f2b-253">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="e3f2b-254">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="e3f2b-254">ArchiveSocial</span></span>

<span data-ttu-id="e3f2b-255">[ArchiveSocial](https://www.archivesocial.com) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-255">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e3f2b-256">Facebook</span><span class="sxs-lookup"><span data-stu-id="e3f2b-256">Facebook</span></span>
    
- <span data-ttu-id="e3f2b-257">Flickr
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-257">Flickr</span></span>
    
- <span data-ttu-id="e3f2b-258">Instagram
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-258">Instagram</span></span>
    
- <span data-ttu-id="e3f2b-259">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e3f2b-259">LinkedIn</span></span>
    
- <span data-ttu-id="e3f2b-260">Pinterest</span><span class="sxs-lookup"><span data-stu-id="e3f2b-260">Pinterest</span></span>
    
- <span data-ttu-id="e3f2b-261">Twitter</span><span class="sxs-lookup"><span data-stu-id="e3f2b-261">Twitter</span></span>
    
- <span data-ttu-id="e3f2b-262">YouTube</span><span class="sxs-lookup"><span data-stu-id="e3f2b-262">YouTube</span></span>
    
- <span data-ttu-id="e3f2b-263">Vimeo</span><span class="sxs-lookup"><span data-stu-id="e3f2b-263">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="e3f2b-264">Globanet</span><span class="sxs-lookup"><span data-stu-id="e3f2b-264">Globanet</span></span>

<span data-ttu-id="e3f2b-265">[Globanet](https://www.globanet.com) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-265">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e3f2b-266">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="e3f2b-266">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="e3f2b-267">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-267">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e3f2b-268">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-268">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e3f2b-269">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-269">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e3f2b-270">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-270">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e3f2b-271">Chat Bloomber
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-271">Bloomberg Chat</span></span>
    
- <span data-ttu-id="e3f2b-272">Posta Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-272">Bloomberg Mail</span></span>
    
- <span data-ttu-id="e3f2b-273">Box
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-273">Box</span></span>
    
- <span data-ttu-id="e3f2b-274">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e3f2b-274">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="e3f2b-275">Messaggistica Istantanea Cisco &amp; Server presenze (v10, SU1 v10.5.1, v11.0, v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-275">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="e3f2b-276">Cisco Webex team</span><span class="sxs-lookup"><span data-stu-id="e3f2b-276">Cisco Webex Teams</span></span>

- <span data-ttu-id="e3f2b-277">Area di lavoro Citrix &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="e3f2b-277">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="e3f2b-278">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="e3f2b-278">CrowdCompass</span></span>

- <span data-ttu-id="e3f2b-279">File di testo delimitati personalizzati
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-279">Custom delimited text files</span></span>
    
- <span data-ttu-id="e3f2b-280">File XML personalizzati
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-280">Custom XML files</span></span>
    
- <span data-ttu-id="e3f2b-281">Facebook (pagine)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-281">Facebook (Pages)</span></span>
    
- <span data-ttu-id="e3f2b-282">Factset
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-282">Factset</span></span>
    
- <span data-ttu-id="e3f2b-283">FXConnect</span><span class="sxs-lookup"><span data-stu-id="e3f2b-283">FXConnect</span></span>
    
- <span data-ttu-id="e3f2b-284">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e3f2b-284">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="e3f2b-285">Jive
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-285">Jive</span></span>
    
- <span data-ttu-id="e3f2b-286">XIP Macgregor
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-286">Macgregor XIP</span></span>

- <span data-ttu-id="e3f2b-287">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e3f2b-287">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="e3f2b-288">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e3f2b-288">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="e3f2b-289">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e3f2b-289">Microsoft Teams</span></span>
       
- <span data-ttu-id="e3f2b-290">Microsoft Yammer
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-290">Microsoft Yammer</span></span>
    
- <span data-ttu-id="e3f2b-291">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="e3f2b-291">Mobile Guard</span></span>
    
- <span data-ttu-id="e3f2b-292">Pivot</span><span class="sxs-lookup"><span data-stu-id="e3f2b-292">Pivot</span></span>
    
- <span data-ttu-id="e3f2b-293">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e3f2b-293">Salesforce Chatter</span></span>

- <span data-ttu-id="e3f2b-294">Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="e3f2b-294">Skype for Business Online</span></span>
    
- <span data-ttu-id="e3f2b-295">Skype for Business, versioni 2007 R2 - 2016 (locale)
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-295">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="e3f2b-296">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="e3f2b-296">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="e3f2b-297">Symphony
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-297">Symphony</span></span>
    
- <span data-ttu-id="e3f2b-298">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-298">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="e3f2b-299">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-299">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="e3f2b-300">Thomson Reuters Dealings 3000/FX Trading
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-300">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="e3f2b-301">Twitter</span><span class="sxs-lookup"><span data-stu-id="e3f2b-301">Twitter</span></span>
    
- <span data-ttu-id="e3f2b-302">Chat UBS
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-302">UBS Chat</span></span>
    
- <span data-ttu-id="e3f2b-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="e3f2b-303">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="e3f2b-304">OpenText</span><span class="sxs-lookup"><span data-stu-id="e3f2b-304">OpenText</span></span>

<span data-ttu-id="e3f2b-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e3f2b-306">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="e3f2b-306">Axs Encrypted</span></span>
    
- <span data-ttu-id="e3f2b-307">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="e3f2b-307">Axs Exchange</span></span>
    
- <span data-ttu-id="e3f2b-308">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="e3f2b-308">Axs Local Archive</span></span>
    
- <span data-ttu-id="e3f2b-309">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="e3f2b-309">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="e3f2b-310">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="e3f2b-310">Axs Signed</span></span>
    
- <span data-ttu-id="e3f2b-311">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e3f2b-311">Bloomberg</span></span>
    
- <span data-ttu-id="e3f2b-312">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="e3f2b-312">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="e3f2b-313">Verba</span><span class="sxs-lookup"><span data-stu-id="e3f2b-313">Verba</span></span>

<span data-ttu-id="e3f2b-314">[Verba](https://www.verba.com) supporta origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-314">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e3f2b-315">Avaya Aura Video
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-315">Avaya Aura Video</span></span>
    
- <span data-ttu-id="e3f2b-316">Avaya Aura Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-316">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="e3f2b-317">Avtec Radio
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-317">Avtec Radio</span></span>
    
- <span data-ttu-id="e3f2b-318">Bosch/Telex Radio
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-318">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="e3f2b-319">BroadSoft Video
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-319">BroadSoft Video</span></span>
    
- <span data-ttu-id="e3f2b-320">BroadSoft Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-320">BroadSoft Voice</span></span>
    
- <span data-ttu-id="e3f2b-321">Centile Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-321">Centile Voice</span></span>
    
- <span data-ttu-id="e3f2b-322">Messaggistica immediata Cisco Jabber
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-322">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="e3f2b-323">Cisco UC Video
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-323">Cisco UC Video</span></span>
    
- <span data-ttu-id="e3f2b-324">Cisco UC Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-324">Cisco UC Voice</span></span>
    
- <span data-ttu-id="e3f2b-325">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="e3f2b-325">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="e3f2b-326">Cisco UCCX/UCCE vocale</span><span class="sxs-lookup"><span data-stu-id="e3f2b-326">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="e3f2b-327">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="e3f2b-327">ESChat Radio</span></span>
    
- <span data-ttu-id="e3f2b-328">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="e3f2b-328">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="e3f2b-329">IP Trade Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-329">IP Trade Voice</span></span>
    
- <span data-ttu-id="e3f2b-330">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="e3f2b-330">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="e3f2b-331">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-331">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="e3f2b-332">Mitel MiContact Center per Lync (prairieFyre) 
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-332">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="e3f2b-333">Oracle / Acme Packet Session Border Controller Video  
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-333">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="e3f2b-334">Oracle / Acme Packet Session Border Controller Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-334">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="e3f2b-335">Singtel Mobile Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-335">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="e3f2b-336">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="e3f2b-336">SIPREC Video</span></span>
    
-  <span data-ttu-id="e3f2b-337">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="e3f2b-337">SIPREC Voice</span></span> 
    
- <span data-ttu-id="e3f2b-338">Messaggistica immediata Skype for Business / Lync
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-338">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="e3f2b-339">Video Skype for Business / Lync
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-339">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="e3f2b-340">Chiamate Skype for Business / Lync
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-340">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="e3f2b-341">Speakerbus Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-341">Speakerbus Voice</span></span>
    
- <span data-ttu-id="e3f2b-342">Video SIP/H.323 standard 
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-342">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="e3f2b-343">Chiamate SIP/H.323 standard 
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-343">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="e3f2b-344">Truphone Voice
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-344">Truphone Voice</span></span>
    
- <span data-ttu-id="e3f2b-345">TwistedPair Radio
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-345">TwistedPair Radio</span></span>
    
- <span data-ttu-id="e3f2b-346">Schermata di Computer Desktop di Windows 
</span><span class="sxs-lookup"><span data-stu-id="e3f2b-346">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="e3f2b-347">Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="e3f2b-347">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="e3f2b-p109">Ecco la procedura per la creazione e configurazione di una cassetta postale di dati di terze parti per l'importazione di dati in Office 365. Nel precedente illustrati, vengono importati elementi a questa cassetta postale se il connettore partner non può eseguire il mapping l'ID dell'elemento a un account utente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p109">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="e3f2b-350">**Completare queste attività nell'interfaccia di amministrazione di Office 365**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-350">**Complete these tasks in the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="e3f2b-p110">Creare un nuovo account utente in Office 365 e assegnare una licenza di Exchange Online piano 2; vedere [aggiungere utenti a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Per effettuare la cassetta postale di conservazione per controversia legale o abilitare una cassetta postale di archiviazione con una quota di archiviazione illimitato è necessaria una licenza piano 2.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p110">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="e3f2b-353">Aggiungere l'account utente per la cassetta postale di dati di terze parti per il ruolo di amministratore **di amministrazione di Exchange** in Office 365, vedere [assegnare ruoli di amministratore in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="e3f2b-353">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e3f2b-p111">Annotare le credenziali per l'account utente. È necessario fornirle al partner, come descritto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p111">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="e3f2b-356">**Completare queste attività nell'interfaccia di amministrazione di Exchange**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-356">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="e3f2b-p112">Nascondere la cassetta postale di terze parti dati dalla Rubrica e altri elenchi di indirizzi nell'organizzazione. vedere [Gestione cassette postali degli utenti](https://go.microsoft.com/fwlink/p/?LinkId=616058). In alternativa, è possibile eseguire il seguente comando PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p112">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="e3f2b-359">Assegnare l'autorizzazione **FullAccess** per la cassetta postale di dati di terze parti in modo che gli amministratori o responsabili della conformità aprire la cassetta postale di terze parti dati nel client desktop Outlook; vedere [Manage permissions per i destinatari](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="e3f2b-359">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="e3f2b-360">Abilitare le seguenti funzionalità Office 365 relativi alla conformità per la cassetta postale di dati di terze parti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-360">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="e3f2b-p113">Abilitare la cassetta postale di archivio; vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md). Consente di liberare spazio nella cassetta postale principale mediante l'impostazione di criteri di archiviazione che sposta gli elementi di dati di terze parti per la cassetta postale di archivio. In questo modo sarà con archiviazione illimitata per i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p113">Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="e3f2b-p114">Effettuare la cassetta postale di dati di terze parti controversie legali. È inoltre possibile applicare un criterio di conservazione di Office 365 in Office 365 Security &amp; centro conformità. Esecuzione di questa cassetta postale in attesa verrà conservazione degli elementi di dati di terze parti (tempo indeterminato o per un periodo specificato) e impedire che venga eliminato dalla cassetta postale. Vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p114">Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. See one of the following topics:</span></span>
    
      - [<span data-ttu-id="e3f2b-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="e3f2b-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="e3f2b-369">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="e3f2b-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="e3f2b-p115">Abilitare la registrazione per l'accesso alla cassetta postale di dati di terze parti, proprietario, delegato e amministrazione di controllo delle cassette postali vedere [abilitare il controllo in Office 365](enable-mailbox-auditing.md). In questo modo è possibile controllare tutte le attività eseguite da qualsiasi utente che ha accesso alla cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p115">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="e3f2b-372">Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e3f2b-372">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="e3f2b-p116">Il passaggio successivo consiste nel configurare cassette postali degli utenti per il supporto dei dati di terze parti. Completare queste attività utilizzando l'interfaccia di amministrazione di Exchange o utilizzando i cmdlet di Windows PowerShell corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p116">The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="e3f2b-375">Abilitare la cassetta postale di archiviazione per ogni utente. vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="e3f2b-375">Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="e3f2b-376">Archiviare le cassette postali utente conservazione per controversia legale o applicare un criterio di conservazione, Office 365 vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-376">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="e3f2b-377">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="e3f2b-377">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="e3f2b-378">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="e3f2b-378">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="e3f2b-379">Come precedentemente illustrato, quando si abilita un blocco delle cassette postali, è possibile impostare una durata per definire quanto tempo devono essere conservati gli elementi dell'origine dati di terze parti oppure è possibile scegliere di conservare gli elementi per un periodo di tempo indeterminato.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-379">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="e3f2b-380">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="e3f2b-380">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="e3f2b-381">Il passaggio finale consiste nel fornire al partner le informazioni seguenti affinché sia in grado di configurare il connettore per connettersi all'organizzazione di Office 365 e importare i dati nelle cassette postali degli utenti e nella cassetta postale dei dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-381">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="e3f2b-382">L'endpoint utilizzato per la connessione al servizio Azure in Office 365:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-382">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="e3f2b-p117">Accesso in credenziali (ID utente di Office 365 e password) della cassetta postale di dati di terze parti creato nel passaggio 2. Queste credenziali sono necessari in modo che il connettore di partner può accedere e importare gli elementi delle cassette postali utente e la cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p117">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="e3f2b-385">Passaggio 5: Registrare il connettore di terze parti dati in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e3f2b-385">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="e3f2b-p118">Avvio 30 settembre 2018, il servizio Azure in Office 365 inizierà con l'autenticazione moderno di Exchange Online per autenticare i connettori di dati di terze parti che tentano di connettersi all'organizzazione di Office 365 per importare i dati. Motivo della modifica è che l'autenticazione moderno offre maggiore protezione rispetto al metodo corrente, è basato su whitelist i connettori di terze parti che utilizzano l'endpoint descritto in precedenza per la connessione al servizio di Azure.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p118">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data. The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="e3f2b-p119">Per abilitare un connettore di dati di terze parti per la connessione a Office 365 utilizzando il nuovo metodo di autenticazione moderno, un amministratore dell'organizzazione Office 365 deve acconsente alla registrazione del connettore come un'applicazione di servizio attendibile in Azure Active Directory. Questa operazione viene eseguita mediante l'accettazione di una richiesta di autorizzazioni per consentire il connettore per accedere ai dati dell'organizzazione in Azure Active Directory. Dopo aver accettato la richiesta, il connettore di terze parti dati aggiunto come un'applicazione enterprise per Azure Active Directory e rappresentato come un'identità di servizio. Per ulteriori informazioni il processo di consenso dell'utente, vedere [Il proprio consenso amministrazione Tenant](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p119">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory. This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory. After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal. For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="e3f2b-392">Ecco la procedura per accedere e accettare la richiesta per registrare il connettore:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-392">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="e3f2b-393">Accedere a [questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e accedere utilizzando le credenziali di un amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-393">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="e3f2b-p120">Viene visualizzata la finestra di dialogo seguente. È possibile espandere accenti circonflessi per esaminare le autorizzazioni assegnate al connettore.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p120">The following dialog box is displayed. You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="e3f2b-396">![Viene visualizzata la finestra di dialogo di richiesta di autorizzazioni](media/O365_ThirdPartyDataConnector_OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-396">![The permissions request dialog is displayed](media/O365_ThirdPartyDataConnector_OptIn1.png)</span></span>
2. <span data-ttu-id="e3f2b-397">Fare clic su **Accept**.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-397">Click **Accept**.</span></span>

<span data-ttu-id="e3f2b-p121">Dopo aver accettato la richiesta, viene visualizzato il [dashboard portale Azure](https://portal.azure.com) . Per visualizzare l'elenco delle applicazioni per l'organizzazione, fare clic su **Azure Active Directory** > **applicazioni aziendali**. Il connettore di dati di terze parti di Office 365 è elencato nella blade **applicazioni aziendali** .</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p121">After you accept the request, the [Azure portal dashboard](https://portal.azure.com) is displayed. To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**. The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3f2b-p122">Dopo 30 settembre 2018, dati di terze parti non sono più da importare nelle cassette postali nell'organizzazione non registrare un connettore di dati di terze parti in Azure Active Directory. Nota esistenti di connettori di terze parti dati, ovvero creato prima del 30 settembre 2018, deve essere registrata anche in Azure Active Directory tramite la procedura descritta nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p122">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory. Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="e3f2b-403">Revoca dell'autorizzazione per un connettore di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e3f2b-403">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="e3f2b-p123">Dopo che l'organizzazione acconsente alla richiesta di autorizzazioni per la registrazione di un connettore di dati di terze parti in Azure Active Directory, l'organizzazione può revocare il consenso in qualsiasi momento. Tuttavia, revoca dell'autorizzazione per un connettore significa che i dati dall'origine dati di terze parti non è più essere importati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p123">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time. However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="e3f2b-p124">Per revocare il consenso dell'utente per un connettore di dati di terze parti, è possibile eliminare l'applicazione (eliminando l'entità servizio corrispondente) da Azure Active Directory utilizzando blade **applicazioni aziendali** nel portale di Azure o con la [ Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell. È inoltre possibile utilizzare il cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p124">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell. You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="e3f2b-408">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e3f2b-408">More information</span></span>

- <span data-ttu-id="e3f2b-p125">Spiegato come precedente, gli elementi alle cassette postali di Exchange come messaggi di posta elettronica vengono importate le origini dati di terze parti. Il connettore partner consente di importare l'elemento utilizzando uno schema necessario per l'API di Office 365. Nella tabella seguente vengono descritte le proprietà del messaggio di un elemento da un'origine dati di terze parti dopo l'importazione di una cassetta postale di Exchange come messaggio di posta elettronica. Nella tabella indica anche se la proprietà message è obbligatoria. Le proprietà obbligatorie devono essere compilate. Se un elemento manca una proprietà obbligatoria, non sarà possibile importare a Office 365. Il processo di importazione restituirà un messaggio di errore che spiega perché un elemento non è stato importato e la proprietà non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p125">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="e3f2b-416">**Proprietà del messaggio**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-416">**Message property**</span></span>|<span data-ttu-id="e3f2b-417">**Obbligatorio?**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-417">**Mandatory?**</span></span>|<span data-ttu-id="e3f2b-418">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-418">**Description**</span></span>|<span data-ttu-id="e3f2b-419">**Valore di esempio**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-419">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e3f2b-420">**FROM**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-420">**FROM**</span></span> <br/> |<span data-ttu-id="e3f2b-421">Sì</span><span class="sxs-lookup"><span data-stu-id="e3f2b-421">Yes</span></span>  <br/> |<span data-ttu-id="e3f2b-p126">L'utente che ha creato o l'elemento inviato nell'origine dati di terze parti. Il connettore partner tenterà di mappare l'ID utente dalla voce di origine (ad esempio un handle Twitter) da un account utente di Office 365 per tutti i partecipanti (utenti nei campi FROM e TO). Verrà importata una copia del messaggio alla cassetta postale di tutti gli altri partecipanti. Se nessuno dei partecipanti dall'elemento può essere associata a un account utente di Office 365, l'elemento verrà importata alla cassetta postale di archiviazione di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p126">The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  </span></span><br/> <br/> <span data-ttu-id="e3f2b-p127">Il partecipante che viene identificato come mittente dell'elemento deve disporre di una cassetta postale attiva nell'organizzazione di Office 365 importato per l'elemento. Se il mittente non dispone di una cassetta postale attiva, viene restituito l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p127">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="e3f2b-428">**TO**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-428">**TO**</span></span> <br/> |<span data-ttu-id="e3f2b-429">Sì</span><span class="sxs-lookup"><span data-stu-id="e3f2b-429">Yes</span></span>  <br/> |<span data-ttu-id="e3f2b-430">L'utente che ha ricevuto un elemento, se applicabile per un elemento nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-430">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="e3f2b-431">**SUBJECT**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-431">**SUBJECT**</span></span> <br/> |<span data-ttu-id="e3f2b-432">No</span><span class="sxs-lookup"><span data-stu-id="e3f2b-432">No</span></span>  <br/> |<span data-ttu-id="e3f2b-433">L'oggetto dell'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-433">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="e3f2b-434">**DATA**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-434">**DATE**</span></span> <br/> |<span data-ttu-id="e3f2b-435">Sì</span><span class="sxs-lookup"><span data-stu-id="e3f2b-435">Yes</span></span>  <br/> |<span data-ttu-id="e3f2b-436">La data in cui l'elemento è stato originariamente creato o inserito nell'origine dati del cliente; ad esempio, la data in cui è stato twittato un messaggio di Twitter.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-436">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="e3f2b-437">**BODY**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-437">**BODY**</span></span> <br/> |<span data-ttu-id="e3f2b-438">No</span><span class="sxs-lookup"><span data-stu-id="e3f2b-438">No</span></span>  <br/> |<span data-ttu-id="e3f2b-p128">Il contenuto del messaggio o post. Per alcune origini dati, il contenuto di questa proprietà può corrispondere a quella come il contenuto per la proprietà **SUBJECT** . Durante il processo di importazione, il connettore partner tenterà di mantenere massima fedeltà dall'origine di contenuto possibile. Se possibile file, grafica o altri contenuti provenienti dal corpo dell'elemento di origine sono incluso nella proprietà. In caso contrario, il contenuto dall'elemento di origine è incluso nella proprietà **allegato** . Il contenuto della proprietà dipenderà sul connettore di partner e alla capacità della piattaforma di origine.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p128">The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  </span></span><br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="e3f2b-445">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-445">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="e3f2b-446">No</span><span class="sxs-lookup"><span data-stu-id="e3f2b-446">No</span></span>  <br/> |<span data-ttu-id="e3f2b-p129">Se un elemento nell'origine dati (ad esempio, visualizzato in una conversazione di messaggistica immediata o Twitter) è un file allegato o includere le immagini, il partner connettersi will primo tentativo di essere inclusi gli allegati nella proprietà **BODY** . Se ciò non è possibile, quindi viene aggiunta al * * allegato * * proprietà. Altri esempi di allegati sono apprezzamenti in Facebook, metadati di origine di contenuto e le risposte a un messaggio o post.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p129">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the ** ATTACHMENT ** property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  </span></span><br/> | `image.gif` <br/> |
    |<span data-ttu-id="e3f2b-450">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="e3f2b-450">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="e3f2b-451">Sì</span><span class="sxs-lookup"><span data-stu-id="e3f2b-451">Yes</span></span>  <br/> | <span data-ttu-id="e3f2b-p130">Si tratta di una proprietà multivalore, che viene creata e compilata dal connettore di partner. Il formato di questa proprietà è `IPM.NOTE.Source.Event`. (Questa proprietà deve iniziare con `IPM.NOTE`; in questo formato è simile a quella per la `IPM.NOTE.X` classe messaggio.) Questa proprietà include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p130">This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  </span></span><br/><br/><span data-ttu-id="e3f2b-455">`Source`-Indica l'origine dati di terze parti. ad esempio Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-455">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="e3f2b-p131">`Event`-Indica il tipo di attività eseguita nell'origine dati di terze parti che ha generato gli elementi; ad esempio, visualizzato in un post di Facebook o Twitter. Gli eventi sono specifici per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p131">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  </span></span><br/> <br/>  <span data-ttu-id="e3f2b-p132">Uno scopo di questa proprietà è per filtrare elementi specifici in base all'origine dati in un elemento ha dato origine o in base al tipo di evento. In una ricerca eDiscovery, ad esempio, è possibile creare una query di ricerca per trovare tutti i tweets che sono stati inviati da un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p132">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  </span></span><br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="e3f2b-p133">Quando gli elementi vengono importati correttamente le cassette postali in Office 365, viene restituito un identificatore univoco al chiamante come parte della risposta HTTP. Questo identificatore, viene chiamato `x-IngestionCorrelationID`, può essere utilizzata per scopi di risoluzione dei problemi successivi da parte dei partner per tenere traccia end-to-end di elementi. È consigliabile che i partner acquisire informazioni e accedere conseguenza dal lato. Di seguito è riportato un esempio di una risposta HTTP che mostra l'identificatore:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p133">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="e3f2b-p134">È possibile utilizzare lo strumento di ricerca del contenuto in Office 365 Security &amp; centro conformità per cercare gli elementi che sono stati importati alle cassette postali in Office 365 da un'origine dati di terze parti. Per eseguire la ricerca in modo specifico per questi elementi importati, è possibile utilizzare le seguenti coppie di valore della proprietà messaggio nella casella parole chiave per la ricerca del contenuto. .</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p134">You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. .</span></span> 
    
  - <span data-ttu-id="e3f2b-p135">**`kind:externaldata`**-Utilizzare questo coppia valore della proprietà per cercare tutti i tipi di dati di terze parti. Ad esempio, per cercare gli elementi che sono stati importati da un'origine dati di terze parti e contenuto la parola "contoso" nella proprietà Subject dell'elemento importato, utilizzare la query con parole chiave `kind:externaldata AND subject:contoso`.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p135">**`kind:externaldata`** - Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="e3f2b-p136">**`itemclass:ipm.externaldata.<third-party data type>`**-Utilizzare questo coppia valore della proprietà di ricerca solo un tipo di impostazione dei dati di terze parti. Ad esempio, per eseguire la ricerca solo dati Facebook che contiene la parola "contoso" nella proprietà Subject, utilizzare la query con parole chiave `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span><span class="sxs-lookup"><span data-stu-id="e3f2b-p136">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="e3f2b-471">Per un elenco completo dei valori da utilizzare per i tipi di dati di terze parti per la `itemclass` proprietà, vedere [Utilizzo della ricerca contenuto per cercare i dati di terze parti che è stati importati a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="e3f2b-471">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="e3f2b-472">Per ulteriori informazioni sull'utilizzo di Ricerca contenuto e sulla creazione di query di ricerca con parole chiave, vedere:</span><span class="sxs-lookup"><span data-stu-id="e3f2b-472">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="e3f2b-473">Ricerca del contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="e3f2b-473">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="e3f2b-474">Query delle parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="e3f2b-474">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
