---
title: Traccia dei messaggi nel centro sicurezza & Compliance
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: Gli amministratori possono utilizzare la traccia dei messaggi nel centro sicurezza & Compliance per scoprire cosa è successo ai messaggi.
ms.openlocfilehash: 95682b02f50996594650ac5d3aebf18f795efd65
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341567"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="da2b5-103">Traccia dei messaggi nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="da2b5-103">Message trace in the Security & Compliance Center</span></span>

<span data-ttu-id="da2b5-p101">La traccia dei messaggi nel centro sicurezza & Compliance segue i messaggi di posta elettronica durante il viaggio nell'organizzazione di Exchange Online. È possibile determinare se un messaggio è stato ricevuto, rifiutato, posticipato o recapitato dal servizio. Vengono inoltre illustrate le azioni eseguite sul messaggio prima del raggiungimento dello stato finale.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p101">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization. You can determine if a message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="da2b5-p102">La traccia dei messaggi nel centro sicurezza & Compliance migliora dopo la traccia del messaggio disponibile nell'interfaccia di amministrazione di Exchange (EAC). È possibile utilizzare le informazioni della traccia dei messaggi per rispondere in modo efficiente alle domande degli utenti su cosa è successo ai propri messaggi, risolvere i problemi relativi al flusso di posta e convalidare le modifiche dei criteri.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p102">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC). You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="da2b5-109">Aprire la traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="da2b5-109">Open message trace</span></span>

