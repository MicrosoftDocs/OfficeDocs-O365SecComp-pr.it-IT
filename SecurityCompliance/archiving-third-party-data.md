---
title: Archiviazione dei dati di terze parti in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
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
ms.openlocfilehash: 06ac436b1583187e89cb7f1beb26411ba02becec
ms.sourcegitcommit: 86ff2eba1d57b9d5288840788529e69ad9d836b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2019
ms.locfileid: "31818613"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="9a6c3-105">Archiviazione di dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="9a6c3-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="9a6c3-106">Office 365 consente agli amministratori di importare e archiviare i dati di terze parti dalle piattaforme per i social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti, alle cassette postali dell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-106">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="9a6c3-107">Di seguito sono riportati alcuni esempi di origini dati di terze parti che è possibile importare in Office 365:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-107">Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="9a6c3-108">**Social** -Twitter, Facebook, Yammer e LinkedIn</span><span class="sxs-lookup"><span data-stu-id="9a6c3-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="9a6c3-109">**Messaggistica istantanea** -Yahoo Messenger, GoogleTalk e Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="9a6c3-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="9a6c3-110">**Collaborazione di documenti** -box e Dropbox</span><span class="sxs-lookup"><span data-stu-id="9a6c3-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="9a6c3-111">**Industrie verticali** -gestione delle relazioni con i clienti (come Salesforce Chatter) e servizi finanziari (come Thomson Reuters e Bloomberg)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="9a6c3-112">**SMS/Text Messaging** -BlackBerry</span><span class="sxs-lookup"><span data-stu-id="9a6c3-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="9a6c3-113">Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo e i criteri di conservazione di Office 365, a tali dati.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-113">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data.</span></span> <span data-ttu-id="9a6c3-114">Ad esempio, quando per una cassetta postale si attiva il blocco a causa di controversie legali, i dati di terze parti verranno mantenuti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-114">For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved.</span></span> <span data-ttu-id="9a6c3-115">È possibile eseguire la ricerca di dati di terze parti utilizzando la ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-115">You can search third-party data by using Content Search.</span></span> <span data-ttu-id="9a6c3-116">In alternativa, è possibile applicare i criteri di archiviazione e conservazione ai dati di terze parti esattamente come per i dati di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-116">Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="9a6c3-117">In breve, l'archiviazione dei dati di terze parti in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-117">In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="9a6c3-118">Di seguito è riportata una panoramica del processo e i passaggi necessari per importare i dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="9a6c3-119">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="9a6c3-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="9a6c3-120">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="9a6c3-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="9a6c3-121">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="9a6c3-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="9a6c3-122">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="9a6c3-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="9a6c3-123">Passaggio 5: registrare il connettore di dati di terze parti in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9a6c3-123">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="9a6c3-124">Processo di importazione di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="9a6c3-124">How the third-party data import process works</span></span>

<span data-ttu-id="9a6c3-125">Nella figura e nella descrizione seguenti viene illustrato il processo di importazione di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-125">The following illustration and description explain how the third-party data import process works.</span></span>
  