1. <span data-ttu-id="da2b5-110">[Accedere a Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con il proprio account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-110">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="da2b5-111">Selezionare l'icona di avvio delle app ![Icona di avvio delle app di Office 365](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) nell'angolo in alto a sinistra e scegliere **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="da2b5-111">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="da2b5-112">Nella barra di spostamento in basso a sinistra, espandere interfaccia di **Amministrazione** e selezionare **sicurezza & Compliance**.</span><span class="sxs-lookup"><span data-stu-id="da2b5-112">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="da2b5-113">Nella pagina **sicurezza _AMP_ conformità** visualizzata, espandere flusso di **posta**e selezionare **traccia messaggi**.</span><span class="sxs-lookup"><span data-stu-id="da2b5-113">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="da2b5-114">Pagina di traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="da2b5-114">Message trace page</span></span>

<span data-ttu-id="da2b5-p103">Da qui è possibile avviare una nuova traccia predefinita facendo clic sul pulsante **Start a Trace** . In questo modo verranno ricercati tutti i messaggi per tutti i mittenti e i destinatari negli ultimi due giorni. In alternativa, è possibile utilizzare una delle query archiviate dalle categorie di query disponibili ed eseguirle così come sono oppure utilizzarle come punti di partenza per le proprie query:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p103">From here you can start a new default trace by clicking on the **Start a trace** button. This will search for all messages for all senders and recipients for the last two days. Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="da2b5-118">**Query predefinite**: query incorporate fornite da Office 365.</span><span class="sxs-lookup"><span data-stu-id="da2b5-118">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="da2b5-119">**Query personalizzate**: query salvate dagli amministratori dell'organizzazione per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="da2b5-119">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="da2b5-p104">**Query**autosaved: le ultime dieci query eseguite più di recente. Questo elenco semplifica la scelta del punto in cui è stato interrotto.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p104">**Autosaved queries**: The last ten most recently run queries. This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="da2b5-122">Anche in questa pagina è disponibile una sezione per i **report scaricabili** per le richieste inviate, nonché i report stessi quando sono disponibili per il download.</span><span class="sxs-lookup"><span data-stu-id="da2b5-122">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="da2b5-123">Opzioni per una nuova traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="da2b5-123">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="da2b5-124">Filtrare in base a mittenti e destinatari</span><span class="sxs-lookup"><span data-stu-id="da2b5-124">Filter by senders and recipients</span></span>

<span data-ttu-id="da2b5-125">I valori predefiniti sono **tutti i mittenti** e **tutti i destinatari**, ma è possibile utilizzare i campi seguenti per filtrare i risultati:</span><span class="sxs-lookup"><span data-stu-id="da2b5-125">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="da2b5-p105">**Da queste persone**: fare clic in questo campo per selezionare uno o più mittenti dall'organizzazione. È anche possibile iniziare a digitare un nome e gli elementi nell'elenco verranno filtrati in base a ciò che è stato digitato, analogamente alla modalità di funzionamento di una pagina di ricerca.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p105">**By these people**: Click in this field to select one or more senders from your organization. You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="da2b5-128">**A queste persone**: fare clic in questo campo per selezionare uno o più destinatari nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-128">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

<span data-ttu-id="da2b5-p106">È inoltre possibile digitare gli indirizzi di posta elettronica di mittenti e destinatari esterni. I caratteri jolly sono supportati`*@contoso.com` ( `scot?@contoso.com`o), ma non è possibile utilizzare più voci con caratteri jolly nello stesso campo contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p106">You can also type the email addresses of external senders and recipients. Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>

### <a name="time-range"></a><span data-ttu-id="da2b5-131">Intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="da2b5-131">Time range</span></span>

<span data-ttu-id="da2b5-p107">Il valore predefinito è **2 giorni**, ma è possibile specificare intervalli di data/ora fino a 90 giorni. Quando si utilizzano intervalli di data/ora, prendere in considerazione i seguenti problemi:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p107">The default value is **2 days**, but you can specify date/time ranges of up to 90 days. When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="da2b5-p108">Per impostazione predefinita, è possibile selezionare l'intervallo di tempo in visualizzazione **Slider** utilizzando una linea temporale. È possibile selezionare solo le impostazioni giorno o ora visualizzate. Se si tenta di selezionare un valore tra i valori interattivi, la bolla iniziale/finale verrà agganciata all'impostazione visualizzata più vicina.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p108">By default, you select the time range in **Slider** view using a time line. You can only select the day or time settings that are displayed. Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![Intervallo di tempo per il dispositivo di scorrimento in una nuova traccia dei messaggi nel centro conformità di sicurezza di &](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="da2b5-p109">Tuttavia, è anche possibile passare alla visualizzazione **personalizzata** in cui è possibile specificare i valori di data e ora di **inizio** e di **fine** (incluse le ore) ed è anche possibile selezionare il **fuso orario** per l'intervallo data/ora. Si noti che l'impostazione del **fuso orario** si applica sia agli input di query sia ai risultati delle query.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p109">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range. Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![Un intervallo di tempo personalizzato in una nuova traccia dei messaggi nel centro sicurezza & Compliance](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="da2b5-p110">Per 10 o meno giorni, i risultati sono disponibili istantaneamente come \*\*\*\* report riepilogativo. Se si specifica un intervallo di tempo pari leggermente superiore a 10 giorni, i risultati verranno posticipati perché sono disponibili solo come file CSV scaricabile ( **Riepilogo avanzato** o rapporti estesi \*\*\*\* ).</span><span class="sxs-lookup"><span data-stu-id="da2b5-p110">For 10 days or less, the results are available instantly as a **Summary** report. If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="da2b5-143">Per ulteriori informazioni sui diversi tipi di report, vedere la sezione [scegliere il tipo di report](#choose-report-type) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="da2b5-143">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="da2b5-p111">**Nota**: i report di riepilogo e Extended Enhanced vengono preparati utilizzando i dati di traccia dei messaggi archiviati e possono richiedere fino a diverse ore prima che il report sia disponibile per il download. A seconda del numero di altri amministratori che hanno inoltrato le richieste di rapporto nello stesso momento, è possibile che si verifichi un ritardo prima dell'inizio dell'elaborazione per la richiesta in coda.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p111">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="da2b5-p112">Il salvataggio di una query in visualizzazione **Slider** consente di salvare l'intervallo di tempo relativo (ad esempio, 3 giorni da oggi). Il salvataggio di una query nella visualizzazione **personalizzata** consente di salvare l'intervallo di data/ora assoluto (ad esempio, 2018-05-06 13:00 a 2018-05-08 18:00).</span><span class="sxs-lookup"><span data-stu-id="da2b5-p112">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today). Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="da2b5-148">Altre opzioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="da2b5-148">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="da2b5-149">Stato del reCapito</span><span class="sxs-lookup"><span data-stu-id="da2b5-149">Delivery status</span></span>

<span data-ttu-id="da2b5-150">È possibile lasciare il valore predefinito **tutti** selezionati oppure è possibile selezionare uno dei seguenti valori per filtrare i risultati:</span><span class="sxs-lookup"><span data-stu-id="da2b5-150">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="da2b5-151">\*\*\*\* Recapitato: il messaggio è stato correttamente recapitato alla destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="da2b5-151">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="da2b5-152">**In sospeso**: il recapito del messaggio viene tentato o ritentato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-152">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="da2b5-153">**Expanded**: un destinatario del gruppo di distribuzione è stato espanso prima del recapito ai singoli membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="da2b5-153">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="da2b5-154">**Errore**: il messaggio non è stato recapitato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-154">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="da2b5-p113">\*\*\*\* In quarantena: il messaggio è stato messo in quarantena (come posta indesiderata, massa o phishing). Per ulteriori informazioni, vedere [messaggi di posta elettronica in quarantena in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span><span class="sxs-lookup"><span data-stu-id="da2b5-p113">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing). For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="da2b5-157">**Filtrato come posta**indesiderata: il messaggio è stato identificato come posta indesiderata e rifiutato o bloccato (non in quarantena).</span><span class="sxs-lookup"><span data-stu-id="da2b5-157">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="da2b5-p114">**Ottenere lo stato:** Il messaggio è stato ricevuto di recente da Office 365, ma non sono ancora disponibili altri dati sullo stato. Eseguire il controllo in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p114">**Getting status:** The message was recently received by Office 365, but no other status data is yet available. Check back in a few minutes.</span></span>

<span data-ttu-id="da2b5-p115">**Nota**: i valori **in sospeso, in** **quarantena**e **filtro come posta** indesiderata sono disponibili solo per le ricerche di meno di 10 giorni. È inoltre possibile che vi sia un ritardo di 5-10 minuti tra lo stato di recapito effettivo e quello riportato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p115">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days. Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="da2b5-162">ID messaggio</span><span class="sxs-lookup"><span data-stu-id="da2b5-162">Message ID</span></span>

<span data-ttu-id="da2b5-p116">Questo è l'ID del messaggio Internet (detto anche ID client) trovato nel campo di intestazione **Message-ID:** nell'intestazione del messaggio. Gli utenti possono fornire questo valore per esaminare i messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p116">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header. Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="da2b5-p117">Questo valore è costante per tutta la durata del messaggio. Per i messaggi creati in Office 365 o Exchange, il valore è nel formato `<GUID@ServerFQDN>`, incluse le parentesi angolari\< \>(). Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Altri sistemi di messaggistica possono utilizzare una sintassi o valori diversi. Questo valore deve essere univoco, ma non tutti i sistemi di posta elettronica seguono scrupolosamente questo requisito. Se il campo di intestazione **Message-ID:** non esiste o è vuoto per i messaggi in arrivo provenienti da origini esterne, viene assegnato un valore arbitrario.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p117">This value is constant for the lifetime of the message. For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>). For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Other messaging systems might use different syntax or values. This value is supposed to be unique, but not all email systems strictly follow this requirement. If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="da2b5-171">Quando si utilizza l' **ID messaggio** per filtrare i risultati, assicurarsi di includere la stringa completa, incluse le parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="da2b5-171">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="da2b5-172">Direction</span><span class="sxs-lookup"><span data-stu-id="da2b5-172">Direction</span></span>

<span data-ttu-id="da2b5-173">È possibile lasciare il valore predefinito **tutti** selezionati oppure è possibile selezionare in **ingresso** (messaggi inviati a destinatari nell'organizzazione) o in **uscita** (messaggi inviati dagli utenti dell'organizzazione) per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="da2b5-173">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="da2b5-174">Indirizzo IP del client originale</span><span class="sxs-lookup"><span data-stu-id="da2b5-174">Original client IP address</span></span>

<span data-ttu-id="da2b5-p118">È possibile archiviare i risultati in base all'indirizzo IP del client per esaminare i computer compromessi che inviano grandi quantità di posta indesiderata o malware. Anche se i messaggi possono sembrare provenienti da più mittenti, è probabile che nello stesso computer vengano generati tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p118">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware. Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="da2b5-177">**Nota**: le informazioni sull'indirizzo IP del client sono disponibili solo per 10 giorni ed è disponibile solo nei rapporti di riepilogo \*\*\*\* o Extended **Enhanced** (file CSV scaricabili).</span><span class="sxs-lookup"><span data-stu-id="da2b5-177">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="da2b5-178">Scegliere il tipo di rapporto</span><span class="sxs-lookup"><span data-stu-id="da2b5-178">Choose report type</span></span>

<span data-ttu-id="da2b5-179">I tipi di report disponibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="da2b5-179">The available report types are:</span></span>

- <span data-ttu-id="da2b5-p119">**Riepilogo**: disponibile se l'intervallo di tempo è inferiore a 10 giorni e non richiede ulteriori opzioni di filtro. I risultati sono disponibili quasi immediatamente dopo aver fatto clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p119">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options. The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="da2b5-p120">**Riepilogo avanzato** o **esteso**: questi rapporti sono disponibili solo come file CSV scaricabili e richiedono una o più delle seguenti opzioni di filtro, indipendentemente dall'intervallo di tempo: **da queste persone**, **a queste persone**o \*\* ID messaggio\*\*. È possibile utilizzare i caratteri jolly per i mittenti o i destinatari, \*ad esempio @contoso. com.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p120">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**. You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="da2b5-184">**Note**:</span><span class="sxs-lookup"><span data-stu-id="da2b5-184">**Notes**:</span></span>

- <span data-ttu-id="da2b5-p121">Il riepilogo avanzato e i report esTesi vengono preparati utilizzando i dati di traccia dei messaggi archiviati e possono richiedere fino a diverse ore prima che il report sia disponibile per il download. A seconda del numero di altri amministratori che hanno inoltrato le richieste di rapporto nello stesso momento, è possibile che si verifichi un ritardo prima che la richiesta in coda inizi a essere elaborata.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p121">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="da2b5-187">Anche se è possibile selezionare un riepilogo avanzato o un report esteso per qualsiasi intervallo di data/ora, in genere le ultime quattro ore di dati archiviati non saranno ancora disponibili per questi due tipi di report.</span><span class="sxs-lookup"><span data-stu-id="da2b5-187">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="da2b5-p122">Quando si fa clic su **Avanti**, viene visualizzata una pagina di riepilogo in cui sono elencate le opzioni di filtro selezionate, un titolo univoco (modificabile) per il report e l'indirizzo di posta elettronica che riceve la notifica al termine della traccia dei messaggi (modificabile anche e deve trovarsi in uno dei domini accettati dell'organizzazione. Fare clic su **prepara rapporto** per inviare la traccia dei messaggi. Nella pagina di **traccia dei messaggi** principale, è possibile visualizzare lo stato del report nella sezione **report scaricabili** .</span><span class="sxs-lookup"><span data-stu-id="da2b5-p122">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains). Click **Prepare report** to submit the message trace. On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="da2b5-191">Per ulteriori informazioni sulle informazioni restituite nei diversi tipi di report, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="da2b5-191">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="da2b5-192">Risultati della traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="da2b5-192">Message trace results</span></span>