![Funzionamento del processo di importazione dei dati di terze parti](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="9a6c3-127">Il cliente lavora con il proprio partner preferito per configurare un connettore che estrae gli elementi dall'origine dati di terze parti e quindi importa tali elementi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-127">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="9a6c3-128">Il connettore partner si connette a origini dati di terze parti tramite un'API di terze parti (su base pianificata o configurata) ed estrae gli elementi dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-128">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="9a6c3-129">Il connettore partner converte il contenuto di un elemento in un formato di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-129">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="9a6c3-130">Vedere la sezione [More information](#more-information) per una descrizione dello schema del formato del messaggio.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-130">See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="9a6c3-131">Il connettore partner si connette al servizio di Azure in Office 365 utilizzando il servizio Web Exchange (EWS) tramite un punto finale noto.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-131">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="9a6c3-p105">Gli elementi vengono importati nella cassetta postale di un utente specifico oppure in una cassetta postale generale di dati di terze parti. Il fatto che un elemento sia importato nella cassetta postale di un utente specifico o nella cassetta postale di dati di terze parti dipende dai seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="9a6c3-134">un.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-134">a.</span></span> <span data-ttu-id="9a6c3-135">**Elementi che dispongono di un ID utente corrispondente a un account utente di office 365** : se il connettore del partner può eseguire il mapping dell'ID utente dell'elemento nell'origine dati di terze parti a un ID utente specifico in Office 365, l'elemento viene \*\*\*\* copiato nella cartella Ripuliture del REC dell'utente. cartella elementi overable.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-135">**Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="9a6c3-136">Gli utenti non possono accedere agli elementi nella cartella Ripuliture.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-136">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="9a6c3-137">Tuttavia, è possibile utilizzare gli strumenti di Office 365 eDiscovery per cercare gli elementi nella cartella Purges.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-137">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="9a6c3-138">b.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-138">b.</span></span> <span data-ttu-id="9a6c3-139">**Elementi che non dispongono di un ID utente corrispondente a un account utente di office 365** -se il connettore partner non è in grado di mappare l'ID utente di un elemento a un ID utente specifico in Office 365, l'elemento viene copiato nella cartella **posta in arrivo** della cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-139">**Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="9a6c3-140">L'importazione di elementi nella posta in arrivo consente a un utente dell'organizzazione di accedere alla cassetta postale di terze parti per visualizzare e gestire questi elementi e vedere se è necessario prevedere modifiche nella configurazione del connettore partner.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-140">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="9a6c3-141">Passaggio 1: trovare un partner di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="9a6c3-141">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="9a6c3-142">Un componente chiave per l'archiviazione dei dati di terze parti in Office 365 è l'individuazione e l'utilizzo di un partner Microsoft specializzato nell'acquisizione dei dati da un'origine dati di terze parti e nell'importarlo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-142">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="9a6c3-143">Dopo aver importato i dati, è possibile archiviarli e conservarli insieme agli altri dati di Microsoft dell'organizzazione, ad esempio la posta elettronica da Exchange e i documenti di SharePoint e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-143">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="9a6c3-144">Un partner crea un connettore che estrae i dati dalle origini dati di terze parti dell'organizzazione (ad esempio, BlackBerry, Facebook, Google +, Thomson Reuters, Twitter e YouTube) e passa tali dati a un'API di Office 365 che importa gli elementi nelle cassette postali di Exchange come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-144">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="9a6c3-145">Nelle sezioni seguenti vengono elencati i partner Microsoft e le origini dati di terze parti che supportano, che partecipano al programma per l'archiviazione dei dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-145">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="9a6c3-146">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="9a6c3-146">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="9a6c3-147">Actiance</span><span class="sxs-lookup"><span data-stu-id="9a6c3-147">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="9a6c3-148">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="9a6c3-148">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="9a6c3-149">Globanet</span><span class="sxs-lookup"><span data-stu-id="9a6c3-149">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="9a6c3-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="9a6c3-150">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="9a6c3-151">Verba</span><span class="sxs-lookup"><span data-stu-id="9a6c3-151">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="9a6c3-152">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="9a6c3-152">17a-4 LLC</span></span>

<span data-ttu-id="9a6c3-153">17a-4 LLC supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-153">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="9a6c3-154">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="9a6c3-154">BlackBerry</span></span>
    
- <span data-ttu-id="9a6c3-155">Flussi di dati di Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9a6c3-155">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="9a6c3-156">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="9a6c3-156">Cisco Jabber</span></span>
    
- <span data-ttu-id="9a6c3-157">Factt</span><span class="sxs-lookup"><span data-stu-id="9a6c3-157">FactSet</span></span>
    
- <span data-ttu-id="9a6c3-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="9a6c3-158">HipChat</span></span>
    
- <span data-ttu-id="9a6c3-159">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="9a6c3-159">InvestEdge</span></span>
    
- <span data-ttu-id="9a6c3-160">LivePerson</span><span class="sxs-lookup"><span data-stu-id="9a6c3-160">LivePerson</span></span>
    
- <span data-ttu-id="9a6c3-161">Flussi di dati MessageLabs</span><span class="sxs-lookup"><span data-stu-id="9a6c3-161">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="9a6c3-162">OpenText</span><span class="sxs-lookup"><span data-stu-id="9a6c3-162">OpenText</span></span>
    
- <span data-ttu-id="9a6c3-163">Guida "click-to-call" di Oracle/ATG</span><span class="sxs-lookup"><span data-stu-id="9a6c3-163">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="9a6c3-164">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="9a6c3-164">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="9a6c3-165">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="9a6c3-165">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="9a6c3-166">MindAlign</span><span class="sxs-lookup"><span data-stu-id="9a6c3-166">MindAlign</span></span>
    
- <span data-ttu-id="9a6c3-167">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-167">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="9a6c3-168">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-168">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="9a6c3-169">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-169">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="9a6c3-170">Database SQL</span><span class="sxs-lookup"><span data-stu-id="9a6c3-170">SQL Databases</span></span>
    
- <span data-ttu-id="9a6c3-171">Squawker</span><span class="sxs-lookup"><span data-stu-id="9a6c3-171">Squawker</span></span>
    
- <span data-ttu-id="9a6c3-172">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="9a6c3-172">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="9a6c3-173">Actiance</span><span class="sxs-lookup"><span data-stu-id="9a6c3-173">Actiance</span></span>

<span data-ttu-id="9a6c3-174">[Actiance](https://www.actiance.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-174">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="9a6c3-175">OBIETTIVO</span><span class="sxs-lookup"><span data-stu-id="9a6c3-175">AIM</span></span>
    
- <span data-ttu-id="9a6c3-176">American Idol</span><span class="sxs-lookup"><span data-stu-id="9a6c3-176">American Idol</span></span>
    
- <span data-ttu-id="9a6c3-177">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-177">Apple Juice</span></span>
    
- <span data-ttu-id="9a6c3-178">AOL con client Pivot</span><span class="sxs-lookup"><span data-stu-id="9a6c3-178">AOL with Pivot client</span></span>
    
- <span data-ttu-id="9a6c3-179">Ares</span><span class="sxs-lookup"><span data-stu-id="9a6c3-179">Ares</span></span>
    
- <span data-ttu-id="9a6c3-180">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-180">Bazaar Voice</span></span>
    
- <span data-ttu-id="9a6c3-181">Bear Share</span><span class="sxs-lookup"><span data-stu-id="9a6c3-181">Bear Share</span></span>
    
- <span data-ttu-id="9a6c3-182">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="9a6c3-182">Bit Torrent</span></span>
    
- <span data-ttu-id="9a6c3-183">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-183">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="9a6c3-184">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-184">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="9a6c3-185">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-185">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="9a6c3-186">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-186">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="9a6c3-187">Posta Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9a6c3-187">Bloomberg Mail</span></span>
    
- <span data-ttu-id="9a6c3-188">CellTrust</span><span class="sxs-lookup"><span data-stu-id="9a6c3-188">CellTrust</span></span>
    
- <span data-ttu-id="9a6c3-189">Chat Import</span><span class="sxs-lookup"><span data-stu-id="9a6c3-189">Chat Import</span></span>
    
- <span data-ttu-id="9a6c3-190">Chat Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="9a6c3-190">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="9a6c3-191">Chiacchiere</span><span class="sxs-lookup"><span data-stu-id="9a6c3-191">Chatter</span></span>
    
- <span data-ttu-id="9a6c3-192">Server di &amp; presenza di messaggistica istantanea Cisco (v 9.0.1, v 9.1, v 9.1.1 su1, V10, v 10.5.1 su1)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-192">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="9a6c3-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="9a6c3-194">Importazione collaborazione</span><span class="sxs-lookup"><span data-stu-id="9a6c3-194">Collaboration Import</span></span>
    
- <span data-ttu-id="9a6c3-195">Registrazione di collaborazione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="9a6c3-195">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="9a6c3-196">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="9a6c3-196">Direct Connect</span></span>
    
- <span data-ttu-id="9a6c3-197">Facebook</span><span class="sxs-lookup"><span data-stu-id="9a6c3-197">Facebook</span></span>
    
- <span data-ttu-id="9a6c3-198">Factt</span><span class="sxs-lookup"><span data-stu-id="9a6c3-198">FactSet</span></span>
    
- <span data-ttu-id="9a6c3-199">FastTrack</span><span class="sxs-lookup"><span data-stu-id="9a6c3-199">FastTrack</span></span>
    
- <span data-ttu-id="9a6c3-200">Gnutella</span><span class="sxs-lookup"><span data-stu-id="9a6c3-200">Gnutella</span></span>
    
- <span data-ttu-id="9a6c3-201">Google +</span><span class="sxs-lookup"><span data-stu-id="9a6c3-201">Google+</span></span>
    
- <span data-ttu-id="9a6c3-202">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="9a6c3-202">GoToMyPC</span></span>
    
- <span data-ttu-id="9a6c3-203">Hopster</span><span class="sxs-lookup"><span data-stu-id="9a6c3-203">Hopster</span></span>
    
- <span data-ttu-id="9a6c3-204">HubConnex</span><span class="sxs-lookup"><span data-stu-id="9a6c3-204">HubConnex</span></span>
    
- <span data-ttu-id="9a6c3-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="9a6c3-206">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="9a6c3-206">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="9a6c3-207">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="9a6c3-207">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="9a6c3-208">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="9a6c3-208">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="9a6c3-209">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="9a6c3-209">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="9a6c3-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="9a6c3-211">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="9a6c3-211">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="9a6c3-212">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="9a6c3-212">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="9a6c3-213">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="9a6c3-213">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="9a6c3-214">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="9a6c3-214">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="9a6c3-215">IM Import</span><span class="sxs-lookup"><span data-stu-id="9a6c3-215">IM Import</span></span>
    
- <span data-ttu-id="9a6c3-216">IM Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="9a6c3-216">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="9a6c3-217">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="9a6c3-217">Indii Messenger</span></span>
    
- <span data-ttu-id="9a6c3-218">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9a6c3-218">Instant Bloomberg</span></span>
    
- <span data-ttu-id="9a6c3-219">IRC</span><span class="sxs-lookup"><span data-stu-id="9a6c3-219">IRC</span></span>
    
- <span data-ttu-id="9a6c3-220">Jive</span><span class="sxs-lookup"><span data-stu-id="9a6c3-220">Jive</span></span>
    
- <span data-ttu-id="9a6c3-221">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-221">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="9a6c3-222">Jive Import</span><span class="sxs-lookup"><span data-stu-id="9a6c3-222">Jive Import</span></span>
    
- <span data-ttu-id="9a6c3-223">JXTA</span><span class="sxs-lookup"><span data-stu-id="9a6c3-223">JXTA</span></span>
    
- <span data-ttu-id="9a6c3-224">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="9a6c3-224">LinkedIn</span></span>
    
- <span data-ttu-id="9a6c3-225">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-225">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="9a6c3-226">MFTP</span><span class="sxs-lookup"><span data-stu-id="9a6c3-226">MFTP</span></span>
    
- <span data-ttu-id="9a6c3-227">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-227">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="9a6c3-228">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-228">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="9a6c3-229">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9a6c3-229">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="9a6c3-230">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-230">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="9a6c3-231">MindAlign</span><span class="sxs-lookup"><span data-stu-id="9a6c3-231">MindAlign</span></span>
    
- <span data-ttu-id="9a6c3-232">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="9a6c3-232">Mobile Guard</span></span>
    
- <span data-ttu-id="9a6c3-233">MSN</span><span class="sxs-lookup"><span data-stu-id="9a6c3-233">MSN</span></span>
    
- <span data-ttu-id="9a6c3-234">My Space</span><span class="sxs-lookup"><span data-stu-id="9a6c3-234">My Space</span></span>
    
- <span data-ttu-id="9a6c3-235">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="9a6c3-235">NEONetwork</span></span>
    
- <span data-ttu-id="9a6c3-236">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="9a6c3-236">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="9a6c3-237">Messaggistica istantanea condivisa di Office 365</span><span class="sxs-lookup"><span data-stu-id="9a6c3-237">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="9a6c3-238">Pinterest</span><span class="sxs-lookup"><span data-stu-id="9a6c3-238">Pinterest</span></span>
    
- <span data-ttu-id="9a6c3-239">Pivot</span><span class="sxs-lookup"><span data-stu-id="9a6c3-239">Pivot</span></span>
    
- <span data-ttu-id="9a6c3-240">QQ</span><span class="sxs-lookup"><span data-stu-id="9a6c3-240">QQ</span></span>
    
- <span data-ttu-id="9a6c3-241">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="9a6c3-241">Skype for Business 2015</span></span>
    
- <span data-ttu-id="9a6c3-242">SoftEther</span><span class="sxs-lookup"><span data-stu-id="9a6c3-242">SoftEther</span></span>
    
- <span data-ttu-id="9a6c3-243">Sinfonia</span><span class="sxs-lookup"><span data-stu-id="9a6c3-243">Symphony</span></span>
    
- <span data-ttu-id="9a6c3-244">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="9a6c3-244">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="9a6c3-245">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="9a6c3-245">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="9a6c3-246">Tor</span><span class="sxs-lookup"><span data-stu-id="9a6c3-246">Tor</span></span>
    
- <span data-ttu-id="9a6c3-247">TTT</span><span class="sxs-lookup"><span data-stu-id="9a6c3-247">TTT</span></span>
    
- <span data-ttu-id="9a6c3-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="9a6c3-248">Twitter</span></span>
    
- <span data-ttu-id="9a6c3-249">WinMX</span><span class="sxs-lookup"><span data-stu-id="9a6c3-249">WinMX</span></span>
    
- <span data-ttu-id="9a6c3-250">Winny</span><span class="sxs-lookup"><span data-stu-id="9a6c3-250">Winny</span></span>
    
- <span data-ttu-id="9a6c3-251">Yahoo</span><span class="sxs-lookup"><span data-stu-id="9a6c3-251">Yahoo</span></span>
    
- <span data-ttu-id="9a6c3-252">Yammer</span><span class="sxs-lookup"><span data-stu-id="9a6c3-252">Yammer</span></span>
    
- <span data-ttu-id="9a6c3-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="9a6c3-253">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="9a6c3-254">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="9a6c3-254">ArchiveSocial</span></span>

<span data-ttu-id="9a6c3-255">[ArchiveSocial](https://www.archivesocial.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-255">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="9a6c3-256">Facebook</span><span class="sxs-lookup"><span data-stu-id="9a6c3-256">Facebook</span></span>
    
- <span data-ttu-id="9a6c3-257">Flickr</span><span class="sxs-lookup"><span data-stu-id="9a6c3-257">Flickr</span></span>
    
- <span data-ttu-id="9a6c3-258">Instagram</span><span class="sxs-lookup"><span data-stu-id="9a6c3-258">Instagram</span></span>
    
- <span data-ttu-id="9a6c3-259">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="9a6c3-259">LinkedIn</span></span>
    
- <span data-ttu-id="9a6c3-260">Pinterest</span><span class="sxs-lookup"><span data-stu-id="9a6c3-260">Pinterest</span></span>
    
- <span data-ttu-id="9a6c3-261">Twitter</span><span class="sxs-lookup"><span data-stu-id="9a6c3-261">Twitter</span></span>
    
- <span data-ttu-id="9a6c3-262">YouTube</span><span class="sxs-lookup"><span data-stu-id="9a6c3-262">YouTube</span></span>
    
- <span data-ttu-id="9a6c3-263">Officemix</span><span class="sxs-lookup"><span data-stu-id="9a6c3-263">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="9a6c3-264">Globanet</span><span class="sxs-lookup"><span data-stu-id="9a6c3-264">Globanet</span></span>

<span data-ttu-id="9a6c3-265">[Globanet](https://www.globanet.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-265">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="9a6c3-266">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="9a6c3-266">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="9a6c3-267">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-267">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="9a6c3-268">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-268">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="9a6c3-269">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-269">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="9a6c3-270">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-270">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="9a6c3-271">Chat Bloomber</span><span class="sxs-lookup"><span data-stu-id="9a6c3-271">Bloomberg Chat</span></span>
    
- <span data-ttu-id="9a6c3-272">Posta Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9a6c3-272">Bloomberg Mail</span></span>
    
- <span data-ttu-id="9a6c3-273">Box</span><span class="sxs-lookup"><span data-stu-id="9a6c3-273">Box</span></span>
    
- <span data-ttu-id="9a6c3-274">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="9a6c3-274">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="9a6c3-275">Server di &amp; presenza di messaggistica istantanea Cisco (V10, v 10.5.1 su1, v 11.0, v 11,5 SU2)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-275">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="9a6c3-276">Team Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="9a6c3-276">Cisco Webex Teams</span></span>

- <span data-ttu-id="9a6c3-277">ShareFile di &amp; area di lavoro Citrix</span><span class="sxs-lookup"><span data-stu-id="9a6c3-277">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="9a6c3-278">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="9a6c3-278">CrowdCompass</span></span>

- <span data-ttu-id="9a6c3-279">File di testo delimitati personalizzati</span><span class="sxs-lookup"><span data-stu-id="9a6c3-279">Custom delimited text files</span></span>
    
- <span data-ttu-id="9a6c3-280">File XML personalizzati</span><span class="sxs-lookup"><span data-stu-id="9a6c3-280">Custom XML files</span></span>
    
- <span data-ttu-id="9a6c3-281">Facebook (pagine)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-281">Facebook (Pages)</span></span>
    
- <span data-ttu-id="9a6c3-282">Factt</span><span class="sxs-lookup"><span data-stu-id="9a6c3-282">Factset</span></span>
    
- <span data-ttu-id="9a6c3-283">FXConnect</span><span class="sxs-lookup"><span data-stu-id="9a6c3-283">FXConnect</span></span>
    
- <span data-ttu-id="9a6c3-284">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="9a6c3-284">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="9a6c3-285">Jive</span><span class="sxs-lookup"><span data-stu-id="9a6c3-285">Jive</span></span>
    
- <span data-ttu-id="9a6c3-286">XIP Macgregor</span><span class="sxs-lookup"><span data-stu-id="9a6c3-286">Macgregor XIP</span></span>

- <span data-ttu-id="9a6c3-287">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="9a6c3-287">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="9a6c3-288">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="9a6c3-288">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="9a6c3-289">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a6c3-289">Microsoft Teams</span></span>
       
- <span data-ttu-id="9a6c3-290">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="9a6c3-290">Microsoft Yammer</span></span>
    
- <span data-ttu-id="9a6c3-291">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="9a6c3-291">Mobile Guard</span></span>
    
- <span data-ttu-id="9a6c3-292">Pivot</span><span class="sxs-lookup"><span data-stu-id="9a6c3-292">Pivot</span></span>
    
- <span data-ttu-id="9a6c3-293">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="9a6c3-293">Salesforce Chatter</span></span>

- <span data-ttu-id="9a6c3-294">Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9a6c3-294">Skype for Business Online</span></span>
    
- <span data-ttu-id="9a6c3-295">Skype for Business, versioni 2007 R2 - 2016 (locale)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-295">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="9a6c3-296">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="9a6c3-296">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="9a6c3-297">Sinfonia</span><span class="sxs-lookup"><span data-stu-id="9a6c3-297">Symphony</span></span>
    
- <span data-ttu-id="9a6c3-298">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="9a6c3-298">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="9a6c3-299">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="9a6c3-299">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="9a6c3-300">Thomson Reuters Dealings 3000/FX Trading</span><span class="sxs-lookup"><span data-stu-id="9a6c3-300">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="9a6c3-301">Twitter</span><span class="sxs-lookup"><span data-stu-id="9a6c3-301">Twitter</span></span>
    
- <span data-ttu-id="9a6c3-302">Chat UBS</span><span class="sxs-lookup"><span data-stu-id="9a6c3-302">UBS Chat</span></span>
    
- <span data-ttu-id="9a6c3-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="9a6c3-303">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="9a6c3-304">OpenText</span><span class="sxs-lookup"><span data-stu-id="9a6c3-304">OpenText</span></span>

<span data-ttu-id="9a6c3-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="9a6c3-306">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="9a6c3-306">Axs Encrypted</span></span>
    
- <span data-ttu-id="9a6c3-307">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="9a6c3-307">Axs Exchange</span></span>
    
- <span data-ttu-id="9a6c3-308">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="9a6c3-308">Axs Local Archive</span></span>
    
- <span data-ttu-id="9a6c3-309">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="9a6c3-309">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="9a6c3-310">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="9a6c3-310">Axs Signed</span></span>
    
- <span data-ttu-id="9a6c3-311">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="9a6c3-311">Bloomberg</span></span>
    
- <span data-ttu-id="9a6c3-312">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="9a6c3-312">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="9a6c3-313">Verba</span><span class="sxs-lookup"><span data-stu-id="9a6c3-313">Verba</span></span>

<span data-ttu-id="9a6c3-314">[Verba](https://www.verba.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-314">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="9a6c3-315">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="9a6c3-315">Avaya Aura Video</span></span>
    
- <span data-ttu-id="9a6c3-316">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-316">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="9a6c3-317">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="9a6c3-317">Avtec Radio</span></span>
    
- <span data-ttu-id="9a6c3-318">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="9a6c3-318">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="9a6c3-319">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="9a6c3-319">BroadSoft Video</span></span>
    
- <span data-ttu-id="9a6c3-320">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-320">BroadSoft Voice</span></span>
    
- <span data-ttu-id="9a6c3-321">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-321">Centile Voice</span></span>
    
- <span data-ttu-id="9a6c3-322">Messaggistica immediata Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="9a6c3-322">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="9a6c3-323">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="9a6c3-323">Cisco UC Video</span></span>
    
- <span data-ttu-id="9a6c3-324">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-324">Cisco UC Voice</span></span>
    
- <span data-ttu-id="9a6c3-325">Video su Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="9a6c3-325">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="9a6c3-326">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-326">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="9a6c3-327">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="9a6c3-327">ESChat Radio</span></span>
    
- <span data-ttu-id="9a6c3-328">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="9a6c3-328">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="9a6c3-329">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-329">IP Trade Voice</span></span>
    
- <span data-ttu-id="9a6c3-330">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="9a6c3-330">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="9a6c3-331">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-331">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="9a6c3-332">Mitel MiContact Center per Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-332">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="9a6c3-333">Oracle / Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="9a6c3-333">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="9a6c3-334">Oracle / Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-334">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="9a6c3-335">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-335">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="9a6c3-336">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="9a6c3-336">SIPREC Video</span></span>
    
-  <span data-ttu-id="9a6c3-337">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-337">SIPREC Voice</span></span> 
    
- <span data-ttu-id="9a6c3-338">Messaggistica immediata Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="9a6c3-338">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="9a6c3-339">Video Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="9a6c3-339">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="9a6c3-340">Chiamate Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="9a6c3-340">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="9a6c3-341">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-341">Speakerbus Voice</span></span>
    
- <span data-ttu-id="9a6c3-342">Video SIP/H.323 standard</span><span class="sxs-lookup"><span data-stu-id="9a6c3-342">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="9a6c3-343">Chiamate SIP/H.323 standard</span><span class="sxs-lookup"><span data-stu-id="9a6c3-343">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="9a6c3-344">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="9a6c3-344">Truphone Voice</span></span>
    
- <span data-ttu-id="9a6c3-345">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="9a6c3-345">TwistedPair Radio</span></span>
    
- <span data-ttu-id="9a6c3-346">Schermata di Computer Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="9a6c3-346">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="9a6c3-347">Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="9a6c3-347">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="9a6c3-348">Di seguito sono riportati i passaggi per la creazione e la configurazione di una cassetta postale di dati di terze parti per l'importazione di dati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-348">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="9a6c3-349">Come spiegato in precedenza, gli elementi vengono importati nella cassetta postale se il connettore partner non è in grado di mappare l'ID utente dell'elemento a un account utente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-349">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 **<span data-ttu-id="9a6c3-350">Completare queste attività nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9a6c3-350">Complete these tasks in the Microsoft 365 admin center</span></span>**
  
1. <span data-ttu-id="9a6c3-351">Creare un nuovo account utente in Office 365 e assegnargli una licenza di Exchange Online piano 2; vedere [aggiungere utenti a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-351">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="9a6c3-352">È necessaria una licenza di piano 2 per attivare il blocco per controversia legale o abilitare una cassetta postale di archiviazione con una quota illimitata.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-352">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="9a6c3-353">Aggiungere l'account utente per la cassetta postale dei dati di terze parti al ruolo **amministratore di Exchange** in Office 365; Per ulteriori informazioni, vedere [assegnare ruoli di amministratore in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-353">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9a6c3-354">Annotare le credenziali per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-354">Write down the credentials for this user account.</span></span> <span data-ttu-id="9a6c3-355">È necessario fornirle al partner, come descritto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-355">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 **<span data-ttu-id="9a6c3-356">Completare queste attività nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="9a6c3-356">Complete these tasks in the Exchange admin center</span></span>**
  
1. <span data-ttu-id="9a6c3-357">Nascondere la cassetta postale dei dati di terze parti nella rubrica e negli altri elenchi di indirizzi dell'organizzazione. vedere [gestire le cassette postali degli utenti](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-357">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="9a6c3-358">In alternativa, è possibile eseguire il comando di PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-358">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="9a6c3-359">Assegnare l'autorizzazione **FullAccess** alla cassetta postale dei dati di terze parti in modo che gli amministratori o i responsabili della conformità possano aprire la cassetta postale dei dati di terze parti nel client desktop di Outlook. vedere [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-359">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="9a6c3-360">Abilitare le seguenti funzionalità di Office 365 correlate alla conformità per la cassetta postale dei dati di terze parti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-360">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="9a6c3-361">Abilitare la cassetta postale di archiviazione; vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-361">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="9a6c3-362">In questo modo sarà possibile liberare lo spazio di archiviazione nella cassetta postale principale impostando un criterio di archiviazione che consente di spostare gli elementi di dati di terze parti nella cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-362">This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="9a6c3-363">In questo modo si otterrà uno spazio di archiviazione illimitato per i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-363">This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="9a6c3-364">Abilitare il blocco per controversia legale nella cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-364">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="9a6c3-365">È anche possibile applicare un criterio di conservazione di Office 365 nel centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-365">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="9a6c3-366">Se si inserisce questa cassetta postale in attesa, verranno mantenuti gli elementi di dati di terze parti (a tempo indeterminato o per una durata specificata) e impedire che vengano eliminati dalla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-366">Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="9a6c3-367">Vedere uno dei seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-367">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="9a6c3-368">Blocco per controversia legale di una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="9a6c3-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="9a6c3-369">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="9a6c3-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="9a6c3-370">Abilitare la registrazione di controllo della cassetta postale per l'accesso del proprietario, di un delegato e dell'amministratore alla cassetta postale dei dati di terze parti; vedere [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-370">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="9a6c3-371">In questo modo è possibile controllare tutte le attività eseguite da qualsiasi utente che abbia accesso alla cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-371">This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="9a6c3-372">Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="9a6c3-372">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="9a6c3-373">Il passaggio successivo consiste nel configurare cassette postali degli utenti per supportare i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-373">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="9a6c3-374">Completare queste attività utilizzando l'interfaccia di amministrazione di Exchange o utilizzando i cmdlet di Windows PowerShell corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-374">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="9a6c3-375">Abilitare la cassetta postale di archiviazione per ogni utente; vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-375">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="9a6c3-376">Inserire le cassette postali degli utenti sul blocco per controversia legale o applicare un criterio di conservazione di Office 365; vedere uno dei seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-376">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="9a6c3-377">Blocco per controversia legale di una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="9a6c3-377">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="9a6c3-378">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="9a6c3-378">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="9a6c3-379">Come precedentemente illustrato, quando si abilita un blocco delle cassette postali, è possibile impostare una durata per definire quanto tempo devono essere conservati gli elementi dell'origine dati di terze parti oppure è possibile scegliere di conservare gli elementi per un periodo di tempo indeterminato.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-379">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="9a6c3-380">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="9a6c3-380">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="9a6c3-381">Il passaggio finale consiste nel fornire al partner le informazioni seguenti affinché sia in grado di configurare il connettore per connettersi all'organizzazione di Office 365 e importare i dati nelle cassette postali degli utenti e nella cassetta postale dei dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-381">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="9a6c3-382">Endpoint utilizzato per la connessione al servizio di Azure in Office 365:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-382">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="9a6c3-383">Credenziali di accesso (ID utente e password di Office 365) della cassetta postale di dati di terze parti creata al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-383">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="9a6c3-384">Queste credenziali sono necessarie affinché il connettore partner possa accedere e importare gli elementi nelle cassette postali degli utenti e nella cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-384">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="9a6c3-385">Passaggio 5: registrare il connettore di dati di terze parti in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9a6c3-385">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="9a6c3-386">A partire da settembre 30, 2018, il servizio di Azure in Office 365 inizierà a utilizzare l'autenticazione moderna in Exchange Online per autenticare i connettori di dati di terze parti che tentano di connettersi all'organizzazione di Office 365 per importare i dati.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-386">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="9a6c3-387">La causa di questa modifica consiste nel fatto che l'autenticazione moderna fornisce maggiore sicurezza rispetto al metodo corrente, basato sulla whitelist di connettori di terze parti che utilizzano l'endpoint descritto in precedenza per la connessione al servizio Azure.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-387">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="9a6c3-388">Per abilitare un connettore di dati di terze parti per la connessione a Office 365 utilizzando il nuovo metodo di autenticazione moderno, un amministratore dell'organizzazione di Office 365 deve acconsentire a registrare il connettore come applicazione di servizio attendibile in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-388">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="9a6c3-389">Per eseguire questa operazione, è necessario accettare una richiesta di autorizzazione per consentire al connettore di accedere ai dati dell'organizzazione in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-389">This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="9a6c3-390">Dopo aver accettato la richiesta, il connettore di dati di terze parti viene aggiunto come applicazione Enterprise ad Azure Active Directory e rappresentato come entità di servizio.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-390">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="9a6c3-391">Per ulteriori informazioni sul processo di consenso, vedere [tenant admin consenso](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-391">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="9a6c3-392">Di seguito sono riportati i passaggi per accedere e accettare la richiesta di registrazione del connettore:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-392">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="9a6c3-393">Accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di un amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-393">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="9a6c3-394">Verrà visualizzata la finestra di dialogo seguente.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-394">The following dialog box is displayed.</span></span> <span data-ttu-id="9a6c3-395">È possibile espandere le carriere per esaminare le autorizzazioni che verranno assegnate al connettore.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-395">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/>![Viene visualizzata la finestra di dialogo delle richieste di autorizzazione](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. <span data-ttu-id="9a6c3-397">Fare clic su **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-397">Click **Accept**.</span></span>

<span data-ttu-id="9a6c3-398">Dopo aver accettato la richiesta, viene visualizzato il [portale di Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="9a6c3-398">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="9a6c3-399">Per visualizzare l'elenco delle applicazioni per l'organizzazione, fare clic su applicazioni di **Azure Active Directory** > **Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-399">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="9a6c3-400">Il connettore di dati di terze parti di Office 365 è elencato nel Blade **applicazioni Enterprise** .</span><span class="sxs-lookup"><span data-stu-id="9a6c3-400">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a6c3-401">Dopo il 30 settembre 2018, i dati di terze parti non verranno più importati nelle cassette postali dell'organizzazione se non si registra un connettore di dati di terze parti in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-401">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="9a6c3-402">Nota i connettori di dati di terze parti esistenti (quelli creati prima del 30 settembre 2018) devono essere registrati anche in Azure Active Directory attenendosi alla procedura descritta nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-402">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="9a6c3-403">Revoca del consenso per un connettore di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="9a6c3-403">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="9a6c3-404">Dopo che l'organizzazione ha acconsentito alla richiesta di autorizzazione per la registrazione di un connettore di dati di terze parti in Azure Active Directory, l'organizzazione può revocare il consenso in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-404">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="9a6c3-405">Tuttavia, la revoca del consenso per un connettore significherà che i dati provenienti dall'origine dati di terze parti non verranno più importati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-405">However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="9a6c3-406">Per revocare il consenso per un connettore di dati di terze parti, è possibile eliminare l'applicazione (eliminando l'entità servizio corrispondente) da Azure Active Directory utilizzando il Blade **applicazioni Enterprise** nel portale di Azure o utilizzando il [ Remove-MsolServicePrincipal viene](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-406">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="9a6c3-407">È inoltre possibile utilizzare il cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-407">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="9a6c3-408">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="9a6c3-408">More information</span></span>

- <span data-ttu-id="9a6c3-409">Come illustrato in precedenza, gli elementi provenienti da origini dati di terze parti vengono importati nelle cassette postali di Exchange come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-409">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="9a6c3-410">Il connettore partner importa l'elemento utilizzando uno schema richiesto dall'API di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-410">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="9a6c3-411">Nella tabella seguente vengono descritte le proprietà del messaggio di un elemento di un'origine dati di terze parti dopo che è stato importato in una cassetta postale di Exchange come messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-411">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="9a6c3-412">Nella tabella viene indicato anche se la proprietà del messaggio è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-412">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="9a6c3-413">È necessario popolare le proprietà obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-413">Mandatory properties must be populated.</span></span> <span data-ttu-id="9a6c3-414">Se un elemento è mancante di una proprietà obbligatoria, non verrà importato in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-414">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="9a6c3-415">Il processo di importazione restituirà un messaggio di errore che spiega perché un elemento non è stato importato e la proprietà non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-415">The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |**<span data-ttu-id="9a6c3-416">Proprietà del messaggio</span><span class="sxs-lookup"><span data-stu-id="9a6c3-416">Message property</span></span>**|**<span data-ttu-id="9a6c3-417">Obbligatorio?</span><span class="sxs-lookup"><span data-stu-id="9a6c3-417">Mandatory?</span></span>**|**<span data-ttu-id="9a6c3-418">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a6c3-418">Description</span></span>**|**<span data-ttu-id="9a6c3-419">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="9a6c3-419">Example value</span></span>**|
    |:-----|:-----|:-----|:-----|
    |**<span data-ttu-id="9a6c3-420">Da</span><span class="sxs-lookup"><span data-stu-id="9a6c3-420">FROM</span></span>** <br/> |<span data-ttu-id="9a6c3-421">Sì</span><span class="sxs-lookup"><span data-stu-id="9a6c3-421">Yes</span></span>  <br/> |<span data-ttu-id="9a6c3-422">L'utente che ha originariamente creato o inviato l'elemento nell'origine dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-422">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="9a6c3-423">Il connettore partner tenterà di mappare l'ID utente dall'elemento di origine (ad esempio un handle Twitter) a un account utente di Office 365 per tutti i partecipanti (utenti nei campi da e a).</span><span class="sxs-lookup"><span data-stu-id="9a6c3-423">The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="9a6c3-424">Verrà importata una copia del messaggio nella cassetta postale di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-424">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="9a6c3-425">Se non è possibile eseguire il mapping di nessuno dei partecipanti dall'elemento a un account utente di Office 365, l'elemento verrà importato nella cassetta postale di archiviazione di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-425">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="9a6c3-426">Il partecipante identificato come mittente dell'elemento deve disporre di una cassetta postale attiva nell'organizzazione di Office 365 in cui l'elemento viene importato.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-426">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="9a6c3-427">In caso contrario, viene restituito l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-427">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**<span data-ttu-id="9a6c3-428">A</span><span class="sxs-lookup"><span data-stu-id="9a6c3-428">TO</span></span>** <br/> |<span data-ttu-id="9a6c3-429">Sì</span><span class="sxs-lookup"><span data-stu-id="9a6c3-429">Yes</span></span>  <br/> |<span data-ttu-id="9a6c3-430">L'utente che ha ricevuto un elemento, se applicabile per un elemento nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-430">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |**<span data-ttu-id="9a6c3-431">Oggetto</span><span class="sxs-lookup"><span data-stu-id="9a6c3-431">SUBJECT</span></span>** <br/> |<span data-ttu-id="9a6c3-432">No</span><span class="sxs-lookup"><span data-stu-id="9a6c3-432">No</span></span>  <br/> |<span data-ttu-id="9a6c3-433">L'oggetto dell'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-433">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**<span data-ttu-id="9a6c3-434">Data</span><span class="sxs-lookup"><span data-stu-id="9a6c3-434">DATE</span></span>** <br/> |<span data-ttu-id="9a6c3-435">Sì</span><span class="sxs-lookup"><span data-stu-id="9a6c3-435">Yes</span></span>  <br/> |<span data-ttu-id="9a6c3-436">La data in cui l'elemento è stato originariamente creato o inserito nell'origine dati del cliente; ad esempio, la data in cui è stato twittato un messaggio di Twitter.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-436">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |**<span data-ttu-id="9a6c3-437">CORPO</span><span class="sxs-lookup"><span data-stu-id="9a6c3-437">BODY</span></span>** <br/> |<span data-ttu-id="9a6c3-438">No</span><span class="sxs-lookup"><span data-stu-id="9a6c3-438">No</span></span>  <br/> |<span data-ttu-id="9a6c3-439">Il contenuto del messaggio o del post.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-439">The contents of the message or post.</span></span> <span data-ttu-id="9a6c3-440">Per alcune origini dati, il contenuto di questa proprietà può corrispondere al contenuto della proprietà **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-440">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="9a6c3-441">Durante il processo di importazione, il connettore partner tenterà di mantenere la massima fedeltà possibile rispetto all'origine del contenuto.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-441">During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="9a6c3-442">Se possibile, i file, gli elementi grafici o altri contenuti del corpo dell'elemento di origine sono inclusi in questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-442">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="9a6c3-443">In caso contrario, il contenuto dell'elemento di origine è incluso nella proprietà **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-443">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="9a6c3-444">Il contenuto di questa proprietà dipenderà dal connettore del partner e dalla funzionalità della piattaforma di origine.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-444">The contents of this property will depend on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**<span data-ttu-id="9a6c3-445">ALLEGATO</span><span class="sxs-lookup"><span data-stu-id="9a6c3-445">ATTACHMENT</span></span>** <br/> |<span data-ttu-id="9a6c3-446">No</span><span class="sxs-lookup"><span data-stu-id="9a6c3-446">No</span></span>  <br/> |<span data-ttu-id="9a6c3-447">Se un elemento nell'origine dati, ad esempio un tweet in Twitter o una conversazione di messaggistica istantanea, ha un file allegato o include immagini, la connessione del partner tenterà innanzitutto di includere gli allegati nella proprietà **Body** .</span><span class="sxs-lookup"><span data-stu-id="9a6c3-447">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="9a6c3-448">Se non è possibile, allora viene aggiunto alla proprietà \* \* ATTACHMENT \* \*.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-448">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="9a6c3-449">Altri esempi di allegati sono i Like su Facebook, i metadati dell'origine del contenuto e le risposte a un messaggio o a un post.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-449">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |**<span data-ttu-id="9a6c3-450">MESSAGECLASS</span><span class="sxs-lookup"><span data-stu-id="9a6c3-450">MESSAGECLASS</span></span>** <br/> |<span data-ttu-id="9a6c3-451">Sì</span><span class="sxs-lookup"><span data-stu-id="9a6c3-451">Yes</span></span>  <br/> | <span data-ttu-id="9a6c3-452">Si tratta di una proprietà multivalore, che viene creata e compilata dal connettore partner.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-452">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="9a6c3-453">Il formato di questa proprietà è `IPM.NOTE.Source.Event`.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-453">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="9a6c3-454">(Questa proprietà deve iniziare con `IPM.NOTE`; questo formato è simile a quello della classe `IPM.NOTE.X` Message). Questa proprietà include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-454">(This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/>`Source` <span data-ttu-id="9a6c3-455">-Indica l'origine dati di terze parti; ad esempio, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-455">- Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  `Event` <span data-ttu-id="9a6c3-456">-Indica il tipo di attività eseguita nell'origine dati di terze parti che ha prodotto gli elementi; ad esempio, un tweet in Twitter o un post in Facebook.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-456">- Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="9a6c3-457">Gli eventi sono specifici per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-457">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="9a6c3-458">Uno scopo di questa proprietà risiede nel filtrare gli elementi specifici in base all'origine dati in cui un elemento ha avuto origine o in base al tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-458">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="9a6c3-459">In una ricerca eDiscovery, ad esempio, è possibile creare una query di ricerca per trovare tutti i tweet pubblicati da un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-459">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="9a6c3-460">Quando gli elementi vengono importati correttamente nelle cassette postali di Office 365, viene restituito un identificatore univoco al chiamante come parte della risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-460">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="9a6c3-461">Questo identificatore, denominato `x-IngestionCorrelationID`, può essere utilizzato per la risoluzione dei problemi successivi da parte di partner per il monitoraggio end-to-end degli elementi.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-461">This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="9a6c3-462">Si consiglia di raccogliere queste informazioni e registrarle nel modo più appropriato.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-462">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="9a6c3-463">Di seguito è riportato un esempio di una risposta HTTP che mostra l'identificatore:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-463">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="9a6c3-464">È possibile utilizzare lo strumento di ricerca contenuto nel centro sicurezza e conformità per cercare gli elementi importati nelle cassette postali di Office 365 da un'origine dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-464">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="9a6c3-465">Per eseguire la ricerca in modo specifico per questi elementi importati, è possibile utilizzare le seguenti coppie proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-465">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="9a6c3-466">**`kind:externaldata`**-Utilizzare questa coppia proprietà-valore per eseguire la ricerca in tutti i tipi di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-466">**`kind:externaldata`** - Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="9a6c3-467">Ad esempio, per cercare gli elementi importati da un'origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query `kind:externaldata AND subject:contoso`di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-467">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="9a6c3-468">**`itemclass:ipm.externaldata.<third-party data type>`**-Utilizzare questa coppia proprietà-valore per cercare solo un tipo di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-468">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="9a6c3-469">Ad esempio, per cercare solo i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query `itemclass:ipm.externaldata.Facebook* AND subject:contoso`di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="9a6c3-469">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="9a6c3-470">Per un elenco completo dei valori da utilizzare per i tipi di dati di terze `itemclass` parti per la proprietà, vedere [utilizzare la ricerca contenuto per cercare i dati di terze parti che sono stati importati in Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="9a6c3-470">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="9a6c3-471">Per ulteriori informazioni sull'utilizzo di Ricerca contenuto e sulla creazione di query di ricerca con parole chiave, vedere:</span><span class="sxs-lookup"><span data-stu-id="9a6c3-471">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="9a6c3-472">Ricerca contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="9a6c3-472">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="9a6c3-473">Query delle parole chiave e condizioni di ricerca per ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="9a6c3-473">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