<span data-ttu-id="da2b5-p123">I diversi tipi di report restituiscono livelli di informazioni diversi. Le informazioni disponibili nei diversi rapporti sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p123">The different report types return different levels of information. The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="da2b5-195">Output del rapporto riepilogativo</span><span class="sxs-lookup"><span data-stu-id="da2b5-195">Summary report output</span></span>

<span data-ttu-id="da2b5-196">Dopo aver eseguito la traccia dei messaggi, i risultati verranno elencati, ordinati in base alla data/ora decrescente (la più recente è la prima).</span><span class="sxs-lookup"><span data-stu-id="da2b5-196">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![Risultati del rapporto riepilogativo per la traccia dei messaggi nel centro sicurezza & Compliance](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="da2b5-198">Il rapporto riepilogativo contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da2b5-198">The summary report contains the following information:</span></span>

- <span data-ttu-id="da2b5-199">**Data**: la data e l'ora in cui il messaggio è stato ricevuto dal servizio, utilizzando il fuso orario UTC configurato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-199">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="da2b5-200">**Sender**: l'indirizzo di posta elettronica del mittente (*dominio\*\*alias*@).</span><span class="sxs-lookup"><span data-stu-id="da2b5-200">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="da2b5-p124">**Destinatario**: l'indirizzo di posta elettronica del destinatario o dei destinatari. Per un messaggio inviato a più destinatari, è presente una riga per ogni destinatario. Se il destinatario è un gruppo di distribuzione, un gruppo di distribuzione dinamico o un gruppo di sicurezza abilitato alla posta elettronica, il gruppo sarà il primo destinatario e quindi ogni membro del gruppo si trova su una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p124">**Recipient**: The email address of the recipient or recipients. For a message sent to multiple recipients, there's one line per recipient. If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="da2b5-204">**Subject**: i primi 256 caratteri del campo **Subject:** del messaggio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-204">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="da2b5-205">**Stato**: questi valori sono descritti nella sezione [stato](#delivery-status) di recapito.</span><span class="sxs-lookup"><span data-stu-id="da2b5-205">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="da2b5-p125">Per impostazione predefinita, i primi risultati di 250 sono caricati e prontamente disponibili. Quando si scorre verso il basso, si verifica una leggera pausa quando viene caricato il prossimo batch di risultati. Invece di scorrere, è possibile fare clic su **carica tutto** per caricare tutti i risultati fino a un massimo di 10.000.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p125">By default, the first 250 results are loaded and readily available. When you scroll down, there's a slight pause as the next batch of results are loaded. Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="da2b5-209">È possibile fare clic sulle intestazioni di colonna per ordinare i risultati in base ai valori della colonna in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="da2b5-209">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="da2b5-210">È possibile fare clic su **Filtra risultati** per filtrare i risultati in base a una o più colonne.</span><span class="sxs-lookup"><span data-stu-id="da2b5-210">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="da2b5-211">È possibile esportare i risultati dopo aver selezionato una o più righe facendo clic su **Esporta risultati** e quindi selezionando **Esporta tutti**i risultati, **Esporta i risultati caricati**o **Esporta selezionati**.</span><span class="sxs-lookup"><span data-stu-id="da2b5-211">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="da2b5-212">Individuare i record correlati per il messaggio</span><span class="sxs-lookup"><span data-stu-id="da2b5-212">Find related records for this message</span></span>

<span data-ttu-id="da2b5-p126">I record dei messaggi correlati sono record che condividono lo stesso ID messaggio. Tenere presente che anche un singolo messaggio inviato tra due persone può generare più record. Il numero di record aumenta quando il messaggio viene influenzato dall'espansione del gruppo di distribuzione, dall'inoltro, dalle regole del flusso di posta (note anche come regole di trasporto) e così via.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p126">Related message records are records that shared the same Message ID. Remember, even a single message sent between two people can generate multiple records. The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="da2b5-216">Dopo aver selezionato la casella di controllo di una riga, è possibile trovare i record correlati per il messaggio facendo clic sul pulsante **trova correlato** visualizzato oppure selezionando **altre opzioni** ![ulteriori](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **record correlati per il messaggio**.</span><span class="sxs-lookup"><span data-stu-id="da2b5-216">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="da2b5-217">Per ulteriori informazioni sull'ID del messaggio, vedere la sezione relativa all'ID del messaggio descritta in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="da2b5-217">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="da2b5-218">Dettagli di traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="da2b5-218">Message trace details</span></span>

<span data-ttu-id="da2b5-219">Nell'output del rapporto riepilogativo, è possibile visualizzare i dettagli relativi a un messaggio utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="da2b5-219">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="da2b5-220">Selezionare la riga (fare clic in un punto qualsiasi della riga tranne la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="da2b5-220">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="da2b5-221">Selezionare la casella di controllo della riga e fare clic su](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **altre opzioni** ![per **visualizzare i dettagli dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="da2b5-221">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![Dettagli dopo aver fatto doppio clic su una riga del rapporto riepilogativo risultati traccia messaggio nel centro sicurezza & Compliance](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="da2b5-223">I dettagli della traccia dei messaggi contengono le informazioni aggiuntive seguenti che non sono presenti nel rapporto riepilogativo:</span><span class="sxs-lookup"><span data-stu-id="da2b5-223">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="da2b5-p127">**Eventi messaggio**: questa sezione contiene classificazioni che consentono di categorizzare le azioni che il servizio assume sui messaggi. Alcuni degli eventi più interessanti che è possibile riscontrare sono:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p127">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages. Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="da2b5-226">**Receive**: il messaggio è stato ricevuto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-226">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="da2b5-227">**Send**: il messaggio è stato inviato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-227">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="da2b5-228">**Esito negativo**: il messaggio non è stato recapitato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-228">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="da2b5-229">**Recapita**: il messaggio è stato recapitato a una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="da2b5-229">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="da2b5-230">**Expand**: il messaggio è stato inviato a un gruppo di distribuzione espanso.</span><span class="sxs-lookup"><span data-stu-id="da2b5-230">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="da2b5-231">**Trasferimento**: i destinatari sono stati spostati in un messaggio di biforcati a causa della conversione del contenuto, dei limiti del destinatario del messaggio o degli agenti.</span><span class="sxs-lookup"><span data-stu-id="da2b5-231">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="da2b5-232">**Posticipare**: il recapito del messaggio è stato posticipato e potrebbe essere ritentato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="da2b5-232">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="da2b5-p128">**Risolto**: il messaggio è stato reindirizzato a un nuovo indirizzo del destinatario basato su una ricerca di Active Directory. In questo caso, l'indirizzo del destinatario originale viene elencato in una riga separata nella traccia dei messaggi insieme allo stato di recapito finale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p128">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up. When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="da2b5-235">Si noti che anche un messaggio non movimentato che è stato recapitato correttamente genererà più voci di **evento** nella traccia dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="da2b5-235">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="da2b5-236">**Ulteriori informazioni**: questa sezione contiene i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="da2b5-236">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="da2b5-p129">**ID messaggio**: questo valore è descritto nella sezione [ID messaggio](#message-id) descritta in precedenza in questo argomento. Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p129">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="da2b5-239">**Dimensione messaggio**</span><span class="sxs-lookup"><span data-stu-id="da2b5-239">**Message size**</span></span>

   - <span data-ttu-id="da2b5-p130">**Da IP**: l'indirizzo IP del computer in cui è stato inviato il messaggio. Per i messaggi in uscita inviati da Exchange Online, questo valore è vuoto.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p130">**From IP**: The IP address of the computer that sent the message. For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="da2b5-p131">**To IP**: l'indirizzo IP o gli indirizzi in cui il servizio ha tentato di recapitare il messaggio. Se il messaggio contiene più destinatari, vengono visualizzati. Per i messaggi in ingresso inviati a Exchange Online, questo valore è vuoto.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p131">**To IP**: The IP address or addresses where the service attempted to deliver the message. If the message has multiple recipients, these are displayed. For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="da2b5-245">Rapporti di riepilogo avanzati</span><span class="sxs-lookup"><span data-stu-id="da2b5-245">Enhanced summary reports</span></span>

<span data-ttu-id="da2b5-p132">I report di riepilogo avanzati disponibili (completati) sono disponibili nella sezione **report scaricabili** all'inizio della traccia dei messaggi. Nel report sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p132">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace. The following information is available in the report:</span></span>

- <span data-ttu-id="da2b5-248">**origin_timestamp**<sup>\*</sup>: la data e l'ora in cui il messaggio è stato ricevuto inizialmente dal servizio, utilizzando il fuso orario UTC configurato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-248">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="da2b5-249">**sender_address**: l'indirizzo di posta elettronica del mittente (*dominio\*\*alias*@).</span><span class="sxs-lookup"><span data-stu-id="da2b5-249">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="da2b5-p133">**Recipient_status**: lo stato del recapito del messaggio al destinatario. Se il messaggio è stato inviato a più destinatari, mostrerà tutti i destinatari e lo stato corrispondente per ognuno, nel formato: \<*stato*\>dell' *Indirizzo*\>##\<di posta elettronica. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p133">**Recipient_status**: The status of the delivery of the message to the recipient. If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>. For example:</span></span>

   - <span data-ttu-id="da2b5-253">**# #Receive, Send** indica che il messaggio è stato ricevuto dal servizio e che è stato inviato alla destinazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="da2b5-253">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="da2b5-254">**# #Receive, Fail** indica che il messaggio è stato ricevuto dal servizio ma il recapito alla destinazione desiderata non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="da2b5-254">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="da2b5-255">**# #Receive, Deliver** indica che il messaggio è stato ricevuto dal servizio e che è stato recapitato alla cassetta postale del destinatario.</span><span class="sxs-lookup"><span data-stu-id="da2b5-255">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="da2b5-256">**MESSAGE_SUBJECT**: i primi 256 caratteri del campo **Subject** del messaggio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-256">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="da2b5-257">**total_bytes**: la dimensione del messaggio in byte, inclusi gli allegati.</span><span class="sxs-lookup"><span data-stu-id="da2b5-257">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="da2b5-p134">**message_id**: questo valore è descritto nella sezione [ID messaggio](#message-id) descritta in precedenza in questo argomento. Ad esempio, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p134">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="da2b5-p135">**network_message_id**: un valore di ID messaggio univoco che persiste in tutte le copie del messaggio che potrebbe essere creato a causa della biforcazione o dell'espansione del gruppo di distribuzione. Un valore di esempio `1341ac7b13fb42ab4d4408cf7f55890f`è.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p135">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion. An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="da2b5-262">**original_client_ip**: l'indirizzo IP del client del mittente.</span><span class="sxs-lookup"><span data-stu-id="da2b5-262">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="da2b5-263">**direzionalità**: indica se il messaggio è stato inviato all'interno (1) all'organizzazione o se è stato inviato in uscita (2) dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-263">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="da2b5-p136">**connector_id**: il nome del connettore di origine o di destinazione. Per ulteriori informazioni sui connettori in Exchange Online, vedere [Configure Mail Flow using Connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="da2b5-p136">**connector_id**: The name of the source or destination connector. For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="da2b5-266">**delivery_priority**<sup>\*</sup>: indica se il messaggio è stato inviato con priorità **alta**, **bassa**o **normale** .</span><span class="sxs-lookup"><span data-stu-id="da2b5-266">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="da2b5-267"><sup>\*</sup>Queste proprietà sono disponibili solo in rapporti di riepilogo avanzati.</span><span class="sxs-lookup"><span data-stu-id="da2b5-267"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="da2b5-268">Rapporti esTesi</span><span class="sxs-lookup"><span data-stu-id="da2b5-268">Extended reports</span></span>

<span data-ttu-id="da2b5-p137">I report esTesi disponibili (completati) sono disponibili nella sezione **report scaricabili** all'inizio della traccia dei messaggi. Quasi tutte le informazioni provenienti da un rapporto riepilogativo avanzato sono disponibili in un report esteso (ad eccezione di **origin_timestamp** e **delivery_priority**). Le informazioni aggiuntive seguenti sono disponibili solo in un report esteso:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p137">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace. Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**). The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="da2b5-272">**Client_IP**: l'indirizzo IP del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-272">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="da2b5-273">**client_hostname**: nome host o FQDN del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-273">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="da2b5-274">**server_ip**: l'indirizzo IP del server di origine o di destinazione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-274">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="da2b5-275">**server_hostname**: il nome host o FQDN del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-275">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="da2b5-p138">**source_context**: informazioni aggiuntive associate al campo di **origine** . Per esempio:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p138">**source_context**: Extra information associated with the **source** field. For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="da2b5-p139">**origine**: componente di Exchange Online responsabile dell'evento. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p139">**source**: The Exchange Online component that's responsible for the event. For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="da2b5-280">**event_id**: corrispondono ai valori di **evento del messaggio** illustrati nella sezione [trova i record correlati per questo messaggio](#find-related-records-for-this-message) .</span><span class="sxs-lookup"><span data-stu-id="da2b5-280">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="da2b5-281">**internal_message_id**: identificatore del messaggio assegnato dal server Exchange Online che sta attualmente elaborando il messaggio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-281">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="da2b5-p140">**recipient_address**: gli indirizzi di posta elettronica dei destinatari del messaggio. Più indirizzi di posta elettronica sono separati dal carattere punto e virgola (;).</span><span class="sxs-lookup"><span data-stu-id="da2b5-p140">**recipient_address**: The email addresses of the message's recipients. Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="da2b5-284">**recipient_count**: il numero totale di destinatari nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-284">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="da2b5-285">**related_recipient_address**: utilizzato con `EXPAND`, `REDIRECT`ed `RESOLVE` eventi per visualizzare gli altri indirizzi di posta elettronica dei destinatari associati al messaggio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-285">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="da2b5-p141">**riferimento**: questo campo contiene informazioni aggiuntive per tipi specifici di eventi. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p141">**reference**: This field contains additional information for specific types of events. For example:</span></span>

   - <span data-ttu-id="da2b5-p142">**DSN**: contiene il collegamento al rapporto, ovvero il valore **message_id** della notifica sullo stato del recapito associato (noto anche come DSN, rapporto di mancato recapito, NDR o messaggio di rimbalzo) se un DSN viene generato dopo questo evento. Se si tratta di un messaggio DSN, questo campo contiene il valore **message_id** del messaggio originale per il quale è stato generato il DSN.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p142">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event. If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="da2b5-290">**Expand**: contiene il valore **related_recipient_address** dei messaggi correlati.</span><span class="sxs-lookup"><span data-stu-id="da2b5-290">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="da2b5-291">**Receive**: potrebbe contenere il valore **message_id** del messaggio correlato se il messaggio è stato generato da altri processi, ad esempio le regole di posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="da2b5-291">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="da2b5-292">**Send**: contiene il valore **internal_message_id** di eventuali messaggi DSN.</span><span class="sxs-lookup"><span data-stu-id="da2b5-292">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="da2b5-293">**Transfer**: contiene il valore **internal_message_id** del messaggio in fase di fork (ad esempio, tramite la conversione del contenuto, i limiti del destinatario del messaggio o gli agenti).</span><span class="sxs-lookup"><span data-stu-id="da2b5-293">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="da2b5-294">**MAILBOXRULE**: contiene il valore **internal_message_id** del messaggio in ingresso che ha causato la regola di posta in arrivo per generare il messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="da2b5-294">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="da2b5-295">Per tutti gli altri tipi di evento, questo campo in genere è vuoto.</span><span class="sxs-lookup"><span data-stu-id="da2b5-295">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="da2b5-p143">**return_path**: l'indirizzo di posta elettronica restituito specificato dal comando **mail from** che ha inviato il messaggio. Anche se questo campo non è mai vuoto, può avere il valore dell'indirizzo mittente nullo rappresentato come `<>`.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p143">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message. Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="da2b5-p144">**message_info**: ulteriori informazioni sul messaggio. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p144">**message_info**: Additional information about the message. For example:</span></span>

   - <span data-ttu-id="da2b5-p145">Data-ora di origine del messaggio in formato UTC `DELIVER` per `SEND` gli eventi e. La data-ora di origination è l'ora in cui il messaggio è stato immesso per la prima volta nell'organizzazione di Exchange Online. La data/ora UTC è rappresentata nel formato data/ora ISO 8601: `yyyy-mm-ddThh:mm:ss.fffZ`, Where `yyyy` = year, `mm` = month, `dd` = Day, `T` indica l'inizio del `hh` componente Time, = hour, `mm` = minute, `ss` = Second, `fff` = frazioni di secondo e `Z` significa `Zulu`, che è un altro modo per indicare l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p145">The message origination date-time in UTC for `DELIVER` and `SEND` events. The origination date-time is the time when the message first entered the Exchange Online organization. The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="da2b5-p146">Errori di autenticazione. Ad esempio, è possibile visualizzare il valore `11a` e il tipo di autenticazione utilizzato quando si è verificato l'errore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p146">Authentication errors. For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="da2b5-305">**tenant_id**: valore GUID che rappresenta l'organizzazione di Exchange Online (ad esempio, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span><span class="sxs-lookup"><span data-stu-id="da2b5-305">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="da2b5-306">**original_server_ip**: l'indirizzo IP del server originale.</span><span class="sxs-lookup"><span data-stu-id="da2b5-306">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="da2b5-p147">**custom_data**: contiene dati relativi a tipi di evento specifici. Per ulteriori informazioni, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p147">**custom_data**: Contains data related to specific event types. For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="da2b5-309">valori di custom_data</span><span class="sxs-lookup"><span data-stu-id="da2b5-309">custom_data values</span></span>

<span data-ttu-id="da2b5-p148">Il campo **custom_data** per un `AGENTINFO` evento viene utilizzato da una vasta gamma di agenti di Exchange Online per registrare i dettagli di elaborazione dei messaggi. Alcuni degli agenti più interessanti sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p148">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details. Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="da2b5-312">Agente filtro posta inDesiderata</span><span class="sxs-lookup"><span data-stu-id="da2b5-312">Spam filter agent</span></span>

<span data-ttu-id="da2b5-p149">Un valore **custom_data** che inizia con `S:SFA` è dell'agente filtro posta indesiderata. I dettagli della chiave sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p149">A **custom_data** value that starts with `S:SFA` is from the spam filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="da2b5-315">**Valore**</span><span class="sxs-lookup"><span data-stu-id="da2b5-315">**Value**</span></span>|<span data-ttu-id="da2b5-316">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="da2b5-316">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="da2b5-317">Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.</span><span class="sxs-lookup"><span data-stu-id="da2b5-317">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="da2b5-318">Il messaggio è stato contrassegnato come posta indesiderata dal filtro contenuto.</span><span class="sxs-lookup"><span data-stu-id="da2b5-318">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="da2b5-319">Le regole del filtro sono state ignorate e il messaggio è stato bloccato perché è stato originato da un mittente bloccato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-319">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="da2b5-p150">Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alle regole di trasporto, che lo contrassegnano automaticamente come indesiderato e che ignorano tutte le regole del filtro aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p150">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="da2b5-322">Per ulteriori informazioni sui diversi valori SCL e sul loro significato, vedere [Spam Confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span><span class="sxs-lookup"><span data-stu-id="da2b5-322">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="da2b5-p151">Il valore del livello di probabilità di phishing (PCL) del messaggio. Questi possono essere interpretati nello stesso modo in cui i valori SCL sono documentati nei [livelli di probabilità di posta](https://technet.microsoft.com/library/jj200686.aspx)indesiderata.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p151">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="da2b5-325">Il mittente del messaggio è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-325">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="da2b5-326">Il messaggio è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="da2b5-326">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="da2b5-327">Il messaggio è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-327">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="da2b5-328">Il messaggio è stato inviato alla cartella posta inDesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="da2b5-328">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="da2b5-p152">Il messaggio è stato instradato attraverso il pool di recapito ad alto rischio. Per ulteriori informazioni, vedere [pool di recapito ad alto rischio per i messaggi in uscita](https://technet.microsoft.com/library/jj200746.aspx).</span><span class="sxs-lookup"><span data-stu-id="da2b5-p152">The message was routed through the higher risk delivery pool. For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="da2b5-331">Il messaggio è stato instradato tramite un pool di recapito ad alto rischio.</span><span class="sxs-lookup"><span data-stu-id="da2b5-331">The message was routed through the normal outbound delivery pool.</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="da2b5-332">Indica una corrispondenza tra le regole relative alla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="da2b5-332">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="da2b5-333">Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-333">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="da2b5-334">La stringa HELO o EHLO del server di posta elettronica di connessione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-334">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="da2b5-335">Il record PTR dell'indirizzo IP del mittente, noto anche come indirizzo DNS inverso.</span><span class="sxs-lookup"><span data-stu-id="da2b5-335">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="da2b5-336">Un esempio di valore di **custom_data** per un messaggio filtrato per la posta indesiderata in questo modo:</span><span class="sxs-lookup"><span data-stu-id="da2b5-336">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="da2b5-337">Agente filtro antiMalware</span><span class="sxs-lookup"><span data-stu-id="da2b5-337">Malware filter agent</span></span>

<span data-ttu-id="da2b5-p153">Un valore **custom_data** che inizia con `S:AMA` è dell'agente di filtro antimalware. I dettagli della chiave sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p153">A **custom_data** value that starts with `S:AMA` is from the malware filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="da2b5-340">**Valore**</span><span class="sxs-lookup"><span data-stu-id="da2b5-340">**Value**</span></span>|<span data-ttu-id="da2b5-341">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="da2b5-341">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da2b5-342">`AMA=SUM|v=1|`o`AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="da2b5-342">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="da2b5-p154">Il messaggio è stato determinato per contenere malware. `SUM` indica che il malware potrebbe essere stato rilevato da un numero qualsiasi di motori. `EV` indica che il malware è stato rilevato da un motore specifico. Quando viene rilevato un malware da un motore, vengono attivate le azioni successive.</span><span class="sxs-lookup"><span data-stu-id="da2b5-p154">The message was determined to contain malware. `SUM` indicates the malware could've been detected by any number of engines. `EV` indicates the malware was detected by a specific engine. When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="da2b5-347">Il messaggio è stato sostituito.</span><span class="sxs-lookup"><span data-stu-id="da2b5-347">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="da2b5-348">Il messaggio è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-348">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="da2b5-349">Il messaggio è stato rinviato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-349">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="da2b5-350">Il messaggio è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-350">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="da2b5-351">Il messaggio è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-351">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="da2b5-352">Il messaggio è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-352">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="da2b5-353">Il messaggio è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-353">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="da2b5-354">Il messaggio è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-354">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="da2b5-355">Il messaggio è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-355">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="da2b5-356">Il nome del malware rilevato.</span><span class="sxs-lookup"><span data-stu-id="da2b5-356">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="da2b5-357">Il nome del file che contiene malware.</span><span class="sxs-lookup"><span data-stu-id="da2b5-357">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="da2b5-358">Un esempio di valore di **custom_data** per un messaggio che contiene malware è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="da2b5-358">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="da2b5-359">Agente delle regole di trasporto</span><span class="sxs-lookup"><span data-stu-id="da2b5-359">Transport Rule agent</span></span>

<span data-ttu-id="da2b5-p155">Un valore **custom_data** che inizia con`S:TRA` è compreso nell'agente della regola di trasporto per le regole del flusso di posta (note anche come regole di trasporto). I dettagli della chiave sono descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p155">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules). The key details are described in the following table:</span></span>

|<span data-ttu-id="da2b5-362">**Valore**</span><span class="sxs-lookup"><span data-stu-id="da2b5-362">**Value**</span></span>|<span data-ttu-id="da2b5-363">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="da2b5-363">**Description**</span></span>|
|:-----|:-----|
|`ETR|ruleId=<guid>`|<span data-ttu-id="da2b5-364">L'ID regola corrispondente.</span><span class="sxs-lookup"><span data-stu-id="da2b5-364">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="da2b5-365">Data e ora in formato UTC quando si è verificata la corrispondenza della regola.</span><span class="sxs-lookup"><span data-stu-id="da2b5-365">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="da2b5-p156">Azione applicata. Per un elenco delle azioni disponibili, vedere [Mail Flow Rule Actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span><span class="sxs-lookup"><span data-stu-id="da2b5-p156">The action that was applied. For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="da2b5-p157">Modalità della regola. I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="da2b5-p157">The mode of the rule. Valid values are: </span></span><br/><span data-ttu-id="da2b5-370">• **Enforce**: tutte le azioni della regola verranno applicate.</span><span class="sxs-lookup"><span data-stu-id="da2b5-370">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="da2b5-371">• **Test con suggerimenti per i criteri:**: tutte le azioni di suggerimento per i criteri verranno inviate, ma non verranno applicate altre azioni di applicazione.</span><span class="sxs-lookup"><span data-stu-id="da2b5-371">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="da2b5-372">• **Test senza suggerimenti**per i criteri: le azioni verranno elencate in un file di registro, tuttavia i mittenti non riceveranno alcuna notifica e le azioni di applicazione non verranno applicate.</span><span class="sxs-lookup"><span data-stu-id="da2b5-372">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="da2b5-373">Un esempio di valore di **custom_data** per i messaggi che soddisfano le condizioni di una regola del flusso di posta è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="da2b5-373">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
